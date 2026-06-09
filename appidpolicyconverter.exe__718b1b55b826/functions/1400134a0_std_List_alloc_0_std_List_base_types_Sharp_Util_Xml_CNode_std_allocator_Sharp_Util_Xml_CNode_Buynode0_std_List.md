# std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>>::_Buynode0(std::_List_node<Sharp::Util::Xml::CNode,void *> *,std::_List_node<Sharp::Util::Xml::CNode,void *> *)

- ea: `0x1400134a0`
- end: `0x1400134ed`
- name: `?_Buynode0@?$_List_alloc@$0A@U?$_List_base_types@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@@std@@QEAAPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@2@PEAU32@0@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *, _QWORD *)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140011ec0`
- `0x140011f68`

## callees

- `0x140001530`
- `0x1400134a0`

## import_xrefs

- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400134c9`
- `msvcp110_win!?_Xbad_alloc@std@@YAXXZ` at `0x1400134c9`

## pseudocode

```c
_QWORD *__fastcall std::_List_alloc<0,std::_List_base_types<Sharp::Util::Xml::CNode>>::_Buynode0(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3)
{
  _QWORD *result; // rax

  result = operator new(0x20u);
  if ( !result )
  {
    std::_Xbad_alloc();
    __debugbreak();
  }
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
0x1400134a0  mov     [rsp+arg_8], rbx
0x1400134a5  mov     [rsp+arg_0], rcx
0x1400134aa  push    rdi
0x1400134ab  sub     rsp, 20h
0x1400134af  mov     rdi, r8
0x1400134b2  mov     rbx, rdx
0x1400134b5  mov     ecx, 20h ; ' '; Size
0x1400134ba  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400134bf  mov     [rsp+28h+arg_0], rax
0x1400134c4  test    rax, rax
0x1400134c7  jnz     short loc_1400134D0
0x1400134c9  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x1400134cf  int     3; Trap to Debugger
0x1400134d0  test    rbx, rbx
0x1400134d3  jnz     short loc_1400134DB
0x1400134d5  mov     rbx, rax
0x1400134d8  mov     rdi, rax
0x1400134db  mov     [rax], rbx
0x1400134de  mov     [rax+8], rdi
0x1400134e2  mov     rbx, [rsp+28h+arg_8]
0x1400134e7  add     rsp, 20h
0x1400134eb  pop     rdi
0x1400134ec  retn
```
