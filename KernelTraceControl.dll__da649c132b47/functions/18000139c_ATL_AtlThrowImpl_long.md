# ATL::AtlThrowImpl(long)

- ea: `0x18000139c`
- end: `0x1800013be`
- name: `?AtlThrowImpl@ATL@@YAXJ@Z`
- size: `34`
- prototype: `void __fastcall __noreturn(int)`
- caller_count: `48`
- callee_count: `2`
- tags: ``

## callers

- `0x180001620`
- `0x180001788`
- `0x180008d5c`
- `0x180009018`
- `0x1800098d0`
- `0x18000c048`
- `0x18000ce70`
- `0x18000d728`
- `0x18000d7e8`
- `0x18000d9bc`
- `0x18000dc18`
- `0x18000e76c`
- `0x18000e858`
- `0x18000e954`
- `0x18000f7cc`
- `0x18000fee4`
- `0x1800100ac`
- `0x180010510`
- `0x180010624`
- `0x180010900`
- `0x180010a20`
- `0x180010c80`
- `0x180010e6c`
- `0x180011024`
- `0x180011134`
- `0x18001285c`
- `0x180012b8c`
- `0x180012df4`
- `0x180012ea8`
- `0x180012fe4`
- `0x1800130a8`
- `0x180013f50`
- `0x1800140dc`
- `0x1800150e8`
- `0x1800157a0`
- `0x180015a08`
- `0x180017354`
- `0x1800175e4`
- `0x180018cf4`
- `0x180019770`
- `0x180019a64`
- `0x18001e0e4`
- `0x180020cc0`
- `0x180021b6c`
- `0x180022440`
- `0x18002282c`
- `0x1800239d8`
- `0x180027d87`

## callees

- `0x180001394`
- `0x180026f66`

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
0x18000139c  sub     rsp, 28h
0x1800013a0  mov     edx, ecx; int
0x1800013a2  lea     rcx, [rsp+28h+pExceptionObject]; this
0x1800013a7  call    ??0CAtlException@ATL@@QEAA@J@Z; ATL::CAtlException::CAtlException(long)
0x1800013ac  lea     rdx, _TI1?AVCAtlException@ATL@@; pThrowInfo
0x1800013b3  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x1800013b8  call    _CxxThrowException_0
```
