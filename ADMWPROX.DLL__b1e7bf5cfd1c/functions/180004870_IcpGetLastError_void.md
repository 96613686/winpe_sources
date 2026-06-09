# IcpGetLastError(void)

- ea: `0x180004870`
- end: `0x18000489c`
- name: `?IcpGetLastError@@YAJXZ`
- size: `44`
- prototype: `__int64(void)`
- caller_count: `16`
- callee_count: `1`
- tags: ``

## callers

- `0x1800048a4`
- `0x180004e28`
- `0x180005650`
- `0x180005bd8`
- `0x180005d6c`
- `0x180005f28`
- `0x180005f7c`
- `0x180006104`
- `0x1800063b4`
- `0x180006460`
- `0x180006508`
- `0x180006704`
- `0x180006918`
- `0x180006a3c`
- `0x180006a98`
- `0x180006ad8`

## callees

- `0x180004870`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180004874`
- `KERNEL32!GetLastError` at `0x18000487e`
- `KERNEL32!GetLastError` at `0x180004874`
- `KERNEL32!GetLastError` at `0x18000487e`

## pseudocode

```c
signed int IcpGetLastError(void)
{
  signed int result; // eax

  if ( !GetLastError() )
    return -2147467259;
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180004870  sub     rsp, 28h
0x180004874  call    cs:__imp_GetLastError
0x18000487a  test    eax, eax
0x18000487c  jz      short loc_180004892
0x18000487e  call    cs:__imp_GetLastError
0x180004884  test    eax, eax
0x180004886  jle     short loc_180004897
0x180004888  movzx   eax, ax
0x18000488b  or      eax, 80070000h
0x180004890  jmp     short loc_180004897
0x180004892  mov     eax, 80004005h
0x180004897  add     rsp, 28h
0x18000489b  retn
```
