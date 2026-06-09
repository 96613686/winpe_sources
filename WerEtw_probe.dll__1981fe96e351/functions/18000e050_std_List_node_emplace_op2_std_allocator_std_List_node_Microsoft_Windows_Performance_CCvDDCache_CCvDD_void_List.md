# std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x18000e050`
- end: `0x18000e0d2`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `130`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180015c0c`

## callees

- `0x180001894`
- `0x18000b534`
- `0x18000e050`
- `0x18000e364`

## pseudocode

```c
void __fastcall std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(
        __int64 a1)
{
  void **v1; // rbx
  void *v3; // rcx

  v1 = *(void ***)(a1 + 8);
  if ( v1 )
  {
    std::vector<char>::~vector<char>(v1 + 14);
    operator delete(v1[13]);
    v1[13] = 0;
    operator delete(v1[12]);
    v1[12] = 0;
    operator delete(v1[11]);
    v1[11] = 0;
    std::wstring::~wstring(v1 + 6);
    std::wstring::~wstring(v1 + 2);
  }
  v3 = *(void **)(a1 + 8);
  if ( v3 )
    operator delete(v3);
}

```

## disassembly

```asm
0x18000e050  mov     [rsp+arg_0], rbx
0x18000e055  push    rdi
0x18000e056  sub     rsp, 20h
0x18000e05a  mov     rbx, [rcx+8]
0x18000e05e  mov     rdi, rcx
0x18000e061  test    rbx, rbx
0x18000e064  jz      short loc_18000E0B4
0x18000e066  lea     rcx, [rbx+70h]
0x18000e06a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18000e06f  mov     rcx, [rbx+68h]; Block
0x18000e073  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e078  mov     qword ptr [rbx+68h], 0
0x18000e080  mov     rcx, [rbx+60h]; Block
0x18000e084  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e089  mov     qword ptr [rbx+60h], 0
0x18000e091  mov     rcx, [rbx+58h]; Block
0x18000e095  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e09a  lea     rcx, [rbx+30h]
0x18000e09e  mov     qword ptr [rbx+58h], 0
0x18000e0a6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e0ab  lea     rcx, [rbx+10h]
0x18000e0af  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e0b4  mov     rcx, [rdi+8]; Block
0x18000e0b8  test    rcx, rcx
0x18000e0bb  jz      short loc_18000E0C7
0x18000e0bd  mov     edx, 0A0h
0x18000e0c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000e0c7  mov     rbx, [rsp+28h+arg_0]
0x18000e0cc  add     rsp, 20h
0x18000e0d0  pop     rdi
0x18000e0d1  retn
```
