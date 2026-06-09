# ATL::AtlThrowImpl(long)

- ea: `0x180020178`
- end: `0x18002019a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `7`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f49c`
- `0x18001fa78`
- `0x18001fcb0`
- `0x180020b20`
- `0x180021228`
- `0x18002140c`
- `0x180022644`

## callees

- `0x18001eddc`
- `0x180022e3b`

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
0x180020178  sub     rsp, 28h
0x18002017c  mov     edx, ecx; int
0x18002017e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180020183  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180020188  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18002018f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180020194  call    _CxxThrowException_0
```
