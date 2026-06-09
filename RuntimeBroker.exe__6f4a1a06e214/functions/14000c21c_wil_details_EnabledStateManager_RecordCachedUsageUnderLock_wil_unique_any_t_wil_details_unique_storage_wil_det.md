# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x14000c21c`
- end: `0x14000c27f`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140007104`
- `0x140008264`

## callees

- `0x1400076cc`
- `0x14000c21c`
- `0x14000d440`

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
0x14000c21c  mov     [rsp+arg_0], rbx
0x14000c221  mov     [rsp+arg_8], rsi
0x14000c226  push    rdi; char *
0x14000c227  sub     rsp, 20h
0x14000c22b  mov     rdi, [rcx+28h]
0x14000c22f  mov     rsi, rcx
0x14000c232  mov     rbx, [rcx+20h]
0x14000c236  mov     rax, rdi
0x14000c239  sub     rax, rbx
0x14000c23c  cmp     rax, 10h
0x14000c240  jb      short loc_14000C26F
0x14000c242  cmp     rbx, rdi
0x14000c245  jz      short loc_14000C258
0x14000c247  mov     rdx, [rbx+8]
0x14000c24b  mov     ecx, [rbx]
0x14000c24d  call    wil_details_RecordCachedUsage
0x14000c252  add     rbx, 10h
0x14000c256  jmp     short loc_14000C242
0x14000c258  mov     rax, [rsi+20h]
0x14000c25c  xor     r8d, r8d; unsigned int
0x14000c25f  mov     edx, 0FEh; unsigned int
0x14000c264  mov     [rsi+28h], rax
0x14000c268  xor     ecx, ecx; this
0x14000c26a  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x14000c26f  mov     rbx, [rsp+28h+arg_0]
0x14000c274  mov     rsi, [rsp+28h+arg_8]
0x14000c279  add     rsp, 20h
0x14000c27d  pop     rdi
0x14000c27e  retn
```
