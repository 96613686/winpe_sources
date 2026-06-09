# WsSetConfigBool

- ea: `0x18002eb04`
- end: `0x18002eb40`
- name: `WsSetConfigBool`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x18002abe4`

## callees

- `0x18002eb04`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb35`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18002eb35`

## pseudocode

```c
LSTATUS __fastcall WsSetConfigBool(HKEY *a1, const WCHAR *a2, unsigned int a3)
{
  HKEY v4; // rcx
  unsigned int Data; // [rsp+50h] [rbp+18h] BYREF

  if ( a3 > 1 )
    return 87;
  v4 = *a1;
  Data = a3;
  return RegSetValueExW(v4, a2, 0, 4u, (const BYTE *)&Data, 4u);
}

```

## disassembly

```asm
0x18002eb04  sub     rsp, 38h
0x18002eb08  cmp     r8d, 1
0x18002eb0c  jbe     short loc_18002EB15
0x18002eb0e  mov     eax, 57h ; 'W'
0x18002eb13  jmp     short loc_18002EB3B
0x18002eb15  mov     rcx, [rcx]; hKey
0x18002eb18  lea     rax, [rsp+38h+Data]
0x18002eb1d  mov     r9d, 4; dwType
0x18002eb23  mov     [rsp+38h+Data], r8d
0x18002eb28  mov     [rsp+38h+cbData], r9d; cbData
0x18002eb2d  xor     r8d, r8d; Reserved
0x18002eb30  mov     [rsp+38h+lpData], rax; lpData
0x18002eb35  call    cs:__imp_RegSetValueExW
0x18002eb3b  add     rsp, 38h
0x18002eb3f  retn
```
