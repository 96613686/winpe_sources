# ATL::AtlThrowImpl(long)

- ea: `0x1800047f8`
- end: `0x18000481a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180003d48`
- `0x1800040b0`
- `0x18000468c`
- `0x1800046c0`
- `0x18000628c`
- `0x180006a2c`
- `0x180006c0c`
- `0x180008f90`

## callees

- `0x180002964`
- `0x1800032ac`

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
0x1800047f8  sub     rsp, 28h
0x1800047fc  mov     edx, ecx; int
0x1800047fe  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004803  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004808  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000480f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004814  call    _CxxThrowException_0
```
