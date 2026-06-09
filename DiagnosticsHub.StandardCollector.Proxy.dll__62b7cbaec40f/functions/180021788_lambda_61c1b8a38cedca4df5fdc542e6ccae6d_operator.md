# _lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()

- ea: `0x180021788`
- end: `0x1800217af`
- name: `_lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()`
- size: `39`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `KERNEL32!WriteConsoleW` at `0x1800217a4`
- `KERNEL32!WriteConsoleW` at `0x1800217a4`

## pseudocode

```c
BOOL __fastcall lambda_61c1b8a38cedca4df5fdc542e6ccae6d_::operator()(__int64 a1)
{
  return WriteConsoleW(hObject, *(const void **)a1, *(_DWORD *)(a1 + 8), *(LPDWORD *)(a1 + 16), 0);
}

```

## disassembly

```asm
0x180021788  sub     rsp, 38h
0x18002178c  mov     r9, [rcx+10h]; lpNumberOfCharsWritten
0x180021790  mov     r8d, [rcx+8]; nNumberOfCharsToWrite
0x180021794  mov     rdx, [rcx]; lpBuffer
0x180021797  mov     rcx, cs:hObject; hConsoleOutput
0x18002179e  and     [rsp+38h+var_18], 0
0x1800217a4  call    cs:__imp_WriteConsoleW
0x1800217aa  add     rsp, 38h
0x1800217ae  retn
```
