# std::_List_alloc<0,std::_List_base_types<Repair *,std::allocator<Repair *>>>::_Buynode0(std::_List_node<Repair *,void *> *,std::_List_node<Repair *,void *> *)

- ea: `0x18000aa18`
- end: `0x18000aa64`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@PEAVRepair@@V?$allocator@PEAVRepair@@@std@@@std@@@std@@QEAAPEAU?$_List_node@PEAVRepair@@PEAX@2@PEAU32@0@Z`
- size: `76`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000a690`
- `0x18000a960`
- `0x18000f684`

## callees

- `0x18000123c`
- `0x180001578`
- `0x18000aa18`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<Repair *>>::_Buynode0(__int64 a1, _QWORD *a2, _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x18u);
  if ( !result )
    std::_Xbad_alloc();
  if ( !a2 )
  {
    a2 = result;
    a3 = result;
  }
  *result = a2;
  result[1] = a3;
  return result;
}

```

## disassembly

```asm
0x18000aa18  mov     [rsp+arg_8], rbx
0x18000aa1d  mov     [rsp+arg_0], rcx
0x18000aa22  push    rdi
0x18000aa23  sub     rsp, 20h
0x18000aa27  mov     rdi, r8
0x18000aa2a  mov     rbx, rdx
0x18000aa2d  mov     ecx, 18h; Size
0x18000aa32  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000aa37  mov     [rsp+28h+arg_0], rax
0x18000aa3c  test    rax, rax
0x18000aa3f  jz      short loc_18000AA5E
0x18000aa41  test    rbx, rbx
0x18000aa44  jnz     short loc_18000AA4C
0x18000aa46  mov     rbx, rax
0x18000aa49  mov     rdi, rax
0x18000aa4c  mov     [rax], rbx
0x18000aa4f  mov     [rax+8], rdi
0x18000aa53  mov     rbx, [rsp+28h+arg_8]
0x18000aa58  add     rsp, 20h
0x18000aa5c  pop     rdi
0x18000aa5d  retn
0x18000aa5e  call    ?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
```
