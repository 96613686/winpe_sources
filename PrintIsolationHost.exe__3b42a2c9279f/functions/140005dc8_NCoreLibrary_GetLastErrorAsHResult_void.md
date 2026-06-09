# NCoreLibrary::GetLastErrorAsHResult(void)

- ea: `0x140005dc8`
- end: `0x140005de3`
- name: `?GetLastErrorAsHResult@NCoreLibrary@@YAJXZ`
- size: `27`
- prototype: `__int64 __fastcall(NCoreLibrary *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x140005ffc`
- `0x140006dcc`

## callees

- `0x140005dc8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140005dcc`
- `KERNEL32!GetLastError` at `0x140005dcc`

## pseudocode

```c
signed int __fastcall NCoreLibrary::GetLastErrorAsHResult(NCoreLibrary *this)
{
  signed int result; // eax

  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x140005dc8  sub     rsp, 28h
0x140005dcc  call    cs:__imp_GetLastError
0x140005dd2  test    eax, eax
0x140005dd4  jle     short loc_140005DDE
0x140005dd6  movzx   eax, ax
0x140005dd9  or      eax, 80070000h
0x140005dde  add     rsp, 28h
0x140005de2  retn
```
