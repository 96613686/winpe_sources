# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x180015c0c`
- end: `0x180015c9b`
- name: `?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `143`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000edc4`
- `0x18000f1d8`

## callees

- `0x1800018a0`
- `0x18000d294`
- `0x18000e050`
- `0x180015c0c`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015c32`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180015c32`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(
        _QWORD *a1,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v8; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v9; // [rsp+28h] [rbp-30h]

  if ( a1[1] == 0x199999999999999LL )
    std::_Xlength_error("list too long");
  v4 = *a1;
  v8 = a1;
  v5 = operator new(0xA0u);
  v9 = v5;
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
    (Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v5 + 2),
    a2);
  ++a1[1];
  v6 = *(_QWORD **)(v4 + 8);
  *v5 = v4;
  v5[1] = v6;
  v9 = 0;
  *(_QWORD *)(v4 + 8) = v5;
  *v6 = v5;
  return std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(&v8);
}

```

## disassembly

```asm
0x180015c0c  push    rbx
0x180015c0e  push    rbp
0x180015c0f  push    rsi
0x180015c10  push    rdi
0x180015c11  sub     rsp, 38h
0x180015c15  mov     rbp, rdx
0x180015c18  mov     rsi, rcx
0x180015c1b  mov     rax, 199999999999999h
0x180015c25  cmp     [rcx+8], rax
0x180015c29  jnz     short loc_180015C39
0x180015c2b  lea     rcx, aListTooLong; "list too long"
0x180015c32  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180015c39  mov     rdi, [rcx]
0x180015c3c  mov     [rsp+58h+var_38], rsi
0x180015c41  mov     [rsp+58h+var_30], 0
0x180015c4a  mov     ecx, 0A0h; Size
0x180015c4f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180015c54  mov     rbx, rax
0x180015c57  mov     [rsp+58h+var_30], rax
0x180015c5c  lea     rcx, [rax+10h]; this
0x180015c60  mov     rdx, rbp; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x180015c63  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x180015c68  nop
0x180015c69  inc     qword ptr [rsi+8]
0x180015c6d  mov     rcx, [rdi+8]
0x180015c71  mov     [rbx], rdi
0x180015c74  mov     [rbx+8], rcx
0x180015c78  mov     [rsp+58h+var_30], 0
0x180015c81  mov     [rdi+8], rbx
0x180015c85  mov     [rcx], rbx
0x180015c88  lea     rcx, [rsp+58h+var_38]
0x180015c8d  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
0x180015c92  add     rsp, 38h
0x180015c96  pop     rdi
0x180015c97  pop     rsi
0x180015c98  pop     rbp
0x180015c99  pop     rbx
0x180015c9a  retn
```
