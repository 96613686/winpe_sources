# Pal::RandomAccessStreamWin32::beginRead(void *,unsigned __int64)

- ea: `0x1800294d0`
- end: `0x1800295d0`
- name: `?beginRead@RandomAccessStreamWin32@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@PEAX_K@Z`
- size: `256`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops`

## callees

- `0x1800161b0`
- `0x180016770`
- `0x180016d58`
- `0x18001b9e0`
- `0x1800294d0`
- `0x180029e10`
- `0x180029f24`
- `0x18002a4d4`
- `0x18002a5ec`
- `0x18002f3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029569`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029569`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002955f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x18002955f`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
struct _OVERLAPPED **__fastcall Pal::RandomAccessStreamWin32::beginRead(
        __int64 a1,
        struct _OVERLAPPED **a2,
        void *a3,
        DWORD a4)
{
  __int64 v8; // rax
  __int64 v9; // rax
  struct _OVERLAPPED *lpOverlapped; // rdx
  DWORD LastError; // eax
  unsigned int *v12; // rax
  __int64 Failed; // rax
  struct _OVERLAPPED *v15; // [rsp+38h] [rbp-40h] BYREF
  std::_Ref_count_base *v16; // [rsp+40h] [rbp-38h]
  _BYTE v17[16]; // [rsp+48h] [rbp-30h] BYREF
  _BYTE v18[32]; // [rsp+58h] [rbp-20h] BYREF
  char v19; // [rsp+B0h] [rbp+38h] BYREF

  Pal::RandomAccessStreamWin32::ensureNotClosed((Pal::RandomAccessStreamWin32 *)a1);
  v8 = Core::requirePresent<Pal::Stream>(v17, a1 + 8);
  Pal::StreamOperationWin32::create(&v15, v8);
  Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v17);
  v9 = std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
         v18,
         &v15);
  Pal::UntypedAsyncOperationCancelList::add(a1 + 32, v9);
  lpOverlapped = v15 + 8;
  v15[8].Pointer = *(PVOID *)(a1 + 24);
  if ( ReadFile(**(HANDLE **)(a1 + 8), a3, a4, 0, lpOverlapped) || (LastError = GetLastError(), LastError == 997) )
  {
    *a2 = v15;
    a2[1] = (struct _OVERLAPPED *)v16;
  }
  else
  {
    v12 = (unsigned int *)PalWindows::errorCodeFromWin32Error(&v19, LastError);
    Failed = Pal::AsyncOperation<unsigned __int64>::createFailed(v18, *v12);
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      a2,
      Failed);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v18);
    if ( v16 )
      std::_Ref_count_base::_Decref(v16);
  }
  return a2;
}

```

## disassembly

```asm
0x1800294d0  push    rbp
0x1800294d2  push    rbx
0x1800294d3  push    rsi
0x1800294d4  push    rdi
0x1800294d5  push    r14
0x1800294d7  push    r15
0x1800294d9  mov     rbp, rsp
0x1800294dc  sub     rsp, 78h
0x1800294e0  mov     rsi, r9
0x1800294e3  mov     r14, r8
0x1800294e6  mov     r15, rdx
0x1800294e9  mov     rdi, rcx
0x1800294ec  call    ?ensureNotClosed@RandomAccessStreamWin32@Pal@@AEAAXXZ; Pal::RandomAccessStreamWin32::ensureNotClosed(void)
0x1800294f1  lea     rdx, [rdi+8]
0x1800294f5  lea     rcx, [rbp+var_30]
0x1800294f9  call    ??$requirePresent@VStream@Pal@@@Core@@YA?AV?$PresentSharedPtr@VStream@Pal@@@0@AEBV?$shared_ptr@VStream@Pal@@@std@@@Z; Core::requirePresent<Pal::Stream>(std::shared_ptr<Pal::Stream> const &)
0x1800294fe  nop
0x1800294ff  mov     rdx, rax
0x180029502  lea     rcx, [rbp+var_40]
0x180029506  call    ?create@StreamOperationWin32@Pal@@SA?AV?$shared_ptr@VStreamOperationWin32@Pal@@@std@@AEBV?$PresentSharedPtr@VFileHandle@Pal@@@Core@@@Z; Pal::StreamOperationWin32::create(Core::PresentSharedPtr<Pal::FileHandle> const &)
0x18002950b  nop
0x18002950c  lea     rcx, [rbp+var_30]
0x180029510  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180029515  lea     rdx, [rbp+var_40]
0x180029519  lea     rcx, [rbp+var_20]
0x18002951d  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180029522  lea     rcx, [rdi+20h]
0x180029526  mov     rdx, rax
0x180029529  call    ?add@UntypedAsyncOperationCancelList@Pal@@QEAAXV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Z; Pal::UntypedAsyncOperationCancelList::add(std::shared_ptr<Pal::UntypedAsyncOperation>)
0x18002952e  mov     rdx, [rbp+var_40]
0x180029532  add     rdx, 100h
0x180029539  mov     eax, [rdi+18h]
0x18002953c  mov     [rdx+10h], eax
0x18002953f  mov     rax, [rdi+18h]
0x180029543  shr     rax, 20h
0x180029547  mov     [rdx+14h], eax
0x18002954a  mov     r8d, esi; nNumberOfBytesToRead
0x18002954d  mov     rcx, [rdi+8]
0x180029551  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x180029556  xor     r9d, r9d; lpNumberOfBytesRead
0x180029559  mov     rdx, r14; lpBuffer
0x18002955c  mov     rcx, [rcx]; hFile
0x18002955f  call    cs:__imp_ReadFile
0x180029565  test    eax, eax
0x180029567  jnz     short loc_1800295B1
0x180029569  call    cs:__imp_GetLastError
0x18002956f  cmp     eax, 3E5h
0x180029574  jz      short loc_1800295B1
0x180029576  mov     edx, eax
0x180029578  lea     rcx, [rbp+arg_0]
0x18002957c  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x180029581  mov     edx, [rax]
0x180029583  lea     rcx, [rbp+var_20]
0x180029587  call    ?createFailed@?$AsyncOperation@_K@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@_K@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<unsigned __int64>::createFailed(Core::StatusCode)
0x18002958c  mov     rdx, rax
0x18002958f  mov     rcx, r15
0x180029592  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180029597  lea     rcx, [rbp+var_20]
0x18002959b  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800295a0  nop
0x1800295a1  mov     rcx, [rbp+var_38]; this
0x1800295a5  test    rcx, rcx
0x1800295a8  jz      short loc_1800295C0
0x1800295aa  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800295af  jmp     short loc_1800295C0
0x1800295b1  mov     rax, [rbp+var_40]
0x1800295b5  mov     [r15], rax
0x1800295b8  mov     rax, [rbp+var_38]
0x1800295bc  mov     [r15+8], rax
0x1800295c0  mov     rax, r15
0x1800295c3  add     rsp, 78h
0x1800295c7  pop     r15
0x1800295c9  pop     r14
0x1800295cb  pop     rdi
0x1800295cc  pop     rsi
0x1800295cd  pop     rbx
0x1800295ce  pop     rbp
0x1800295cf  retn
```
