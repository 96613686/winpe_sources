# Registry::Key::HKLM(void)

- ea: `0x18000cb08`
- end: `0x18000cb3a`
- name: `?HKLM@Key@Registry@@SA?AU12@XZ`
- size: `50`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000cc78`

## callees

- `0x18000cb08`
- `0x1800171d8`

## pseudocode

```c
__int64 __fastcall Registry::Key::HKLM(__int64 a1)
{
  bool v2; // zf
  __int64 result; // rax

  v2 = wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled((wil::details *)`wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl'::`2'::impl) == 0;
  *(_QWORD *)(a1 + 8) = -2147483646;
  result = a1;
  *(_BYTE *)a1 = v2;
  return result;
}

```

## disassembly

```asm
0x18000cb08  push    rbx
0x18000cb0a  sub     rsp, 30h
0x18000cb0e  mov     rbx, rcx
0x18000cb11  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown> `wil::Feature<__WilFeatureTraits_Feature_InstallServiceShutdown>::GetImpl(void)'::`2'::impl
0x18000cb18  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_InstallServiceShutdown@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_InstallServiceShutdown>::__private_IsEnabled(void)
0x18000cb1d  test    al, al
0x18000cb1f  mov     qword ptr [rbx+8], 0FFFFFFFF80000002h
0x18000cb27  mov     rax, rbx
0x18000cb2a  jz      short loc_18000CB31
0x18000cb2c  mov     byte ptr [rbx], 0
0x18000cb2f  jmp     short loc_18000CB34
0x18000cb31  mov     byte ptr [rbx], 1
0x18000cb34  add     rsp, 30h
0x18000cb38  pop     rbx
0x18000cb39  retn
```
