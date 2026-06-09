# _com_raise_error(long,IErrorInfo *)

- ea: `0x180007f90`
- end: `0x180007fc3`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `51`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180002dd8`

## callees

- `0x180009ddb`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(__int64 a1, struct IErrorInfo *a2)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  __int128 v4; // [rsp+30h] [rbp-18h]

  v3 = -2147024882;
  pExceptionObject = &_com_error::`vftable';
  v4 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x180007f90  sub     rsp, 48h
0x180007f94  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x180007f9b  mov     [rsp+48h+var_20], 8007000Eh
0x180007fa3  xorps   xmm0, xmm0
0x180007fa6  mov     [rsp+48h+pExceptionObject], rax
0x180007fab  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180007fb2  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180007fb7  movdqu  [rsp+48h+var_18], xmm0
0x180007fbd  call    _CxxThrowException_0
```
