# ATL::CComObject<CIMRequestRA>::`scalar deleting destructor'(uint)

- ea: `0x140003e20`
- end: `0x140003e50`
- name: `??_G?$CComObject@VCIMRequestRA@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CIMRequestRA *__fastcall(CIMRequestRA *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140003480`
- `0x140003e20`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x140003e3c`
- `msvcrt!??3@YAXPEAX@Z` at `0x140003e3c`

## pseudocode

```c
CIMRequestRA *__fastcall ATL::CComObject<CIMRequestRA>::`scalar deleting destructor'(CIMRequestRA *a1, char a2)
{
  ATL::CComObject<CIMRequestRA>::~CComObject<CIMRequestRA>(a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x140003e20  mov     [rsp+arg_0], rbx
0x140003e25  push    rdi
0x140003e26  sub     rsp, 20h
0x140003e2a  mov     ebx, edx
0x140003e2c  mov     rdi, rcx
0x140003e2f  call    ??1?$CComObject@VCIMRequestRA@@@ATL@@UEAA@XZ; ATL::CComObject<CIMRequestRA>::~CComObject<CIMRequestRA>(void)
0x140003e34  test    bl, 1
0x140003e37  jz      short loc_140003E42
0x140003e39  mov     rcx, rdi
0x140003e3c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x140003e42  mov     rbx, [rsp+28h+arg_0]
0x140003e47  mov     rax, rdi
0x140003e4a  add     rsp, 20h
0x140003e4e  pop     rdi
0x140003e4f  retn
```
