# CMonitorManager::DoCreateMonitorForCaptureDeviceIfAppropriate(IMMDevice *)

- ea: `0x1800ca864`
- end: `0x1800caf93`
- name: `?DoCreateMonitorForCaptureDeviceIfAppropriate@CMonitorManager@@AEAAJPEAUIMMDevice@@@Z`
- size: `1839`
- prototype: `__int64 __fastcall(CMonitorManager *__hidden this, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1801291a0`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x180036208`
- `0x1800382ac`
- `0x180053400`
- `0x18006e7fc`
- `0x180072450`
- `0x1800b18b4`
- `0x1800b3d4c`
- `0x1800b9bac`
- `0x1800ca6c4`
- `0x1800ca864`
- `0x1800caf9c`
- `0x1800cf8c0`
- `0x1800d0764`
- `0x1800e5ab0`
- `0x1800e82c0`
- `0x180128f70`
- `0x18012bb8c`
- `0x18012c974`
- `0x18012d988`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cac4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800cac4a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cac6f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x1800cac6f`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cacb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cadc5`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cacb7`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800cadc5`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cacd1`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800cacd1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca8d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca9dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caf7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca8d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca989`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800ca9dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad41`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800cad5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800caf7e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cac9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cade1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cac9e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800cade1`

## string_xrefs

- `0x1800cac43`: `AudioSrv.dll`
- `0x1800cac97`: `Windows.Security.Authorization.AppCapabilityAccess.AppCapability`

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
          &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 68, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v29);
        v9 = WPP_GLOBAL_Control;
      }
      if ( v9 != &WPP_GLOBAL_Control && (*((_DWORD *)v9 + 7) & 0x800000) != 0 && *((_BYTE *)v9 + 25) >= 4u )
        WPP_SF_(v9[2], 69, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids);
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
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v28);
        v12 = WPP_GLOBAL_Control;
      }
      else
      {
        v13 = v28;
      }
      if ( v12 != &WPP_GLOBAL_Control && (*((_DWORD *)v12 + 7) & 0x800000) != 0 && *((_BYTE *)v12 + 25) >= 4u )
        WPP_SF_S(v12[2], 71, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, pv);
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
          &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
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
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 73, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, v29);
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
          (unsigned int)&WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids,
          (_DWORD)pv,
          (__int64)v22);
        v21 = WPP_GLOBAL_Control;
      }
      if ( v21 != &WPP_GLOBAL_Control && (*((_DWORD *)v21 + 7) & 0x800000) != 0 && *((_BYTE *)v21 + 25) >= 4u )
        WPP_SF_q(v21[2], 75, &WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids, *((_QWORD *)v13 + 26));
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
0x1800ca864  mov     [rsp+arg_10], rbx
0x1800ca869  push    rdi
0x1800ca86a  push    r12
0x1800ca86c  push    r13
0x1800ca86e  push    r14
0x1800ca870  push    r15
0x1800ca872  sub     rsp, 310h
0x1800ca879  mov     rax, cs:__security_cookie
0x1800ca880  xor     rax, rsp
0x1800ca883  mov     [rsp+338h+var_38], rax
0x1800ca88b  mov     rbx, rdx
0x1800ca88e  mov     r13, rcx
0x1800ca891  xor     edi, edi
0x1800ca893  mov     [rsp+338h+var_2A8], rdi
0x1800ca89b  mov     [rsp+338h+var_2D8], rdi
0x1800ca8a0  mov     [rsp+338h+var_2F8], dil
0x1800ca8a5  mov     [rsp+338h+var_2D0], edi
0x1800ca8a9  lea     rdx, [rcx+10h]; struct _RTL_CRITICAL_SECTION *
0x1800ca8ad  lea     rcx, [rsp+338h+var_2A0]; this
0x1800ca8b5  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800ca8ba  nop
0x1800ca8bb  cmp     dword ptr [r13+38h], 1
0x1800ca8c0  jz      short loc_1800CA8DD
0x1800ca8c2  lea     rcx, [rsp+338h+var_2A0]; this
0x1800ca8ca  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800ca8cf  nop
0x1800ca8d0  xor     ecx, ecx; pv
0x1800ca8d2  call    cs:__imp_CoTaskMemFree
0x1800ca8d8  jmp     loc_1800CA9E6
0x1800ca8dd  mov     rax, [rbx]
0x1800ca8e0  lea     r8, [rsp+338h+var_2A8]
0x1800ca8e8  lea     rdx, _GUID_1be09788_6894_4089_8586_9a2a6c265ac5
0x1800ca8ef  mov     rcx, rbx
0x1800ca8f2  mov     rax, [rax]
0x1800ca8f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca8fa  mov     r15d, eax
0x1800ca8fd  test    eax, eax
0x1800ca8ff  js      loc_1800CA98F
0x1800ca905  mov     rcx, [rsp+338h+var_2A8]
0x1800ca90d  mov     rax, [rcx]
0x1800ca910  lea     rdx, [rsp+338h+var_2D0]
0x1800ca915  mov     rax, [rax+18h]
0x1800ca919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca91e  mov     r15d, eax
0x1800ca921  test    eax, eax
0x1800ca923  js      short loc_1800CA98F
0x1800ca925  mov     eax, [rsp+338h+var_2D0]
0x1800ca929  cmp     eax, 1
0x1800ca92c  jnz     short loc_1800CA948
0x1800ca92e  lea     r8, [rsp+338h+var_2F8]; bool *
0x1800ca933  lea     rdx, [rsp+338h+var_2D8]; unsigned __int16 **
0x1800ca938  mov     rcx, rbx; struct IMMDevice *
0x1800ca93b  call    ?IsCaptureMonitorEnabled@CMonitor@@KA_NPEAUIMMDevice@@PEAPEAGPEA_N@Z; CMonitor::IsCaptureMonitorEnabled(IMMDevice *,ushort * *,bool *)
0x1800ca940  test    al, al
0x1800ca942  jnz     short loc_1800CA960
0x1800ca944  mov     eax, [rsp+338h+var_2D0]
0x1800ca948  test    eax, eax
0x1800ca94a  jnz     short loc_1800CA9CA
0x1800ca94c  lea     r8, [rsp+338h+var_2D8]; unsigned __int16 **
0x1800ca951  mov     rdx, rbx; struct IMMDevice *
0x1800ca954  mov     rcx, r13; this
0x1800ca957  call    ?IsRenderMirrorEnabled@CMonitorManager@@AEAA_NPEAUIMMDevice@@PEAPEAG@Z; CMonitorManager::IsRenderMirrorEnabled(IMMDevice *,ushort * *)
0x1800ca95c  test    al, al
0x1800ca95e  jz      short loc_1800CA9CA
0x1800ca960  mov     [rsp+338h+pv], rdi
0x1800ca965  mov     rax, [rbx]
0x1800ca968  lea     rdx, [rsp+338h+pv]
0x1800ca96d  mov     rcx, rbx
0x1800ca970  mov     rax, [rax+28h]
0x1800ca974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ca979  mov     r15d, eax
0x1800ca97c  test    eax, eax
0x1800ca97e  jns     loc_1800CAA1E
0x1800ca984  mov     rcx, [rsp+338h+pv]; pv
0x1800ca989  call    cs:__imp_CoTaskMemFree
0x1800ca98f  lea     r14, WPP_GLOBAL_Control
0x1800ca996  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ca99d  cmp     rcx, r14
0x1800ca9a0  jz      short loc_1800CA9CA
0x1800ca9a2  test    dword ptr [rcx+1Ch], 800000h
0x1800ca9a9  jz      short loc_1800CA9CA
0x1800ca9ab  cmp     byte ptr [rcx+19h], 2
0x1800ca9af  jb      short loc_1800CA9CA
0x1800ca9b1  mov     edx, 4Ch ; 'L'
0x1800ca9b6  mov     r9d, r15d
0x1800ca9b9  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800ca9c0  mov     rcx, [rcx+10h]
0x1800ca9c4  call    WPP_SF_d
0x1800ca9c9  nop
0x1800ca9ca  lea     rcx, [rsp+338h+var_2A0]; this
0x1800ca9d2  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800ca9d7  nop
0x1800ca9d8  mov     rcx, [rsp+338h+var_2D8]; pv
0x1800ca9dd  call    cs:__imp_CoTaskMemFree
0x1800ca9e3  mov     edi, r15d
0x1800ca9e6  lea     rcx, [rsp+338h+var_2A8]
0x1800ca9ee  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800ca9f3  mov     eax, edi
0x1800ca9f5  mov     rcx, [rsp+338h+var_38]
0x1800ca9fd  xor     rcx, rsp; StackCookie
0x1800caa00  call    __security_check_cookie
0x1800caa05  mov     rbx, [rsp+338h+arg_10]
0x1800caa0d  add     rsp, 310h
0x1800caa14  pop     r15
0x1800caa16  pop     r14
0x1800caa18  pop     r13
0x1800caa1a  pop     r12
0x1800caa1c  pop     rdi
0x1800caa1d  retn
0x1800caa1e  lea     r14, WPP_GLOBAL_Control
0x1800caa25  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caa2c  cmp     rcx, r14
0x1800caa2f  jz      short loc_1800CAA8A
0x1800caa31  test    dword ptr [rcx+1Ch], 800000h
0x1800caa38  jz      short loc_1800CAA61
0x1800caa3a  cmp     byte ptr [rcx+19h], 4
0x1800caa3e  jb      short loc_1800CAA61
0x1800caa40  mov     edx, 44h ; 'D'
0x1800caa45  mov     r9, [rsp+338h+var_2D8]
0x1800caa4a  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800caa51  mov     rcx, [rcx+10h]
0x1800caa55  call    WPP_SF_S
0x1800caa5a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caa61  cmp     rcx, r14
0x1800caa64  jz      short loc_1800CAA8A
0x1800caa66  test    dword ptr [rcx+1Ch], 800000h
0x1800caa6d  jz      short loc_1800CAA8A
0x1800caa6f  cmp     byte ptr [rcx+19h], 4
0x1800caa73  jb      short loc_1800CAA8A
0x1800caa75  mov     edx, 45h ; 'E'
0x1800caa7a  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800caa81  mov     rcx, [rcx+10h]
0x1800caa85  call    WPP_SF_
0x1800caa8a  mov     [rsp+338h+var_2E0], rdi
0x1800caa8f  lea     r8, LocaleName
0x1800caa96  cmp     [rsp+338h+var_2F8], dil
0x1800caa9b  cmovz   r8, [rsp+338h+var_2D8]; unsigned __int16 *
0x1800caaa1  lea     rax, [rsp+338h+var_2E0]
0x1800caaa6  mov     [rsp+338h+var_308], rax; struct CMonitorManager::CaptureMonitor **
0x1800caaab  mov     [rsp+338h+var_310], rdi; struct Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *
0x1800caab0  mov     [rsp+338h+var_318], dil; bool
0x1800caab5  xor     r9d, r9d; struct StreamConnectionSettings *
0x1800caab8  mov     rdx, [rsp+338h+pv]; unsigned __int16 *
0x1800caabd  mov     rcx, r13; this
0x1800caac0  call    ?CreateMonitor@CMonitorManager@@AEAAJPEBG0PEAUStreamConnectionSettings@@_NPEAUICapabilityUsageSession@Management@CapabilityAccess@Internal@Windows@@PEAPEAVCaptureMonitor@1@@Z; CMonitorManager::CreateMonitor(ushort const *,ushort const *,StreamConnectionSettings *,bool,Windows::Internal::CapabilityAccess::Management::ICapabilityUsageSession *,CMonitorManager::CaptureMonitor * *)
0x1800caac5  mov     [rsp+338h+var_2B0], eax
0x1800caacc  mov     r15d, eax
0x1800caacf  test    eax, eax
0x1800caad1  js      loc_1800CAF6E
0x1800caad7  lea     rdx, [r13+48h]; struct _RTL_CRITICAL_SECTION *
0x1800caadb  lea     rcx, [rsp+338h+var_290]; this
0x1800caae3  call    ??0CCritSecLock@ATL@@QEAA@AEAU_RTL_CRITICAL_SECTION@@_N@Z; ATL::CCritSecLock::CCritSecLock(_RTL_CRITICAL_SECTION &,bool)
0x1800caae8  nop
0x1800caae9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800caaf0  cmp     rcx, r14
0x1800caaf3  jz      short loc_1800CAB5F
0x1800caaf5  test    dword ptr [rcx+1Ch], 800000h
0x1800caafc  jz      short loc_1800CAB2A
0x1800caafe  cmp     byte ptr [rcx+19h], 4
0x1800cab02  jb      short loc_1800CAB2A
0x1800cab04  mov     edx, 46h ; 'F'
0x1800cab09  mov     rbx, [rsp+338h+var_2E0]
0x1800cab0e  mov     r9, rbx
0x1800cab11  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800cab18  mov     rcx, [rcx+10h]
0x1800cab1c  call    WPP_SF_q
0x1800cab21  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cab28  jmp     short loc_1800CAB2F
0x1800cab2a  mov     rbx, [rsp+338h+var_2E0]
0x1800cab2f  cmp     rcx, r14
0x1800cab32  jz      short loc_1800CAB64
0x1800cab34  test    dword ptr [rcx+1Ch], 800000h
0x1800cab3b  jz      short loc_1800CAB64
0x1800cab3d  cmp     byte ptr [rcx+19h], 4
0x1800cab41  jb      short loc_1800CAB64
0x1800cab43  mov     edx, 47h ; 'G'
0x1800cab48  mov     r9, [rsp+338h+pv]
0x1800cab4d  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800cab54  mov     rcx, [rcx+10h]
0x1800cab58  call    WPP_SF_S
0x1800cab5d  jmp     short loc_1800CAB64
0x1800cab5f  mov     rbx, [rsp+338h+var_2E0]
0x1800cab64  mov     r8, [rsp+338h+pv]
0x1800cab69  lea     rdx, [rsp+338h+var_2B8]
0x1800cab71  mov     rcx, r13
0x1800cab74  call    ?FindMonitor@CMonitorManager@@AEAA?AV?$CComPtr@VCaptureMonitor@CMonitorManager@@@ATL@@PEBG@Z; CMonitorManager::FindMonitor(ushort const *)
0x1800cab79  nop
0x1800cab7a  mov     rax, [rsp+338h+var_2B8]
0x1800cab82  test    rax, rax
0x1800cab85  jnz     loc_1800CAEC8
0x1800cab8b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cab92  cmp     rcx, r14
0x1800cab95  jz      short loc_1800CABBE
0x1800cab97  test    dword ptr [rcx+1Ch], 800000h
0x1800cab9e  jz      short loc_1800CABBE
0x1800caba0  cmp     byte ptr [rcx+19h], 4
0x1800caba4  jb      short loc_1800CABBE
0x1800caba6  lea     edx, [rax+48h]
0x1800caba9  mov     r9, [rsp+338h+pv]
0x1800cabae  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800cabb5  mov     rcx, [rcx+10h]
0x1800cabb9  call    WPP_SF_S
0x1800cabbe  mov     r15d, edi
0x1800cabc1  lea     rcx, [r13+70h]
0x1800cabc5  mov     rdx, rbx
0x1800cabc8  call    ?AddTail@?$CAtlList@V?$CComQIPtr@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@ATL@@V?$CComQIPtrElementTraits@VCaptureMonitor@CMonitorManager@@$1?IID_IUnknown@@3U_GUID@@B@2@@ATL@@QEAAPEAU__POSITION@@PEAVCaptureMonitor@CMonitorManager@@@Z; ATL::CAtlList<ATL::CComQIPtr<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>,ATL::CComQIPtrElementTraits<CMonitorManager::CaptureMonitor,&_GUID const IID_IUnknown>>::AddTail(CMonitorManager::CaptureMonitor *)
0x1800cabcd  nop
0x1800cabce  jmp     short loc_1800CABEC
0x1800cabd0  mov     r15d, dword ptr [rsp+338h+var_2E8]
0x1800cabd5  xor     edi, edi
0x1800cabd7  lea     r14, WPP_GLOBAL_Control
0x1800cabde  test    r15d, r15d
0x1800cabe1  js      loc_1800CAF52
0x1800cabe7  mov     rbx, [rsp+338h+var_2E0]
0x1800cabec  mov     rcx, cs:WPP_GLOBAL_Control
0x1800cabf3  cmp     rcx, r14
0x1800cabf6  jz      short loc_1800CAC21
0x1800cabf8  test    dword ptr [rcx+1Ch], 800000h
0x1800cabff  jz      short loc_1800CAC21
0x1800cac01  cmp     byte ptr [rcx+19h], 4
0x1800cac05  jb      short loc_1800CAC21
0x1800cac07  mov     edx, 49h ; 'I'
0x1800cac0c  mov     r9, [rsp+338h+var_2D8]
0x1800cac11  lea     r8, WPP_72c9fd82aa603dc17c55ee7407a1fef9_Traceguids
0x1800cac18  mov     rcx, [rcx+10h]
0x1800cac1c  call    WPP_SF_S
0x1800cac21  xor     edx, edx; Val
0x1800cac23  mov     r8d, 206h; Size
0x1800cac29  lea     rcx, [rsp+338h+var_246]; void *
0x1800cac31  call    memset_0
0x1800cac36  mov     [rsp+338h+var_2E8], rdi
0x1800cac3b  mov     [rsp+338h+Buffer], di
0x1800cac43  lea     rcx, aAudiosrvDll_1; "AudioSrv.dll"
0x1800cac4a  call    cs:__imp_GetModuleHandleW
0x1800cac50  test    rax, rax
0x1800cac53  jz      loc_1800CAE97
0x1800cac59  mov     r9d, 104h; cchBufferMax
0x1800cac5f  lea     r8, [rsp+338h+Buffer]; lpBuffer
0x1800cac67  mov     edx, 1F4h; uID
0x1800cac6c  mov     rcx, rax; hInstance
0x1800cac6f  call    cs:__imp_LoadStringW
0x1800cac75  test    eax, eax
0x1800cac77  jle     loc_1800CAE97
0x1800cac7d  mov     [rsp+338h+var_2C0], rdi
0x1800cac82  lea     r9, [rsp+338h+string]; string
0x1800cac8a  lea     r8, [rsp+338h+hstringHeader]; hstringHeader
0x1800cac92  mov     edx, 40h ; '@'; length
0x1800cac97  lea     rcx, ?RuntimeClass_Windows_Security_Authorization_AppCapabilityAccess_AppCapability@@3QBGB; "Windows.Security.Authorization.AppCapab"...
0x1800cac9e  call    cs:__imp_WindowsCreateStringReference
0x1800caca4  test    eax, eax
0x1800caca6  jns     short loc_1800CACBD
0x1800caca8  xor     r9d, r9d; lpArguments
0x1800cacab  xor     r8d, r8d; nNumberOfArguments
0x1800cacae  lea     edx, [r9+1]; dwExceptionFlags
0x1800cacb2  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800cacb7  call    cs:__imp_RaiseException
0x1800cacbd  lea     r8, [rsp+338h+var_2C0]
0x1800cacc2  lea     rdx, _GUID_7c353e2a_46ee_44e5_af3d_6ad3fc49bd22
0x1800cacc9  mov     rcx, [rsp+338h+string]
0x1800cacd1  call    cs:__imp_RoGetActivationFactory
0x1800cacd7  mov     r12d, eax
0x1800cacda  test    eax, eax
0x1800cacdc  jns     loc_1800CAD6D
0x1800cace2  mov     rcx, [rsp+338h]; this
0x1800cacea  mov     r9d, eax; char *
0x1800caced  lea     r8, aAvcoreAudiocor; "avcore\\audiocore\\capturemonitor\\moni"...
0x1800cacf4  mov     edx, 988h; void *
0x1800cacf9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800cacfe  nop
0x1800cacff  lea     rcx, [rsp+338h+var_2C0]
0x1800cad04  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x1800cad09  nop
0x1800cad0a  lea     rcx, [rsp+338h+var_2E8]
0x1800cad0f  call    ??1?$com_ptr_t@UIAudioPumpDspResourceTrackerToken@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>::~com_ptr_t<IAudioPumpDspResourceTrackerToken,wil::err_returncode_policy>(void)
0x1800cad14  nop
0x1800cad15  lea     rcx, [rsp+338h+var_2B8]
0x1800cad1d  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800cad22  nop
0x1800cad23  lea     rcx, [rsp+338h+var_290]; this
0x1800cad2b  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800cad30  nop
0x1800cad31  lea     rcx, [rsp+338h+var_2E0]
0x1800cad36  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1800cad3b  nop
0x1800cad3c  mov     rcx, [rsp+338h+pv]; pv
0x1800cad41  call    cs:__imp_CoTaskMemFree
0x1800cad47  mov     [rsp+338h+pv], rdi
0x1800cad4c  lea     rcx, [rsp+338h+var_2A0]; this
0x1800cad54  call    ??1CCritSecLock@ATL@@QEAA@XZ; ATL::CCritSecLock::~CCritSecLock(void)
0x1800cad59  nop
0x1800cad5a  mov     rcx, [rsp+338h+var_2D8]; pv
0x1800cad5f  call    cs:__imp_CoTaskMemFree
0x1800cad65  mov     edi, r12d
0x1800cad68  jmp     loc_1800CA9E6
0x1800cad6d  mov     [rsp+338h+var_2C8], rdi
0x1800cad72  mov     rax, [rsp+338h+var_2C0]
0x1800cad77  mov     [rsp+338h+var_280], rax
0x1800cad7f  mov     rax, [rax]
0x1800cad82  mov     rax, [rax+40h]
0x1800cad86  mov     [rsp+338h+var_278], rax
  ... truncated ...
```
