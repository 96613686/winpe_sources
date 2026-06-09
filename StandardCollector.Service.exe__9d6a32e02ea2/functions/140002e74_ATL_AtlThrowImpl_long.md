# ATL::AtlThrowImpl(long)

- ea: `0x140002e74`
- end: `0x140002e96`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `29`
- callee_count: `2`
- tags: ``

## callers

- `0x140001388`
- `0x1400024fc`
- `0x140002600`
- `0x140002688`
- `0x1400027c4`
- `0x140002da0`
- `0x140002e98`
- `0x140005b70`
- `0x14000697c`
- `0x14000792c`
- `0x140007f38`
- `0x14000914c`
- `0x14000918c`
- `0x14000f098`
- `0x14000f1d0`
- `0x14000f9d4`
- `0x140011b04`
- `0x140011cb0`
- `0x140011de4`
- `0x14001204c`
- `0x1400121e0`
- `0x1400124d0`
- `0x140012610`
- `0x140012844`
- `0x140012990`
- `0x140012a70`
- `0x140012aa0`
- `0x140012db0`
- `0x140014a6c`

## callees

- `0x140002e6c`
- `0x14001472c`

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
0x140002e74  sub     rsp, 28h
0x140002e78  mov     edx, ecx; int
0x140002e7a  lea     rcx, [rsp+28h+pExceptionObject]; this
0x140002e7f  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x140002e84  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x140002e8b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x140002e90  call    _CxxThrowException_0
```
