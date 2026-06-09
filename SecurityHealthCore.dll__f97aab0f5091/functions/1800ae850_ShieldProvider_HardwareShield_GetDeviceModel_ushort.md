# ShieldProvider::HardwareShield::GetDeviceModel(ushort * *)

- ea: `0x1800ae850`
- end: `0x1800aeda9`
- name: `?GetDeviceModel@HardwareShield@ShieldProvider@@UEAAJPEAPEAG@Z`
- size: `1369`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800aedb0`
- `0x1800aedc0`

## callees

- `0x18000ccb0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180058070`
- `0x180063188`
- `0x1800ae850`
- `0x1800e1764`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800aea65`
- `ole32!CoSetProxyBlanket` at `0x1800aea65`
- `ole32!CoCreateInstance` at `0x1800ae948`
- `ole32!CoCreateInstance` at `0x1800ae948`
- `ole32!CoTaskMemFree` at `0x1800ae91c`
- `ole32!CoTaskMemFree` at `0x1800aec0b`
- `ole32!CoTaskMemFree` at `0x1800aec68`
- `ole32!CoTaskMemFree` at `0x1800aed7d`
- `ole32!CoTaskMemFree` at `0x1800ae91c`
- `ole32!CoTaskMemFree` at `0x1800aec0b`
- `ole32!CoTaskMemFree` at `0x1800aec68`
- `ole32!CoTaskMemFree` at `0x1800aed7d`
- `OLEAUT32!__imp_VariantClear` at `0x1800aecd0`
- `OLEAUT32!__imp_VariantClear` at `0x1800aed46`
- `OLEAUT32!__imp_VariantClear` at `0x1800aecd0`
- `OLEAUT32!__imp_VariantClear` at `0x1800aed46`

## string_xrefs

- `0x1800aeaa6`: `SELECT * FROM Win32_ComputerSystem`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::GetDeviceModel(ShieldProvider::HardwareShield *this, LPVOID *a2)
{
  int v3; // eax
  unsigned __int16 *v4; // r8
  int v5; // ebx
  int v6; // eax
  HRESULT v7; // eax
  LPVOID v8; // rbx
  __int64 (__fastcall *v9)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // rsi
  _bstr_t *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HRESULT v15; // eax
  IUnknown *v16; // rsi
  ULONG (__stdcall *Release)(IUnknown *); // r15
  _bstr_t *v18; // rax
  __int64 v19; // rbx
  _bstr_t *v20; // rax
  __int64 v21; // rdx
  int v22; // eax
  int v23; // eax
  unsigned __int16 *v24; // r8
  int v25; // eax
  int v26; // esi
  void *v27; // rbx
  IUnknown *pProxy; // [rsp+50h] [rbp-19h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-11h] BYREF
  __int64 v31; // [rsp+60h] [rbp-9h] BYREF
  __int64 v32; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v33[8]; // [rsp+70h] [rbp+7h] BYREF
  __int64 v34; // [rsp+78h] [rbp+Fh] BYREF
  VARIANTARG pvarg; // [rsp+80h] [rbp+17h] BYREF
  _BYTE v36[40]; // [rsp+98h] [rbp+2Fh] BYREF
  int v37; // [rsp+E0h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+E8h] [rbp+7Fh] BYREF

  v34 = 0;
  v3 = CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(&v34);
  v5 = v3;
  if ( v3 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        479,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v3);
    goto LABEL_69;
  }
  *a2 = 0;
  pv = 0;
  v6 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&pv, (unsigned __int16 **)L"Unknown", v4);
  v5 = v6;
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        480,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v6);
    goto LABEL_9;
  }
  ppv = 0;
  v7 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v5 = v7;
  if ( v7 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        481,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v7);
    goto LABEL_15;
  }
  pProxy = 0;
  v8 = ppv;
  v9 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL);
  v10 = _bstr_t::_bstr_t((_bstr_t *)v33, L"\\\\.\\root\\cimv2");
  if ( *(_QWORD *)v10 )
    v11 = **(_QWORD **)v10;
  else
    v11 = 0;
  v5 = v9(v8, v11, 0, 0, 0, 0, 0, 0, &pProxy);
  _bstr_t::_Free((_bstr_t *)v33);
  if ( v5 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v13 = 482;
    v14 = (unsigned int)v5;
    goto LABEL_23;
  }
  v15 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  v5 = v15;
  if ( v15 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_24;
    v13 = 483;
    v14 = (unsigned int)v15;
LABEL_23:
    WPP_SF_d(v12[2], v13, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, v14);
LABEL_24:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
LABEL_15:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
LABEL_9:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_69;
  }
  v31 = 0;
  v16 = pProxy;
  Release = pProxy->lpVtbl[6].Release;
  v18 = _bstr_t::_bstr_t((_bstr_t *)v36, L"SELECT * FROM Win32_ComputerSystem");
  if ( *(_QWORD *)v18 )
    v19 = **(_QWORD **)v18;
  else
    v19 = 0;
  v20 = _bstr_t::_bstr_t((_bstr_t *)v33, L"WQL");
  if ( *(_QWORD *)v20 )
    v21 = **(_QWORD **)v20;
  else
    v21 = 0;
  v5 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, __int64 *))Release)(
         v16,
         v21,
         v19,
         48,
         0,
         &v31);
  _bstr_t::_Free((_bstr_t *)v33);
  _bstr_t::_Free((_bstr_t *)v36);
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        484,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v5);
LABEL_39:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v31);
    goto LABEL_24;
  }
  v32 = 0;
  v37 = 0;
  v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v31 + 32LL))(
          v31,
          0xFFFFFFFFLL,
          1,
          &v32,
          &v37);
  v5 = v22;
  if ( v22 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        485,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v22);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v32);
    goto LABEL_39;
  }
  if ( v37 != 1 )
  {
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v32);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v31);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
    if ( pv )
      CoTaskMemFree(pv);
    v5 = -2147019873;
    goto LABEL_69;
  }
  pvarg.vt = 0;
  v23 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v32 + 32LL))(
          v32,
          L"Model",
          0,
          &pvarg,
          0,
          0);
  if ( v23 >= 0 && pvarg.vt == 8 )
  {
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v25 = CommonUtil::UtilCoDuplicateString((CommonUtil *)&pv, pvarg.pbstrVal, v24);
    v26 = v25;
    v27 = 0;
    *a2 = pv;
    if ( v25 < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          486,
          &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
          (unsigned int)v25);
      if ( pvarg.vt )
        VariantClear(&pvarg);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v32);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v31);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
      CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
      v5 = v26;
      goto LABEL_69;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        487,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v23);
    v27 = pv;
  }
  if ( pvarg.vt )
    VariantClear(&pvarg);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v32);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v31);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
  if ( v27 )
    CoTaskMemFree(v27);
  v5 = 0;
LABEL_69:
  CommonUtil::AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>::~AutoRef<WSD::HealthAdvisor::AssessmentQueueItem>(&v34);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x1800ae850  mov     [rsp-8+arg_0], rbx
0x1800ae855  push    rbp
0x1800ae856  push    rsi
0x1800ae857  push    r12
0x1800ae859  push    r14
0x1800ae85b  push    r15
0x1800ae85d  lea     rbp, [rsp-37h]
0x1800ae862  sub     rsp, 0A0h
0x1800ae869  mov     r14, rdx
0x1800ae86c  xor     r12d, r12d
0x1800ae86f  mov     [rbp+57h+var_48], r12
0x1800ae873  lea     rcx, [rbp+57h+var_48]
0x1800ae877  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800ae87c  mov     ebx, eax
0x1800ae87e  test    eax, eax
0x1800ae880  jns     short loc_1800AE8C0
0x1800ae882  lea     rdx, WPP_GLOBAL_Control
0x1800ae889  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae890  cmp     rcx, rdx
0x1800ae893  jz      loc_1800AED86
0x1800ae899  test    byte ptr [rcx+1Ch], 1
0x1800ae89d  jz      loc_1800AED86
0x1800ae8a3  mov     edx, 1DFh
0x1800ae8a8  mov     r9d, eax
0x1800ae8ab  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae8b2  mov     rcx, [rcx+10h]
0x1800ae8b6  call    WPP_SF_d
0x1800ae8bb  jmp     loc_1800AED86
0x1800ae8c0  mov     [r14], r12
0x1800ae8c3  mov     [rbp+57h+pv], r12
0x1800ae8c7  lea     rdx, aUnknown_1; "Unknown"
0x1800ae8ce  lea     rcx, [rbp+57h+pv]; this
0x1800ae8d2  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800ae8d7  mov     ebx, eax
0x1800ae8d9  test    eax, eax
0x1800ae8db  jns     short loc_1800AE927
0x1800ae8dd  lea     rdx, WPP_GLOBAL_Control
0x1800ae8e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae8eb  cmp     rcx, rdx
0x1800ae8ee  jz      short loc_1800AE90F
0x1800ae8f0  test    byte ptr [rcx+1Ch], 1
0x1800ae8f4  jz      short loc_1800AE90F
0x1800ae8f6  mov     edx, 1E0h
0x1800ae8fb  mov     r9d, eax
0x1800ae8fe  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae905  mov     rcx, [rcx+10h]
0x1800ae909  call    WPP_SF_d
0x1800ae90e  nop
0x1800ae90f  mov     rcx, [rbp+57h+pv]; pv
0x1800ae913  test    rcx, rcx
0x1800ae916  jz      loc_1800AED86
0x1800ae91c  call    cs:__imp_CoTaskMemFree
0x1800ae922  jmp     loc_1800AED86
0x1800ae927  mov     [rbp+57h+var_68], r12
0x1800ae92b  lea     rax, [rbp+57h+var_68]
0x1800ae92f  mov     [rsp+0C0h+ppv], rax; ppv
0x1800ae934  lea     r9, IID_IWbemLocator; riid
0x1800ae93b  xor     edx, edx; pUnkOuter
0x1800ae93d  lea     r8d, [rdx+1]; dwClsContext
0x1800ae941  lea     rcx, CLSID_WbemLocator; rclsid
0x1800ae948  call    cs:__imp_CoCreateInstance
0x1800ae94e  mov     ebx, eax
0x1800ae950  test    eax, eax
0x1800ae952  jns     short loc_1800AE994
0x1800ae954  lea     rdx, WPP_GLOBAL_Control
0x1800ae95b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae962  cmp     rcx, rdx
0x1800ae965  jz      short loc_1800AE986
0x1800ae967  test    byte ptr [rcx+1Ch], 1
0x1800ae96b  jz      short loc_1800AE986
0x1800ae96d  mov     edx, 1E1h
0x1800ae972  mov     r9d, eax
0x1800ae975  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae97c  mov     rcx, [rcx+10h]
0x1800ae980  call    WPP_SF_d
0x1800ae985  nop
0x1800ae986  lea     rcx, [rbp+57h+var_68]
0x1800ae98a  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae98f  jmp     loc_1800AE90F
0x1800ae994  mov     [rbp+57h+pProxy], r12
0x1800ae998  mov     rbx, [rbp+57h+var_68]
0x1800ae99c  mov     rax, [rbx]
0x1800ae99f  mov     rsi, [rax+18h]
0x1800ae9a3  lea     rdx, aRootCimv2_0; "\\\\.\\root\\cimv2"
0x1800ae9aa  lea     rcx, [rbp+57h+var_50]; this
0x1800ae9ae  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800ae9b3  nop
0x1800ae9b4  mov     rcx, [rax]
0x1800ae9b7  test    rcx, rcx
0x1800ae9ba  jz      short loc_1800AE9C1
0x1800ae9bc  mov     rdx, [rcx]
0x1800ae9bf  jmp     short loc_1800AE9C4
0x1800ae9c1  mov     rdx, r12
0x1800ae9c4  lea     rax, [rbp+57h+pProxy]
0x1800ae9c8  mov     [rsp+0C0h+var_80], rax
0x1800ae9cd  mov     qword ptr [rsp+0C0h+dwCapabilities], r12
0x1800ae9d2  mov     [rsp+0C0h+pAuthInfo], r12
0x1800ae9d7  mov     [rsp+0C0h+dwImpLevel], r12d
0x1800ae9dc  mov     [rsp+0C0h+ppv], r12
0x1800ae9e1  xor     r9d, r9d
0x1800ae9e4  xor     r8d, r8d
0x1800ae9e7  mov     rcx, rbx
0x1800ae9ea  mov     rax, rsi
0x1800ae9ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae9f2  mov     ebx, eax
0x1800ae9f4  lea     rcx, [rbp+57h+var_50]; this
0x1800ae9f8  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800ae9fd  test    ebx, ebx
0x1800ae9ff  jns     short loc_1800AEA41
0x1800aea01  lea     rdx, WPP_GLOBAL_Control
0x1800aea08  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aea0f  cmp     rcx, rdx
0x1800aea12  jz      short loc_1800AEA33
0x1800aea14  test    byte ptr [rcx+1Ch], 1
0x1800aea18  jz      short loc_1800AEA33
0x1800aea1a  mov     edx, 1E2h
0x1800aea1f  mov     r9d, ebx
0x1800aea22  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aea29  mov     rcx, [rcx+10h]
0x1800aea2d  call    WPP_SF_d
0x1800aea32  nop
0x1800aea33  lea     rcx, [rbp+57h+pProxy]
0x1800aea37  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aea3c  jmp     loc_1800AE986
0x1800aea41  mov     [rsp+0C0h+dwCapabilities], r12d; dwCapabilities
0x1800aea46  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x1800aea4b  mov     eax, 3
0x1800aea50  mov     [rsp+0C0h+dwImpLevel], eax; dwImpLevel
0x1800aea54  mov     dword ptr [rsp+0C0h+ppv], eax; dwAuthnLevel
0x1800aea58  xor     r9d, r9d; pServerPrincName
0x1800aea5b  xor     r8d, r8d; dwAuthzSvc
0x1800aea5e  lea     edx, [rax+7]; dwAuthnSvc
0x1800aea61  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800aea65  call    cs:__imp_CoSetProxyBlanket
0x1800aea6b  mov     ebx, eax
0x1800aea6d  test    eax, eax
0x1800aea6f  jns     short loc_1800AEA94
0x1800aea71  lea     rdx, WPP_GLOBAL_Control
0x1800aea78  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aea7f  cmp     rcx, rdx
0x1800aea82  jz      short loc_1800AEA33
0x1800aea84  test    byte ptr [rcx+1Ch], 1
0x1800aea88  jz      short loc_1800AEA33
0x1800aea8a  mov     edx, 1E3h
0x1800aea8f  mov     r9d, eax
0x1800aea92  jmp     short loc_1800AEA22
0x1800aea94  mov     [rbp+57h+var_60], r12
0x1800aea98  mov     rsi, [rbp+57h+pProxy]
0x1800aea9c  mov     rax, [rsi]
0x1800aea9f  mov     r15, [rax+0A0h]
0x1800aeaa6  lea     rdx, aSelectFromWin3_0; "SELECT * FROM Win32_ComputerSystem"
0x1800aeaad  lea     rcx, [rbp+57h+var_28]; this
0x1800aeab1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800aeab6  nop
0x1800aeab7  mov     rcx, [rax]
0x1800aeaba  test    rcx, rcx
0x1800aeabd  jz      short loc_1800AEAC4
0x1800aeabf  mov     rbx, [rcx]
0x1800aeac2  jmp     short loc_1800AEAC7
0x1800aeac4  mov     rbx, r12
0x1800aeac7  lea     rdx, aWql; "WQL"
0x1800aeace  lea     rcx, [rbp+57h+var_50]; this
0x1800aead2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800aead7  nop
0x1800aead8  mov     rcx, [rax]
0x1800aeadb  test    rcx, rcx
0x1800aeade  jz      short loc_1800AEAE5
0x1800aeae0  mov     rdx, [rcx]
0x1800aeae3  jmp     short loc_1800AEAE8
0x1800aeae5  mov     rdx, r12
0x1800aeae8  lea     rax, [rbp+57h+var_60]
0x1800aeaec  mov     qword ptr [rsp+0C0h+dwImpLevel], rax
0x1800aeaf1  mov     [rsp+0C0h+ppv], r12
0x1800aeaf6  mov     r9d, 30h ; '0'
0x1800aeafc  mov     r8, rbx
0x1800aeaff  mov     rcx, rsi
0x1800aeb02  mov     rax, r15
0x1800aeb05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb0a  mov     ebx, eax
0x1800aeb0c  lea     rcx, [rbp+57h+var_50]; this
0x1800aeb10  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800aeb15  nop
0x1800aeb16  lea     rcx, [rbp+57h+var_28]; this
0x1800aeb1a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800aeb1f  test    ebx, ebx
0x1800aeb21  jns     short loc_1800AEB63
0x1800aeb23  lea     rdx, WPP_GLOBAL_Control
0x1800aeb2a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeb31  cmp     rcx, rdx
0x1800aeb34  jz      short loc_1800AEB55
0x1800aeb36  test    byte ptr [rcx+1Ch], 1
0x1800aeb3a  jz      short loc_1800AEB55
0x1800aeb3c  mov     edx, 1E4h
0x1800aeb41  mov     r9d, ebx
0x1800aeb44  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aeb4b  mov     rcx, [rcx+10h]
0x1800aeb4f  call    WPP_SF_d
0x1800aeb54  nop
0x1800aeb55  lea     rcx, [rbp+57h+var_60]
0x1800aeb59  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aeb5e  jmp     loc_1800AEA33
0x1800aeb63  mov     [rbp+57h+var_58], r12
0x1800aeb67  mov     [rbp+57h+arg_10], r12d
0x1800aeb6b  mov     rcx, [rbp+57h+var_60]
0x1800aeb6f  mov     rax, [rcx]
0x1800aeb72  lea     rdx, [rbp+57h+arg_10]
0x1800aeb76  mov     [rsp+0C0h+ppv], rdx
0x1800aeb7b  lea     r9, [rbp+57h+var_58]
0x1800aeb7f  mov     r8d, 1
0x1800aeb85  or      edx, 0FFFFFFFFh
0x1800aeb88  mov     rax, [rax+20h]
0x1800aeb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb91  mov     ebx, eax
0x1800aeb93  test    eax, eax
0x1800aeb95  jns     short loc_1800AEBD4
0x1800aeb97  lea     rdx, WPP_GLOBAL_Control
0x1800aeb9e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeba5  cmp     rcx, rdx
0x1800aeba8  jz      short loc_1800AEBC9
0x1800aebaa  test    byte ptr [rcx+1Ch], 1
0x1800aebae  jz      short loc_1800AEBC9
0x1800aebb0  mov     edx, 1E5h
0x1800aebb5  mov     r9d, eax
0x1800aebb8  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aebbf  mov     rcx, [rcx+10h]
0x1800aebc3  call    WPP_SF_d
0x1800aebc8  nop
0x1800aebc9  lea     rcx, [rbp+57h+var_58]
0x1800aebcd  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aebd2  jmp     short loc_1800AEB55
0x1800aebd4  cmp     [rbp+57h+arg_10], 1
0x1800aebd8  jz      short loc_1800AEC1B
0x1800aebda  lea     rcx, [rbp+57h+var_58]
0x1800aebde  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aebe3  nop
0x1800aebe4  lea     rcx, [rbp+57h+var_60]
0x1800aebe8  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aebed  nop
0x1800aebee  lea     rcx, [rbp+57h+pProxy]
0x1800aebf2  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aebf7  nop
0x1800aebf8  lea     rcx, [rbp+57h+var_68]
0x1800aebfc  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aec01  nop
0x1800aec02  mov     rcx, [rbp+57h+pv]; pv
0x1800aec06  test    rcx, rcx
0x1800aec09  jz      short loc_1800AEC11
0x1800aec0b  call    cs:__imp_CoTaskMemFree
0x1800aec11  mov     ebx, 8007139Fh
0x1800aec16  jmp     loc_1800AED86
0x1800aec1b  mov     word ptr [rbp+57h+pvarg], r12w
0x1800aec20  mov     rcx, [rbp+57h+var_58]
0x1800aec24  mov     rax, [rcx]
0x1800aec27  mov     qword ptr [rsp+0C0h+dwImpLevel], r12
0x1800aec2c  mov     [rsp+0C0h+ppv], r12
0x1800aec31  lea     r9, [rbp+57h+pvarg]
0x1800aec35  xor     r8d, r8d
0x1800aec38  lea     rdx, aModel; "Model"
0x1800aec3f  mov     rax, [rax+20h]
0x1800aec43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aec48  test    eax, eax
0x1800aec4a  js      loc_1800AED06
0x1800aec50  mov     ecx, 8
0x1800aec55  cmp     cx, word ptr [rbp+57h+pvarg]
0x1800aec59  jnz     loc_1800AED06
0x1800aec5f  mov     rcx, [rbp+57h+pv]; pv
0x1800aec63  test    rcx, rcx
0x1800aec66  jz      short loc_1800AEC72
0x1800aec68  call    cs:__imp_CoTaskMemFree
0x1800aec6e  mov     [rbp+57h+pv], r12
0x1800aec72  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 **
0x1800aec76  lea     rcx, [rbp+57h+pv]; this
0x1800aec7a  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800aec7f  mov     esi, eax
0x1800aec81  mov     rcx, [rbp+57h+pv]
0x1800aec85  mov     rbx, r12
0x1800aec88  mov     [r14], rcx
0x1800aec8b  test    eax, eax
0x1800aec8d  jns     loc_1800AED3B
0x1800aec93  lea     rdx, WPP_GLOBAL_Control
0x1800aec9a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800aeca1  cmp     rcx, rdx
0x1800aeca4  jz      short loc_1800AECC5
0x1800aeca6  test    byte ptr [rcx+1Ch], 1
0x1800aecaa  jz      short loc_1800AECC5
0x1800aecac  mov     edx, 1E6h
0x1800aecb1  mov     r9d, eax
0x1800aecb4  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800aecbb  mov     rcx, [rcx+10h]
0x1800aecbf  call    WPP_SF_d
0x1800aecc4  nop
0x1800aecc5  cmp     word ptr [rbp+57h+pvarg], r12w
0x1800aecca  jz      short loc_1800AECD7
0x1800aeccc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800aecd0  call    cs:__imp_VariantClear
0x1800aecd6  nop
0x1800aecd7  lea     rcx, [rbp+57h+var_58]
0x1800aecdb  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800aece0  nop
0x1800aece1  lea     rcx, [rbp+57h+var_60]
  ... truncated ...
```
