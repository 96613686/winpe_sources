# Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::ReregisterWait(void)

- ea: `0x18002cb00`
- end: `0x18002cb4c`
- name: `?ReregisterWait@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@QEAAXXZ`
- size: `76`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002c230`
- `0x180030420`

## callees

- `0x180010e48`
- `0x180010ec0`
- `0x18002cb00`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002cb30`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18002cb30`

## pseudocode

```c
__int64 __fastcall Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::ReregisterWait(
        __int64 a1)
{
  __int64 v1; // r9
  void *v2; // rdx
  _BYTE v4[24]; // [rsp+20h] [rbp-18h] BYREF

  std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    v4,
    a1 + 88);
  if ( v4[8] )
  {
    v2 = *(void **)(v1 + 80);
    if ( v2 )
      SetThreadpoolWait(*(PTP_WAIT *)(v1 + 8), v2, *(PFILETIME *)(v1 + 192));
  }
  return std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(v4);
}

```

## disassembly

```asm
0x18002cb00  sub     rsp, 38h
0x18002cb04  lea     rdx, [rcx+58h]
0x18002cb08  mov     r9, rcx
0x18002cb0b  lea     rcx, [rsp+38h+var_18]
0x18002cb10  call    ??0?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@Utry_to_lock_t@1@@Z; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &,std::try_to_lock_t)
0x18002cb15  cmp     [rsp+38h+var_10], 0
0x18002cb1a  jz      short loc_18002CB3C
0x18002cb1c  mov     rdx, [r9+50h]; h
0x18002cb20  test    rdx, rdx
0x18002cb23  jz      short loc_18002CB3C
0x18002cb25  mov     r8, [r9+0C0h]; pftTimeout
0x18002cb2c  mov     rcx, [r9+8]; pwa
0x18002cb30  call    cs:__imp_SetThreadpoolWait
0x18002cb37  nop     dword ptr [rax+rax+00h]
0x18002cb3c  lea     rcx, [rsp+38h+var_18]
0x18002cb41  call    ??1?$shared_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@XZ; std::shared_lock<Rdp::Utils::Synchronization::rundown_mutex>::~shared_lock<Rdp::Utils::Synchronization::rundown_mutex>(void)
0x18002cb46  add     rsp, 38h
0x18002cb4a  retn
```
