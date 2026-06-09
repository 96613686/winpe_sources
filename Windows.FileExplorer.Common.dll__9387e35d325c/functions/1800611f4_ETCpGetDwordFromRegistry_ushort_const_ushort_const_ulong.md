# ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)

- ea: `0x1800611f4`
- end: `0x1800612f4`
- name: `?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z`
- size: `256`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800612fc`
- `0x180066b48`

## callees

- `0x180004d6c`
- `0x1800077c8`
- `0x18002037c`
- `0x18002edcc`
- `0x1800611f4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006123d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18006123d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061278`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180061278`

## string_xrefs

- `0x1800612a1`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x1800612c4`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`

## pseudocode

```c
__int64 __fastcall ETCpGetDwordFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, BYTE *a3)
{
  LSTATUS v6; // eax
  LSTATUS v7; // ebx
  __int64 v8; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey[0] = 0;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    hKey,
    0);
  v6 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, hKey);
  Type = 4;
  v7 = v6;
  cbData = 4;
  if ( v6 || (v7 = RegQueryValueExW(hKey[0], lpValueName, 0, &Type, a3, &cbData)) != 0 )
  {
    if ( v7 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
        (const char *)(unsigned int)v7,
        phkResult);
  }
  else
  {
    if ( Type == 4 )
    {
      if ( cbData == 4 )
      {
        v7 = 0;
        goto LABEL_11;
      }
      v8 = 102;
    }
    else
    {
      v8 = 98;
    }
    v7 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v8,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
           (const char *)0xD,
           phkResult);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800611f4  mov     rax, rsp
0x1800611f7  mov     [rax+8], rbx
0x1800611fb  mov     [rax+10h], rsi
0x1800611ff  push    rdi
0x180061200  sub     rsp, 40h
0x180061204  mov     rsi, rdx
0x180061207  mov     qword ptr [rax-10h], 0
0x18006120f  mov     rbx, rcx
0x180061212  xor     edx, edx
0x180061214  lea     rcx, [rax-10h]
0x180061218  mov     rdi, r8
0x18006121b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180061220  lea     rax, [rsp+48h+hKey]
0x180061225  mov     r9d, 1; samDesired
0x18006122b  xor     r8d, r8d; ulOptions
0x18006122e  mov     [rsp+48h+phkResult], rax; int
0x180061233  mov     rdx, rbx; lpSubKey
0x180061236  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18006123d  call    cs:__imp_RegOpenKeyExW
0x180061243  mov     [rsp+48h+Type], 4
0x18006124b  mov     ebx, eax
0x18006124d  mov     [rsp+48h+cbData], 4
0x180061255  test    eax, eax
0x180061257  jnz     short loc_1800612BB
0x180061259  mov     rcx, [rsp+48h+hKey]; hKey
0x18006125e  lea     rax, [rsp+48h+cbData]
0x180061263  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180061268  lea     r9, [rsp+48h+Type]; lpType
0x18006126d  xor     r8d, r8d; lpReserved
0x180061270  mov     [rsp+48h+phkResult], rdi; unsigned int
0x180061275  mov     rdx, rsi; lpValueName
0x180061278  call    cs:__imp_RegQueryValueExW
0x18006127e  mov     ebx, eax
0x180061280  test    eax, eax
0x180061282  jnz     short loc_1800612BB
0x180061284  cmp     [rsp+48h+Type], 4
0x180061289  jz      short loc_180061290
0x18006128b  lea     edx, [rax+62h]
0x18006128e  jmp     short loc_18006129C
0x180061290  cmp     [rsp+48h+cbData], 4
0x180061295  jz      short loc_1800612B7
0x180061297  mov     edx, 66h ; 'f'; void *
0x18006129c  mov     rcx, [rsp+48h]; this
0x1800612a1  lea     r8, aOnecoreInterna_9; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800612a8  mov     r9d, 0Dh; char *
0x1800612ae  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800612b3  mov     ebx, eax
0x1800612b5  jmp     short loc_1800612D8
0x1800612b7  xor     ebx, ebx
0x1800612b9  jmp     short loc_1800612D8
0x1800612bb  test    ebx, ebx
0x1800612bd  jns     short loc_1800612D8
0x1800612bf  mov     rcx, [rsp+48h]; this
0x1800612c4  lea     r8, aOnecoreInterna_9; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800612cb  mov     r9d, ebx; char *
0x1800612ce  mov     edx, 6Bh ; 'k'; void *
0x1800612d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800612d8  lea     rcx, [rsp+48h+hKey]
0x1800612dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800612e2  mov     rsi, [rsp+48h+arg_8]
0x1800612e7  mov     eax, ebx
0x1800612e9  mov     rbx, [rsp+48h+arg_0]
0x1800612ee  add     rsp, 40h
0x1800612f2  pop     rdi
0x1800612f3  retn
```
