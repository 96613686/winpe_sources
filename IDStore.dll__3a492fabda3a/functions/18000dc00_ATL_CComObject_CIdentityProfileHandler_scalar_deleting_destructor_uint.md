# ATL::CComObject<CIdentityProfileHandler>::`scalar deleting destructor'(uint)

- ea: `0x18000dc00`
- end: `0x18000dc30`
- name: `??_G?$CComObject@VCIdentityProfileHandler@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIdentityProfileHandler *__fastcall(CIdentityProfileHandler *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x18000dc00`
- `0x18000dc38`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc1c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000dc1c`

## pseudocode

```c
CIdentityProfileHandler *__fastcall ATL::CComObject<CIdentityProfileHandler>::`scalar deleting destructor'(
        CIdentityProfileHandler *a1,
        char a2)
{
  ATL::CComObject<CIdentityProfileHandler>::~CComObject<CIdentityProfileHandler>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x18000dc00  mov     [rsp+arg_0], rbx
0x18000dc05  push    rdi
0x18000dc06  sub     rsp, 20h
0x18000dc0a  mov     ebx, edx
0x18000dc0c  mov     rdi, rcx
0x18000dc0f  call    ??1?$CComObject@VCIdentityProfileHandler@@@ATL@@UEAA@XZ; ATL::CComObject<CIdentityProfileHandler>::~CComObject<CIdentityProfileHandler>(void)
0x18000dc14  test    bl, 1
0x18000dc17  jz      short loc_18000DC22
0x18000dc19  mov     rcx, rdi
0x18000dc1c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000dc22  mov     rbx, [rsp+28h+arg_0]
0x18000dc27  mov     rax, rdi
0x18000dc2a  add     rsp, 20h
0x18000dc2e  pop     rdi
0x18000dc2f  retn
```
