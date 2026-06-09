# CWmsHypervWmi::GetTargetComputer(CWmsHypervWmi::GetTargetComputerSearchMethod,ushort *,IWbemServices * *,IWbemClassObject * *)

- ea: `0x14003f918`
- end: `0x14003fd85`
- name: `?GetTargetComputer@CWmsHypervWmi@@AEAAJW4GetTargetComputerSearchMethod@1@PEAGPEAPEAUIWbemServices@@PEAPEAUIWbemClassObject@@@Z`
- size: `1133`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `8`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x14003d330`
- `0x14003d5a0`
- `0x14003d8fc`
- `0x14003f220`
- `0x14003fd90`
- `0x14004099c`
- `0x1400417a0`
- `0x140042950`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x1400033e8`
- `0x14003f918`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x14007e010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14003fb02`
- `KERNEL32!IsDebuggerPresent` at `0x14003fbab`
- `KERNEL32!IsDebuggerPresent` at `0x14003fc9d`
- `KERNEL32!IsDebuggerPresent` at `0x14003fb02`
- `KERNEL32!IsDebuggerPresent` at `0x14003fbab`
- `KERNEL32!IsDebuggerPresent` at `0x14003fc9d`
- `ole32!CoCreateInstance` at `0x14003f986`
- `ole32!CoCreateInstance` at `0x14003f986`
- `ole32!CoSetProxyBlanket` at `0x14003fa0a`
- `ole32!CoSetProxyBlanket` at `0x14003fa0a`
- `OLEAUT32!__imp_SysAllocString` at `0x14003fb57`
- `OLEAUT32!__imp_SysAllocString` at `0x14003fb57`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fcf9`
- `OLEAUT32!__imp_SysFreeString` at `0x14003fcf9`

## string_xrefs

- `0x14003fad5`: `CWmsHypervWmi::GetTargetComputer`
- `0x14003fb7e`: `CWmsHypervWmi::GetTargetComputer`
- `0x14003fc72`: `CWmsHypervWmi::GetTargetComputer`
- `0x14003fac2`: `pszSearchCommand`
- `0x14003fb0a`: `pszSearchCommand`
- `0x14003fb6b`: `bstrSearchCommand`
- `0x14003fbb3`: `bstrSearchCommand`
- `0x14003fa25`: `select * from Msvm_ComputerSystem Where ElementName = '%s'`
- `0x14003fa2c`: `select * from Msvm_ComputerSystem Where Name = '%s'`

## pseudocode

```c
__int64 __fastcall CWmsHypervWmi::GetTargetComputer(__int64 a1, int a2, _WORD *a3, IUnknown **a4, _QWORD *a5)
{
  OLECHAR *v8; // r13
  _QWORD *v9; // r12
  HRESULT v10; // ebx
  unsigned int v11; // r12d
  const unsigned __int16 *v12; // rsi
  _WORD *v13; // rax
  __int64 v14; // rcx
  __int64 v15; // rbx
  unsigned __int64 v16; // rbx
  OLECHAR *v17; // rax
  unsigned int v18; // r12d
  bool v19; // zf
  const unsigned __int16 *v20; // rax
  BSTR v21; // rax
  RPC_AUTH_IDENTITY_HANDLE pAuthInfo; // [rsp+30h] [rbp-40h]
  DWORD dwCapabilities[2]; // [rsp+38h] [rbp-38h]
  __int64 v25; // [rsp+50h] [rbp-20h] BYREF
  __int64 v26; // [rsp+58h] [rbp-18h] BYREF
  OLECHAR *psz; // [rsp+60h] [rbp-10h]
  LPVOID ppv; // [rsp+68h] [rbp-8h] BYREF
  int v29; // [rsp+B0h] [rbp+40h] BYREF
  int v30; // [rsp+B4h] [rbp+44h]
  IUnknown *pProxy; // [rsp+C8h] [rbp+58h] BYREF

  v30 = HIDWORD(a1);
  ppv = 0;
  pProxy = 0;
  v26 = 0;
  v8 = 0;
  v25 = 0;
  psz = 0;
  v29 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = a5;
  *a5 = 0;
  v10 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  if ( v10 < 0 )
  {
    v11 = 1930;
    goto LABEL_35;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
          ppv,
          CWmsHypervWmi::s_bstrWmiNamespaceVirtualization,
          0,
          0,
          0,
          0,
          0,
          0,
          &pProxy);
  if ( v10 < 0 )
  {
    v11 = 1933;
    goto LABEL_35;
  }
  v10 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 3u, 3u, 0, 0);
  if ( v10 < 0 )
  {
    v11 = 1936;
    goto LABEL_35;
  }
  v12 = aSelectFromMsvm_2;
  if ( a2 != 1 )
    v12 = aSelectFromMsvm_1;
  if ( !a3 )
  {
    v10 = -2147024809;
LABEL_34:
    v11 = 1951;
LABEL_35:
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      v11,
      L"CWmsHypervWmi::GetTargetComputer",
      L"CHRA",
      L"hr",
      v10);
    if ( IsDebuggerPresent() )
    {
      dwCapabilities[0] = v10;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v11,
        L"CWmsHypervWmi::GetTargetComputer",
        L"CHRA",
        L"hr",
        *(_QWORD *)dwCapabilities);
    }
    else
    {
      LODWORD(pAuthInfo) = v10;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v11,
        L"CWmsHypervWmi::GetTargetComputer",
        L"CHRA",
        L"hr",
        pAuthInfo);
    }
    goto LABEL_38;
  }
  v13 = a3;
  v14 = 0x7FFFFFFF;
  do
  {
    if ( !*v13 )
      break;
    ++v13;
    --v14;
  }
  while ( v14 );
  v10 = v14 == 0 ? 0x80070057 : 0;
  if ( !v14 )
    goto LABEL_34;
  v15 = 53;
  if ( a2 != 1 )
    v15 = 60;
  v16 = ((0x7FFFFFFF - v14) & -(__int64)(v14 != 0)) + v15;
  v17 = (OLECHAR *)operator new(saturated_mul(v16, 2u));
  psz = v17;
  if ( !v17 )
  {
    v18 = 1956;
    v10 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7A4u,
      L"CWmsHypervWmi::GetTargetComputer",
      L"CPR",
      L"pszSearchCommand",
      -2147024882);
    v19 = !IsDebuggerPresent();
    v20 = L"pszSearchCommand";
    goto LABEL_20;
  }
  v10 = StringCchPrintfW(v17, v16, v12, a3);
  if ( v10 < 0 )
  {
    v11 = 1959;
    goto LABEL_35;
  }
  v21 = SysAllocString(psz);
  v8 = v21;
  if ( !v21 )
  {
    v18 = 1962;
    v10 = -2147024882;
    LOGASSERTHR(
      L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
      0x7AAu,
      L"CWmsHypervWmi::GetTargetComputer",
      L"CPR",
      L"bstrSearchCommand",
      -2147024882);
    v19 = !IsDebuggerPresent();
    v20 = L"bstrSearchCommand";
LABEL_20:
    if ( v19 )
    {
      LODWORD(pAuthInfo) = -2147024882;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v18,
        L"CWmsHypervWmi::GetTargetComputer",
        L"CPR",
        v20,
        pAuthInfo);
    }
    else
    {
      dwCapabilities[0] = -2147024882;
      DEBUGMSGLEVEL(
        2u,
        L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\wmshypervwmi.cpp",
        v18,
        L"CWmsHypervWmi::GetTargetComputer",
        L"CPR",
        v20,
        *(_QWORD *)dwCapabilities);
    }
    goto LABEL_38;
  }
  v10 = ((__int64 (__fastcall *)(IUnknown *, BSTR, BSTR, __int64, _QWORD, __int64 *))pProxy->lpVtbl[6].Release)(
          pProxy,
          CWmsHypervWmi::s_bstrWql,
          v21,
          48,
          0,
          &v26);
  if ( v10 < 0 )
  {
    v11 = 1965;
    goto LABEL_35;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64, __int64 *, int *))(*(_QWORD *)v26 + 32LL))(
    v26,
    0xFFFFFFFFLL,
    1,
    &v25,
    &v29);
  if ( v29 )
  {
    v10 = 0;
    *v9 = v25;
    v25 = 0;
    if ( a4 )
    {
      *a4 = pProxy;
      pProxy = 0;
    }
  }
  else
  {
    v10 = -2147024894;
  }
LABEL_38:
  SysFreeString(v8);
  operator delete(psz);
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
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
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14003f918  mov     [rsp-38h+arg_8], rbx
0x14003f91d  mov     [rsp-38h+arg_0], rcx
0x14003f922  push    rbp
0x14003f923  push    rsi
0x14003f924  push    rdi
0x14003f925  push    r12
0x14003f927  push    r13
0x14003f929  push    r14
0x14003f92b  push    r15
0x14003f92d  mov     rbp, rsp
0x14003f930  sub     rsp, 70h
0x14003f934  xor     esi, esi
0x14003f936  mov     rdi, r9
0x14003f939  mov     [rbp+var_8], rsi
0x14003f93d  mov     r14, r8
0x14003f940  mov     [rbp+pProxy], rsi
0x14003f944  mov     r15d, edx
0x14003f947  mov     [rbp+var_18], rsi
0x14003f94b  mov     r13d, esi
0x14003f94e  mov     [rbp+var_20], rsi
0x14003f952  mov     [rbp+psz], rsi
0x14003f956  mov     dword ptr [rbp+arg_0], esi
0x14003f959  test    r9, r9
0x14003f95c  jz      short loc_14003F961
0x14003f95e  mov     [r9], rsi
0x14003f961  mov     r12, [rbp+arg_20]
0x14003f965  lea     rax, [rbp+var_8]
0x14003f969  xor     edx, edx; pUnkOuter
0x14003f96b  mov     [rsp+70h+ppv], rax; ppv
0x14003f970  lea     r9, IID_IWbemLocator; riid
0x14003f977  lea     rcx, CLSID_WbemLocator; rclsid
0x14003f97e  mov     [r12], rsi
0x14003f982  lea     r8d, [rdx+1]; dwClsContext
0x14003f986  call    cs:__imp_CoCreateInstance
0x14003f98c  mov     ebx, eax
0x14003f98e  test    eax, eax
0x14003f990  jns     short loc_14003F99D
0x14003f992  mov     r12d, 78Ah
0x14003f998  jmp     loc_14003FC67
0x14003f99d  mov     rcx, [rbp+var_8]
0x14003f9a1  lea     rdx, [rbp+pProxy]
0x14003f9a5  mov     [rsp+70h+var_30], rdx
0x14003f9aa  xor     r9d, r9d
0x14003f9ad  mov     rdx, cs:?s_bstrWmiNamespaceVirtualization@CWmsHypervWmi@@0PEAGEA; ushort * CWmsHypervWmi::s_bstrWmiNamespaceVirtualization
0x14003f9b4  xor     r8d, r8d
0x14003f9b7  mov     qword ptr [rsp+70h+dwCapabilities], rsi
0x14003f9bc  mov     rax, [rcx]
0x14003f9bf  mov     [rsp+70h+pAuthInfo], rsi
0x14003f9c4  mov     [rsp+70h+dwImpLevel], esi
0x14003f9c8  mov     [rsp+70h+ppv], rsi
0x14003f9cd  mov     rax, [rax+18h]
0x14003f9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003f9d6  mov     ebx, eax
0x14003f9d8  test    eax, eax
0x14003f9da  jns     short loc_14003F9E7
0x14003f9dc  mov     r12d, 78Dh
0x14003f9e2  jmp     loc_14003FC67
0x14003f9e7  mov     rcx, [rbp+pProxy]; pProxy
0x14003f9eb  mov     eax, 3
0x14003f9f0  mov     [rsp+70h+dwCapabilities], esi; dwCapabilities
0x14003f9f4  xor     r9d, r9d; pServerPrincName
0x14003f9f7  mov     [rsp+70h+pAuthInfo], rsi; pAuthInfo
0x14003f9fc  xor     r8d, r8d; dwAuthzSvc
0x14003f9ff  mov     [rsp+70h+dwImpLevel], eax; dwImpLevel
0x14003fa03  lea     edx, [rax+7]; dwAuthnSvc
0x14003fa06  mov     dword ptr [rsp+70h+ppv], eax; dwAuthnLevel
0x14003fa0a  call    cs:__imp_CoSetProxyBlanket
0x14003fa10  mov     ebx, eax
0x14003fa12  test    eax, eax
0x14003fa14  jns     short loc_14003FA21
0x14003fa16  mov     r12d, 790h
0x14003fa1c  jmp     loc_14003FC67
0x14003fa21  cmp     r15d, 1
0x14003fa25  lea     rax, aSelectFromMsvm_1; "select * from Msvm_ComputerSystem Where"...
0x14003fa2c  lea     rsi, aSelectFromMsvm_2; "select * from Msvm_ComputerSystem Where"...
0x14003fa33  cmovnz  rsi, rax
0x14003fa37  xor     r9d, r9d
0x14003fa3a  test    r14, r14
0x14003fa3d  jz      loc_14003FC5C
0x14003fa43  mov     edx, 7FFFFFFFh
0x14003fa48  mov     rax, r14
0x14003fa4b  mov     ecx, edx
0x14003fa4d  cmp     [rax], r9w
0x14003fa51  jz      short loc_14003FA5D
0x14003fa53  add     rax, 2
0x14003fa57  sub     rcx, 1
0x14003fa5b  jnz     short loc_14003FA4D
0x14003fa5d  mov     rax, rcx
0x14003fa60  neg     rax
0x14003fa63  mov     rax, rcx
0x14003fa66  sbb     ebx, ebx
0x14003fa68  sub     rdx, rcx
0x14003fa6b  not     ebx
0x14003fa6d  and     ebx, 80070057h
0x14003fa73  neg     rax
0x14003fa76  sbb     r8, r8
0x14003fa79  and     r8, rdx
0x14003fa7c  test    rcx, rcx
0x14003fa7f  jz      loc_14003FC61
0x14003fa85  mov     ebx, 35h ; '5'
0x14003fa8a  cmp     r15d, 1
0x14003fa8e  lea     ecx, [rbx+7]
0x14003fa91  cmovnz  ebx, ecx
0x14003fa94  lea     eax, [rcx-3Ah]
0x14003fa97  add     rbx, r8
0x14003fa9a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x14003faa1  mul     rbx
0x14003faa4  cmovb   rax, rcx
0x14003faa8  mov     rcx, rax; Size
0x14003faab  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14003fab0  xor     r15d, r15d
0x14003fab3  mov     [rbp+psz], rax
0x14003fab7  test    rax, rax
0x14003faba  jnz     short loc_14003FB31
0x14003fabc  mov     r14d, 8007000Eh
0x14003fac2  lea     rax, aPszsearchcomma; "pszSearchCommand"
0x14003fac9  lea     r15, aCpr; "CPR"
0x14003fad0  mov     [rsp+70h+dwImpLevel], r14d; int
0x14003fad5  lea     rsi, aCwmshypervwmiG_0; "CWmsHypervWmi::GetTargetComputer"
0x14003fadc  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14003fae1  mov     r12d, 7A4h
0x14003fae7  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003faee  mov     r9, r15; unsigned __int16 *
0x14003faf1  mov     r8, rsi; unsigned __int16 *
0x14003faf4  mov     edx, r12d; unsigned int
0x14003faf7  mov     rcx, rdi; unsigned __int16 *
0x14003fafa  mov     ebx, r14d
0x14003fafd  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003fb02  call    cs:__imp_IsDebuggerPresent
0x14003fb08  test    eax, eax
0x14003fb0a  lea     rax, aPszsearchcomma; "pszSearchCommand"
0x14003fb11  jz      short loc_14003FB22
0x14003fb13  mov     [rsp+70h+dwCapabilities], r14d
0x14003fb18  mov     [rsp+70h+pAuthInfo], rax
0x14003fb1d  jmp     loc_14003FCB0
0x14003fb22  mov     dword ptr [rsp+70h+pAuthInfo], r14d
0x14003fb27  mov     qword ptr [rsp+70h+dwImpLevel], rax
0x14003fb2c  jmp     loc_14003FCDC
0x14003fb31  mov     r9, r14
0x14003fb34  mov     r8, rsi; unsigned __int16 *
0x14003fb37  mov     rdx, rbx; unsigned __int64
0x14003fb3a  mov     rcx, rax; unsigned __int16 *
0x14003fb3d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003fb42  mov     ebx, eax
0x14003fb44  test    eax, eax
0x14003fb46  jns     short loc_14003FB53
0x14003fb48  mov     r12d, 7A7h
0x14003fb4e  jmp     loc_14003FC67
0x14003fb53  mov     rcx, [rbp+psz]; psz
0x14003fb57  call    cs:__imp_SysAllocString
0x14003fb5d  mov     r13, rax
0x14003fb60  test    rax, rax
0x14003fb63  jnz     short loc_14003FBBF
0x14003fb65  mov     r14d, 8007000Eh
0x14003fb6b  lea     rax, aBstrsearchcomm; "bstrSearchCommand"
0x14003fb72  lea     r15, aCpr; "CPR"
0x14003fb79  mov     [rsp+70h+dwImpLevel], r14d; int
0x14003fb7e  lea     rsi, aCwmshypervwmiG_0; "CWmsHypervWmi::GetTargetComputer"
0x14003fb85  mov     [rsp+70h+ppv], rax; unsigned __int16 *
0x14003fb8a  mov     r12d, 7AAh
0x14003fb90  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003fb97  mov     r9, r15; unsigned __int16 *
0x14003fb9a  mov     r8, rsi; unsigned __int16 *
0x14003fb9d  mov     edx, r12d; unsigned int
0x14003fba0  mov     rcx, rdi; unsigned __int16 *
0x14003fba3  mov     ebx, r14d
0x14003fba6  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003fbab  call    cs:__imp_IsDebuggerPresent
0x14003fbb1  test    eax, eax
0x14003fbb3  lea     rax, aBstrsearchcomm; "bstrSearchCommand"
0x14003fbba  jmp     loc_14003FB11
0x14003fbbf  mov     rcx, [rbp+pProxy]
0x14003fbc3  lea     rdx, [rbp+var_18]
0x14003fbc7  mov     qword ptr [rsp+70h+dwImpLevel], rdx
0x14003fbcc  mov     r9d, 30h ; '0'
0x14003fbd2  mov     rdx, cs:?s_bstrWql@CWmsHypervWmi@@0PEAGEA; ushort * CWmsHypervWmi::s_bstrWql
0x14003fbd9  mov     r8, r13
0x14003fbdc  mov     [rsp+70h+ppv], r15
0x14003fbe1  mov     rax, [rcx]
0x14003fbe4  mov     rax, [rax+0A0h]
0x14003fbeb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fbf0  mov     ebx, eax
0x14003fbf2  test    eax, eax
0x14003fbf4  jns     short loc_14003FBFE
0x14003fbf6  mov     r12d, 7ADh
0x14003fbfc  jmp     short loc_14003FC67
0x14003fbfe  mov     rcx, [rbp+var_18]
0x14003fc02  lea     r9, [rbp+arg_0]
0x14003fc06  mov     [rsp+70h+ppv], r9
0x14003fc0b  mov     r8d, 1
0x14003fc11  lea     r9, [rbp+var_20]
0x14003fc15  or      edx, 0FFFFFFFFh
0x14003fc18  mov     rax, [rcx]
0x14003fc1b  mov     rax, [rax+20h]
0x14003fc1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fc24  cmp     dword ptr [rbp+arg_0], r15d
0x14003fc28  jnz     short loc_14003FC34
0x14003fc2a  mov     ebx, 80070002h
0x14003fc2f  jmp     loc_14003FCF6
0x14003fc34  mov     rax, [rbp+var_20]
0x14003fc38  mov     ebx, r15d
0x14003fc3b  mov     [r12], rax
0x14003fc3f  mov     [rbp+var_20], r15
0x14003fc43  test    rdi, rdi
0x14003fc46  jz      loc_14003FCF6
0x14003fc4c  mov     rax, [rbp+pProxy]
0x14003fc50  mov     [rdi], rax
0x14003fc53  mov     [rbp+pProxy], r15
0x14003fc57  jmp     loc_14003FCF6
0x14003fc5c  mov     ebx, 80070057h
0x14003fc61  mov     r12d, 79Fh
0x14003fc67  lea     r15, aChra; "CHRA"
0x14003fc6e  mov     [rsp+70h+dwImpLevel], ebx; int
0x14003fc72  lea     rsi, aCwmshypervwmiG_0; "CWmsHypervWmi::GetTargetComputer"
0x14003fc79  mov     r9, r15; unsigned __int16 *
0x14003fc7c  lea     rdi, aTermsrvWmsSrcD_29; "termsrv\\wms\\src\\devices\\wmssvc\\wms"...
0x14003fc83  mov     r8, rsi; unsigned __int16 *
0x14003fc86  lea     r14, aHr; "hr"
0x14003fc8d  mov     rcx, rdi; unsigned __int16 *
0x14003fc90  mov     edx, r12d; unsigned int
0x14003fc93  mov     [rsp+70h+ppv], r14; unsigned __int16 *
0x14003fc98  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14003fc9d  call    cs:__imp_IsDebuggerPresent
0x14003fca3  test    eax, eax
0x14003fca5  jz      short loc_14003FCD3
0x14003fca7  mov     [rsp+70h+dwCapabilities], ebx
0x14003fcab  mov     [rsp+70h+pAuthInfo], r14
0x14003fcb0  mov     qword ptr [rsp+70h+dwImpLevel], r15
0x14003fcb5  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14003fcbc  mov     r9d, r12d
0x14003fcbf  mov     [rsp+70h+ppv], rsi
0x14003fcc4  mov     r8, rdi
0x14003fcc7  mov     ecx, 2; unsigned __int8
0x14003fccc  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14003fcd1  jmp     short loc_14003FCF6
0x14003fcd3  mov     dword ptr [rsp+70h+pAuthInfo], ebx
0x14003fcd7  mov     qword ptr [rsp+70h+dwImpLevel], r14
0x14003fcdc  mov     r9, rsi
0x14003fcdf  mov     [rsp+70h+ppv], r15
0x14003fce4  mov     r8d, r12d
0x14003fce7  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14003fcee  mov     rdx, rdi
0x14003fcf1  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14003fcf6  mov     rcx, r13; bstrString
0x14003fcf9  call    cs:__imp_SysFreeString
0x14003fcff  mov     rcx, [rbp+psz]; Block
0x14003fd03  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14003fd08  mov     rcx, [rbp+var_20]
0x14003fd0c  xor     r13d, r13d
0x14003fd0f  test    rcx, rcx
0x14003fd12  jz      short loc_14003FD24
0x14003fd14  mov     rax, [rcx]
0x14003fd17  mov     rax, [rax+10h]
0x14003fd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd20  mov     [rbp+var_20], r13
0x14003fd24  mov     rcx, [rbp+var_18]
0x14003fd28  test    rcx, rcx
0x14003fd2b  jz      short loc_14003FD3D
0x14003fd2d  mov     rax, [rcx]
0x14003fd30  mov     rax, [rax+10h]
0x14003fd34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd39  mov     [rbp+var_18], r13
0x14003fd3d  mov     rcx, [rbp+pProxy]
0x14003fd41  test    rcx, rcx
0x14003fd44  jz      short loc_14003FD56
0x14003fd46  mov     rax, [rcx]
0x14003fd49  mov     rax, [rax+10h]
0x14003fd4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd52  mov     [rbp+pProxy], r13
0x14003fd56  mov     rcx, [rbp+var_8]
0x14003fd5a  test    rcx, rcx
0x14003fd5d  jz      short loc_14003FD6B
0x14003fd5f  mov     rax, [rcx]
0x14003fd62  mov     rax, [rax+10h]
0x14003fd66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003fd6b  mov     eax, ebx
0x14003fd6d  mov     rbx, [rsp+70h+arg_8]
0x14003fd75  add     rsp, 70h
0x14003fd79  pop     r15
0x14003fd7b  pop     r14
0x14003fd7d  pop     r13
0x14003fd7f  pop     r12
0x14003fd81  pop     rdi
0x14003fd82  pop     rsi
0x14003fd83  pop     rbp
0x14003fd84  retn
```
