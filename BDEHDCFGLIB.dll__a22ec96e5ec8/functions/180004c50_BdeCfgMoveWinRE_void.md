# BdeCfgMoveWinRE(void)

- ea: `0x180004c50`
- end: `0x180004ca8`
- name: `?BdeCfgMoveWinRE@@YAJXZ`
- size: `88`
- prototype: `signed int(void)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, installer_update`

## callees

- `0x180004c50`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004c85`
- `KERNEL32!GetLastError` at `0x180004c85`
- `ReAgent!WinReInstall` at `0x180004c7b`
- `ReAgent!WinReInstall` at `0x180004c7b`

## pseudocode

```c
signed int BdeCfgMoveWinRE(void)
{
  signed int result; // eax
  int v1; // [rsp+30h] [rbp+8h] BYREF

  v1 = 0;
  if ( !g_pService )
    return -1063256042;
  if ( (unsigned int)WinReInstall(1, &v1) )
    return v1 == 0;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004c50  push    rdi
0x180004c52  sub     rsp, 20h
0x180004c56  cmp     cs:?g_pService@@3PEAUIVdsService@@EA, 0; IVdsService * g_pService
0x180004c5e  mov     [rsp+28h+arg_0], 0
0x180004c66  jnz     short loc_180004C6F
0x180004c68  mov     eax, 0C0A00016h
0x180004c6d  jmp     short loc_180004CA2
0x180004c6f  mov     edi, 1
0x180004c74  lea     rdx, [rsp+28h+arg_0]
0x180004c79  mov     ecx, edi
0x180004c7b  call    cs:__imp_WinReInstall
0x180004c81  test    eax, eax
0x180004c83  jnz     short loc_180004C99
0x180004c85  call    cs:__imp_GetLastError
0x180004c8b  test    eax, eax
0x180004c8d  jle     short loc_180004CA2
0x180004c8f  movzx   eax, ax
0x180004c92  or      eax, 80070000h
0x180004c97  jmp     short loc_180004CA2
0x180004c99  xor     eax, eax
0x180004c9b  cmp     [rsp+28h+arg_0], eax
0x180004c9f  cmovz   eax, edi
0x180004ca2  add     rsp, 20h
0x180004ca6  pop     rdi
0x180004ca7  retn
```
