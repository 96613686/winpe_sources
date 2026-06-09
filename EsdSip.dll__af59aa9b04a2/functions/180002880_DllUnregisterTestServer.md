# DllUnregisterTestServer

- ea: `0x180002880`
- end: `0x1800028c8`
- name: `DllUnregisterTestServer`
- size: `72`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002880`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x18000289c`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18000289c`
- `KERNEL32!GetLastError` at `0x1800028a6`
- `KERNEL32!GetLastError` at `0x1800028a6`

## pseudocode

```c
signed int DllUnregisterTestServer()
{
  signed int result; // eax

  if ( !*(_QWORD *)&g_pgSubject.Data1 )
    return -2147019873;
  if ( CryptSIPRemoveProvider(&GUID_ESDSIP_TEST) )
  {
    result = 0;
    *(_QWORD *)&g_pgSubject.Data1 = 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180002880  sub     rsp, 28h
0x180002884  cmp     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, 0; _GUID * g_pgSubject ...
0x18000288c  jnz     short loc_180002895
0x18000288e  mov     eax, 8007139Fh
0x180002893  jmp     short loc_1800028C3
0x180002895  lea     rcx, GUID_ESDSIP_TEST; pgProv
0x18000289c  call    cs:__imp_CryptSIPRemoveProvider
0x1800028a2  test    eax, eax
0x1800028a4  jnz     short loc_1800028BA
0x1800028a6  call    cs:__imp_GetLastError
0x1800028ac  test    eax, eax
0x1800028ae  jle     short loc_1800028C3
0x1800028b0  movzx   eax, ax
0x1800028b3  or      eax, 80070000h
0x1800028b8  jmp     short loc_1800028C3
0x1800028ba  xor     eax, eax
0x1800028bc  mov     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, rax; _GUID * g_pgSubject ...
0x1800028c3  add     rsp, 28h
0x1800028c7  retn
```
