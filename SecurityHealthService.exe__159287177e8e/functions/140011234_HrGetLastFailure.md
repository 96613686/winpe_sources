# HrGetLastFailure

- ea: `0x140011234`
- end: `0x140011259`
- name: `HrGetLastFailure`
- size: `37`
- prototype: `signed int()`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x140005e1c`
- `0x140006714`
- `0x14000e6e4`
- `0x14000e780`
- `0x14000e800`
- `0x14000e8b4`
- `0x14000e990`
- `0x14000ec7c`
- `0x14000ef14`
- `0x14000efc4`
- `0x1400104e4`
- `0x140011ef0`

## callees

- `0x140011234`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140011238`
- `KERNEL32!GetLastError` at `0x140011238`

## pseudocode

```c
signed int HrGetLastFailure()
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    result = (unsigned __int16)result | 0x80070000;
  if ( result >= 0 )
    return -2147467259;
  return result;
}

```

## disassembly

```asm
0x140011234  sub     rsp, 28h
0x140011238  call    cs:__imp_GetLastError
0x14001123e  test    eax, eax
0x140011240  jle     short loc_14001124A
0x140011242  movzx   eax, ax
0x140011245  or      eax, 80070000h
0x14001124a  test    eax, eax
0x14001124c  mov     ecx, 80004005h
0x140011251  cmovns  eax, ecx
0x140011254  add     rsp, 28h
0x140011258  retn
```
