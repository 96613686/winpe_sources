# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ulong const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(void)

- ea: `0x140015820`
- end: `0x140015894`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBKV?$shared_ptr@UProcessTracker@CExec@@@std@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x14001a43c`

## callees

- `0x1400026b8`
- `0x140015820`
- `0x140024010`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<unsigned long const,std::shared_ptr<CExec::ProcessTracker>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  volatile signed __int32 *v3; // rbx
  void *v4; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = *(volatile signed __int32 **)(v1 + 48);
    if ( v3 )
    {
      if ( _InterlockedExchangeAdd(v3 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v3)(v3);
        if ( _InterlockedExchangeAdd(v3 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v3 + 8LL))(v3);
      }
    }
  }
  v4 = *(void **)(a1 + 8);
  if ( v4 )
    operator delete(v4, 0x38u);
}

```

## disassembly

```asm
0x140015820  mov     [rsp+arg_8], rbx
0x140015825  push    rdi
0x140015826  sub     rsp, 20h
0x14001582a  mov     rbx, [rcx+8]
0x14001582e  mov     rdi, rcx
0x140015831  test    rbx, rbx
0x140015834  jz      short loc_140015876
0x140015836  mov     rbx, [rbx+30h]
0x14001583a  test    rbx, rbx
0x14001583d  jz      short loc_140015876
0x14001583f  or      eax, 0FFFFFFFFh
0x140015842  lock xadd [rbx+8], eax
0x140015847  cmp     eax, 1
0x14001584a  jnz     short loc_140015876
0x14001584c  mov     rax, [rbx]
0x14001584f  mov     rcx, rbx
0x140015852  mov     rax, [rax]
0x140015855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001585a  or      eax, 0FFFFFFFFh
0x14001585d  lock xadd [rbx+0Ch], eax
0x140015862  cmp     eax, 1
0x140015865  jnz     short loc_140015876
0x140015867  mov     rax, [rbx]
0x14001586a  mov     rcx, rbx
0x14001586d  mov     rax, [rax+8]
0x140015871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015876  mov     rcx, [rdi+8]; void *
0x14001587a  test    rcx, rcx
0x14001587d  jz      short loc_140015889
0x14001587f  mov     edx, 38h ; '8'; unsigned __int64
0x140015884  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015889  mov     rbx, [rsp+28h+arg_8]
0x14001588e  add     rsp, 20h
0x140015892  pop     rdi
0x140015893  retn
```
