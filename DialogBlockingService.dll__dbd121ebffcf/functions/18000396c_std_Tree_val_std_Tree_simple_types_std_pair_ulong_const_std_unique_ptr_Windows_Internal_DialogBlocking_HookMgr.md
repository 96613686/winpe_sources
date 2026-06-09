# std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr,std::default_delete<Windows::Internal::DialogBlocking::HookMgr>>>,void *> *)

- ea: `0x18000396c`
- end: `0x1800039d8`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@1@@Z`
- size: `108`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000396c`
- `0x180003e18`
- `0x18000a328`

## callees

- `0x180001644`
- `0x18000396c`
- `0x18000899c`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  Windows::Internal::DialogBlocking::HookMgr *v6; // rdi
  void *v7; // rsi

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (Windows::Internal::DialogBlocking::HookMgr *)v3[5];
      v7 = v3;
      v3 = (_QWORD *)*v3;
      if ( v6 )
      {
        Windows::Internal::DialogBlocking::HookMgr::~HookMgr(v6);
        operator delete(v6, 0x28u);
      }
      operator delete(v7, 0x30u);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x18000396c  push    rbx
0x18000396e  push    rbp
0x18000396f  push    rsi
0x180003970  push    rdi
0x180003971  push    r14
0x180003973  sub     rsp, 20h
0x180003977  cmp     byte ptr [r8+19h], 0
0x18000397c  mov     rbx, r8
0x18000397f  mov     rbp, rdx
0x180003982  mov     r14, rcx
0x180003985  jnz     short loc_1800039CD
0x180003987  mov     r8, [rbx+10h]
0x18000398b  mov     rdx, rbp
0x18000398e  mov     rcx, r14
0x180003991  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CBKV?$unique_ptr@VHookMgr@DialogBlocking@Internal@Windows@@U?$default_delete@VHookMgr@DialogBlocking@Internal@Windows@@@std@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>>>(std::allocator<std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *>> &,std::_Tree_node<std::pair<ulong const,std::unique_ptr<Windows::Internal::DialogBlocking::HookMgr>>,void *> *)
0x180003996  mov     rdi, [rbx+28h]
0x18000399a  mov     rsi, rbx
0x18000399d  mov     rbx, [rbx]
0x1800039a0  test    rdi, rdi
0x1800039a3  jz      short loc_1800039BA
0x1800039a5  mov     rcx, rdi; this
0x1800039a8  call    ??1HookMgr@DialogBlocking@Internal@Windows@@QEAA@XZ; Windows::Internal::DialogBlocking::HookMgr::~HookMgr(void)
0x1800039ad  mov     edx, 28h ; '('; unsigned __int64
0x1800039b2  mov     rcx, rdi; void *
0x1800039b5  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800039ba  mov     edx, 30h ; '0'; unsigned __int64
0x1800039bf  mov     rcx, rsi; void *
0x1800039c2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800039c7  cmp     byte ptr [rbx+19h], 0
0x1800039cb  jz      short loc_180003987
0x1800039cd  add     rsp, 20h
0x1800039d1  pop     r14
0x1800039d3  pop     rdi
0x1800039d4  pop     rsi
0x1800039d5  pop     rbp
0x1800039d6  pop     rbx
0x1800039d7  retn
```
