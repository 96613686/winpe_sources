# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180010dd4`
- end: `0x180010e38`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009c00`
- `0x18000b6cc`

## callees

- `0x1800097cc`
- `0x18000c8e8`
- `0x180010dd4`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int *v5; // rbx
  unsigned int *v6; // rdi
  const char *v7; // [rsp+20h] [rbp-8h]

  v5 = *(unsigned int **)(a1 + 32);
  v6 = *(unsigned int **)(a1 + 40);
  if ( (unsigned __int64)((char *)v6 - (char *)v5) >= 0x10 )
  {
    while ( v5 != v6 )
    {
      wil_details_RecordCachedUsage(*v5, *((_QWORD *)v5 + 1));
      v5 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x180010dd4  mov     [rsp+arg_0], rbx
0x180010dd9  mov     [rsp+arg_8], rsi
0x180010dde  push    rdi; char *
0x180010ddf  sub     rsp, 20h
0x180010de3  mov     rsi, rcx
0x180010de6  mov     rbx, [rcx+20h]
0x180010dea  mov     rdi, [rcx+28h]
0x180010dee  mov     rax, rdi
0x180010df1  sub     rax, rbx
0x180010df4  cmp     rax, 10h
0x180010df8  jb      short loc_180010E28
0x180010dfa  cmp     rbx, rdi
0x180010dfd  jz      short loc_180010E10
0x180010dff  mov     rdx, [rbx+8]
0x180010e03  mov     ecx, [rbx]
0x180010e05  call    wil_details_RecordCachedUsage
0x180010e0a  add     rbx, 10h
0x180010e0e  jmp     short loc_180010DFA
0x180010e10  mov     rax, [rsi+20h]
0x180010e14  mov     [rsi+28h], rax
0x180010e18  xor     r8d, r8d; unsigned int
0x180010e1b  mov     edx, 0FEh; unsigned int
0x180010e20  xor     ecx, ecx; this
0x180010e22  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180010e27  nop
0x180010e28  mov     rbx, [rsp+28h+arg_0]
0x180010e2d  mov     rsi, [rsp+28h+arg_8]
0x180010e32  add     rsp, 20h
0x180010e36  pop     rdi
0x180010e37  retn
```
