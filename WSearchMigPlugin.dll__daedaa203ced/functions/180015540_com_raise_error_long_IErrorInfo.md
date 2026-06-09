# _com_raise_error(long,IErrorInfo *)

- ea: `0x180015540`
- end: `0x180015565`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180015340`
- `0x180015358`

## callees

- `0x1800032a8`
- `0x18001544c`

## pseudocode

```c
void __fastcall __noreturn _com_raise_error(int a1, struct IErrorInfo *a2)
{
  _BYTE pExceptionObject[40]; // [rsp+20h] [rbp-28h] BYREF

  _com_error::_com_error((_com_error *)pExceptionObject, a1, a2);
  throw (_com_error *)pExceptionObject;
}

```

## disassembly

```asm
0x180015540  sub     rsp, 48h
0x180015544  mov     r8, rdx; struct IErrorInfo *
0x180015547  mov     edx, ecx; int
0x180015549  lea     rcx, [rsp+48h+pExceptionObject]; this
0x18001554e  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x180015553  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x18001555a  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x18001555f  call    _CxxThrowException_0
```
