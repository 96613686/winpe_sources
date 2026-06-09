# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180012a7c`
- end: `0x180012adf`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000d31c`

## callees

- `0x180012a7c`
- `0x180013f14`
- `0x180014ba0`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  __int64 v4; // rdi
  __int64 v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(_QWORD *)(a1 + 40);
  v6 = *(_QWORD *)(a1 + 32);
  if ( (unsigned __int64)(v4 - v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*(_DWORD *)v6, *(_QWORD *)(v6 + 8));
      v6 += 16;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x180012a7c  mov     [rsp+arg_0], rbx
0x180012a81  mov     [rsp+arg_8], rsi
0x180012a86  push    rdi; char *
0x180012a87  sub     rsp, 20h
0x180012a8b  mov     rdi, [rcx+28h]
0x180012a8f  mov     rsi, rcx
0x180012a92  mov     rbx, [rcx+20h]
0x180012a96  mov     rax, rdi
0x180012a99  sub     rax, rbx
0x180012a9c  cmp     rax, 10h
0x180012aa0  jb      short loc_180012ACF
0x180012aa2  cmp     rbx, rdi
0x180012aa5  jz      short loc_180012AB8
0x180012aa7  mov     rdx, [rbx+8]
0x180012aab  mov     ecx, [rbx]
0x180012aad  call    wil_details_RecordCachedUsage
0x180012ab2  add     rbx, 10h
0x180012ab6  jmp     short loc_180012AA2
0x180012ab8  mov     rax, [rsi+20h]
0x180012abc  xor     r8d, r8d; unsigned int
0x180012abf  mov     edx, 0FEh; unsigned int
0x180012ac4  mov     [rsi+28h], rax
0x180012ac8  xor     ecx, ecx; this
0x180012aca  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x180012acf  mov     rbx, [rsp+28h+arg_0]
0x180012ad4  mov     rsi, [rsp+28h+arg_8]
0x180012ad9  add     rsp, 20h
0x180012add  pop     rdi
0x180012ade  retn
```
