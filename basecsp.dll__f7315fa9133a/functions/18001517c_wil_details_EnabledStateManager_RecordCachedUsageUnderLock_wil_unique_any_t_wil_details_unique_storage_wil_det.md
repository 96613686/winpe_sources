# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18001517c`
- end: `0x1800151e0`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180014b7c`
- `0x180014c74`

## callees

- `0x18001517c`
- `0x1800179b8`
- `0x180019fe4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v5; // rbx
  __int64 v6; // rdi
  const char *v7; // [rsp+20h] [rbp-8h]

  v5 = *(_QWORD *)(a1 + 32);
  v6 = *(_QWORD *)(a1 + 40);
  if ( (unsigned __int64)(v6 - v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v5, *(_QWORD *)(v5 + 8));
      v5 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x18001517c  mov     [rsp+arg_0], rbx
0x180015181  mov     [rsp+arg_8], rsi
0x180015186  push    rdi; char *
0x180015187  sub     rsp, 20h
0x18001518b  mov     rsi, rcx
0x18001518e  mov     rbx, [rcx+20h]
0x180015192  mov     rdi, [rcx+28h]
0x180015196  mov     rax, rdi
0x180015199  sub     rax, rbx
0x18001519c  cmp     rax, 10h
0x1800151a0  jb      short loc_1800151D0
0x1800151a2  cmp     rbx, rdi
0x1800151a5  jz      short loc_1800151B8
0x1800151a7  mov     rdx, [rbx+8]
0x1800151ab  mov     ecx, [rbx]
0x1800151ad  call    wil_details_RecordCachedUsage
0x1800151b2  add     rbx, 10h
0x1800151b6  jmp     short loc_1800151A2
0x1800151b8  mov     rax, [rsi+20h]
0x1800151bc  mov     [rsi+28h], rax
0x1800151c0  xor     r8d, r8d; unsigned int
0x1800151c3  mov     edx, 0FEh; unsigned int
0x1800151c8  xor     ecx, ecx; this
0x1800151ca  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x1800151cf  nop
0x1800151d0  mov     rbx, [rsp+28h+arg_0]
0x1800151d5  mov     rsi, [rsp+28h+arg_8]
0x1800151da  add     rsp, 20h
0x1800151de  pop     rdi
0x1800151df  retn
```
