# ATL::CComObject<CIMOfferRA>::`vector deleting destructor'(uint)

- ea: `0x140003de0`
- end: `0x140003e10`
- name: `??_E?$CComObject@VCIMOfferRA@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIMOfferRA *__fastcall(CIMOfferRA *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003440`
- `0x140003de0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003dfc`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003dfc`

## pseudocode

```c
CIMOfferRA *__fastcall ATL::CComObject<CIMOfferRA>::`vector deleting destructor'(CIMOfferRA *a1, char a2)
{
  ATL::CComObject<CIMOfferRA>::~CComObject<CIMOfferRA>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003de0  mov     [rsp+arg_0], rbx
0x140003de5  push    rdi
0x140003de6  sub     rsp, 20h
0x140003dea  mov     ebx, edx
0x140003dec  mov     rdi, rcx
0x140003def  call    ??1?$CComObject@VCIMOfferRA@@@ATL@@UEAA@XZ; ATL::CComObject<CIMOfferRA>::~CComObject<CIMOfferRA>(void)
0x140003df4  test    bl, 1
0x140003df7  jz      short loc_140003E02
0x140003df9  mov     rcx, rdi
0x140003dfc  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003e02  mov     rbx, [rsp+28h+arg_0]
0x140003e07  mov     rax, rdi
0x140003e0a  add     rsp, 20h
0x140003e0e  pop     rdi
0x140003e0f  retn
```
