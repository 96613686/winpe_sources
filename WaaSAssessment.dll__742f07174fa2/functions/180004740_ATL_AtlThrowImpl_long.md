# ATL::AtlThrowImpl(long)

- ea: `0x180004740`
- end: `0x180004762`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1800032f8`
- `0x18000369c`
- `0x180003c78`
- `0x180003cac`
- `0x180003ef0`
- `0x180004098`
- `0x18000455c`
- `0x18000509c`
- `0x1800056b8`
- `0x18000589c`

## callees

- `0x180002f98`
- `0x18001965f`

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
0x180004740  sub     rsp, 28h
0x180004744  mov     edx, ecx; int
0x180004746  lea     rcx, [rsp+28h+pExceptionObject]; this
0x18000474b  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004750  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180004757  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x18000475c  call    _CxxThrowException_0
```
