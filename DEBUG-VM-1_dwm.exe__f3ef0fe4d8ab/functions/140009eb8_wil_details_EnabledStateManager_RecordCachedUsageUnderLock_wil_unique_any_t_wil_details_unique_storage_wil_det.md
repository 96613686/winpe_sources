# wil::details::EnabledStateManager::RecordCachedUsageUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x140009eb8`
- end: `0x140009f1b`
- name: `?RecordCachedUsageUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `99`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400041e4`
- `0x14000d0d0`

## callees

- `0x140009eb8`
- `0x14000b564`
- `0x14000c260`

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
0x140009eb8  mov     [rsp+arg_0], rbx
0x140009ebd  mov     [rsp+arg_8], rsi
0x140009ec2  push    rdi; char *
0x140009ec3  sub     rsp, 20h
0x140009ec7  mov     rdi, [rcx+28h]
0x140009ecb  mov     rsi, rcx
0x140009ece  mov     rbx, [rcx+20h]
0x140009ed2  mov     rax, rdi
0x140009ed5  sub     rax, rbx
0x140009ed8  cmp     rax, 10h
0x140009edc  jb      short loc_140009F0B
0x140009ede  cmp     rbx, rdi
0x140009ee1  jz      short loc_140009EF4
0x140009ee3  mov     rdx, [rbx+8]
0x140009ee7  mov     ecx, [rbx]
0x140009ee9  call    wil_details_RecordCachedUsage
0x140009eee  add     rbx, 10h
0x140009ef2  jmp     short loc_140009EDE
0x140009ef4  mov     rax, [rsi+20h]
0x140009ef8  xor     r8d, r8d; unsigned int
0x140009efb  mov     edx, 0FEh; unsigned int
0x140009f00  mov     [rsi+28h], rax
0x140009f04  xor     ecx, ecx; this
0x140009f06  call    ?WilApi_RecordFeatureUsage@details@wil@@YAXIIIPEBD@Z; wil::details::WilApi_RecordFeatureUsage(uint,uint,uint,char const *)
0x140009f0b  mov     rbx, [rsp+28h+arg_0]
0x140009f10  mov     rsi, [rsp+28h+arg_8]
0x140009f15  add     rsp, 20h
0x140009f19  pop     rdi
0x140009f1a  retn
```
