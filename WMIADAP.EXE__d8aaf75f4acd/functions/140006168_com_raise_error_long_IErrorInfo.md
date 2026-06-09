# _com_raise_error(long,IErrorInfo *)

- ea: `0x140006168`
- end: `0x140006197`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `47`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140006084`

## callees

- `0x14000298c`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  void **pExceptionObject; // [rsp+20h] [rbp-28h] BYREF
  int v3; // [rsp+28h] [rbp-20h]
  __int128 v4; // [rsp+30h] [rbp-18h]

  v3 = a1;
  pExceptionObject = &_com_error::`vftable';
  v4 = 0;
  throw (_com_error *)&pExceptionObject;
}

```

## disassembly

```asm
0x140006168  sub     rsp, 48h
0x14000616c  lea     rax, ??_7_com_error@@6B@; const _com_error::`vftable'
0x140006173  mov     [rsp+48h+var_20], ecx
0x140006177  xorps   xmm0, xmm0
0x14000617a  mov     [rsp+48h+pExceptionObject], rax
0x14000617f  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x140006184  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x14000618b  movdqu  [rsp+48h+var_18], xmm0
0x140006191  call    _CxxThrowException_0
```
