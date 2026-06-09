# ATL::AtlThrowImpl(long)

- ea: `0x140003b88`
- end: `0x140003baa`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `10`
- callee_count: `2`
- tags: ``

## callers

- `0x1400028c0`
- `0x140002bec`
- `0x1400031c8`
- `0x1400031fc`
- `0x140003334`
- `0x1400034dc`
- `0x1400039a4`
- `0x1400048d0`
- `0x140004eb8`
- `0x140005098`

## callees

- `0x1400020ac`
- `0x1400025c8`

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
0x140003b88  sub     rsp, 28h
0x140003b8c  mov     edx, ecx; int
0x140003b8e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x140003b93  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x140003b98  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x140003b9f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140003ba4  call    _CxxThrowException_0
```
