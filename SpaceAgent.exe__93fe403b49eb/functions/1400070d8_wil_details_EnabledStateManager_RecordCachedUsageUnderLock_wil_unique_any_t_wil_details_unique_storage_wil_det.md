# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x1400070d8`
- end: `0x14000713b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: `void __fastcall(__int64, __int64, __int64, unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006cfc`
- `0x14000a120`

## callees

- `0x1400070d8`
- `0x140008fd4`
- `0x140009d10`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::RecordCachedUsageUnderLock(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        unsigned int a4)
{
  unsigned int *v4; // rdi
  unsigned int *v6; // rbx
  const char *v7; // [rsp+20h] [rbp-8h]

  v4 = *(unsigned int **)(a1 + 40);
  v6 = *(unsigned int **)(a1 + 32);
  if ( (unsigned __int64)((char *)v4 - (char *)v6) >= 0x10 )
  {
    while ( v6 != v4 )
    {
      wil_details_RecordCachedUsage(*v6, *((_QWORD *)v6 + 1));
      v6 += 4;
    }
    *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32);
    wil::details::WilApi_RecordFeatureUsage(0, 0xFEu, 0, a4, v7);
  }
}

```

## disassembly

```asm
0x1400070d8  mov     [rsp+arg_0], rbx
0x1400070dd  mov     [rsp+arg_8], rsi
0x1400070e2  push    rdi; char *
0x1400070e3  sub     rsp, 20h
0x1400070e7  mov     rdi, [rcx+28h]
0x1400070eb  mov     rsi, rcx
0x1400070ee  mov     rbx, [rcx+20h]
0x1400070f2  mov     rax, rdi
0x1400070f5  sub     rax, rbx
0x1400070f8  cmp     rax, 10h
0x1400070fc  jb      short loc_14000712B
0x1400070fe  cmp     rbx, rdi
0x140007101  jz      short loc_140007114
0x140007103  mov     rdx, [rbx+8]
0x140007107  mov     ecx, [rbx]
0x140007109  call    wil_details_RecordCachedUsage
0x14000710e  add     rbx, 10h
0x140007112  jmp     short loc_1400070FE
0x140007114  mov     rax, [rsi+20h]
0x140007118  xor     r8d, r8d; unsigned int
0x14000711b  mov     edx, 0FEh; unsigned int
0x140007120  mov     [rsi+28h], rax
0x140007124  xor     ecx, ecx; this
0x140007126  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14000712b  mov     rbx, [rsp+28h+arg_0]
0x140007130  mov     rsi, [rsp+28h+arg_8]
0x140007135  add     rsp, 20h
0x140007139  pop     rdi
0x14000713a  retn
```
