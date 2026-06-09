# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000cc00`
- end: `0x18000cc64`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180007658`
- `0x180014c1c`

## callees

- `0x18000cc00`
- `0x18000d660`
- `0x18000dc3c`

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
0x18000cc00  mov     [rsp+arg_0], rbx
0x18000cc05  mov     [rsp+arg_8], rsi
0x18000cc0a  push    rdi; char *
0x18000cc0b  sub     rsp, 20h
0x18000cc0f  mov     rsi, rcx
0x18000cc12  mov     rbx, [rcx+20h]
0x18000cc16  mov     rdi, [rcx+28h]
0x18000cc1a  mov     rax, rdi
0x18000cc1d  sub     rax, rbx
0x18000cc20  cmp     rax, 10h
0x18000cc24  jb      short loc_18000CC54
0x18000cc26  cmp     rbx, rdi
0x18000cc29  jz      short loc_18000CC3C
0x18000cc2b  mov     rdx, [rbx+8]
0x18000cc2f  mov     ecx, [rbx]
0x18000cc31  call    wil_details_RecordCachedUsage
0x18000cc36  add     rbx, 10h
0x18000cc3a  jmp     short loc_18000CC26
0x18000cc3c  mov     rax, [rsi+20h]
0x18000cc40  mov     [rsi+28h], rax
0x18000cc44  xor     r8d, r8d; unsigned int
0x18000cc47  mov     edx, 0FEh; unsigned int
0x18000cc4c  xor     ecx, ecx; this
0x18000cc4e  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x18000cc53  nop
0x18000cc54  mov     rbx, [rsp+28h+arg_0]
0x18000cc59  mov     rsi, [rsp+28h+arg_8]
0x18000cc5e  add     rsp, 20h
0x18000cc62  pop     rdi
0x18000cc63  retn
```
