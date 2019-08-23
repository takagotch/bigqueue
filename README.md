### bigqueue
---
https://github.com/bulldog2011/bigqueue

```java
public class MappedPageFactoryImpl implements IMappedPageFactory {
  
  private final static Logger logger = LoggerFactory.getLogger(MappedPageFactoryImpl.class);
  
  private int pageSize;
  
  private final Object mapLock = new Object();
  private final Map<Long, Object> pageCreationLockMap = new HashMap<Long, Object>();
  
  public static final String PAGE_FILE_NAME = "page";
  public static final String PAGE_FILE_SUFFIX = ".dat";
  
  private ILRUCache<Long, MapperPageImpl> cache;
  
  public MappedPageFactoryImpl(int pageSize, String pageDir, long cacheTTL) {
    this.pageSize = pageSize;
    this.pageDir = pageDir;
    this.ttl = cacheTTL;
    this.pageDirFile = new File(this.pageDir);
    if (!pageDirFile.exists()) {
      pageDirFile.mkdirs();
    }
    if (!this.pageDir.endsWith(File.separator)) {
      this.pageDir += File.separator;
    }
    this.pageFile = this.pageDir + PAGE_FILE_NAME + "-";
    this.cache = new LRUCacheImpl<Long, MappedPageImpl>();
  }
  
  public IMappedPag acquirePage(long index) throws IOException {
    MapperedPageImpl mpi = cache.get(index);
    if (mpi == null) {
      try {
      
      }
    }
  }
  
  
  
  
  
  @Override
  public long getBackPageFileSize9) {
    long totaSize = 0L;
    File[] pageFiles = this.pageDirFile.listFIles();
    if(pageFiles != null && pageFiles.length > 0) {
      for(File pageFile : pageFiles) {
        String fileName = pageFile.getName();
        if (fileName.endsWith(PAGE_FILE_SUFFIX)) {
          totalSize += pageFile.length();
        }
      }
    }
    return totalSize;
  }
}
```

```
```

```
```


