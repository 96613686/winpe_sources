# PnpApiWrapper::Details::ConfigretToHresult(ulong)

- ea: `0x180047d74`
- end: `0x180047dc7`
- name: `?ConfigretToHresult@Details@PnpApiWrapper@@YAJK@Z`
- size: `83`
- prototype: `__int64 __fastcall(PnpApiWrapper::Details *__hidden this, unsigned int)`
- caller_count: `6`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180048034`
- `0x180048380`
- `0x1800486e0`
- `0x1800487e0`
- `0x180048c50`
- `0x180048eb4`

## callees

- `0x180047d74`

## pseudocode

```c
__int64 __fastcall PnpApiWrapper::Details::ConfigretToHresult(PnpApiWrapper::Details *this)
{
  __int64 result; // rax

  switch ( (_DWORD)this )
  {
    case 0:
      return 0;
    case 2:
      return 2147942414LL;
    case 0xD:
      return 2206912515LL;
    case 0x13:
      return 2206912517LL;
    case 0x25:
      return 2206912516LL;
    case 0x33:
      return 2147942405LL;
  }
  result = 2206912515LL;
  if ( (_DWORD)this != 55 )
    return 2206912518LL;
  return result;
}

```

## disassembly

```asm
0x180047d74  test    ecx, ecx
0x180047d76  jz      short loc_180047DC4
0x180047d78  cmp     ecx, 2
0x180047d7b  jz      short loc_180047DBD
0x180047d7d  cmp     ecx, 0Dh
0x180047d80  jz      short loc_180047DB6
0x180047d82  cmp     ecx, 13h
0x180047d85  jz      short loc_180047DAF
0x180047d87  cmp     ecx, 25h ; '%'
0x180047d8a  jz      short loc_180047DA8
0x180047d8c  cmp     ecx, 33h ; '3'
0x180047d8f  jz      short loc_180047DA1
0x180047d91  mov     eax, 838AD003h
0x180047d96  cmp     ecx, 37h ; '7'
0x180047d99  lea     edx, [rax+3]
0x180047d9c  cmovnz  eax, edx
0x180047d9f  retn
0x180047da1  mov     eax, 80070005h
0x180047da6  retn
0x180047da8  mov     eax, 838AD004h
0x180047dad  retn
0x180047daf  mov     eax, 838AD005h
0x180047db4  retn
0x180047db6  mov     eax, 838AD003h
0x180047dbb  retn
0x180047dbd  mov     eax, 8007000Eh
0x180047dc2  retn
0x180047dc4  xor     eax, eax
0x180047dc6  retn
```
