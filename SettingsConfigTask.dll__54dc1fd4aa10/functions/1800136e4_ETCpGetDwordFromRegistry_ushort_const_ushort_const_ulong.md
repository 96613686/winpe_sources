# ETCpGetDwordFromRegistry(ushort const *,ushort const *,ulong &)

- ea: `0x1800136e4`
- end: `0x1800137dd`
- name: `?ETCpGetDwordFromRegistry@@YAJPEBG0AEAK@Z`
- size: `249`
- prototype: `__int64 __fastcall(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800137e4`
- `0x180018f48`

## callees

- `0x18000972c`
- `0x18001297c`
- `0x1800136e4`
- `0x18001b968`
- `0x18001fb74`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013726`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180013726`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013761`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180013761`

## string_xrefs

- `0x18001378a`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`
- `0x1800137ad`: `onecore\internal\enduser\inc\EnterpriseTemporaryControl.h`

## pseudocode

```c
__int64 __fastcall ETCpGetDwordFromRegistry(LPCWSTR lpSubKey, LPCWSTR lpValueName, LPBYTE lpData)
{
  HKEY *v6; // rax
  LSTATUS v7; // eax
  LSTATUS v8; // ebx
  __int64 v9; // rdx
  unsigned int phkResult; // [rsp+20h] [rbp-28h]
  DWORD cbData; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey[2]; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  DWORD Type; // [rsp+68h] [rbp+20h] BYREF

  hKey[0] = 0;
  v6 = (HKEY *)wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(
                 hKey,
                 lpValueName,
                 lpData);
  v7 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, lpSubKey, 0, 1u, v6);
  Type = 4;
  v8 = v7;
  cbData = 4;
  if ( v7 || (v8 = RegQueryValueExW(hKey[0], lpValueName, 0, &Type, lpData, &cbData)) != 0 )
  {
    if ( v8 < 0 )
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6B,
        (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
        (const char *)(unsigned int)v8,
        phkResult);
  }
  else
  {
    if ( Type == 4 )
    {
      if ( cbData == 4 )
      {
        v8 = 0;
        goto LABEL_11;
      }
      v9 = 102;
    }
    else
    {
      v9 = 98;
    }
    v8 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)v9,
           (unsigned int)"onecore\\internal\\enduser\\inc\\EnterpriseTemporaryControl.h",
           (const char *)0xD,
           phkResult);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800136e4  mov     rax, rsp
0x1800136e7  mov     [rax+8], rbx
0x1800136eb  mov     [rax+10h], rsi
0x1800136ef  push    rdi
0x1800136f0  sub     rsp, 40h
0x1800136f4  mov     rbx, rcx
0x1800136f7  mov     qword ptr [rax-10h], 0
0x1800136ff  lea     rcx, [rax-10h]
0x180013703  mov     rdi, r8
0x180013706  mov     rsi, rdx
0x180013709  call    ?put@?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAPEAPEAUHKEY__@@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>::put(void)
0x18001370e  mov     r9d, 1; samDesired
0x180013714  mov     [rsp+48h+phkResult], rax; int
0x180013719  xor     r8d, r8d; ulOptions
0x18001371c  mov     rdx, rbx; lpSubKey
0x18001371f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013726  call    cs:__imp_RegOpenKeyExW
0x18001372c  mov     [rsp+48h+Type], 4
0x180013734  mov     ebx, eax
0x180013736  mov     [rsp+48h+cbData], 4
0x18001373e  test    eax, eax
0x180013740  jnz     short loc_1800137A4
0x180013742  mov     rcx, [rsp+48h+hKey]; hKey
0x180013747  lea     rax, [rsp+48h+cbData]
0x18001374c  mov     [rsp+48h+lpcbData], rax; lpcbData
0x180013751  lea     r9, [rsp+48h+Type]; lpType
0x180013756  xor     r8d, r8d; lpReserved
0x180013759  mov     [rsp+48h+phkResult], rdi; unsigned int
0x18001375e  mov     rdx, rsi; lpValueName
0x180013761  call    cs:__imp_RegQueryValueExW
0x180013767  mov     ebx, eax
0x180013769  test    eax, eax
0x18001376b  jnz     short loc_1800137A4
0x18001376d  cmp     [rsp+48h+Type], 4
0x180013772  jz      short loc_180013779
0x180013774  lea     edx, [rax+62h]
0x180013777  jmp     short loc_180013785
0x180013779  cmp     [rsp+48h+cbData], 4
0x18001377e  jz      short loc_1800137A0
0x180013780  mov     edx, 66h ; 'f'; void *
0x180013785  mov     rcx, [rsp+48h]; this
0x18001378a  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x180013791  mov     r9d, 0Dh; char *
0x180013797  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001379c  mov     ebx, eax
0x18001379e  jmp     short loc_1800137C1
0x1800137a0  xor     ebx, ebx
0x1800137a2  jmp     short loc_1800137C1
0x1800137a4  test    ebx, ebx
0x1800137a6  jns     short loc_1800137C1
0x1800137a8  mov     rcx, [rsp+48h]; this
0x1800137ad  lea     r8, aOnecoreInterna_6; "onecore\\internal\\enduser\\inc\\Enterp"...
0x1800137b4  mov     r9d, ebx; char *
0x1800137b7  mov     edx, 6Bh ; 'k'; void *
0x1800137bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137c1  lea     rcx, [rsp+48h+hKey]
0x1800137c6  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800137cb  mov     rsi, [rsp+48h+arg_8]
0x1800137d0  mov     eax, ebx
0x1800137d2  mov     rbx, [rsp+48h+arg_0]
0x1800137d7  add     rsp, 40h
0x1800137db  pop     rdi
0x1800137dc  retn
```
