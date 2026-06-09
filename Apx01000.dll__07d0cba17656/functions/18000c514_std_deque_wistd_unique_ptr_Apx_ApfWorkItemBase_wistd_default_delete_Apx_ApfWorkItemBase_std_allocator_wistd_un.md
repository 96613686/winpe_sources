# std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>,std::allocator<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>>::~deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>,std::allocator<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>>(void)

- ea: `0x18000c514`
- end: `0x18000c61f`
- name: `??1?$deque@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@V?$allocator@V?$unique_ptr@VApfWorkItemBase@Apx@@U?$default_delete@VApfWorkItemBase@Apx@@@wistd@@@wistd@@@std@@@std@@QEAA@XZ`
- size: `267`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18000c690`

## callees

- `0x180002100`
- `0x18000c514`
- `0x18002a010`

## pseudocode

```c
void __fastcall std::deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>::~deque<wistd::unique_ptr<Apx::ApfWorkItemBase,wistd::default_delete<Apx::ApfWorkItemBase>>>(
        __int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // r8
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v7; // rdi
  void *v8; // rcx
  __int64 v9; // rcx
  const struct std::nothrow_t *v10; // rdx
  void *v11; // rax
  void *v12; // rcx

  while ( 1 )
  {
    v2 = *(_QWORD *)(a1 + 32);
    if ( !v2 )
      break;
    v3 = ((_DWORD)v2 - 1 + *(_DWORD *)(a1 + 24)) & 1;
    v4 = *(_QWORD *)(*(_QWORD *)(a1 + 8)
                   + 8 * ((*(_QWORD *)(a1 + 16) - 1LL) & ((unsigned __int64)(v2 - 1 + *(_QWORD *)(a1 + 24)) >> 1)));
    v5 = *(_QWORD *)(v4 + 8 * v3);
    *(_QWORD *)(v4 + 8 * v3) = 0;
    if ( v5 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 8LL))(v5, 1);
    if ( (*(_QWORD *)(a1 + 32))-- == 1 )
      *(_QWORD *)(a1 + 24) = 0;
  }
  if ( *(_QWORD *)(a1 + 8) )
  {
    v7 = *(_QWORD *)(a1 + 16);
    while ( v7 > 0 )
    {
      --v7;
      v8 = *(void **)(*(_QWORD *)(a1 + 8) + 8 * v7);
      if ( v8 )
        operator delete(v8, (const struct std::nothrow_t *)0x10);
    }
    v9 = *(_QWORD *)(a1 + 8);
    v10 = (const struct std::nothrow_t *)(8LL * *(_QWORD *)(a1 + 16));
    if ( (unsigned __int64)v10 < 0x1000 )
    {
      v11 = *(void **)(a1 + 8);
    }
    else
    {
      v11 = *(void **)(v9 - 8);
      if ( (unsigned __int64)(v9 - (_QWORD)v11 - 8) > 0x1F )
        __fastfail(5u);
      v10 = (const struct std::nothrow_t *)((char *)v10 + 39);
    }
    operator delete(v11, v10);
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  v12 = *(void **)a1;
  *(_QWORD *)a1 = 0;
  operator delete(v12, (const struct std::nothrow_t *)0x10);
}

```

## disassembly

```asm
0x18000c514  mov     [rsp+arg_8], rbx
0x18000c519  push    rdi
0x18000c51a  sub     rsp, 20h
0x18000c51e  mov     rbx, rcx
0x18000c521  mov     rcx, [rbx+20h]
0x18000c525  test    rcx, rcx
0x18000c528  jz      short loc_18000C583
0x18000c52a  mov     r8, [rbx+18h]
0x18000c52e  dec     rcx
0x18000c531  mov     rax, [rbx+10h]
0x18000c535  add     r8, rcx
0x18000c538  dec     rax
0x18000c53b  mov     rdx, r8
0x18000c53e  shr     rdx, 1
0x18000c541  and     r8d, 1
0x18000c545  and     rdx, rax
0x18000c548  mov     rax, [rbx+8]
0x18000c54c  mov     rdx, [rax+rdx*8]
0x18000c550  mov     rcx, [rdx+r8*8]
0x18000c554  mov     qword ptr [rdx+r8*8], 0
0x18000c55c  test    rcx, rcx
0x18000c55f  jz      short loc_18000C572
0x18000c561  mov     rax, [rcx]
0x18000c564  mov     edx, 1
0x18000c569  mov     rax, [rax+8]
0x18000c56d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c572  sub     qword ptr [rbx+20h], 1
0x18000c577  jnz     short loc_18000C521
0x18000c579  mov     qword ptr [rbx+18h], 0
0x18000c581  jmp     short loc_18000C521
0x18000c583  cmp     qword ptr [rbx+8], 0
0x18000c588  jz      short loc_18000C601
0x18000c58a  mov     rdi, [rbx+10h]
0x18000c58e  jmp     short loc_18000C5AA
0x18000c590  mov     rax, [rbx+8]
0x18000c594  dec     rdi
0x18000c597  mov     rcx, [rax+rdi*8]; void *
0x18000c59b  test    rcx, rcx
0x18000c59e  jz      short loc_18000C5AA
0x18000c5a0  mov     edx, 10h; struct std::nothrow_t *
0x18000c5a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c5aa  test    rdi, rdi
0x18000c5ad  jg      short loc_18000C590
0x18000c5af  mov     rax, [rbx+10h]
0x18000c5b3  mov     rcx, [rbx+8]
0x18000c5b7  lea     rdx, ds:0[rax*8]; struct std::nothrow_t *
0x18000c5bf  cmp     rdx, 1000h
0x18000c5c6  jb      short loc_18000C5E6
0x18000c5c8  mov     rax, [rcx-8]
0x18000c5cc  sub     rcx, rax
0x18000c5cf  sub     rcx, 8
0x18000c5d3  cmp     rcx, 1Fh
0x18000c5d7  ja      short loc_18000C5DF
0x18000c5d9  add     rdx, 27h ; '''
0x18000c5dd  jmp     short loc_18000C5E9
0x18000c5df  mov     ecx, 5
0x18000c5e4  int     29h; Win8: RtlFailFast(ecx)
0x18000c5e6  mov     rax, rcx
0x18000c5e9  mov     rcx, rax; void *
0x18000c5ec  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000c5f1  mov     qword ptr [rbx+8], 0
0x18000c5f9  mov     qword ptr [rbx+10h], 0
0x18000c601  mov     rcx, [rbx]; void *
0x18000c604  mov     edx, 10h; struct std::nothrow_t *
0x18000c609  mov     qword ptr [rbx], 0
0x18000c610  mov     rbx, [rsp+28h+arg_8]
0x18000c615  add     rsp, 20h
0x18000c619  pop     rdi
0x18000c61a  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
