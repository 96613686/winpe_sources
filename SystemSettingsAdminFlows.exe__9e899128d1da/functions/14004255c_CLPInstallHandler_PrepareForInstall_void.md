# CLPInstallHandler::PrepareForInstall(void)

- ea: `0x14004255c`
- end: `0x1400428aa`
- name: `?PrepareForInstall@CLPInstallHandler@@QEAAJXZ`
- size: `846`
- prototype: `__int64 __fastcall(CLPInstallHandler *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140040c30`

## callees

- `0x140005f30`
- `0x140005f60`
- `0x140005fdc`
- `0x14000d850`
- `0x14000e624`
- `0x14002a3e8`
- `0x1400337b0`
- `0x14003aed0`
- `0x14003d630`
- `0x14003e03c`
- `0x14003e8f4`
- `0x14003f000`
- `0x140041054`
- `0x140041300`
- `0x1400414e8`
- `0x14004255c`
- `0x140068760`
- `0x14007d010`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x14004265f`
- `KERNEL32!EnterCriticalSection` at `0x14004265f`
- `KERNEL32!CreateEventW` at `0x1400426ee`
- `KERNEL32!CreateEventW` at `0x1400426ee`
- `KERNEL32!TlsGetValue` at `0x14004258e`
- `KERNEL32!TlsGetValue` at `0x14004258e`
- `KERNEL32!TlsSetValue` at `0x1400425c6`
- `KERNEL32!TlsSetValue` at `0x1400425c6`
- `KERNEL32!InitializeSRWLock` at `0x140042769`
- `KERNEL32!InitializeSRWLock` at `0x14004278c`
- `KERNEL32!InitializeSRWLock` at `0x140042769`
- `KERNEL32!InitializeSRWLock` at `0x14004278c`

## string_xrefs

- `0x140042673`: `Settings Language Pack Installer`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLPInstallHandler::PrepareForInstall(CLPInstallHandler *this)
{
  CLPInstallHandler *v1; // r14
  RTL_SRWLOCK *Value; // rax
  RTL_SRWLOCK *p_TlsValue; // rsi
  char v4; // r13
  PVOID *v5; // rcx
  unsigned int v6; // edx
  __int64 v7; // rdx
  int Error; // r15d
  struct IUnknown **v9; // rax
  HANDLE EventW; // r15
  CLPInstallHandler *v11; // rax
  RTL_SRWLOCK *v12; // rbx
  _QWORD *v13; // rcx
  RTL_SRWLOCK *v14; // rax
  std::_Ref_count_base *v15; // rcx
  unsigned int v16; // edx
  __int64 v17; // r12
  RTL_SRWLOCK *v19; // [rsp+30h] [rbp-A8h] BYREF
  __int64 v20; // [rsp+38h] [rbp-A0h] BYREF
  __int64 v21; // [rsp+40h] [rbp-98h] BYREF
  CLPInstallHandler *v22; // [rsp+48h] [rbp-90h]
  __int64 TlsValue; // [rsp+50h] [rbp-88h] BYREF
  RTL_SRWLOCK *v24; // [rsp+58h] [rbp-80h]
  char *v25; // [rsp+60h] [rbp-78h] BYREF
  long *v26; // [rsp+68h] [rbp-70h] BYREF
  ATL::CAtlException *v27; // [rsp+70h] [rbp-68h] BYREF
  _BYTE v28[32]; // [rsp+78h] [rbp-60h] BYREF

  v1 = this;
  v22 = this;
  Value = (RTL_SRWLOCK *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  LODWORD(v20) = -1;
  TlsValue = 0;
  if ( Value )
  {
    v19 = Value;
  }
  else
  {
    p_TlsValue = (RTL_SRWLOCK *)&TlsValue;
    v19 = (RTL_SRWLOCK *)&TlsValue;
    LODWORD(v20) = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
  }
  v24 = p_TlsValue;
  v4 = 1;
  ++LODWORD(p_TlsValue->Ptr);
  v5 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v6 = 5 * LODWORD(p_TlsValue->Ptr);
    if ( v6 > 0x1E1 )
      v7 = 0;
    else
      v7 = 479LL - v6;
    WPP_SF_sq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v7],
      (char)v1);
    v5 = (PVOID *)WPP_GLOBAL_Control;
  }
  Error = 0;
  if ( !*(_BYTE *)v1 )
  {
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v1 + 8));
    v25 = (char *)v1 + 8;
    if ( *(_BYTE *)v1 )
    {
LABEL_37:
      Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)&v25);
      v5 = (PVOID *)WPP_GLOBAL_Control;
      goto LABEL_38;
    }
    try
    {
      std::wstring::wstring((__int64)v28, (__int64)L"Settings Language Pack Installer");
      v9 = (struct IUnknown **)WUUtil::CreateSession(&v21, v28);
      if ( *((struct IUnknown **)v1 + 6) != *v9 )
        ATL::AtlComPtrAssign((struct IUnknown **)v1 + 6, *v9);
      wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(&v21);
      std::wstring::_Tidy_deallocate(v28);
    }
    catch ( long *v26 )
    {
      LODWORD(v21) = *(_DWORD *)v26;
      goto LABEL_16;
    }
    catch ( ATL::CAtlException *v27 )
    {
      LODWORD(v21) = *(_DWORD *)v27;
LABEL_16:
      Error = v21;
      p_TlsValue = v19;
      v1 = v22;
      if ( (int)v21 < 0 )
        goto LABEL_35;
      v4 = 1;
    }
    EventW = CreateEventW(0, 1, 0, 0);
    if ( EventW != *((HANDLE *)v1 + 13) )
    {
      Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close((char *)v1 + 96);
      *((_QWORD *)v1 + 13) = EventW;
    }
    if ( *((_QWORD *)v1 + 13) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_35;
    }
    v11 = (CLPInstallHandler *)operator new(0x78u, (const struct std::nothrow_t *)std::nothrow);
    v12 = (RTL_SRWLOCK *)v11;
    v22 = v11;
    if ( v11 )
    {
      v13 = (_QWORD *)*((_QWORD *)v1 + 6);
      *(_QWORD *)v11 = v13;
      if ( v13 )
        (*(void (__fastcall **)(_QWORD *, _QWORD))(*v13 + 8LL))(v13, *v13);
      v12[1].Ptr = 0;
      InitializeSRWLock(v12 + 2);
      v12[3].Ptr = 0;
      v12[4].Ptr = 0;
      v12[12].Ptr = 0;
      InitializeSRWLock(v12 + 13);
      LODWORD(v12[14].Ptr) = 0;
    }
    else
    {
      v12 = 0;
    }
    v19 = v12;
    if ( v12 )
    {
      v14 = (RTL_SRWLOCK *)operator new(0x18u);
      v24 = v14;
      *(_OWORD *)&v14->Ptr = 0;
      LODWORD(v14[1].Ptr) = 1;
      HIDWORD(v14[1].Ptr) = 1;
      v14->Ptr = &std::_Ref_count_resource<CUpdateSearcher *,std::default_delete<CUpdateSearcher>>::`vftable';
      v14[2].Ptr = v12;
      v19 = 0;
    }
    else
    {
      v14 = 0;
      v12 = 0;
    }
    *((_QWORD *)v1 + 7) = v12;
    v15 = (std::_Ref_count_base *)*((_QWORD *)v1 + 8);
    *((_QWORD *)v1 + 8) = v14;
    if ( v15 )
      std::_Ref_count_base::_Decref(v15);
    std::unique_ptr<CUpdateSearcher>::~unique_ptr<CUpdateSearcher>(&v19);
    if ( *((_QWORD *)v1 + 7) )
      goto LABEL_36;
    Error = -2147024882;
LABEL_35:
    v4 = 0;
LABEL_36:
    *(_BYTE *)v1 = v4;
    goto LABEL_37;
  }
LABEL_38:
  if ( v5 != &WPP_GLOBAL_Control && *((char *)v5 + 28) < 0 )
  {
    v16 = 5 * LODWORD(p_TlsValue->Ptr);
    if ( v16 > 0x1E1 )
      v17 = 0;
    else
      v17 = 479LL - v16;
    WPP_SF_sqd(
      (unsigned int)v5[2],
      11,
      (unsigned int)WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids,
      (unsigned int)&asc_14008A110[v17],
      (char)v1,
      Error,
      v19,
      v20);
  }
  --LODWORD(p_TlsValue->Ptr);
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>((DWORD *)&v20);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x14004255c  push    rbx
0x14004255e  push    rsi
0x14004255f  push    r12
0x140042561  push    r13
0x140042563  push    r14
0x140042565  push    r15
0x140042567  sub     rsp, 0A8h
0x14004256e  mov     rax, cs:__security_cookie
0x140042575  xor     rax, rsp
0x140042578  mov     [rsp+0D8h+var_40], rax
0x140042580  mov     r14, rcx
0x140042583  mov     [rsp+0D8h+var_90], rcx
0x140042588  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x14004258e  call    cs:__imp_TlsGetValue
0x140042594  mov     rsi, rax
0x140042597  mov     dword ptr [rsp+0D8h+var_A0], 0FFFFFFFFh
0x14004259f  mov     [rsp+0D8h+TlsValue], 0
0x1400425a8  test    rax, rax
0x1400425ab  jnz     short loc_1400425CE
0x1400425ad  lea     rsi, [rsp+0D8h+TlsValue]
0x1400425b2  mov     [rsp+0D8h+var_A8], rsi
0x1400425b7  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x1400425bd  mov     dword ptr [rsp+0D8h+var_A0], ecx
0x1400425c1  lea     rdx, [rsp+0D8h+TlsValue]; lpTlsValue
0x1400425c6  call    cs:__imp_TlsSetValue
0x1400425cc  jmp     short loc_1400425D3
0x1400425ce  mov     [rsp+0D8h+var_A8], rsi
0x1400425d3  mov     [rsp+0D8h+var_80], rsi
0x1400425d8  mov     r13d, 1
0x1400425de  add     [rsi], r13d
0x1400425e1  lea     rax, WPP_GLOBAL_Control
0x1400425e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400425ef  cmp     rcx, rax
0x1400425f2  jz      short loc_140042646
0x1400425f4  test    byte ptr [rcx+1Ch], 80h
0x1400425f8  jz      short loc_140042646
0x1400425fa  mov     eax, [rsi]
0x1400425fc  lea     edx, [rax+rax*4]
0x1400425ff  mov     r12d, 1DFh
0x140042605  cmp     edx, 1E1h
0x14004260b  ja      short loc_140042617
0x14004260d  mov     eax, edx
0x14004260f  mov     edx, r12d
0x140042612  sub     rdx, rax
0x140042615  jmp     short loc_140042619
0x140042617  xor     edx, edx
0x140042619  lea     r9, asc_14008A110; "                                       "...
0x140042620  add     r9, rdx
0x140042623  mov     edx, 0Ah
0x140042628  mov     [rsp+0D8h+var_B8], r14
0x14004262d  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x140042634  mov     rcx, [rcx+10h]
0x140042638  call    WPP_SF_sq
0x14004263d  mov     rcx, cs:WPP_GLOBAL_Control
0x140042644  jmp     short loc_14004264C
0x140042646  mov     r12d, 1DFh
0x14004264c  xor     r15d, r15d
0x14004264f  cmp     [r14], r15b
0x140042652  jnz     loc_140042826
0x140042658  lea     rbx, [r14+8]
0x14004265c  mov     rcx, rbx; lpCriticalSection
0x14004265f  call    cs:__imp_EnterCriticalSection
0x140042665  mov     [rsp+0D8h+var_78], rbx
0x14004266a  cmp     [r14], r15b
0x14004266d  jnz     loc_140042815
0x140042673  lea     rdx, aSettingsLangua; "Settings Language Pack Installer"
0x14004267a  lea     rcx, [rsp+0D8h+var_60]
0x14004267f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x140042684  nop
0x140042685  lea     rdx, [rsp+0D8h+var_60]
0x14004268a  lea     rcx, [rsp+0D8h+var_98]
0x14004268f  call    ?CreateSession@WUUtil@@YA?AV?$CComPtr@UIUpdateSession@@@ATL@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WUUtil::CreateSession(std::wstring const &)
0x140042694  lea     rcx, [r14+30h]; struct IUnknown **
0x140042698  mov     rdx, [rax]; struct IUnknown *
0x14004269b  cmp     [rcx], rdx
0x14004269e  jz      short loc_1400426A5
0x1400426a0  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x1400426a5  lea     rcx, [rsp+0D8h+var_98]
0x1400426aa  call    ??1?$com_ptr_t@UIPackageManagerInternal@Internal@Deployment@Management@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>::~com_ptr_t<Windows::Management::Deployment::Internal::IPackageManagerInternal,wil::err_exception_policy>(void)
0x1400426af  nop
0x1400426b0  lea     rcx, [rsp+0D8h+var_60]
0x1400426b5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400426ba  nop
0x1400426bb  jmp     short loc_1400426E3
0x1400426bd  jmp     short $+2
0x1400426bf  mov     r15d, dword ptr [rsp+0D8h+var_98]
0x1400426c4  mov     r12d, 1DFh
0x1400426ca  mov     rsi, [rsp+0D8h+var_A8]
0x1400426cf  mov     r14, [rsp+0D8h+var_90]
0x1400426d4  test    r15d, r15d
0x1400426d7  js      loc_14004280F
0x1400426dd  mov     r13d, 1
0x1400426e3  xor     r9d, r9d; lpName
0x1400426e6  xor     r8d, r8d; bInitialState
0x1400426e9  mov     edx, r13d; bManualReset
0x1400426ec  xor     ecx, ecx; lpEventAttributes
0x1400426ee  call    cs:__imp_CreateEventW
0x1400426f4  mov     r15, rax
0x1400426f7  cmp     rax, [r14+68h]
0x1400426fb  jz      short loc_14004270A
0x1400426fd  lea     rcx, [r14+60h]
0x140042701  call    ?Close@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Close(void)
0x140042706  mov     [r14+68h], r15
0x14004270a  cmp     qword ptr [r14+68h], 0
0x14004270f  jz      short loc_140042716
0x140042711  xor     r15d, r15d
0x140042714  jmp     short loc_140042726
0x140042716  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x14004271b  mov     r15d, eax
0x14004271e  test    eax, eax
0x140042720  js      loc_14004280F
0x140042726  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14004272d  mov     ecx, 78h ; 'x'; unsigned __int64
0x140042732  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140042737  mov     rbx, rax
0x14004273a  mov     [rsp+0D8h+var_90], rax
0x14004273f  test    rax, rax
0x140042742  jz      short loc_14004279B
0x140042744  mov     rcx, [r14+30h]
0x140042748  mov     [rax], rcx
0x14004274b  test    rcx, rcx
0x14004274e  jz      short loc_14004275D
0x140042750  mov     rdx, [rcx]
0x140042753  mov     rax, [rdx+8]
0x140042757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004275c  nop
0x14004275d  mov     qword ptr [rbx+8], 0
0x140042765  lea     rcx, [rbx+10h]; SRWLock
0x140042769  call    cs:__imp_InitializeSRWLock
0x14004276f  nop
0x140042770  mov     qword ptr [rbx+18h], 0
0x140042778  mov     qword ptr [rbx+20h], 0
0x140042780  mov     qword ptr [rbx+60h], 0
0x140042788  lea     rcx, [rbx+68h]; SRWLock
0x14004278c  call    cs:__imp_InitializeSRWLock
0x140042792  mov     dword ptr [rbx+70h], 0
0x140042799  jmp     short loc_14004279D
0x14004279b  xor     ebx, ebx
0x14004279d  mov     [rsp+0D8h+var_A8], rbx
0x1400427a2  test    rbx, rbx
0x1400427a5  jz      short loc_1400427DD
0x1400427a7  mov     ecx, 18h; Size
0x1400427ac  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400427b1  mov     [rsp+0D8h+var_80], rax
0x1400427b6  xorps   xmm0, xmm0
0x1400427b9  movups  xmmword ptr [rax], xmm0
0x1400427bc  mov     [rax+8], r13d
0x1400427c0  mov     [rax+0Ch], r13d
0x1400427c4  lea     rcx, ??_7?$_Ref_count_resource@PEAVCUpdateSearcher@@U?$default_delete@VCUpdateSearcher@@@std@@@std@@6B@; const std::_Ref_count_resource<CUpdateSearcher *,std::default_delete<CUpdateSearcher>>::`vftable'
0x1400427cb  mov     [rax], rcx
0x1400427ce  mov     [rax+10h], rbx
0x1400427d2  mov     [rsp+0D8h+var_A8], 0
0x1400427db  jmp     short loc_1400427E1
0x1400427dd  xor     eax, eax
0x1400427df  xor     ebx, ebx
0x1400427e1  mov     [r14+38h], rbx
0x1400427e5  mov     rcx, [r14+40h]; this
0x1400427e9  mov     [r14+40h], rax
0x1400427ed  test    rcx, rcx
0x1400427f0  jz      short loc_1400427F8
0x1400427f2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1400427f7  nop
0x1400427f8  lea     rcx, [rsp+0D8h+var_A8]
0x1400427fd  call    ??1?$unique_ptr@VCUpdateSearcher@@U?$default_delete@VCUpdateSearcher@@@std@@@std@@QEAA@XZ; std::unique_ptr<CUpdateSearcher>::~unique_ptr<CUpdateSearcher>(void)
0x140042802  cmp     qword ptr [r14+38h], 0
0x140042807  jnz     short loc_140042812
0x140042809  mov     r15d, 8007000Eh
0x14004280f  xor     r13b, r13b
0x140042812  mov     [r14], r13b
0x140042815  lea     rcx, [rsp+0D8h+var_78]; this
0x14004281a  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x14004281f  mov     rcx, cs:WPP_GLOBAL_Control
0x140042826  lea     rax, WPP_GLOBAL_Control
0x14004282d  cmp     rcx, rax
0x140042830  jz      short loc_140042879
0x140042832  test    byte ptr [rcx+1Ch], 80h
0x140042836  jz      short loc_140042879
0x140042838  mov     eax, [rsi]
0x14004283a  lea     edx, [rax+rax*4]
0x14004283d  cmp     edx, 1E1h
0x140042843  ja      short loc_14004284C
0x140042845  mov     eax, edx
0x140042847  sub     r12, rax
0x14004284a  jmp     short loc_14004284F
0x14004284c  xor     r12d, r12d
0x14004284f  lea     r9, asc_14008A110; "                                       "...
0x140042856  add     r9, r12
0x140042859  mov     edx, 0Bh
0x14004285e  mov     [rsp+0D8h+var_B0], r15d
0x140042863  mov     [rsp+0D8h+var_B8], r14
0x140042868  lea     r8, WPP_8576bded7d1f387ce8b248c32f4115b5_Traceguids
0x14004286f  mov     rcx, [rcx+10h]
0x140042873  call    WPP_SF_sqd
0x140042878  nop
0x140042879  dec     dword ptr [rsi]
0x14004287b  lea     rcx, [rsp+0D8h+var_A0]
0x140042880  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x140042885  mov     eax, r15d
0x140042888  mov     rcx, [rsp+0D8h+var_40]
0x140042890  xor     rcx, rsp; StackCookie
0x140042893  call    __security_check_cookie
0x140042898  add     rsp, 0A8h
0x14004289f  pop     r15
0x1400428a1  pop     r14
0x1400428a3  pop     r13
0x1400428a5  pop     r12
0x1400428a7  pop     rsi
0x1400428a8  pop     rbx
0x1400428a9  retn
```
