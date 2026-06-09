# Pal::IOImplWin32Base::beginOpenFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation,Pal::FileAccessKind)

- ea: `0x180029290`
- end: `0x1800294c9`
- name: `?beginOpenFile@IOImplWin32Base@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4FileLocation@2@W4FileAccessKind@2@@Z`
- size: `569`
- prototype: `__int64 __fastcall(_QWORD *, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, service_task, broker_com_uri`

## callees

- `0x18000d090`
- `0x18000d49c`
- `0x1800126c4`
- `0x180012720`
- `0x180016548`
- `0x180016770`
- `0x180016d58`
- `0x18001b9e0`
- `0x1800226a0`
- `0x180024c14`
- `0x180025c68`
- `0x180029290`
- `0x180029b4c`
- `0x180029edc`
- `0x18002a1e0`
- `0x18002a5ec`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293e2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800293d2`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x1800293d2`

## pseudocode

```c
__int64 __fastcall Pal::IOImplWin32Base::beginOpenFile(_QWORD *a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  unsigned int v5; // edi
  __int64 v9; // rax
  unsigned int v10; // edi
  unsigned int v11; // r14d
  __int64 v12; // rbx
  DWORD LastError; // eax
  unsigned int *v14; // rax
  __int64 v15; // rax
  std::_Ref_count_base *v16; // rdi
  __int64 v17; // rax
  _BYTE v19[8]; // [rsp+30h] [rbp-81h] BYREF
  __int128 v20; // [rsp+38h] [rbp-79h] BYREF
  _DWORD v21[2]; // [rsp+50h] [rbp-61h] BYREF
  __int64 v22; // [rsp+58h] [rbp-59h]
  __int128 v23; // [rsp+60h] [rbp-51h]
  std::_Ref_count_base *v24; // [rsp+70h] [rbp-41h] BYREF
  std::_Ref_count_base *v25; // [rsp+78h] [rbp-39h]
  _BYTE v26[32]; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp-1h] BYREF

  v5 = a4;
  *(_QWORD *)&v20 = a2;
  if ( (_DWORD)a4 != 4 || a1[19] )
  {
    Pal::IOImplWindows::composeFullFileName(a1, v27, a3, a4);
    if ( a5 == 1 )
    {
      std::wstring::wstring(v26);
      std::wstring::wstring(&v24);
      (*(void (__fastcall **)(_QWORD *, __int64, _BYTE *, std::_Ref_count_base **))(*a1 + 88LL))(a1, a3, v26, &v24);
      (*(void (__fastcall **)(_QWORD *, _BYTE *, _QWORD))(*a1 + 40LL))(a1, v26, v5);
      std::wstring::_Tidy_deallocate(&v24);
      std::wstring::_Tidy_deallocate(v26);
      v10 = -1073741824;
      v11 = 2;
    }
    else
    {
      v11 = 3;
      v10 = 0x80000000;
    }
    v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    CallingStateTracker::CallingStateTracker(v19);
    v21[0] = 32;
    v21[1] = 128;
    v22 = 0x40000000;
    v23 = 0;
    *(_QWORD *)&v20 = CreateFile2(v12, v10, 1, v11, v21);
    if ( (_QWORD)v20 == -1 )
    {
      LastError = GetLastError();
      v14 = (unsigned int *)PalWindows::errorCodeFromWin32Error(&v20, LastError);
      v15 = Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(&v24, *v14);
      std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
        a2,
        v15);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v24);
    }
    else
    {
      v16 = (std::_Ref_count_base *)operator new(0xA0u);
      v24 = v16;
      *(_OWORD *)v16 = 0;
      *((_DWORD *)v16 + 2) = 1;
      *((_DWORD *)v16 + 3) = 1;
      *(_QWORD *)v16 = &std::_Ref_count_obj2<pplx::details::_Task_impl<unsigned char>>::`vftable';
      std::_Construct_in_place<Pal::RandomAccessStreamWin32,void * &>((char *)v16 + 16, &v20);
      v24 = (std::_Ref_count_base *)((char *)v16 + 16);
      v25 = v16;
      v20 = 0;
      v17 = Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createSucceeded(v26, &v24);
      std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
        a2,
        v17);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v26);
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
    }
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v19);
    std::wstring::_Tidy_deallocate(v27);
  }
  else
  {
    v9 = Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(&v24, 8388610);
    std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<unsigned char> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<unsigned char> const>>>::CacheEntry>(
      a2,
      v9);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v24);
  }
  return a2;
}

```

## disassembly

```asm
0x180029290  push    rbp
0x180029292  push    rbx
0x180029293  push    rsi
0x180029294  push    rdi
0x180029295  push    r14
0x180029297  lea     rbp, [rsp-2Fh]
0x18002929c  sub     rsp, 0E0h
0x1800292a3  mov     rax, cs:__security_cookie
0x1800292aa  xor     rax, rsp
0x1800292ad  mov     [rbp+4Fh+var_30], rax
0x1800292b1  mov     edi, r9d
0x1800292b4  mov     r14, r8
0x1800292b7  mov     rsi, rdx
0x1800292ba  mov     rbx, rcx
0x1800292bd  mov     qword ptr [rbp+4Fh+var_C8], rdx
0x1800292c1  cmp     r9d, 4
0x1800292c5  jnz     short loc_1800292F9
0x1800292c7  cmp     qword ptr [rcx+98h], 0
0x1800292cf  jnz     short loc_1800292F9
0x1800292d1  mov     edx, cs:dword_1800A4920
0x1800292d7  lea     rcx, [rbp+4Fh+var_90]
0x1800292db  call    ?createFailed@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(Core::StatusCode)
0x1800292e0  mov     rdx, rax
0x1800292e3  mov     rcx, rsi
0x1800292e6  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x1800292eb  lea     rcx, [rbp+4Fh+var_90]
0x1800292ef  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800292f4  jmp     loc_1800294AC
0x1800292f9  lea     rdx, [rbp+4Fh+var_50]
0x1800292fd  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x180029302  nop
0x180029303  mov     ecx, [rbp+4Fh+arg_20]
0x180029306  cmp     ecx, 1
0x180029309  jnz     short loc_180029365
0x18002930b  lea     rcx, [rbp+4Fh+var_70]
0x18002930f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180029314  nop
0x180029315  lea     rcx, [rbp+4Fh+var_90]
0x180029319  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18002931e  nop
0x18002931f  mov     rax, [rbx]
0x180029322  lea     r9, [rbp+4Fh+var_90]
0x180029326  lea     r8, [rbp+4Fh+var_70]
0x18002932a  mov     rdx, r14
0x18002932d  mov     rcx, rbx
0x180029330  mov     rax, [rax+58h]
0x180029334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029339  mov     rax, [rbx]
0x18002933c  mov     r8d, edi
0x18002933f  lea     rdx, [rbp+4Fh+var_70]
0x180029343  mov     rcx, rbx
0x180029346  mov     rax, [rax+28h]
0x18002934a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002934f  nop
0x180029350  lea     rcx, [rbp+4Fh+var_90]
0x180029354  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029359  nop
0x18002935a  lea     rcx, [rbp+4Fh+var_70]
0x18002935e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180029363  jmp     short loc_18002936E
0x180029365  test    ecx, ecx
0x180029367  jz      short loc_18002937B
0x180029369  cmp     ecx, 1
0x18002936c  jnz     short loc_18002937B
0x18002936e  mov     edi, 0C0000000h
0x180029373  mov     r14d, 2
0x180029379  jmp     short loc_180029386
0x18002937b  mov     r14d, 3
0x180029381  mov     edi, 80000000h
0x180029386  lea     rcx, [rbp+4Fh+var_50]
0x18002938a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002938f  mov     rbx, rax
0x180029392  lea     rcx, [rsp+100h+var_D0]
0x180029397  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18002939c  nop
0x18002939d  mov     [rbp+4Fh+var_B0], 20h ; ' '
0x1800293a4  mov     [rbp+4Fh+var_AC], 80h
0x1800293ab  mov     [rbp+4Fh+var_A8], 40000000h
0x1800293b3  xorps   xmm0, xmm0
0x1800293b6  movdqu  [rbp+4Fh+var_A0], xmm0
0x1800293bb  lea     rax, [rbp+4Fh+var_B0]
0x1800293bf  mov     [rsp+100h+var_E0], rax
0x1800293c4  mov     r9d, r14d
0x1800293c7  mov     r8d, 1
0x1800293cd  mov     edx, edi
0x1800293cf  mov     rcx, rbx
0x1800293d2  call    cs:__imp_CreateFile2
0x1800293d8  mov     qword ptr [rbp+4Fh+var_C8], rax
0x1800293dc  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800293e0  jnz     short loc_180029417
0x1800293e2  call    cs:__imp_GetLastError
0x1800293e8  mov     edx, eax
0x1800293ea  lea     rcx, [rbp+4Fh+var_C8]
0x1800293ee  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x1800293f3  mov     edx, [rax]
0x1800293f5  lea     rcx, [rbp+4Fh+var_90]
0x1800293f9  call    ?createFailed@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(Core::StatusCode)
0x1800293fe  mov     rdx, rax
0x180029401  mov     rcx, rsi
0x180029404  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x180029409  lea     rcx, [rbp+4Fh+var_90]
0x18002940d  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180029412  jmp     loc_180029498
0x180029417  mov     ecx, 0A0h; Size
0x18002941c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180029421  mov     rdi, rax
0x180029424  mov     [rbp+4Fh+var_90], rax
0x180029428  xorps   xmm0, xmm0
0x18002942b  movups  xmmword ptr [rax], xmm0
0x18002942e  mov     dword ptr [rax+8], 1
0x180029435  mov     dword ptr [rax+0Ch], 1
0x18002943c  lea     rax, ??_7?$_Ref_count_obj2@U?$_Task_impl@E@details@pplx@@@std@@6B@; const std::_Ref_count_obj2<pplx::details::_Task_impl<uchar>>::`vftable'
0x180029443  mov     [rdi], rax
0x180029446  lea     rbx, [rdi+10h]
0x18002944a  lea     rdx, [rbp+4Fh+var_C8]
0x18002944e  mov     rcx, rbx
0x180029451  call    ??$_Construct_in_place@VRandomAccessStreamWin32@Pal@@AEAPEAX@std@@YAXAEAVRandomAccessStreamWin32@Pal@@AEAPEAX@Z; std::_Construct_in_place<Pal::RandomAccessStreamWin32,void * &>(Pal::RandomAccessStreamWin32 &,void * &)
0x180029456  nop
0x180029457  mov     [rbp+4Fh+var_90], rbx
0x18002945b  mov     [rbp+4Fh+var_88], rdi
0x18002945f  xorps   xmm0, xmm0
0x180029462  movdqu  [rbp+4Fh+var_C8], xmm0
0x180029467  lea     rdx, [rbp+4Fh+var_90]
0x18002946b  lea     rcx, [rbp+4Fh+var_70]
0x18002946f  call    ?createSucceeded@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@$$QEBV?$shared_ptr@VStream@Pal@@@std@@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createSucceeded(std::shared_ptr<Pal::Stream> const &&)
0x180029474  mov     rdx, rax
0x180029477  mov     rcx, rsi
0x18002947a  call    ??0?$shared_ptr@VCacheEntry@?$MemoryCache@UBlobId@PersistentMapsCache@MapControl@@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@UHashFunction@123@U?$AlwaysTruePredicate@V?$shared_ptr@$$CBV?$vector@EV?$allocator@E@std@@@std@@@std@@@Core@@@Utility@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry>(std::shared_ptr<Utility::MemoryCache<MapControl::PersistentMapsCache::BlobId,std::shared_ptr<std::vector<uchar> const>,MapControl::PersistentMapsCache::BlobId::HashFunction,Core::AlwaysTruePredicate<std::shared_ptr<std::vector<uchar> const>>>::CacheEntry> const &)
0x18002947f  lea     rcx, [rbp+4Fh+var_70]
0x180029483  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180029488  nop
0x180029489  mov     rcx, [rbp+4Fh+var_88]; this
0x18002948d  test    rcx, rcx
0x180029490  jz      short loc_180029498
0x180029492  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180029497  nop
0x180029498  lea     rcx, [rsp+100h+var_D0]; this
0x18002949d  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x1800294a2  nop
0x1800294a3  lea     rcx, [rbp+4Fh+var_50]
0x1800294a7  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800294ac  mov     rax, rsi
0x1800294af  mov     rcx, [rbp+4Fh+var_30]
0x1800294b3  xor     rcx, rsp; StackCookie
0x1800294b6  call    __security_check_cookie
0x1800294bb  add     rsp, 0E0h
0x1800294c2  pop     r14
0x1800294c4  pop     rdi
0x1800294c5  pop     rsi
0x1800294c6  pop     rbx
0x1800294c7  pop     rbp
0x1800294c8  retn
```
