# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>> const &,ushort &,bond::_bond_enumerators::BondDataType::BondDataType &,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)

- ea: `0x18000d8e4`
- end: `0x18000d9bd`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAAXAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEAGAEAW4BondDataType@5_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `217`
- prototype: `__int64 __fastcall(bond::InputBuffer **, __int64, _WORD *, _DWORD *, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000e2dc`

## callees

- `0x18000d8e4`
- `0x1800110c0`
- `0x18001b528`
- `0x18001f55c`
- `0x18002099c`
- `0x180022000`

## pseudocode

```c
__int64 __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        _WORD *a3,
        _DWORD *a4,
        __int64 a5)
{
  bond::InputBuffer *v8; // r8
  __int64 result; // rax
  bond::InputBuffer *v10; // [rsp+30h] [rbp-38h] BYREF
  char v11; // [rsp+38h] [rbp-30h]

  do
  {
    if ( *a3 == 1 )
    {
      if ( *a4 == 2 )
      {
        v8 = *a1;
        v10 = v8;
        v11 = 0;
        if ( *((_DWORD *)v8 + 6) == *((_DWORD *)v8 + 8) )
          bond::InputBuffer::EofException(v8, 1u);
        *(_BYTE *)(*(_QWORD *)(a5 + 8) + 1LL) = *(_BYTE *)((unsigned int)(*((_DWORD *)v8 + 8))++ + *((_QWORD *)v8 + 2));
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v10);
        goto LABEL_8;
      }
    }
    else if ( *a3 > 1u )
    {
      break;
    }
    if ( *a4 <= 1u )
      break;
    bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&private: static bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(
      a1,
      a2,
      (unsigned __int16)*a3,
      (unsigned int)*a4,
      a5);
LABEL_8:
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  while ( *a3 <= 1u && *a4 > 1u );
  while ( 1 )
  {
    result = (unsigned int)*a4;
    if ( (unsigned int)result <= 1 )
      break;
    bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
  }
  return result;
}

```

## disassembly

```asm
0x18000d8e4  push    rbx
0x18000d8e6  push    rbp
0x18000d8e7  push    rsi
0x18000d8e8  push    rdi
0x18000d8e9  push    r14
0x18000d8eb  sub     rsp, 40h
0x18000d8ef  mov     rbx, r9
0x18000d8f2  mov     rsi, r8
0x18000d8f5  mov     rdi, rcx
0x18000d8f8  mov     r14d, 1
0x18000d8fe  mov     rbp, [rsp+68h+arg_20]
0x18000d906  cmp     r14w, [rsi]
0x18000d90a  jnz     short loc_18000D94D
0x18000d90c  cmp     dword ptr [rbx], 2
0x18000d90f  jnz     short loc_18000D94F
0x18000d911  mov     r8, [rdi]
0x18000d914  mov     [rsp+68h+var_38], r8
0x18000d919  mov     [rsp+68h+var_30], 0
0x18000d91e  mov     eax, [r8+18h]
0x18000d922  sub     eax, [r8+20h]
0x18000d926  cmp     eax, r14d
0x18000d929  jb      short loc_18000D983
0x18000d92b  mov     edx, [r8+20h]
0x18000d92f  mov     rax, [r8+10h]
0x18000d933  mov     rcx, [rbp+8]
0x18000d937  mov     al, [rdx+rax]
0x18000d93a  mov     [rcx+1], al
0x18000d93d  add     [r8+20h], r14d
0x18000d941  lea     rcx, [rsp+68h+var_38]
0x18000d946  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000d94b  jmp     short loc_18000D968
0x18000d94d  jb      short loc_18000D9AC
0x18000d94f  cmp     [rbx], r14d
0x18000d952  jbe     short loc_18000D9AC
0x18000d954  mov     [rsp+68h+var_48], rbp
0x18000d959  mov     r9d, [rbx]
0x18000d95c  movzx   r8d, word ptr [rsi]
0x18000d960  mov     rcx, rdi
0x18000d963  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$00Uoptional_field_modifier@reflection@bond@@UTouchSettings@Devices@Input@Data@Windows@@_N$00$1?s_allowTouchScreenWake_metadata@Schema@TouchSettings@Devices@Input@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>>(bond::reflection::FieldTemplate<1,bond::reflection::optional_field_modifier,Windows::Data::Input::Devices::TouchSettings,bool,1,&bond::Metadata const Windows::Data::Input::Devices::TouchSettings::Schema::s_allowTouchScreenWake_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &)
0x18000d968  mov     r8, rsi
0x18000d96b  mov     rdx, rbx
0x18000d96e  mov     rcx, [rdi]; this
0x18000d971  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000d976  cmp     r14w, [rsi]
0x18000d97a  jb      short loc_18000D9AC
0x18000d97c  cmp     [rbx], r14d
0x18000d97f  ja      short loc_18000D906
0x18000d981  jmp     short loc_18000D9AC
0x18000d983  mov     edx, r14d; unsigned int
0x18000d986  mov     rcx, r8; this
0x18000d989  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000d98f  cmp     eax, r14d
0x18000d992  jz      short loc_18000D9B2
0x18000d994  mov     edx, eax
0x18000d996  mov     rcx, [rdi]; this
0x18000d999  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000d99e  mov     r8, rsi
0x18000d9a1  mov     rdx, rbx
0x18000d9a4  mov     rcx, [rdi]; this
0x18000d9a7  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x18000d9ac  mov     eax, [rbx]
0x18000d9ae  test    eax, eax
0x18000d9b0  jnz     short loc_18000D98F
0x18000d9b2  add     rsp, 40h
0x18000d9b6  pop     r14
0x18000d9b8  pop     rdi
0x18000d9b9  pop     rsi
0x18000d9ba  pop     rbp
0x18000d9bb  pop     rbx
0x18000d9bc  retn
```
