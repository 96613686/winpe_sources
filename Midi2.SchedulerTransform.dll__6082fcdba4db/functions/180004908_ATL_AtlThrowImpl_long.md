# ATL::AtlThrowImpl(long)

- ea: `0x180004908`
- end: `0x18000492a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003e5c`
- `0x1800041c0`
- `0x18000479c`
- `0x1800047d0`
- `0x18000639c`
- `0x180006b3c`
- `0x180006d1c`
- `0x1800090b0`

## callees

- `0x180002a74`
- `0x1800033bc`

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
0x180004908  sub     rsp, 28h
0x18000490c  mov     edx, ecx; int
0x18000490e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004913  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004918  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000491f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004924  call    _CxxThrowException_0
```
