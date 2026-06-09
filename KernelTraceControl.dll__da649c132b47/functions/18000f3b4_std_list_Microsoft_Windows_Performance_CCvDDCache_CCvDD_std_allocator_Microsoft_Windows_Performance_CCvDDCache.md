# std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Buynode(std::_List_nod<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Node *,std::_List_nod<Microsoft::Windows::Performance::CCvDDCache::CCvDD,std::allocator<Microsoft::Windows::Performance::CCvDDCache::CCvDD>>::_Node *,Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)

- ea: `0x18000f3b4`
- end: `0x18000f436`
- name: `?_Buynode@?$list@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@std@@IEAAPEAU_Node@?$_List_nod@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@V?$allocator@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@std@@@2@PEAU342@0AEBUCCvDD@CCvDDCache@Performance@Windows@Microsoft@@@Z`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d360`

## callees

- `0x180009018`
- `0x18000f3b4`
- `0x18002687c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall std::list<Microsoft::Windows::Performance::CCvDDCache::CCvDD>::_Buynode(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *a4)
{
  _QWORD *v7; // rax
  _QWORD *v8; // rbx
  _QWORD *v9; // rax
  Microsoft::Windows::Performance::CCvDDCache::CCvDD *v10; // rcx
  _QWORD *v12; // [rsp+50h] [rbp+8h]

  v7 = operator new(0xB8u);
  v8 = v7;
  v12 = v7;
  try
  {
    if ( v7 )
      *v7 = a2;
    v9 = v7 + 1;
    if ( v9 )
      *v9 = a3;
    v10 = (Microsoft::Windows::Performance::CCvDDCache::CCvDD *)(v8 + 2);
    if ( v8 != (_QWORD *)-16LL )
      Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(v10, a4);
  }
  catch ( ... )
  {
    std::allocator<unsigned int>::deallocate(v10, v12);
    throw;
  }
  return v8;
}

```

## disassembly

```asm
0x18000f3b4  mov     rax, rsp
0x18000f3b7  mov     [rax+8], rcx
0x18000f3bb  push    r14
0x18000f3bd  sub     rsp, 40h
0x18000f3c1  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x18000f3c9  mov     [rax+10h], rbx
0x18000f3cd  mov     [rax+18h], rsi
0x18000f3d1  mov     [rax+20h], rdi
0x18000f3d5  mov     r14, r9
0x18000f3d8  mov     rsi, r8
0x18000f3db  mov     rdi, rdx
0x18000f3de  mov     ecx, 0B8h; Size
0x18000f3e3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f3e8  mov     rbx, rax
0x18000f3eb  mov     [rsp+48h+arg_0], rax
0x18000f3f0  test    rax, rax
0x18000f3f3  jz      short loc_18000F3F8
0x18000f3f5  mov     [rax], rdi
0x18000f3f8  add     rax, 8
0x18000f3fc  jz      short loc_18000F401
0x18000f3fe  mov     [rax], rsi
0x18000f401  lea     rcx, [rbx+10h]; this
0x18000f405  mov     [rsp+48h+var_20], rcx
0x18000f40a  mov     [rsp+48h+var_18], rcx
0x18000f40f  test    rcx, rcx
0x18000f412  jz      short loc_18000F41D
0x18000f414  mov     rdx, r14; struct Microsoft::Windows::Performance::CCvDDCache::CCvDD *
0x18000f417  call    ??0CCvDD@CCvDDCache@Performance@Windows@Microsoft@@QEAA@AEBU01234@@Z; Microsoft::Windows::Performance::CCvDDCache::CCvDD::CCvDD(Microsoft::Windows::Performance::CCvDDCache::CCvDD const &)
0x18000f41c  nop
0x18000f41d  mov     rax, rbx
0x18000f420  mov     rbx, [rsp+48h+arg_8]
0x18000f425  mov     rsi, [rsp+48h+arg_10]
0x18000f42a  mov     rdi, [rsp+48h+arg_18]
0x18000f42f  add     rsp, 40h
0x18000f433  pop     r14
0x18000f435  retn
```
