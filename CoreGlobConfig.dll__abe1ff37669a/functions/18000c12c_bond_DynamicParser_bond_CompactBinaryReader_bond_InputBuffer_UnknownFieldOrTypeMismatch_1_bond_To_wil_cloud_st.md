# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(ushort,bond::Metadata const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &)

- ea: `0x18000c12c`
- end: `0x18000c172`
- name: `??$UnknownFieldOrTypeMismatch@$00V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NGAEBUMetadata@1@GW4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@@Z`
- size: `70`
- prototype: `char __fastcall(__int64 *, __int16, __int64, __int16, __int64, __int64)`
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a7a4`
- `0x18000a86c`
- `0x18000aa0c`

## callees

- `0x180009b08`
- `0x18000ba24`
- `0x18000c12c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<1,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>>(
        __int64 *a1,
        __int16 a2,
        __int64 a3,
        __int16 a4,
        __int64 a5,
        __int64 a6)
{
  if ( a4 == a2 && (unsigned int)(a5 - 10) > 3 )
    return bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
             a2,
             (unsigned int)a5,
             a5,
             a6,
             *a1);
  bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>((bond::InputBuffer *)*a1, a5);
  return 0;
}

```

## disassembly

```asm
0x18000c12c  sub     rsp, 38h
0x18000c130  movzx   r10d, dx
0x18000c134  mov     edx, dword ptr [rsp+38h+arg_20]
0x18000c138  cmp     r9w, r10w
0x18000c13c  jnz     short loc_18000C163
0x18000c13e  lea     eax, [rdx-0Ah]
0x18000c141  cmp     eax, 3
0x18000c144  jbe     short loc_18000C163
0x18000c146  mov     rax, [rcx]
0x18000c149  mov     r8d, edx
0x18000c14c  mov     r9, [rsp+38h+arg_28]
0x18000c151  movzx   ecx, r10w
0x18000c155  mov     [rsp+38h+arg_20], rax
0x18000c15a  add     rsp, 38h
0x18000c15e  jmp     ??$BasicTypeField@V?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@UBuiltInProtocols@bond@@V?$RequiredFieldValiadator@V?$cloud_store_data@UCultureSettings@Culture@Globalization@Data@Windows@@@wil@@@4@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z; bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>,bond::BuiltInProtocols,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Globalization::Culture::CultureSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)
0x18000c163  mov     rcx, [rcx]; this
0x18000c166  call    ??$SkipType@$$V@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@IEAAXW4BondDataType@2_bond_enumerators@1@@Z; bond::CompactBinaryReader<bond::InputBuffer>::SkipType<>(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000c16b  xor     al, al
0x18000c16d  add     rsp, 38h
0x18000c171  retn
```
