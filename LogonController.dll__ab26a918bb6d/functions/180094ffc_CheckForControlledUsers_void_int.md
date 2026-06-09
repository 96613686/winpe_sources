# _CheckForControlledUsers(void *,int *)

- ea: `0x180094ffc`
- end: `0x18009516a`
- name: `?_CheckForControlledUsers@@YAJPEAXPEAH@Z`
- size: `366`
- prototype: `__int64 __fastcall(void *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180094d5c`

## callees

- `0x1800680e4`
- `0x180094ffc`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095046`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180095046`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095154`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180095154`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800950ff`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800950ff`

## string_xrefs

- `0x180095089`: `onecore\ds\security\eas\policyengine\common.cpp`
- `0x180095075`: `RegOpenKeyEx`

## pseudocode

```c
__int64 __fastcall _CheckForControlledUsers(HKEY a1, int *a2)
{
  unsigned int v3; // ebx
  LSTATUS v4; // eax
  PHKEY phkResult; // [rsp+20h] [rbp-48h]
  PHKEY phkResulta; // [rsp+20h] [rbp-48h]
  DWORD cSubKeys; // [rsp+70h] [rbp+8h] BYREF
  HKEY hKey; // [rsp+78h] [rbp+10h] BYREF

  cSubKeys = 0;
  hKey = 0;
  *a2 = 0;
  if ( !a1 )
    return 0;
  v3 = RegOpenKeyExW(a1, L"ControlledUsers", 0, 0x20019u, &hKey);
  if ( v3 - 2 > 1 )
  {
    if ( v3 )
    {
      if ( (int)v3 > 0 )
        v3 = (unsigned __int16)v3 | 0xC0070000;
      LODWORD(phkResult) = 241;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        phkResult,
        L"RegOpenKeyEx",
        &sourceString);
      goto LABEL_16;
    }
    v4 = RegQueryInfoKeyW(hKey, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
    v3 = v4;
    if ( v4 )
    {
      if ( v4 > 0 )
        v3 = (unsigned __int16)v4 | 0xC0070000;
      LODWORD(phkResulta) = 260;
      DbgPrintfW(
        1u,
        L"(0x%08x) %ws:%u : %ws:%ws\n",
        v3,
        L"onecore\\ds\\security\\eas\\policyengine\\common.cpp",
        phkResulta,
        L"RegQueryInfoKey",
        &sourceString);
      goto LABEL_16;
    }
    if ( cSubKeys )
      *a2 = 1;
  }
  v3 = 0;
LABEL_16:
  if ( hKey )
    RegCloseKey(hKey);
  return v3;
}

```

## disassembly

```asm
0x180094ffc  mov     [rsp+arg_10], rbx
0x180095001  push    rdi
0x180095002  sub     rsp, 60h
0x180095006  mov     [rsp+68h+cSubKeys], 0
0x18009500e  mov     rdi, rdx
0x180095011  mov     [rsp+68h+hKey], 0
0x18009501a  mov     dword ptr [rdx], 0
0x180095020  test    rcx, rcx
0x180095023  jnz     short loc_18009502C
0x180095025  xor     ebx, ebx
0x180095027  jmp     loc_18009515A
0x18009502c  lea     rax, [rsp+68h+hKey]
0x180095031  mov     r9d, 20019h; samDesired
0x180095037  xor     r8d, r8d; ulOptions
0x18009503a  mov     [rsp+68h+phkResult], rax; phkResult
0x18009503f  lea     rdx, aControlleduser; "ControlledUsers"
0x180095046  call    cs:__imp_RegOpenKeyExW
0x18009504c  mov     ebx, eax
0x18009504e  add     eax, 0FFFFFFFEh
0x180095051  cmp     eax, 1
0x180095054  jbe     loc_180095148
0x18009505a  test    ebx, ebx
0x18009505c  jz      short loc_1800950A9
0x18009505e  jle     short loc_180095069
0x180095060  movzx   ebx, bx
0x180095063  or      ebx, 0C0070000h
0x180095069  lea     rax, sourceString
0x180095070  mov     [rsp+68h+lpcbMaxClassLen], rax
0x180095075  lea     rax, aRegopenkeyex; "RegOpenKeyEx"
0x18009507c  mov     [rsp+68h+lpcbMaxSubKeyLen], rax
0x180095081  mov     dword ptr [rsp+68h+phkResult], 0F1h
0x180095089  lea     r9, aOnecoreDsSecur_0; "onecore\\ds\\security\\eas\\policyengin"...
0x180095090  mov     r8d, ebx
0x180095093  lea     rdx, a0x08xWsUWsWs; "(0x%08x) %ws:%u : %ws:%ws\n"
0x18009509a  mov     ecx, 1; unsigned int
0x18009509f  call    ?DbgPrintfW@@YAXKPEBGZZ; DbgPrintfW(ulong,ushort const *,...)
0x1800950a4  jmp     loc_18009514A
0x1800950a9  mov     rcx, [rsp+68h+hKey]; hKey
0x1800950ae  lea     rax, [rsp+68h+cSubKeys]
0x1800950b3  mov     [rsp+68h+lpftLastWriteTime], 0; lpftLastWriteTime
0x1800950bc  xor     r9d, r9d; lpReserved
0x1800950bf  mov     [rsp+68h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x1800950c8  xor     r8d, r8d; lpcchClass
0x1800950cb  mov     [rsp+68h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x1800950d4  xor     edx, edx; lpClass
0x1800950d6  mov     [rsp+68h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800950df  mov     [rsp+68h+lpcValues], 0; lpcValues
0x1800950e8  mov     [rsp+68h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800950f1  mov     [rsp+68h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800950fa  mov     [rsp+68h+phkResult], rax; lpcSubKeys
0x1800950ff  call    cs:__imp_RegQueryInfoKeyW
0x180095105  mov     ebx, eax
0x180095107  test    eax, eax
0x180095109  jz      short loc_18009513B
0x18009510b  jle     short loc_180095116
0x18009510d  movzx   ebx, ax
0x180095110  or      ebx, 0C0070000h
0x180095116  lea     rax, sourceString
0x18009511d  mov     [rsp+68h+lpcbMaxClassLen], rax
0x180095122  lea     rax, aRegqueryinfoke; "RegQueryInfoKey"
0x180095129  mov     [rsp+68h+lpcbMaxSubKeyLen], rax
0x18009512e  mov     dword ptr [rsp+68h+phkResult], 104h
0x180095136  jmp     loc_180095089
0x18009513b  cmp     [rsp+68h+cSubKeys], 0
0x180095140  jz      short loc_180095148
0x180095142  mov     dword ptr [rdi], 1
0x180095148  xor     ebx, ebx
0x18009514a  mov     rcx, [rsp+68h+hKey]; hKey
0x18009514f  test    rcx, rcx
0x180095152  jz      short loc_18009515A
0x180095154  call    cs:__imp_RegCloseKey
0x18009515a  mov     eax, ebx
0x18009515c  mov     rbx, [rsp+68h+arg_10]
0x180095164  add     rsp, 60h
0x180095168  pop     rdi
0x180095169  retn
```
