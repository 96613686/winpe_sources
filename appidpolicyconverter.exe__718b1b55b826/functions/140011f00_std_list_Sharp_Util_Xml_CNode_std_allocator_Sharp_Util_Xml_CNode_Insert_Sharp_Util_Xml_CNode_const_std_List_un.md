# std::list<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::_Insert<Sharp::Util::Xml::CNode const &>(std::_List_unchecked_const_iterator<std::_List_val<std::_List_simple_types<Sharp::Util::Xml::CNode>>,std::_Iterator_base0>,Sharp::Util::Xml::CNode const &)

- ea: `0x140011f00`
- end: `0x140011f61`
- name: `??$_Insert@AEBVCNode@Xml@Util@Sharp@@@?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAXV?$_List_unchecked_const_iterator@V?$_List_val@U?$_List_simple_types@VCNode@Xml@Util@Sharp@@@std@@@std@@U_Iterator_base0@2@@1@AEBVCNode@Xml@Util@Sharp@@@Z`
- size: `97`
- prototype: `__int64 *__fastcall(__int64, __int64, const struct Sharp::Util::Xml::CNode *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400137d8`

## callees

- `0x140011ec0`
- `0x140011f00`

## import_xrefs

- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140011f3d`
- `msvcp110_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x140011f3d`

## pseudocode

```c
__int64 *__fastcall std::list<Sharp::Util::Xml::CNode>::_Insert<Sharp::Util::Xml::CNode const &>(
        __int64 a1,
        __int64 a2,
        const struct Sharp::Util::Xml::CNode *a3)
{
  __int64 v5; // r8
  __int64 v6; // rax
  __int64 *result; // rax

  v5 = std::_List_buy<Sharp::Util::Xml::CNode>::_Buynode<Sharp::Util::Xml::CNode const &>(
         a1,
         a2,
         *(_QWORD *)(a2 + 8),
         a3);
  v6 = *(_QWORD *)(a1 + 8);
  if ( v6 == 0x7FFFFFFFFFFFFFELL )
    std::_Xlength_error("list<T> too long");
  *(_QWORD *)(a1 + 8) = v6 + 1;
  *(_QWORD *)(a2 + 8) = v5;
  result = *(__int64 **)(v5 + 8);
  *result = v5;
  return result;
}

```

## disassembly

```asm
0x140011f00  mov     [rsp+arg_0], rbx
0x140011f05  push    rdi
0x140011f06  sub     rsp, 20h
0x140011f0a  mov     r9, r8
0x140011f0d  mov     rbx, rdx
0x140011f10  mov     r8, [rdx+8]
0x140011f14  mov     rdi, rcx
0x140011f17  call    ??$_Buynode@AEBVCNode@Xml@Util@Sharp@@@?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@1@PEAU21@0AEBVCNode@Xml@Util@Sharp@@@Z; std::_List_buy<Sharp::Util::Xml::CNode>::_Buynode<Sharp::Util::Xml::CNode const &>(std::_List_node<Sharp::Util::Xml::CNode,void *> *,std::_List_node<Sharp::Util::Xml::CNode,void *> *,Sharp::Util::Xml::CNode const &)
0x140011f1c  mov     r8, rax
0x140011f1f  mov     rdx, 7FFFFFFFFFFFFFEh
0x140011f29  mov     rax, [rdi+8]
0x140011f2d  sub     rdx, rax
0x140011f30  cmp     rdx, 1
0x140011f34  jnb     short loc_140011F44
0x140011f36  lea     rcx, aListTTooLong; "list<T> too long"
0x140011f3d  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x140011f44  inc     rax
0x140011f47  mov     [rdi+8], rax
0x140011f4b  mov     [rbx+8], r8
0x140011f4f  mov     rax, [r8+8]
0x140011f53  mov     rbx, [rsp+28h+arg_0]
0x140011f58  mov     [rax], r8
0x140011f5b  add     rsp, 20h
0x140011f5f  pop     rdi
0x140011f60  retn
```
