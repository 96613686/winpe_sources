# ATL::AtlThrowImpl(long)

- ea: `0x180004768`
- end: `0x18000478a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003cb8`
- `0x180004020`
- `0x1800045fc`
- `0x180004630`
- `0x1800061fc`
- `0x18000699c`
- `0x180006b7c`
- `0x180008f00`

## callees

- `0x1800028d4`
- `0x18000321c`

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
0x180004768  sub     rsp, 28h
0x18000476c  mov     edx, ecx; int
0x18000476e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004773  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004778  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000477f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004784  call    _CxxThrowException_0
```
