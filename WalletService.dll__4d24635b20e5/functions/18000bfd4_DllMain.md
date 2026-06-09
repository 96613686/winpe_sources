# DllMain

- ea: `0x18000bfd4`
- end: `0x18000c046`
- name: `DllMain`
- size: `114`
- prototype: `BOOL __stdcall(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x180002504`

## callees

- `0x18000ab08`
- `0x18000b8d4`
- `0x18000bfd4`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c03e`
- `api-ms-win-core-libraryloader-l1-2-0!DisableThreadLibraryCalls` at `0x18000c03e`

## pseudocode

```c
BOOL __stdcall DllMain(HINSTANCE hinstDLL, DWORD fdwReason, LPVOID lpvReserved)
{
  if ( wil::details::g_processShutdownInProgress )
  {
    if ( !fdwReason )
    {
LABEL_4:
      if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::GetImpl'::`2'::impl) )
        SetProcessMitigationMode(0);
      return 1;
    }
  }
  else if ( !fdwReason )
  {
    wil::details::g_processShutdownInProgress = lpvReserved != 0;
    goto LABEL_4;
  }
  if ( fdwReason == 1 )
  {
    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::GetImpl'::`2'::impl) )
      SetProcessMitigationMode(2);
    DisableThreadLibraryCalls(hinstDLL);
  }
  return 1;
}

```

## disassembly

```asm
0x18000bfd4  push    rbx
0x18000bfd6  sub     rsp, 20h
0x18000bfda  cmp     cs:?g_processShutdownInProgress@details@wil@@3_NA, 0; bool wil::details::g_processShutdownInProgress
0x18000bfe1  mov     rbx, rcx
0x18000bfe4  jnz     short loc_18000C018
0x18000bfe6  test    edx, edx
0x18000bfe8  jnz     short loc_18000C01C
0x18000bfea  test    r8, r8
0x18000bfed  jz      short loc_18000BFF6
0x18000bfef  mov     cs:?g_processShutdownInProgress@details@wil@@3_NA, 1; bool wil::details::g_processShutdownInProgress
0x18000bff6  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::GetImpl(void)'::`2'::impl
0x18000bffd  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::__private_IsEnabled(void)
0x18000c002  test    al, al
0x18000c004  jz      short loc_18000C00D
0x18000c006  xor     ecx, ecx
0x18000c008  call    SetProcessMitigationMode
0x18000c00d  mov     eax, 1
0x18000c012  add     rsp, 20h
0x18000c016  pop     rbx
0x18000c017  retn
0x18000c018  test    edx, edx
0x18000c01a  jz      short loc_18000BFF6
0x18000c01c  cmp     edx, 1
0x18000c01f  jnz     short loc_18000C00D
0x18000c021  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard> `wil::Feature<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::GetImpl(void)'::`2'::impl
0x18000c028  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_WalletServiceRedirectionGuard>::__private_IsEnabled(void)
0x18000c02d  test    al, al
0x18000c02f  jz      short loc_18000C03B
0x18000c031  mov     ecx, 2
0x18000c036  call    SetProcessMitigationMode
0x18000c03b  mov     rcx, rbx; hLibModule
0x18000c03e  call    cs:__imp_DisableThreadLibraryCalls
0x18000c044  jmp     short loc_18000C00D
```
