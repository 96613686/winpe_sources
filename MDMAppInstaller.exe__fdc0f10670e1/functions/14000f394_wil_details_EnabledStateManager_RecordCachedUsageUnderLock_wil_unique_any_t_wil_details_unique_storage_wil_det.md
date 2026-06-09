# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000f394`
- end: `0x14000f3f8`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `100`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000e62c`
- `0x14000edec`

## callees

- `0x14000f394`
- `0x140011478`
- `0x140013a90`

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
0x14000f394  mov     [rsp+arg_0], rbx
0x14000f399  mov     [rsp+arg_8], rsi
0x14000f39e  push    rdi; char *
0x14000f39f  sub     rsp, 20h
0x14000f3a3  mov     rsi, rcx
0x14000f3a6  mov     rbx, [rcx+20h]
0x14000f3aa  mov     rdi, [rcx+28h]
0x14000f3ae  mov     rax, rdi
0x14000f3b1  sub     rax, rbx
0x14000f3b4  cmp     rax, 10h
0x14000f3b8  jb      short loc_14000F3E8
0x14000f3ba  cmp     rbx, rdi
0x14000f3bd  jz      short loc_14000F3D0
0x14000f3bf  mov     rdx, [rbx+8]
0x14000f3c3  mov     ecx, [rbx]
0x14000f3c5  call    wil_details_RecordCachedUsage
0x14000f3ca  add     rbx, 10h
0x14000f3ce  jmp     short loc_14000F3BA
0x14000f3d0  mov     rax, [rsi+20h]
0x14000f3d4  mov     [rsi+28h], rax
0x14000f3d8  xor     r8d, r8d; unsigned int
0x14000f3db  mov     edx, 0FEh; unsigned int
0x14000f3e0  xor     ecx, ecx; this
0x14000f3e2  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14000f3e7  nop
0x14000f3e8  mov     rbx, [rsp+28h+arg_0]
0x14000f3ed  mov     rsi, [rsp+28h+arg_8]
0x14000f3f2  add     rsp, 20h
0x14000f3f6  pop     rdi
0x14000f3f7  retn
```
