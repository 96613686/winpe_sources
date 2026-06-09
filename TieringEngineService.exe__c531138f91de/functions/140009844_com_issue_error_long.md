# _com_issue_error(long)

- ea: `0x140009844`
- end: `0x140009866`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000565c`
- `0x140006e70`

## callees

- `0x140004ee4`
- `0x14003faba`

## pseudocode

```c
void __fastcall __noreturn _com_issue_error(int a1)
{
  char pExceptionObject; // [rsp+38h] [rbp+10h] BYREF

  ATL::CAtlException::CAtlException((ATL::CAtlException *)&pExceptionObject, a1);
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x140009844  sub     rsp, 28h
0x140009848  mov     edx, ecx; int
0x14000984a  lea     rcx, [rsp+28h+pExceptionObject]; this
0x14000984f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x140009854  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x14000985b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140009860  call    _CxxThrowException_0
```
