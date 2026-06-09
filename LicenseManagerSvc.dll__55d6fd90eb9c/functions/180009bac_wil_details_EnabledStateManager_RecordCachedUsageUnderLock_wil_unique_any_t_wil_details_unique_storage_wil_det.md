# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180009bac`
- end: `0x180009c10`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180009674`
- `0x1800096c8`

## callees

- `0x180009bac`
- `0x18000b0d0`
- `0x18000bdf0`

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
0x180009bac  mov     [rsp+arg_0], rbx
0x180009bb1  mov     [rsp+arg_8], rsi
0x180009bb6  push    rdi; char *
0x180009bb7  sub     rsp, 20h
0x180009bbb  mov     rsi, rcx
0x180009bbe  mov     rbx, [rcx+20h]
0x180009bc2  mov     rdi, [rcx+28h]
0x180009bc6  mov     rax, rdi
0x180009bc9  sub     rax, rbx
0x180009bcc  cmp     rax, 10h
0x180009bd0  jb      short loc_180009C00
0x180009bd2  cmp     rbx, rdi
0x180009bd5  jz      short loc_180009BE8
0x180009bd7  mov     rdx, [rbx+8]
0x180009bdb  mov     ecx, [rbx]
0x180009bdd  call    wil_details_RecordCachedUsage
0x180009be2  add     rbx, 10h
0x180009be6  jmp     short loc_180009BD2
0x180009be8  mov     rax, [rsi+20h]
0x180009bec  mov     [rsi+28h], rax
0x180009bf0  xor     r8d, r8d; unsigned int
0x180009bf3  mov     edx, 0FEh; unsigned int
0x180009bf8  xor     ecx, ecx; this
0x180009bfa  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180009bff  nop
0x180009c00  mov     rbx, [rsp+28h+arg_0]
0x180009c05  mov     rsi, [rsp+28h+arg_8]
0x180009c0a  add     rsp, 20h
0x180009c0e  pop     rdi
0x180009c0f  retn
```
