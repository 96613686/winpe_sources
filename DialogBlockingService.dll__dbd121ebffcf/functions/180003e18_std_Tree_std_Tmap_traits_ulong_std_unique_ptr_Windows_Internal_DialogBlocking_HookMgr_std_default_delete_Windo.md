# std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>,0>>::~_Tree<std::_Tmap_traits<ulong,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>,0>>(void)

- ea: `0x180003e18`
- end: `0x180003e88`
- name: `??1?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA@XZ`
- size: `112`
- prototype: `void __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800099d8`

## callees

- `0x180001644`
- `0x18000396c`
- `0x180003e18`
- `0x18000899c`

## pseudocode

```c
void __fastcall std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>::~_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>,0>>(
        void **a1)
{
  _QWORD *v2; // rbx
  Windows::Internal::DialogBlocking::HookMgr *v3; // rsi
  void *v4; // rbp

  v2 = (_QWORD *)*((_QWORD *)*a1 + 1);
  while ( !*((_BYTE *)v2 + 25) )
  {
    std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(
      (__int64)a1,
      (__int64)a1,
      v2[2]);
    v3 = (Windows::Internal::DialogBlocking::HookMgr *)v2[5];
    v4 = v2;
    v2 = (_QWORD *)*v2;
    if ( v3 )
    {
      Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v3);
      operator delete(v3, 0x28u);
    }
    operator delete(v4, 0x30u);
  }
  operator delete(*a1, 0x30u);
}

```

## disassembly

```asm
0x180003e18  push    rbx
0x180003e1a  push    rbp
0x180003e1b  push    rsi
0x180003e1c  push    rdi
0x180003e1d  sub     rsp, 28h
0x180003e21  mov     rax, [rcx]
0x180003e24  mov     rdi, rcx
0x180003e27  mov     rbx, [rax+8]
0x180003e2b  jmp     short loc_180003E6D
0x180003e2d  mov     r8, [rbx+10h]
0x180003e31  mov     rdx, rdi
0x180003e34  mov     rcx, rdi
0x180003e37  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *> *)
0x180003e3c  mov     rsi, [rbx+28h]
0x180003e40  mov     rbp, rbx
0x180003e43  mov     rbx, [rbx]
0x180003e46  test    rsi, rsi
0x180003e49  jz      short loc_180003E60
0x180003e4b  mov     rcx, rsi; this
0x180003e4e  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x180003e53  mov     edx, 28h ; '('; unsigned __int64
0x180003e58  mov     rcx, rsi; void *
0x180003e5b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003e60  mov     edx, 30h ; '0'; unsigned __int64
0x180003e65  mov     rcx, rbp; void *
0x180003e68  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180003e6d  cmp     byte ptr [rbx+19h], 0
0x180003e71  jz      short loc_180003E2D
0x180003e73  mov     rcx, [rdi]; void *
0x180003e76  mov     edx, 30h ; '0'; unsigned __int64
0x180003e7b  add     rsp, 28h
0x180003e7f  pop     rdi
0x180003e80  pop     rsi
0x180003e81  pop     rbp
0x180003e82  pop     rbx
0x180003e83  jmp     ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
```
