# DllUnregisterServer

- ea: `0x180002830`
- end: `0x180002878`
- name: `DllUnregisterServer`
- size: `72`
- prototype: `HRESULT __stdcall()`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180002830`

## import_xrefs

- `CRYPT32!CryptSIPRemoveProvider` at `0x18000284c`
- `CRYPT32!CryptSIPRemoveProvider` at `0x18000284c`
- `KERNEL32!GetLastError` at `0x180002856`
- `KERNEL32!GetLastError` at `0x180002856`

## pseudocode

```c
HRESULT __stdcall DllUnregisterServer()
{
  HRESULT result; // eax

  if ( !*(_QWORD *)&g_pgSubject.Data1 )
    return -2147019873;
  if ( CryptSIPRemoveProvider(&GUID_ESDSIP) )
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
0x180002830  sub     rsp, 28h
0x180002834  cmp     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, 0; _GUID * g_pgSubject ...
0x18000283c  jnz     short loc_180002845
0x18000283e  mov     eax, 8007139Fh
0x180002843  jmp     short loc_180002873
0x180002845  lea     rcx, GUID_ESDSIP; pgProv
0x18000284c  call    cs:__imp_CryptSIPRemoveProvider
0x180002852  test    eax, eax
0x180002854  jnz     short loc_18000286A
0x180002856  call    cs:__imp_GetLastError
0x18000285c  test    eax, eax
0x18000285e  jle     short loc_180002873
0x180002860  movzx   eax, ax
0x180002863  or      eax, 80070000h
0x180002868  jmp     short loc_180002873
0x18000286a  xor     eax, eax
0x18000286c  mov     qword ptr cs:?g_pgSubject@@3PEAU_GUID@@EA.Data1, rax; _GUID * g_pgSubject ...
0x180002873  add     rsp, 28h
0x180002877  retn
```
