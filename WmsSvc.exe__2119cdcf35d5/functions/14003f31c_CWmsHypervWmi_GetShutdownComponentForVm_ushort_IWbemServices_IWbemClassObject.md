# CWmsHypervWmi::GetShutdownComponentForVm(ushort *,IWbemServices * *,IWbemClassObject * *)

- ea: `0x14003f31c`
- end: `0x14003f910`
- name: `?GetShutdownComponentForVm@CWmsHypervWmi@@AEAAJPEAGPEAPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z`
- size: `1524`
- prototype: `__int64 __fastcall(CWmsHypervWmi *this, unsigned __int16 *, IUnknown **, struct IWbemClassObject **)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140042950`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x14003f31c`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14003f3ca`
- `KERNEL32!IsDebuggerPresent` at `0x14003f489`
- `KERNEL32!IsDebuggerPresent` at `0x14003f511`
- `KERNEL32!IsDebuggerPresent` at `0x14003f5e5`
- `KERNEL32!IsDebuggerPresent` at `0x14003f673`
- `KERNEL32!IsDebuggerPresent` at `0x14003f6e6`
- `KERNEL32!IsDebuggerPresent` at `0x14003f790`
- `KERNEL32!IsDebuggerPresent` at `0x14003f847`
- `KERNEL32!IsDebuggerPresent` at `0x14003f3ca`
- `KERNEL32!IsDebuggerPresent` at `0x14003f489`
- `KERNEL32!IsDebuggerPresent` at `0x14003f511`
- `KERNEL32!IsDebuggerPresent` at `0x14003f5e5`
- `KERNEL32!IsDebuggerPresent` at `0x14003f673`
- `KERNEL32!IsDebuggerPresent` at `0x14003f6e6`
- `KERNEL32!IsDebuggerPresent` at `0x14003f790`
- `KERNEL32!IsDebuggerPresent` at `0x14003f847`
- `ole32!CoCreateInstance` at `0x14003f386`
- `ole32!CoCreateInstance` at `0x14003f386`
- `ole32!CoSetProxyBlanket` at `0x14003f4cd`
- `ole32!CoSetProxyBlanket` at `0x14003f4cd`
- `OLEAUT32!__imp_SysAllocString` at `0x14003f696`
- `OLEAUT32!__imp_SysAllocString` at `0x14003f696`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f888`
- `OLEAUT32!__imp_SysFreeString` at `0x14003f888`

## string_xrefs

- `0x14003f5a9`: `pszSearchCommand`
- `0x14003f5ed`: `pszSearchCommand`
- `0x14003f6aa`: `bstrSearchCommand`
- `0x14003f6ee`: `bstrSearchCommand`
- `0x14003f39d`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f45c`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f4e4`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f5bc`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f646`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f6bd`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f763`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f81a`: `CWmsHypervWmi::GetShutdownComponentForVm`
- `0x14003f623`: `select * from Msvm_ShutdownComponent Where SystemName = '%s'`

## pseudocode

```c
__int64 __fastcall CWmsHypervWmi::GetShutdownComponentForVm(
        CWmsHypervWmi *this,
        unsigned __int16 *a2,
        IUnknown **a3,
        struct IWbemClassObject **a4)
{
  OLECHAR *v7; // r12
  OLECHAR *v8; // r13
  HRESULT v9; // eax
  unsigned int v10; // ebx
  __int64 v11; // r9
  __int64 v12; // r8
  int v13; // eax
  HRESULT v14; // eax
  unsigned __int16 *v15; // rax
  __int64 v16; // rcx
  __int64 v17; // r8
  unsigned __int64 v18; // rbx
  unsigned __int16 *v19; // rax
  int v20; // eax
  BSTR v21; // rax
  int v22; // eax
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+30h] [rbp-30h]
  DWORD dwCapabilities[2]; // [rsp+38h] [rbp-28h]
  __int64 v26; // [rsp+50h] [rbp-10h] BYREF
  LPVOID ppv; // [rsp+58h] [rbp-8h] BYREF
  int v28; // [rsp+A0h] [rbp+40h] BYREF
  int v29; // [rsp+A4h] [rbp+44h]
  IUnknown *pProxy; // [rsp+B0h] [rbp+50h] BYREF
  struct IWbemClassObject *v31; // [rsp+B8h] [rbp+58h] BYREF

  v29 = HIDWORD(this);
  ppv = 0;
  pProxy = 0;
  v26 = 0;
  v7 = 0;
  v31 = 0;
  v8 = 0;
  v28 = 0;
  if ( a3 )
    *a3 = 0;
  *a4 = 0;
  v9 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v10 = v9;
  if ( v9 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7ECu,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v9);
    if ( IsDebuggerPresent() )
    {
      v11 = 2028;
LABEL_6:
      dwCapabilities[0] = v10;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v11,
        L"CWmsHypervWmi::GetShutdownComponentForVm",
        L"CHRA",
        L"hr",
        *(_QWORD *)dwCapabilities);
      goto LABEL_46;
    }
    v12 = 2028;
    goto LABEL_45;
  }
  v13 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
          ppv,
          CWmsHypervWmi::s_bstrWmiNamespaceVirtualization,
          0,
          0,
          0,
          0,
          0,
          0,
          &pProxy);
  v10 = v13;
  if ( v13 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7EFu,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v13);
    if ( IsDebuggerPresent() )
    {
      v11 = 2031;
      goto LABEL_6;
    }
    v12 = 2031;
    goto LABEL_45;
  }
  v14 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  v10 = v14;
  if ( v14 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7F2u,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v14);
    if ( IsDebuggerPresent() )
    {
      v11 = 2034;
      goto LABEL_6;
    }
    v12 = 2034;
    goto LABEL_45;
  }
  if ( !a2 )
  {
    v10 = -2147024809;
LABEL_42:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7F8u,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v10);
    if ( IsDebuggerPresent() )
    {
      v11 = 2040;
      goto LABEL_6;
    }
    v12 = 2040;
LABEL_45:
    LODWORD(pAuthInfo) = v10;
    DEBUGMSGBOX(
      L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      v12,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      pAuthInfo);
    goto LABEL_46;
  }
  v15 = a2;
  v16 = 0x7FFFFFFF;
  do
  {
    if ( !*v15 )
      break;
    ++v15;
    --v16;
  }
  while ( v16 );
  v10 = v16 == 0 ? 0x80070057 : 0;
  v17 = (0x7FFFFFFF - v16) & -(__int64)(v16 != 0);
  if ( !v16 )
    goto LABEL_42;
  v18 = v17 + 62;
  v19 = (unsigned __int16 *)operator new(saturated_mul(v17 + 62, 2u));
  v7 = v19;
  if ( !v19 )
  {
    v10 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7FDu,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CPR",
      L"pszSearchCommand",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      dwCapabilities[0] = -2147024882;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        2045,
        L"CWmsHypervWmi::GetShutdownComponentForVm",
        L"CPR",
        L"pszSearchCommand",
        *(_QWORD *)dwCapabilities);
    }
    else
    {
      LODWORD(pAuthInfo) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        2045,
        L"CWmsHypervWmi::GetShutdownComponentForVm",
        L"CPR",
        L"pszSearchCommand",
        pAuthInfo);
    }
    goto LABEL_46;
  }
  v20 = StringCchPrintfW(v19, v18, aSelectFromMsvm_0, a2);
  v10 = v20;
  if ( v20 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x800u,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v20);
    if ( IsDebuggerPresent() )
    {
      v11 = 2048;
      goto LABEL_6;
    }
    v12 = 2048;
    goto LABEL_45;
  }
  v21 = SysAllocString(v7);
  v8 = v21;
  if ( !v21 )
  {
    v10 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x803u,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CPR",
      L"bstrSearchCommand",
      -2147024882);
    if ( IsDebuggerPresent() )
    {
      dwCapabilities[0] = -2147024882;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        2051,
        L"CWmsHypervWmi::GetShutdownComponentForVm",
        L"CPR",
        L"bstrSearchCommand",
        *(_QWORD *)dwCapabilities);
    }
    else
    {
      LODWORD(pAuthInfo) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        2051,
        L"CWmsHypervWmi::GetShutdownComponentForVm",
        L"CPR",
        L"bstrSearchCommand",
        pAuthInfo);
    }
    goto LABEL_46;
  }
  v22 = ((__int64 (__fastcall *)(IUnknown *, BSTR, BSTR, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
          pProxy,
          CWmsHypervWmi::s_bstrWql,
          v21,
          48,
          0,
          &v26);
  v10 = v22;
  if ( v22 < 0 )
  {
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x806u,
      L"CWmsHypervWmi::GetShutdownComponentForVm",
      L"CHRA",
      L"hr",
      v22);
    if ( IsDebuggerPresent() )
    {
      v11 = 2054;
      goto LABEL_6;
    }
    v12 = 2054;
    goto LABEL_45;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64, struct IWbemClassObject **, int *))(*(_QWORD *)v26 + 32LL))(
    v26,
    0xFFFFFFFFLL,
    1,
    &v31,
    &v28);
  if ( v28 )
  {
    v10 = 0;
    *a4 = v31;
    v31 = 0;
    if ( a3 )
    {
      *a3 = pProxy;
      pProxy = 0;
    }
  }
  else
  {
    v10 = -2147024894;
  }
LABEL_46:
  SysFreeString(v8);
  operator delete(v7);
  if ( v31 )
  {
    ((void (__fastcall *)(struct IWbemClassObject *))v31->lpVtbl->Release)(v31);
    v31 = 0;
  }
  if ( v26 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    v26 = 0;
  }
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return v10;
}

```

## disassembly

```asm
0x14003f31c  mov     [rsp-38h+arg_8], rbx
0x14003f321  mov     [rsp-38h+arg_0], rcx
0x14003f326  push    rbp
0x14003f327  push    rsi
0x14003f328  push    rdi
0x14003f329  push    r12
0x14003f32b  push    r13
0x14003f32d  push    r14
0x14003f32f  push    r15
0x14003f331  mov     rbp, rsp
0x14003f334  sub     rsp, 60h
0x14003f338  xor     r15d, r15d
0x14003f33b  mov     r14, r9
0x14003f33e  mov     [rbp+var_8], r15
0x14003f342  mov     rdi, r8
0x14003f345  mov     [rbp+pProxy], r15
0x14003f349  mov     rsi, rdx
0x14003f34c  mov     [rbp+var_10], r15
0x14003f350  mov     r12d, r15d
0x14003f353  mov     [rbp+arg_18], r15
0x14003f357  mov     r13d, r15d
0x14003f35a  mov     dword ptr [rbp+arg_0], r15d
0x14003f35e  test    r8, r8
0x14003f361  jz      short loc_14003F366
0x14003f363  mov     [r8], r15
0x14003f366  xor     edx, edx; pUnkOuter
0x14003f368  mov     [r9], r15
0x14003f36b  lea     rax, [rbp+var_8]
0x14003f36f  lea     r9, IID_IWbemLocator; riid
0x14003f376  mov     [rsp+60h+ppv], rax; ppv
0x14003f37b  lea     rcx, CLSID_WbemLocator; rclsid
0x14003f382  lea     r8d, [rdx+1]; dwClsContext
0x14003f386  call    cs:__imp_CoCreateInstance
0x14003f38c  mov     ebx, eax
0x14003f38e  test    eax, eax
0x14003f390  jns     short loc_14003F411
0x14003f392  mov     [rsp+60h+dwImpLevel], eax; int
0x14003f396  lea     r15, aChra; "CHRA"
0x14003f39d  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f3a4  mov     r9, r15; unsigned __int16 *
0x14003f3a7  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f3ae  mov     r8, rsi; unsigned __int16 *
0x14003f3b1  lea     r14, aHr; "hr"
0x14003f3b8  mov     rcx, rdi; unsigned __int16 *
0x14003f3bb  mov     edx, 7ECh; unsigned int
0x14003f3c0  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003f3c5  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f3ca  call    cs:__imp_IsDebuggerPresent
0x14003f3d0  test    eax, eax
0x14003f3d2  jz      short loc_14003F406
0x14003f3d4  mov     r9d, 7ECh
0x14003f3da  mov     [rsp+60h+dwCapabilities], ebx
0x14003f3de  mov     [rsp+60h+pAuthInfo], r14
0x14003f3e3  mov     qword ptr [rsp+60h+dwImpLevel], r15
0x14003f3e8  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14003f3ef  mov     r8, rdi
0x14003f3f2  mov     [rsp+60h+ppv], rsi
0x14003f3f7  mov     ecx, 2; unsigned __int8
0x14003f3fc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14003f401  jmp     loc_14003F882
0x14003f406  mov     r8d, 7ECh
0x14003f40c  jmp     loc_14003F862
0x14003f411  mov     rcx, [rbp+var_8]
0x14003f415  lea     rdx, [rbp+pProxy]
0x14003f419  mov     [rsp+60h+var_20], rdx
0x14003f41e  xor     r9d, r9d
0x14003f421  mov     rdx, cs:?s_bstrWmiNamespaceVirtualization@CWmsHypervWmi@@0PEAGEA; ushort * CWmsHypervWmi::s_bstrWmiNamespaceVirtualization
0x14003f428  xor     r8d, r8d
0x14003f42b  mov     qword ptr [rsp+60h+dwCapabilities], r15
0x14003f430  mov     rax, [rcx]
0x14003f433  mov     [rsp+60h+pAuthInfo], r15
0x14003f438  mov     [rsp+60h+dwImpLevel], r15d
0x14003f43d  mov     [rsp+60h+ppv], r15
0x14003f442  mov     rax, [rax+18h]
0x14003f446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f44b  mov     ebx, eax
0x14003f44d  test    eax, eax
0x14003f44f  jns     short loc_14003F4A9
0x14003f451  mov     [rsp+60h+dwImpLevel], eax; int
0x14003f455  lea     r15, aChra; "CHRA"
0x14003f45c  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f463  mov     r9, r15; unsigned __int16 *
0x14003f466  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f46d  mov     r8, rsi; unsigned __int16 *
0x14003f470  lea     r14, aHr; "hr"
0x14003f477  mov     rcx, rdi; unsigned __int16 *
0x14003f47a  mov     edx, 7EFh; unsigned int
0x14003f47f  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003f484  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f489  call    cs:__imp_IsDebuggerPresent
0x14003f48f  test    eax, eax
0x14003f491  jz      short loc_14003F49E
0x14003f493  mov     r9d, 7EFh
0x14003f499  jmp     loc_14003F3DA
0x14003f49e  mov     r8d, 7EFh
0x14003f4a4  jmp     loc_14003F862
0x14003f4a9  mov     rcx, [rbp+pProxy]; pProxy
0x14003f4ad  mov     eax, 3
0x14003f4b2  mov     [rsp+60h+dwCapabilities], r15d; dwCapabilities
0x14003f4b7  xor     r9d, r9d; pServerPrincName
0x14003f4ba  mov     [rsp+60h+pAuthInfo], r15; pAuthInfo
0x14003f4bf  xor     r8d, r8d; dwAuthzSvc
0x14003f4c2  mov     [rsp+60h+dwImpLevel], eax; dwImpLevel
0x14003f4c6  lea     edx, [rax+7]; dwAuthnSvc
0x14003f4c9  mov     dword ptr [rsp+60h+ppv], eax; dwAuthnLevel
0x14003f4cd  call    cs:__imp_CoSetProxyBlanket
0x14003f4d3  mov     ebx, eax
0x14003f4d5  test    eax, eax
0x14003f4d7  jns     short loc_14003F531
0x14003f4d9  mov     [rsp+60h+dwImpLevel], eax; int
0x14003f4dd  lea     r15, aChra; "CHRA"
0x14003f4e4  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f4eb  mov     r9, r15; unsigned __int16 *
0x14003f4ee  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f4f5  mov     r8, rsi; unsigned __int16 *
0x14003f4f8  lea     r14, aHr; "hr"
0x14003f4ff  mov     rcx, rdi; unsigned __int16 *
0x14003f502  mov     edx, 7F2h; unsigned int
0x14003f507  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003f50c  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f511  call    cs:__imp_IsDebuggerPresent
0x14003f517  test    eax, eax
0x14003f519  jz      short loc_14003F526
0x14003f51b  mov     r9d, 7F2h
0x14003f521  jmp     loc_14003F3DA
0x14003f526  mov     r8d, 7F2h
0x14003f52c  jmp     loc_14003F862
0x14003f531  test    rsi, rsi
0x14003f534  jz      loc_14003F80A
0x14003f53a  mov     edx, 7FFFFFFFh
0x14003f53f  mov     rax, rsi
0x14003f542  mov     ecx, edx
0x14003f544  cmp     [rax], r15w
0x14003f548  jz      short loc_14003F554
0x14003f54a  add     rax, 2
0x14003f54e  sub     rcx, 1
0x14003f552  jnz     short loc_14003F544
0x14003f554  mov     rax, rcx
0x14003f557  neg     rax
0x14003f55a  mov     rax, rcx
0x14003f55d  sbb     ebx, ebx
0x14003f55f  sub     rdx, rcx
0x14003f562  not     ebx
0x14003f564  and     ebx, 80070057h
0x14003f56a  neg     rax
0x14003f56d  sbb     r8, r8
0x14003f570  and     r8, rdx
0x14003f573  test    rcx, rcx
0x14003f576  jz      loc_14003F80F
0x14003f57c  lea     rbx, [r8+3Eh]
0x14003f580  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14003f587  mov     eax, 2
0x14003f58c  mul     rbx
0x14003f58f  cmovb   rax, rcx
0x14003f593  mov     rcx, rax; Size
0x14003f596  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003f59b  mov     r12, rax
0x14003f59e  test    rax, rax
0x14003f5a1  jnz     short loc_14003F620
0x14003f5a3  mov     r14d, 8007000Eh
0x14003f5a9  lea     rax, aPszsearchcomma; "pszSearchCommand"
0x14003f5b0  lea     r15, aCpr; "CPR"
0x14003f5b7  mov     [rsp+60h+dwImpLevel], r14d; int
0x14003f5bc  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f5c3  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14003f5c8  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f5cf  mov     r9, r15; unsigned __int16 *
0x14003f5d2  mov     r8, rsi; unsigned __int16 *
0x14003f5d5  mov     rcx, rdi; unsigned __int16 *
0x14003f5d8  mov     edx, 7FDh; unsigned int
0x14003f5dd  mov     ebx, r14d
0x14003f5e0  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f5e5  call    cs:__imp_IsDebuggerPresent
0x14003f5eb  test    eax, eax
0x14003f5ed  lea     rax, aPszsearchcomma; "pszSearchCommand"
0x14003f5f4  jz      short loc_14003F60B
0x14003f5f6  mov     [rsp+60h+dwCapabilities], r14d
0x14003f5fb  mov     r9d, 7FDh
0x14003f601  mov     [rsp+60h+pAuthInfo], rax
0x14003f606  jmp     loc_14003F3E3
0x14003f60b  mov     dword ptr [rsp+60h+pAuthInfo], r14d
0x14003f610  mov     r8d, 7FDh
0x14003f616  mov     qword ptr [rsp+60h+dwImpLevel], rax
0x14003f61b  jmp     loc_14003F86B
0x14003f620  mov     r9, rsi
0x14003f623  lea     r8, aSelectFromMsvm_0; "select * from Msvm_ShutdownComponent Wh"...
0x14003f62a  mov     rdx, rbx; unsigned __int64
0x14003f62d  mov     rcx, r12; unsigned __int16 *
0x14003f630  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003f635  mov     ebx, eax
0x14003f637  test    eax, eax
0x14003f639  jns     short loc_14003F693
0x14003f63b  mov     [rsp+60h+dwImpLevel], eax; int
0x14003f63f  lea     r15, aChra; "CHRA"
0x14003f646  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f64d  mov     r9, r15; unsigned __int16 *
0x14003f650  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f657  mov     r8, rsi; unsigned __int16 *
0x14003f65a  lea     r14, aHr; "hr"
0x14003f661  mov     rcx, rdi; unsigned __int16 *
0x14003f664  mov     edx, 800h; unsigned int
0x14003f669  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003f66e  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f673  call    cs:__imp_IsDebuggerPresent
0x14003f679  test    eax, eax
0x14003f67b  jz      short loc_14003F688
0x14003f67d  mov     r9d, 800h
0x14003f683  jmp     loc_14003F3DA
0x14003f688  mov     r8d, 800h
0x14003f68e  jmp     loc_14003F862
0x14003f693  mov     rcx, r12; psz
0x14003f696  call    cs:__imp_SysAllocString
0x14003f69c  mov     r13, rax
0x14003f69f  test    rax, rax
0x14003f6a2  jnz     short loc_14003F721
0x14003f6a4  mov     r14d, 8007000Eh
0x14003f6aa  lea     rax, aBstrsearchcomm; "bstrSearchCommand"
0x14003f6b1  lea     r15, aCpr; "CPR"
0x14003f6b8  mov     [rsp+60h+dwImpLevel], r14d; int
0x14003f6bd  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f6c4  mov     [rsp+60h+ppv], rax; unsigned __int16 *
0x14003f6c9  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f6d0  mov     r9, r15; unsigned __int16 *
0x14003f6d3  mov     r8, rsi; unsigned __int16 *
0x14003f6d6  mov     rcx, rdi; unsigned __int16 *
0x14003f6d9  mov     edx, 803h; unsigned int
0x14003f6de  mov     ebx, r14d
0x14003f6e1  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f6e6  call    cs:__imp_IsDebuggerPresent
0x14003f6ec  test    eax, eax
0x14003f6ee  lea     rax, aBstrsearchcomm; "bstrSearchCommand"
0x14003f6f5  jz      short loc_14003F70C
0x14003f6f7  mov     [rsp+60h+dwCapabilities], r14d
0x14003f6fc  mov     r9d, 803h
0x14003f702  mov     [rsp+60h+pAuthInfo], rax
0x14003f707  jmp     loc_14003F3E3
0x14003f70c  mov     dword ptr [rsp+60h+pAuthInfo], r14d
0x14003f711  mov     r8d, 803h
0x14003f717  mov     qword ptr [rsp+60h+dwImpLevel], rax
0x14003f71c  jmp     loc_14003F86B
0x14003f721  mov     rcx, [rbp+pProxy]
0x14003f725  lea     rdx, [rbp+var_10]
0x14003f729  mov     qword ptr [rsp+60h+dwImpLevel], rdx
0x14003f72e  mov     r9d, 30h ; '0'
0x14003f734  mov     rdx, cs:?s_bstrWql@CWmsHypervWmi@@0PEAGEA; ushort * CWmsHypervWmi::s_bstrWql
0x14003f73b  mov     r8, r13
0x14003f73e  mov     [rsp+60h+ppv], r15
0x14003f743  mov     rax, [rcx]
0x14003f746  mov     rax, [rax+0A0h]
0x14003f74d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f752  mov     ebx, eax
0x14003f754  test    eax, eax
0x14003f756  jns     short loc_14003F7B0
0x14003f758  mov     [rsp+60h+dwImpLevel], eax; int
0x14003f75c  lea     r15, aChra; "CHRA"
0x14003f763  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f76a  mov     r9, r15; unsigned __int16 *
0x14003f76d  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003f774  mov     r8, rsi; unsigned __int16 *
0x14003f777  lea     r14, aHr; "hr"
0x14003f77e  mov     rcx, rdi; unsigned __int16 *
0x14003f781  mov     edx, 806h; unsigned int
0x14003f786  mov     [rsp+60h+ppv], r14; unsigned __int16 *
0x14003f78b  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003f790  call    cs:__imp_IsDebuggerPresent
0x14003f796  test    eax, eax
0x14003f798  jz      short loc_14003F7A5
0x14003f79a  mov     r9d, 806h
0x14003f7a0  jmp     loc_14003F3DA
0x14003f7a5  mov     r8d, 806h
0x14003f7ab  jmp     loc_14003F862
0x14003f7b0  mov     rcx, [rbp+var_10]
0x14003f7b4  lea     r9, [rbp+arg_0]
0x14003f7b8  mov     [rsp+60h+ppv], r9
0x14003f7bd  mov     r8d, 1
0x14003f7c3  lea     r9, [rbp+arg_18]
0x14003f7c7  or      edx, 0FFFFFFFFh
0x14003f7ca  mov     rax, [rcx]
0x14003f7cd  mov     rax, [rax+20h]
0x14003f7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f7d6  cmp     dword ptr [rbp+arg_0], r15d
0x14003f7da  jnz     short loc_14003F7E6
0x14003f7dc  mov     ebx, 80070002h
0x14003f7e1  jmp     loc_14003F885
0x14003f7e6  mov     rax, [rbp+arg_18]
0x14003f7ea  mov     ebx, r15d
0x14003f7ed  mov     [r14], rax
0x14003f7f0  mov     [rbp+arg_18], r15
0x14003f7f4  test    rdi, rdi
0x14003f7f7  jz      loc_14003F885
0x14003f7fd  mov     rax, [rbp+pProxy]
0x14003f801  mov     [rdi], rax
0x14003f804  mov     [rbp+pProxy], r15
0x14003f808  jmp     short loc_14003F885
0x14003f80a  mov     ebx, 80070057h
0x14003f80f  lea     r15, aChra; "CHRA"
0x14003f816  mov     [rsp+60h+dwImpLevel], ebx; int
0x14003f81a  lea     rsi, aCwmshypervwmiG_13; "CWmsHypervWmi::GetShutdownComponentForV"...
0x14003f821  mov     r9, r15; unsigned __int16 *
0x14003f824  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
  ... truncated ...
```
