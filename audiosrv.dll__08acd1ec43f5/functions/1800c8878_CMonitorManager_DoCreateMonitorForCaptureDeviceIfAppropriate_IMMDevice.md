# CMonitorManager::DoCreateMonitorForCaptureDeviceIfAppropriate(IMMDevice *)

- ea: `0x1800c8878`
- end: `0x1800c8fa7`
- name: `?DoCreateMonitorForCaptureDeviceIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@@Z`
- size: `1839`
- prototype: `__int64 __fastcall(CMonitorManager *__hidden this, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801293f0`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x180036368`
- `0x18003840c`
- `0x180052f70`
- `0x18006e2fc`
- `0x180071f50`
- `0x1800afbc4`
- `0x1800b205c`
- `0x1800b805c`
- `0x1800c86d8`
- `0x1800c8878`
- `0x1800c8fb0`
- `0x1800cd8d0`
- `0x1800ce774`
- `0x1800e5330`
- `0x1800e7b40`
- `0x1801291c0`
- `0x18012bddc`
- `0x18012cbc4`
- `0x18012dbd8`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800c8c5e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800c8c5e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c8c83`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800c8c83`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8ccb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8dd9`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8ccb`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800c8dd9`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c8ce5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800c8ce5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c88e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c899d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c89f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8d55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8f92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c88e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c899d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c89f1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8d55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8d73`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c8f92`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8df5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8cb2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800c8df5`

## string_xrefs

- `0x1800c8c57`: `AudioSrv.dll`
- `0x1800c8cab`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall CMonitorManager::DoCreateMonitorForCaptureDeviceIfAppropriate(
        CMonitorManager *this,
        struct IMMDevice *a2,
        bool a3)
{
  unsigned int v5; // edi
  int v6; // r15d
  int v7; // eax
  _QWORD *v9; // rcx
  unsigned __int16 *v10; // r8
  bool v11; // r8
  _QWORD *v12; // rcx
  CMonitorManager::CaptureMonitor *v13; // rbx
  HMODULE ModuleHandleW; // rax
  int ActivationFactory; // eax
  int v16; // r12d
  unsigned __int64 v17; // r12
  __int64 v18; // rdx
  __int64 v19; // rcx
  CMonitor *v20; // rcx
  _QWORD *v21; // rcx
  _QWORD *v22; // rax
  ATL::CAtlException *v23; // rbx
  int v24; // [rsp+20h] [rbp-318h]
  bool v25; // [rsp+40h] [rbp-2F8h] BYREF
  LPVOID pv; // [rsp+48h] [rbp-2F0h] BYREF
  __int64 v27; // [rsp+50h] [rbp-2E8h] BYREF
  CMonitorManager::CaptureMonitor *v28; // [rsp+58h] [rbp-2E0h] BYREF
  unsigned __int16 *v29; // [rsp+60h] [rbp-2D8h] BYREF
  int v30; // [rsp+68h] [rbp-2D0h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-2C8h] BYREF
  __int64 v32; // [rsp+78h] [rbp-2C0h] BYREF
  __int64 v33; // [rsp+80h] [rbp-2B8h] BYREF
  int v34; // [rsp+88h] [rbp-2B0h]
  __int64 v35; // [rsp+90h] [rbp-2A8h] BYREF
  _BYTE v36[16]; // [rsp+98h] [rbp-2A0h] BYREF
  _BYTE v37[16]; // [rsp+A8h] [rbp-290h] BYREF
  __int64 v38; // [rsp+B8h] [rbp-280h]
  __int64 (__fastcall *v39)(__int64, HSTRING, _QWORD); // [rsp+C0h] [rbp-278h]
  ATL::CAtlException *v40; // [rsp+C8h] [rbp-270h] BYREF
  HSTRING string; // [rsp+D0h] [rbp-268h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+D8h] [rbp-260h] BYREF
  WCHAR Buffer; // [rsp+F0h] [rbp-248h] BYREF
  _BYTE v44[526]; // [rsp+F2h] [rbp-246h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+338h] [rbp+0h]

  v5 = 0;
  v35 = 0;
  v29 = 0;
  v25 = 0;
  v30 = 0;
  ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v36, (struct _RTL_CRITICAL_SECTION *)((char *)this + 16), a3);
  if ( *((_DWORD *)this + 14) == 1 )
  {
    v6 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_1be09788_6894_4089_8586_9a2a6c265ac5,
           &v35);
    if ( v6 < 0 || (v6 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 24LL))(v35, &v30), v6 < 0) )
    {
LABEL_12:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          76,
          WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
          (unsigned int)v6);
      }
      goto LABEL_16;
    }
    v7 = v30;
    if ( v30 == 1 )
    {
      if ( CMonitor::IsCaptureMonitorEnabled(a2, &v29, &v25) )
        goto LABEL_10;
      v7 = v30;
    }
    if ( v7 || !CMonitorManager::IsRenderMirrorEnabled(this, a2, &v29) )
      goto LABEL_16;
LABEL_10:
    pv = 0;
    v6 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))a2->lpVtbl->GetId)(a2, &pv);
    if ( v6 < 0 )
    {
      CoTaskMemFree(pv);
      goto LABEL_12;
    }
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v29);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800000) != 0 && *((_BYTE *)v9 + 25) >= 4u )
        WPP_SF_(v9[2], 69, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
    }
    v28 = 0;
    v10 = (unsigned __int16 *)&LocaleName;
    if ( !v25 )
      v10 = v29;
    v34 = CMonitorManager::CreateMonitor(this, (const unsigned __int16 *)pv, v10, 0, 0, 0, &v28);
    v6 = v34;
    if ( v34 < 0 )
      goto LABEL_85;
    ATL::CCritSecLock::CCritSecLock((ATL::CCritSecLock *)v37, (struct _RTL_CRITICAL_SECTION *)((char *)this + 72), v11);
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      v13 = v28;
    }
    else
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v13 = v28;
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v28);
        v12 = WPP_GLOBAL_Control;
      }
      else
      {
        v13 = v28;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800000) != 0 && *((_BYTE *)v12 + 25) >= 4u )
        WPP_SF_S(v12[2], 71, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, pv);
    }
    CMonitorManager::FindMonitor(this, &v33, pv);
    if ( !v33 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)(v33 + 72),
          WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
          pv);
      }
      try
      {
        v6 = 0;
        ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(
          (char *)this + 112,
          v13);
      }
      catch ( ATL::CAtlException *v40 )
      {
        v23 = v40;
        if ( *(_DWORD *)v40 == -1073741571 )
          _o__resetstkoflw();
        LODWORD(v27) = *(_DWORD *)v23;
        v6 = v27;
        if ( (int)v27 >= 0 )
        {
          v13 = v28;
          goto LABEL_46;
        }
LABEL_84:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
        ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v37);
LABEL_85:
        wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
        CoTaskMemFree(pv);
        if ( v6 < 0 )
          goto LABEL_12;
LABEL_16:
        ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v36);
        CoTaskMemFree(v29);
        v5 = v6;
        goto LABEL_17;
      }
LABEL_46:
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v29);
      }
      memset_0(v44, 0, 0x206u);
      v27 = 0;
      Buffer = 0;
      ModuleHandleW = GetModuleHandleW(L"AudioSrv.dll");
      if ( ModuleHandleW && LoadStringW(ModuleHandleW, 0x1F4u, &Buffer, 260) > 0 )
      {
        v32 = 0;
        if ( WindowsCreateStringReference(
               L"Windows.Security.Authorization.AppCapabilityAccess.AppCapability",
               0x40u,
               &hstringHeader,
               &string) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        ActivationFactory = RoGetActivationFactory(string, &GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22, &v32);
        v16 = ActivationFactory;
        if ( ActivationFactory < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x988,
            (unsigned int)"avcore\\audiocore\\capturemonitor\\monitormanager.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v24);
LABEL_56:
          wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v32);
          wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v27);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
          ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v37);
          wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v28);
          CoTaskMemFree(pv);
          pv = 0;
          ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v36);
          CoTaskMemFree(v29);
          v5 = v16;
          goto LABEL_17;
        }
        v31 = 0;
        v38 = v32;
        v39 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD))(*(_QWORD *)v32 + 64LL);
        v31 = 0;
        v17 = -1;
        do
          ++v17;
        while ( c_szCapabilityMicrophone[v17] );
        if ( v17 > 0xFFFFFFFF )
        {
          LODWORD(v17) = -1;
          RaiseException(0xC000000D, 1u, 0, 0);
        }
        WindowsCreateStringReference(c_szCapabilityMicrophone, v17, &hstringHeader, &string);
        v16 = v39(v38, string, &v31);
        if ( v16 < 0 )
        {
          v18 = 2443;
LABEL_63:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v18,
            (unsigned int)"avcore\\audiocore\\capturemonitor\\monitormanager.cpp",
            (const char *)(unsigned int)v16,
            v24);
          wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v31);
          goto LABEL_56;
        }
        v19 = v27;
        v27 = 0;
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
        v16 = (**v31)(v31, &GUID_11c7ccb6_c74f_50a3_b960_88008767d939, &v27);
        if ( v16 < 0 )
        {
          v18 = 2444;
          goto LABEL_63;
        }
        wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v31);
        wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v32);
      }
      v20 = (CMonitor *)*((_QWORD *)v13 + 26);
      if ( v34 )
        CMonitor::Terminate(v20, 1, 0);
      else
        CMonitor::Start(v20);
      wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(&v27);
      goto LABEL_84;
    }
    v21 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
    {
      if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800000) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        v22 = (_QWORD *)(v33 + 168);
        if ( *(_QWORD *)(v33 + 192) > 7u )
          v22 = (_QWORD *)*v22;
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          74,
          (unsigned int)WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
          (_DWORD)pv,
          (__int64)v22);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x800000) != 0 && *((_BYTE *)v21 + 25) >= 4u )
        WPP_SF_q(v21[2], 75, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, *((_QWORD *)v13 + 26));
    }
    CMonitorManager::CaptureMonitor::Uninitialize(v13);
    goto LABEL_84;
  }
  ATL::CCritSecLock::~CCritSecLock((ATL::CCritSecLock *)v36);
  CoTaskMemFree(0);
LABEL_17:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v35);
  return v5;
}

```

## disassembly

```asm
0x1800c8878  mov     [rsp+arg_10], rbx
0x1800c887d  push    rdi
0x1800c887e  push    r12
0x1800c8880  push    r13
0x1800c8882  push    r14
0x1800c8884  push    r15
0x1800c8886  sub     rsp, 310h
0x1800c888d  mov     rax, cs:__security_cookie
0x1800c8894  xor     rax, rsp
0x1800c8897  mov     [rsp+338h+var_38], rax
0x1800c889f  mov     rbx, rdx
0x1800c88a2  mov     r13, rcx
0x1800c88a5  xor     edi, edi
0x1800c88a7  mov     [rsp+338h+var_2A8], rdi
0x1800c88af  mov     [rsp+338h+var_2D8], rdi
0x1800c88b4  mov     [rsp+338h+var_2F8], dil
0x1800c88b9  mov     [rsp+338h+var_2D0], edi
0x1800c88bd  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x1800c88c1  lea     rcx, [rsp+338h+var_2A0]; this
0x1800c88c9  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800c88ce  nop
0x1800c88cf  cmp     dword ptr [r13+38h], 1
0x1800c88d4  jz      short loc_1800C88F1
0x1800c88d6  lea     rcx, [rsp+338h+var_2A0]; this
0x1800c88de  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800c88e3  nop
0x1800c88e4  xor     ecx, ecx; pv
0x1800c88e6  call    cs:__imp_CoTaskMemFree
0x1800c88ec  jmp     loc_1800C89FA
0x1800c88f1  mov     rax, [rbx]
0x1800c88f4  lea     r8, [rsp+338h+var_2A8]
0x1800c88fc  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x1800c8903  mov     rcx, rbx
0x1800c8906  mov     rax, [rax]
0x1800c8909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c890e  mov     r15d, eax
0x1800c8911  test    eax, eax
0x1800c8913  js      loc_1800C89A3
0x1800c8919  mov     rcx, [rsp+338h+var_2A8]
0x1800c8921  mov     rax, [rcx]
0x1800c8924  lea     rdx, [rsp+338h+var_2D0]
0x1800c8929  mov     rax, [rax+18h]
0x1800c892d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c8932  mov     r15d, eax
0x1800c8935  test    eax, eax
0x1800c8937  js      short loc_1800C89A3
0x1800c8939  mov     eax, [rsp+338h+var_2D0]
0x1800c893d  cmp     eax, 1
0x1800c8940  jnz     short loc_1800C895C
0x1800c8942  lea     r8, [rsp+338h+var_2F8]; bool *
0x1800c8947  lea     rdx, [rsp+338h+var_2D8]; unsigned __int16 **
0x1800c894c  mov     rcx, rbx; struct IMMDevice *
0x1800c894f  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x1800c8954  test    al, al
0x1800c8956  jnz     short loc_1800C8974
0x1800c8958  mov     eax, [rsp+338h+var_2D0]
0x1800c895c  test    eax, eax
0x1800c895e  jnz     short loc_1800C89DE
0x1800c8960  lea     r8, [rsp+338h+var_2D8]; unsigned __int16 **
0x1800c8965  mov     rdx, rbx; struct IMMDevice *
0x1800c8968  mov     rcx, r13; this
0x1800c896b  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x1800c8970  test    al, al
0x1800c8972  jz      short loc_1800C89DE
0x1800c8974  mov     [rsp+338h+pv], rdi
0x1800c8979  mov     rax, [rbx]
0x1800c897c  lea     rdx, [rsp+338h+pv]
0x1800c8981  mov     rcx, rbx
0x1800c8984  mov     rax, [rax+28h]
0x1800c8988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c898d  mov     r15d, eax
0x1800c8990  test    eax, eax
0x1800c8992  jns     loc_1800C8A32
0x1800c8998  mov     rcx, [rsp+338h+pv]; pv
0x1800c899d  call    cs:__imp_CoTaskMemFree
0x1800c89a3  lea     r14, WPP_GLOBAL_Control
0x1800c89aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c89b1  cmp     rcx, r14
0x1800c89b4  jz      short loc_1800C89DE
0x1800c89b6  test    dword ptr [rcx+1Ch], 800000h
0x1800c89bd  jz      short loc_1800C89DE
0x1800c89bf  cmp     byte ptr [rcx+19h], 2
0x1800c89c3  jb      short loc_1800C89DE
0x1800c89c5  mov     edx, 4Ch ; 'L'
0x1800c89ca  mov     r9d, r15d
0x1800c89cd  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c89d4  mov     rcx, [rcx+10h]
0x1800c89d8  call    WPP_SF_d
0x1800c89dd  nop
0x1800c89de  lea     rcx, [rsp+338h+var_2A0]; this
0x1800c89e6  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800c89eb  nop
0x1800c89ec  mov     rcx, [rsp+338h+var_2D8]; pv
0x1800c89f1  call    cs:__imp_CoTaskMemFree
0x1800c89f7  mov     edi, r15d
0x1800c89fa  lea     rcx, [rsp+338h+var_2A8]
0x1800c8a02  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c8a07  mov     eax, edi
0x1800c8a09  mov     rcx, [rsp+338h+var_38]
0x1800c8a11  xor     rcx, rsp; StackCookie
0x1800c8a14  call    __security_check_cookie
0x1800c8a19  mov     rbx, [rsp+338h+arg_10]
0x1800c8a21  add     rsp, 310h
0x1800c8a28  pop     r15
0x1800c8a2a  pop     r14
0x1800c8a2c  pop     r13
0x1800c8a2e  pop     r12
0x1800c8a30  pop     rdi
0x1800c8a31  retn
0x1800c8a32  lea     r14, WPP_GLOBAL_Control
0x1800c8a39  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8a40  cmp     rcx, r14
0x1800c8a43  jz      short loc_1800C8A9E
0x1800c8a45  test    dword ptr [rcx+1Ch], 800000h
0x1800c8a4c  jz      short loc_1800C8A75
0x1800c8a4e  cmp     byte ptr [rcx+19h], 4
0x1800c8a52  jb      short loc_1800C8A75
0x1800c8a54  mov     edx, 44h ; 'D'
0x1800c8a59  mov     r9, [rsp+338h+var_2D8]
0x1800c8a5e  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8a65  mov     rcx, [rcx+10h]
0x1800c8a69  call    WPP_SF_S
0x1800c8a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8a75  cmp     rcx, r14
0x1800c8a78  jz      short loc_1800C8A9E
0x1800c8a7a  test    dword ptr [rcx+1Ch], 800000h
0x1800c8a81  jz      short loc_1800C8A9E
0x1800c8a83  cmp     byte ptr [rcx+19h], 4
0x1800c8a87  jb      short loc_1800C8A9E
0x1800c8a89  mov     edx, 45h ; 'E'
0x1800c8a8e  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8a95  mov     rcx, [rcx+10h]
0x1800c8a99  call    WPP_SF_
0x1800c8a9e  mov     [rsp+338h+var_2E0], rdi
0x1800c8aa3  lea     r8, LocaleName
0x1800c8aaa  cmp     [rsp+338h+var_2F8], dil
0x1800c8aaf  cmovz   r8, [rsp+338h+var_2D8]; unsigned __int16 *
0x1800c8ab5  lea     rax, [rsp+338h+var_2E0]
0x1800c8aba  mov     [rsp+338h+var_308], rax; struct CMonitorManager::CaptureMonitor **
0x1800c8abf  mov     [rsp+338h+var_310], rdi; struct Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *
0x1800c8ac4  mov     [rsp+338h+var_318], dil; bool
0x1800c8ac9  xor     r9d, r9d; struct StreamConnectionSettings *
0x1800c8acc  mov     rdx, [rsp+338h+pv]; unsigned __int16 *
0x1800c8ad1  mov     rcx, r13; this
0x1800c8ad4  call    ?CreateMonitor@CMonitorManager@@AEAAJPEBG0PEAUStreamConnectionSettings@@_NPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@PEAPEAVCaptureMonitor@1@@Z; CMonitorManager::CreateMonitor(ushort const *,ushort const *,StreamConnectionSettings *,bool,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *,CMonitorManager::CaptureMonitor * *)
0x1800c8ad9  mov     [rsp+338h+var_2B0], eax
0x1800c8ae0  mov     r15d, eax
0x1800c8ae3  test    eax, eax
0x1800c8ae5  js      loc_1800C8F82
0x1800c8aeb  lea     rdx, [r13+48h]; struct _RTL_CRITICAL_SECTION *
0x1800c8aef  lea     rcx, [rsp+338h+var_290]; this
0x1800c8af7  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800c8afc  nop
0x1800c8afd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8b04  cmp     rcx, r14
0x1800c8b07  jz      short loc_1800C8B73
0x1800c8b09  test    dword ptr [rcx+1Ch], 800000h
0x1800c8b10  jz      short loc_1800C8B3E
0x1800c8b12  cmp     byte ptr [rcx+19h], 4
0x1800c8b16  jb      short loc_1800C8B3E
0x1800c8b18  mov     edx, 46h ; 'F'
0x1800c8b1d  mov     rbx, [rsp+338h+var_2E0]
0x1800c8b22  mov     r9, rbx
0x1800c8b25  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8b2c  mov     rcx, [rcx+10h]
0x1800c8b30  call    WPP_SF_q
0x1800c8b35  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8b3c  jmp     short loc_1800C8B43
0x1800c8b3e  mov     rbx, [rsp+338h+var_2E0]
0x1800c8b43  cmp     rcx, r14
0x1800c8b46  jz      short loc_1800C8B78
0x1800c8b48  test    dword ptr [rcx+1Ch], 800000h
0x1800c8b4f  jz      short loc_1800C8B78
0x1800c8b51  cmp     byte ptr [rcx+19h], 4
0x1800c8b55  jb      short loc_1800C8B78
0x1800c8b57  mov     edx, 47h ; 'G'
0x1800c8b5c  mov     r9, [rsp+338h+pv]
0x1800c8b61  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8b68  mov     rcx, [rcx+10h]
0x1800c8b6c  call    WPP_SF_S
0x1800c8b71  jmp     short loc_1800C8B78
0x1800c8b73  mov     rbx, [rsp+338h+var_2E0]
0x1800c8b78  mov     r8, [rsp+338h+pv]
0x1800c8b7d  lea     rdx, [rsp+338h+var_2B8]
0x1800c8b85  mov     rcx, r13
0x1800c8b88  call    ?FindMonitor@CMonitorManager@@AEAA?AV?$CComPtr@VCaptureMonitor@CMonitorManager@@@ATL@@PEBG@Z; CMonitorManager::FindMonitor(ushort const *)
0x1800c8b8d  nop
0x1800c8b8e  mov     rax, [rsp+338h+var_2B8]
0x1800c8b96  test    rax, rax
0x1800c8b99  jnz     loc_1800C8EDC
0x1800c8b9f  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8ba6  cmp     rcx, r14
0x1800c8ba9  jz      short loc_1800C8BD2
0x1800c8bab  test    dword ptr [rcx+1Ch], 800000h
0x1800c8bb2  jz      short loc_1800C8BD2
0x1800c8bb4  cmp     byte ptr [rcx+19h], 4
0x1800c8bb8  jb      short loc_1800C8BD2
0x1800c8bba  lea     edx, [rax+48h]
0x1800c8bbd  mov     r9, [rsp+338h+pv]
0x1800c8bc2  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8bc9  mov     rcx, [rcx+10h]
0x1800c8bcd  call    WPP_SF_S
0x1800c8bd2  mov     r15d, edi
0x1800c8bd5  lea     rcx, [r13+70h]
0x1800c8bd9  mov     rdx, rbx
0x1800c8bdc  call    ?AddTail@?$CAtlList@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAAPEAU__POSITION@@PEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(CMonitorManager::CaptureMonitor *)
0x1800c8be1  nop
0x1800c8be2  jmp     short loc_1800C8C00
0x1800c8be4  mov     r15d, dword ptr [rsp+338h+var_2E8]
0x1800c8be9  xor     edi, edi
0x1800c8beb  lea     r14, WPP_GLOBAL_Control
0x1800c8bf2  test    r15d, r15d
0x1800c8bf5  js      loc_1800C8F66
0x1800c8bfb  mov     rbx, [rsp+338h+var_2E0]
0x1800c8c00  mov     rcx, cs:WPP_GLOBAL_Control
0x1800c8c07  cmp     rcx, r14
0x1800c8c0a  jz      short loc_1800C8C35
0x1800c8c0c  test    dword ptr [rcx+1Ch], 800000h
0x1800c8c13  jz      short loc_1800C8C35
0x1800c8c15  cmp     byte ptr [rcx+19h], 4
0x1800c8c19  jb      short loc_1800C8C35
0x1800c8c1b  mov     edx, 49h ; 'I'
0x1800c8c20  mov     r9, [rsp+338h+var_2D8]
0x1800c8c25  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800c8c2c  mov     rcx, [rcx+10h]
0x1800c8c30  call    WPP_SF_S
0x1800c8c35  xor     edx, edx; Val
0x1800c8c37  mov     r8d, 206h; Size
0x1800c8c3d  lea     rcx, [rsp+338h+var_246]; void *
0x1800c8c45  call    memset_0
0x1800c8c4a  mov     [rsp+338h+var_2E8], rdi
0x1800c8c4f  mov     [rsp+338h+Buffer], di
0x1800c8c57  lea     rcx, aAudiosrvDll_1; "AudioSrv.dll"
0x1800c8c5e  call    cs:__imp_GetModuleHandleW
0x1800c8c64  test    rax, rax
0x1800c8c67  jz      loc_1800C8EAB
0x1800c8c6d  mov     r9d, 104h; cchBufferMax
0x1800c8c73  lea     r8, [rsp+338h+Buffer]; lpBuffer
0x1800c8c7b  mov     edx, 1F4h; uID
0x1800c8c80  mov     rcx, rax; hInstance
0x1800c8c83  call    cs:__imp_LoadStringW
0x1800c8c89  test    eax, eax
0x1800c8c8b  jle     loc_1800C8EAB
0x1800c8c91  mov     [rsp+338h+var_2C0], rdi
0x1800c8c96  lea     r9, [rsp+338h+string]; string
0x1800c8c9e  lea     r8, [rsp+338h+hstringHeader]; hstringHeader
0x1800c8ca6  mov     edx, 40h ; '@'; length
0x1800c8cab  lea     rcx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x1800c8cb2  call    cs:__imp_WindowsCreateStringReference
0x1800c8cb8  test    eax, eax
0x1800c8cba  jns     short loc_1800C8CD1
0x1800c8cbc  xor     r9d, r9d; lpArguments
0x1800c8cbf  xor     r8d, r8d; nNumberOfArguments
0x1800c8cc2  lea     edx, [r9+1]; dwExceptionFlags
0x1800c8cc6  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800c8ccb  call    cs:__imp_RaiseException
0x1800c8cd1  lea     r8, [rsp+338h+var_2C0]
0x1800c8cd6  lea     rdx, _GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x1800c8cdd  mov     rcx, [rsp+338h+string]
0x1800c8ce5  call    cs:__imp_RoGetActivationFactory
0x1800c8ceb  mov     r12d, eax
0x1800c8cee  test    eax, eax
0x1800c8cf0  jns     loc_1800C8D81
0x1800c8cf6  mov     rcx, [rsp+338h]; this
0x1800c8cfe  mov     r9d, eax; char *
0x1800c8d01  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\capturemonitor\\moni"...
0x1800c8d08  mov     edx, 988h; void *
0x1800c8d0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c8d12  nop
0x1800c8d13  lea     rcx, [rsp+338h+var_2C0]
0x1800c8d18  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x1800c8d1d  nop
0x1800c8d1e  lea     rcx, [rsp+338h+var_2E8]
0x1800c8d23  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x1800c8d28  nop
0x1800c8d29  lea     rcx, [rsp+338h+var_2B8]
0x1800c8d31  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c8d36  nop
0x1800c8d37  lea     rcx, [rsp+338h+var_290]; this
0x1800c8d3f  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800c8d44  nop
0x1800c8d45  lea     rcx, [rsp+338h+var_2E0]
0x1800c8d4a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800c8d4f  nop
0x1800c8d50  mov     rcx, [rsp+338h+pv]; pv
0x1800c8d55  call    cs:__imp_CoTaskMemFree
0x1800c8d5b  mov     [rsp+338h+pv], rdi
0x1800c8d60  lea     rcx, [rsp+338h+var_2A0]; this
0x1800c8d68  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800c8d6d  nop
0x1800c8d6e  mov     rcx, [rsp+338h+var_2D8]; pv
0x1800c8d73  call    cs:__imp_CoTaskMemFree
0x1800c8d79  mov     edi, r12d
0x1800c8d7c  jmp     loc_1800C89FA
0x1800c8d81  mov     [rsp+338h+var_2C8], rdi
0x1800c8d86  mov     rax, [rsp+338h+var_2C0]
0x1800c8d8b  mov     [rsp+338h+var_280], rax
0x1800c8d93  mov     rax, [rax]
0x1800c8d96  mov     rax, [rax+40h]
0x1800c8d9a  mov     [rsp+338h+var_278], rax
  ... truncated ...
```
