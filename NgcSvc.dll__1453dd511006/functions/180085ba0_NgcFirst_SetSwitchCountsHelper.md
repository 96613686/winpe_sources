# NgcFirst::SetSwitchCountsHelper

- ea: `0x180085ba0`
- end: `0x180085cfe`
- name: `NgcFirst::SetSwitchCountsHelper`
- size: `350`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int, LPCWSTR, BYTE *lpData)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180042e40`
- `0x180044714`
- `0x1800856b8`

## callees

- `0x18000782c`
- `0x180032b6c`
- `0x180032c20`
- `0x180048304`
- `0x180085ba0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085c55`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180085c55`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085c87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085cca`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085c87`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180085cca`

## string_xrefs

- `0x180085bd2`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`
- `0x180085c9b`: `onecore\ds\security\ngc\credprov\utils\ngcfirst\ngcfirst.cpp`

## pseudocode

```c
__int64 __fastcall NgcFirst::SetSwitchCountsHelper(
        LPCWSTR lpSubKey,
        LPCWSTR lpValueName,
        const BYTE *a3,
        LPCWSTR a4,
        BYTE *lpData)
{
  unsigned int v9; // ebx
  __int64 v10; // rdx
  const BYTE *v11; // rbx
  unsigned int v12; // eax
  __int64 v13; // rdx
  int dwOptions; // [rsp+20h] [rbp-48h]
  unsigned int dwOptionsa; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  HKEY hKey; // [rsp+70h] [rbp+8h] BYREF

  if ( lpSubKey )
  {
    v11 = lpData;
    if ( !a3 && !lpData )
    {
      v9 = -2147024809;
      v10 = 441;
      goto LABEL_3;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v12 = RegCreateKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 0, 0, 0x20006u, 0, &hKey, 0);
    if ( v12 )
    {
      v13 = 454;
    }
    else if ( a3 && (v12 = RegSetValueExW(hKey, lpValueName, 0, 4u, a3, 4u)) != 0 )
    {
      v13 = 465;
    }
    else
    {
      if ( !v11 || (v12 = RegSetValueExW(hKey, a4, 0, 4u, v11, 4u)) == 0 )
      {
        v9 = 0;
        goto LABEL_17;
      }
      v13 = 477;
    }
    v9 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v13,
           (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
           (const char *)v12,
           dwOptionsa);
LABEL_17:
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
    return v9;
  }
  v9 = -2147467261;
  v10 = 440;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)"onecore\\ds\\security\\ngc\\credprov\\utils\\ngcfirst\\ngcfirst.cpp",
    (const char *)v9,
    dwOptions);
  return v9;
}

```

## disassembly

```asm
0x180085ba0  mov     [rsp+arg_8], rbx
0x180085ba5  mov     [rsp+arg_10], rbp
0x180085baa  push    rsi
0x180085bab  push    rdi
0x180085bac  push    r14
0x180085bae  sub     rsp, 50h
0x180085bb2  mov     r14, r9
0x180085bb5  mov     rdi, r8
0x180085bb8  mov     rbp, rdx
0x180085bbb  mov     rsi, rcx
0x180085bbe  test    rcx, rcx
0x180085bc1  jnz     short loc_180085BE6
0x180085bc3  mov     ebx, 80004003h
0x180085bc8  mov     edx, 1B8h; void *
0x180085bcd  mov     rcx, [rsp+68h]; this
0x180085bd2  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180085bd9  mov     r9d, ebx; char *
0x180085bdc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180085be1  jmp     loc_180085CE7
0x180085be6  mov     rbx, [rsp+68h+lpData]
0x180085bee  test    rdi, rdi
0x180085bf1  jnz     short loc_180085C04
0x180085bf3  test    rbx, rbx
0x180085bf6  jnz     short loc_180085C04
0x180085bf8  mov     ebx, 80070057h
0x180085bfd  mov     edx, 1B9h
0x180085c02  jmp     short loc_180085BCD
0x180085c04  xor     edx, edx
0x180085c06  mov     [rsp+68h+hKey], 0
0x180085c0f  lea     rcx, [rsp+68h+hKey]
0x180085c14  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180085c19  mov     [rsp+68h+lpdwDisposition], 0; lpdwDisposition
0x180085c22  lea     rax, [rsp+68h+hKey]
0x180085c27  mov     [rsp+68h+phkResult], rax; phkResult
0x180085c2c  xor     r9d, r9d; lpClass
0x180085c2f  mov     [rsp+68h+lpSecurityAttributes], 0; lpSecurityAttributes
0x180085c38  xor     r8d, r8d; Reserved
0x180085c3b  mov     [rsp+68h+samDesired], 20006h; samDesired
0x180085c43  mov     rdx, rsi; lpSubKey
0x180085c46  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180085c4d  mov     [rsp+68h+dwOptions], 0; dwOptions
0x180085c55  call    cs:__imp_RegCreateKeyExW
0x180085c5b  test    eax, eax
0x180085c5d  jz      short loc_180085C66
0x180085c5f  mov     edx, 1C6h
0x180085c64  jmp     short loc_180085C96
0x180085c66  mov     esi, 4
0x180085c6b  test    rdi, rdi
0x180085c6e  jz      short loc_180085CAE
0x180085c70  mov     rcx, [rsp+68h+hKey]; hKey
0x180085c75  mov     r9d, esi; dwType
0x180085c78  mov     [rsp+68h+samDesired], esi; cbData
0x180085c7c  xor     r8d, r8d; Reserved
0x180085c7f  mov     rdx, rbp; lpValueName
0x180085c82  mov     qword ptr [rsp+68h+dwOptions], rdi; unsigned int
0x180085c87  call    cs:__imp_RegSetValueExW
0x180085c8d  test    eax, eax
0x180085c8f  jz      short loc_180085CAE
0x180085c91  mov     edx, 1D1h; void *
0x180085c96  mov     rcx, [rsp+68h]; this
0x180085c9b  lea     r8, aOnecoreDsSecur_37; "onecore\\ds\\security\\ngc\\credprov\\u"...
0x180085ca2  mov     r9d, eax; char *
0x180085ca5  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180085caa  mov     ebx, eax
0x180085cac  jmp     short loc_180085CDD
0x180085cae  test    rbx, rbx
0x180085cb1  jz      short loc_180085CDB
0x180085cb3  mov     rcx, [rsp+68h+hKey]; hKey
0x180085cb8  mov     r9d, esi; dwType
0x180085cbb  mov     [rsp+68h+samDesired], esi; cbData
0x180085cbf  xor     r8d, r8d; Reserved
0x180085cc2  mov     rdx, r14; lpValueName
0x180085cc5  mov     qword ptr [rsp+68h+dwOptions], rbx; lpData
0x180085cca  call    cs:__imp_RegSetValueExW
0x180085cd0  test    eax, eax
0x180085cd2  jz      short loc_180085CDB
0x180085cd4  mov     edx, 1DDh
0x180085cd9  jmp     short loc_180085C96
0x180085cdb  xor     ebx, ebx
0x180085cdd  lea     rcx, [rsp+68h+hKey]
0x180085ce2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180085ce7  lea     r11, [rsp+68h+var_18]
0x180085cec  mov     eax, ebx
0x180085cee  mov     rbx, [r11+28h]
0x180085cf2  mov     rbp, [r11+30h]
0x180085cf6  mov     rsp, r11
0x180085cf9  pop     r14
0x180085cfb  pop     rdi
0x180085cfc  pop     rsi
0x180085cfd  retn
```
