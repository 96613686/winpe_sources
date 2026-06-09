# ATL::AtlThrowImpl(long)

- ea: `0x180004684`
- end: `0x1800046a6`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `14`
- callee_count: `2`
- tags: ``

## callers

- `0x1800039b4`
- `0x180003ba8`
- `0x180003f3c`
- `0x180004518`
- `0x18000454c`
- `0x180004ee0`
- `0x18000663c`
- `0x180006f6c`
- `0x18000766c`
- `0x18000784c`
- `0x180008b4c`
- `0x180009250`
- `0x1800093f8`
- `0x1800098c0`

## callees

- `0x18000257c`
- `0x180002968`

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
0x180004684  sub     rsp, 28h
0x180004688  mov     edx, ecx; int
0x18000468a  lea     rcx, [rsp+28h+pExceptionObject]; this
0x18000468f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004694  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000469b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800046a0  call    _CxxThrowException_0
```
