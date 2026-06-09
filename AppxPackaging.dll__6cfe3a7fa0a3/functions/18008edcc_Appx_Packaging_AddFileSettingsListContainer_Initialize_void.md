# Appx::Packaging::AddFileSettingsListContainer::Initialize(void)

- ea: `0x18008edcc`
- end: `0x18008fcf9`
- name: `?Initialize@AddFileSettingsListContainer@Packaging@Appx@@QEAAJXZ`
- size: `3885`
- prototype: `__int64 __fastcall(Appx::Packaging::AddFileSettingsListContainer *__hidden this)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007e738`
- `0x18008e6e0`

## callees

- `0x180006ef8`
- `0x1800133fc`
- `0x180071f50`
- `0x18008edcc`
- `0x18008fd00`
- `0x1800992c4`
- `0x1800992d0`

## import_xrefs

- `ntdll!RtlInitializeGenericTableAvl` at `0x18008eea6`
- `ntdll!RtlInitializeGenericTableAvl` at `0x18008eea6`

## string_xrefs

- `0x18008f00b`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x18008f05d`: `application/vnd.openxmlformats-officedocument.wordprocessingml.document`
- `0x18008f8bf`: `text/xml`
- `0x18008f8e8`: `text/xml`
- `0x18008f665`: `application/xslt+xml`
- `0x18008f68e`: `application/xslt+xml`
- `0x18008f3b1`: `application/x-rar-compressed`
- `0x18008ef67`: `application/vnd.ms-cab-compressed`
- `0x18008f101`: `application/x-gzip-compressed`
- `0x18008f388`: `application/vnd.openxmlformats-officedocument.presentationml.presentation`
- `0x18008eedf`: `application/atom+xml`
- `0x18008f1f7`: `application/vnd.ms-powerpoint.template.macroenabled.12`
- `0x18008f455`: `application/xaml+xml`
- `0x18008f29b`: `application/vnd.openxmlformats-officedocument.presentationml.slideshow`
- `0x18008f3da`: `application/rss+xml`
- `0x18008f0af`: `application/xml-dtd`
- `0x18008f4d0`: `application/xhtml+xml`
- `0x18008f403`: `application/soap+xml`
- `0x18008f6b7`: `application/x-zip-compressed`
- `0x18008f153`: `application/json`
- `0x18008f63c`: `application/vnd.openxmlformats-officedocument.spreadsheetml.template`
- `0x18008fb78`: `image/svg+xml`
- `0x18008f220`: `application/vnd.openxmlformats-officedocument.presentationml.template`
- `0x18008f613`: `application/vnd.ms-excel.template.macroEnabled.12`
- `0x18008f5ea`: `application/vnd.openxmlformats-officedocument.spreadsheetml.sheet`

## pseudocode

```c
__int64 __fastcall Appx::Packaging::AddFileSettingsListContainer::Initialize(
        Appx::Packaging::AddFileSettingsListContainer *this)
{
  int MappedItem; // edi
  _DWORD *v3; // rdi
  __int64 v4; // rdx
  struct _RTL_AVL_TABLE *v6; // rax
  struct _RTL_AVL_TABLE *v7; // rdi
  __int64 v8; // rdx
  int TableContext; // [rsp+20h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+28h]

  MappedItem = 0;
  if ( *((_DWORD *)this + 4) )
    return (unsigned int)MappedItem;
  v3 = operator new(0x10u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v3 )
  {
    v3[2] = 1;
    *(_QWORD *)v3 = L"application/octet-stream";
  }
  else
  {
    v3 = 0;
  }
  if ( *(_DWORD **)this == v3 )
  {
    v3 = *(_DWORD **)this;
  }
  else
  {
    operator delete(*(void **)this, 0x10u);
    *(_QWORD *)this = v3;
  }
  if ( !v3 )
  {
    v4 = 74;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\addfilesettings.cpp",
      (const char *)0x8007000ELL,
      TableContext);
    return 2147942414LL;
  }
  v6 = (struct _RTL_AVL_TABLE *)operator new(0x78u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v6[1].BalancedRoot.Parent = 0;
    v6[1].BalancedRoot.LeftChild = (struct _RTL_BALANCED_LINKS *)Common::DeallocateRaw<Appx::Packaging::AddFileSettings *>;
    RtlInitializeGenericTableAvl(
      v6,
      Common::GenericMapCaseInsensitiveCompare,
      Common::GenericMap<unsigned short *,void *>::GenericMapAllocate,
      Common::GenericMap<unsigned short const *,Appx::Packaging::Bitmap *>::GenericMapFree,
      0);
  }
  else
  {
    v7 = 0;
  }
  if ( *((struct _RTL_AVL_TABLE **)this + 1) == v7 )
  {
    v7 = (struct _RTL_AVL_TABLE *)*((_QWORD *)this + 1);
  }
  else
  {
    Common::AutoPtrDeallocate<Common::GenericMap<unsigned short const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>(*((struct _RTL_AVL_TABLE **)this + 1));
    *((_QWORD *)this + 1) = v7;
  }
  if ( !v7 )
  {
    v4 = 77;
    goto LABEL_10;
  }
  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                 this,
                 L"atom",
                 L"application/atom+xml",
                 APPX_COMPRESSION_OPTION_NORMAL);
  if ( MappedItem >= 0 )
  {
    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                   this,
                   L"appx",
                   L"application/vnd.ms-appx",
                   APPX_COMPRESSION_OPTION_NONE);
    if ( MappedItem >= 0 )
    {
      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                     this,
                     L"b64",
                     L"application/base64",
                     APPX_COMPRESSION_OPTION_NORMAL);
      if ( MappedItem >= 0 )
      {
        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                       this,
                       L"cab",
                       L"application/vnd.ms-cab-compressed",
                       APPX_COMPRESSION_OPTION_NONE);
        if ( MappedItem >= 0 )
        {
          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                         this,
                         L"doc",
                         L"application/msword",
                         APPX_COMPRESSION_OPTION_NORMAL);
          if ( MappedItem >= 0 )
          {
            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                           this,
                           L"dot",
                           L"application/msword",
                           APPX_COMPRESSION_OPTION_NORMAL);
            if ( MappedItem >= 0 )
            {
              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                             this,
                             L"docm",
                             L"application/vnd.ms-word.document.macroenabled.12",
                             APPX_COMPRESSION_OPTION_NONE);
              if ( MappedItem >= 0 )
              {
                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                               this,
                               L"docx",
                               L"application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                               APPX_COMPRESSION_OPTION_NONE);
                if ( MappedItem >= 0 )
                {
                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                 this,
                                 L"dotm",
                                 L"application/vnd.ms-word.document.macroenabled.12",
                                 APPX_COMPRESSION_OPTION_NONE);
                  if ( MappedItem >= 0 )
                  {
                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                   this,
                                   L"dotx",
                                   L"application/vnd.openxmlformats-officedocument.wordprocessingml.document",
                                   APPX_COMPRESSION_OPTION_NONE);
                    if ( MappedItem >= 0 )
                    {
                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                     this,
                                     L"dll",
                                     L"application/x-msdownload",
                                     APPX_COMPRESSION_OPTION_NORMAL);
                      if ( MappedItem >= 0 )
                      {
                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                       this,
                                       L"dtd",
                                       L"application/xml-dtd",
                                       APPX_COMPRESSION_OPTION_NORMAL);
                        if ( MappedItem >= 0 )
                        {
                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                         this,
                                         L"exe",
                                         L"application/x-msdownload",
                                         APPX_COMPRESSION_OPTION_NORMAL);
                          if ( MappedItem >= 0 )
                          {
                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                           this,
                                           L"gz",
                                           L"application/x-gzip-compressed",
                                           APPX_COMPRESSION_OPTION_NONE);
                            if ( MappedItem >= 0 )
                            {
                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                             this,
                                             L"java",
                                             L"application/java",
                                             APPX_COMPRESSION_OPTION_NORMAL);
                              if ( MappedItem >= 0 )
                              {
                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                               this,
                                               L"json",
                                               L"application/json",
                                               APPX_COMPRESSION_OPTION_NORMAL);
                                if ( MappedItem >= 0 )
                                {
                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                 this,
                                                 L"p7s",
                                                 L"application/x-pkcs7-signature",
                                                 APPX_COMPRESSION_OPTION_NORMAL);
                                  if ( MappedItem >= 0 )
                                  {
                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                   this,
                                                   L"pdf",
                                                   L"application/pdf",
                                                   APPX_COMPRESSION_OPTION_NORMAL);
                                    if ( MappedItem >= 0 )
                                    {
                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                     this,
                                                     L"ps",
                                                     L"application/postscript",
                                                     APPX_COMPRESSION_OPTION_NORMAL);
                                      if ( MappedItem >= 0 )
                                      {
                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                       this,
                                                       L"potm",
                                                       L"application/vnd.ms-powerpoint.template.macroenabled.12",
                                                       APPX_COMPRESSION_OPTION_NONE);
                                        if ( MappedItem >= 0 )
                                        {
                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                         this,
                                                         L"potx",
                                                         L"application/vnd.openxmlformats-officedocument.presentationml.template",
                                                         APPX_COMPRESSION_OPTION_NONE);
                                          if ( MappedItem >= 0 )
                                          {
                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                           this,
                                                           L"ppam",
                                                           L"application/vnd.ms-powerpoint.addin.macroenabled.12",
                                                           APPX_COMPRESSION_OPTION_NONE);
                                            if ( MappedItem >= 0 )
                                            {
                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                             this,
                                                             L"ppsm",
                                                             L"application/vnd.ms-powerpoint.slideshow.macroenabled.12",
                                                             APPX_COMPRESSION_OPTION_NONE);
                                              if ( MappedItem >= 0 )
                                              {
                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                               this,
                                                               L"ppsx",
                                                               L"application/vnd.openxmlformats-officedocument.presentationml.slideshow",
                                                               APPX_COMPRESSION_OPTION_NONE);
                                                if ( MappedItem >= 0 )
                                                {
                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                 this,
                                                                 L"ppt",
                                                                 L"application/vnd.ms-powerpoint",
                                                                 APPX_COMPRESSION_OPTION_NORMAL);
                                                  if ( MappedItem >= 0 )
                                                  {
                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                   this,
                                                                   L"pot",
                                                                   L"application/vnd.ms-powerpoint",
                                                                   APPX_COMPRESSION_OPTION_NORMAL);
                                                    if ( MappedItem >= 0 )
                                                    {
                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                     this,
                                                                     L"pps",
                                                                     L"application/vnd.ms-powerpoint",
                                                                     APPX_COMPRESSION_OPTION_NORMAL);
                                                      if ( MappedItem >= 0 )
                                                      {
                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                       this,
                                                                       L"ppa",
                                                                       L"application/vnd.ms-powerpoint",
                                                                       APPX_COMPRESSION_OPTION_NORMAL);
                                                        if ( MappedItem >= 0 )
                                                        {
                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                         this,
                                                                         L"pptm",
                                                                         L"application/vnd.ms-powerpoint.presentation.macroenabled.12",
                                                                         APPX_COMPRESSION_OPTION_NONE);
                                                          if ( MappedItem >= 0 )
                                                          {
                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                           this,
                                                                           L"pptx",
                                                                           L"application/vnd.openxmlformats-officedocument"
                                                                            ".presentationml.presentation",
                                                                           APPX_COMPRESSION_OPTION_NONE);
                                                            if ( MappedItem >= 0 )
                                                            {
                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                             this,
                                                                             L"rar",
                                                                             L"application/x-rar-compressed",
                                                                             APPX_COMPRESSION_OPTION_NONE);
                                                              if ( MappedItem >= 0 )
                                                              {
                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                               this,
                                                                               L"rss",
                                                                               L"application/rss+xml",
                                                                               APPX_COMPRESSION_OPTION_NORMAL);
                                                                if ( MappedItem >= 0 )
                                                                {
                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                 this,
                                                                                 L"soap",
                                                                                 L"application/soap+xml",
                                                                                 APPX_COMPRESSION_OPTION_NORMAL);
                                                                  if ( MappedItem >= 0 )
                                                                  {
                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                   this,
                                                                                   L"tar",
                                                                                   L"application/x-tar",
                                                                                   APPX_COMPRESSION_OPTION_NONE);
                                                                    if ( MappedItem >= 0 )
                                                                    {
                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                     this,
                                                                                     L"xaml",
                                                                                     L"application/xaml+xml",
                                                                                     APPX_COMPRESSION_OPTION_NORMAL);
                                                                      if ( MappedItem >= 0 )
                                                                      {
                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                       this,
                                                                                       L"xap",
                                                                                       L"application/x-silverlight-app",
                                                                                       APPX_COMPRESSION_OPTION_NONE);
                                                                        if ( MappedItem >= 0 )
                                                                        {
                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                         this,
                                                                                         L"xbap",
                                                                                         L"application/x-ms-xbap",
                                                                                         APPX_COMPRESSION_OPTION_NORMAL);
                                                                          if ( MappedItem >= 0 )
                                                                          {
                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                           this,
                                                                                           L"xhtml",
                                                                                           L"application/xhtml+xml",
                                                                                           APPX_COMPRESSION_OPTION_NORMAL);
                                                                            if ( MappedItem >= 0 )
                                                                            {
                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                             this,
                                                                                             L"xlam",
                                                                                             L"application/vnd.ms-excel.ad"
                                                                                              "din.macroenabled.12",
                                                                                             APPX_COMPRESSION_OPTION_NONE);
                                                                              if ( MappedItem >= 0 )
                                                                              {
                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                               this,
                                                                                               L"xls",
                                                                                               L"application/vnd.ms-excel",
                                                                                               APPX_COMPRESSION_OPTION_NORMAL);
                                                                                if ( MappedItem >= 0 )
                                                                                {
                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                                 this,
                                                                                                 L"xlt",
                                                                                                 L"application/vnd.ms-excel",
                                                                                                 APPX_COMPRESSION_OPTION_NORMAL);
                                                                                  if ( MappedItem >= 0 )
                                                                                  {
                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                                   this,
                                                                                                   L"xla",
                                                                                                   L"application/vnd.ms-excel",
                                                                                                   APPX_COMPRESSION_OPTION_NORMAL);
                                                                                    if ( MappedItem >= 0 )
                                                                                    {
                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(
                                                                                                     this,
                                                                                                     L"xlsb",
                                                                                                     L"application/vnd.ms-excel.sheet.binary.macroEnabled.12",
                                                                                                     APPX_COMPRESSION_OPTION_NONE);
                                                                                      if ( MappedItem >= 0 )
                                                                                      {
                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xlsm", L"application/vnd.ms-excel.sheet.macroEnabled.12", APPX_COMPRESSION_OPTION_NONE);
                                                                                        if ( MappedItem >= 0 )
                                                                                        {
                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xlsx", L"application/vnd.openxmlformats-officedocument.spreadsheetml.sheet", APPX_COMPRESSION_OPTION_NONE);
                                                                                          if ( MappedItem >= 0 )
                                                                                          {
                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xltm", L"application/vnd.ms-excel.template.macroEnabled.12", APPX_COMPRESSION_OPTION_NONE);
                                                                                            if ( MappedItem >= 0 )
                                                                                            {
                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xltx", L"application/vnd.openxmlformats-officedocument.spreadsheetml.template", APPX_COMPRESSION_OPTION_NONE);
                                                                                              if ( MappedItem >= 0 )
                                                                                              {
                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xsl", L"application/xslt+xml", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                if ( MappedItem >= 0 )
                                                                                                {
                                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xslt", L"application/xslt+xml", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                  if ( MappedItem >= 0 )
                                                                                                  {
                                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"zip", L"application/x-zip-compressed", APPX_COMPRESSION_OPTION_NONE);
                                                                                                    if ( MappedItem >= 0 )
                                                                                                    {
                                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"c", L"text/plain", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                      if ( MappedItem >= 0 )
                                                                                                      {
                                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"cpp", L"text/plain", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                        if ( MappedItem >= 0 )
                                                                                                        {
                                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"cs", L"text/plain", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                          if ( MappedItem >= 0 )
                                                                                                          {
                                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"css", L"text/css", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                            if ( MappedItem >= 0 )
                                                                                                            {
                                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"csv", L"text/csv", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                              if ( MappedItem >= 0 )
                                                                                                              {
                                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"h", L"text/plain", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                if ( MappedItem >= 0 )
                                                                                                                {
                                                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"htm", L"text/html", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                  if ( MappedItem >= 0 )
                                                                                                                  {
                                                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"html", L"text/html", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                    if ( MappedItem >= 0 )
                                                                                                                    {
                                                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"js", L"application/x-javascript", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                      if ( MappedItem >= 0 )
                                                                                                                      {
                                                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"rtf", L"text/richtext", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                        if ( MappedItem >= 0 )
                                                                                                                        {
                                                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"sct", L"text/scriptlet", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                          if ( MappedItem >= 0 )
                                                                                                                          {
                                                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"txt", L"text/plain", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                            if ( MappedItem >= 0 )
                                                                                                                            {
                                                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xml", L"text/xml", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                              if ( MappedItem >= 0 )
                                                                                                                              {
                                                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"xsd", L"text/xml", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                if ( MappedItem >= 0 )
                                                                                                                                {
                                                                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"aiff", L"audio/x-aiff", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                  if ( MappedItem >= 0 )
                                                                                                                                  {
                                                                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"au", L"audio/basic", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                    if ( MappedItem >= 0 )
                                                                                                                                    {
                                                                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"m4a", L"audio/mp4", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                      if ( MappedItem >= 0 )
                                                                                                                                      {
                                                                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"mid", L"audio/mid", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                        if ( MappedItem >= 0 )
                                                                                                                                        {
                                                                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"mp3", L"audio/mpeg", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                          if ( MappedItem >= 0 )
                                                                                                                                          {
                                                                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"smf", L"audio/mid", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                            if ( MappedItem >= 0 )
                                                                                                                                            {
                                                                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"wav", L"audio/wav", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                              if ( MappedItem >= 0 )
                                                                                                                                              {
                                                                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"wma", L"audio/x-ms-wma", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                if ( MappedItem >= 0 )
                                                                                                                                                {
                                                                                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"bmp", L"image/bmp", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                  if ( MappedItem >= 0 )
                                                                                                                                                  {
                                                                                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"emf", L"image/x-emf", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                    if ( MappedItem >= 0 )
                                                                                                                                                    {
                                                                                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"gif", L"image/gif", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                      if ( MappedItem >= 0 )
                                                                                                                                                      {
                                                                                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"ico", L"image/vnd.microsoft.icon", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                        if ( MappedItem >= 0 )
                                                                                                                                                        {
                                                                                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"jpg", L"image/jpeg", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                          if ( MappedItem >= 0 )
                                                                                                                                                          {
                                                                                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"jpeg", L"image/jpeg", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                            if ( MappedItem >= 0 )
                                                                                                                                                            {
                                                                                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"png", L"image/png", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                              if ( MappedItem >= 0 )
                                                                                                                                                              {
                                                                                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"svg", L"image/svg+xml", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                                if ( MappedItem >= 0 )
                                                                                                                                                                {
                                                                                                                                                                  MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"tif", L"image/tiff", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                                  if ( MappedItem >= 0 )
                                                                                                                                                                  {
                                                                                                                                                                    MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"tiff", L"image/tiff", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                                    if ( MappedItem >= 0 )
                                                                                                                                                                    {
                                                                                                                                                                      MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"wmf", L"image/x-wmf", APPX_COMPRESSION_OPTION_NORMAL);
                                                                                                                                                                      if ( MappedItem >= 0 )
                                                                                                                                                                      {
                                                                                                                                                                        MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"avi", L"video/avi", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                                        if ( MappedItem >= 0 )
                                                                                                                                                                        {
                                                                                                                                                                          MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"mpeg", L"video/mpeg", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                                          if ( MappedItem >= 0 )
                                                                                                                                                                          {
                                                                                                                                                                            MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"mpg", L"video/mpeg", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                                            if ( MappedItem >= 0 )
                                                                                                                                                                            {
                                                                                                                                                                              MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"mov", L"video/quicktime", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                                              if ( MappedItem >= 0 )
                                                                                                                                                                              {
                                                                                                                                                                                MappedItem = Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(this, L"wmv", L"video/x-ms-wmv", APPX_COMPRESSION_OPTION_NONE);
                                                                                                                                                                                if ( MappedItem >= 0 )
                                                                                                                                                                                {
                                                                                                                                                                                  *((_DWORD *)this + 4) = 1;
                                                                                                                                                                                  return (unsigned int)MappedItem;
                                                                                                                                                                                }
                                                                                                                                                                                v8 = 171;
                                                                                                                                                                              }
                                                                                                                                                                              else
                                                                                                                                                                              {
                                                                                                                                                                                v8 = 170;
                                                                                                                                                                              }
                                                                                                                                                                            }
                                                                                                                                                                            else
                                                                                                                                                                            {
                                                                                                                                                                              v8 = 169;
                                                                                                                                                                            }
                                                                                                                                                                          }
                                                                                                                                                                          else
                                                                                                                                                                          {
                                                                                                                                                                            v8 = 168;
                                                                                                                                                                          }
                                                                                                                                                                        }
                                                                                                                                                                        else
                                                                                                                                                                        {
                                                                                                                                                                          v8 = 167;
                                                                                                                                                                        }
                                                                                                                                                                      }
                                                                                                                                                                      else
                                                                                                                                                                      {
                                                                                                                                                                        v8 = 165;
                                                                                                                                                                      }
                                                                                                                                                                    }
                                                                                                                                                                    else
                                                                                                                                                                    {
                                                                                                                                                                      v8 = 164;
                                                                                                                                                                    }
                                                                                                                                                                  }
                                                                                                                                                                  else
                                                                                                                                                                  {
                                                                                                                                                                    v8 = 163;
                                                                                                                                                                  }
                                                                                                                                                                }
                                                                                                                                                                else
                                                                                                                                                                {
                                                                                                                                                                  v8 = 162;
                                                                                                                                                                }
                                                                                                                                                              }
                                                                                                                                                              else
                                                                                                                                                              {
                                                                                                                                                                v8 = 161;
                                                                                                                                                              }
                                                                                                                                                            }
                                                                                                                                                            else
                                                                                                                                                            {
                                                                                                                                                              v8 = 160;
                                                                                                                                                            }
                                                                                                                                                          }
                                                                                                                                                          else
                                                                                                                                                          {
                                                                                                                                                            v8 = 159;
                                                                                                                                                          }
                                                                                                                                                        }
                                                                                                                                                        else
                                                                                                                                                        {
                                                                                                                                                          v8 = 158;
                                                                                                                                                        }
                                                                                                                                                      }
                                                                                                                                                      else
                                                                                                                                                      {
                                                                                                                                                        v8 = 157;
                                                                                                                                                      }
                                                                                                                                                    }
                                                                                                                                                    else
                                                                                                                                                    {
                                                                                                                                                      v8 = 156;
                                                                                                                                                    }
                                                                                                                                                  }
                                                                                                                                                  else
                                                                                                                                                  {
                                                                                                                                                    v8 = 155;
                                                                                                                                                  }
                                                                                                                                                }
                                                                                                                                                else
                                                                                                                                                {
                                                                                                                                                  v8 = 153;
                                                                                                                                                }
                                                                                                                                              }
                                                                                                                                              else
                                                                                                                                              {
                                                                                                                                                v8 = 152;
                                                                                                                                              }
                                                                                                                                            }
                                                                                                                                            else
                                                                                                                                            {
                                                                                                                                              v8 = 151;
                                                                                                                                            }
                                                                                                                                          }
                                                                                                                                          else
                                                                                                                                          {
                                                                                                                                            v8 = 150;
                                                                                                                                          }
                                                                                                                                        }
                                                                                                                                        else
                                                                                                                                        {
                                                                                                                                          v8 = 149;
                                                                                                                                        }
                                                                                                                                      }
                                                                                                                                      else
                                                                                                                                      {
                                                                                                                                        v8 = 148;
                                                                                                                                      }
                                                                                                                                    }
                                                                                                                                    else
                                                                                                                                    {
                                                                                                                                      v8 = 147;
                                                                                                                                    }
                                                                                                                                  }
                                                                                                                                  else
                                                                                                                                  {
                                                                                                                                    v8 = 146;
                                                                                                                                  }
                                                                                                                                }
                                                                                                                                else
                                                                                                                                {
                                                                                                                                  v8 = 144;
                                                                                                                                }
                                                                                                                              }
                                                                                                                              else
                                                                                                                              {
                                                                                                                                v8 = 143;
                                                                                                                              }
                                                                                                                            }
                                                                                                                            else
                                                                                                                            {
                                                                                                                              v8 = 142;
                                                                                                                            }
                                                                                                                          }
                                                                                                                          else
                                                                                                                          {
                                                                                                                            v8 = 141;
                                                                                                                          }
                                                                                                                        }
                                                                                                                        else
                                                                                                                        {
                                                                                                                          v8 = 140;
                                                                                                                        }
                                                                                                                      }
                                                                                                                      else
                                                                                                                      {
                                                                                                                        v8 = 139;
                                                                                                                      }
                                                                                                                    }
                                                                                                                    else
                                                                                                                    {
                                                                                                                      v8 = 138;
                                                                                                                    }
                                                                                                                  }
                                                                                                                  else
                                                                                                                  {
                                                                                                                    v8 = 137;
                                                                                                                  }
                                                                                                                }
                                                                                                                else
                                                                                                                {
                                                                                                                  v8 = 136;
                                                                                                                }
                                                                                                              }
                                                                                                              else
                                                                                                              {
                                                                                                                v8 = 135;
                                                                                                              }
                                                                                                            }
                                                                                                            else
                                                                                                            {
                                                                                                              v8 = 134;
                                                                                                            }
                                                                                                          }
                                                                                                          else
                                                                                                          {
                                                                                                            v8 = 133;
                                                                                                          }
                                                                                                        }
                                                                                                        else
                                                                                                        {
                                                                                                          v8 = 132;
                                                                                                        }
                                                                                                      }
                                                                                                      else
                                                                                                      {
                                                                                                        v8 = 131;
                                                                                                      }
                                                                                                    }
                                                                                                    else
                                                                                                    {
                                                                                                      v8 = 129;
                                                                                                    }
                                                                                                  }
                                                                                                  else
                                                                                                  {
                                                                                                    v8 = 128;
                                                                                                  }
                                                                                                }
                                                                                                else
                                                                                                {
                                                                                                  v8 = 127;
                                                                                                }
                                                                                              }
                                                                                              else
                                                                                              {
                                                                                                v8 = 126;
                                                                                              }
                                                                                            }
                                                                                            else
                                                                                            {
                                                                                              v8 = 125;
                                                                                            }
                                                                                          }
                                                                                          else
                                                                                          {
                                                                                            v8 = 124;
                                                                                          }
                                                                                        }
                                                                                        else
                                                                                        {
                                                                                          v8 = 123;
                                                                                        }
                                                                                      }
                                                                                      else
                                                                                      {
                                                                                        v8 = 122;
                                                                                      }
                                                                                    }
                                                                                    else
                                                                                    {
                                                                                      v8 = 121;
                                                                                    }
                                                                                  }
                                                                                  else
                                                                                  {
                                                                                    v8 = 120;
                                                                                  }
                                                                                }
                                                                                else
                                                                                {
                                                                                  v8 = 119;
                                                                                }
                                                                              }
                                                                              else
                                                                              {
                                                                                v8 = 118;
                                                                              }
                                                                            }
                                                                            else
                                                                            {
                                                                              v8 = 117;
                                                                            }
                                                                          }
                                                                          else
                                                                          {
                                                                            v8 = 116;
                                                                          }
                                                                        }
                                                                        else
                                                                        {
                                                                          v8 = 115;
                                                                        }
                                                                      }
                                                                      else
                                                                      {
                                                                        v8 = 114;
                                                                      }
                                                                    }
                                                                    else
                                                                    {
                                                                      v8 = 113;
                                                                    }
                                                                  }
                                                                  else
                                                                  {
                                                                    v8 = 112;
                                                                  }
                                                                }
                                                                else
                                                                {
                                                                  v8 = 111;
                                                                }
                                                              }
                                                              else
                                                              {
                                                                v8 = 110;
                                                              }
                                                            }
                                                            else
                                                            {
                                                              v8 = 109;
                                                            }
                                                          }
                                                          else
                                                          {
                                                            v8 = 108;
                                                          }
                                                        }
                                                        else
                                                        {
                                                          v8 = 107;
                                                        }
                                                      }
                                                      else
                                                      {
                                                        v8 = 106;
                                                      }
                                                    }
                                                    else
                                                    {
                                                      v8 = 105;
                                                    }
                                                  }
                                                  else
                                                  {
                                                    v8 = 104;
                                                  }
                                                }
                                                else
                                                {
                                                  v8 = 103;
                                                }
                                              }
                                              else
                                              {
                                                v8 = 102;
                                              }
                                            }
                                            else
                                            {
                                              v8 = 101;
                                            }
                                          }
                                          else
                                          {
                                            v8 = 100;
                                          }
                                        }
                                        else
                                        {
                                          v8 = 99;
                                        }
                                      }
                                      else
                                      {
                                        v8 = 98;
                                      }
                                    }
                                    else
                                    {
                                      v8 = 97;
                                    }
                                  }
                                  else
                                  {
                                    v8 = 96;
                                  }
                                }
                                else
                                {
                                  v8 = 95;
                                }
                              }
                              else
                              {
                                v8 = 94;
                              }
                            }
                            else
                            {
                              v8 = 93;
                            }
                          }
                          else
                          {
                            v8 = 92;
                          }
                        }
                        else
                        {
                          v8 = 91;
                        }
                      }
                      else
                      {
                        v8 = 90;
                      }
                    }
                    else
                    {
                      v8 = 89;
                    }
                  }
                  else
                  {
                    v8 = 88;
                  }
                }
                else
                {
                  v8 = 87;
                }
              }
              else
              {
                v8 = 86;
              }
            }
            else
            {
              v8 = 85;
            }
          }
          else
          {
            v8 = 84;
          }
        }
        else
        {
          v8 = 83;
        }
      }
      else
      {
        v8 = 82;
      }
    }
    else
    {
      v8 = 81;
    }
  }
  else
  {
    v8 = 80;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecore\\printscan\\appxpackaging\\lib\\core\\src\\addfilesettings.cpp",
    (const char *)(unsigned int)MappedItem,
    TableContext);
  return (unsigned int)MappedItem;
}

```

## disassembly

```asm
0x18008edcc  push    rbp
0x18008edce  push    rbx
0x18008edcf  push    rdi
0x18008edd0  push    r14
0x18008edd2  push    r15
0x18008edd4  mov     rbp, rsp
0x18008edd7  sub     rsp, 30h
0x18008eddb  xor     edi, edi
0x18008eddd  mov     rbx, rcx
0x18008ede0  cmp     [rcx+10h], edi
0x18008ede3  jnz     loc_18008FCEA
0x18008ede9  lea     r15d, [rdi+10h]
0x18008eded  mov     ecx, r15d; unsigned __int64
0x18008edf0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008edf7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008edfc  lea     r14d, [r15-0Fh]
0x18008ee00  mov     rdi, rax
0x18008ee03  test    rax, rax
0x18008ee06  jz      short loc_18008EE18
0x18008ee08  lea     rax, aApplicationOct; "application/octet-stream"
0x18008ee0f  mov     [rdi+8], r14d
0x18008ee13  mov     [rdi], rax
0x18008ee16  jmp     short loc_18008EE1A
0x18008ee18  xor     edi, edi
0x18008ee1a  cmp     [rbx], rdi
0x18008ee1d  jz      short loc_18008EE2F
0x18008ee1f  mov     rcx, [rbx]; void *
0x18008ee22  mov     rdx, r15; unsigned __int64
0x18008ee25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18008ee2a  mov     [rbx], rdi
0x18008ee2d  jmp     short loc_18008EE32
0x18008ee2f  mov     rdi, [rbx]
0x18008ee32  test    rdi, rdi
0x18008ee35  jnz     short loc_18008EE59
0x18008ee37  lea     edx, [rdi+4Ah]; void *
0x18008ee3a  mov     rcx, [rbp+28h]; this
0x18008ee3e  lea     r8, aOnecorePrintsc_190; "onecore\\printscan\\appxpackaging\\lib"...
0x18008ee45  mov     ebx, 8007000Eh
0x18008ee4a  mov     r9d, ebx; char *
0x18008ee4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18008ee52  mov     eax, ebx
0x18008ee54  jmp     loc_18008FCEC
0x18008ee59  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008ee60  mov     ecx, 78h ; 'x'; unsigned __int64
0x18008ee65  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18008ee6a  mov     rdi, rax
0x18008ee6d  test    rax, rax
0x18008ee70  jz      short loc_18008EEB4
0x18008ee72  mov     qword ptr [rax+68h], 0
0x18008ee7a  lea     r9, ?GenericMapFree@?$GenericMap@PEBGPEAVBitmap@Packaging@Appx@@@Common@@CAXPEAU_RTL_AVL_TABLE@@PEAX@Z; FreeRoutine
0x18008ee81  lea     rax, ??$DeallocateRaw@PEAVAddFileSettings@Packaging@Appx@@@Common@@YAXPEAVAddFileSettings@Packaging@Appx@@@Z; Common::DeallocateRaw<Appx::Packaging::AddFileSettings *>(Appx::Packaging::AddFileSettings *)
0x18008ee88  mov     qword ptr [rsp+30h+TableContext], 0; TableContext
0x18008ee91  lea     r8, ?GenericMapAllocate@?$GenericMap@PEAGPEAX@Common@@CAPEAXPEAU_RTL_AVL_TABLE@@K@Z; AllocateRoutine
0x18008ee98  mov     [rdi+70h], rax
0x18008ee9c  lea     rdx, ?GenericMapCaseInsensitiveCompare@Common@@YA?AW4_RTL_GENERIC_COMPARE_RESULTS@@PEAU_RTL_AVL_TABLE@@PEAX1@Z; CompareRoutine
0x18008eea3  mov     rcx, rdi; Table
0x18008eea6  call    cs:__imp_RtlInitializeGenericTableAvl
0x18008eead  nop     dword ptr [rax+rax+00h]
0x18008eeb2  jmp     short loc_18008EEB6
0x18008eeb4  xor     edi, edi
0x18008eeb6  cmp     [rbx+8], rdi
0x18008eeba  jz      short loc_18008EECB
0x18008eebc  mov     rcx, [rbx+8]; void *
0x18008eec0  call    ??$AutoPtrDeallocate@V?$GenericMap@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@Common@@@Common@@YAXPEAV?$GenericMap@PEBGPEAVAppxBlockMapFile@BlockMap@Packaging@Appx@@@0@@Z; Common::AutoPtrDeallocate<Common::GenericMap<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *>>(Common::GenericMap<ushort const *,Appx::Packaging::BlockMap::AppxBlockMapFile *> *)
0x18008eec5  mov     [rbx+8], rdi
0x18008eec9  jmp     short loc_18008EECF
0x18008eecb  mov     rdi, [rbx+8]
0x18008eecf  test    rdi, rdi
0x18008eed2  jnz     short loc_18008EEDC
0x18008eed4  lea     edx, [rdi+4Dh]
0x18008eed7  jmp     loc_18008EE3A
0x18008eedc  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008eedf  lea     r8, aApplicationAto; "application/atom+xml"
0x18008eee6  lea     rdx, aAtom; "atom"
0x18008eeed  mov     rcx, rbx; this
0x18008eef0  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008eef5  mov     edi, eax
0x18008eef7  test    eax, eax
0x18008eef9  jns     short loc_18008EF18
0x18008eefb  mov     edx, 50h ; 'P'; void *
0x18008ef00  mov     rcx, [rbp+28h]; this
0x18008ef04  lea     r8, aOnecorePrintsc_190; "onecore\\printscan\\appxpackaging\\lib"...
0x18008ef0b  mov     r9d, edi; char *
0x18008ef0e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18008ef13  jmp     loc_18008FCEA
0x18008ef18  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008ef1b  lea     r8, aApplicationVnd_5; "application/vnd.ms-appx"
0x18008ef22  lea     rdx, aAppx; "appx"
0x18008ef29  mov     rcx, rbx; this
0x18008ef2c  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008ef31  mov     edi, eax
0x18008ef33  test    eax, eax
0x18008ef35  jns     short loc_18008EF3E
0x18008ef37  mov     edx, 51h ; 'Q'
0x18008ef3c  jmp     short loc_18008EF00
0x18008ef3e  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008ef41  lea     r8, aApplicationBas; "application/base64"
0x18008ef48  lea     rdx, aB64; "b64"
0x18008ef4f  mov     rcx, rbx; this
0x18008ef52  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008ef57  mov     edi, eax
0x18008ef59  test    eax, eax
0x18008ef5b  jns     short loc_18008EF64
0x18008ef5d  mov     edx, 52h ; 'R'
0x18008ef62  jmp     short loc_18008EF00
0x18008ef64  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008ef67  lea     r8, aApplicationVnd_8; "application/vnd.ms-cab-compressed"
0x18008ef6e  lea     rdx, aCab; "cab"
0x18008ef75  mov     rcx, rbx; this
0x18008ef78  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008ef7d  mov     edi, eax
0x18008ef7f  test    eax, eax
0x18008ef81  jns     short loc_18008EF8D
0x18008ef83  mov     edx, 53h ; 'S'
0x18008ef88  jmp     loc_18008EF00
0x18008ef8d  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008ef90  lea     r8, aApplicationMsw; "application/msword"
0x18008ef97  lea     rdx, aDoc; "doc"
0x18008ef9e  mov     rcx, rbx; this
0x18008efa1  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008efa6  mov     edi, eax
0x18008efa8  test    eax, eax
0x18008efaa  jns     short loc_18008EFB6
0x18008efac  mov     edx, 54h ; 'T'
0x18008efb1  jmp     loc_18008EF00
0x18008efb6  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008efb9  lea     r8, aApplicationMsw; "application/msword"
0x18008efc0  lea     rdx, aDot; "dot"
0x18008efc7  mov     rcx, rbx; this
0x18008efca  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008efcf  mov     edi, eax
0x18008efd1  test    eax, eax
0x18008efd3  jns     short loc_18008EFDF
0x18008efd5  mov     edx, 55h ; 'U'
0x18008efda  jmp     loc_18008EF00
0x18008efdf  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008efe2  lea     r8, aApplicationVnd_11; "application/vnd.ms-word.document.macroe"...
0x18008efe9  lea     rdx, aDocm; "docm"
0x18008eff0  mov     rcx, rbx; this
0x18008eff3  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008eff8  mov     edi, eax
0x18008effa  test    eax, eax
0x18008effc  jns     short loc_18008F008
0x18008effe  mov     edx, 56h ; 'V'
0x18008f003  jmp     loc_18008EF00
0x18008f008  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f00b  lea     r8, aApplicationVnd_6; "application/vnd.openxmlformats-officedo"...
0x18008f012  lea     rdx, aDocx; "docx"
0x18008f019  mov     rcx, rbx; this
0x18008f01c  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f021  mov     edi, eax
0x18008f023  test    eax, eax
0x18008f025  jns     short loc_18008F031
0x18008f027  mov     edx, 57h ; 'W'
0x18008f02c  jmp     loc_18008EF00
0x18008f031  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f034  lea     r8, aApplicationVnd_11; "application/vnd.ms-word.document.macroe"...
0x18008f03b  lea     rdx, aDotm; "dotm"
0x18008f042  mov     rcx, rbx; this
0x18008f045  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f04a  mov     edi, eax
0x18008f04c  test    eax, eax
0x18008f04e  jns     short loc_18008F05A
0x18008f050  mov     edx, 58h ; 'X'
0x18008f055  jmp     loc_18008EF00
0x18008f05a  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f05d  lea     r8, aApplicationVnd_6; "application/vnd.openxmlformats-officedo"...
0x18008f064  lea     rdx, aDotx; "dotx"
0x18008f06b  mov     rcx, rbx; this
0x18008f06e  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f073  mov     edi, eax
0x18008f075  test    eax, eax
0x18008f077  jns     short loc_18008F083
0x18008f079  mov     edx, 59h ; 'Y'
0x18008f07e  jmp     loc_18008EF00
0x18008f083  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f086  lea     r8, aApplicationXMs_0; "application/x-msdownload"
0x18008f08d  lea     rdx, aDll; "dll"
0x18008f094  mov     rcx, rbx; this
0x18008f097  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f09c  mov     edi, eax
0x18008f09e  test    eax, eax
0x18008f0a0  jns     short loc_18008F0AC
0x18008f0a2  mov     edx, 5Ah ; 'Z'
0x18008f0a7  jmp     loc_18008EF00
0x18008f0ac  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f0af  lea     r8, aApplicationXml; "application/xml-dtd"
0x18008f0b6  lea     rdx, aDtd; "dtd"
0x18008f0bd  mov     rcx, rbx; this
0x18008f0c0  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f0c5  mov     edi, eax
0x18008f0c7  test    eax, eax
0x18008f0c9  jns     short loc_18008F0D5
0x18008f0cb  mov     edx, 5Bh ; '['
0x18008f0d0  jmp     loc_18008EF00
0x18008f0d5  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f0d8  lea     r8, aApplicationXMs_0; "application/x-msdownload"
0x18008f0df  lea     rdx, aExe_0; "exe"
0x18008f0e6  mov     rcx, rbx; this
0x18008f0e9  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f0ee  mov     edi, eax
0x18008f0f0  test    eax, eax
0x18008f0f2  jns     short loc_18008F0FE
0x18008f0f4  mov     edx, 5Ch ; '\'
0x18008f0f9  jmp     loc_18008EF00
0x18008f0fe  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f101  lea     r8, aApplicationXGz; "application/x-gzip-compressed"
0x18008f108  lea     rdx, aGz; "gz"
0x18008f10f  mov     rcx, rbx; this
0x18008f112  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f117  mov     edi, eax
0x18008f119  test    eax, eax
0x18008f11b  jns     short loc_18008F127
0x18008f11d  mov     edx, 5Dh ; ']'
0x18008f122  jmp     loc_18008EF00
0x18008f127  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f12a  lea     r8, aApplicationJav; "application/java"
0x18008f131  lea     rdx, aJava; "java"
0x18008f138  mov     rcx, rbx; this
0x18008f13b  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f140  mov     edi, eax
0x18008f142  test    eax, eax
0x18008f144  jns     short loc_18008F150
0x18008f146  mov     edx, 5Eh ; '^'
0x18008f14b  jmp     loc_18008EF00
0x18008f150  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f153  lea     r8, aApplicationJso; "application/json"
0x18008f15a  lea     rdx, aJson; "json"
0x18008f161  mov     rcx, rbx; this
0x18008f164  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f169  mov     edi, eax
0x18008f16b  test    eax, eax
0x18008f16d  jns     short loc_18008F179
0x18008f16f  mov     edx, 5Fh ; '_'
0x18008f174  jmp     loc_18008EF00
0x18008f179  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f17c  lea     r8, aApplicationXPk; "application/x-pkcs7-signature"
0x18008f183  lea     rdx, aP7s; "p7s"
0x18008f18a  mov     rcx, rbx; this
0x18008f18d  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f192  mov     edi, eax
0x18008f194  test    eax, eax
0x18008f196  jns     short loc_18008F1A2
0x18008f198  mov     edx, 60h ; '`'
0x18008f19d  jmp     loc_18008EF00
0x18008f1a2  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f1a5  lea     r8, aApplicationPdf; "application/pdf"
0x18008f1ac  lea     rdx, aPdf; "pdf"
0x18008f1b3  mov     rcx, rbx; this
0x18008f1b6  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f1bb  mov     edi, eax
0x18008f1bd  test    eax, eax
0x18008f1bf  jns     short loc_18008F1CB
0x18008f1c1  mov     edx, 61h ; 'a'
0x18008f1c6  jmp     loc_18008EF00
0x18008f1cb  mov     r9d, r14d; enum APPX_COMPRESSION_OPTION
0x18008f1ce  lea     r8, aApplicationPos; "application/postscript"
0x18008f1d5  lea     rdx, aPs; "ps"
0x18008f1dc  mov     rcx, rbx; this
0x18008f1df  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f1e4  mov     edi, eax
0x18008f1e6  test    eax, eax
0x18008f1e8  jns     short loc_18008F1F4
0x18008f1ea  mov     edx, 62h ; 'b'
0x18008f1ef  jmp     loc_18008EF00
0x18008f1f4  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f1f7  lea     r8, aApplicationVnd_2; "application/vnd.ms-powerpoint.template."...
0x18008f1fe  lea     rdx, aPotm; "potm"
0x18008f205  mov     rcx, rbx; this
0x18008f208  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f20d  mov     edi, eax
0x18008f20f  test    eax, eax
0x18008f211  jns     short loc_18008F21D
0x18008f213  mov     edx, 63h ; 'c'
0x18008f218  jmp     loc_18008EF00
0x18008f21d  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f220  lea     r8, aApplicationVnd_10; "application/vnd.openxmlformats-officedo"...
0x18008f227  lea     rdx, aPotx; "potx"
0x18008f22e  mov     rcx, rbx; this
0x18008f231  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f236  mov     edi, eax
0x18008f238  test    eax, eax
0x18008f23a  jns     short loc_18008F246
0x18008f23c  mov     edx, 64h ; 'd'
0x18008f241  jmp     loc_18008EF00
0x18008f246  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f249  lea     r8, aApplicationVnd_15; "application/vnd.ms-powerpoint.addin.mac"...
0x18008f250  lea     rdx, aPpam; "ppam"
0x18008f257  mov     rcx, rbx; this
0x18008f25a  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
0x18008f25f  mov     edi, eax
0x18008f261  test    eax, eax
0x18008f263  jns     short loc_18008F26F
0x18008f265  mov     edx, 65h ; 'e'
0x18008f26a  jmp     loc_18008EF00
0x18008f26f  xor     r9d, r9d; enum APPX_COMPRESSION_OPTION
0x18008f272  lea     r8, aApplicationVnd_13; "application/vnd.ms-powerpoint.slideshow"...
0x18008f279  lea     rdx, aPpsm; "ppsm"
0x18008f280  mov     rcx, rbx; this
0x18008f283  call    ?CreateMappedItem@AddFileSettingsListContainer@Packaging@Appx@@AEAAJPEBG0W4APPX_COMPRESSION_OPTION@@@Z; Appx::Packaging::AddFileSettingsListContainer::CreateMappedItem(ushort const *,ushort const *,APPX_COMPRESSION_OPTION)
  ... truncated ...
```
