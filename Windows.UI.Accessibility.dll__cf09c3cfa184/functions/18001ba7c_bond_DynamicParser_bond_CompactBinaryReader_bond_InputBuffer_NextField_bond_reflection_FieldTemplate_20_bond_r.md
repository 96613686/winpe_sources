# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::NextField<bond::reflection::FieldTemplate<20,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusActiveSessions,std::vector<Windows::Data::Shell::FocusSession,std::allocator<Windows::Data::Shell::FocusSession>>,16,&bond::Metadata const Windows::Data::Shell::FocusActiveSessions::Schema::s_sessions_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>>>>(bond::reflection::FieldTemplate<20,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusActiveSessions,std::vector<Windows::Data::Shell::FocusSession,std::allocator<Windows::Data::Shell::FocusSession>>,16,&bond::Metadata const Windows::Data::Shell::FocusActiveSessions::Schema::s_sessions_metadata> const &,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>>> const &)

- ea: `0x18001ba7c`
- end: `0x18001bb1d`
- name: `??$NextField@U?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusActiveSessions@Shell@Data@Windows@@V?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@$0BA@$1?s_sessions_metadata@Schema@FocusActiveSessions@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0BE@Uoptional_field_modifier@reflection@bond@@UFocusActiveSessions@Shell@Data@Windows@@V?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@$0BA@$1?s_sessions_metadata@Schema@FocusActiveSessions@Shell@Data@Windows@@0UMetadata@bond@@B@reflection@1@AEBV?$To@V?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusActiveSessions@Shell@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `161`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c218`

## callees

- `0x180015544`
- `0x180015e78`
- `0x18001b298`
- `0x18001ba7c`
- `0x1800205d8`
- `0x1800205f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::NextField<bond::reflection::FieldTemplate<20,bond::reflection::optional_field_modifier,Windows::Data::Shell::FocusActiveSessions,std::vector<Windows::Data::Shell::FocusSession>,16,&private: static bond::Metadata const Windows::Data::Shell::FocusActiveSessions::Schema::s_sessions_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusActiveSessions>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  bond::InputBuffer *v5; // [rsp+20h] [rbp-20h] BYREF
  char v6; // [rsp+28h] [rbp-18h]
  bond::InputBuffer *v7; // [rsp+30h] [rbp-10h] BYREF
  char v8; // [rsp+38h] [rbp-8h]

  v7 = *a1;
  v3 = *(_QWORD *)(a3 + 8);
  v8 = 0;
  v5 = v7;
  v6 = 0;
  bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(v7);
  bond::DeserializeElements<std::vector<Windows::Data::Shell::FocusSession>,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(
    (__int64 *)(v3 + 16),
    (__int64 *)&v5,
    0);
  bond::value_common<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>(&v5);
  bond::value_common<std::vector<Windows::Data::Shell::FocusSession>,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::vector<Windows::Data::Shell::FocusSession>,bond::CompactBinaryReader<bond::InputBuffer> &>(&v7);
  return 0;
}

```

## disassembly

```asm
0x18001ba7c  mov     [rsp-8+arg_10], rbx
0x18001ba81  mov     [rsp-8+arg_18], rdi
0x18001ba86  mov     [rsp-8+arg_8], rdx
0x18001ba8b  push    rbp
0x18001ba8c  mov     rbp, rsp
0x18001ba8f  sub     rsp, 40h
0x18001ba93  mov     rdi, [rcx]
0x18001ba96  mov     [rbp+var_10], rdi
0x18001ba9a  mov     rbx, [r8+8]
0x18001ba9e  mov     [rbp+var_8], 0
0x18001baa2  mov     [rbp+var_20], rdi
0x18001baa6  mov     [rbp+var_18], 0
0x18001baaa  mov     [rbp+arg_0], 0Ah
0x18001bab1  mov     dword ptr [rbp+arg_8], 0
0x18001bab8  lea     r8, [rbp+arg_0]
0x18001babc  lea     rdx, [rbp+arg_8]
0x18001bac0  mov     rcx, rdi; this
0x18001bac3  call    ?ReadContainerBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAIAEAW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(uint &,bond::_bond_enumerators::BondDataType::BondDataType &)
0x18001bac8  cmp     [rbp+arg_0], 0Ah
0x18001bacc  jnz     short loc_18001BAE1
0x18001bace  lea     rcx, [rbx+10h]
0x18001bad2  mov     r8d, dword ptr [rbp+arg_8]
0x18001bad6  lea     rdx, [rbp+var_20]
0x18001bada  call    ??$DeserializeElements@V?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@V?$value@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@bond@@@bond@@YAXAEAV?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@AEBV?$value@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@X@0@I@Z; bond::DeserializeElements<std::vector<Windows::Data::Shell::FocusSession>,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void>>(std::vector<Windows::Data::Shell::FocusSession> &,bond::value<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &,void> const &,uint)
0x18001badf  jmp     short loc_18001BAF8
0x18001bae1  mov     ebx, dword ptr [rbp+arg_8]
0x18001bae4  test    ebx, ebx
0x18001bae6  jz      short loc_18001BAF8
0x18001bae8  mov     edx, [rbp+arg_0]
0x18001baeb  mov     rcx, rdi; this
0x18001baee  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18001baf3  add     ebx, 0FFFFFFFFh
0x18001baf6  jnz     short loc_18001BAE8
0x18001baf8  lea     rcx, [rbp+var_20]
0x18001bafc  call    ??1?$value_common@UFocusSession@Shell@Data@Windows@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<Windows::Data::Shell::FocusSession,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001bb01  nop
0x18001bb02  lea     rcx, [rbp+var_10]
0x18001bb06  call    ??1?$value_common@V?$vector@UFocusSession@Shell@Data@Windows@@V?$allocator@UFocusSession@Shell@Data@Windows@@@std@@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::vector<Windows::Data::Shell::FocusSession>,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::vector<Windows::Data::Shell::FocusSession>,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001bb0b  xor     al, al
0x18001bb0d  mov     rbx, [rsp+40h+arg_10]
0x18001bb12  mov     rdi, [rsp+40h+arg_18]
0x18001bb17  add     rsp, 40h
0x18001bb1b  pop     rbp
0x18001bb1c  retn
```
