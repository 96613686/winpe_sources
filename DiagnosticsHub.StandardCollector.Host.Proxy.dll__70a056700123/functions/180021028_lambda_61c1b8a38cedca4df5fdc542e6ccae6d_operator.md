# _lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()

- ea: `0x180021028`
- end: `0x18002104f`
- name: `_lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x180021044`
- `KERNEL32!WriteConsoleW` at `0x180021044`

## pseudocode

```c
BOOL __fastcall lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()(__int64 a1)
{
  return WriteConsoleW(hObject, *(const void **)a1, *(_DWORD *)(a1 + 8), *(LPDWORD *)(a1 + 16), 0);
}

```

## disassembly

```asm
0x180021028  sub     rsp, 38h
0x18002102c  mov     r9, [rcx+10h]; lpNumberOfCharsWritten
0x180021030  mov     r8d, [rcx+8]; nNumberOfCharsToWrite
0x180021034  mov     rdx, [rcx]; lpBuffer
0x180021037  mov     rcx, cs:hObject; hConsoleOutput
0x18002103e  and     [rsp+38h+var_18], 0
0x180021044  call    cs:__imp_WriteConsoleW
0x18002104a  add     rsp, 38h
0x18002104e  retn
```
