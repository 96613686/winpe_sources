# GetLastWin32Error(void)

- ea: `0x1800030d4`
- end: `0x1800030fd`
- name: `?GetLastWin32Error@@YAJXZ`
- size: `41`
- prototype: `__int64(void)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180001050`
- `0x180002048`
- `0x1800022a0`
- `0x180002fac`

## callees

- `0x1800030d4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800030d8`
- `KERNEL32!GetLastError` at `0x1800030d8`

## pseudocode

```c
__int64 GetLastWin32Error(void)
{
  signed int LastError; // ecx
  __int64 result; // rax

  LastError = GetLastError();
  if ( !LastError )
    return 2147500037LL;
  result = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    return (unsigned int)LastError;
  return result;
}

```

## disassembly

```asm
0x1800030d4  sub     rsp, 28h
0x1800030d8  call    cs:__imp_GetLastError
0x1800030de  mov     ecx, eax
0x1800030e0  test    eax, eax
0x1800030e2  jz      short loc_1800030F3
0x1800030e4  movzx   eax, cx
0x1800030e7  or      eax, 80070000h
0x1800030ec  test    ecx, ecx
0x1800030ee  cmovle  eax, ecx
0x1800030f1  jmp     short loc_1800030F8
0x1800030f3  mov     eax, 80004005h
0x1800030f8  add     rsp, 28h
0x1800030fc  retn
```
