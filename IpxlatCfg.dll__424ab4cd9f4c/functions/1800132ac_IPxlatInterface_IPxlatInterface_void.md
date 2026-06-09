# IPxlatInterface::~IPxlatInterface(void)

- ea: `0x1800132ac`
- end: `0x1800132de`
- name: `??1IPxlatInterface@@QEAA@XZ`
- size: `50`
- prototype: `void __fastcall(IPxlatInterface *__hidden this)`
- caller_count: `7`
- callee_count: `4`
- tags: ``

## callers

- `0x18000e734`
- `0x18000f260`
- `0x18000f34c`
- `0x18000f37c`
- `0x18000f4f8`
- `0x18000f668`
- `0x18000f9f0`

## callees

- `0x18001254c`
- `0x1800132ac`
- `0x180013720`
- `0x1800179d0`

## pseudocode

```c
void __fastcall IPxlatInterface::~IPxlatInterface(IPxlatInterface *this)
{
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl'::`2'::impl) )
    IPxlatTelemetry::IPxlatDisabled<_GUID &>((char *)this + 208);
  IPxlatInterface::Cleanup(this);
}

```

## disassembly

```asm
0x1800132ac  push    rbx
0x1800132ae  sub     rsp, 20h
0x1800132b2  mov     rbx, rcx
0x1800132b5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry> `wil::Feature<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::GetImpl(void)'::`2'::impl
0x1800132bc  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CLAT_Preview2_Telemetry>::__private_IsEnabled(void)
0x1800132c1  test    al, al
0x1800132c3  jz      short loc_1800132D1
0x1800132c5  lea     rcx, [rbx+0D0h]
0x1800132cc  call    ??$IPxlatDisabled@AEAU_GUID@@@IPxlatTelemetry@@SAXAEAU_GUID@@@Z; IPxlatTelemetry::IPxlatDisabled<_GUID &>(_GUID &)
0x1800132d1  mov     rcx, rbx; this
0x1800132d4  add     rsp, 20h
0x1800132d8  pop     rbx
0x1800132d9  jmp     ?Cleanup@IPxlatInterface@@QEAAXXZ; IPxlatInterface::Cleanup(void)
```
