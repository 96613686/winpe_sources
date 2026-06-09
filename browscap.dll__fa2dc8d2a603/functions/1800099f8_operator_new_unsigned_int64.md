# operator new(unsigned __int64)

- ea: `0x1800099f8`
- end: `0x180009a28`
- name: `??2@YAPEAX_K@Z`
- size: `48`
- prototype: `void *__fastcall(unsigned __int64)`
- caller_count: `26`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000276c`
- `0x180003750`
- `0x1800039c4`
- `0x180003b20`
- `0x180003c50`
- `0x1800043bc`
- `0x1800045b4`
- `0x180007968`
- `0x180007a70`
- `0x180008ac4`
- `0x180008bc4`
- `0x180008e40`
- `0x180008fa8`
- `0x180009530`
- `0x1800096bc`
- `0x1800097a8`
- `0x180009ab4`
- `0x180009b10`
- `0x180009b68`
- `0x180009c40`
- `0x18000a1ac`
- `0x18000a2e4`
- `0x18000a750`
- `0x18000a920`
- `0x18000b000`
- `0x18000b0b8`

## callees

- `0x180009988`
- `0x1800099f8`
- `0x18000b4d1`

## import_xrefs

- `msvcrt!malloc` at `0x1800099fc`
- `msvcrt!malloc` at `0x1800099fc`

## pseudocode

```c
void *__fastcall operator new(size_t a1)
{
  void *result; // rax
  int v2; // edx
  struct IErrorInfo *v3; // r8
  bool v4; // r9
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  result = malloc(a1);
  if ( !result )
  {
    _com_error::_com_error((_com_error *)pExceptionObject, v2, v3, v4);
    throw (_com_error *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800099f8  sub     rsp, 48h
0x1800099fc  call    cs:__imp_malloc
0x180009a02  test    rax, rax
0x180009a05  jz      short loc_180009A0C
0x180009a07  add     rsp, 48h
0x180009a0b  retn
0x180009a0c  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180009a11  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180009a16  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180009a1d  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180009a22  call    _CxxThrowException_0
```
