# Pal::IOImplWin32Base::beginOpenFile(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,Pal::FileLocation,Pal::FileAccessKind)

- ea: `0x180015400`
- end: `0x180015639`
- name: `?beginOpenFile@IOImplWin32Base@Pal@@UEAA?AV?$shared_ptr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@std@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@4@W4FileLocation@2@W4FileAccessKind@2@@Z`
- size: `569`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, broker_com_uri`

## callees

- `0x1800094a0`
- `0x180009988`
- `0x18000ba50`
- `0x18000c2f8`
- `0x18000c354`
- `0x18000cb24`
- `0x18000d81c`
- `0x180010354`
- `0x180010f34`
- `0x180011628`
- `0x180013da8`
- `0x180015400`
- `0x180016058`
- `0x180016424`
- `0x18001679c`
- `0x180016ce8`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015552`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015552`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180015542`
- `api-ms-win-core-file-l1-2-0!CreateFile2` at `0x180015542`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
_QWORD *__fastcall Pal::IOImplWin32Base::beginOpenFile(_QWORD *a1, _QWORD *a2, __int64 a3, unsigned int a4, int a5)
{
  _QWORD *v9; // rax
  unsigned int v10; // edi
  __int64 v11; // rbx
  DWORD LastError; // eax
  unsigned int *v13; // rax
  _QWORD *v14; // rax
  _DWORD *v15; // rdi
  _QWORD *v16; // rax
  _BYTE v18[8]; // [rsp+30h] [rbp-81h] BYREF
  __int128 v19; // [rsp+38h] [rbp-79h] BYREF
  int v20; // [rsp+50h] [rbp-61h]
  int v21; // [rsp+54h] [rbp-5Dh]
  __int64 v22; // [rsp+58h] [rbp-59h]
  __int128 v23; // [rsp+60h] [rbp-51h]
  _DWORD *v24; // [rsp+70h] [rbp-41h] BYREF
  std::_Ref_count_base *v25; // [rsp+78h] [rbp-39h]
  _BYTE v26[32]; // [rsp+90h] [rbp-21h] BYREF
  _BYTE v27[32]; // [rsp+B0h] [rbp-1h] BYREF

  *(_QWORD *)&v19 = a2;
  if ( a4 != 4 || a1[19] )
  {
    Pal::IOImplWindows::composeFullFileName((__int64)a1, (__int64)v27, a3, a4);
    if ( a5 == 1 )
    {
      std::wstring::wstring((__int64)v26);
      std::wstring::wstring((__int64)&v24);
      (*(void (__fastcall **)(_QWORD *, __int64, _BYTE *, _DWORD **))(*a1 + 88LL))(a1, a3, v26, &v24);
      (*(void (__fastcall **)(_QWORD *, _BYTE *, _QWORD))(*a1 + 40LL))(a1, v26, a4);
      std::wstring::_Tidy_deallocate(&v24);
      std::wstring::_Tidy_deallocate(v26);
      v10 = -1073741824;
    }
    else
    {
      v10 = 0x80000000;
    }
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v27);
    CallingStateTracker::CallingStateTracker(v18);
    v20 = 32;
    v21 = 128;
    v22 = 0x40000000;
    v23 = 0;
    *(_QWORD *)&v19 = CreateFile2(v11, v10, 1);
    if ( (_QWORD)v19 == -1 )
    {
      LastError = GetLastError();
      v13 = (unsigned int *)PalWindows::errorCodeFromWin32Error(&v19, LastError);
      v14 = (_QWORD *)Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(&v24, *v13);
      std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, v14);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v24);
    }
    else
    {
      v15 = operator new(0xA0u);
      v24 = v15;
      *(_OWORD *)v15 = 0;
      v15[2] = 1;
      v15[3] = 1;
      *(_QWORD *)v15 = &std::_Ref_count_obj2<Pal::AsyncOperation<unsigned __int64>>::`vftable';
      std::_Construct_in_place<Pal::RandomAccessStreamWin32,void * &>(
        (Pal::RandomAccessStreamWin32 *)(v15 + 4),
        (void **)&v19);
      v24 = v15 + 4;
      v25 = (std::_Ref_count_base *)v15;
      v19 = 0;
      v16 = (_QWORD *)Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createSucceeded(v26, &v24);
      std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, v16);
      Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(v26);
      if ( v25 )
        std::_Ref_count_base::_Decref(v25);
    }
    CallingStateTracker::~CallingStateTracker((CallingStateTracker *)v18);
    std::wstring::_Tidy_deallocate(v27);
  }
  else
  {
    v9 = (_QWORD *)Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(&v24, 8388610);
    std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(a2, v9);
    Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(&v24);
  }
  return a2;
}

```

## disassembly

```asm
0x180015400  push    rbp
0x180015402  push    rbx
0x180015403  push    rsi
0x180015404  push    rdi
0x180015405  push    r14
0x180015407  lea     rbp, [rsp-2Fh]
0x18001540c  sub     rsp, 0E0h
0x180015413  mov     rax, cs:__security_cookie
0x18001541a  xor     rax, rsp
0x18001541d  mov     [rbp+4Fh+var_30], rax
0x180015421  mov     edi, r9d
0x180015424  mov     r14, r8
0x180015427  mov     rsi, rdx
0x18001542a  mov     rbx, rcx
0x18001542d  mov     qword ptr [rbp+4Fh+var_C8], rdx
0x180015431  cmp     r9d, 4
0x180015435  jnz     short loc_180015469
0x180015437  cmp     qword ptr [rcx+98h], 0
0x18001543f  jnz     short loc_180015469
0x180015441  mov     edx, cs:dword_180048AD8
0x180015447  lea     rcx, [rbp+4Fh+var_90]
0x18001544b  call    ?createFailed@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(Core::StatusCode)
0x180015450  mov     rdx, rax
0x180015453  mov     rcx, rsi
0x180015456  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x18001545b  lea     rcx, [rbp+4Fh+var_90]
0x18001545f  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015464  jmp     loc_18001561C
0x180015469  lea     rdx, [rbp+4Fh+var_50]
0x18001546d  call    ?composeFullFileName@IOImplWindows@Pal@@IEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@W4FileLocation@2@@Z; Pal::IOImplWindows::composeFullFileName(std::wstring const &,Pal::FileLocation)
0x180015472  nop
0x180015473  mov     ecx, [rbp+4Fh+arg_20]
0x180015476  cmp     ecx, 1
0x180015479  jnz     short loc_1800154D5
0x18001547b  lea     rcx, [rbp+4Fh+var_70]
0x18001547f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180015484  nop
0x180015485  lea     rcx, [rbp+4Fh+var_90]
0x180015489  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001548e  nop
0x18001548f  mov     rax, [rbx]
0x180015492  lea     r9, [rbp+4Fh+var_90]
0x180015496  lea     r8, [rbp+4Fh+var_70]
0x18001549a  mov     rdx, r14
0x18001549d  mov     rcx, rbx
0x1800154a0  mov     rax, [rax+58h]
0x1800154a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a9  mov     rax, [rbx]
0x1800154ac  mov     r8d, edi
0x1800154af  lea     rdx, [rbp+4Fh+var_70]
0x1800154b3  mov     rcx, rbx
0x1800154b6  mov     rax, [rax+28h]
0x1800154ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154bf  nop
0x1800154c0  lea     rcx, [rbp+4Fh+var_90]
0x1800154c4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800154c9  nop
0x1800154ca  lea     rcx, [rbp+4Fh+var_70]
0x1800154ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800154d3  jmp     short loc_1800154DE
0x1800154d5  test    ecx, ecx
0x1800154d7  jz      short loc_1800154EB
0x1800154d9  cmp     ecx, 1
0x1800154dc  jnz     short loc_1800154EB
0x1800154de  mov     edi, 0C0000000h
0x1800154e3  mov     r14d, 2
0x1800154e9  jmp     short loc_1800154F6
0x1800154eb  mov     r14d, 3
0x1800154f1  mov     edi, 80000000h
0x1800154f6  lea     rcx, [rbp+4Fh+var_50]
0x1800154fa  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800154ff  mov     rbx, rax
0x180015502  lea     rcx, [rsp+100h+var_D0]
0x180015507  call    ??0CallingStateTracker@@QEAA@W4CallingState@@@Z; CallingStateTracker::CallingStateTracker(CallingState)
0x18001550c  nop
0x18001550d  mov     [rbp+4Fh+var_B0], 20h ; ' '
0x180015514  mov     [rbp+4Fh+var_AC], 80h
0x18001551b  mov     [rbp+4Fh+var_A8], 40000000h
0x180015523  xorps   xmm0, xmm0
0x180015526  movdqu  [rbp+4Fh+var_A0], xmm0
0x18001552b  lea     rax, [rbp+4Fh+var_B0]
0x18001552f  mov     [rsp+100h+var_E0], rax
0x180015534  mov     r9d, r14d
0x180015537  mov     r8d, 1
0x18001553d  mov     edx, edi
0x18001553f  mov     rcx, rbx
0x180015542  call    cs:__imp_CreateFile2
0x180015548  mov     qword ptr [rbp+4Fh+var_C8], rax
0x18001554c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015550  jnz     short loc_180015587
0x180015552  call    cs:__imp_GetLastError
0x180015558  mov     edx, eax
0x18001555a  lea     rcx, [rbp+4Fh+var_C8]
0x18001555e  call    ?errorCodeFromWin32Error@PalWindows@@YA?AVStatusCode@Core@@K@Z; PalWindows::errorCodeFromWin32Error(ulong)
0x180015563  mov     edx, [rax]
0x180015565  lea     rcx, [rbp+4Fh+var_90]
0x180015569  call    ?createFailed@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@VStatusCode@4@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createFailed(Core::StatusCode)
0x18001556e  mov     rdx, rax
0x180015571  mov     rcx, rsi
0x180015574  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x180015579  lea     rcx, [rbp+4Fh+var_90]
0x18001557d  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x180015582  jmp     loc_180015608
0x180015587  mov     ecx, 0A0h; Size
0x18001558c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015591  mov     rdi, rax
0x180015594  mov     [rbp+4Fh+var_90], rax
0x180015598  xorps   xmm0, xmm0
0x18001559b  movups  xmmword ptr [rax], xmm0
0x18001559e  mov     dword ptr [rax+8], 1
0x1800155a5  mov     dword ptr [rax+0Ch], 1
0x1800155ac  lea     rax, ??_7?$_Ref_count_obj2@V?$AsyncOperation@_K@Pal@@@std@@6B@; const std::_Ref_count_obj2<Pal::AsyncOperation<unsigned __int64>>::`vftable'
0x1800155b3  mov     [rdi], rax
0x1800155b6  lea     rbx, [rdi+10h]
0x1800155ba  lea     rdx, [rbp+4Fh+var_C8]
0x1800155be  mov     rcx, rbx
0x1800155c1  call    ??$_Construct_in_place@VRandomAccessStreamWin32@Pal@@AEAPEAX@std@@YAXAEAVRandomAccessStreamWin32@Pal@@AEAPEAX@Z; std::_Construct_in_place<Pal::RandomAccessStreamWin32,void * &>(Pal::RandomAccessStreamWin32 &,void * &)
0x1800155c6  nop
0x1800155c7  mov     [rbp+4Fh+var_90], rbx
0x1800155cb  mov     [rbp+4Fh+var_88], rdi
0x1800155cf  xorps   xmm0, xmm0
0x1800155d2  movdqu  [rbp+4Fh+var_C8], xmm0
0x1800155d7  lea     rdx, [rbp+4Fh+var_90]
0x1800155db  lea     rcx, [rbp+4Fh+var_70]
0x1800155df  call    ?createSucceeded@?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@SA?AV?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@$$QEBV?$shared_ptr@VStream@Pal@@@std@@@Z; Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>::createSucceeded(std::shared_ptr<Pal::Stream> const &&)
0x1800155e4  mov     rdx, rax
0x1800155e7  mov     rcx, rsi
0x1800155ea  call    ??0?$shared_ptr@VWrlTimerWrapper@Detail@Pal@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Pal::Detail::WrlTimerWrapper>::shared_ptr<Pal::Detail::WrlTimerWrapper>(std::shared_ptr<Pal::Detail::WrlTimerWrapper> const &)
0x1800155ef  lea     rcx, [rbp+4Fh+var_70]
0x1800155f3  call    ??1?$PresentSharedPtr@V?$AsyncOperation@V?$shared_ptr@VStream@Pal@@@std@@@Pal@@@Core@@QEAA@XZ; Core::PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>::~PresentSharedPtr<Pal::AsyncOperation<std::shared_ptr<Pal::Stream>>>(void)
0x1800155f8  nop
0x1800155f9  mov     rcx, [rbp+4Fh+var_88]; this
0x1800155fd  test    rcx, rcx
0x180015600  jz      short loc_180015608
0x180015602  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x180015607  nop
0x180015608  lea     rcx, [rsp+100h+var_D0]; this
0x18001560d  call    ??1CallingStateTracker@@QEAA@XZ; CallingStateTracker::~CallingStateTracker(void)
0x180015612  nop
0x180015613  lea     rcx, [rbp+4Fh+var_50]
0x180015617  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001561c  mov     rax, rsi
0x18001561f  mov     rcx, [rbp+4Fh+var_30]
0x180015623  xor     rcx, rsp; StackCookie
0x180015626  call    __security_check_cookie
0x18001562b  add     rsp, 0E0h
0x180015632  pop     r14
0x180015634  pop     rdi
0x180015635  pop     rsi
0x180015636  pop     rbx
0x180015637  pop     rbp
0x180015638  retn
```
