# CONFIG_OBJECT_EXTENSION::InitializeObjectTypeInformation(void)

- ea: `0x18001b0b0`
- end: `0x18001b137`
- name: `?InitializeObjectTypeInformation@CONFIG_OBJECT_EXTENSION@@MEAAJXZ`
- size: `135`
- prototype: `__int64 __fastcall(CONFIG_OBJECT_EXTENSION *__hidden this)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callees

- `0x18000fc84`
- `0x180012b28`
- `0x18001b0b0`

## string_xrefs

- `0x18001b0bc`: `CONFIGS`
- `0x18001b0c3`: `CONFIG`

## pseudocode

```c
int __fastcall CONFIG_OBJECT_EXTENSION::InitializeObjectTypeInformation(CONFIG_OBJECT_EXTENSION *this)
{
  int result; // eax

  result = OBJECT_EXTENSION::SetObjectType(this, L"CONFIG", L"CONFIGS", 0x400004CBu);
  if ( result >= 0 )
    return OBJECT_EXTENSION::AddVerbTypeInformation(
             this,
             0xAu,
             (const unsigned __int16 **const)&g_apszconfigVerbNames,
             (unsigned int (*const)[2])g_adwconfigVerbMetadata,
             0x1Du,
             (const unsigned __int16 **const)&g_apszconfigParamNames,
             (unsigned int (*const)[3])g_adwconfigParameterMetadata,
             0x21u,
             (const unsigned __int16 **const)&g_apszconfigExamples,
             (unsigned int (*const)[2])g_adwconfigExampleMetadata);
  return result;
}

```

## disassembly

```asm
0x18001b0b0  push    rbx
0x18001b0b2  sub     rsp, 50h
0x18001b0b6  mov     r9d, 400004CBh; unsigned int
0x18001b0bc  lea     r8, aConfigs; "CONFIGS"
0x18001b0c3  lea     rdx, aConfig; "CONFIG"
0x18001b0ca  mov     rbx, rcx
0x18001b0cd  call    ?SetObjectType@OBJECT_EXTENSION@@IEAAJPEBG0K@Z; OBJECT_EXTENSION::SetObjectType(ushort const *,ushort const *,ulong)
0x18001b0d2  test    eax, eax
0x18001b0d4  js      short loc_18001B131
0x18001b0d6  lea     rax, ?g_adwconfigExampleMetadata@@3PAY01KA; ulong (near * g_adwconfigExampleMetadata)[2]
0x18001b0dd  mov     edx, 0Ah; unsigned int
0x18001b0e2  mov     [rsp+58h+var_10], rax; unsigned int (*)[2]
0x18001b0e7  lea     r9, ?g_adwconfigVerbMetadata@@3PAY01KA; unsigned int (*)[2]
0x18001b0ee  lea     rax, ?g_apszconfigExamples@@3PAPEBGA; ushort const * near * g_apszconfigExamples
0x18001b0f5  mov     rcx, rbx; this
0x18001b0f8  mov     [rsp+58h+var_18], rax; unsigned __int16 **
0x18001b0fd  lea     r8, ?g_apszconfigVerbNames@@3PAPEBGA; unsigned __int16 **
0x18001b104  mov     [rsp+58h+var_20], 21h ; '!'; unsigned int
0x18001b10c  lea     rax, ?g_adwconfigParameterMetadata@@3PAY02KA; ulong (near * g_adwconfigParameterMetadata)[3]
0x18001b113  mov     [rsp+58h+var_28], rax; unsigned int (*)[3]
0x18001b118  lea     rax, ?g_apszconfigParamNames@@3PAPEBGA; ushort const * near * g_apszconfigParamNames
0x18001b11f  mov     [rsp+58h+var_30], rax; unsigned __int16 **
0x18001b124  mov     [rsp+58h+var_38], 1Dh; unsigned int
0x18001b12c  call    ?AddVerbTypeInformation@OBJECT_EXTENSION@@IEAAJKQEAPEBGQEAY01KK0QEAY02KK01@Z; OBJECT_EXTENSION::AddVerbTypeInformation(ulong,ushort const * * const,ulong (* const)[2],ulong,ushort const * * const,ulong (* const)[3],ulong,ushort const * * const,ulong (* const)[2])
0x18001b131  add     rsp, 50h
0x18001b135  pop     rbx
0x18001b136  retn
```
