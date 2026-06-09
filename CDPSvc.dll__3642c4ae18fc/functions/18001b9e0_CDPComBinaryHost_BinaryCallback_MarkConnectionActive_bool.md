# CDPComBinaryHost::BinaryCallback::MarkConnectionActive(bool)

- ea: `0x18001b9e0`
- end: `0x18001ba5f`
- name: `?MarkConnectionActive@BinaryCallback@CDPComBinaryHost@@QEAAX_N@Z`
- size: `127`
- prototype: `void __fastcall(PVOID pv, bool)`
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b940`
- `0x18002edc0`
- `0x18002eea0`
- `0x18002ef30`

## callees

- `0x18000a52c`
- `0x18001b9e0`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ba4e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001ba4e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ba11`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001ba11`

## pseudocode

```c
void __fastcall CDPComBinaryHost::BinaryCallback::MarkConnectionActive(struct _TP_TIMER **pv, char a2)
{
  struct _TP_TIMER **v3; // rbx
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v5; // rcx
  struct _FILETIME pftDueTime; // [rsp+30h] [rbp+8h] BYREF

  if ( pv[25] )
  {
    v3 = pv + 30;
    if ( !pv[30] )
    {
      ThreadpoolTimer = CreateThreadpoolTimer(CDPComBinaryHost::BinaryCallback::ThreadPoolTimerCallback, pv, 0);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v3,
        ThreadpoolTimer);
    }
    v5 = *v3;
    pftDueTime = (struct _FILETIME)((-(__int64)(a2 != 0) & 0xFFFFFFFF502A9280uLL) - 50000000);
    SetThreadpoolTimer(v5, &pftDueTime, 0, 0);
  }
}

```

## disassembly

```asm
0x18001b9e0  mov     [rsp+arg_8], rbx
0x18001b9e5  push    rdi
0x18001b9e6  sub     rsp, 20h
0x18001b9ea  cmp     qword ptr [rcx+0C8h], 0
0x18001b9f2  mov     dil, dl
0x18001b9f5  jz      short loc_18001BA54
0x18001b9f7  lea     rbx, [rcx+0F0h]
0x18001b9fe  cmp     qword ptr [rbx], 0
0x18001ba02  jnz     short loc_18001BA22
0x18001ba04  mov     rdx, rcx; pv
0x18001ba07  xor     r8d, r8d; pcbe
0x18001ba0a  lea     rcx, ?ThreadPoolTimerCallback@BinaryCallback@CDPComBinaryHost@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001ba11  call    cs:__imp_CreateThreadpoolTimer
0x18001ba17  mov     rdx, rax
0x18001ba1a  mov     rcx, rbx
0x18001ba1d  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x18001ba22  neg     dil
0x18001ba25  lea     rdx, [rsp+28h+pftDueTime]; pftDueTime
0x18001ba2a  mov     rcx, 0FFFFFFFF502A9280h
0x18001ba34  sbb     rax, rax
0x18001ba37  xor     r9d, r9d; msWindowLength
0x18001ba3a  and     rax, rcx
0x18001ba3d  xor     r8d, r8d; msPeriod
0x18001ba40  mov     rcx, [rbx]; pti
0x18001ba43  add     rax, 0FFFFFFFFFD050F80h
0x18001ba49  mov     qword ptr [rsp+28h+pftDueTime.dwLowDateTime], rax
0x18001ba4e  call    cs:__imp_SetThreadpoolTimer
0x18001ba54  mov     rbx, [rsp+28h+arg_8]
0x18001ba59  add     rsp, 20h
0x18001ba5d  pop     rdi
0x18001ba5e  retn
```
