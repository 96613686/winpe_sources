# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000802c`
- end: `0x180008090`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007ac0`
- `0x180007bec`

## callees

- `0x18000802c`
- `0x18000a570`
- `0x18000bc00`

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
0x18000802c  mov     [rsp+arg_0], rbx
0x180008031  mov     [rsp+arg_8], rsi
0x180008036  push    rdi; char *
0x180008037  sub     rsp, 20h
0x18000803b  mov     rsi, rcx
0x18000803e  mov     rbx, [rcx+20h]
0x180008042  mov     rdi, [rcx+28h]
0x180008046  mov     rax, rdi
0x180008049  sub     rax, rbx
0x18000804c  cmp     rax, 10h
0x180008050  jb      short loc_180008080
0x180008052  cmp     rbx, rdi
0x180008055  jz      short loc_180008068
0x180008057  mov     rdx, [rbx+8]
0x18000805b  mov     ecx, [rbx]
0x18000805d  call    wil_details_RecordCachedUsage
0x180008062  add     rbx, 10h
0x180008066  jmp     short loc_180008052
0x180008068  mov     rax, [rsi+20h]
0x18000806c  mov     [rsi+28h], rax
0x180008070  xor     r8d, r8d; unsigned int
0x180008073  mov     edx, 0FEh; unsigned int
0x180008078  xor     ecx, ecx; this
0x18000807a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000807f  nop
0x180008080  mov     rbx, [rsp+28h+arg_0]
0x180008085  mov     rsi, [rsp+28h+arg_8]
0x18000808a  add     rsp, 20h
0x18000808e  pop     rdi
0x18000808f  retn
```
