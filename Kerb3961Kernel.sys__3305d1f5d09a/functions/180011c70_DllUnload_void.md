# DllUnload(void)

- ea: `0x180011c70`
- end: `0x180011d2a`
- name: `?DllUnload@@YAJXZ`
- size: `186`
- prototype: `__int64(void)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x180011b40`
- `0x180011c70`
- `0x180012240`

## import_xrefs

- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180011cdd`
- `ntoskrnl!RtlUnregisterFeatureConfigurationChangeNotification` at `0x180011cdd`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180011d00`
- `ntoskrnl!RtlUnregisterFeatureUsageProvider` at `0x180011d00`
- `ntoskrnl!EtwUnregister` at `0x180011cc5`
- `ntoskrnl!EtwUnregister` at `0x180011cc5`

## pseudocode

```c
__int64 DllUnload(void)
{
  unsigned __int64 i; // rbx
  REGHANDLE v1; // rcx

  for ( i = 0; i < countAtexitFunctions; ++i )
    (*((void (**)(void))atexitFunctions + i))();
  Kerb3961Free(atexitFunctions);
  v1 = RegHandle;
  dword_18001A000 = 0;
  RegHandle = 0;
  EtwUnregister(v1);
  if ( g_wil_details_featureChangeNotification )
  {
    RtlUnregisterFeatureConfigurationChangeNotification();
    g_wil_details_featureChangeNotification = 0;
  }
  if ( g_wil_details_featureUsageProvider )
  {
    RtlUnregisterFeatureUsageProvider();
    g_wil_details_featureUsageProvider = 0;
  }
  g_wil_details_isFeatureStagingInitialized = 0;
  return 0;
}

```

## disassembly

```asm
0x180011c70  push    rbx
0x180011c72  sub     rsp, 20h
0x180011c76  xor     ebx, ebx
0x180011c78  cmp     cs:?countAtexitFunctions@@3_KA, rbx; unsigned __int64 countAtexitFunctions
0x180011c7f  jbe     short loc_180011C9D
0x180011c81  mov     rax, cs:?atexitFunctions@@3PEAP6AXXZEA; void (** atexitFunctions)(void)
0x180011c88  mov     rax, [rax+rbx*8]
0x180011c8c  call    _guard_dispatch_icall
0x180011c91  inc     rbx
0x180011c94  cmp     rbx, cs:?countAtexitFunctions@@3_KA; unsigned __int64 countAtexitFunctions
0x180011c9b  jb      short loc_180011C81
0x180011c9d  mov     rcx, cs:?atexitFunctions@@3PEAP6AXXZEA; void (** atexitFunctions)(void)
0x180011ca4  call    Kerb3961Free
0x180011ca9  mov     rcx, cs:RegHandle; RegHandle
0x180011cb0  mov     cs:dword_18001A000, 0
0x180011cba  mov     cs:RegHandle, 0
0x180011cc5  call    cs:__imp_EtwUnregister
0x180011ccc  nop     dword ptr [rax+rax+00h]
0x180011cd1  mov     rcx, cs:g_wil_details_featureChangeNotification
0x180011cd8  test    rcx, rcx
0x180011cdb  jz      short loc_180011CF4
0x180011cdd  call    cs:__imp_RtlUnregisterFeatureConfigurationChangeNotification
0x180011ce4  nop     dword ptr [rax+rax+00h]
0x180011ce9  mov     cs:g_wil_details_featureChangeNotification, 0
0x180011cf4  mov     rcx, cs:g_wil_details_featureUsageProvider
0x180011cfb  test    rcx, rcx
0x180011cfe  jz      short loc_180011D17
0x180011d00  call    cs:__imp_RtlUnregisterFeatureUsageProvider
0x180011d07  nop     dword ptr [rax+rax+00h]
0x180011d0c  mov     cs:g_wil_details_featureUsageProvider, 0
0x180011d17  mov     cs:g_wil_details_isFeatureStagingInitialized, 0
0x180011d21  xor     eax, eax
0x180011d23  add     rsp, 20h
0x180011d27  pop     rbx
0x180011d28  retn
```
