# InProcClientAPIStub::UiaNode_GetRuntimeId(char *)

- ea: `0x1800c1680`
- end: `0x1800c1c67`
- name: `?UiaNode_GetRuntimeId@InProcClientAPIStub@@SAJPEAD@Z`
- size: `1511`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x1800320ec`
- `0x1800c1680`
- `0x1800c1c70`
- `0x1800c2068`
- `0x1800c20c0`
- `0x180186cd0`
- `0x1801e8320`
- `0x1801e8344`
- `0x1801e88a0`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c1781`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800c1781`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c1753`
- `ext-ms-win-rtcore-ntuser-window-ext-l1-1-0!GetClassNameW` at `0x1800c1753`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c19bc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c19f9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c1ab7`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c19bc`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c19f9`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1800c1ab7`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1873`
- `OLEAUT32!__imp_SafeArrayGetDim` at `0x1800c1873`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c18e5`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1800c18e5`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c18c8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1800c18c8`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c190d`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x1800c190d`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c197e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1b83`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c197e`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x1800c1b83`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1892`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1800c1892`

## string_xrefs

- `0x1800c1a4b`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1b4e`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1b64`: `onecore\windows\accessibletech\common\SafeArray.h`
- `0x1800c1a74`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`
- `0x1800c1c2e`: `onecore\windows\accessibletech\uiautomationcore\uianode.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall InProcClientAPIStub::UiaNode_GetRuntimeId(char *a1)
{
  __int64 v1; // rdi
  __int64 v2; // rbx
  struct tagSAFEARRAY **v3; // r15
  __int64 v4; // rsi
  __int64 v5; // rdx
  __int64 (__fastcall ***v6)(_QWORD, GUID *, LONG *); // rsi
  __int64 v7; // rcx
  BOOL v8; // ecx
  int RuntimeIdFromProviderEntryPoint; // eax
  unsigned int RuntimeIdFromPartial; // ebx
  int v11; // eax
  int v12; // ecx
  struct IRawElementProviderFragment *v13; // rsi
  int v14; // ecx
  int v15; // ebx
  HRESULT Vartype; // eax
  HRESULT LBound; // eax
  HRESULT UBound; // eax
  unsigned __int64 v19; // rax
  _DWORD *v20; // rdi
  unsigned int v21; // ecx
  int i; // ebx
  SAFEARRAY *v24; // rcx
  __int64 v25; // r14
  __int64 v26; // rdx
  __int64 v27; // r9
  int lpString2; // [rsp+20h] [rbp-E0h]
  int lpString2a; // [rsp+20h] [rbp-E0h]
  int lpString2b; // [rsp+20h] [rbp-E0h]
  VARTYPE pvt; // [rsp+30h] [rbp-D0h] BYREF
  SAFEARRAY *psa; // [rsp+38h] [rbp-C8h] BYREF
  LONG plUbound; // [rsp+40h] [rbp-C0h] BYREF
  LONG plLbound[2]; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v35; // [rsp+50h] [rbp-B0h]
  SAFEARRAY *v36; // [rsp+58h] [rbp-A8h]
  int v37; // [rsp+60h] [rbp-A0h]
  void *ppvData; // [rsp+68h] [rbp-98h] BYREF
  struct IRawElementProviderFragment *v39; // [rsp+70h] [rbp-90h] BYREF
  WCHAR ClassName[128]; // [rsp+80h] [rbp-80h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1D8h] [rbp+D8h]

  v1 = *(_QWORD *)a1;
  v2 = *((unsigned int *)a1 + 2);
  v3 = (struct tagSAFEARRAY **)*((_QWORD *)a1 + 2);
  *v3 = 0;
  if ( (unsigned int)v2 < *(_DWORD *)(v1 + 240)
    && (unsigned int)v2 < 6
    && (v4 = (unsigned int)v2, *(_BYTE *)(v1 + 24 * v2 + 104)) )
  {
    wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(plLbound, v1 + 8 * (3 * v2 + 12));
    v25 = *(_QWORD *)plLbound;
    if ( *(_QWORD *)plLbound )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plLbound + 16LL))(*(_QWORD *)plLbound);
    if ( v25 )
      return (*(unsigned int (__fastcall **)(__int64, struct tagSAFEARRAY **))(*(_QWORD *)v25 + 80LL))(v25, v3);
  }
  else
  {
    v4 = v2;
  }
  if ( (unsigned int)v2 >= *(_DWORD *)(v1 + 240) )
    return 0;
  if ( (unsigned int)v2 >= 6 )
    return 0;
  v5 = v1 + 24 * v4;
  if ( *(_BYTE *)(v5 + 104) )
    return 0;
  _mm_lfence();
  v6 = *(__int64 (__fastcall ****)(_QWORD, GUID *, LONG *))(v1 + 24 * v4 + 96);
  if ( !v6 )
    return 0;
  if ( (v7 = *(_QWORD *)(v1 + 256)) == 0
    || *(_DWORD *)(v7 + 40)
    || !*(_DWORD *)(v5 + 108)
    || *(_BYTE *)(v7 + 60)
    || (!GetClassNameW(*(HWND *)(v7 + 24), ClassName, 128)
      ? (v8 = 0)
      : (v8 = CompareStringW(0x7Fu, 1u, ClassName, -1, L"Chrome_RenderWidgetHostHWND", -1) == 2),
        !v8) )
  {
    LOBYTE(pvt) = 0;
    RuntimeIdFromProviderEntryPoint = UiaNode::TryGetRuntimeIdFromProviderEntryPoint((UiaNode *)v1, v3, (bool *)&pvt);
    RuntimeIdFromPartial = RuntimeIdFromProviderEntryPoint;
    if ( RuntimeIdFromProviderEntryPoint < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xBB3,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
        (const char *)(unsigned int)RuntimeIdFromProviderEntryPoint,
        lpString2);
      return RuntimeIdFromPartial;
    }
    if ( (_BYTE)pvt )
      return 0;
  }
  *(_QWORD *)plLbound = 0;
  v11 = (**v6)(v6, &GUID_f7063da8_8359_439c_9297_bbc5299a7d87, plLbound);
  v13 = *(struct IRawElementProviderFragment **)plLbound;
  if ( v11 )
    v13 = 0;
  v39 = v13;
  if ( !v13 )
    return 0;
  psa = 0;
  *(_QWORD *)plLbound = L"IRawElementProviderFragment::GetRuntimeId";
  v35 = 0;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v12,
      (unsigned int)UiaProviderCallout_Start,
      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
      0,
      0);
  v15 = ((__int64 (__fastcall *)(struct IRawElementProviderFragment *, SAFEARRAY **))v13->lpVtbl->GetRuntimeId)(
          v13,
          &psa);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McTemplateU0zqq_EventWriteTransfer(
      v14,
      (unsigned int)UiaProviderCallout_Stop,
      (unsigned int)L"IRawElementProviderFragment::GetRuntimeId",
      0,
      0);
  if ( v15 == -2147220991 )
  {
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v13->lpVtbl->Release)(v13);
    return (unsigned int)-2147220991;
  }
  if ( v15 < 0 || !psa )
  {
    if ( psa )
    {
      SafeArrayDestroy(psa);
      psa = 0;
    }
    goto LABEL_49;
  }
  v37 = 0;
  ppvData = 0;
  v36 = psa;
  if ( SafeArrayGetDim(psa) != 1 )
  {
    v27 = 2147942487LL;
    RuntimeIdFromPartial = -2147024809;
    v26 = 92;
    goto LABEL_66;
  }
  pvt = 0;
  Vartype = SafeArrayGetVartype(v36, &pvt);
  RuntimeIdFromPartial = Vartype;
  if ( Vartype < 0 )
  {
    v26 = 95;
    v27 = (unsigned int)Vartype;
    goto LABEL_66;
  }
  if ( pvt != 3 && pvt != 22 )
  {
    v27 = 2147942487LL;
    RuntimeIdFromPartial = -2147024809;
    v26 = 106;
LABEL_66:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v26,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)v27,
      lpString2);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)RuntimeIdFromPartial,
      lpString2b);
    v24 = v36;
    if ( v36 )
      goto LABEL_67;
    goto LABEL_53;
  }
  plLbound[0] = 0;
  plUbound = 0;
  LBound = SafeArrayGetLBound(v36, 1u, plLbound);
  RuntimeIdFromPartial = LBound;
  if ( LBound < 0 )
  {
    v26 = 111;
LABEL_63:
    v27 = (unsigned int)LBound;
    goto LABEL_66;
  }
  UBound = SafeArrayGetUBound(v36, 1u, &plUbound);
  RuntimeIdFromPartial = UBound;
  if ( UBound < 0 )
  {
    v26 = 112;
    v27 = (unsigned int)UBound;
    goto LABEL_66;
  }
  v37 = plUbound - plLbound[0] + 1;
  LBound = SafeArrayAccessData(v36, &ppvData);
  RuntimeIdFromPartial = LBound;
  if ( LBound < 0 )
  {
    v26 = 115;
    goto LABEL_63;
  }
  v19 = 4LL * (unsigned int)v37;
  if ( !is_mul_ok((unsigned int)v37, 4u) )
    v19 = -1;
  v20 = operator new[](v19, (const struct std::nothrow_t *)std::nothrow);
  if ( !v20 )
  {
    RuntimeIdFromPartial = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA2,
      (unsigned int)"onecore\\windows\\accessibletech\\common\\SafeArray.h",
      (const char *)0x8007000ELL,
      lpString2);
    v24 = v36;
    if ( v36 )
LABEL_67:
      SafeArrayUnaccessData(v24);
LABEL_53:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xBD6,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\uianode.cpp",
      (const char *)RuntimeIdFromPartial,
      lpString2a);
    operator delete(0);
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v13->lpVtbl->Release)(v13);
    return RuntimeIdFromPartial;
  }
  v21 = 0;
  for ( i = v37; v21 < v37; i = v37 )
  {
    v20[v21] = *((_DWORD *)ppvData + v21);
    ++v21;
  }
  if ( v36 )
    SafeArrayUnaccessData(v36);
  if ( !i )
  {
    operator delete(v20);
    AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(&psa);
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v39);
    return 0;
  }
  if ( i == 1 || *v20 != 3 )
  {
    *v3 = psa;
    psa = 0;
    operator delete(v20);
    if ( psa )
    {
      SafeArrayDestroy(psa);
      psa = 0;
    }
LABEL_49:
    ((void (__fastcall *)(struct IRawElementProviderFragment *))v13->lpVtbl->Release)(v13);
    return 0;
  }
  RuntimeIdFromPartial = UiaNode::ProviderGetRuntimeIdFromPartial(v13, v20, i, v3);
  operator delete(v20);
  if ( psa )
  {
    SafeArrayDestroy(psa);
    psa = 0;
  }
  ((void (__fastcall *)(struct IRawElementProviderFragment *))v13->lpVtbl->Release)(v13);
  return RuntimeIdFromPartial;
}

```

## disassembly

```asm
0x1800c1680  push    rbp
0x1800c1682  push    rbx
0x1800c1683  push    rsi
0x1800c1684  push    rdi
0x1800c1685  push    r12
0x1800c1687  push    r13
0x1800c1689  push    r14
0x1800c168b  push    r15
0x1800c168d  lea     rbp, [rsp-98h]
0x1800c1695  sub     rsp, 198h
0x1800c169c  mov     rax, cs:__security_cookie
0x1800c16a3  xor     rax, rsp
0x1800c16a6  mov     [rbp+0D0h+var_50], rax
0x1800c16ad  xor     r12d, r12d
0x1800c16b0  mov     rdi, [rcx]
0x1800c16b3  mov     ebx, [rcx+8]
0x1800c16b6  mov     r15, [rcx+10h]
0x1800c16ba  mov     [r15], r12
0x1800c16bd  cmp     ebx, [rdi+0F0h]
0x1800c16c3  jnb     short loc_1800C16DB
0x1800c16c5  cmp     ebx, 6
0x1800c16c8  jnb     short loc_1800C16DB
0x1800c16ca  mov     esi, ebx
0x1800c16cc  lea     rax, [rbx+rbx*2]
0x1800c16d0  cmp     [rdi+rax*8+68h], r12b
0x1800c16d5  jnz     loc_1800C1AD7
0x1800c16db  mov     rsi, rbx
0x1800c16de  cmp     ebx, [rdi+0F0h]
0x1800c16e4  jnb     loc_1800C1A14
0x1800c16ea  cmp     ebx, 6
0x1800c16ed  jnb     loc_1800C1A14
0x1800c16f3  lea     rax, [rsi+rsi*2]
0x1800c16f7  lea     rdx, [rdi+rax*8]
0x1800c16fb  cmp     byte ptr [rdx+68h], 0
0x1800c16ff  jnz     loc_1800C1A14
0x1800c1705  lfence
0x1800c1708  lea     rax, [rsi+rsi*2]
0x1800c170c  mov     rsi, [rdi+rax*8+60h]
0x1800c1711  test    rsi, rsi
0x1800c1714  jz      loc_1800C1A14
0x1800c171a  mov     rcx, [rdi+100h]
0x1800c1721  mov     r13, 0FFFFFFFFFFFFFFFFh
0x1800c1728  mov     r14d, 1
0x1800c172e  test    rcx, rcx
0x1800c1731  jz      short loc_1800C1795
0x1800c1733  cmp     dword ptr [rcx+28h], 0
0x1800c1737  jnz     short loc_1800C1795
0x1800c1739  cmp     dword ptr [rdx+6Ch], 0
0x1800c173d  jz      short loc_1800C1795
0x1800c173f  cmp     byte ptr [rcx+3Ch], 0
0x1800c1743  jnz     short loc_1800C1795
0x1800c1745  mov     r8d, 80h; nMaxCount
0x1800c174b  lea     rdx, [rbp+0D0h+ClassName]; lpClassName
0x1800c174f  mov     rcx, [rcx+18h]; hWnd
0x1800c1753  call    cs:__imp_GetClassNameW
0x1800c1759  test    eax, eax
0x1800c175b  jz      loc_1800C1B98
0x1800c1761  mov     [rsp+1D0h+cchCount2], r13d; cchCount2
0x1800c1766  lea     rax, aChromeRenderwi; "Chrome_RenderWidgetHostHWND"
0x1800c176d  mov     [rsp+1D0h+lpString2], rax; int
0x1800c1772  mov     r9d, r13d; cchCount1
0x1800c1775  lea     r8, [rbp+0D0h+ClassName]; lpString1
0x1800c1779  mov     edx, r14d; dwCmpFlags
0x1800c177c  mov     ecx, 7Fh; Locale
0x1800c1781  call    cs:__imp_CompareStringW
0x1800c1787  mov     ecx, r12d
0x1800c178a  cmp     eax, 2
0x1800c178d  cmovz   ecx, r14d
0x1800c1791  test    ecx, ecx
0x1800c1793  jnz     short loc_1800C17BF
0x1800c1795  mov     byte ptr [rsp+1D0h+pvt], 0
0x1800c179a  lea     r8, [rsp+1D0h+pvt]; bool *
0x1800c179f  mov     rdx, r15; struct tagSAFEARRAY **
0x1800c17a2  mov     rcx, rdi; this
0x1800c17a5  call    ?TryGetRuntimeIdFromProviderEntryPoint@UiaNode@@AEBAJPEAPEAUtagSAFEARRAY@@PEA_N@Z; UiaNode::TryGetRuntimeIdFromProviderEntryPoint(tagSAFEARRAY * *,bool *)
0x1800c17aa  mov     ebx, eax
0x1800c17ac  test    eax, eax
0x1800c17ae  js      loc_1800C1C24
0x1800c17b4  cmp     byte ptr [rsp+1D0h+pvt], 0
0x1800c17b9  jnz     loc_1800C1A14
0x1800c17bf  mov     qword ptr [rsp+1D0h+plLbound], r12
0x1800c17c4  mov     rax, [rsi]
0x1800c17c7  lea     r8, [rsp+1D0h+plLbound]
0x1800c17cc  lea     rdx, _GUID_f7063da8_8359_439c_9297_bbc5299a7d87
0x1800c17d3  mov     rcx, rsi
0x1800c17d6  mov     rax, [rax]
0x1800c17d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c17de  mov     rsi, qword ptr [rsp+1D0h+plLbound]
0x1800c17e3  test    eax, eax
0x1800c17e5  cmovnz  rsi, r12
0x1800c17e9  mov     [rsp+1D0h+var_160], rsi
0x1800c17ee  test    rsi, rsi
0x1800c17f1  jz      loc_1800C1AAD
0x1800c17f7  mov     [rsp+1D0h+psa], r12
0x1800c17fc  lea     rdi, aIrawelementpro_0; "IRawElementProviderFragment::GetRuntime"...
0x1800c1803  mov     qword ptr [rsp+1D0h+plLbound], rdi
0x1800c1808  mov     [rsp+1D0h+var_180], r12
0x1800c180d  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800c1814  jnz     loc_1800C1BC5
0x1800c181a  mov     rax, [rsi]
0x1800c181d  lea     rdx, [rsp+1D0h+psa]
0x1800c1822  mov     rcx, rsi
0x1800c1825  mov     rax, [rax+20h]
0x1800c1829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c182e  mov     ebx, eax
0x1800c1830  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800c1837  jnz     loc_1800C1BE1
0x1800c183d  cmp     ebx, 80040201h
0x1800c1843  jz      loc_1800C1BA0
0x1800c1849  mov     rcx, [rsp+1D0h+psa]; psa
0x1800c184e  test    ebx, ebx
0x1800c1850  js      loc_1800C1AB2
0x1800c1856  test    rcx, rcx
0x1800c1859  jz      loc_1800C1AB2
0x1800c185f  mov     [rsp+1D0h+var_178], r12
0x1800c1864  mov     [rsp+1D0h+var_170], r12d
0x1800c1869  mov     [rsp+1D0h+ppvData], r12
0x1800c186e  mov     [rsp+1D0h+var_178], rcx
0x1800c1873  call    cs:__imp_SafeArrayGetDim
0x1800c1879  cmp     eax, 1
0x1800c187c  jnz     loc_1800C1B39
0x1800c1882  mov     [rsp+1D0h+pvt], r12w
0x1800c1888  lea     rdx, [rsp+1D0h+pvt]; pvt
0x1800c188d  mov     rcx, [rsp+1D0h+var_178]; psa
0x1800c1892  call    cs:__imp_SafeArrayGetVartype
0x1800c1898  mov     ebx, eax
0x1800c189a  test    eax, eax
0x1800c189c  js      loc_1800C1B8E
0x1800c18a2  movzx   eax, [rsp+1D0h+pvt]
0x1800c18a7  cmp     ax, 3
0x1800c18ab  jnz     loc_1800C1C07
0x1800c18b1  mov     [rsp+1D0h+plLbound], r12d
0x1800c18b6  mov     [rsp+1D0h+plUbound], r12d
0x1800c18bb  lea     r8, [rsp+1D0h+plLbound]; plLbound
0x1800c18c0  mov     edx, r14d; nDim
0x1800c18c3  mov     rcx, [rsp+1D0h+var_178]; psa
0x1800c18c8  call    cs:__imp_SafeArrayGetLBound
0x1800c18ce  mov     ebx, eax
0x1800c18d0  test    eax, eax
0x1800c18d2  js      loc_1800C1B25
0x1800c18d8  lea     r8, [rsp+1D0h+plUbound]; plUbound
0x1800c18dd  mov     edx, r14d; nDim
0x1800c18e0  mov     rcx, [rsp+1D0h+var_178]; psa
0x1800c18e5  call    cs:__imp_SafeArrayGetUBound
0x1800c18eb  mov     ebx, eax
0x1800c18ed  test    eax, eax
0x1800c18ef  js      loc_1800C1B2F
0x1800c18f5  mov     eax, [rsp+1D0h+plUbound]
0x1800c18f9  sub     eax, [rsp+1D0h+plLbound]
0x1800c18fd  inc     eax
0x1800c18ff  mov     [rsp+1D0h+var_170], eax
0x1800c1903  lea     rdx, [rsp+1D0h+ppvData]; ppvData
0x1800c1908  mov     rcx, [rsp+1D0h+var_178]; psa
0x1800c190d  call    cs:__imp_SafeArrayAccessData
0x1800c1913  mov     ebx, eax
0x1800c1915  test    eax, eax
0x1800c1917  js      loc_1800C1BFD
0x1800c191d  mov     ecx, [rsp+1D0h+var_170]
0x1800c1921  mov     eax, 4
0x1800c1926  mul     rcx
0x1800c1929  cmovb   rax, r13
0x1800c192d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c1934  mov     rcx, rax; unsigned __int64
0x1800c1937  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c193c  mov     rdi, rax
0x1800c193f  test    rax, rax
0x1800c1942  jz      loc_1800C1A3C
0x1800c1948  mov     ecx, r12d
0x1800c194b  mov     ebx, [rsp+1D0h+var_170]
0x1800c194f  test    ebx, ebx
0x1800c1951  jz      short loc_1800C1974
0x1800c1953  mov     edx, ecx
0x1800c1955  lea     r8, ds:0[rdx*4]
0x1800c195d  mov     rdx, [rsp+1D0h+ppvData]
0x1800c1962  mov     eax, [rdx+r8]
0x1800c1966  mov     [r8+rdi], eax
0x1800c196a  inc     ecx
0x1800c196c  mov     ebx, [rsp+1D0h+var_170]
0x1800c1970  cmp     ecx, ebx
0x1800c1972  jb      short loc_1800C1953
0x1800c1974  mov     rcx, [rsp+1D0h+var_178]; psa
0x1800c1979  test    rcx, rcx
0x1800c197c  jz      short loc_1800C1984
0x1800c197e  call    cs:__imp_SafeArrayUnaccessData
0x1800c1984  test    ebx, ebx
0x1800c1986  jz      loc_1800C1C44
0x1800c198c  cmp     ebx, 1
0x1800c198f  jz      short loc_1800C19D9
0x1800c1991  cmp     dword ptr [rdi], 3
0x1800c1994  jnz     short loc_1800C19D9
0x1800c1996  mov     r9, r15; struct tagSAFEARRAY **
0x1800c1999  mov     r8d, ebx; int
0x1800c199c  mov     rdx, rdi; int *
0x1800c199f  mov     rcx, rsi; struct IRawElementProviderFragment *
0x1800c19a2  call    ?ProviderGetRuntimeIdFromPartial@UiaNode@@SAJPEAUIRawElementProviderFragment@@PEBHHPEAPEAUtagSAFEARRAY@@@Z; UiaNode::ProviderGetRuntimeIdFromPartial(IRawElementProviderFragment *,int const *,int,tagSAFEARRAY * *)
0x1800c19a7  mov     ebx, eax
0x1800c19a9  mov     rcx, rdi; Block
0x1800c19ac  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c19b1  nop
0x1800c19b2  mov     rcx, [rsp+1D0h+psa]; psa
0x1800c19b7  test    rcx, rcx
0x1800c19ba  jz      short loc_1800C19C7
0x1800c19bc  call    cs:__imp_SafeArrayDestroy
0x1800c19c2  mov     [rsp+1D0h+psa], r12
0x1800c19c7  mov     rax, [rsi]
0x1800c19ca  mov     rcx, rsi
0x1800c19cd  mov     rax, [rax+10h]
0x1800c19d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c19d6  nop
0x1800c19d7  jmp     short loc_1800C1A17
0x1800c19d9  mov     rax, [rsp+1D0h+psa]
0x1800c19de  mov     [r15], rax
0x1800c19e1  mov     [rsp+1D0h+psa], r12
0x1800c19e6  mov     rcx, rdi; Block
0x1800c19e9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c19ee  nop
0x1800c19ef  mov     rcx, [rsp+1D0h+psa]; psa
0x1800c19f4  test    rcx, rcx
0x1800c19f7  jz      short loc_1800C1A04
0x1800c19f9  call    cs:__imp_SafeArrayDestroy
0x1800c19ff  mov     [rsp+1D0h+psa], r12
0x1800c1a04  mov     rax, [rsi]
0x1800c1a07  mov     rcx, rsi
0x1800c1a0a  mov     rax, [rax+10h]
0x1800c1a0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1a13  nop
0x1800c1a14  mov     ebx, r12d
0x1800c1a17  mov     eax, ebx
0x1800c1a19  mov     rcx, [rbp+0D0h+var_50]
0x1800c1a20  xor     rcx, rsp; StackCookie
0x1800c1a23  call    __security_check_cookie
0x1800c1a28  add     rsp, 198h
0x1800c1a2f  pop     r15
0x1800c1a31  pop     r14
0x1800c1a33  pop     r13
0x1800c1a35  pop     r12
0x1800c1a37  pop     rdi
0x1800c1a38  pop     rsi
0x1800c1a39  pop     rbx
0x1800c1a3a  pop     rbp
0x1800c1a3b  retn
0x1800c1a3c  mov     rcx, [rbp+0D8h]; this
0x1800c1a43  mov     ebx, 8007000Eh
0x1800c1a48  mov     r9d, ebx; char *
0x1800c1a4b  lea     r8, aOnecoreWindows_145; "onecore\\windows\\accessibletech\\commo"...
0x1800c1a52  mov     edx, 0A2h; void *
0x1800c1a57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1a5c  mov     rcx, [rsp+1D0h+var_178]
0x1800c1a61  test    rcx, rcx
0x1800c1a64  jnz     loc_1800C1B83
0x1800c1a6a  mov     rcx, [rbp+0D8h]; this
0x1800c1a71  mov     r9d, ebx; char *
0x1800c1a74  lea     r8, aOnecoreWindows_137; "onecore\\windows\\accessibletech\\uiaut"...
0x1800c1a7b  mov     edx, 0BD6h; void *
0x1800c1a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800c1a85  xor     ecx, ecx; Block
0x1800c1a87  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800c1a8c  nop
0x1800c1a8d  lea     rcx, [rsp+1D0h+psa]
0x1800c1a92  call    ?SafeRelease@?$AutoCleanupInfo@PEAUtagSAFEARRAY@@@@SAXAEAPEAUtagSAFEARRAY@@@Z; AutoCleanupInfo<tagSAFEARRAY *>::SafeRelease(tagSAFEARRAY * &)
0x1800c1a97  nop
0x1800c1a98  mov     rax, [rsi]
0x1800c1a9b  mov     rcx, rsi
0x1800c1a9e  mov     rax, [rax+10h]
0x1800c1aa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1aa7  nop
0x1800c1aa8  jmp     loc_1800C1A17
0x1800c1aad  jmp     loc_1800C1A14
0x1800c1ab2  test    rcx, rcx
0x1800c1ab5  jz      short loc_1800C1AC2
0x1800c1ab7  call    cs:__imp_SafeArrayDestroy
0x1800c1abd  mov     [rsp+1D0h+psa], r12
0x1800c1ac2  mov     rax, [rsi]
0x1800c1ac5  mov     rcx, rsi
0x1800c1ac8  mov     rax, [rax+10h]
0x1800c1acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1ad1  nop
0x1800c1ad2  jmp     loc_1800C1A14
0x1800c1ad7  add     rax, 0Ch
0x1800c1adb  lea     rdx, [rdi+rax*8]
0x1800c1adf  lea     rcx, [rsp+1D0h+plLbound]
0x1800c1ae4  call    ??$com_query@VIUiaNode@@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@wil@@YA?AV?$com_ptr_t@VIUiaNode@@Uerr_exception_policy@wil@@@0@AEAV?$ComPtr@UIUnknown@@@WRL@Microsoft@@@Z; wil::com_query<IUiaNode,Microsoft::WRL::ComPtr<IUnknown> &>(Microsoft::WRL::ComPtr<IUnknown> &)
0x1800c1ae9  mov     r14, qword ptr [rsp+1D0h+plLbound]
0x1800c1aee  test    r14, r14
0x1800c1af1  jz      short loc_1800C1B03
0x1800c1af3  mov     rax, [r14]
0x1800c1af6  mov     rcx, r14
0x1800c1af9  mov     rax, [rax+10h]
0x1800c1afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b02  nop
0x1800c1b03  test    r14, r14
0x1800c1b06  jz      loc_1800C16DE
0x1800c1b0c  mov     rax, [r14]
0x1800c1b0f  mov     rdx, r15
0x1800c1b12  mov     rcx, r14
0x1800c1b15  mov     rax, [rax+50h]
0x1800c1b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c1b1e  mov     ebx, eax
0x1800c1b20  jmp     loc_1800C1A17
0x1800c1b25  mov     edx, 6Fh ; 'o'
  ... truncated ...
```
