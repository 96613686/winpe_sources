# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::GetPendingRequestCounter(void)

- ea: `0x140017bd8`
- end: `0x140017c05`
- name: `?GetPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEBAHXZ`
- size: `45`
- prototype: `__int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14002f250`

## callees

- `0x140017b78`
- `0x140017ce8`

## pseudocode

```c
__int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::GetPendingRequestCounter(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *this)
{
  Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *v1; // rbx
  _BYTE v3[24]; // [rsp+20h] [rbp-18h] BYREF

  v1 = this;
  wil::acquire_kspin_lock(v3, (char *)this + 24);
  LODWORD(v1) = *((_DWORD *)v1 + 8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v3);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x140017bd8  push    rbx
0x140017bda  sub     rsp, 30h
0x140017bde  mov     rbx, rcx
0x140017be1  lea     rdx, [rcx+18h]
0x140017be5  lea     rcx, [rsp+38h+var_18]
0x140017bea  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x140017bef  mov     ebx, [rbx+20h]
0x140017bf2  lea     rcx, [rsp+38h+var_18]
0x140017bf7  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x140017bfc  mov     eax, ebx
0x140017bfe  add     rsp, 30h
0x140017c02  pop     rbx
0x140017c03  retn
```
