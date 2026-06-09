# std::_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>::~_List_node_emplace_op2<std::allocator<std::_List_node<Microsoft::Windows::Performance::CCvDDCache::CCvDD,void *>>>(void)

- ea: `0x18001fc60`
- end: `0x18001fce3`
- name: `??1?$_List_node_emplace_op2@V?$allocator@U?$_List_node@UCCvDD@CCvDDCache@Performance@Windows@Microsoft@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `131`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180027b70`

## callees

- `0x180001bf8`
- `0x18000a924`
- `0x18001fc60`
- `0x18001ff78`

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
0x18001fc60  mov     [rsp+arg_0], rbx
0x18001fc65  push    rdi
0x18001fc66  sub     rsp, 20h
0x18001fc6a  mov     rbx, [rcx+8]
0x18001fc6e  mov     rdi, rcx
0x18001fc71  test    rbx, rbx
0x18001fc74  jz      short loc_18001FCC4
0x18001fc76  lea     rcx, [rbx+70h]
0x18001fc7a  call    ??1?$vector@DV?$allocator@D@std@@@std@@QEAA@XZ; std::vector<char>::~vector<char>(void)
0x18001fc7f  mov     rcx, [rbx+68h]; void *
0x18001fc83  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc88  mov     qword ptr [rbx+68h], 0
0x18001fc90  mov     rcx, [rbx+60h]; void *
0x18001fc94  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fc99  mov     qword ptr [rbx+60h], 0
0x18001fca1  mov     rcx, [rbx+58h]; void *
0x18001fca5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fcaa  lea     rcx, [rbx+30h]
0x18001fcae  mov     qword ptr [rbx+58h], 0
0x18001fcb6  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fcbb  lea     rcx, [rbx+10h]
0x18001fcbf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001fcc4  mov     rcx, [rdi+8]; void *
0x18001fcc8  test    rcx, rcx
0x18001fccb  jz      short loc_18001FCD7
0x18001fccd  mov     edx, 0A0h; unsigned __int64
0x18001fcd2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fcd7  mov     rbx, [rsp+28h+arg_0]
0x18001fcdc  add     rsp, 20h
0x18001fce0  pop     rdi
0x18001fce1  retn
```
