# Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(void)

- ea: `0x140017ba4`
- end: `0x140017bcf`
- name: `?DecrementPendingRequestCounter@ScoReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@AEAAXXZ`
- size: `43`
- prototype: `void __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140017c70`
- `0x14002f2f4`

## callees

- `0x140017b78`
- `0x140017ce8`

## pseudocode

```c
void __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader::DecrementPendingRequestCounter(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::ScoReader *this)
{
  _BYTE v2[24]; // [rsp+20h] [rbp-18h] BYREF

  wil::acquire_kspin_lock(v2, (char *)this + 24);
  --*((_DWORD *)this + 8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&public: static void wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(v2);
}

```

## disassembly

```asm
0x140017ba4  push    rbx
0x140017ba6  sub     rsp, 30h
0x140017baa  mov     rbx, rcx
0x140017bad  lea     rdx, [rcx+18h]
0x140017bb1  lea     rcx, [rsp+38h+var_18]
0x140017bb6  call    ?acquire_kspin_lock@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@@1@PEA_K@Z; wil::acquire_kspin_lock(unsigned __int64 *)
0x140017bbb  dec     dword ptr [rbx+20h]
0x140017bbe  lea     rcx, [rsp+38h+var_18]
0x140017bc3  call    ??1?$unique_storage@U?$resource_policy@PEA_K$$A6AXAEBUkspin_lock_saved_irql@details@wil@@@Z$1?Release@123@SAX0@ZU?$integral_constant@_K$01@wistd@@U123@PEA_K$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned __int64 *,void (wil::details::kspin_lock_saved_irql const &),&wil::details::kspin_lock_saved_irql::Release(wil::details::kspin_lock_saved_irql const &),wistd::integral_constant<unsigned __int64,2>,wil::details::kspin_lock_saved_irql,unsigned __int64 *,0,std::nullptr_t>>(void)
0x140017bc8  add     rsp, 30h
0x140017bcc  pop     rbx
0x140017bcd  retn
```
