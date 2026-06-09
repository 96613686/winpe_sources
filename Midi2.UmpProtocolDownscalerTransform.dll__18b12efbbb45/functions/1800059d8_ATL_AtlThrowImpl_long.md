# ATL::AtlThrowImpl(long)

- ea: `0x1800059d8`
- end: `0x1800059fa`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180004f28`
- `0x180005290`
- `0x18000586c`
- `0x1800058a0`
- `0x18000746c`
- `0x180007c0c`
- `0x180007dec`
- `0x18000a170`

## callees

- `0x180003a50`
- `0x180004494`

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
0x1800059d8  sub     rsp, 28h
0x1800059dc  mov     edx, ecx; int
0x1800059de  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800059e3  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800059e8  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800059ef  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800059f4  call    _CxxThrowException_0
```
