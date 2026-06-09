# ATL::AtlThrowImpl(long)

- ea: `0x180004eb8`
- end: `0x180004eda`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x18000440c`
- `0x180004770`
- `0x180004d4c`
- `0x180004d80`
- `0x18000695c`
- `0x1800070fc`
- `0x1800072dc`
- `0x1800095d0`

## callees

- `0x180003004`
- `0x180003970`

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
0x180004eb8  sub     rsp, 28h
0x180004ebc  mov     edx, ecx; int
0x180004ebe  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004ec3  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004ec8  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180004ecf  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004ed4  call    _CxxThrowException_0
```
