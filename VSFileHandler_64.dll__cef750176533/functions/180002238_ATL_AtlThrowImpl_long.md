# ATL::AtlThrowImpl(long)

- ea: `0x180002238`
- end: `0x18000225a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180001618`
- `0x180001a38`
- `0x180001f88`
- `0x1800038c4`
- `0x180003bb0`
- `0x180003be8`
- `0x180003d1c`
- `0x18000421c`
- `0x180004bb4`
- `0x180005538`
- `0x18000572c`
- `0x1800060c0`
- `0x180006878`
- `0x180006918`
- `0x1800069b4`
- `0x180006b4c`
- `0x180006b5c`
- `0x180006ce8`
- `0x180006f00`
- `0x18001ad8c`

## callees

- `0x180002230`
- `0x180009408`

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
0x180002238  sub     rsp, 28h
0x18000223c  mov     edx, ecx; int
0x18000223e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180002243  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180002248  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000224f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180002254  call    _CxxThrowException
```
