# ATL::AtlThrowImpl(long)

- ea: `0x180004328`
- end: `0x18000434a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `16`
- callee_count: `2`
- tags: ``

## callers

- `0x180002e98`
- `0x180003280`
- `0x18000385c`
- `0x180003890`
- `0x180003ad4`
- `0x180003c7c`
- `0x180004144`
- `0x180004e2c`
- `0x180005588`
- `0x180005764`
- `0x180007090`
- `0x180007368`
- `0x180007be0`
- `0x180008eac`
- `0x180009700`
- `0x180009b54`

## callees

- `0x1800024ec`
- `0x1800028d8`

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
0x180004328  sub     rsp, 28h
0x18000432c  mov     edx, ecx; int
0x18000432e  lea     rcx, [rsp+28h+pExceptionObject]; this
0x180004333  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x180004338  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18000433f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180004344  call    _CxxThrowException_0
```
