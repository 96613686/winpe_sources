# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::TouchpadSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &,Windows::Data::Input::Devices::TouchpadSettings::Schema const &)

- ea: `0x180009f30`
- end: `0x180009fc7`
- name: `??$Apply@USchema@TouchpadSettings@Devices@Input@Data@Windows@@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA_NAEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEBUSchema@TouchpadSettings@Devices@Input@Data@Windows@@@Z`
- size: `151`
- prototype: `char __fastcall(__int64, _WORD *, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180019250`

## callees

- `0x180009f30`
- `0x18001c420`
- `0x18002099c`
- `0x180020a28`
- `0x180022000`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::Apply<Windows::Data::Input::Devices::TouchpadSettings::Schema,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>>(
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
0x180009f30  mov     [rsp+arg_8], rbx
0x180009f35  mov     [rsp+arg_10], r8
0x180009f3a  push    rdi
0x180009f3b  sub     rsp, 30h
0x180009f3f  mov     rbx, rdx
0x180009f42  mov     rdi, rcx
0x180009f45  mov     dl, [rcx+8]
0x180009f48  mov     rcx, [rcx]
0x180009f4b  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180009f50  xor     eax, eax
0x180009f52  mov     word ptr [rbx], 0FFFFh
0x180009f57  mov     rcx, [rdi]; this
0x180009f5a  lea     r8, [rsp+38h+arg_10]
0x180009f5f  lea     rdx, [rsp+38h+arg_0]
0x180009f64  mov     word ptr [rsp+38h+arg_10], ax
0x180009f69  mov     [rsp+38h+arg_0], eax
0x180009f6d  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009f72  lea     r9, [rsp+38h+arg_0]
0x180009f77  mov     [rsp+38h+var_18], rbx
0x180009f7c  lea     r8, [rsp+38h+arg_10]
0x180009f81  mov     rcx, rdi
0x180009f84  call    ??@7a0513645d88cff4e0402a39d484e782@
0x180009f89  cmp     byte ptr [rdi+8], 0
0x180009f8d  jnz     short loc_180009FBA
0x180009f8f  jmp     short loc_180009FB2
0x180009f91  cmp     eax, 1
0x180009f94  jz      short loc_180009FA0
0x180009f96  mov     rcx, [rdi]; this
0x180009f99  mov     edx, eax
0x180009f9b  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180009fa0  mov     rcx, [rdi]; this
0x180009fa3  lea     r8, [rsp+38h+arg_10]
0x180009fa8  lea     rdx, [rsp+38h+arg_0]
0x180009fad  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180009fb2  mov     eax, [rsp+38h+arg_0]
0x180009fb6  test    eax, eax
0x180009fb8  jnz     short loc_180009F91
0x180009fba  mov     rbx, [rsp+38h+arg_8]
0x180009fbf  xor     al, al
0x180009fc1  add     rsp, 30h
0x180009fc5  pop     rdi
0x180009fc6  retn
```
