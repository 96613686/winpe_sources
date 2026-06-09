# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::push_back(Microsoft::Windows::Performance::CCvDDCache::CCvDD &&)

- ea: `0x180026a08`
- end: `0x180026a97`
- name: `?push_back@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@QEAAX$$QEAUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `143`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f9e4`
- `0x18001fdf8`

## callees

- `0x180001b84`
- `0x18001deac`
- `0x18001ec70`
- `0x180026a08`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180026a2e`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180026a2e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::push_back(
        _QWORD *a1,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a2)
{
  __int64 v4; // rdi
  _QWORD *v5; // rbx
  _QWORD *v6; // rcx
  _QWORD *v7; // [rsp+20h] [rbp-38h] BYREF
  _QWORD *v8; // [rsp+28h] [rbp-30h]

  if ( a1[1] == 0x199999999999999LL )
    std::_Xlength_error("list too long");
  v4 = *a1;
  v7 = a1;
  v5 = operator new(0xA0u);
  v8 = v5;
  Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(
    (Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v5 + 2),
    a2);
  ++a1[1];
  v6 = *(_QWORD **)(v4 + 8);
  *v5 = v4;
  v5[1] = v6;
  v8 = 0;
  *(_QWORD *)(v4 + 8) = v5;
  *v6 = v5;
  std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>((__int64)&v7);
}

```

## disassembly

```asm
0x180026a08  push    rbx
0x180026a0a  push    rbp
0x180026a0b  push    rsi
0x180026a0c  push    rdi
0x180026a0d  sub     rsp, 38h
0x180026a11  mov     rbp, rdx
0x180026a14  mov     rsi, rcx
0x180026a17  mov     rax, 199999999999999h
0x180026a21  cmp     [rcx+8], rax
0x180026a25  jnz     short loc_180026A35
0x180026a27  lea     rcx, aListTooLong; "list too long"
0x180026a2e  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180026a35  mov     rdi, [rcx]
0x180026a38  mov     [rsp+58h+var_38], rsi
0x180026a3d  mov     [rsp+58h+var_30], 0
0x180026a46  mov     ecx, 0A0h; Size
0x180026a4b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180026a50  mov     rbx, rax
0x180026a53  mov     [rsp+58h+var_30], rax
0x180026a58  lea     rcx, [rax+10h]; this
0x180026a5c  mov     rdx, rbp; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x180026a5f  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x180026a64  nop
0x180026a65  inc     qword ptr [rsi+8]
0x180026a69  mov     rcx, [rdi+8]
0x180026a6d  mov     [rbx], rdi
0x180026a70  mov     [rbx+8], rcx
0x180026a74  mov     [rsp+58h+var_30], 0
0x180026a7d  mov     [rdi+8], rbx
0x180026a81  mov     [rcx], rbx
0x180026a84  lea     rcx, [rsp+58h+var_38]
0x180026a89  call    ??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)
0x180026a8e  add     rsp, 38h
0x180026a92  pop     rdi
0x180026a93  pop     rsi
0x180026a94  pop     rbp
0x180026a95  pop     rbx
0x180026a96  retn
```
