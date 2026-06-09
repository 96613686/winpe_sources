# KSMidiDevice::OpenStream(void)

- ea: `0x180049b78`
- end: `0x18004a363`
- name: `?OpenStream@KSMidiDevice@@IEAAJXZ`
- size: `2027`
- prototype: `__int64 __fastcall(KSMidiDevice *__hidden this)`
- caller_count: `2`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048b80`
- `0x18004acb0`

## callees

- `0x180005020`
- `0x180005044`
- `0x180005800`
- `0x180005e90`
- `0x18000b394`
- `0x18000c684`
- `0x180013540`
- `0x180015144`
- `0x180042480`
- `0x180043a74`
- `0x1800467b0`
- `0x180047210`
- `0x180047294`
- `0x180047b58`
- `0x180048474`
- `0x180048670`
- `0x18004881c`
- `0x180048940`
- `0x180048a64`
- `0x180049b78`
- `0x18004a36c`
- `0x18004a458`
- `0x180057c3c`
- `0x18005813c`
- `0x1800592dc`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a114`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004a114`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049d57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049deb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049d57`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180049deb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d0a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180049d0a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a09d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18004a09d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049ff2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180049ff2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004a0d0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0af`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049fdf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a0af`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004a006`
- `api-ms-win-core-com-l1-1-0!StringFromCLSID` at `0x18004a006`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a0e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f44`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049f9b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049fea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a0e4`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180049f6b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180049f6b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049c14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0bb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049c14`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049e64`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18004a0bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
    v51[0] = off_18005F9B0;
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
    v55[0] = off_18005F980;
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
0x180049b78  push    rbp
0x180049b7a  push    rbx
0x180049b7b  push    rsi
0x180049b7c  push    rdi
0x180049b7d  push    r12
0x180049b7f  push    r13
0x180049b81  push    r14
0x180049b83  push    r15
0x180049b85  lea     rbp, [rsp-8]
0x180049b8a  sub     rsp, 108h
0x180049b91  mov     rax, cs:__security_cookie
0x180049b98  xor     rax, rsp
0x180049b9b  mov     [rbp+40h+var_48], rax
0x180049b9f  mov     rdi, rcx
0x180049ba2  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180049ba9  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180049bae  xor     r13d, r13d
0x180049bb1  test    al, al
0x180049bb3  jz      loc_18004A336
0x180049bb9  mov     [rbp+40h+var_A8], rdi
0x180049bbd  mov     [rbp+40h+var_A0], 1
0x180049bc1  cmp     [rdi+38h], r13
0x180049bc5  jz      short loc_180049BD0
0x180049bc7  lea     r15, [rdi+4Ch]
0x180049bcb  jmp     loc_180049E6A
0x180049bd0  mov     rcx, [rdi+30h]; SRWLock
0x180049bd4  call    ?GetHandle@KsHandleWrapper@@QEAAPEAXXZ; KsHandleWrapper::GetHandle(void)
0x180049bd9  mov     rbx, rax
0x180049bdc  mov     qword ptr [rbp+40h+pguid.Data1], rax
0x180049be0  inc     rax
0x180049be3  test    rax, 0FFFFFFFFFFFFFFFEh
0x180049be9  jnz     short loc_180049C50
0x180049beb  mov     rcx, [rbp+48h]; this
0x180049bef  mov     r9d, 8007000Eh; char *
0x180049bf5  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049bfc  mov     edx, 101h; void *
0x180049c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049c06  nop
0x180049c07  lea     rax, [rbx-1]
0x180049c0b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180049c0f  ja      short loc_180049C1B
0x180049c11  mov     rcx, rbx; hObject
0x180049c14  call    cs:__imp_CloseHandle
0x180049c1a  nop
0x180049c1b  mov     rcx, [rdi+58h]; this
0x180049c1f  test    rcx, rcx
0x180049c22  jz      loc_18004A1C9
0x180049c28  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180049c2d  mov     rbx, [rdi+58h]
0x180049c31  mov     [rdi+58h], r13
0x180049c35  test    rbx, rbx
0x180049c38  jz      loc_18004A1C9
0x180049c3e  mov     rcx, rbx; this
0x180049c41  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180049c46  mov     edx, 90h
0x180049c4b  jmp     loc_18004A1C1
0x180049c50  mov     [rsp+140h+pv], rbx
0x180049c55  mov     rax, [rdi+40h]
0x180049c59  mov     [rsp+140h+var_F0], rax
0x180049c5e  lea     r15, [rdi+4Ch]
0x180049c62  lea     r8, [rdi+48h]
0x180049c66  lea     rax, [rsp+140h+pv]
0x180049c6b  mov     [rsp+140h+var_120], rax; int
0x180049c70  mov     r9, r15
0x180049c73  lea     rdx, [rsp+140h+var_F0]
0x180049c78  lea     rcx, [rsp+140h+Block]
0x180049c7d  call    ??$make_unique@VKsHandleWrapper@@PEAGAEAIAEAW4_MidiTransport@@PEAX$0A@@std@@YA?AV?$unique_ptr@VKsHandleWrapper@@U?$default_delete@VKsHandleWrapper@@@std@@@0@$$QEAPEAGAEAIAEAW4_MidiTransport@@$$QEAPEAX@Z; std::make_unique<KsHandleWrapper,ushort *,uint &,_MidiTransport &,void *,0>(ushort * &&,uint &,_MidiTransport &,void * &&)
0x180049c82  mov     rdx, [rax]
0x180049c85  mov     [rax], r13
0x180049c88  mov     rsi, [rdi+38h]
0x180049c8c  mov     [rdi+38h], rdx
0x180049c90  mov     r14d, 0D8h
0x180049c96  test    rsi, rsi
0x180049c99  jz      short loc_180049CAE
0x180049c9b  mov     rcx, rsi; this
0x180049c9e  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180049ca3  mov     edx, r14d
0x180049ca6  mov     rcx, rsi; Block
0x180049ca9  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049cae  mov     rsi, [rsp+140h+Block]
0x180049cb3  test    rsi, rsi
0x180049cb6  jz      short loc_180049CCB
0x180049cb8  mov     rcx, rsi; this
0x180049cbb  call    ??1KsHandleWrapper@@QEAA@XZ; KsHandleWrapper::~KsHandleWrapper(void)
0x180049cc0  mov     rdx, r14
0x180049cc3  mov     rcx, rsi; Block
0x180049cc6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049ccb  mov     rsi, [rdi+38h]
0x180049ccf  lea     rax, off_18005F9B0
0x180049cd6  mov     [rsp+140h+var_E8], rax
0x180049cdb  mov     [rsp+140h+var_E0], rdi
0x180049ce0  lea     rax, [rsp+140h+var_E8]
0x180049ce5  mov     [rbp+40h+var_B0], rax
0x180049ce9  lea     rax, [rsp+140h+var_E8]
0x180049cee  mov     [rsp+140h+Block], rax
0x180049cf3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::GetImpl(void)'::`2'::impl
0x180049cfa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MIDI2DeviceRemoval>::__private_IsEnabled(void)
0x180049cff  test    al, al
0x180049d01  jz      loc_180049DF2
0x180049d07  mov     rcx, rsi; SRWLock
0x180049d0a  call    cs:__imp_AcquireSRWLockExclusive
0x180049d10  cmp     [rbp+40h+var_B0], r13
0x180049d14  jnz     short loc_180049D23
0x180049d16  mov     r14d, 80070057h
0x180049d1c  mov     edx, 49h ; 'I'
0x180049d21  jmp     short loc_180049D3C
0x180049d23  lea     rcx, [rsi+40h]
0x180049d27  cmp     [rcx+38h], r13
0x180049d2b  jz      loc_180049DD9
0x180049d31  mov     r14d, 800704DFh
0x180049d37  mov     edx, 4Ah ; 'J'; void *
0x180049d3c  mov     r9d, r14d; char *
0x180049d3f  lea     r8, aAvcoreMidi2Inc_1; "avcore\\midi2\\inc\\KsHandleWrapper.h"
0x180049d46  mov     rcx, [rbp+48h]; this
0x180049d4a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d4f  test    rsi, rsi
0x180049d52  jz      short loc_180049D5E
0x180049d54  mov     rcx, rsi; SRWLock
0x180049d57  call    cs:__imp_ReleaseSRWLockExclusive
0x180049d5d  nop
0x180049d5e  mov     rcx, [rbp+40h+var_B0]
0x180049d62  test    rcx, rcx
0x180049d65  jz      short loc_180049D7E
0x180049d67  lea     rdx, [rsp+140h+var_E8]
0x180049d6c  cmp     rcx, rdx
0x180049d6f  mov     rax, [rcx]
0x180049d72  setnz   dl
0x180049d75  mov     rax, [rax+20h]
0x180049d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d7e  mov     edx, 10Ah; void *
0x180049d83  mov     rcx, [rbp+48h]; this
0x180049d87  mov     r9d, r14d; char *
0x180049d8a  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049d91  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049d96  nop
0x180049d97  mov     rcx, rbx; hObject
0x180049d9a  call    cs:__imp_CloseHandle
0x180049da0  nop
0x180049da1  mov     rcx, [rdi+58h]; this
0x180049da5  test    rcx, rcx
0x180049da8  jz      short loc_180049DD1
0x180049daa  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180049daf  mov     rbx, [rdi+58h]
0x180049db3  mov     [rdi+58h], r13
0x180049db7  test    rbx, rbx
0x180049dba  jz      short loc_180049DD1
0x180049dbc  mov     rcx, rbx; this
0x180049dbf  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180049dc4  mov     edx, 90h
0x180049dc9  mov     rcx, rbx; Block
0x180049dcc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049dd1  mov     eax, r14d
0x180049dd4  jmp     loc_18004A338
0x180049dd9  lea     rdx, [rsp+140h+var_E8]
0x180049dde  call    ??4?$function@$$A6AXXZ@std@@QEAAAEAV01@$$QEAV01@@Z; std::function<void (void)>::operator=(std::function<void (void)> &&)
0x180049de3  test    rsi, rsi
0x180049de6  jz      short loc_180049DF2
0x180049de8  mov     rcx, rsi; SRWLock
0x180049deb  call    cs:__imp_ReleaseSRWLockExclusive
0x180049df1  nop
0x180049df2  mov     rcx, [rbp+40h+var_B0]
0x180049df6  test    rcx, rcx
0x180049df9  jz      short loc_180049E12
0x180049dfb  mov     rax, [rcx]
0x180049dfe  lea     rdx, [rsp+140h+var_E8]
0x180049e03  cmp     rcx, rdx
0x180049e06  setnz   dl
0x180049e09  mov     rax, [rax+20h]
0x180049e0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e12  lea     rax, off_18005F980
0x180049e19  mov     [rbp+40h+var_98], rax
0x180049e1d  mov     [rbp+40h+var_90], rdi
0x180049e21  lea     rax, [rbp+40h+var_98]
0x180049e25  mov     [rbp+40h+var_60], rax
0x180049e29  lea     rdx, [rbp+40h+var_98]
0x180049e2d  mov     rcx, [rdi+38h]; SRWLock
0x180049e31  call    ?RegisterOnRestoreCallback@KsHandleWrapper@@QEAAJV?$function@$$A6AXXZ@std@@@Z; KsHandleWrapper::RegisterOnRestoreCallback(std::function<void (void)>)
0x180049e36  mov     r14d, eax
0x180049e39  test    eax, eax
0x180049e3b  jns     short loc_180049E47
0x180049e3d  mov     edx, 10Eh
0x180049e42  jmp     loc_180049D83
0x180049e47  mov     rcx, [rdi+38h]; this
0x180049e4b  call    ?Open@KsHandleWrapper@@QEAAJXZ; KsHandleWrapper::Open(void)
0x180049e50  mov     r14d, eax
0x180049e53  test    eax, eax
0x180049e55  jns     short loc_180049E61
0x180049e57  mov     edx, 110h
0x180049e5c  jmp     loc_180049D83
0x180049e61  mov     rcx, rbx; hObject
0x180049e64  call    cs:__imp_CloseHandle
0x180049e6a  mov     eax, [r15]
0x180049e6d  sub     eax, 2
0x180049e70  mov     esi, 90h
0x180049e75  test    eax, 0FFFFFFFDh
0x180049e7a  jnz     loc_18004A22B
0x180049e80  cmp     [rdi+50h], r13
0x180049e84  jnz     loc_18004A0EA
0x180049e8a  xorps   xmm0, xmm0
0x180049e8d  movups  xmmword ptr [rbp+40h+pguid.Data1], xmm0
0x180049e91  mov     [rsp+140h+pv], r13
0x180049e96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180049e9d  lea     ecx, [rsi-28h]; unsigned __int64
0x180049ea0  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180049ea5  mov     rcx, rax
0x180049ea8  mov     r12d, 7
0x180049eae  test    rax, rax
0x180049eb1  jz      short loc_180049EEC
0x180049eb3  mov     [rax], r13
0x180049eb6  mov     [rax+8], r13
0x180049eba  mov     [rax+10h], r13
0x180049ebe  mov     [rax+18h], r13
0x180049ec2  mov     [rax+20h], r13d
0x180049ec6  mov     [rax+28h], r13
0x180049eca  mov     [rax+30h], r13
0x180049ece  mov     [rax+38h], r13
0x180049ed2  mov     [rax+40h], r13
0x180049ed6  xorps   xmm0, xmm0
0x180049ed9  movups  xmmword ptr [rax+48h], xmm0
0x180049edd  mov     [rax+58h], r13
0x180049ee1  mov     [rax+60h], r12
0x180049ee5  mov     [rax+48h], r13w
0x180049eea  jmp     short loc_180049EEF
0x180049eec  mov     rcx, r13
0x180049eef  mov     rbx, [rdi+50h]
0x180049ef3  mov     [rdi+50h], rcx
0x180049ef7  test    rbx, rbx
0x180049efa  jz      short loc_180049F11
0x180049efc  mov     rcx, rbx; this
0x180049eff  call    ??1MEMORY_MAPPED_PIPE@@QEAA@XZ; MEMORY_MAPPED_PIPE::~MEMORY_MAPPED_PIPE(void)
0x180049f04  mov     edx, 68h ; 'h'
0x180049f09  mov     rcx, rbx; Block
0x180049f0c  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180049f11  mov     rcx, [rdi+50h]
0x180049f15  test    rcx, rcx
0x180049f18  jnz     short loc_180049F4F
0x180049f1a  mov     rcx, [rbp+48h]; this
0x180049f1e  mov     r9d, 8007000Eh; char *
0x180049f24  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049f2b  mov     edx, 11Fh; void *
0x180049f30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f35  nop
0x180049f36  mov     rcx, [rsp+140h+pv]; pv
0x180049f3b  test    rcx, rcx
0x180049f3e  jz      loc_18004A19B
0x180049f44  call    cs:__imp_CoTaskMemFree
0x180049f4a  jmp     loc_18004A19B
0x180049f4f  mov     eax, [rdi+2Ch]
0x180049f52  mov     [rcx+4], eax
0x180049f55  mov     ecx, r13d
0x180049f58  cmp     dword ptr [r15], 2
0x180049f5c  setnz   cl
0x180049f5f  inc     ecx
0x180049f61  mov     rax, [rdi+50h]
0x180049f65  mov     [rax], ecx
0x180049f67  lea     rcx, [rbp+40h+pguid]; pguid
0x180049f6b  call    cs:__imp_CoCreateGuid
0x180049f71  mov     r14d, eax
0x180049f74  test    eax, eax
0x180049f76  jns     short loc_180049FD5
0x180049f78  mov     edx, 125h; void *
0x180049f7d  mov     r9d, r14d; char *
0x180049f80  lea     r8, aAvcoreMidi2Lib; "avcore\\midi2\\libs\\midiks\\midiks.cpp"
0x180049f87  mov     rcx, [rbp+48h]; this
0x180049f8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180049f90  nop
0x180049f91  mov     rcx, [rsp+140h+pv]; pv
0x180049f96  test    rcx, rcx
0x180049f99  jz      short loc_180049FA2
0x180049f9b  call    cs:__imp_CoTaskMemFree
0x180049fa1  nop
0x180049fa2  mov     rcx, [rdi+58h]; this
0x180049fa6  test    rcx, rcx
0x180049fa9  jz      loc_180049DD1
0x180049faf  call    ?Shutdown@CMidiXProc@@QEAAJXZ; CMidiXProc::Shutdown(void)
0x180049fb4  mov     rbx, [rdi+58h]
0x180049fb8  mov     [rdi+58h], r13
0x180049fbc  test    rbx, rbx
0x180049fbf  jz      loc_180049DD1
0x180049fc5  mov     rcx, rbx; this
0x180049fc8  call    ??1CMidiXProc@@QEAA@XZ; CMidiXProc::~CMidiXProc(void)
0x180049fcd  mov     rdx, rsi
0x180049fd0  jmp     loc_180049DC9
0x180049fd5  mov     r14, [rsp+140h+pv]
0x180049fda  test    r14, r14
0x180049fdd  jz      short loc_180049FF8
0x180049fdf  call    cs:__imp_GetLastError
0x180049fe5  mov     ebx, eax
0x180049fe7  mov     rcx, r14; pv
0x180049fea  call    cs:__imp_CoTaskMemFree
0x180049ff0  mov     ecx, ebx; dwErrCode
0x180049ff2  call    cs:__imp_SetLastError
0x180049ff8  mov     [rsp+140h+pv], r13
0x180049ffd  lea     rdx, [rsp+140h+pv]; lplpsz
0x18004a002  lea     rcx, [rbp+40h+pguid]; rclsid
0x18004a006  call    cs:__imp_StringFromCLSID
0x18004a00c  mov     r14d, eax
0x18004a00f  test    eax, eax
0x18004a011  jns     short loc_18004A01D
0x18004a013  mov     edx, 126h
  ... truncated ...
```
