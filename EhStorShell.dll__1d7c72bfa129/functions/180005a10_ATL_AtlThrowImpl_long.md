# ATL::AtlThrowImpl(long)

- ea: `0x180005a10`
- end: `0x180005a2a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800059a4`
- `0x1800059dc`
- `0x180007f20`
- `0x180008570`
- `0x180009b44`
- `0x180009b6c`

## callees

- `0x18000b538`

## pseudocode

```c
void __fastcall __noreturn ATL::AtlThrowImpl(int a1)
{
  int pExceptionObject; // [rsp+30h] [rbp+8h] BYREF

  pExceptionObject = a1;
  throw (ATL::CAtlException *)&pExceptionObject;
}

```

## disassembly

```asm
0x180005a10  sub     rsp, 28h
0x180005a14  mov     [rsp+28h+pExceptionObject], ecx
0x180005a18  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x180005a1f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180005a24  call    _CxxThrowException_0
```
