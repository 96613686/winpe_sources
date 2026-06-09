# HrGetLastFailure

- ea: `0x1800090e4`
- end: `0x180009109`
- name: `HrGetLastFailure`
- size: `37`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x1800025d8`
- `0x180005010`
- `0x180006a2c`
- `0x180006d84`
- `0x180006e04`
- `0x180006eb0`
- `0x18000726c`
- `0x1800074fc`
- `0x1800075ac`
- `0x180007e24`
- `0x180007fdc`
- `0x1800081e0`

## callees

- `0x1800090e4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800090e8`
- `KERNEL32!GetLastError` at `0x1800090e8`

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
0x1800090e4  sub     rsp, 28h
0x1800090e8  call    cs:__imp_GetLastError
0x1800090ee  test    eax, eax
0x1800090f0  jle     short loc_1800090FA
0x1800090f2  movzx   eax, ax
0x1800090f5  or      eax, 80070000h
0x1800090fa  test    eax, eax
0x1800090fc  mov     ecx, 80004005h
0x180009101  cmovns  eax, ecx
0x180009104  add     rsp, 28h
0x180009108  retn
```
