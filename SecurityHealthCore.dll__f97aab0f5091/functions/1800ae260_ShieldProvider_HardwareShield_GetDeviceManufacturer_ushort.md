# ShieldProvider::HardwareShield::GetDeviceManufacturer(ushort * *)

- ea: `0x1800ae260`
- end: `0x1800ae7b9`
- name: `?GetDeviceManufacturer@HardwareShield@ShieldProvider@@UEAAJPEAPEAG@Z`
- size: `1369`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, unsigned __int16 **)`
- caller_count: `9`
- callee_count: `9`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800ae7c0`
- `0x1800ae7d0`
- `0x1800ae7e0`
- `0x1800ae7f0`
- `0x1800ae800`
- `0x1800ae810`
- `0x1800ae820`
- `0x1800ae830`
- `0x1800ae840`

## callees

- `0x18000ccb0`
- `0x18000ccd4`
- `0x18000d7fc`
- `0x180011730`
- `0x180058070`
- `0x180063188`
- `0x1800ae260`
- `0x1800e1764`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800ae475`
- `ole32!CoSetProxyBlanket` at `0x1800ae475`
- `ole32!CoCreateInstance` at `0x1800ae358`
- `ole32!CoCreateInstance` at `0x1800ae358`
- `ole32!CoTaskMemFree` at `0x1800ae32c`
- `ole32!CoTaskMemFree` at `0x1800ae61b`
- `ole32!CoTaskMemFree` at `0x1800ae678`
- `ole32!CoTaskMemFree` at `0x1800ae78d`
- `ole32!CoTaskMemFree` at `0x1800ae32c`
- `ole32!CoTaskMemFree` at `0x1800ae61b`
- `ole32!CoTaskMemFree` at `0x1800ae678`
- `ole32!CoTaskMemFree` at `0x1800ae78d`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae6e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae756`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae6e0`
- `OLEAUT32!__imp_VariantClear` at `0x1800ae756`

## string_xrefs

- `0x1800ae4b6`: `SELECT * FROM Win32_ComputerSystem`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall ShieldProvider::HardwareShield::GetDeviceManufacturer(
        ShieldProvider::HardwareShield *this,
        LPVOID *a2)
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
        470,
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
        471,
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
        472,
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
    v13 = 473;
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
    v13 = 474;
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
        475,
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
        476,
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
          L"Manufacturer",
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
          477,
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
        478,
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
0x1800ae260  mov     [rsp-8+arg_0], rbx
0x1800ae265  push    rbp
0x1800ae266  push    rsi
0x1800ae267  push    r12
0x1800ae269  push    r14
0x1800ae26b  push    r15
0x1800ae26d  lea     rbp, [rsp-37h]
0x1800ae272  sub     rsp, 0A0h
0x1800ae279  mov     r14, rdx
0x1800ae27c  xor     r12d, r12d
0x1800ae27f  mov     [rbp+57h+var_48], r12
0x1800ae283  lea     rcx, [rbp+57h+var_48]
0x1800ae287  call    ??$NewRefInstance@VComClientImpersonator@ShieldProvider@@@CommonUtil@@YAJPEAPEAVComClientImpersonator@ShieldProvider@@@Z; CommonUtil::NewRefInstance<ShieldProvider::ComClientImpersonator>(ShieldProvider::ComClientImpersonator * *)
0x1800ae28c  mov     ebx, eax
0x1800ae28e  test    eax, eax
0x1800ae290  jns     short loc_1800AE2D0
0x1800ae292  lea     rdx, WPP_GLOBAL_Control
0x1800ae299  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae2a0  cmp     rcx, rdx
0x1800ae2a3  jz      loc_1800AE796
0x1800ae2a9  test    byte ptr [rcx+1Ch], 1
0x1800ae2ad  jz      loc_1800AE796
0x1800ae2b3  mov     edx, 1D6h
0x1800ae2b8  mov     r9d, eax
0x1800ae2bb  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae2c2  mov     rcx, [rcx+10h]
0x1800ae2c6  call    WPP_SF_d
0x1800ae2cb  jmp     loc_1800AE796
0x1800ae2d0  mov     [r14], r12
0x1800ae2d3  mov     [rbp+57h+pv], r12
0x1800ae2d7  lea     rdx, aUnknown_1; "Unknown"
0x1800ae2de  lea     rcx, [rbp+57h+pv]; this
0x1800ae2e2  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800ae2e7  mov     ebx, eax
0x1800ae2e9  test    eax, eax
0x1800ae2eb  jns     short loc_1800AE337
0x1800ae2ed  lea     rdx, WPP_GLOBAL_Control
0x1800ae2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae2fb  cmp     rcx, rdx
0x1800ae2fe  jz      short loc_1800AE31F
0x1800ae300  test    byte ptr [rcx+1Ch], 1
0x1800ae304  jz      short loc_1800AE31F
0x1800ae306  mov     edx, 1D7h
0x1800ae30b  mov     r9d, eax
0x1800ae30e  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae315  mov     rcx, [rcx+10h]
0x1800ae319  call    WPP_SF_d
0x1800ae31e  nop
0x1800ae31f  mov     rcx, [rbp+57h+pv]; pv
0x1800ae323  test    rcx, rcx
0x1800ae326  jz      loc_1800AE796
0x1800ae32c  call    cs:__imp_CoTaskMemFree
0x1800ae332  jmp     loc_1800AE796
0x1800ae337  mov     [rbp+57h+var_68], r12
0x1800ae33b  lea     rax, [rbp+57h+var_68]
0x1800ae33f  mov     [rsp+0C0h+ppv], rax; ppv
0x1800ae344  lea     r9, IID_IWbemLocator; riid
0x1800ae34b  xor     edx, edx; pUnkOuter
0x1800ae34d  lea     r8d, [rdx+1]; dwClsContext
0x1800ae351  lea     rcx, CLSID_WbemLocator; rclsid
0x1800ae358  call    cs:__imp_CoCreateInstance
0x1800ae35e  mov     ebx, eax
0x1800ae360  test    eax, eax
0x1800ae362  jns     short loc_1800AE3A4
0x1800ae364  lea     rdx, WPP_GLOBAL_Control
0x1800ae36b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae372  cmp     rcx, rdx
0x1800ae375  jz      short loc_1800AE396
0x1800ae377  test    byte ptr [rcx+1Ch], 1
0x1800ae37b  jz      short loc_1800AE396
0x1800ae37d  mov     edx, 1D8h
0x1800ae382  mov     r9d, eax
0x1800ae385  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae38c  mov     rcx, [rcx+10h]
0x1800ae390  call    WPP_SF_d
0x1800ae395  nop
0x1800ae396  lea     rcx, [rbp+57h+var_68]
0x1800ae39a  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae39f  jmp     loc_1800AE31F
0x1800ae3a4  mov     [rbp+57h+pProxy], r12
0x1800ae3a8  mov     rbx, [rbp+57h+var_68]
0x1800ae3ac  mov     rax, [rbx]
0x1800ae3af  mov     rsi, [rax+18h]
0x1800ae3b3  lea     rdx, aRootCimv2_0; "\\\\.\\root\\cimv2"
0x1800ae3ba  lea     rcx, [rbp+57h+var_50]; this
0x1800ae3be  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800ae3c3  nop
0x1800ae3c4  mov     rcx, [rax]
0x1800ae3c7  test    rcx, rcx
0x1800ae3ca  jz      short loc_1800AE3D1
0x1800ae3cc  mov     rdx, [rcx]
0x1800ae3cf  jmp     short loc_1800AE3D4
0x1800ae3d1  mov     rdx, r12
0x1800ae3d4  lea     rax, [rbp+57h+pProxy]
0x1800ae3d8  mov     [rsp+0C0h+var_80], rax
0x1800ae3dd  mov     qword ptr [rsp+0C0h+dwCapabilities], r12
0x1800ae3e2  mov     [rsp+0C0h+pAuthInfo], r12
0x1800ae3e7  mov     [rsp+0C0h+dwImpLevel], r12d
0x1800ae3ec  mov     [rsp+0C0h+ppv], r12
0x1800ae3f1  xor     r9d, r9d
0x1800ae3f4  xor     r8d, r8d
0x1800ae3f7  mov     rcx, rbx
0x1800ae3fa  mov     rax, rsi
0x1800ae3fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae402  mov     ebx, eax
0x1800ae404  lea     rcx, [rbp+57h+var_50]; this
0x1800ae408  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800ae40d  test    ebx, ebx
0x1800ae40f  jns     short loc_1800AE451
0x1800ae411  lea     rdx, WPP_GLOBAL_Control
0x1800ae418  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae41f  cmp     rcx, rdx
0x1800ae422  jz      short loc_1800AE443
0x1800ae424  test    byte ptr [rcx+1Ch], 1
0x1800ae428  jz      short loc_1800AE443
0x1800ae42a  mov     edx, 1D9h
0x1800ae42f  mov     r9d, ebx
0x1800ae432  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae439  mov     rcx, [rcx+10h]
0x1800ae43d  call    WPP_SF_d
0x1800ae442  nop
0x1800ae443  lea     rcx, [rbp+57h+pProxy]
0x1800ae447  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae44c  jmp     loc_1800AE396
0x1800ae451  mov     [rsp+0C0h+dwCapabilities], r12d; dwCapabilities
0x1800ae456  mov     [rsp+0C0h+pAuthInfo], r12; pAuthInfo
0x1800ae45b  mov     eax, 3
0x1800ae460  mov     [rsp+0C0h+dwImpLevel], eax; dwImpLevel
0x1800ae464  mov     dword ptr [rsp+0C0h+ppv], eax; dwAuthnLevel
0x1800ae468  xor     r9d, r9d; pServerPrincName
0x1800ae46b  xor     r8d, r8d; dwAuthzSvc
0x1800ae46e  lea     edx, [rax+7]; dwAuthnSvc
0x1800ae471  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800ae475  call    cs:__imp_CoSetProxyBlanket
0x1800ae47b  mov     ebx, eax
0x1800ae47d  test    eax, eax
0x1800ae47f  jns     short loc_1800AE4A4
0x1800ae481  lea     rdx, WPP_GLOBAL_Control
0x1800ae488  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae48f  cmp     rcx, rdx
0x1800ae492  jz      short loc_1800AE443
0x1800ae494  test    byte ptr [rcx+1Ch], 1
0x1800ae498  jz      short loc_1800AE443
0x1800ae49a  mov     edx, 1DAh
0x1800ae49f  mov     r9d, eax
0x1800ae4a2  jmp     short loc_1800AE432
0x1800ae4a4  mov     [rbp+57h+var_60], r12
0x1800ae4a8  mov     rsi, [rbp+57h+pProxy]
0x1800ae4ac  mov     rax, [rsi]
0x1800ae4af  mov     r15, [rax+0A0h]
0x1800ae4b6  lea     rdx, aSelectFromWin3_0; "SELECT * FROM Win32_ComputerSystem"
0x1800ae4bd  lea     rcx, [rbp+57h+var_28]; this
0x1800ae4c1  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800ae4c6  nop
0x1800ae4c7  mov     rcx, [rax]
0x1800ae4ca  test    rcx, rcx
0x1800ae4cd  jz      short loc_1800AE4D4
0x1800ae4cf  mov     rbx, [rcx]
0x1800ae4d2  jmp     short loc_1800AE4D7
0x1800ae4d4  mov     rbx, r12
0x1800ae4d7  lea     rdx, aWql; "WQL"
0x1800ae4de  lea     rcx, [rbp+57h+var_50]; this
0x1800ae4e2  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800ae4e7  nop
0x1800ae4e8  mov     rcx, [rax]
0x1800ae4eb  test    rcx, rcx
0x1800ae4ee  jz      short loc_1800AE4F5
0x1800ae4f0  mov     rdx, [rcx]
0x1800ae4f3  jmp     short loc_1800AE4F8
0x1800ae4f5  mov     rdx, r12
0x1800ae4f8  lea     rax, [rbp+57h+var_60]
0x1800ae4fc  mov     qword ptr [rsp+0C0h+dwImpLevel], rax
0x1800ae501  mov     [rsp+0C0h+ppv], r12
0x1800ae506  mov     r9d, 30h ; '0'
0x1800ae50c  mov     r8, rbx
0x1800ae50f  mov     rcx, rsi
0x1800ae512  mov     rax, r15
0x1800ae515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae51a  mov     ebx, eax
0x1800ae51c  lea     rcx, [rbp+57h+var_50]; this
0x1800ae520  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800ae525  nop
0x1800ae526  lea     rcx, [rbp+57h+var_28]; this
0x1800ae52a  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800ae52f  test    ebx, ebx
0x1800ae531  jns     short loc_1800AE573
0x1800ae533  lea     rdx, WPP_GLOBAL_Control
0x1800ae53a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae541  cmp     rcx, rdx
0x1800ae544  jz      short loc_1800AE565
0x1800ae546  test    byte ptr [rcx+1Ch], 1
0x1800ae54a  jz      short loc_1800AE565
0x1800ae54c  mov     edx, 1DBh
0x1800ae551  mov     r9d, ebx
0x1800ae554  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae55b  mov     rcx, [rcx+10h]
0x1800ae55f  call    WPP_SF_d
0x1800ae564  nop
0x1800ae565  lea     rcx, [rbp+57h+var_60]
0x1800ae569  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae56e  jmp     loc_1800AE443
0x1800ae573  mov     [rbp+57h+var_58], r12
0x1800ae577  mov     [rbp+57h+arg_10], r12d
0x1800ae57b  mov     rcx, [rbp+57h+var_60]
0x1800ae57f  mov     rax, [rcx]
0x1800ae582  lea     rdx, [rbp+57h+arg_10]
0x1800ae586  mov     [rsp+0C0h+ppv], rdx
0x1800ae58b  lea     r9, [rbp+57h+var_58]
0x1800ae58f  mov     r8d, 1
0x1800ae595  or      edx, 0FFFFFFFFh
0x1800ae598  mov     rax, [rax+20h]
0x1800ae59c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae5a1  mov     ebx, eax
0x1800ae5a3  test    eax, eax
0x1800ae5a5  jns     short loc_1800AE5E4
0x1800ae5a7  lea     rdx, WPP_GLOBAL_Control
0x1800ae5ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae5b5  cmp     rcx, rdx
0x1800ae5b8  jz      short loc_1800AE5D9
0x1800ae5ba  test    byte ptr [rcx+1Ch], 1
0x1800ae5be  jz      short loc_1800AE5D9
0x1800ae5c0  mov     edx, 1DCh
0x1800ae5c5  mov     r9d, eax
0x1800ae5c8  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae5cf  mov     rcx, [rcx+10h]
0x1800ae5d3  call    WPP_SF_d
0x1800ae5d8  nop
0x1800ae5d9  lea     rcx, [rbp+57h+var_58]
0x1800ae5dd  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae5e2  jmp     short loc_1800AE565
0x1800ae5e4  cmp     [rbp+57h+arg_10], 1
0x1800ae5e8  jz      short loc_1800AE62B
0x1800ae5ea  lea     rcx, [rbp+57h+var_58]
0x1800ae5ee  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae5f3  nop
0x1800ae5f4  lea     rcx, [rbp+57h+var_60]
0x1800ae5f8  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae5fd  nop
0x1800ae5fe  lea     rcx, [rbp+57h+pProxy]
0x1800ae602  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae607  nop
0x1800ae608  lea     rcx, [rbp+57h+var_68]
0x1800ae60c  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae611  nop
0x1800ae612  mov     rcx, [rbp+57h+pv]; pv
0x1800ae616  test    rcx, rcx
0x1800ae619  jz      short loc_1800AE621
0x1800ae61b  call    cs:__imp_CoTaskMemFree
0x1800ae621  mov     ebx, 8007139Fh
0x1800ae626  jmp     loc_1800AE796
0x1800ae62b  mov     word ptr [rbp+57h+pvarg], r12w
0x1800ae630  mov     rcx, [rbp+57h+var_58]
0x1800ae634  mov     rax, [rcx]
0x1800ae637  mov     qword ptr [rsp+0C0h+dwImpLevel], r12
0x1800ae63c  mov     [rsp+0C0h+ppv], r12
0x1800ae641  lea     r9, [rbp+57h+pvarg]
0x1800ae645  xor     r8d, r8d
0x1800ae648  lea     rdx, aManufacturer; "Manufacturer"
0x1800ae64f  mov     rax, [rax+20h]
0x1800ae653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae658  test    eax, eax
0x1800ae65a  js      loc_1800AE716
0x1800ae660  mov     ecx, 8
0x1800ae665  cmp     cx, word ptr [rbp+57h+pvarg]
0x1800ae669  jnz     loc_1800AE716
0x1800ae66f  mov     rcx, [rbp+57h+pv]; pv
0x1800ae673  test    rcx, rcx
0x1800ae676  jz      short loc_1800AE682
0x1800ae678  call    cs:__imp_CoTaskMemFree
0x1800ae67e  mov     [rbp+57h+pv], r12
0x1800ae682  mov     rdx, qword ptr [rbp+57h+pvarg+8]; unsigned __int16 **
0x1800ae686  lea     rcx, [rbp+57h+pv]; this
0x1800ae68a  call    ?UtilCoDuplicateString@CommonUtil@@YAJPEAPEAGPEAG@Z; CommonUtil::UtilCoDuplicateString(ushort * *,ushort *)
0x1800ae68f  mov     esi, eax
0x1800ae691  mov     rcx, [rbp+57h+pv]
0x1800ae695  mov     rbx, r12
0x1800ae698  mov     [r14], rcx
0x1800ae69b  test    eax, eax
0x1800ae69d  jns     loc_1800AE74B
0x1800ae6a3  lea     rdx, WPP_GLOBAL_Control
0x1800ae6aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ae6b1  cmp     rcx, rdx
0x1800ae6b4  jz      short loc_1800AE6D5
0x1800ae6b6  test    byte ptr [rcx+1Ch], 1
0x1800ae6ba  jz      short loc_1800AE6D5
0x1800ae6bc  mov     edx, 1DDh
0x1800ae6c1  mov     r9d, eax
0x1800ae6c4  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800ae6cb  mov     rcx, [rcx+10h]
0x1800ae6cf  call    WPP_SF_d
0x1800ae6d4  nop
0x1800ae6d5  cmp     word ptr [rbp+57h+pvarg], r12w
0x1800ae6da  jz      short loc_1800AE6E7
0x1800ae6dc  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800ae6e0  call    cs:__imp_VariantClear
0x1800ae6e6  nop
0x1800ae6e7  lea     rcx, [rbp+57h+var_58]
0x1800ae6eb  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800ae6f0  nop
0x1800ae6f1  lea     rcx, [rbp+57h+var_60]
  ... truncated ...
```
