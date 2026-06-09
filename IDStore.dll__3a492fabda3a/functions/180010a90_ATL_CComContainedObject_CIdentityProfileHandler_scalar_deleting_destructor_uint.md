# ATL::CComContainedObject<CIdentityProfileHandler>::`scalar deleting destructor'(uint)

- ea: `0x180010a90`
- end: `0x180010ac0`
- name: `??_G?$CComContainedObject@VCIdentityProfileHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIdentityProfileHandler *__fastcall(CIdentityProfileHandler *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000dc78`
- `0x180010a90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180010aac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180010aac`

## pseudocode

```c
CIdentityProfileHandler *__fastcall ATL::CComContainedObject<CIdentityProfileHandler>::`scalar deleting destructor'(
        CIdentityProfileHandler *a1,
        char a2)
{
  CIdentityProfileHandler::~CIdentityProfileHandler(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180010a90  mov     [rsp+arg_0], rbx
0x180010a95  push    rdi
0x180010a96  sub     rsp, 20h
0x180010a9a  mov     ebx, edx
0x180010a9c  mov     rdi, rcx
0x180010a9f  call    ??1CIdentityProfileHandler@@UEAA@XZ; CIdentityProfileHandler::~CIdentityProfileHandler(void)
0x180010aa4  test    bl, 1
0x180010aa7  jz      short loc_180010AB2
0x180010aa9  mov     rcx, rdi
0x180010aac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180010ab2  mov     rbx, [rsp+28h+arg_0]
0x180010ab7  mov     rax, rdi
0x180010aba  add     rsp, 20h
0x180010abe  pop     rdi
0x180010abf  retn
```
