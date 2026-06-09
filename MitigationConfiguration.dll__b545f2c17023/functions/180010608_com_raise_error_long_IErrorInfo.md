# _com_raise_error(long,IErrorInfo *)

- ea: `0x180010608`
- end: `0x18001062d`
- name: `?_com_raise_error@@YAXJPEAUIErrorInfo@@@Z`
- size: `37`
- prototype: `void __fastcall __noreturn(int, struct IErrorInfo *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180010438`
- `0x18001044c`

## callees

- `0x180002654`
- `0x180010538`

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
0x180010608  sub     rsp, 48h
0x18001060c  mov     r8, rdx; struct IErrorInfo *
0x18001060f  mov     edx, ecx; int
0x180010611  lea     rcx, [rsp+48h+pExceptionObject]; this
0x180010616  call    ??0_com_error@@QEAA@JPEAUIErrorInfo@@_N@Z; _com_error::_com_error(long,IErrorInfo *,bool)
0x18001061b  lea     rdx, _TI1?AV_com_error@@; pThrowInfo
0x180010622  lea     rcx, [rsp+48h+pExceptionObject]; pExceptionObject
0x180010627  call    _CxxThrowException_0
```
