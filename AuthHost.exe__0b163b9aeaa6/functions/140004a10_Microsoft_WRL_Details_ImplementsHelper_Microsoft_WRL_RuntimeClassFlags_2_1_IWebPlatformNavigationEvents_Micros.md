# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::CanCastTo(_GUID const &,void * *,bool *)

- ea: `0x140004a10`
- end: `0x140004ab7`
- name: `?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00UIWebPlatformNavigationEvents@@U?$ChainInterfaces@UIHttpSecurity@@UIWindowForBindingUI@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@UIServiceProvider@@UIWebPlatformSecurityManager@@UIWebPlatformPermanentSecurityManager@@UIWebPlatformVisualViewportEvents@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z`
- size: `167`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x140005780`

## callees

- `0x140004a10`
- `0x140005590`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<2>,1,IWebPlatformNavigationEvents,Microsoft::WRL::ChainInterfaces<IHttpSecurity,IWindowForBindingUI,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,IServiceProvider,IWebPlatformSecurityManager,IWebPlatformPermanentSecurityManager,IWebPlatformVisualViewportEvents>::CanCastTo(
        __int64 a1,
        const struct _GUID *a2)
{
  const struct _GUID *v2; // rcx
  _QWORD *v3; // r8
  __int64 v4; // r10
  const struct _GUID *v5; // rcx
  const struct _GUID *v6; // rcx
  const struct _GUID *v8; // rcx
  const struct _GUID *v9; // rcx
  const struct _GUID *v10; // rcx
  _QWORD *v11; // r8
  __int64 v12; // r10

  if ( (unsigned int)InlineIsEqualGUID(a2, &GUID_7fe59da0_016a_4344_832c_b7f863b5f924)
    || (unsigned int)InlineIsEqualGUID(v2, &GUID_79eac9d7_bafa_11ce_8c82_00aa004ba90b)
    || (unsigned int)InlineIsEqualGUID(v5, &GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b)
    || (unsigned int)InlineIsEqualGUID(v6, &GUID_6d5140c1_7436_11ce_8034_00aa006009fa)
    || (unsigned int)InlineIsEqualGUID(v8, &GUID_49d33aad_f985_4b70_97a0_28eceb6523bf)
    || (unsigned int)InlineIsEqualGUID(v9, &GUID_e4dfc97c_9bef_4803_8ce1_0f980df7c847) )
  {
    *v3 = v4;
    return 0;
  }
  if ( (unsigned int)InlineIsEqualGUID(v10, &GUID_5396d4ce_6bac_447a_9271_b233b6d4bc25) )
  {
    *v11 = v12 + 8;
    return 0;
  }
  return 2147500034LL;
}

```

## disassembly

```asm
0x140004a10  sub     rsp, 28h
0x140004a14  mov     r9, rdx
0x140004a17  mov     r10, rcx
0x140004a1a  mov     rcx, r9; struct _GUID *
0x140004a1d  lea     rdx, _GUID_7fe59da0_016a_4344_832c_b7f863b5f924; struct _GUID *
0x140004a24  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a29  test    eax, eax
0x140004a2b  jnz     short loc_140004A51
0x140004a2d  lea     rdx, _GUID_79eac9d7_bafa_11ce_8c82_00aa004ba90b; struct _GUID *
0x140004a34  add     r10, 8
0x140004a38  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a3d  test    eax, eax
0x140004a3f  jnz     short loc_140004A51
0x140004a41  lea     rdx, _GUID_79eac9d5_bafa_11ce_8c82_00aa004ba90b; struct _GUID *
0x140004a48  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a4d  test    eax, eax
0x140004a4f  jz      short loc_140004A58
0x140004a51  mov     [r8], r10
0x140004a54  xor     eax, eax
0x140004a56  jmp     short loc_140004AB2
0x140004a58  lea     rdx, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; struct _GUID *
0x140004a5f  add     r10, 8
0x140004a63  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a68  test    eax, eax
0x140004a6a  jnz     short loc_140004A51
0x140004a6c  lea     rdx, _GUID_49d33aad_f985_4b70_97a0_28eceb6523bf; struct _GUID *
0x140004a73  add     r10, 8
0x140004a77  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a7c  test    eax, eax
0x140004a7e  jnz     short loc_140004A51
0x140004a80  lea     rdx, _GUID_e4dfc97c_9bef_4803_8ce1_0f980df7c847; struct _GUID *
0x140004a87  add     r10, 8
0x140004a8b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004a90  test    eax, eax
0x140004a92  jnz     short loc_140004A51
0x140004a94  lea     rdx, _GUID_5396d4ce_6bac_447a_9271_b233b6d4bc25; struct _GUID *
0x140004a9b  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x140004aa0  test    eax, eax
0x140004aa2  jz      short loc_140004AAD
0x140004aa4  lea     rax, [r10+8]
0x140004aa8  mov     [r8], rax
0x140004aab  jmp     short loc_140004A54
0x140004aad  mov     eax, 80004002h
0x140004ab2  add     rsp, 28h
0x140004ab6  retn
```
