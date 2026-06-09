# TimeUpdate::GetSettings(void)

- ea: `0x180006ec4`
- end: `0x180006f17`
- name: `?GetSettings@TimeUpdate@@AEAA?AV?$shared_ptr@VSettings@@@std@@XZ`
- size: `83`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config, installer_update`

## callers

- `0x180006350`
- `0x1800064e4`
- `0x180006598`
- `0x1800084c4`
- `0x1800110f3`

## callees

- `0x180004e68`
- `0x180005840`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ee0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180006ee0`

## pseudocode

```c
__int64 __fastcall TimeUpdate::GetSettings(__int64 a1, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = (struct _RTL_CRITICAL_SECTION *)(a1 + 16);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 16));
  v5 = v2;
  std::shared_ptr<Settings>::shared_ptr<Settings>(a2);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v5);
  return a2;
}

```

## disassembly

```asm
0x180006ec4  mov     [rsp+arg_8], rbx
0x180006ec9  mov     [rsp+arg_10], rsi
0x180006ece  push    rdi
0x180006ecf  sub     rsp, 20h
0x180006ed3  lea     rbx, [rcx+10h]
0x180006ed7  mov     rdi, rcx
0x180006eda  mov     rcx, rbx; lpCriticalSection
0x180006edd  mov     rsi, rdx
0x180006ee0  call    cs:__imp_EnterCriticalSection
0x180006ee6  lea     rdx, [rdi+0E0h]
0x180006eed  mov     [rsp+28h+arg_0], rbx
0x180006ef2  mov     rcx, rsi
0x180006ef5  call    ??0?$shared_ptr@VSettings@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Settings>::shared_ptr<Settings>(std::shared_ptr<Settings> const &)
0x180006efa  lea     rcx, [rsp+28h+arg_0]
0x180006eff  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180006f04  mov     rbx, [rsp+28h+arg_8]
0x180006f09  mov     rax, rsi
0x180006f0c  mov     rsi, [rsp+28h+arg_10]
0x180006f11  add     rsp, 20h
0x180006f15  pop     rdi
0x180006f16  retn
```
