# ATL::AtlThrowImpl(long)

- ea: `0x180006a80`
- end: `0x180006aa2`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a618`
- `0x18000a6c0`
- `0x18000ac50`
- `0x18000ae58`
- `0x18000b590`
- `0x18000b7a8`
- `0x18000b9a8`
- `0x18000bf30`

## callees

- `0x18000255c`
- `0x180006900`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a1);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180006a80  sub     rsp, 28h
0x180006a84  mov     edx, ecx; int
0x180006a86  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180006a8b  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180006a90  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180006a97  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180006a9c  call    _CxxThrowException_0
```
