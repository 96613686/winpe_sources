# ATL::AtlThrowImpl(long)

- ea: `0x180004e40`
- end: `0x180004e62`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x18000462c`
- `0x180004c08`
- `0x1800057d0`
- `0x180005e98`
- `0x18000607c`
- `0x180007274`

## callees

- `0x180003fbc`
- `0x180009f64`

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
0x180004e40  sub     rsp, 28h
0x180004e44  mov     edx, ecx; int
0x180004e46  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004e4b  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004e50  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180004e57  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004e5c  call    _CxxThrowException_0
```
