# WalletEncrypter::Cleanup(void)

- ea: `0x18001b49c`
- end: `0x18001b4d2`
- name: `?Cleanup@WalletEncrypter@@AEAAXXZ`
- size: `54`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800110f0`
- `0x18001b41c`

## callees

- `0x18001b2e0`
- `0x18001b310`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001b4bf`

## pseudocode

```c
void __fastcall WalletEncrypter::Cleanup(void **this)
{
  void *v2; // rcx

  tlx::replace<tlx::handle_traits<void *,long (*)(void * const &),&long wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>>(this);
  tlx::replace<tlx::handle_traits<void *,long (*)(void *),&long BCryptDestroyKey(void *),0>>(this + 3);
  v2 = this[2];
  this[2] = 0;
  CoTaskMemFree(v2);
  *((_DWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x18001b49c  push    rbx
0x18001b49e  sub     rsp, 20h
0x18001b4a2  mov     rbx, rcx
0x18001b4a5  call    ??$replace@U?$handle_traits@PEAXP6AJAEBQEAX@Z$1?_WpBCryptCloseAlgorithmProvider@detail@wp@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJAEBQEAX@Z$1?_WpBCryptCloseAlgorithmProvider@detail@wp@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void * const &),&wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void * const &),&wp::detail::_WpBCryptCloseAlgorithmProvider(void * const &),0>> &)
0x18001b4aa  lea     rcx, [rbx+18h]
0x18001b4ae  call    ??$replace@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@U?$handle_traits@PEAXP6AJPEAX@Z$1?BCryptDestroyKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>>(tlx::unique_any<tlx::handle_traits<void *,long (*)(void *),&BCryptDestroyKey(void *),0>> &)
0x18001b4b3  mov     rcx, [rbx+10h]; pv
0x18001b4b7  mov     qword ptr [rbx+10h], 0
0x18001b4bf  call    cs:__imp_CoTaskMemFree
0x18001b4c5  mov     dword ptr [rbx+8], 0
0x18001b4cc  add     rsp, 20h
0x18001b4d0  pop     rbx
0x18001b4d1  retn
```
