# ATL::AtlThrowImpl(long)

- ea: `0x180006018`
- end: `0x18000603a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180005568`
- `0x1800058d0`
- `0x180005eac`
- `0x180005ee0`
- `0x180007aac`
- `0x18000824c`
- `0x18000842c`
- `0x18000a7b0`

## callees

- `0x180004188`
- `0x180004ad0`

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
0x180006018  sub     rsp, 28h
0x18000601c  mov     edx, ecx; int
0x18000601e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180006023  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180006028  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000602f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180006034  call    _CxxThrowException_0
```
