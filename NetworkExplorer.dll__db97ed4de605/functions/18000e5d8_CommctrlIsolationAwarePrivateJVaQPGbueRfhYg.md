# CommctrlIsolationAwarePrivateJVaQPGbueRfhYg

- ea: `0x18000e5d8`
- end: `0x18000e5fc`
- name: `CommctrlIsolationAwarePrivateJVaQPGbueRfhYg`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000e6cc`
- `0x18000ea20`

## callees

- `0x18000e5d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5dc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e5dc`

## pseudocode

```c
signed int CommctrlIsolationAwarePrivateJVaQPGbueRfhYg()
{
  signed int result; // eax

  result = GetLastError();
  if ( result )
  {
    if ( result <= 0 )
      return result;
  }
  else
  {
    LOWORD(result) = 1359;
  }
  return (unsigned __int16)result | 0x80070000;
}

```

## disassembly

```asm
0x18000e5d8  sub     rsp, 28h
0x18000e5dc  call    cs:__imp_GetLastError
0x18000e5e2  test    eax, eax
0x18000e5e4  jnz     short loc_18000E5ED
0x18000e5e6  mov     eax, 54Fh
0x18000e5eb  jmp     short loc_18000E5EF
0x18000e5ed  jle     short loc_18000E5F7
0x18000e5ef  movzx   eax, ax
0x18000e5f2  or      eax, 80070000h
0x18000e5f7  add     rsp, 28h
0x18000e5fb  retn
```
