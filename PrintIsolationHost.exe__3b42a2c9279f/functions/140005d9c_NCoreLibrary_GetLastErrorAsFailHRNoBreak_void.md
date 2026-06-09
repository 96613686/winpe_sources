# NCoreLibrary::GetLastErrorAsFailHRNoBreak(void)

- ea: `0x140005d9c`
- end: `0x140005dc0`
- name: `?GetLastErrorAsFailHRNoBreak@NCoreLibrary@@YAJXZ`
- size: `36`
- prototype: `__int64 __fastcall(NCoreLibrary *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005ffc`
- `0x140006694`

## callees

- `0x140005d9c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005da0`
- `KERNEL32!GetLastError` at `0x140005da0`

## pseudocode

```c
signed int __fastcall NCoreLibrary::GetLastErrorAsFailHRNoBreak(NCoreLibrary *this)
{
  signed int result; // eax

  result = GetLastError();
  if ( !result )
    return -2147467259;
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140005d9c  sub     rsp, 28h
0x140005da0  call    cs:__imp_GetLastError
0x140005da6  test    eax, eax
0x140005da8  jnz     short loc_140005DB1
0x140005daa  mov     eax, 80004005h
0x140005daf  jmp     short loc_140005DBB
0x140005db1  jle     short loc_140005DBB
0x140005db3  movzx   eax, ax
0x140005db6  or      eax, 80070000h
0x140005dbb  add     rsp, 28h
0x140005dbf  retn
```
