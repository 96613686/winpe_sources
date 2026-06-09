# HrGetLastError(void)

- ea: `0x180001c80`
- end: `0x180001c9b`
- name: `?HrGetLastError@@YAJXZ`
- size: `27`
- prototype: `__int64(void)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x180001820`
- `0x180001980`
- `0x180003550`
- `0x1800037c0`
- `0x180003850`
- `0x180003920`
- `0x180003f80`
- `0x1800067f0`
- `0x180006820`
- `0x180006870`
- `0x1800068b0`
- `0x180006ac0`
- `0x180007ba8`
- `0x180007f80`
- `0x180009834`
- `0x18000a0fc`
- `0x18000a374`
- `0x18000a8dc`
- `0x18000ab80`
- `0x18000b940`
- `0x18000e700`
- `0x18000e7b0`
- `0x18000e8e0`
- `0x18000eaa0`

## callees

- `0x180001c80`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180001c84`
- `KERNEL32!GetLastError` at `0x180001c84`

## pseudocode

```c
signed int HrGetLastError(void)
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
0x180001c80  sub     rsp, 28h
0x180001c84  call    cs:__imp_GetLastError
0x180001c8a  test    eax, eax
0x180001c8c  jle     short loc_180001C96
0x180001c8e  movzx   eax, ax
0x180001c91  or      eax, 80070000h
0x180001c96  add     rsp, 28h
0x180001c9a  retn
```
