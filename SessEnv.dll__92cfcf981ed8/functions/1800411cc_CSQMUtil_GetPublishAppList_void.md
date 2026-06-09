# CSQMUtil::GetPublishAppList(void)

- ea: `0x1800411cc`
- end: `0x1800416ef`
- name: `?GetPublishAppList@CSQMUtil@@CAJXZ`
- size: `1315`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180040e44`

## callees

- `0x180003f30`
- `0x180004e00`
- `0x1800411cc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800414f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800414f6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800412df`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800413a7`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800412df`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x1800413a7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004121a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18004121a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800414e1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800414e1`
- `OLEAUT32!__imp_SysAllocString` at `0x180041250`
- `OLEAUT32!__imp_SysAllocString` at `0x1800412fe`
- `OLEAUT32!__imp_SysAllocString` at `0x180041328`
- `OLEAUT32!__imp_SysAllocString` at `0x180041250`
- `OLEAUT32!__imp_SysAllocString` at `0x1800412fe`
- `OLEAUT32!__imp_SysAllocString` at `0x180041328`
- `OLEAUT32!__imp_SysFreeString` at `0x180041696`
- `OLEAUT32!__imp_SysFreeString` at `0x18004169f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800416c1`
- `OLEAUT32!__imp_SysFreeString` at `0x180041696`
- `OLEAUT32!__imp_SysFreeString` at `0x18004169f`
- `OLEAUT32!__imp_SysFreeString` at `0x1800416c1`
- `OLEAUT32!__imp_SysStringLen` at `0x180041479`
- `OLEAUT32!__imp_SysStringLen` at `0x1800415d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800415e9`
- `OLEAUT32!__imp_SysStringLen` at `0x180041479`
- `OLEAUT32!__imp_SysStringLen` at `0x1800415d6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800415e9`
- `OLEAUT32!__imp_VariantInit` at `0x18004141f`
- `OLEAUT32!__imp_VariantInit` at `0x180041582`
- `OLEAUT32!__imp_VariantInit` at `0x18004141f`
- `OLEAUT32!__imp_VariantInit` at `0x180041582`
- `OLEAUT32!__imp_VariantClear` at `0x18004148b`
- `OLEAUT32!__imp_VariantClear` at `0x180041632`
- `OLEAUT32!__imp_VariantClear` at `0x18004148b`
- `OLEAUT32!__imp_VariantClear` at `0x180041632`

## string_xrefs

- `0x180041229`: `CoCreateInstance failed: 0x%x in %s`
- `0x180041249`: `\\.\root\CIMV2\TerminalServices`
- `0x18004137b`: `pWbemServices->ExecQuery failed: 0x%x in %s`
- `0x18004160d`: `StringCchCopy failed with 0x%08X.`

## pseudocode

```c
__int64 CSQMUtil::GetPublishAppList(void)
{
  OLECHAR *v0; // r12
  OLECHAR *v1; // r13
  HRESULT v2; // eax
  signed int v3; // ebx
  OLECHAR *v4; // r15
  const char *v5; // rdx
  BSTR v6; // rax
  BSTR v7; // rax
  unsigned __int64 v8; // rsi
  int v9; // eax
  int v10; // ebx
  int v11; // eax
  OLECHAR *bstrVal; // rcx
  unsigned __int16 *v13; // rdi
  signed int LastError; // eax
  int v15; // eax
  int v16; // eax
  UINT v17; // eax
  const unsigned __int16 *v18; // r8
  UINT v19; // r14d
  int v20; // eax
  LPVOID ppv; // [rsp+50h] [rbp-28h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-20h] BYREF
  int v24; // [rsp+C0h] [rbp+48h] BYREF
  __int64 v25; // [rsp+C8h] [rbp+50h] BYREF
  IUnknown *v26; // [rsp+D0h] [rbp+58h] BYREF
  IUnknown *pProxy; // [rsp+D8h] [rbp+60h] BYREF

  ppv = 0;
  pProxy = 0;
  v26 = 0;
  v25 = 0;
  v0 = 0;
  v24 = 0;
  v1 = 0;
  v2 = CoCreateInstance(&CLSID_WbemLocator, 0, 1u, &IID_IWbemLocator, &ppv);
  v3 = v2;
  if ( v2 < 0 )
  {
    v4 = 0;
    v5 = "CoCreateInstance failed: 0x%x in %s";
LABEL_3:
    _DbgPrintMessage(8, v5, (unsigned int)v2, "CSQMUtil::GetPublishAppList");
    goto LABEL_55;
  }
  v6 = SysAllocString(L"\\\\.\\root\\CIMV2\\TerminalServices");
  v4 = v6;
  if ( !v6 )
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "SysAllocString bszNetworkResource failed: 0x%x in %s",
      2147942414LL,
      "CSQMUtil::GetPublishAppList");
    goto LABEL_55;
  }
  v2 = (*(__int64 (__fastcall **)(LPVOID, BSTR, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, IUnknown **))(*(_QWORD *)ppv + 24LL))(
         ppv,
         v6,
         0,
         0,
         0,
         0,
         0,
         0,
         &pProxy);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = "pWbemLocator->ConnectServer() failed: 0x%x in %s";
    goto LABEL_3;
  }
  v2 = CoSetProxyBlanket(pProxy, 0xAu, 0, 0, 6u, 3u, 0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = "CoSetProxyBlanket() failed: 0x%x in %s";
    goto LABEL_3;
  }
  v0 = SysAllocString(L"SELECT Name FROM Win32_TSPublishedApplication");
  if ( !v0 )
  {
    v3 = -2147024882;
    _DbgPrintMessage(8, "SysAllocString bszQuery failed: 0x%x in %s", 2147942414LL, "CSQMUtil::GetPublishAppList");
    goto LABEL_55;
  }
  v7 = SysAllocString(L"WQL");
  v1 = v7;
  if ( !v7 )
  {
    v3 = -2147024882;
    _DbgPrintMessage(
      8,
      "SysAllocString bszQueryLanguage failed: 0x%x in %s",
      2147942414LL,
      "CSQMUtil::GetPublishAppList");
    goto LABEL_55;
  }
  v2 = ((__int64 (__fastcall *)(IUnknown *, BSTR, OLECHAR *, _QWORD, _QWORD, IUnknown **))pProxy->lpVtbl[6].Release)(
         pProxy,
         v7,
         v0,
         0,
         0,
         &v26);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = "pWbemServices->ExecQuery failed: 0x%x in %s";
    goto LABEL_3;
  }
  v2 = CoSetProxyBlanket(v26, 0xAu, 0, 0, 6u, 3u, 0, 0);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = "CoSetProxyBlanket failed: 0x%x in %s";
    goto LABEL_3;
  }
  v8 = 0;
  do
  {
    v9 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64 *, int *))v26->lpVtbl[1].AddRef)(
           v26,
           5000,
           1,
           &v25,
           &v24);
    v10 = v9;
    if ( v9 < 0 )
      _DbgPrintMessage(8, "pEnumWbemClassObject->Next failed with 0x%08X.", v9);
    if ( v25 )
    {
      memset(&pvarg, 0, sizeof(pvarg));
      VariantInit(&pvarg);
      v11 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v25 + 32LL))(
              v25,
              L"Name",
              0,
              &pvarg,
              0,
              0);
      v10 = v11;
      if ( v11 >= 0 )
      {
        bstrVal = pvarg.bstrVal;
        if ( !pvarg.llVal )
          bstrVal = (OLECHAR *)L"Unknown App";
        v8 += SysStringLen(bstrVal) + 1LL;
        VariantClear(&pvarg);
      }
      else
      {
        _DbgPrintMessage(8, "pWbemClassObject->Get Name failed with 0x%08X.", v11);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
      v25 = 0;
    }
  }
  while ( v10 != 1 && v10 >= 0 );
  v2 = ((__int64 (__fastcall *)(IUnknown *))v26->lpVtbl[1].QueryInterface)(v26);
  v3 = v2;
  if ( v2 < 0 )
  {
    v5 = "pEnumWbemClassObject->Reset failed: 0x%x in %s";
    goto LABEL_3;
  }
  hMem = LocalAlloc(0x40u, 2 * v8 + 2);
  v13 = (unsigned __int16 *)hMem;
  if ( hMem )
    goto LABEL_39;
  LastError = GetLastError();
  v3 = LastError;
  if ( LastError > 0 )
    v3 = (unsigned __int16)LastError | 0x80070000;
  if ( v3 >= 0 )
  {
    v13 = (unsigned __int16 *)hMem;
    while ( 1 )
    {
LABEL_39:
      v15 = ((__int64 (__fastcall *)(IUnknown *, __int64, __int64, __int64 *, int *))v26->lpVtbl[1].AddRef)(
              v26,
              5000,
              1,
              &v25,
              &v24);
      v3 = v15;
      if ( v15 < 0 )
        _DbgPrintMessage(8, "pEnumWbemClassObject->Next failed with 0x%08X.", v15);
      if ( v25 )
      {
        memset(&pvarg, 0, sizeof(pvarg));
        VariantInit(&pvarg);
        v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v25 + 32LL))(
                v25,
                L"Name",
                0,
                &pvarg,
                0,
                0);
        if ( v16 >= 0 )
        {
          if ( pvarg.llVal )
          {
            v17 = SysStringLen(pvarg.bstrVal);
            v18 = pvarg.bstrVal;
          }
          else
          {
            v17 = SysStringLen((BSTR)L"Unknown App");
            v18 = L"Unknown App";
          }
          v19 = v17;
          v20 = StringCchCopyW(v13, v8, v18);
          v3 = v20;
          if ( v20 < 0 )
          {
            _DbgPrintMessage(8, "StringCchCopy failed with 0x%08X.", v20);
            v3 = 0;
          }
          v8 -= v19;
          v13 += v19 + 1;
          VariantClear(&pvarg);
        }
        else
        {
          _DbgPrintMessage(8, "pWbemClassObject->Get Name failed with 0x%08X.", v16);
          v3 = 0;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v25 = 0;
      }
      if ( v3 == 1 )
        break;
      if ( v3 < 0 )
        goto LABEL_55;
    }
    v3 = 0;
  }
  else
  {
    _DbgPrintMessage(
      8,
      "LocalAlloc for CSQMUtil::WRdsRdshSQMData.szRemoteAppNames failed: 0x%x in %s",
      (unsigned int)v3,
      "CSQMUtil::GetPublishAppList");
  }
LABEL_55:
  if ( v25 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    v25 = 0;
  }
  if ( v26 )
  {
    ((void (__fastcall *)(IUnknown *))v26->lpVtbl->Release)(v26);
    v26 = 0;
  }
  SysFreeString(v1);
  SysFreeString(v0);
  if ( pProxy )
  {
    ((void (__fastcall *)(IUnknown *))pProxy->lpVtbl->Release)(pProxy);
    pProxy = 0;
  }
  SysFreeString(v4);
  if ( ppv )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)ppv + 16LL))(ppv);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800411cc  push    rbp
0x1800411ce  push    rbx
0x1800411cf  push    rsi
0x1800411d0  push    rdi
0x1800411d1  push    r12
0x1800411d3  push    r13
0x1800411d5  push    r14
0x1800411d7  push    r15
0x1800411d9  mov     rbp, rsp
0x1800411dc  sub     rsp, 78h
0x1800411e0  xor     r14d, r14d
0x1800411e3  lea     rax, [rbp+var_28]
0x1800411e7  lea     r9, IID_IWbemLocator; riid
0x1800411ee  mov     [rbp+var_28], r14
0x1800411f2  xor     edx, edx; pUnkOuter
0x1800411f4  mov     [rbp+pProxy], r14
0x1800411f8  lea     rcx, CLSID_WbemLocator; rclsid
0x1800411ff  mov     [rbp+arg_10], r14
0x180041203  lea     r8d, [r14+1]; dwClsContext
0x180041207  mov     [rbp+arg_8], r14
0x18004120b  mov     r12d, r14d
0x18004120e  mov     [rbp+arg_0], r14d
0x180041212  mov     r13d, r14d
0x180041215  mov     [rsp+78h+ppv], rax; ppv
0x18004121a  call    cs:__imp_CoCreateInstance
0x180041220  mov     ebx, eax
0x180041222  test    eax, eax
0x180041224  jns     short loc_180041249
0x180041226  mov     r15d, r14d
0x180041229  lea     rdx, aCocreateinstan; "CoCreateInstance failed: 0x%x in %s"
0x180041230  mov     r8d, eax
0x180041233  lea     r9, aCsqmutilGetpub; "CSQMUtil::GetPublishAppList"
0x18004123a  mov     ecx, 8; int
0x18004123f  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041244  jmp     loc_180041661
0x180041249  lea     rcx, psz; "\\\\.\\root\\CIMV2\\TerminalServices"
0x180041250  call    cs:__imp_SysAllocString
0x180041256  mov     r15, rax
0x180041259  test    rax, rax
0x18004125c  jnz     short loc_180041270
0x18004125e  mov     r8d, 8007000Eh
0x180041264  lea     rdx, aSysallocstring_0; "SysAllocString bszNetworkResource faile"...
0x18004126b  mov     ebx, r8d
0x18004126e  jmp     short loc_180041233
0x180041270  mov     rcx, [rbp+var_28]
0x180041274  lea     rdx, [rbp+pProxy]
0x180041278  mov     [rsp+78h+var_38], rdx
0x18004127d  xor     r9d, r9d
0x180041280  mov     qword ptr [rsp+78h+dwCapabilities], r14
0x180041285  xor     r8d, r8d
0x180041288  mov     [rsp+78h+pAuthInfo], r14
0x18004128d  mov     rdx, r15
0x180041290  mov     rax, [rcx]
0x180041293  mov     [rsp+78h+dwImpLevel], r14d
0x180041298  mov     [rsp+78h+ppv], r14
0x18004129d  mov     rax, [rax+18h]
0x1800412a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800412a6  mov     ebx, eax
0x1800412a8  test    eax, eax
0x1800412aa  jns     short loc_1800412B8
0x1800412ac  lea     rdx, aPwbemlocatorCo; "pWbemLocator->ConnectServer() failed: 0"...
0x1800412b3  jmp     loc_180041230
0x1800412b8  mov     rcx, [rbp+pProxy]; pProxy
0x1800412bc  mov     edi, 3
0x1800412c1  mov     [rsp+78h+dwCapabilities], r14d; dwCapabilities
0x1800412c6  xor     r9d, r9d; pServerPrincName
0x1800412c9  mov     [rsp+78h+pAuthInfo], r14; pAuthInfo
0x1800412ce  xor     r8d, r8d; dwAuthzSvc
0x1800412d1  mov     [rsp+78h+dwImpLevel], edi; dwImpLevel
0x1800412d5  lea     esi, [rdi+3]
0x1800412d8  lea     edx, [rdi+7]; dwAuthnSvc
0x1800412db  mov     dword ptr [rsp+78h+ppv], esi; dwAuthnLevel
0x1800412df  call    cs:__imp_CoSetProxyBlanket
0x1800412e5  mov     ebx, eax
0x1800412e7  test    eax, eax
0x1800412e9  jns     short loc_1800412F7
0x1800412eb  lea     rdx, aCosetproxyblan_1; "CoSetProxyBlanket() failed: 0x%x in %s"
0x1800412f2  jmp     loc_180041230
0x1800412f7  lea     rcx, aSelectNameFrom; "SELECT Name FROM Win32_TSPublishedAppli"...
0x1800412fe  call    cs:__imp_SysAllocString
0x180041304  mov     r12, rax
0x180041307  test    rax, rax
0x18004130a  jnz     short loc_180041321
0x18004130c  mov     r8d, 8007000Eh
0x180041312  lea     rdx, aSysallocstring; "SysAllocString bszQuery failed: 0x%x in"...
0x180041319  mov     ebx, r8d
0x18004131c  jmp     loc_180041233
0x180041321  lea     rcx, aWql; "WQL"
0x180041328  call    cs:__imp_SysAllocString
0x18004132e  mov     r13, rax
0x180041331  test    rax, rax
0x180041334  jnz     short loc_18004134B
0x180041336  mov     r8d, 8007000Eh
0x18004133c  lea     rdx, aSysallocstring_1; "SysAllocString bszQueryLanguage failed:"...
0x180041343  mov     ebx, r8d
0x180041346  jmp     loc_180041233
0x18004134b  mov     rcx, [rbp+pProxy]
0x18004134f  lea     rdx, [rbp+arg_10]
0x180041353  mov     qword ptr [rsp+78h+dwImpLevel], rdx
0x180041358  xor     r9d, r9d
0x18004135b  mov     r8, r12
0x18004135e  mov     [rsp+78h+ppv], r14
0x180041363  mov     rdx, r13
0x180041366  mov     rax, [rcx]
0x180041369  mov     rax, [rax+0A0h]
0x180041370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180041375  mov     ebx, eax
0x180041377  test    eax, eax
0x180041379  jns     short loc_180041387
0x18004137b  lea     rdx, aPwbemservicesE; "pWbemServices->ExecQuery failed: 0x%x i"...
0x180041382  jmp     loc_180041230
0x180041387  mov     rcx, [rbp+arg_10]; pProxy
0x18004138b  xor     r9d, r9d; pServerPrincName
0x18004138e  mov     [rsp+78h+dwCapabilities], r14d; dwCapabilities
0x180041393  xor     r8d, r8d; dwAuthzSvc
0x180041396  mov     [rsp+78h+pAuthInfo], r14; pAuthInfo
0x18004139b  mov     [rsp+78h+dwImpLevel], edi; dwImpLevel
0x18004139f  lea     edx, [r9+0Ah]; dwAuthnSvc
0x1800413a3  mov     dword ptr [rsp+78h+ppv], esi; dwAuthnLevel
0x1800413a7  call    cs:__imp_CoSetProxyBlanket
0x1800413ad  mov     ebx, eax
0x1800413af  test    eax, eax
0x1800413b1  jns     short loc_1800413BF
0x1800413b3  lea     rdx, aCosetproxyblan; "CoSetProxyBlanket failed: 0x%x in %s"
0x1800413ba  jmp     loc_180041230
0x1800413bf  mov     rsi, r14
0x1800413c2  mov     rcx, [rbp+arg_10]
0x1800413c6  lea     rdx, [rbp+arg_0]
0x1800413ca  mov     [rsp+78h+ppv], rdx
0x1800413cf  lea     r9, [rbp+arg_8]
0x1800413d3  mov     edx, 1388h
0x1800413d8  mov     r8d, 1
0x1800413de  mov     rax, [rcx]
0x1800413e1  mov     rax, [rax+20h]
0x1800413e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800413ea  mov     ebx, eax
0x1800413ec  test    eax, eax
0x1800413ee  jns     short loc_180041404
0x1800413f0  mov     r8d, eax
0x1800413f3  lea     rdx, aPenumwbemclass; "pEnumWbemClassObject->Next failed with "...
0x1800413fa  mov     ecx, 8; int
0x1800413ff  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041404  cmp     [rbp+arg_8], r14
0x180041408  jz      loc_1800414A5
0x18004140e  xorps   xmm0, xmm0
0x180041411  lea     rcx, [rbp+pvarg]; pvarg
0x180041415  xor     eax, eax
0x180041417  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004141b  mov     qword ptr [rbp+pvarg+10h], rax
0x18004141f  call    cs:__imp_VariantInit
0x180041425  mov     rcx, [rbp+arg_8]
0x180041429  lea     r9, [rbp+pvarg]
0x18004142d  mov     qword ptr [rsp+78h+dwImpLevel], r14
0x180041432  lea     rdx, aName; "Name"
0x180041439  xor     r8d, r8d
0x18004143c  mov     [rsp+78h+ppv], r14
0x180041441  mov     rax, [rcx]
0x180041444  mov     rax, [rax+20h]
0x180041448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004144d  mov     ebx, eax
0x18004144f  test    eax, eax
0x180041451  jns     short loc_180041469
0x180041453  mov     r8d, eax
0x180041456  lea     rdx, aPwbemclassobje; "pWbemClassObject->Get Name failed with "...
0x18004145d  mov     ecx, 8; int
0x180041462  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041467  jmp     short loc_180041491
0x180041469  mov     rcx, qword ptr [rbp+pvarg+8]
0x18004146d  test    rcx, rcx
0x180041470  jnz     short loc_180041479
0x180041472  lea     rcx, pbstr; "Unknown App"
0x180041479  call    cs:__imp_SysStringLen
0x18004147f  mov     eax, eax
0x180041481  lea     rcx, [rbp+pvarg]; pvarg
0x180041485  inc     rax
0x180041488  add     rsi, rax
0x18004148b  call    cs:__imp_VariantClear
0x180041491  mov     rcx, [rbp+arg_8]
0x180041495  mov     rax, [rcx]
0x180041498  mov     rax, [rax+10h]
0x18004149c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414a1  mov     [rbp+arg_8], r14
0x1800414a5  cmp     ebx, 1
0x1800414a8  jz      short loc_1800414B2
0x1800414aa  test    ebx, ebx
0x1800414ac  jns     loc_1800413C2
0x1800414b2  mov     rcx, [rbp+arg_10]
0x1800414b6  mov     rax, [rcx]
0x1800414b9  mov     rax, [rax+18h]
0x1800414bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800414c2  mov     ebx, eax
0x1800414c4  test    eax, eax
0x1800414c6  jns     short loc_1800414D4
0x1800414c8  lea     rdx, aPenumwbemclass_0; "pEnumWbemClassObject->Reset failed: 0x%"...
0x1800414cf  jmp     loc_180041230
0x1800414d4  lea     rdx, ds:2[rsi*2]; uBytes
0x1800414dc  mov     ecx, 40h ; '@'; uFlags
0x1800414e1  call    cs:__imp_LocalAlloc
0x1800414e7  mov     cs:hMem, rax
0x1800414ee  mov     rdi, rax
0x1800414f1  test    rax, rax
0x1800414f4  jnz     short loc_180041525
0x1800414f6  call    cs:__imp_GetLastError
0x1800414fc  mov     ebx, eax
0x1800414fe  test    eax, eax
0x180041500  jle     short loc_18004150B
0x180041502  movzx   ebx, ax
0x180041505  or      ebx, 80070000h
0x18004150b  test    ebx, ebx
0x18004150d  jns     short loc_18004151E
0x18004150f  mov     r8d, ebx
0x180041512  lea     rdx, aLocalallocForC; "LocalAlloc for CSQMUtil::WRdsRdshSQMDat"...
0x180041519  jmp     loc_180041233
0x18004151e  mov     rdi, cs:hMem
0x180041525  mov     rcx, [rbp+arg_10]
0x180041529  lea     rdx, [rbp+arg_0]
0x18004152d  mov     [rsp+78h+ppv], rdx
0x180041532  lea     r9, [rbp+arg_8]
0x180041536  mov     edx, 1388h
0x18004153b  mov     r8d, 1
0x180041541  mov     rax, [rcx]
0x180041544  mov     rax, [rax+20h]
0x180041548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004154d  mov     ebx, eax
0x18004154f  test    eax, eax
0x180041551  jns     short loc_180041567
0x180041553  mov     r8d, eax
0x180041556  lea     rdx, aPenumwbemclass; "pEnumWbemClassObject->Next failed with "...
0x18004155d  mov     ecx, 8; int
0x180041562  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180041567  cmp     [rbp+arg_8], r14
0x18004156b  jz      loc_18004164F
0x180041571  xorps   xmm0, xmm0
0x180041574  lea     rcx, [rbp+pvarg]; pvarg
0x180041578  xor     eax, eax
0x18004157a  movups  xmmword ptr [rbp+pvarg], xmm0
0x18004157e  mov     qword ptr [rbp+pvarg+10h], rax
0x180041582  call    cs:__imp_VariantInit
0x180041588  mov     rcx, [rbp+arg_8]
0x18004158c  lea     r9, [rbp+pvarg]
0x180041590  mov     qword ptr [rsp+78h+dwImpLevel], r14
0x180041595  lea     rdx, aName; "Name"
0x18004159c  xor     r8d, r8d
0x18004159f  mov     [rsp+78h+ppv], r14
0x1800415a4  mov     rax, [rcx]
0x1800415a7  mov     rax, [rax+20h]
0x1800415ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800415b0  test    eax, eax
0x1800415b2  jns     short loc_1800415CD
0x1800415b4  mov     r8d, eax
0x1800415b7  lea     rdx, aPwbemclassobje; "pWbemClassObject->Get Name failed with "...
0x1800415be  mov     ecx, 8; int
0x1800415c3  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800415c8  mov     ebx, r14d
0x1800415cb  jmp     short loc_18004163B
0x1800415cd  mov     rcx, qword ptr [rbp+pvarg+8]; pbstr
0x1800415d1  test    rcx, rcx
0x1800415d4  jz      short loc_1800415E2
0x1800415d6  call    cs:__imp_SysStringLen
0x1800415dc  mov     r8, qword ptr [rbp+pvarg+8]
0x1800415e0  jmp     short loc_1800415F6
0x1800415e2  lea     rcx, pbstr; "Unknown App"
0x1800415e9  call    cs:__imp_SysStringLen
0x1800415ef  lea     r8, pbstr; "Unknown App"
0x1800415f6  mov     rdx, rsi; unsigned __int64
0x1800415f9  mov     rcx, rdi; unsigned __int16 *
0x1800415fc  mov     r14d, eax
0x1800415ff  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180041604  mov     ebx, eax
0x180041606  test    eax, eax
0x180041608  jns     short loc_180041620
0x18004160a  mov     r8d, eax
0x18004160d  lea     rdx, aStringcchcopyF; "StringCchCopy failed with 0x%08X."
0x180041614  mov     ecx, 8; int
0x180041619  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18004161e  xor     ebx, ebx
0x180041620  mov     eax, r14d
0x180041623  lea     rcx, [rbp+pvarg]; pvarg
0x180041627  sub     rsi, rax
0x18004162a  lea     eax, [r14+1]
0x18004162e  lea     rdi, [rdi+rax*2]
0x180041632  call    cs:__imp_VariantClear
0x180041638  xor     r14d, r14d
0x18004163b  mov     rcx, [rbp+arg_8]
0x18004163f  mov     rax, [rcx]
0x180041642  mov     rax, [rax+10h]
0x180041646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004164b  mov     [rbp+arg_8], r14
0x18004164f  cmp     ebx, 1
0x180041652  jz      short loc_18004165E
0x180041654  test    ebx, ebx
0x180041656  jns     loc_180041525
0x18004165c  jmp     short loc_180041661
0x18004165e  mov     ebx, r14d
0x180041661  mov     rcx, [rbp+arg_8]
0x180041665  test    rcx, rcx
0x180041668  jz      short loc_18004167A
0x18004166a  mov     rax, [rcx]
0x18004166d  mov     rax, [rax+10h]
0x180041671  call    _guard_dispatch_icall$thunk$10345483385596137414
  ... truncated ...
```
