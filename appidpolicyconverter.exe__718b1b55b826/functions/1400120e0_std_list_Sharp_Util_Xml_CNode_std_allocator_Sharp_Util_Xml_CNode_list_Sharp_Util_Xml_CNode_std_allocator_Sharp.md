# std::list<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>::~list<Sharp::Util::Xml::CNode,std::allocator<Sharp::Util::Xml::CNode>>(void)

- ea: `0x1400120e0`
- end: `0x140012131`
- name: `??1?$list@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAA@XZ`
- size: `81`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14001377c`
- `0x14001534d`
- `0x140015399`
- `0x1400153ff`

## callees

- `0x140009dcc`
- `0x1400120e0`
- `0x1400134f4`

## pseudocode

```c
__int64 __fastcall std::list<Sharp::Util::Xml::CNode>::~list<Sharp::Util::Xml::CNode>(__int64 a1)
{
  _QWORD *v2; // rdx
  _QWORD *v3; // rbx

  v2 = **(_QWORD ***)a1;
  **(_QWORD **)a1 = *(_QWORD *)a1;
  *(_QWORD *)(*(_QWORD *)a1 + 8LL) = *(_QWORD *)a1;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v2 != *(_QWORD **)a1 )
  {
    do
    {
      v3 = (_QWORD *)*v2;
      std::_List_buy<Sharp::Util::Xml::CNode>::_Freenode();
      v2 = v3;
    }
    while ( v3 != *(_QWORD **)a1 );
  }
  return std::_List_buy<std::wstring>::~_List_buy<std::wstring>(a1);
}

```

## disassembly

```asm
0x1400120e0  mov     [rsp+arg_8], rbx
0x1400120e5  mov     [rsp+arg_0], rcx
0x1400120ea  push    rdi
0x1400120eb  sub     rsp, 20h
0x1400120ef  mov     rdi, rcx
0x1400120f2  mov     rax, [rcx]
0x1400120f5  mov     rdx, [rax]
0x1400120f8  mov     [rax], rax
0x1400120fb  mov     rax, [rcx]
0x1400120fe  mov     [rax+8], rax
0x140012102  mov     qword ptr [rcx+8], 0
0x14001210a  cmp     rdx, [rcx]
0x14001210d  jz      short loc_14001211F
0x14001210f  mov     rbx, [rdx]
0x140012112  call    ?_Freenode@?$_List_buy@VCNode@Xml@Util@Sharp@@V?$allocator@VCNode@Xml@Util@Sharp@@@std@@@std@@QEAAXPEAU?$_List_node@VCNode@Xml@Util@Sharp@@PEAX@2@@Z; std::_List_buy<Sharp::Util::Xml::CNode>::_Freenode(std::_List_node<Sharp::Util::Xml::CNode,void *> *)
0x140012117  mov     rdx, rbx
0x14001211a  cmp     rbx, [rdi]
0x14001211d  jnz     short loc_14001210F
0x14001211f  mov     rcx, rdi
0x140012122  mov     rbx, [rsp+28h+arg_8]
0x140012127  add     rsp, 20h
0x14001212b  pop     rdi
0x14001212c  jmp     ??1?$_List_buy@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAA@XZ; std::_List_buy<std::wstring>::~_List_buy<std::wstring>(void)
```
