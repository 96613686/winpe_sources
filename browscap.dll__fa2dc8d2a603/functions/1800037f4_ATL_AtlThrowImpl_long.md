# ATL::AtlThrowImpl(long)

- ea: `0x1800037f4`
- end: `0x180003816`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `23`
- callee_count: `2`
- tags: ``

## callers

- `0x180001010`
- `0x180001130`
- `0x18000276c`
- `0x180002b10`
- `0x180002cc8`
- `0x180002e4c`
- `0x1800034f8`
- `0x18000352c`
- `0x180003f7c`
- `0x180004a4c`
- `0x1800050c0`
- `0x180005408`
- `0x180005eb0`
- `0x1800061ec`
- `0x18000672c`
- `0x180006b14`
- `0x180007358`
- `0x180007570`
- `0x1800076e8`
- `0x180007968`
- `0x180007a70`
- `0x18000888c`
- `0x180009e8c`

## callees

- `0x1800022f8`
- `0x18000b4d1`

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
0x1800037f4  sub     rsp, 28h
0x1800037f8  mov     edx, ecx; int
0x1800037fa  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800037ff  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180003804  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000380b  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180003810  call    _CxxThrowException_0
```
