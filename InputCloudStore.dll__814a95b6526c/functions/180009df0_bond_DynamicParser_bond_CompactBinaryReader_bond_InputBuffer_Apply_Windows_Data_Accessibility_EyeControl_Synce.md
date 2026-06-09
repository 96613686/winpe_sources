# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>> const &,Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema const &)

- ea: `0x180009df0`
- end: `0x180009e87`
- name: `??$Apply@USchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@V?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@USyncedSettings@EyeControl@Accessibility@Data@Windows@@@wil@@@bond@@@1@AEBUSchema@SyncedSettings@EyeControl@Accessibility@Data@Windows@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000bd64`

## callees

- `0x180009df0`
- `0x18001c15c`
- `0x18002099c`
- `0x180020a28`
- `0x180022000`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Accessibility::EyeControl::SyncedSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Accessibility::EyeControl::SyncedSettings>>>>(
        __int64 a1,
        _WORD *a2,
        __int64 a3)
{
  _WORD *v3; // rbx
  bond::InputBuffer *v5; // rcx
  int v6; // edx
  int v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+50h] [rbp+18h] BYREF

  v9 = a3;
  v3 = a2;
  LOBYTE(a2) = *(_BYTE *)(a1 + 8);
  bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(*(_QWORD *)a1, a2);
  *v3 = -1;
  v5 = *(bond::InputBuffer **)a1;
  LOWORD(v9) = 0;
  v8 = 0;
  bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(v5);
  __(a1, v6, (unsigned int)&v9, (unsigned int)&v8, (__int64)v3);
  if ( !*(_BYTE *)(a1 + 8) )
  {
    while ( v8 )
    {
      if ( v8 != 1 )
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(*(bond::InputBuffer **)a1);
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*(bond::InputBuffer **)a1);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180009df0  mov     [rsp+arg_8], rbx
0x180009df5  mov     [rsp+arg_10], r8
0x180009dfa  push    rdi
0x180009dfb  sub     rsp, 30h
0x180009dff  mov     rbx, rdx
0x180009e02  mov     rdi, rcx
0x180009e05  mov     dl, [rcx+8]
0x180009e08  mov     rcx, [rcx]
0x180009e0b  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009e10  xor     eax, eax
0x180009e12  mov     word ptr [rbx], 0FFFFh
0x180009e17  mov     rcx, [rdi]; this
0x180009e1a  lea     r8, [rsp+38h+arg_10]
0x180009e1f  lea     rdx, [rsp+38h+arg_0]
0x180009e24  mov     word ptr [rsp+38h+arg_10], ax
0x180009e29  mov     [rsp+38h+arg_0], eax
0x180009e2d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009e32  lea     r9, [rsp+38h+arg_0]
0x180009e37  mov     [rsp+38h+var_18], rbx
0x180009e3c  lea     r8, [rsp+38h+arg_10]
0x180009e41  mov     rcx, rdi
0x180009e44  call    ??@5285c9c0a9c863fc65ab703c026a5de8@
0x180009e49  cmp     byte ptr [rdi+8], 0
0x180009e4d  jnz     short loc_180009E7A
0x180009e4f  jmp     short loc_180009E72
0x180009e51  cmp     eax, 1
0x180009e54  jz      short loc_180009E60
0x180009e56  mov     rcx, [rdi]; this
0x180009e59  mov     edx, eax
0x180009e5b  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180009e60  mov     rcx, [rdi]; this
0x180009e63  lea     r8, [rsp+38h+arg_10]
0x180009e68  lea     rdx, [rsp+38h+arg_0]
0x180009e6d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009e72  mov     eax, [rsp+38h+arg_0]
0x180009e76  test    eax, eax
0x180009e78  jnz     short loc_180009E51
0x180009e7a  mov     rbx, [rsp+38h+arg_8]
0x180009e7f  xor     al, al
0x180009e81  add     rsp, 30h
0x180009e85  pop     rdi
0x180009e86  retn
```
