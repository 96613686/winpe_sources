# AMovieSetupRegisterServer

- ea: `0x1800026b8`
- end: `0x1800029c0`
- name: `AMovieSetupRegisterServer`
- size: `776`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1800023c4`

## callees

- `0x180001460`
- `0x180002330`
- `0x1800026b8`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x1800027ed`
- `ADVAPI32!RegCloseKey` at `0x1800028e8`
- `ADVAPI32!RegCloseKey` at `0x180002983`
- `ADVAPI32!RegCloseKey` at `0x18000298e`
- `ADVAPI32!RegCloseKey` at `0x1800027ed`
- `ADVAPI32!RegCloseKey` at `0x1800028e8`
- `ADVAPI32!RegCloseKey` at `0x180002983`
- `ADVAPI32!RegCloseKey` at `0x18000298e`
- `ADVAPI32!RegCreateKeyExW` at `0x18000274c`
- `ADVAPI32!RegCreateKeyExW` at `0x18000284f`
- `ADVAPI32!RegCreateKeyExW` at `0x18000274c`
- `ADVAPI32!RegCreateKeyExW` at `0x18000284f`
- `ADVAPI32!RegSetValueExW` at `0x1800027dc`
- `ADVAPI32!RegSetValueExW` at `0x1800028d7`
- `ADVAPI32!RegSetValueExW` at `0x180002976`
- `ADVAPI32!RegSetValueExW` at `0x1800027dc`
- `ADVAPI32!RegSetValueExW` at `0x1800028d7`
- `ADVAPI32!RegSetValueExW` at `0x180002976`
- `ole32!StringFromGUID2` at `0x1800026f0`
- `ole32!StringFromGUID2` at `0x1800026f0`

## string_xrefs

- `0x180002703`: `CLSID\%ls`
- `0x18000295d`: `ThreadingModel`

## pseudocode

```c
__int64 __fastcall AMovieSetupRegisterServer(const GUID *a1, __int64 a2, __int64 a3)
{
  LSTATUS v5; // eax
  __int64 result; // rax
  __int64 v7; // r8
  WCHAR *v8; // rax
  LSTATUS v9; // edi
  HKEY v10; // rcx
  __int64 v11; // r8
  WCHAR *v12; // rax
  __int64 v13; // rdx
  WCHAR *v14; // rax
  LSTATUS v15; // ebx
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  HKEY phkResult; // [rsp+58h] [rbp-A8h] BYREF
  OLECHAR sz[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR SubKey[264]; // [rsp+B0h] [rbp-50h] BYREF

  StringFromGUID2(a1, sz, 39);
  hKey = 0;
  StringCchPrintfW(SubKey, 0x104u, L"CLSID\\%ls", sz);
  v5 = RegCreateKeyExW(HKEY_CLASSES_ROOT, SubKey, 0, 0, 0, 0x2000000u, 0, &hKey, 0);
  if ( v5 )
    return v5 | 0x80070000;
  StringCchPrintfW(SubKey, 0x104u, L"%ls", a2);
  v7 = 260;
  v8 = SubKey;
  do
  {
    if ( !*v8 )
      break;
    ++v8;
    --v7;
  }
  while ( v7 );
  result = v7 == 0 ? 0x80070057 : 0;
  if ( v7 )
  {
    v9 = RegSetValueExW(hKey, 0, 0, 1u, (const BYTE *)SubKey, 2 * (v7 != 0 ? 260 - v7 : 0) + 2);
    if ( v9
      || (phkResult = 0,
          StringCchPrintfW(SubKey, 0x104u, L"%ls", L"InprocServer32"),
          (v9 = RegCreateKeyExW(hKey, SubKey, 0, 0, 0, 0x2000000u, 0, &phkResult, 0)) != 0) )
    {
      v10 = hKey;
LABEL_9:
      RegCloseKey(v10);
      return v9 | 0x80070000;
    }
    StringCchPrintfW(SubKey, 0x104u, L"%ls", a3);
    v11 = 260;
    v12 = SubKey;
    do
    {
      if ( !*v12 )
        break;
      ++v12;
      --v11;
    }
    while ( v11 );
    result = v11 == 0 ? 0x80070057 : 0;
    if ( v11 )
    {
      v9 = RegSetValueExW(phkResult, 0, 0, 1u, (const BYTE *)SubKey, 2 * (v11 != 0 ? 260 - v11 : 0) + 2);
      if ( v9 )
      {
        RegCloseKey(hKey);
        v10 = phkResult;
        goto LABEL_9;
      }
      StringCchPrintfW(SubKey, 0x104u, L"%ls", L"Both");
      v13 = 260;
      v14 = SubKey;
      do
      {
        if ( !*v14 )
          break;
        ++v14;
        --v13;
      }
      while ( v13 );
      result = v13 == 0 ? 0x80070057 : 0;
      if ( v13 )
      {
        v15 = RegSetValueExW(
                phkResult,
                L"ThreadingModel",
                0,
                1u,
                (const BYTE *)SubKey,
                2 * (v13 != 0 ? 260 - v13 : 0) + 2);
        RegCloseKey(hKey);
        RegCloseKey(phkResult);
        if ( v15 > 0 )
          return (unsigned __int16)v15 | 0x80070000;
        return (unsigned int)v15;
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800026b8  push    rbp
0x1800026ba  push    rbx
0x1800026bb  push    rsi
0x1800026bc  push    rdi
0x1800026bd  push    r14
0x1800026bf  lea     rbp, [rsp-1D0h]
0x1800026c7  sub     rsp, 2D0h
0x1800026ce  mov     rax, cs:__security_cookie
0x1800026d5  xor     rax, rsp
0x1800026d8  mov     [rbp+1F0h+var_30], rax
0x1800026df  mov     rsi, r8
0x1800026e2  mov     rdi, rdx
0x1800026e5  mov     r8d, 27h ; '''; cchMax
0x1800026eb  lea     rdx, [rsp+2F0h+sz]; lpsz
0x1800026f0  call    cs:__imp_StringFromGUID2
0x1800026f6  mov     ebx, 104h
0x1800026fb  lea     r9, [rsp+2F0h+sz]
0x180002700  xor     r14d, r14d
0x180002703  lea     r8, aClsidLs; "CLSID\\%ls"
0x18000270a  mov     edx, ebx; unsigned __int64
0x18000270c  mov     [rsp+2F0h+hKey], r14
0x180002711  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180002715  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000271a  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x18000271f  lea     rax, [rsp+2F0h+hKey]
0x180002724  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180002729  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x18000272d  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x180002732  xor     r9d, r9d; lpClass
0x180002735  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18000273d  xor     r8d, r8d; Reserved
0x180002740  mov     rcx, 0FFFFFFFF80000000h; hKey
0x180002747  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x18000274c  call    cs:__imp_RegCreateKeyExW
0x180002752  test    eax, eax
0x180002754  jz      short loc_180002760
0x180002756  or      eax, 80070000h
0x18000275b  jmp     loc_1800029A3
0x180002760  mov     r9, rdi
0x180002763  lea     r8, aLs; "%ls"
0x18000276a  mov     rdx, rbx; unsigned __int64
0x18000276d  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x180002771  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002776  mov     r8, rbx
0x180002779  lea     rax, [rbp+1F0h+SubKey]
0x18000277d  cmp     [rax], r14w
0x180002781  jz      short loc_18000278D
0x180002783  add     rax, 2
0x180002787  sub     r8, 1
0x18000278b  jnz     short loc_18000277D
0x18000278d  mov     rax, r8
0x180002790  mov     rdx, rbx
0x180002793  neg     rax
0x180002796  mov     rcx, r8
0x180002799  sbb     eax, eax
0x18000279b  sub     rdx, r8
0x18000279e  not     eax
0x1800027a0  and     eax, 80070057h
0x1800027a5  neg     rcx
0x1800027a8  sbb     r9, r9
0x1800027ab  and     r9, rdx
0x1800027ae  test    r8, r8
0x1800027b1  jz      loc_1800029A3
0x1800027b7  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800027bc  lea     eax, ds:2[r9*2]
0x1800027c4  mov     [rsp+2F0h+samDesired], eax; cbData
0x1800027c8  mov     r9d, 1; dwType
0x1800027ce  lea     rax, [rbp+1F0h+SubKey]
0x1800027d2  xor     r8d, r8d; Reserved
0x1800027d5  xor     edx, edx; lpValueName
0x1800027d7  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1800027dc  call    cs:__imp_RegSetValueExW
0x1800027e2  mov     edi, eax
0x1800027e4  test    eax, eax
0x1800027e6  jz      short loc_180002800
0x1800027e8  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800027ed  call    cs:__imp_RegCloseKey
0x1800027f3  or      edi, 80070000h
0x1800027f9  mov     eax, edi
0x1800027fb  jmp     loc_1800029A3
0x180002800  lea     r9, aInprocserver32; "InprocServer32"
0x180002807  mov     [rsp+2F0h+var_298], r14
0x18000280c  lea     r8, aLs; "%ls"
0x180002813  mov     rdx, rbx; unsigned __int64
0x180002816  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18000281a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000281f  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002824  lea     rax, [rsp+2F0h+var_298]
0x180002829  mov     [rsp+2F0h+lpdwDisposition], r14; lpdwDisposition
0x18000282e  lea     rdx, [rbp+1F0h+SubKey]; lpSubKey
0x180002832  mov     [rsp+2F0h+phkResult], rax; phkResult
0x180002837  xor     r9d, r9d; lpClass
0x18000283a  mov     [rsp+2F0h+lpSecurityAttributes], r14; lpSecurityAttributes
0x18000283f  xor     r8d, r8d; Reserved
0x180002842  mov     [rsp+2F0h+samDesired], 2000000h; samDesired
0x18000284a  mov     [rsp+2F0h+dwOptions], r14d; dwOptions
0x18000284f  call    cs:__imp_RegCreateKeyExW
0x180002855  mov     edi, eax
0x180002857  test    eax, eax
0x180002859  jnz     short loc_1800027E8
0x18000285b  mov     r9, rsi
0x18000285e  lea     r8, aLs; "%ls"
0x180002865  mov     rdx, rbx; unsigned __int64
0x180002868  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18000286c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002871  mov     r8, rbx
0x180002874  lea     rax, [rbp+1F0h+SubKey]
0x180002878  cmp     [rax], r14w
0x18000287c  jz      short loc_180002888
0x18000287e  add     rax, 2
0x180002882  sub     r8, 1
0x180002886  jnz     short loc_180002878
0x180002888  mov     rax, r8
0x18000288b  mov     rdx, rbx
0x18000288e  neg     rax
0x180002891  mov     rcx, r8
0x180002894  sbb     eax, eax
0x180002896  sub     rdx, r8
0x180002899  not     eax
0x18000289b  and     eax, 80070057h
0x1800028a0  neg     rcx
0x1800028a3  sbb     r9, r9
0x1800028a6  and     r9, rdx
0x1800028a9  test    r8, r8
0x1800028ac  jz      loc_1800029A3
0x1800028b2  mov     rcx, [rsp+2F0h+var_298]; hKey
0x1800028b7  lea     eax, ds:2[r9*2]
0x1800028bf  mov     [rsp+2F0h+samDesired], eax; cbData
0x1800028c3  mov     r9d, 1; dwType
0x1800028c9  lea     rax, [rbp+1F0h+SubKey]
0x1800028cd  xor     r8d, r8d; Reserved
0x1800028d0  xor     edx, edx; lpValueName
0x1800028d2  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x1800028d7  call    cs:__imp_RegSetValueExW
0x1800028dd  mov     edi, eax
0x1800028df  test    eax, eax
0x1800028e1  jz      short loc_1800028F8
0x1800028e3  mov     rcx, [rsp+2F0h+hKey]; hKey
0x1800028e8  call    cs:__imp_RegCloseKey
0x1800028ee  mov     rcx, [rsp+2F0h+var_298]
0x1800028f3  jmp     loc_1800027ED
0x1800028f8  lea     r9, aBoth; "Both"
0x1800028ff  mov     rdx, rbx; unsigned __int64
0x180002902  lea     r8, aLs; "%ls"
0x180002909  lea     rcx, [rbp+1F0h+SubKey]; Buffer
0x18000290d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180002912  mov     rdx, rbx
0x180002915  lea     rax, [rbp+1F0h+SubKey]
0x180002919  cmp     [rax], r14w
0x18000291d  jz      short loc_180002929
0x18000291f  add     rax, 2
0x180002923  sub     rdx, 1
0x180002927  jnz     short loc_180002919
0x180002929  mov     rax, rdx
0x18000292c  mov     rcx, rdx
0x18000292f  neg     rax
0x180002932  sbb     eax, eax
0x180002934  sub     rbx, rdx
0x180002937  not     eax
0x180002939  and     eax, 80070057h
0x18000293e  neg     rcx
0x180002941  sbb     r8, r8
0x180002944  and     r8, rbx
0x180002947  test    rdx, rdx
0x18000294a  jz      short loc_1800029A3
0x18000294c  mov     rcx, [rsp+2F0h+var_298]; hKey
0x180002951  lea     eax, ds:2[r8*2]
0x180002959  mov     [rsp+2F0h+samDesired], eax; cbData
0x18000295d  lea     rdx, ValueName; "ThreadingModel"
0x180002964  lea     rax, [rbp+1F0h+SubKey]
0x180002968  mov     r9d, 1; dwType
0x18000296e  xor     r8d, r8d; Reserved
0x180002971  mov     qword ptr [rsp+2F0h+dwOptions], rax; lpData
0x180002976  call    cs:__imp_RegSetValueExW
0x18000297c  mov     rcx, [rsp+2F0h+hKey]; hKey
0x180002981  mov     ebx, eax
0x180002983  call    cs:__imp_RegCloseKey
0x180002989  mov     rcx, [rsp+2F0h+var_298]; hKey
0x18000298e  call    cs:__imp_RegCloseKey
0x180002994  test    ebx, ebx
0x180002996  jle     short loc_1800029A1
0x180002998  movzx   ebx, bx
0x18000299b  or      ebx, 80070000h
0x1800029a1  mov     eax, ebx
0x1800029a3  mov     rcx, [rbp+1F0h+var_30]
0x1800029aa  xor     rcx, rsp; StackCookie
0x1800029ad  call    __security_check_cookie
0x1800029b2  add     rsp, 2D0h
0x1800029b9  pop     r14
0x1800029bb  pop     rdi
0x1800029bc  pop     rsi
0x1800029bd  pop     rbx
0x1800029be  pop     rbp
0x1800029bf  retn
```
