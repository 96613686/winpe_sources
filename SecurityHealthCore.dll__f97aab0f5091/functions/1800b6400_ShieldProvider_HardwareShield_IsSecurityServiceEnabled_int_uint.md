# ShieldProvider::HardwareShield::IsSecurityServiceEnabled(int *,uint)

- ea: `0x1800b6400`
- end: `0x1800b6911`
- name: `?IsSecurityServiceEnabled@HardwareShield@ShieldProvider@@AEAAJPEAHI@Z`
- size: `1297`
- prototype: `__int64 __fastcall(ShieldProvider::HardwareShield *__hidden this, int *, unsigned int)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800b2ff0`
- `0x1800b70e0`

## callees

- `0x18000ccb0`
- `0x18000d7fc`
- `0x180058070`
- `0x180063188`
- `0x1800b6400`
- `0x1800e7010`

## import_xrefs

- `ole32!CoSetProxyBlanket` at `0x1800b656a`
- `ole32!CoSetProxyBlanket` at `0x1800b656a`
- `ole32!CoCreateInstance` at `0x1800b6452`
- `ole32!CoCreateInstance` at `0x1800b6452`
- `OLEAUT32!__imp_VariantClear` at `0x1800b681a`
- `OLEAUT32!__imp_VariantClear` at `0x1800b688c`
- `OLEAUT32!__imp_VariantClear` at `0x1800b68c7`
- `OLEAUT32!__imp_VariantClear` at `0x1800b681a`
- `OLEAUT32!__imp_VariantClear` at `0x1800b688c`
- `OLEAUT32!__imp_VariantClear` at `0x1800b68c7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800b6781`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800b6781`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800b67d2`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800b67d2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800b679b`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800b679b`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800b6866`
- `OLEAUT32!__imp_SafeArrayGetElement` at `0x1800b6866`

## string_xrefs

- `0x1800b6712`: `SecurityServicesRunning`

## pseudocode

```c
__int64 __fastcall ShieldProvider::HardwareShield::IsSecurityServiceEnabled(
        ShieldProvider::HardwareShield *this,
        int *a2,
        int a3)
{
  HRESULT v5; // eax
  int v6; // ebx
  LPVOID v7; // rbx
  __int64 (__fastcall *v8)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **); // rdi
  _bstr_t *v9; // rax
  __int64 v10; // rdx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  HRESULT v14; // eax
  IUnknown *v15; // rdi
  ULONG (__stdcall *Release)(IUnknown *); // r14
  _bstr_t *v17; // rax
  __int64 v18; // rbx
  _bstr_t *v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  HRESULT LBound; // eax
  _QWORD *v23; // rcx
  __int64 v24; // rdx
  VARTYPE vt; // ax
  LONG i; // eax
  IUnknown *pProxy; // [rsp+50h] [rbp-29h] BYREF
  __int64 v29; // [rsp+58h] [rbp-21h] BYREF
  __int64 v30; // [rsp+60h] [rbp-19h] BYREF
  LONG plUbound; // [rsp+68h] [rbp-11h] BYREF
  LPVOID ppv; // [rsp+70h] [rbp-9h] BYREF
  VARIANTARG pvarg; // [rsp+78h] [rbp-1h] BYREF
  _DWORD pv[16]; // [rsp+90h] [rbp+17h] BYREF
  ShieldProvider::HardwareShield *rgIndices; // [rsp+E0h] [rbp+67h] BYREF
  int v36; // [rsp+E8h] [rbp+6Fh] BYREF
  LONG plLbound; // [rsp+F8h] [rbp+7Fh] BYREF

  rgIndices = this;
  *a2 = 0;
  ppv = 0;
  v5 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v6 = v5;
  if ( v5 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        252,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v5);
    goto LABEL_53;
  }
  v7 = ppv;
  pProxy = 0;
  v8 = *(__int64 (__fastcall **)(LPVOID, __int64, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL);
  v9 = _bstr_t::_bstr_t((_bstr_t *)&rgIndices, L"\\\\.\\root\\Microsoft\\Windows\\DeviceGuard");
  if ( *(_QWORD *)v9 )
    v10 = **(_QWORD **)v9;
  else
    v10 = 0;
  v6 = v8(v7, v10, 0, 0, 0, 0, 0, 0, &pProxy);
  _bstr_t::_Free((_bstr_t *)&rgIndices);
  if ( v6 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    v12 = 253;
    v13 = (unsigned int)v6;
    goto LABEL_12;
  }
  v14 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  v6 = v14;
  if ( v14 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_52;
    v12 = 254;
    v13 = (unsigned int)v14;
LABEL_12:
    WPP_SF_d(v11[2], v12, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, v13);
LABEL_52:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
    goto LABEL_53;
  }
  v15 = pProxy;
  v29 = 0;
  Release = pProxy->lpVtbl[6].Release;
  v17 = _bstr_t::_bstr_t((_bstr_t *)pv, L"SELECT * FROM Win32_DeviceGuard");
  if ( *(_QWORD *)v17 )
    v18 = **(_QWORD **)v17;
  else
    v18 = 0;
  v19 = _bstr_t::_bstr_t((_bstr_t *)&rgIndices, L"WQL");
  if ( *(_QWORD *)v19 )
    v20 = **(_QWORD **)v19;
  else
    v20 = 0;
  v6 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64, _QWORD, __int64 *))Release)(
         v15,
         v20,
         v18,
         48,
         0,
         &v29);
  _bstr_t::_Free((_bstr_t *)&rgIndices);
  _bstr_t::_Free((_bstr_t *)pv);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        255,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v6);
    goto LABEL_51;
  }
  v30 = 0;
  v36 = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v29 + 32LL))(
          v29,
          0xFFFFFFFFLL,
          1,
          &v30,
          &v36);
  v6 = v21;
  if ( v21 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        256,
        &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids,
        (unsigned int)v21);
LABEL_50:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
LABEL_51:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
    goto LABEL_52;
  }
  if ( v36 != 1 )
  {
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
    v6 = -2147019873;
LABEL_53:
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
    return (unsigned int)v6;
  }
  pvarg.vt = 0;
  plLbound = 0;
  plUbound = 0;
  LBound = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v30 + 32LL))(
             v30,
             L"SecurityServicesRunning",
             0,
             &pvarg,
             0,
             0);
  v6 = LBound;
  if ( LBound < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = 257;
LABEL_47:
      WPP_SF_d(v23[2], v24, &WPP_60a6be03328e3dc19e58859635691dd5_Traceguids, (unsigned int)LBound);
      goto LABEL_48;
    }
    goto LABEL_48;
  }
  vt = pvarg.vt;
  if ( pvarg.vt != 8195 )
    goto LABEL_64;
  if ( SafeArrayGetDim(pvarg.parray) != 1 )
  {
    vt = pvarg.vt;
LABEL_64:
    if ( vt )
      VariantClear(&pvarg);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
    CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
    return 2147549183LL;
  }
  LBound = SafeArrayGetLBound(pvarg.parray, 1u, &plLbound);
  v6 = LBound;
  if ( LBound < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = 258;
      goto LABEL_47;
    }
LABEL_48:
    if ( pvarg.vt )
      VariantClear(&pvarg);
    goto LABEL_50;
  }
  LBound = SafeArrayGetUBound(pvarg.parray, 1u, &plUbound);
  v6 = LBound;
  if ( LBound < 0 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v24 = 259;
      goto LABEL_47;
    }
    goto LABEL_48;
  }
  for ( i = plLbound; ; i = (_DWORD)rgIndices + 1 )
  {
    LODWORD(rgIndices) = i;
    if ( i > plUbound )
      break;
    pv[0] = 0;
    if ( SafeArrayGetElement(pvarg.parray, (LONG *)&rgIndices, pv) >= 0 && pv[0] == a3 )
    {
      *a2 = 1;
      break;
    }
  }
  if ( pvarg.vt )
    VariantClear(&pvarg);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v30);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&v29);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&pProxy);
  CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(&ppv);
  return 0;
}

```

## disassembly

```asm
0x1800b6400  mov     [rsp-8+arg_10], rbx
0x1800b6405  mov     [rsp-8+rgIndices], rcx
0x1800b640a  push    rbp
0x1800b640b  push    rsi
0x1800b640c  push    rdi
0x1800b640d  push    r12
0x1800b640f  push    r13
0x1800b6411  push    r14
0x1800b6413  push    r15
0x1800b6415  lea     rbp, [rsp-27h]
0x1800b641a  sub     rsp, 0A0h
0x1800b6421  xor     r12d, r12d
0x1800b6424  lea     rax, [rbp+57h+var_60]
0x1800b6428  mov     r15d, r8d
0x1800b642b  mov     [rdx], r12d
0x1800b642e  mov     rsi, rdx
0x1800b6431  mov     [rbp+57h+var_60], r12
0x1800b6435  lea     r9, IID_IWbemLocator; riid
0x1800b643c  mov     [rsp+0D0h+ppv], rax; ppv
0x1800b6441  lea     r13d, [r12+1]
0x1800b6446  xor     edx, edx; pUnkOuter
0x1800b6448  mov     r8d, r13d; dwClsContext
0x1800b644b  lea     rcx, CLSID_WbemLocator; rclsid
0x1800b6452  call    cs:__imp_CoCreateInstance
0x1800b6458  mov     ebx, eax
0x1800b645a  test    eax, eax
0x1800b645c  jns     short loc_1800B649C
0x1800b645e  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6465  lea     rdx, WPP_GLOBAL_Control
0x1800b646c  cmp     rcx, rdx
0x1800b646f  jz      loc_1800B683B
0x1800b6475  test    [rcx+1Ch], r13b
0x1800b6479  jz      loc_1800B683B
0x1800b647f  mov     rcx, [rcx+10h]
0x1800b6483  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b648a  mov     edx, 0FCh
0x1800b648f  mov     r9d, eax
0x1800b6492  call    WPP_SF_d
0x1800b6497  jmp     loc_1800B683B
0x1800b649c  mov     rbx, [rbp+57h+var_60]
0x1800b64a0  lea     rdx, aRootMicrosoftW; "\\\\.\\root\\Microsoft\\Windows\\Device"...
0x1800b64a7  mov     [rbp+57h+pProxy], r12
0x1800b64ab  lea     rcx, [rbp+57h+rgIndices]; this
0x1800b64af  mov     rax, [rbx]
0x1800b64b2  mov     rdi, [rax+18h]
0x1800b64b6  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800b64bb  mov     rcx, [rax]
0x1800b64be  test    rcx, rcx
0x1800b64c1  jz      short loc_1800B64C8
0x1800b64c3  mov     rdx, [rcx]
0x1800b64c6  jmp     short loc_1800B64CB
0x1800b64c8  mov     rdx, r12
0x1800b64cb  lea     rax, [rbp+57h+pProxy]
0x1800b64cf  xor     r9d, r9d
0x1800b64d2  mov     [rsp+0D0h+var_90], rax
0x1800b64d7  xor     r8d, r8d
0x1800b64da  mov     qword ptr [rsp+0D0h+dwCapabilities], r12
0x1800b64df  mov     rcx, rbx
0x1800b64e2  mov     [rsp+0D0h+pAuthInfo], r12
0x1800b64e7  mov     rax, rdi
0x1800b64ea  mov     [rsp+0D0h+dwImpLevel], r12d
0x1800b64ef  mov     [rsp+0D0h+ppv], r12
0x1800b64f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b64f9  lea     rcx, [rbp+57h+rgIndices]; this
0x1800b64fd  mov     ebx, eax
0x1800b64ff  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800b6504  test    ebx, ebx
0x1800b6506  jns     short loc_1800B6546
0x1800b6508  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b650f  lea     rdx, WPP_GLOBAL_Control
0x1800b6516  cmp     rcx, rdx
0x1800b6519  jz      loc_1800B6832
0x1800b651f  test    [rcx+1Ch], r13b
0x1800b6523  jz      loc_1800B6832
0x1800b6529  mov     edx, 0FDh
0x1800b652e  mov     r9d, ebx
0x1800b6531  mov     rcx, [rcx+10h]
0x1800b6535  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b653c  call    WPP_SF_d
0x1800b6541  jmp     loc_1800B6832
0x1800b6546  mov     rcx, [rbp+57h+pProxy]; pProxy
0x1800b654a  mov     eax, 3
0x1800b654f  mov     [rsp+0D0h+dwCapabilities], r12d; dwCapabilities
0x1800b6554  xor     r9d, r9d; pServerPrincName
0x1800b6557  mov     [rsp+0D0h+pAuthInfo], r12; pAuthInfo
0x1800b655c  xor     r8d, r8d; dwAuthzSvc
0x1800b655f  mov     [rsp+0D0h+dwImpLevel], eax; dwImpLevel
0x1800b6563  lea     edx, [rax+7]; dwAuthnSvc
0x1800b6566  mov     dword ptr [rsp+0D0h+ppv], eax; dwAuthnLevel
0x1800b656a  call    cs:__imp_CoSetProxyBlanket
0x1800b6570  mov     ebx, eax
0x1800b6572  test    eax, eax
0x1800b6574  jns     short loc_1800B65A1
0x1800b6576  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b657d  lea     rdx, WPP_GLOBAL_Control
0x1800b6584  cmp     rcx, rdx
0x1800b6587  jz      loc_1800B6832
0x1800b658d  test    [rcx+1Ch], r13b
0x1800b6591  jz      loc_1800B6832
0x1800b6597  mov     edx, 0FEh
0x1800b659c  mov     r9d, eax
0x1800b659f  jmp     short loc_1800B6531
0x1800b65a1  mov     rdi, [rbp+57h+pProxy]
0x1800b65a5  lea     rdx, aSelectFromWin3; "SELECT * FROM Win32_DeviceGuard"
0x1800b65ac  mov     [rbp+57h+var_78], r12
0x1800b65b0  lea     rcx, [rbp+57h+pv]; this
0x1800b65b4  mov     rax, [rdi]
0x1800b65b7  mov     r14, [rax+0A0h]
0x1800b65be  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800b65c3  mov     rcx, [rax]
0x1800b65c6  test    rcx, rcx
0x1800b65c9  jz      short loc_1800B65D0
0x1800b65cb  mov     rbx, [rcx]
0x1800b65ce  jmp     short loc_1800B65D3
0x1800b65d0  mov     rbx, r12
0x1800b65d3  lea     rdx, aWql; "WQL"
0x1800b65da  lea     rcx, [rbp+57h+rgIndices]; this
0x1800b65de  call    ??0_bstr_t@@QEAA@PEBG@Z; _bstr_t::_bstr_t(ushort const *)
0x1800b65e3  mov     rcx, [rax]
0x1800b65e6  test    rcx, rcx
0x1800b65e9  jz      short loc_1800B65F0
0x1800b65eb  mov     rdx, [rcx]
0x1800b65ee  jmp     short loc_1800B65F3
0x1800b65f0  mov     rdx, r12
0x1800b65f3  lea     rax, [rbp+57h+var_78]
0x1800b65f7  mov     r9d, 30h ; '0'
0x1800b65fd  mov     qword ptr [rsp+0D0h+dwImpLevel], rax
0x1800b6602  mov     r8, rbx
0x1800b6605  mov     rax, r14
0x1800b6608  mov     [rsp+0D0h+ppv], r12
0x1800b660d  mov     rcx, rdi
0x1800b6610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6615  lea     rcx, [rbp+57h+rgIndices]; this
0x1800b6619  mov     ebx, eax
0x1800b661b  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800b6620  lea     rcx, [rbp+57h+pv]; this
0x1800b6624  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x1800b6629  test    ebx, ebx
0x1800b662b  jns     short loc_1800B666B
0x1800b662d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6634  lea     rdx, WPP_GLOBAL_Control
0x1800b663b  cmp     rcx, rdx
0x1800b663e  jz      loc_1800B6829
0x1800b6644  test    [rcx+1Ch], r13b
0x1800b6648  jz      loc_1800B6829
0x1800b664e  mov     rcx, [rcx+10h]
0x1800b6652  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b6659  mov     edx, 0FFh
0x1800b665e  mov     r9d, ebx
0x1800b6661  call    WPP_SF_d
0x1800b6666  jmp     loc_1800B6829
0x1800b666b  mov     rcx, [rbp+57h+var_78]
0x1800b666f  lea     rdx, [rbp+57h+arg_8]
0x1800b6673  mov     [rbp+57h+var_70], r12
0x1800b6677  lea     r9, [rbp+57h+var_70]
0x1800b667b  mov     [rbp+57h+arg_8], r12d
0x1800b667f  mov     r8d, r13d
0x1800b6682  mov     [rsp+0D0h+ppv], rdx
0x1800b6687  or      edx, 0FFFFFFFFh
0x1800b668a  mov     rax, [rcx]
0x1800b668d  mov     rax, [rax+20h]
0x1800b6691  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6696  mov     ebx, eax
0x1800b6698  test    eax, eax
0x1800b669a  jns     short loc_1800B66DA
0x1800b669c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b66a3  lea     rdx, WPP_GLOBAL_Control
0x1800b66aa  cmp     rcx, rdx
0x1800b66ad  jz      loc_1800B6820
0x1800b66b3  test    [rcx+1Ch], r13b
0x1800b66b7  jz      loc_1800B6820
0x1800b66bd  mov     rcx, [rcx+10h]
0x1800b66c1  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b66c8  mov     edx, 100h
0x1800b66cd  mov     r9d, eax
0x1800b66d0  call    WPP_SF_d
0x1800b66d5  jmp     loc_1800B6820
0x1800b66da  cmp     [rbp+57h+arg_8], r13d
0x1800b66de  jz      short loc_1800B6705
0x1800b66e0  lea     rcx, [rbp+57h+var_70]
0x1800b66e4  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b66e9  lea     rcx, [rbp+57h+var_78]
0x1800b66ed  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b66f2  lea     rcx, [rbp+57h+pProxy]
0x1800b66f6  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b66fb  mov     ebx, 8007139Fh
0x1800b6700  jmp     loc_1800B683B
0x1800b6705  mov     rcx, [rbp+57h+var_70]
0x1800b6709  lea     r9, [rbp+57h+pvarg]
0x1800b670d  mov     word ptr [rbp+57h+pvarg], r12w
0x1800b6712  lea     rdx, aSecurityservic; "SecurityServicesRunning"
0x1800b6719  mov     [rbp+57h+plLbound], r12d
0x1800b671d  xor     r8d, r8d
0x1800b6720  mov     [rbp+57h+plUbound], r12d
0x1800b6724  mov     rax, [rcx]
0x1800b6727  mov     qword ptr [rsp+0D0h+dwImpLevel], r12
0x1800b672c  mov     [rsp+0D0h+ppv], r12
0x1800b6731  mov     rax, [rax+20h]
0x1800b6735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b673a  mov     ebx, eax
0x1800b673c  test    eax, eax
0x1800b673e  jns     short loc_1800B676B
0x1800b6740  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b6747  lea     rdx, WPP_GLOBAL_Control
0x1800b674e  cmp     rcx, rdx
0x1800b6751  jz      loc_1800B680F
0x1800b6757  test    [rcx+1Ch], r13b
0x1800b675b  jz      loc_1800B680F
0x1800b6761  mov     edx, 101h
0x1800b6766  jmp     loc_1800B67FC
0x1800b676b  movzx   eax, word ptr [rbp+57h+pvarg]
0x1800b676f  mov     ecx, 2003h
0x1800b6774  cmp     ax, cx
0x1800b6777  jnz     loc_1800B68BE
0x1800b677d  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800b6781  call    cs:__imp_SafeArrayGetDim
0x1800b6787  cmp     eax, r13d
0x1800b678a  jnz     loc_1800B68BA
0x1800b6790  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800b6794  lea     r8, [rbp+57h+plLbound]; plLbound
0x1800b6798  mov     edx, r13d; nDim
0x1800b679b  call    cs:__imp_SafeArrayGetLBound
0x1800b67a1  mov     ebx, eax
0x1800b67a3  test    eax, eax
0x1800b67a5  jns     short loc_1800B67C7
0x1800b67a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b67ae  lea     rdx, WPP_GLOBAL_Control
0x1800b67b5  cmp     rcx, rdx
0x1800b67b8  jz      short loc_1800B680F
0x1800b67ba  test    [rcx+1Ch], r13b
0x1800b67be  jz      short loc_1800B680F
0x1800b67c0  mov     edx, 102h
0x1800b67c5  jmp     short loc_1800B67FC
0x1800b67c7  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800b67cb  lea     r8, [rbp+57h+plUbound]; plUbound
0x1800b67cf  mov     edx, r13d; nDim
0x1800b67d2  call    cs:__imp_SafeArrayGetUBound
0x1800b67d8  mov     ebx, eax
0x1800b67da  test    eax, eax
0x1800b67dc  jns     short loc_1800B684B
0x1800b67de  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b67e5  lea     rdx, WPP_GLOBAL_Control
0x1800b67ec  cmp     rcx, rdx
0x1800b67ef  jz      short loc_1800B680F
0x1800b67f1  test    [rcx+1Ch], r13b
0x1800b67f5  jz      short loc_1800B680F
0x1800b67f7  mov     edx, 103h
0x1800b67fc  mov     rcx, [rcx+10h]
0x1800b6800  lea     r8, WPP_60a6be03328e3dc19e58859635691dd5_Traceguids
0x1800b6807  mov     r9d, eax
0x1800b680a  call    WPP_SF_d
0x1800b680f  cmp     word ptr [rbp+57h+pvarg], r12w
0x1800b6814  jz      short loc_1800B6820
0x1800b6816  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b681a  call    cs:__imp_VariantClear
0x1800b6820  lea     rcx, [rbp+57h+var_70]
0x1800b6824  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b6829  lea     rcx, [rbp+57h+var_78]
0x1800b682d  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b6832  lea     rcx, [rbp+57h+pProxy]
0x1800b6836  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b683b  lea     rcx, [rbp+57h+var_60]
0x1800b683f  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b6844  mov     eax, ebx
0x1800b6846  jmp     loc_1800B68F6
0x1800b684b  mov     eax, [rbp+57h+plLbound]
0x1800b684e  mov     dword ptr [rbp+57h+rgIndices], eax
0x1800b6851  cmp     eax, [rbp+57h+plUbound]
0x1800b6854  jg      short loc_1800B6881
0x1800b6856  mov     rcx, qword ptr [rbp+57h+pvarg+8]; psa
0x1800b685a  lea     r8, [rbp+57h+pv]; pv
0x1800b685e  lea     rdx, [rbp+57h+rgIndices]; rgIndices
0x1800b6862  mov     [rbp+57h+pv], r12d
0x1800b6866  call    cs:__imp_SafeArrayGetElement
0x1800b686c  test    eax, eax
0x1800b686e  js      short loc_1800B6876
0x1800b6870  cmp     [rbp+57h+pv], r15d
0x1800b6874  jz      short loc_1800B687E
0x1800b6876  mov     eax, dword ptr [rbp+57h+rgIndices]
0x1800b6879  add     eax, r13d
0x1800b687c  jmp     short loc_1800B684E
0x1800b687e  mov     [rsi], r13d
0x1800b6881  cmp     word ptr [rbp+57h+pvarg], r12w
0x1800b6886  jz      short loc_1800B6892
0x1800b6888  lea     rcx, [rbp+57h+pvarg]; pvarg
0x1800b688c  call    cs:__imp_VariantClear
0x1800b6892  lea     rcx, [rbp+57h+var_70]
0x1800b6896  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b689b  lea     rcx, [rbp+57h+var_78]
0x1800b689f  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b68a4  lea     rcx, [rbp+57h+pProxy]
0x1800b68a8  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b68ad  lea     rcx, [rbp+57h+var_60]
0x1800b68b1  call    ??1?$AutoRef@UIAccountProtectionNotificationsSink@@@CommonUtil@@QEAA@XZ; CommonUtil::AutoRef<IAccountProtectionNotificationsSink>::~AutoRef<IAccountProtectionNotificationsSink>(void)
0x1800b68b6  xor     eax, eax
0x1800b68b8  jmp     short loc_1800B68F6
0x1800b68ba  movzx   eax, word ptr [rbp+57h+pvarg]
0x1800b68be  test    ax, ax
0x1800b68c1  jz      short loc_1800B68CD
0x1800b68c3  lea     rcx, [rbp+57h+pvarg]; pvarg
  ... truncated ...
```
