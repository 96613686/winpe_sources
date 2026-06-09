# CloudCacheInitializer::LoadRS3CacheBlob(HKEY__ *)

- ea: `0x1800cff10`
- end: `0x1800d0299`
- name: `?LoadRS3CacheBlob@CloudCacheInitializer@@CA?AV?$versioned@Vblob@bond@@@@PEAUHKEY__@@@Z`
- size: `905`
- prototype: `unsigned __int8 *__fastcall(unsigned __int8 *, __int64)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x180012ad4`

## callees

- `0x18000dfe4`
- `0x18000e8d0`
- `0x180016cf4`
- `0x18002605c`
- `0x18002aa88`
- `0x18002c020`
- `0x180047904`
- `0x180051a78`
- `0x180051b84`
- `0x180062040`
- `0x18007e6d8`
- `0x180086db8`
- `0x1800b3714`
- `0x1800cff10`
- `0x1800d02a0`
- `0x1800d02cc`
- `0x1800d1d50`
- `0x1801201a0`
- `0x1801202a0`

## import_xrefs

- `SHCORE!SHCreateStreamOnFileW` at `0x1800d00f6`
- `SHCORE!SHCreateStreamOnFileW` at `0x1800d00f6`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d00a9`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x1800d00a9`

## string_xrefs

- `0x1800cffdf`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d000d`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d0031`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d007b`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d00bd`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d010a`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d015c`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`
- `0x1800d01a3`: `onecoreuap\shell\cloudstore\store\cache\src\cloudcacheinitializer.cpp`

## pseudocode

```c
unsigned __int8 *__fastcall CloudCacheInitializer::LoadRS3CacheBlob(unsigned __int8 *a1, __int64 a2)
{
  const struct std::nothrow_t *v3; // rdx
  IStream *ppstm[2]; // [rsp+30h] [rbp-D0h] BYREF
  int v6; // [rsp+40h] [rbp-C0h]
  PCWSTR pszPathIn; // [rsp+48h] [rbp-B8h]
  unsigned __int8 *v8; // [rsp+60h] [rbp-A0h] BYREF

  v8 = a1;
  pszPathIn = 0;
  CloudStoreUtilities::GetRegistryDataAlloc(&v8, a2, L"Data", 8);
  *(_OWORD *)ppstm = 0;
  v6 = 0;
  versioned<bond::blob>::versioned<bond::blob>(a1, ppstm, 0);
  boost::detail::shared_count::~shared_count((boost::detail::shared_count *)&ppstm[1]);
  if ( v8 )
    operator delete(v8, v3);
  return a1;
}

```

## disassembly

```asm
0x1800cff10  mov     [rsp-8+arg_10], rbx
0x1800cff15  push    rbp
0x1800cff16  push    rsi
0x1800cff17  push    rdi
0x1800cff18  push    r14
0x1800cff1a  push    r15
0x1800cff1c  lea     rbp, [rsp-1F0h]
0x1800cff24  sub     rsp, 2F0h
0x1800cff2b  mov     rax, cs:__security_cookie
0x1800cff32  xor     rax, rsp
0x1800cff35  mov     [rbp+210h+var_30], rax
0x1800cff3c  mov     rdi, rcx
0x1800cff3f  mov     [rsp+310h+var_2B0], rcx
0x1800cff44  xor     r15d, r15d
0x1800cff47  mov     [rsp+310h+pszPathIn], r15
0x1800cff4c  lea     rax, [rsp+310h+pszPathIn]
0x1800cff51  mov     qword ptr [rsp+310h+var_2F0], rax; int
0x1800cff56  lea     r9d, [r15+8]
0x1800cff5a  lea     r8, aData_0; "Data"
0x1800cff61  lea     rcx, [rsp+310h+var_2B0]
0x1800cff66  call    ?GetRegistryDataAlloc@CloudStoreUtilities@@YA?AV?$unique_ptr@$$BY0A@$$CBEU?$default_delete@$$BY0A@$$CBE@std@@@std@@PEAUHKEY__@@PEBGKPEA_K@Z; CloudStoreUtilities::GetRegistryDataAlloc(HKEY__ *,ushort const *,ulong,unsigned __int64 *)
0x1800cff6b  nop
0x1800cff6c  mov     rsi, [rsp+310h+pszPathIn]
0x1800cff71  test    rsi, rsi
0x1800cff74  jnz     short loc_1800CFFB2
0x1800cff76  xorps   xmm0, xmm0
0x1800cff79  movdqu  xmmword ptr [rsp+310h+ppstm], xmm0
0x1800cff7f  mov     [rsp+310h+var_2D0], r15d
0x1800cff84  xor     r8d, r8d
0x1800cff87  lea     rdx, [rsp+310h+ppstm]
0x1800cff8c  mov     rcx, rdi
0x1800cff8f  call    ??0?$versioned@Vblob@bond@@@@QEAA@AEBVblob@bond@@_K@Z; versioned<bond::blob>::versioned<bond::blob>(bond::blob const &,unsigned __int64)
0x1800cff94  lea     rcx, [rsp+310h+ppstm+8]; this
0x1800cff99  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800cff9e  nop
0x1800cff9f  mov     rcx, [rsp+310h+var_2B0]
0x1800cffa4  test    rcx, rcx
0x1800cffa7  jz      loc_1800D0270
0x1800cffad  jmp     loc_1800D026B
0x1800cffb2  mov     [rsp+310h+var_2A4], r15
0x1800cffb7  mov     [rsp+310h+var_29C], r15d
0x1800cffbc  mov     r8d, esi; unsigned int
0x1800cffbf  mov     rbx, [rsp+310h+var_2B0]
0x1800cffc4  mov     rdx, rbx; unsigned __int8 *
0x1800cffc7  lea     rcx, [rsp+310h+var_2A8]; this
0x1800cffcc  call    ?DeSerialize@CloudStoreMetadata@Cloud@Storage@Internal@Windows@@QEAAJPEBEI@Z; Windows::Internal::Storage::Cloud::CloudStoreMetadata::DeSerialize(uchar const *,uint)
0x1800cffd1  mov     rcx, [rbp+218h]; this
0x1800cffd8  test    eax, eax
0x1800cffda  jns     short loc_1800CFFF1
0x1800cffdc  mov     r9d, eax; char *
0x1800cffdf  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800cffe6  mov     edx, 35Fh; void *
0x1800cffeb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800cfff1  lea     r8, [rsi-10h]
0x1800cfff5  cmp     [rsp+310h+var_29C], 1
0x1800cfffa  jnz     loc_1800D01F5
0x1800d0000  mov     rcx, [rbp+218h]; this
0x1800d0007  test    r8b, 1
0x1800d000b  jz      short loc_1800D001F
0x1800d000d  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d0014  mov     edx, 366h; void *
0x1800d0019  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d001f  mov     rcx, [rbp+218h]; this
0x1800d0026  shr     r8, 1
0x1800d0029  cmp     [rbx+r8*2+10h], r15w
0x1800d002f  jz      short loc_1800D0043
0x1800d0031  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d0038  mov     edx, 368h; void *
0x1800d003d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800d0043  mov     [rsp+310h+pszPathIn], r15
0x1800d0048  lea     rax, [rsp+310h+pszPathIn]
0x1800d004d  mov     [rsp+310h+ppstm], rax
0x1800d0052  mov     [rsp+310h+ppstm+8], r15
0x1800d0057  mov     byte ptr [rsp+310h+var_2D0], 1
0x1800d005c  lea     r8, [rsp+310h+ppstm+8]; unsigned __int16 *
0x1800d0061  lea     rcx, LocaleName; this
0x1800d0068  call    ?GetFileStorageRootPath@CloudStoreUtilities@@YAJPEBG0PEAPEAG@Z; CloudStoreUtilities::GetFileStorageRootPath(ushort const *,ushort const *,ushort * *)
0x1800d006d  mov     rcx, [rbp+218h]; this
0x1800d0074  test    eax, eax
0x1800d0076  jns     short loc_1800D008D
0x1800d0078  mov     r9d, eax; char *
0x1800d007b  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d0082  mov     edx, 36Ch; void *
0x1800d0087  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d008d  lea     rcx, [rsp+310h+ppstm]
0x1800d0092  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1800d0097  lea     r9, [rbx+10h]; pszMore
0x1800d009b  mov     r8, [rsp+310h+pszPathIn]; pszPathIn
0x1800d00a0  mov     edx, 104h; cchPathOut
0x1800d00a5  lea     rcx, [rbp+210h+pszPathOut]; pszPathOut
0x1800d00a9  call    cs:__imp_PathCchCombine
0x1800d00af  mov     rcx, [rbp+218h]; this
0x1800d00b6  test    eax, eax
0x1800d00b8  jns     short loc_1800D00CF
0x1800d00ba  mov     r9d, eax; char *
0x1800d00bd  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d00c4  mov     edx, 36Fh; void *
0x1800d00c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d00cf  mov     [rsp+310h+var_2B8], r15
0x1800d00d4  lea     rax, [rsp+310h+var_2B8]
0x1800d00d9  mov     [rsp+310h+ppstm], rax
0x1800d00de  mov     [rsp+310h+ppstm+8], r15
0x1800d00e3  mov     byte ptr [rsp+310h+var_2D0], 1
0x1800d00e8  lea     r8, [rsp+310h+ppstm+8]; ppstm
0x1800d00ed  mov     edx, 20h ; ' '; grfMode
0x1800d00f2  lea     rcx, [rbp+210h+pszPathOut]; pszFile
0x1800d00f6  call    cs:__imp_SHCreateStreamOnFileW
0x1800d00fc  mov     rcx, [rbp+218h]; this
0x1800d0103  test    eax, eax
0x1800d0105  jns     short loc_1800D011C
0x1800d0107  mov     r9d, eax; char *
0x1800d010a  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d0111  mov     edx, 372h; void *
0x1800d0116  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d011c  lea     rcx, [rsp+310h+ppstm]
0x1800d0121  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800d0126  mov     [rsp+310h+var_2C0], r15
0x1800d012b  lea     rax, [rsp+310h+var_2C0]
0x1800d0130  mov     [rsp+310h+ppstm], rax
0x1800d0135  mov     [rsp+310h+ppstm+8], r15
0x1800d013a  mov     byte ptr [rsp+310h+var_2D0], 1
0x1800d013f  lea     rdx, [rsp+310h+ppstm+8]; struct Windows::Storage::Streams::IBuffer **
0x1800d0144  mov     rcx, [rsp+310h+var_2B8]; struct IStream *
0x1800d0149  call    ?ConvertIStreamToIBuffer@@YAJPEAUIStream@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; ConvertIStreamToIBuffer(IStream *,Windows::Storage::Streams::IBuffer * *)
0x1800d014e  mov     rcx, [rbp+218h]; this
0x1800d0155  test    eax, eax
0x1800d0157  jns     short loc_1800D016E
0x1800d0159  mov     r9d, eax; char *
0x1800d015c  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d0163  mov     edx, 375h; void *
0x1800d0168  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d016e  lea     rcx, [rsp+310h+ppstm]
0x1800d0173  call    ??1?$out_param_t@V?$com_ptr_t@U?$IAsyncOperation@PEAVGetDefaultSignInAccountResult@Web@Authentication@Security@Internal@Windows@@@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>::~out_param_t<wil::com_ptr_t<Windows::Foundation::IAsyncOperation<Windows::Internal::Security::Authentication::Web::GetDefaultSignInAccountResult *>,wil::err_exception_policy>>(void)
0x1800d0178  xorps   xmm0, xmm0
0x1800d017b  movdqu  xmmword ptr [rsp+310h+ppstm], xmm0
0x1800d0181  mov     [rsp+310h+var_2D0], r15d
0x1800d0186  lea     rdx, [rsp+310h+ppstm]; struct bond::blob *
0x1800d018b  mov     rcx, [rsp+310h+var_2C0]; struct Windows::Storage::Streams::IBuffer *
0x1800d0190  call    ?ConvertIBufferToBondBlob@@YAJPEAUIBuffer@Streams@Storage@Windows@@PEAVblob@bond@@@Z; ConvertIBufferToBondBlob(Windows::Storage::Streams::IBuffer *,bond::blob *)
0x1800d0195  mov     rcx, [rbp+218h]; this
0x1800d019c  test    eax, eax
0x1800d019e  jns     short loc_1800D01B5
0x1800d01a0  mov     r9d, eax; char *
0x1800d01a3  lea     r8, aOnecoreuapShel_17; "onecoreuap\\shell\\cloudstore\\store\\c"...
0x1800d01aa  mov     edx, 378h; void *
0x1800d01af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800d01b5  mov     r8, [rsp+310h+var_2A4]
0x1800d01ba  lea     rdx, [rsp+310h+ppstm]
0x1800d01bf  mov     rcx, rdi
0x1800d01c2  call    ??0?$versioned@Vblob@bond@@@@QEAA@AEBVblob@bond@@_K@Z; versioned<bond::blob>::versioned<bond::blob>(bond::blob const &,unsigned __int64)
0x1800d01c7  nop
0x1800d01c8  lea     rcx, [rsp+310h+ppstm+8]; this
0x1800d01cd  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800d01d2  nop
0x1800d01d3  lea     rcx, [rsp+310h+var_2C0]
0x1800d01d8  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800d01dd  nop
0x1800d01de  lea     rcx, [rsp+310h+var_2B8]
0x1800d01e3  call    ??1?$com_ptr_t@V?$AgileVector@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@U?$DefaultEqualityPredicate@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4Collections@Foundation@5@U?$DefaultLifetimeTraits@PEAVCloudStoreData@Cloud@Storage@Internal@Windows@@@4785@$0A@@Internal@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>::~com_ptr_t<Windows::Foundation::Collections::Internal::AgileVector<Windows::Internal::Storage::Cloud::CloudStoreData *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Internal::Storage::Cloud::CloudStoreData *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Internal::Storage::Cloud::CloudStoreData *>,0>,wil::err_exception_policy>(void)
0x1800d01e8  nop
0x1800d01e9  lea     rcx, [rsp+310h+pszPathIn]
0x1800d01ee  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d01f3  jmp     short loc_1800D0263
0x1800d01f5  mov     [rbp+210h+var_288], r15
0x1800d01f9  mov     [rbp+210h+var_280], r15
0x1800d01fd  mov     [rbp+210h+var_278], r15
0x1800d0201  mov     [rbp+210h+var_270], r15d
0x1800d0205  mov     [rbp+210h+var_26C], 20h ; ' '
0x1800d020c  mov     [rbp+210h+var_268], 0FFFFFFFFh
0x1800d0213  xorps   xmm0, xmm0
0x1800d0216  movdqa  [rbp+210h+var_260], xmm0
0x1800d021b  xorps   xmm1, xmm1
0x1800d021e  movdqa  [rbp+210h+var_250], xmm1
0x1800d0223  lea     rdx, [rbx+10h]
0x1800d0227  lea     rcx, [rbp+210h+var_290]
0x1800d022b  call    ?Write@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAAXPEBXI@Z; bond::OutputMemoryStream<std::allocator<char>>::Write(void const *,uint)
0x1800d0230  lea     rdx, [rsp+310h+ppstm]
0x1800d0235  lea     rcx, [rbp+210h+var_290]
0x1800d0239  call    ?GetBuffer@?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEBA?AVblob@2@XZ; bond::OutputMemoryStream<std::allocator<char>>::GetBuffer(void)
0x1800d023e  mov     r8, [rsp+310h+var_2A4]
0x1800d0243  mov     rdx, rax
0x1800d0246  mov     rcx, rdi
0x1800d0249  call    ??0?$versioned@Vblob@bond@@@@QEAA@AEBVblob@bond@@_K@Z; versioned<bond::blob>::versioned<bond::blob>(bond::blob const &,unsigned __int64)
0x1800d024e  lea     rcx, [rsp+310h+ppstm+8]; this
0x1800d0253  call    ??1shared_count@detail@boost@@QEAA@XZ; boost::detail::shared_count::~shared_count(void)
0x1800d0258  nop
0x1800d0259  lea     rcx, [rbp+210h+var_290]
0x1800d025d  call    ??1?$OutputMemoryStream@V?$allocator@D@std@@@bond@@QEAA@XZ; bond::OutputMemoryStream<std::allocator<char>>::~OutputMemoryStream<std::allocator<char>>(void)
0x1800d0262  nop
0x1800d0263  test    rbx, rbx
0x1800d0266  jz      short loc_1800D0270
0x1800d0268  mov     rcx, rbx; void *
0x1800d026b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800d0270  mov     rax, rdi
0x1800d0273  mov     rcx, [rbp+210h+var_30]
0x1800d027a  xor     rcx, rsp; StackCookie
0x1800d027d  call    __security_check_cookie
0x1800d0282  mov     rbx, [rsp+310h+arg_10]
0x1800d028a  add     rsp, 2F0h
0x1800d0291  pop     r15
0x1800d0293  pop     r14
0x1800d0295  pop     rdi
0x1800d0296  pop     rsi
0x1800d0297  pop     rbp
0x1800d0298  retn
```
