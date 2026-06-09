# KSMidiDevice::OpenStream(void)

- ea: `0x180029038`
- end: `0x180029823`
- name: `?OpenStream@KSMidiDevice@@IEAAJXZ`
- size: `2027`
- prototype: `__int64 __fastcall(KSMidiDevice *__hidden this)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180028020`
- `0x18002a310`

## callees

- `0x180004410`
- `0x180004434`
- `0x180004bf0`
- `0x180005260`
- `0x18000a814`
- `0x18000bb04`
- `0x18000f684`
- `0x180010f30`
- `0x180011400`
- `0x180025cfc`
- `0x180026760`
- `0x1800267e4`
- `0x1800270a8`
- `0x180027910`
- `0x180027b0c`
- `0x180027cb8`
- `0x180027ddc`
- `0x180027f00`
- `0x180029038`
- `0x18002982c`
- `0x180029918`
- `0x18002a3c0`
- `0x18003c59c`
- `0x18003cb40`
- `0x18003dd1c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029217`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800292ab`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180029217`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800292ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800291ca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800291ca`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002955d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002955d`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800295d4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x1800295d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800294b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029590`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800294b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180029590`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002949f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002956f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002949f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002956f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002945b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180029404`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002945b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294aa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295a4`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800294c6`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x1800294c6`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002942b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002942b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002925a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002957b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800290d4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002925a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029324`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002957b`

## pseudocode

```c
__int64 __fastcall KSMidiDevice::OpenStream(KSMidiDevice *this)
{
  _DWORD *v2; // r15
  char *Handle; // rbx
  CMidiXProc *v4; // rcx
  CMidiXProc *v5; // rbx
  __int64 *v6; // rax
  __int64 v7; // rdx
  KsHandleWrapper *v8; // rsi
  void *v9; // rsi
  RTL_SRWLOCK *v10; // rsi
  HRESULT v11; // r14d
  __int64 v12; // rdx
  _QWORD *v13; // rdx
  __int64 v14; // rdx
  CMidiXProc *v15; // rcx
  CMidiXProc *v16; // rbx
  _QWORD *v18; // rdx
  char *v19; // rax
  char *v20; // rcx
  MEMORY_MAPPED_PIPE *v21; // rbx
  __int64 v22; // rcx
  __int64 v23; // rdx
  CMidiXProc *v24; // rcx
  void *v25; // r14
  DWORD LastError; // ebx
  __int64 v27; // r8
  _WORD **v28; // rcx
  _WORD *v29; // rbx
  __int64 v30; // rbx
  const WCHAR *v31; // r9
  HANDLE EventW; // r12
  void *v33; // r14
  DWORD v34; // r15d
  unsigned int v35; // r8d
  const char *v36; // r9
  char *v37; // rax
  char *v38; // rbx
  CMidiXProc *v39; // r14
  CMidiXProc *v40; // rcx
  __int64 v41; // rdx
  void *v42; // rcx
  int v43; // eax
  void *v44; // rbx
  void *v45; // rbx
  int v46; // [rsp+20h] [rbp-E0h]
  int v47; // [rsp+20h] [rbp-E0h]
  LPVOID pv; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v50; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v51[7]; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD *v52; // [rsp+90h] [rbp-70h]
  KSMidiDevice *v53; // [rsp+98h] [rbp-68h]
  char v54; // [rsp+A0h] [rbp-60h]
  _QWORD v55[8]; // [rsp+A8h] [rbp-58h] BYREF
  GUID pguid; // [rsp+E8h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
    return 0;
  v53 = this;
  v54 = 1;
  if ( !*((_QWORD *)this + 7) )
  {
    Handle = (char *)KsHandleWrapper::GetHandle(*((PSRWLOCK *)this + 6));
    *(_QWORD *)&pguid.Data1 = Handle;
    if ( ((unsigned __int64)(Handle + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x101,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)0x8007000ELL,
        v46);
      if ( (unsigned __int64)(Handle - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        CloseHandle(Handle);
      v4 = (CMidiXProc *)*((_QWORD *)this + 11);
      if ( !v4 )
        return 2147942414LL;
      CMidiXProc::Shutdown(v4);
      v5 = (CMidiXProc *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = 0;
      if ( !v5 )
        return 2147942414LL;
      CMidiXProc::~CMidiXProc(v5);
      goto LABEL_81;
    }
    pv = Handle;
    v50 = *((_QWORD *)this + 8);
    v2 = (_DWORD *)((char *)this + 76);
    v6 = (__int64 *)std::make_unique<KsHandleWrapper,unsigned short *,unsigned int &,enum _MidiTransport &,void *,0>(
                      (unsigned int)&Block,
                      (unsigned int)&v50,
                      (int)this + 72,
                      (int)this + 76,
                      (__int64)&pv);
    v7 = *v6;
    *v6 = 0;
    v8 = (KsHandleWrapper *)*((_QWORD *)this + 7);
    *((_QWORD *)this + 7) = v7;
    if ( v8 )
    {
      KsHandleWrapper::~KsHandleWrapper(v8);
      operator delete(v8);
    }
    v9 = Block;
    if ( Block )
    {
      KsHandleWrapper::~KsHandleWrapper((KsHandleWrapper *)Block);
      operator delete(v9);
    }
    v10 = (RTL_SRWLOCK *)*((_QWORD *)this + 7);
    v51[0] = off_180042880;
    v51[1] = this;
    v52 = v51;
    Block = v51;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl'::`2'::impl) )
    {
      AcquireSRWLockExclusive(v10);
      if ( !v52 )
      {
        v11 = -2147024809;
        v12 = 73;
LABEL_19:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v12,
          (unsigned int)"avcore\\midi2\\inc\\KsHandleWrapper.h",
          (const char *)(unsigned int)v11,
          v46);
        if ( v10 )
          ReleaseSRWLockExclusive(v10);
        if ( v52 )
        {
          v13 = v51;
          LOBYTE(v13) = v52 != v51;
          (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v52 + 32LL))(v52, v13);
        }
        v14 = 266;
        goto LABEL_24;
      }
      if ( v10[15].Ptr )
      {
        v11 = -2147023649;
        v12 = 74;
        goto LABEL_19;
      }
      std::function<void (void)>::operator=(&v10[8], v51);
      if ( v10 )
        ReleaseSRWLockExclusive(v10);
    }
    if ( v52 )
    {
      v18 = v51;
      LOBYTE(v18) = v52 != v51;
      (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v52 + 32LL))(v52, v18);
    }
    v55[0] = off_180042850;
    v55[1] = this;
    v55[7] = v55;
    v11 = KsHandleWrapper::RegisterOnRestoreCallback(*((PSRWLOCK *)this + 7));
    if ( v11 >= 0 )
    {
      v11 = KsHandleWrapper::Open(*((KsHandleWrapper **)this + 7));
      if ( v11 >= 0 )
      {
        CloseHandle(Handle);
        goto LABEL_37;
      }
      v14 = 272;
    }
    else
    {
      v14 = 270;
    }
LABEL_24:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
      (const char *)(unsigned int)v11,
      v46);
    CloseHandle(Handle);
    v15 = (CMidiXProc *)*((_QWORD *)this + 11);
    if ( !v15 )
      return (unsigned int)v11;
    CMidiXProc::Shutdown(v15);
    v16 = (CMidiXProc *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = 0;
    if ( !v16 )
      return (unsigned int)v11;
LABEL_26:
    CMidiXProc::~CMidiXProc(v16);
    operator delete(v16);
    return (unsigned int)v11;
  }
  v2 = (_DWORD *)((char *)this + 76);
LABEL_37:
  if ( ((*v2 - 2) & 0xFFFFFFFD) != 0 )
  {
    *((_DWORD *)this + 10) = 0;
  }
  else
  {
    if ( !*((_QWORD *)this + 10) )
    {
      pguid = 0;
      pv = 0;
      v19 = (char *)operator new(0x68u, (const struct std::nothrow_t *)std::nothrow);
      v20 = v19;
      if ( v19 )
      {
        *(_QWORD *)v19 = 0;
        *((_QWORD *)v19 + 1) = 0;
        *((_QWORD *)v19 + 2) = 0;
        *((_QWORD *)v19 + 3) = 0;
        *((_DWORD *)v19 + 8) = 0;
        *((_QWORD *)v19 + 5) = 0;
        *((_QWORD *)v19 + 6) = 0;
        *((_QWORD *)v19 + 7) = 0;
        *((_QWORD *)v19 + 8) = 0;
        *(_OWORD *)(v19 + 72) = 0;
        *((_QWORD *)v19 + 11) = 0;
        *((_QWORD *)v19 + 12) = 7;
        *((_WORD *)v19 + 36) = 0;
      }
      else
      {
        v20 = 0;
      }
      v21 = (MEMORY_MAPPED_PIPE *)*((_QWORD *)this + 10);
      *((_QWORD *)this + 10) = v20;
      if ( v21 )
      {
        MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(v21);
        operator delete(v21);
      }
      v22 = *((_QWORD *)this + 10);
      if ( !v22 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x11F,
          (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
          (const char *)0x8007000ELL,
          v46);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_78;
      }
      *(_DWORD *)(v22 + 4) = *((_DWORD *)this + 11);
      **((_DWORD **)this + 10) = (*v2 != 2) + 1;
      v11 = CoCreateGuid(&pguid);
      if ( v11 < 0 )
      {
        v23 = 293;
        goto LABEL_49;
      }
      v25 = pv;
      if ( pv )
      {
        LastError = GetLastError();
        CoTaskMemFree(v25);
        SetLastError(LastError);
      }
      pv = 0;
      v11 = StringFromCLSID(&pguid, (LPOLESTR *)&pv);
      if ( v11 < 0 )
      {
        v23 = 294;
LABEL_49:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v23,
          (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
          (const char *)(unsigned int)v11,
          v46);
        if ( pv )
          CoTaskMemFree(pv);
        goto LABEL_51;
      }
      _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(*((_QWORD *)this + 10) + 56LL);
      v28 = (_WORD **)(*((_QWORD *)this + 10) + 72LL);
      if ( *(_QWORD *)(*((_QWORD *)this + 10) + 96LL) < 7u )
      {
        ____Reallocate_for_V_lambda_1___1_____Assign_G___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV23_QEBG_K_Z_PEBG___basic_string_GU__char_traits_G_std__V__allocator_G_2__std__AEAAAEAV01__KV_lambda_1___1_____Assign_G_01_AEAAAEAV01_QEBG0_Z_PEBG_Z(
          v28,
          7,
          v27,
          L"Global\\");
      }
      else
      {
        if ( *(_QWORD *)(*((_QWORD *)this + 10) + 96LL) <= 7u )
          v29 = (_WORD *)(*((_QWORD *)this + 10) + 72LL);
        else
          v29 = *v28;
        *(_QWORD *)(*((_QWORD *)this + 10) + 88LL) = 7;
        memmove_0(v29, L"Global\\", 0xEu);
        v29[7] = 0;
      }
      std::wstring::operator+=((void *)(*((_QWORD *)this + 10) + 72LL), pv);
      v30 = *((_QWORD *)this + 10);
      v31 = (const WCHAR *)(v30 + 72);
      if ( *(_QWORD *)(v30 + 96) > 7u )
        v31 = *(const WCHAR **)v31;
      EventW = CreateEventW(0, 1, 0, v31);
      v33 = *(void **)(v30 + 64);
      if ( v33 )
      {
        v34 = GetLastError();
        if ( !CloseHandle(v33) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v35, v36);
        SetLastError(v34);
      }
      *(_QWORD *)(v30 + 64) = EventW;
      if ( pv )
        CoTaskMemFree(pv);
    }
    v37 = (char *)operator new(0x90u, (const struct std::nothrow_t *)std::nothrow);
    v38 = v37;
    *(_QWORD *)&pguid.Data1 = v37;
    if ( v37 )
    {
      *(_DWORD *)v37 = 1;
      InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v37 + 8), 0, 0);
      v38[48] = 0;
      *((_DWORD *)v38 + 13) = 0;
      *((_QWORD *)v38 + 7) = 0;
      *((_QWORD *)v38 + 8) = 0;
      *((_QWORD *)v38 + 9) = 0;
      *((_DWORD *)v38 + 20) = 0;
      *((_QWORD *)v38 + 11) = 0;
      *((_QWORD *)v38 + 12) = 0;
      *((_QWORD *)v38 + 13) = 0;
      *((_QWORD *)v38 + 14) = 0;
      *((_QWORD *)v38 + 15) = 0;
      *((_QWORD *)v38 + 16) = 0;
      *((_QWORD *)v38 + 17) = 0;
    }
    else
    {
      v38 = 0;
    }
    v39 = (CMidiXProc *)*((_QWORD *)this + 11);
    *((_QWORD *)this + 11) = v38;
    if ( v39 )
    {
      CMidiXProc::~CMidiXProc(v39);
      operator delete(v39);
    }
    if ( !*((_QWORD *)this + 11) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x132,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)0x8007000ELL,
        v46);
LABEL_78:
      v40 = (CMidiXProc *)*((_QWORD *)this + 11);
      if ( !v40 )
        return 2147942414LL;
      CMidiXProc::Shutdown(v40);
      v5 = (CMidiXProc *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = 0;
      if ( !v5 )
        return 2147942414LL;
      CMidiXProc::~CMidiXProc(v5);
LABEL_81:
      operator delete(v5);
      return 2147942414LL;
    }
    v11 = KSMidiDevice::ConfigureLoopedBuffer(this);
    if ( v11 < 0 )
    {
      v41 = 310;
LABEL_85:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v41,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v11,
        v46);
      goto LABEL_51;
    }
    v11 = KSMidiDevice::ConfigureLoopedRegisters(this);
    if ( v11 < 0 )
    {
      v41 = 311;
      goto LABEL_85;
    }
    v11 = KSMidiDevice::ConfigureLoopedEvent(this);
    if ( v11 < 0 )
    {
      v41 = 312;
      goto LABEL_85;
    }
  }
  v11 = KSMidiDevice::PinSetState(this, KSSTATE_ACQUIRE);
  if ( v11 < 0 )
  {
    v41 = 322;
    goto LABEL_85;
  }
  v11 = KSMidiDevice::PinSetState(this, KSSTATE_PAUSE);
  if ( v11 < 0 )
  {
    v41 = 323;
    goto LABEL_85;
  }
  v11 = KSMidiDevice::PinSetState(this, KSSTATE_RUN);
  if ( v11 < 0 )
  {
    v41 = 324;
    goto LABEL_85;
  }
  v42 = (void *)*((_QWORD *)this + 11);
  if ( v42 )
  {
    pv = 0;
    v43 = CMidiXProc::Initialize(v42, *((_QWORD *)this + 3), *((_QWORD *)this + 4));
    v11 = v43;
    if ( v43 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x14A,
        (unsigned int)"avcore\\midi2\\libs\\midiks\\midiks.cpp",
        (const char *)(unsigned int)v43,
        v47);
      v44 = pv;
      if ( pv )
      {
        MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)pv);
        operator delete(v44);
      }
LABEL_51:
      v24 = (CMidiXProc *)*((_QWORD *)this + 11);
      if ( !v24 )
        return (unsigned int)v11;
      CMidiXProc::Shutdown(v24);
      v16 = (CMidiXProc *)*((_QWORD *)this + 11);
      *((_QWORD *)this + 11) = 0;
      if ( !v16 )
        return (unsigned int)v11;
      goto LABEL_26;
    }
    v45 = pv;
    if ( pv )
    {
      MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE((MEMORY_MAPPED_PIPE *)pv);
      operator delete(v45);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180029038  push    rbp
0x18002903a  push    rbx
0x18002903b  push    rsi
0x18002903c  push    rdi
0x18002903d  push    r12
0x18002903f  push    r13
0x180029041  push    r14
0x180029043  push    r15
0x180029045  lea     rbp, [rsp-8]
0x18002904a  sub     rsp, 108h
0x180029051  mov     rax, cs:__security_cookie
0x180029058  xor     rax, rsp
0x18002905b  mov     [rbp+40h+var_48], rax
0x18002905f  mov     rdi, rcx
0x180029062  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180029069  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x18002906e  xor     r13d, r13d
0x180029071  test    al, al
0x180029073  jz      loc_1800297F6
0x180029079  mov     [rbp+40h+var_A8], rdi
0x18002907d  mov     [rbp+40h+var_A0], 1
0x180029081  cmp     [rdi+38h], r13
0x180029085  jz      short loc_180029090
0x180029087  lea     r15, [rdi+4Ch]
0x18002908b  jmp     loc_18002932A
0x180029090  mov     rcx, [rdi+30h]; SRWLock
0x180029094  call    ?GetHandle@KsHandleWrapper@@QEAAPEAXXZ; KsHandleWrapper::GetHandle(void)
0x180029099  mov     rbx, rax
0x18002909c  mov     qword ptr [rbp+40h+pguid.Data1], rax
0x1800290a0  inc     rax
0x1800290a3  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800290a9  jnz     short loc_180029110
0x1800290ab  mov     rcx, [rbp+48h]; this
0x1800290af  mov     r9d, 8007000Eh; char *
0x1800290b5  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800290bc  mov     edx, 101h; void *
0x1800290c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800290c6  nop
0x1800290c7  lea     rax, [rbx-1]
0x1800290cb  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800290cf  ja      short loc_1800290DB
0x1800290d1  mov     rcx, rbx; hObject
0x1800290d4  call    cs:__imp_CloseHandle
0x1800290da  nop
0x1800290db  mov     rcx, [rdi+58h]; this
0x1800290df  test    rcx, rcx
0x1800290e2  jz      loc_180029689
0x1800290e8  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x1800290ed  mov     rbx, [rdi+58h]
0x1800290f1  mov     [rdi+58h], r13
0x1800290f5  test    rbx, rbx
0x1800290f8  jz      loc_180029689
0x1800290fe  mov     rcx, rbx; this
0x180029101  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180029106  mov     edx, 90h
0x18002910b  jmp     loc_180029681
0x180029110  mov     [rsp+140h+pv], rbx
0x180029115  mov     rax, [rdi+40h]
0x180029119  mov     [rsp+140h+var_F0], rax
0x18002911e  lea     r15, [rdi+4Ch]
0x180029122  lea     r8, [rdi+48h]
0x180029126  lea     rax, [rsp+140h+pv]
0x18002912b  mov     [rsp+140h+var_120], rax; int
0x180029130  mov     r9, r15
0x180029133  lea     rdx, [rsp+140h+var_F0]
0x180029138  lea     rcx, [rsp+140h+Block]
0x18002913d  call    ??$make_unique@VKsHandleWrapper@@PEAGAEAIAEAW4_MidiTransport@@PEAX$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAGAEAIAEAW4_MidiTransport@@$$QEAPEAX@Z; std::make_unique<KsHandleWrapper,ushort *,uint &,_MidiTransport &,void *,0>(ushort * &&,uint &,_MidiTransport &,void * &&)
0x180029142  mov     rdx, [rax]
0x180029145  mov     [rax], r13
0x180029148  mov     rsi, [rdi+38h]
0x18002914c  mov     [rdi+38h], rdx
0x180029150  mov     r14d, 0D8h
0x180029156  test    rsi, rsi
0x180029159  jz      short loc_18002916E
0x18002915b  mov     rcx, rsi; this
0x18002915e  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180029163  mov     edx, r14d
0x180029166  mov     rcx, rsi; Block
0x180029169  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002916e  mov     rsi, [rsp+140h+Block]
0x180029173  test    rsi, rsi
0x180029176  jz      short loc_18002918B
0x180029178  mov     rcx, rsi; this
0x18002917b  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180029180  mov     rdx, r14
0x180029183  mov     rcx, rsi; Block
0x180029186  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002918b  mov     rsi, [rdi+38h]
0x18002918f  lea     rax, off_180042880
0x180029196  mov     [rsp+140h+var_E8], rax
0x18002919b  mov     [rsp+140h+var_E0], rdi
0x1800291a0  lea     rax, [rsp+140h+var_E8]
0x1800291a5  mov     [rbp+40h+var_B0], rax
0x1800291a9  lea     rax, [rsp+140h+var_E8]
0x1800291ae  mov     [rsp+140h+Block], rax
0x1800291b3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x1800291ba  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x1800291bf  test    al, al
0x1800291c1  jz      loc_1800292B2
0x1800291c7  mov     rcx, rsi; SRWLock
0x1800291ca  call    cs:__imp_AcquireSRWLockExclusive
0x1800291d0  cmp     [rbp+40h+var_B0], r13
0x1800291d4  jnz     short loc_1800291E3
0x1800291d6  mov     r14d, 80070057h
0x1800291dc  mov     edx, 49h ; 'I'
0x1800291e1  jmp     short loc_1800291FC
0x1800291e3  lea     rcx, [rsi+40h]
0x1800291e7  cmp     [rcx+38h], r13
0x1800291eb  jz      loc_180029299
0x1800291f1  mov     r14d, 800704DFh
0x1800291f7  mov     edx, 4Ah ; 'J'; void *
0x1800291fc  mov     r9d, r14d; char *
0x1800291ff  lea     r8, aAvcoreMidi2Inc_0; "avcore\\midi2\\inc\\KsHandleWrapper.h"
0x180029206  mov     rcx, [rbp+48h]; this
0x18002920a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002920f  test    rsi, rsi
0x180029212  jz      short loc_18002921E
0x180029214  mov     rcx, rsi; SRWLock
0x180029217  call    cs:__imp_ReleaseSRWLockExclusive
0x18002921d  nop
0x18002921e  mov     rcx, [rbp+40h+var_B0]
0x180029222  test    rcx, rcx
0x180029225  jz      short loc_18002923E
0x180029227  lea     rdx, [rsp+140h+var_E8]
0x18002922c  cmp     rcx, rdx
0x18002922f  mov     rax, [rcx]
0x180029232  setnz   dl
0x180029235  mov     rax, [rax+20h]
0x180029239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002923e  mov     edx, 10Ah; void *
0x180029243  mov     rcx, [rbp+48h]; this
0x180029247  mov     r9d, r14d; char *
0x18002924a  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029251  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029256  nop
0x180029257  mov     rcx, rbx; hObject
0x18002925a  call    cs:__imp_CloseHandle
0x180029260  nop
0x180029261  mov     rcx, [rdi+58h]; this
0x180029265  test    rcx, rcx
0x180029268  jz      short loc_180029291
0x18002926a  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x18002926f  mov     rbx, [rdi+58h]
0x180029273  mov     [rdi+58h], r13
0x180029277  test    rbx, rbx
0x18002927a  jz      short loc_180029291
0x18002927c  mov     rcx, rbx; this
0x18002927f  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180029284  mov     edx, 90h
0x180029289  mov     rcx, rbx; Block
0x18002928c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180029291  mov     eax, r14d
0x180029294  jmp     loc_1800297F8
0x180029299  lea     rdx, [rsp+140h+var_E8]
0x18002929e  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x1800292a3  test    rsi, rsi
0x1800292a6  jz      short loc_1800292B2
0x1800292a8  mov     rcx, rsi; SRWLock
0x1800292ab  call    cs:__imp_ReleaseSRWLockExclusive
0x1800292b1  nop
0x1800292b2  mov     rcx, [rbp+40h+var_B0]
0x1800292b6  test    rcx, rcx
0x1800292b9  jz      short loc_1800292D2
0x1800292bb  mov     rax, [rcx]
0x1800292be  lea     rdx, [rsp+140h+var_E8]
0x1800292c3  cmp     rcx, rdx
0x1800292c6  setnz   dl
0x1800292c9  mov     rax, [rax+20h]
0x1800292cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292d2  lea     rax, off_180042850
0x1800292d9  mov     [rbp+40h+var_98], rax
0x1800292dd  mov     [rbp+40h+var_90], rdi
0x1800292e1  lea     rax, [rbp+40h+var_98]
0x1800292e5  mov     [rbp+40h+var_60], rax
0x1800292e9  lea     rdx, [rbp+40h+var_98]
0x1800292ed  mov     rcx, [rdi+38h]; SRWLock
0x1800292f1  call    ?RegisterOnRestoreCallback@KsHandleWrapper@@QEAAJV?$function@$$A6AXXZ@std@@@Z; KsHandleWrapper::RegisterOnRestoreCallback(std::function<void (void)>)
0x1800292f6  mov     r14d, eax
0x1800292f9  test    eax, eax
0x1800292fb  jns     short loc_180029307
0x1800292fd  mov     edx, 10Eh
0x180029302  jmp     loc_180029243
0x180029307  mov     rcx, [rdi+38h]; this
0x18002930b  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180029310  mov     r14d, eax
0x180029313  test    eax, eax
0x180029315  jns     short loc_180029321
0x180029317  mov     edx, 110h
0x18002931c  jmp     loc_180029243
0x180029321  mov     rcx, rbx; hObject
0x180029324  call    cs:__imp_CloseHandle
0x18002932a  mov     eax, [r15]
0x18002932d  sub     eax, 2
0x180029330  mov     esi, 90h
0x180029335  test    eax, 0FFFFFFFDh
0x18002933a  jnz     loc_1800296EB
0x180029340  cmp     [rdi+50h], r13
0x180029344  jnz     loc_1800295AA
0x18002934a  xorps   xmm0, xmm0
0x18002934d  movups  xmmword ptr [rbp+40h+pguid.Data1], xmm0
0x180029351  mov     [rsp+140h+pv], r13
0x180029356  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18002935d  lea     ecx, [rsi-28h]; unsigned __int64
0x180029360  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180029365  mov     rcx, rax
0x180029368  mov     r12d, 7
0x18002936e  test    rax, rax
0x180029371  jz      short loc_1800293AC
0x180029373  mov     [rax], r13
0x180029376  mov     [rax+8], r13
0x18002937a  mov     [rax+10h], r13
0x18002937e  mov     [rax+18h], r13
0x180029382  mov     [rax+20h], r13d
0x180029386  mov     [rax+28h], r13
0x18002938a  mov     [rax+30h], r13
0x18002938e  mov     [rax+38h], r13
0x180029392  mov     [rax+40h], r13
0x180029396  xorps   xmm0, xmm0
0x180029399  movups  xmmword ptr [rax+48h], xmm0
0x18002939d  mov     [rax+58h], r13
0x1800293a1  mov     [rax+60h], r12
0x1800293a5  mov     [rax+48h], r13w
0x1800293aa  jmp     short loc_1800293AF
0x1800293ac  mov     rcx, r13
0x1800293af  mov     rbx, [rdi+50h]
0x1800293b3  mov     [rdi+50h], rcx
0x1800293b7  test    rbx, rbx
0x1800293ba  jz      short loc_1800293D1
0x1800293bc  mov     rcx, rbx; this
0x1800293bf  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x1800293c4  mov     edx, 68h ; 'h'
0x1800293c9  mov     rcx, rbx; Block
0x1800293cc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800293d1  mov     rcx, [rdi+50h]
0x1800293d5  test    rcx, rcx
0x1800293d8  jnz     short loc_18002940F
0x1800293da  mov     rcx, [rbp+48h]; this
0x1800293de  mov     r9d, 8007000Eh; char *
0x1800293e4  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x1800293eb  mov     edx, 11Fh; void *
0x1800293f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800293f5  nop
0x1800293f6  mov     rcx, [rsp+140h+pv]; pv
0x1800293fb  test    rcx, rcx
0x1800293fe  jz      loc_18002965B
0x180029404  call    cs:__imp_CoTaskMemFree
0x18002940a  jmp     loc_18002965B
0x18002940f  mov     eax, [rdi+2Ch]
0x180029412  mov     [rcx+4], eax
0x180029415  mov     ecx, r13d
0x180029418  cmp     dword ptr [r15], 2
0x18002941c  setnz   cl
0x18002941f  inc     ecx
0x180029421  mov     rax, [rdi+50h]
0x180029425  mov     [rax], ecx
0x180029427  lea     rcx, [rbp+40h+pguid]; pguid
0x18002942b  call    cs:__imp_CoCreateGuid
0x180029431  mov     r14d, eax
0x180029434  test    eax, eax
0x180029436  jns     short loc_180029495
0x180029438  mov     edx, 125h; void *
0x18002943d  mov     r9d, r14d; char *
0x180029440  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180029447  mov     rcx, [rbp+48h]; this
0x18002944b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029450  nop
0x180029451  mov     rcx, [rsp+140h+pv]; pv
0x180029456  test    rcx, rcx
0x180029459  jz      short loc_180029462
0x18002945b  call    cs:__imp_CoTaskMemFree
0x180029461  nop
0x180029462  mov     rcx, [rdi+58h]; this
0x180029466  test    rcx, rcx
0x180029469  jz      loc_180029291
0x18002946f  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180029474  mov     rbx, [rdi+58h]
0x180029478  mov     [rdi+58h], r13
0x18002947c  test    rbx, rbx
0x18002947f  jz      loc_180029291
0x180029485  mov     rcx, rbx; this
0x180029488  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x18002948d  mov     rdx, rsi
0x180029490  jmp     loc_180029289
0x180029495  mov     r14, [rsp+140h+pv]
0x18002949a  test    r14, r14
0x18002949d  jz      short loc_1800294B8
0x18002949f  call    cs:__imp_GetLastError
0x1800294a5  mov     ebx, eax
0x1800294a7  mov     rcx, r14; pv
0x1800294aa  call    cs:__imp_CoTaskMemFree
0x1800294b0  mov     ecx, ebx; dwErrCode
0x1800294b2  call    cs:__imp_SetLastError
0x1800294b8  mov     [rsp+140h+pv], r13
0x1800294bd  lea     rdx, [rsp+140h+pv]; lplpsz
0x1800294c2  lea     rcx, [rbp+40h+pguid]; rclsid
0x1800294c6  call    cs:__imp_StringFromCLSID
0x1800294cc  mov     r14d, eax
0x1800294cf  test    eax, eax
0x1800294d1  jns     short loc_1800294DD
0x1800294d3  mov     edx, 126h
  ... truncated ...
```
