# CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::~TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>(void)

- ea: `0x180010ee0`
- end: `0x180010efb`
- name: `??1?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@QEAA@XZ`
- size: `27`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010e30`
- `0x180010e90`
- `0x18002a5e6`

## callees

- `0x1800114f8`
- `0x1800158b4`

## pseudocode

```c
__int64 __fastcall CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::~TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>(
        __int64 a1)
{
  CodeIntegrity::Management::detail::TransactionHandle<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>,CodeIntegrity::Management::detail::DeleteTag>::cleanup();
  return wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void SIPolicyPmCloseTransactionHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(a1);
}

```

## disassembly

```asm
0x180010ee0  push    rbx
0x180010ee2  sub     rsp, 20h
0x180010ee6  mov     rbx, rcx
0x180010ee9  call    ?cleanup@?$TransactionHandle@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@UDeleteTag@detail@Management@CodeIntegrity@@@detail@Management@CodeIntegrity@@AEAAXXZ
0x180010eee  mov     rcx, rbx
0x180010ef1  add     rsp, 20h
0x180010ef5  pop     rbx
0x180010ef6  jmp     ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?SIPolicyPmCloseTransactionHandle@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
```
