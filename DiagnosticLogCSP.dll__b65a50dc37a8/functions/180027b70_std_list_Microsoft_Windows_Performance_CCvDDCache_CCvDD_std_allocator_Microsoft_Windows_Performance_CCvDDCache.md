# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x180027b70`
- end: `0x180027c06`
- name: `?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `150`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180020a14`
- `0x180020e38`

## callees

- `0x180001bb4`
- `0x18001ee48`
- `0x18001fc60`
- `0x180027b70`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180027b96`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180027b96`

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
0x180027b70  push    rbx
0x180027b72  push    rbp
0x180027b73  push    rsi
0x180027b74  push    rdi
0x180027b75  sub     rsp, 38h
0x180027b79  mov     rbp, rdx
0x180027b7c  mov     rsi, rcx
0x180027b7f  mov     rax, 199999999999999h
0x180027b89  cmp     [rcx+8], rax
0x180027b8d  jnz     short loc_180027BA3
0x180027b8f  lea     rcx, aListTooLong; "list too long"
0x180027b96  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180027ba3  mov     rdi, [rcx]
0x180027ba6  mov     [rsp+58h+var_38], rsi
0x180027bab  mov     [rsp+58h+var_30], 0
0x180027bb4  mov     ecx, 0A0h; Size
0x180027bb9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180027bbe  mov     rbx, rax
0x180027bc1  mov     [rsp+58h+var_30], rax
0x180027bc6  lea     rcx, [rax+10h]; this
0x180027bca  mov     rdx, rbp; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x180027bcd  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x180027bd2  nop
0x180027bd3  inc     qword ptr [rsi+8]
0x180027bd7  mov     rcx, [rdi+8]
0x180027bdb  mov     [rbx], rdi
0x180027bde  mov     [rbx+8], rcx
0x180027be2  mov     [rsp+58h+var_30], 0
0x180027beb  mov     [rdi+8], rbx
0x180027bef  mov     [rcx], rbx
0x180027bf2  lea     rcx, [rsp+58h+var_38]
0x180027bf7  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
0x180027bfc  add     rsp, 38h
0x180027c00  pop     rdi
0x180027c01  pop     rsi
0x180027c02  pop     rbp
0x180027c03  pop     rbx
0x180027c04  retn
```
