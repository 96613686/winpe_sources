# std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface,std::default_delete<IPxlatInterface>>>>,0>>(void)

- ea: `0x18000f260`
- end: `0x18000f2d0`
- name: `??1?$_Tree@V?$_Tmap_traits@_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@U?$less@_K@2@V?$allocator@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(void **)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x18000f340`
- `0x18000f41c`

## callees

- `0x180002110`
- `0x18000e734`
- `0x18000f260`
- `0x1800132ac`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,std::unique_ptr<IPxlatInterface>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rbx
  IPxlatInterface *v3; // rsi
  void *v4; // rbp

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      v2[2]);
    v3 = (IPxlatInterface *)v2[5];
    v4 = v2;
    v2 = (_QWORD *)*v2;
    if ( v3 )
    {
      IPxlatInterface::~IPxlatInterface(v3);
      operator delete(v3, 0xE8u);
    }
    operator delete(v4, 0x30u);
  }
  operator delete(*a1, 0x30u);
}

```

## disassembly

```asm
0x18000f260  push    rbx
0x18000f262  push    rbp
0x18000f263  push    rsi
0x18000f264  push    rdi
0x18000f265  sub     rsp, 28h
0x18000f269  mov     rax, [rcx]
0x18000f26c  mov     rdi, rcx
0x18000f26f  mov     rbx, [rax+8]
0x18000f273  jmp     short loc_18000F2B5
0x18000f275  mov     r8, [rbx+10h]
0x18000f279  mov     rdx, rdi
0x18000f27c  mov     rcx, rdi
0x18000f27f  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_KV?$unique_ptr@VIPxlatInterface@@U?$default_delete@VIPxlatInterface@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>>>(std::allocator<std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *>> &,std::_Tree_node<std::pair<unsigned __int64 const,std::unique_ptr<IPxlatInterface>>,void *> *)
0x18000f284  mov     rsi, [rbx+28h]
0x18000f288  mov     rbp, rbx
0x18000f28b  mov     rbx, [rbx]
0x18000f28e  test    rsi, rsi
0x18000f291  jz      short loc_18000F2A8
0x18000f293  mov     rcx, rsi; this
0x18000f296  call    ??1IPxlatInterface@@QEAA@XZ; IPxlatInterface::~IPxlatInterface(void)
0x18000f29b  mov     edx, 0E8h; unsigned __int64
0x18000f2a0  mov     rcx, rsi; void *
0x18000f2a3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2a8  mov     edx, 30h ; '0'; unsigned __int64
0x18000f2ad  mov     rcx, rbp; void *
0x18000f2b0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f2b5  cmp     byte ptr [rbx+19h], 0
0x18000f2b9  jz      short loc_18000F275
0x18000f2bb  mov     rcx, [rdi]; void *
0x18000f2be  mov     edx, 30h ; '0'; unsigned __int64
0x18000f2c3  add     rsp, 28h
0x18000f2c7  pop     rdi
0x18000f2c8  pop     rsi
0x18000f2c9  pop     rbp
0x18000f2ca  pop     rbx
0x18000f2cb  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
