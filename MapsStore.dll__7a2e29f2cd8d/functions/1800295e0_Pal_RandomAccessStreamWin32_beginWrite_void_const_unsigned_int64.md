# Pal::RandomAccessStreamWin32::beginWrite(void const *,unsigned __int64)

- ea: `0x1800295e0`
- end: `0x1800296e0`
- name: `?beginWrite@RandomAccessStreamWin32@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@_K@Pal@@@std@@PEBX_K@Z`
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
- `0x1800295e0`
- `0x180029e10`
- `0x180029f24`
- `0x18002a4d4`
- `0x18002a5ec`
- `0x18002f3c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029679`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029679`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002966f`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18002966f`

## pseudocode

```c
struct _OVERLAPPED **__fastcall Pal::RandomAccessStreamWin32::beginWrite(
        __int64 a1,
        struct _OVERLAPPED **a2,
        const void *a3,
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
  if ( WriteFile(**(HANDLE **)(a1 + 8), a3, a4, 0, lpOverlapped) || (LastError = GetLastError(), LastError == 997) )
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
0x1800295e0  push    rbp
0x1800295e2  push    rbx
0x1800295e3  push    rsi
0x1800295e4  push    rdi
0x1800295e5  push    r14
0x1800295e7  push    r15
0x1800295e9  mov     rbp, rsp
0x1800295ec  sub     rsp, 78h
0x1800295f0  mov     rsi, r9
0x1800295f3  mov     r14, r8
0x1800295f6  mov     r15, rdx
0x1800295f9  mov     rdi, rcx
0x1800295fc  call    ?ensureNotClosed@RandomAccessStreamWin32@Pal@@AEAAXXZ; Pal::RandomAccessStreamWin32::ensureNotClosed(void)
0x180029601  lea     rdx, [rdi+8]
0x180029605  lea     rcx, [rbp+var_30]
0x180029609  call    ??$requirePresent@VStream@Pal@@@Core@@YA?AV?$PresentSharedPtr@VStream@Pal@@@0@AEBV?$shared_ptr@VStream@Pal@@@std@@@Z; Core::requirePresent<Pal::Stream>(std::shared_ptr<Pal::Stream> const &)
0x18002960e  nop
0x18002960f  mov     rdx, rax
0x180029612  lea     rcx, [rbp+var_40]
0x180029616  call    ?create@StreamOperationWin32@Pal@@SA?AV?$shared_ptr@VStreamOperationWin32@Pal@@@std@@AEBV?$PresentSharedPtr@VFileHandle@Pal@@@Core@@@Z; Pal::StreamOperationWin32::create(Core::PresentSharedPtr<Pal::FileHandle> const &)
0x18002961b  nop
0x18002961c  lea     rcx, [rbp+var_30]
0x180029620  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180029625  lea     rdx, [rbp+var_40]
0x180029629  lea     rcx, [rbp+var_20]
0x18002962d  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180029632  lea     rcx, [rdi+20h]
0x180029636  mov     rdx, rax
0x180029639  call    ?add@UntypedAsyncOperationCancelList@Pal@@QEAAXV?$shared_ptr@VUntypedAsyncOperation@Pal@@@std@@@Z; Pal::UntypedAsyncOperationCancelList::add(std::shared_ptr<Pal::UntypedAsyncOperation>)
0x18002963e  mov     rdx, [rbp+var_40]
0x180029642  add     rdx, 100h
0x180029649  mov     eax, [rdi+18h]
0x18002964c  mov     [rdx+10h], eax
0x18002964f  mov     rax, [rdi+18h]
0x180029653  shr     rax, 20h
0x180029657  mov     [rdx+14h], eax
0x18002965a  mov     r8d, esi; nNumberOfBytesToWrite
0x18002965d  mov     rcx, [rdi+8]
0x180029661  mov     [rsp+78h+lpOverlapped], rdx; lpOverlapped
0x180029666  xor     r9d, r9d; lpNumberOfBytesWritten
0x180029669  mov     rdx, r14; lpBuffer
0x18002966c  mov     rcx, [rcx]; hFile
0x18002966f  call    cs:__imp_WriteFile
0x180029675  test    eax, eax
0x180029677  jnz     short loc_1800296C1
0x180029679  call    cs:__imp_GetLastError
0x18002967f  cmp     eax, 3E5h
0x180029684  jz      short loc_1800296C1
0x180029686  mov     edx, eax
0x180029688  lea     rcx, [rbp+arg_0]
0x18002968c  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x180029691  mov     edx, [rax]
0x180029693  lea     rcx, [rbp+var_20]
0x180029697  call    ?createFailed@?$AsyncOperation@_K@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@_K@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<unsigned __int64>::createFailed(Core::StatusCode)
0x18002969c  mov     rdx, rax
0x18002969f  mov     rcx, r15
0x1800296a2  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800296a7  lea     rcx, [rbp+var_20]
0x1800296ab  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800296b0  nop
0x1800296b1  mov     rcx, [rbp+var_38]; this
0x1800296b5  test    rcx, rcx
0x1800296b8  jz      short loc_1800296D0
0x1800296ba  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800296bf  jmp     short loc_1800296D0
0x1800296c1  mov     rax, [rbp+var_40]
0x1800296c5  mov     [r15], rax
0x1800296c8  mov     rax, [rbp+var_38]
0x1800296cc  mov     [r15+8], rax
0x1800296d0  mov     rax, r15
0x1800296d3  add     rsp, 78h
0x1800296d7  pop     r15
0x1800296d9  pop     r14
0x1800296db  pop     rdi
0x1800296dc  pop     rsi
0x1800296dd  pop     rbx
0x1800296de  pop     rbp
0x1800296df  retn
```
