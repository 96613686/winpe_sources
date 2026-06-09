# Registry::Key::~Key(void)

- ea: `0x18000c780`
- end: `0x18000c7af`
- name: `??1Key@Registry@@QEAA@XZ`
- size: `47`
- prototype: `void __fastcall(Registry::Key *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000cc78`

## callees

- `0x18000c780`
- `0x1800171d8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7a2`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000c7a2`

## pseudocode

```c
void __fastcall Registry::Key::~Key(HKEY *this)
{
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl) )
  {
    if ( *(_BYTE *)this )
      RegCloseKey(this[1]);
  }
}

```

## disassembly

```asm
0x18000c780  push    rbx
0x18000c782  sub     rsp, 20h
0x18000c786  mov     rbx, rcx
0x18000c789  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown> `wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl(void)'::`2'::impl
0x18000c790  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)
0x18000c795  test    al, al
0x18000c797  jz      short loc_18000C7A9
0x18000c799  cmp     byte ptr [rbx], 0
0x18000c79c  jz      short loc_18000C7A9
0x18000c79e  mov     rcx, [rbx+8]; hKey
0x18000c7a2  call    cs:__imp_RegCloseKey
0x18000c7a8  nop
0x18000c7a9  add     rsp, 20h
0x18000c7ad  pop     rbx
0x18000c7ae  retn
```
