# ATL::CComObject<CMsMpComFactoryHome>::`vector deleting destructor'(uint)

- ea: `0x180002e90`
- end: `0x180002ec0`
- name: `??_E?$CComObject@VCMsMpComFactoryHome@@@ATL@@UEAAPEAXI@Z`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002c90`
- `0x180002e90`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180002eac`
- `msvcrt!??3@YAXPEAX@Z` at `0x180002eac`

## pseudocode

```c
void *__fastcall ATL::CComObject<CMsMpComFactoryHome>::`vector deleting destructor'(void *a1, char a2)
{
  ATL::CComObject<CMsMpComFactoryHome>::~CComObject<CMsMpComFactoryHome>((__int64)a1);
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180002e90  mov     [rsp+arg_0], rbx
0x180002e95  push    rdi
0x180002e96  sub     rsp, 20h
0x180002e9a  mov     ebx, edx
0x180002e9c  mov     rdi, rcx
0x180002e9f  call    ??1?$CComObject@VCMsMpComFactoryHome@@@ATL@@UEAA@XZ; ATL::CComObject<CMsMpComFactoryHome>::~CComObject<CMsMpComFactoryHome>(void)
0x180002ea4  test    bl, 1
0x180002ea7  jz      short loc_180002EB2
0x180002ea9  mov     rcx, rdi
0x180002eac  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180002eb2  mov     rbx, [rsp+28h+arg_0]
0x180002eb7  mov     rax, rdi
0x180002eba  add     rsp, 20h
0x180002ebe  pop     rdi
0x180002ebf  retn
```
