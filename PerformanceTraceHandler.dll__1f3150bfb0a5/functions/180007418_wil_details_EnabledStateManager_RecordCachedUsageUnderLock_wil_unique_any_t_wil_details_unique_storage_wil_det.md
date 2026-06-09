# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180007418`
- end: `0x18000747c`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007000`
- `0x18000c5fc`

## callees

- `0x180007418`
- `0x180009044`
- `0x18000a440`

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
0x180007418  mov     [rsp+arg_0], rbx
0x18000741d  mov     [rsp+arg_8], rsi
0x180007422  push    rdi; char *
0x180007423  sub     rsp, 20h
0x180007427  mov     rsi, rcx
0x18000742a  mov     rbx, [rcx+20h]
0x18000742e  mov     rdi, [rcx+28h]
0x180007432  mov     rax, rdi
0x180007435  sub     rax, rbx
0x180007438  cmp     rax, 10h
0x18000743c  jb      short loc_18000746C
0x18000743e  cmp     rbx, rdi
0x180007441  jz      short loc_180007454
0x180007443  mov     rdx, [rbx+8]
0x180007447  mov     ecx, [rbx]
0x180007449  call    wil_details_RecordCachedUsage
0x18000744e  add     rbx, 10h
0x180007452  jmp     short loc_18000743E
0x180007454  mov     rax, [rsi+20h]
0x180007458  mov     [rsi+28h], rax
0x18000745c  xor     r8d, r8d; unsigned int
0x18000745f  mov     edx, 0FEh; unsigned int
0x180007464  xor     ecx, ecx; this
0x180007466  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000746b  nop
0x18000746c  mov     rbx, [rsp+28h+arg_0]
0x180007471  mov     rsi, [rsp+28h+arg_8]
0x180007476  add     rsp, 20h
0x18000747a  pop     rdi
0x18000747b  retn
```
