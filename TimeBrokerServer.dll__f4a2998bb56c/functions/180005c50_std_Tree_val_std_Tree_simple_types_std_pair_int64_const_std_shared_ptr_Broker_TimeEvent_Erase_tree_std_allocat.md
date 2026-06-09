# std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)

- ea: `0x180005c50`
- end: `0x180005d01`
- name: `??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z`
- size: `177`
- prototype: `void __fastcall(__int64, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180005c50`
- `0x180005d10`
- `0x180011be8`

## callees

- `0x180005c50`
- `0x1800131e4`
- `0x18001c010`

## pseudocode

```c
void __fastcall std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  _QWORD *v3; // rbx
  volatile signed __int32 *v6; // rdi
  void *v7; // r14

  v3 = (_QWORD *)a3;
  if ( !*(_BYTE *)(a3 + 25) )
  {
    do
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(
        a1,
        a2,
        v3[2]);
      v6 = (volatile signed __int32 *)v3[6];
      v7 = v3;
      v3 = (_QWORD *)*v3;
      if ( v6 && _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
        if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
      }
      operator delete(v7, 0x38u);
    }
    while ( !*((_BYTE *)v3 + 25) );
  }
}

```

## disassembly

```asm
0x180005c50  mov     [rsp+arg_10], rbx
0x180005c55  mov     [rsp+arg_18], rbp
0x180005c5a  push    rsi
0x180005c5b  sub     rsp, 20h
0x180005c5f  cmp     byte ptr [r8+19h], 0
0x180005c64  mov     rbx, r8
0x180005c67  mov     rsi, rdx
0x180005c6a  mov     rbp, rcx
0x180005c6d  jnz     short loc_180005CC3
0x180005c6f  mov     [rsp+28h+arg_0], rdi
0x180005c74  mov     [rsp+28h+arg_8], r14
0x180005c79  mov     r8, [rbx+10h]
0x180005c7d  mov     rdx, rsi
0x180005c80  mov     rcx, rbp
0x180005c83  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@$$CB_JV?$shared_ptr@VTimeEvent@Broker@@@std@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>>>(std::allocator<std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *>> &,std::_Tree_node<std::pair<__int64 const,std::shared_ptr<Broker::TimeEvent>>,void *> *)
0x180005c88  mov     rdi, [rbx+30h]
0x180005c8c  mov     r14, rbx
0x180005c8f  mov     rbx, [rbx]
0x180005c92  test    rdi, rdi
0x180005c95  jz      short loc_180005CA6
0x180005c97  mov     eax, 0FFFFFFFFh
0x180005c9c  lock xadd [rdi+8], eax
0x180005ca1  cmp     eax, 1
0x180005ca4  jz      short loc_180005CD3
0x180005ca6  mov     edx, 38h ; '8'; unsigned __int64
0x180005cab  mov     rcx, r14; void *
0x180005cae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180005cb3  cmp     byte ptr [rbx+19h], 0
0x180005cb7  jz      short loc_180005C79
0x180005cb9  mov     r14, [rsp+28h+arg_8]
0x180005cbe  mov     rdi, [rsp+28h+arg_0]
0x180005cc3  mov     rbx, [rsp+28h+arg_10]
0x180005cc8  mov     rbp, [rsp+28h+arg_18]
0x180005ccd  add     rsp, 20h
0x180005cd1  pop     rsi
0x180005cd2  retn
0x180005cd3  mov     rax, [rdi]
0x180005cd6  mov     rcx, rdi
0x180005cd9  mov     rax, [rax]
0x180005cdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ce1  mov     eax, 0FFFFFFFFh
0x180005ce6  lock xadd [rdi+0Ch], eax
0x180005ceb  cmp     eax, 1
0x180005cee  jnz     short loc_180005CA6
0x180005cf0  mov     rax, [rdi]
0x180005cf3  mov     rcx, rdi
0x180005cf6  mov     rax, [rax+8]
0x180005cfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005cff  jmp     short loc_180005CA6
```
