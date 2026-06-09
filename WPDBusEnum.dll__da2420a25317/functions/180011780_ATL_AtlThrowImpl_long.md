# ATL::AtlThrowImpl(long)

- ea: `0x180011780`
- end: `0x18001179a`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `26`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `6`
- callee_count: `1`
- tags: ``

## callers

- `0x1800116ac`
- `0x180011734`
- `0x180011948`
- `0x180011db0`
- `0x180011de8`
- `0x180011ee0`

## callees

- `0x1800154f0`

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
0x180011780  sub     rsp, 28h
0x180011784  mov     [rsp+28h+pExceptionObject], ecx
0x180011788  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x18001178f  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180011794  call    _CxxThrowException_0
```
