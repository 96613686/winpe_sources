# std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x18001ec70`
- end: `0x18001ecf2`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `130`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180026a08`

## callees

- `0x180001bc8`
- `0x18000a600`
- `0x18001ec70`
- `0x18001ef84`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  void **v1; // rbx
  unsigned __int64 v3; // rdx
  unsigned __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  void *v6; // rcx

  v1 = *(void ***)(a1 + 8);
  if ( v1 )
  {
    std::vector<char>::~vector<char>(v1 + 14);
    operator delete(v1[13], v3);
    v1[13] = 0;
    operator delete(v1[12], v4);
    v1[12] = 0;
    operator delete(v1[11], v5);
    v1[11] = 0;
    std::wstring::~wstring(v1 + 6);
    std::wstring::~wstring(v1 + 2);
  }
  v6 = *(void **)(a1 + 8);
  if ( v6 )
    operator delete(v6, 0xA0u);
}

```

## disassembly

```asm
0x18001ec70  mov     [rsp+arg_0], rbx
0x18001ec75  push    rdi
0x18001ec76  sub     rsp, 20h
0x18001ec7a  mov     rbx, [rcx+8]
0x18001ec7e  mov     rdi, rcx
0x18001ec81  test    rbx, rbx
0x18001ec84  jz      short loc_18001ECD4
0x18001ec86  lea     rcx, [rbx+70h]
0x18001ec8a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001ec8f  mov     rcx, [rbx+68h]; void *
0x18001ec93  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ec98  mov     qword ptr [rbx+68h], 0
0x18001eca0  mov     rcx, [rbx+60h]; void *
0x18001eca4  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001eca9  mov     qword ptr [rbx+60h], 0
0x18001ecb1  mov     rcx, [rbx+58h]; void *
0x18001ecb5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ecba  lea     rcx, [rbx+30h]
0x18001ecbe  mov     qword ptr [rbx+58h], 0
0x18001ecc6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001eccb  lea     rcx, [rbx+10h]
0x18001eccf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ecd4  mov     rcx, [rdi+8]; void *
0x18001ecd8  test    rcx, rcx
0x18001ecdb  jz      short loc_18001ECE7
0x18001ecdd  mov     edx, 0A0h; unsigned __int64
0x18001ece2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001ece7  mov     rbx, [rsp+28h+arg_0]
0x18001ecec  add     rsp, 20h
0x18001ecf0  pop     rdi
0x18001ecf1  retn
```
