# std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>,void *>>>(void)

- ea: `0x18002310c`
- end: `0x180023188`
- name: `??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V12@@std@@PEAX@std@@@std@@@std@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x1800239c0`

## callees

- `0x180001894`
- `0x18002310c`
- `0x18002a010`

## pseudocode

```c
void __fastcall std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const,ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>,void *>>>(
        __int64 a1)
{
  __int64 v1; // rbx
  volatile signed __int32 *v3; // rdx
  volatile signed __int32 *v4; // rdx
  void *v5; // rcx

  v1 = *(_QWORD *)(a1 + 8);
  if ( v1 )
  {
    v3 = (volatile signed __int32 *)(*(_QWORD *)(v1 + 40) - 24LL);
    if ( _InterlockedExchangeAdd(v3 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v3 + 8LL))(*(_QWORD *)v3);
    v4 = (volatile signed __int32 *)(*(_QWORD *)(v1 + 32) - 24LL);
    if ( _InterlockedExchangeAdd(v4 + 4, 0xFFFFFFFF) <= 1 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v4 + 8LL))(*(_QWORD *)v4);
  }
  v5 = *(void **)(a1 + 8);
  if ( v5 )
    operator delete(v5);
}

```

## disassembly

```asm
0x18002310c  mov     [rsp+arg_0], rbx
0x180023111  push    rdi
0x180023112  sub     rsp, 20h
0x180023116  mov     rbx, [rcx+8]
0x18002311a  mov     rdi, rcx
0x18002311d  test    rbx, rbx
0x180023120  jz      short loc_18002316A
0x180023122  mov     rdx, [rbx+28h]
0x180023126  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002312a  or      eax, 0FFFFFFFFh
0x18002312d  lock xadd [rdx+10h], eax
0x180023132  sub     eax, 1
0x180023135  jg      short loc_180023146
0x180023137  mov     rcx, [rdx]
0x18002313a  mov     rax, [rcx]
0x18002313d  mov     rax, [rax+8]
0x180023141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023146  mov     rdx, [rbx+20h]
0x18002314a  add     rdx, 0FFFFFFFFFFFFFFE8h
0x18002314e  or      eax, 0FFFFFFFFh
0x180023151  lock xadd [rdx+10h], eax
0x180023156  sub     eax, 1
0x180023159  jg      short loc_18002316A
0x18002315b  mov     rcx, [rdx]
0x18002315e  mov     rax, [rcx]
0x180023161  mov     rax, [rax+8]
0x180023165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002316a  mov     rcx, [rdi+8]; Block
0x18002316e  test    rcx, rcx
0x180023171  jz      short loc_18002317D
0x180023173  mov     edx, 30h ; '0'
0x180023178  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002317d  mov     rbx, [rsp+28h+arg_0]
0x180023182  add     rsp, 20h
0x180023186  pop     rdi
0x180023187  retn
```
