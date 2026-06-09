# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000ae24`
- end: `0x18000b00f`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSyncedSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `491`
- prototype: `char __fastcall(__int64, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011a08`

## callees

- `0x18000ae24`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`
- `0x18001f55c`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSyncedSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        bond::InputBuffer *a5)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  bond::InputBuffer *v16; // [rsp+20h] [rbp-10h] BYREF
  char v17; // [rsp+28h] [rbp-8h]

  if ( a3 > 8 )
  {
    v10 = a3 - 9;
    if ( !v10 )
    {
      v16 = a5;
      v17 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
      return 0;
    }
    v11 = v10 - 5;
    if ( !v11 )
      goto LABEL_11;
    v12 = v11 - 1;
    if ( !v12 )
      goto LABEL_10;
    v13 = v12 - 1;
    if ( !v13 )
      goto LABEL_10;
    v14 = v13 - 1;
    if ( !v14 )
      goto LABEL_10;
    if ( v14 == 1 )
    {
      v16 = a5;
      v17 = 1;
      bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
    }
  }
  else
  {
    if ( a3 == 8 )
    {
      v16 = a5;
      v17 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
      return 0;
    }
    v5 = a3 - 2;
    if ( v5 )
    {
      v6 = v5 - 1;
      if ( v6 )
      {
        v7 = v6 - 1;
        if ( v7 )
        {
          v8 = v7 - 1;
          if ( v8 )
          {
            v9 = v8 - 1;
            if ( v9 )
            {
              if ( v9 == 1 )
              {
                v16 = a5;
                v17 = 1;
                bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
              }
              return 0;
            }
          }
        }
LABEL_10:
        v16 = a5;
        v17 = 1;
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
        return 0;
      }
LABEL_11:
      v16 = a5;
      v17 = 1;
      bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
      return 0;
    }
    v16 = a5;
    v17 = 0;
    if ( *((_DWORD *)a5 + 6) == *((_DWORD *)a5 + 8) )
      bond::InputBuffer::EofException(a5, 1u);
    **(_BYTE **)(a4 + 8) = *(_BYTE *)((unsigned int)(*((_DWORD *)a5 + 8))++ + *((_QWORD *)a5 + 2));
    bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
  }
  return 0;
}

```

## disassembly

```asm
0x18000ae24  push    rbp
0x18000ae26  mov     rbp, rsp
0x18000ae29  sub     rsp, 30h
0x18000ae2d  cmp     r8d, 8
0x18000ae31  jg      loc_18000AF53
0x18000ae37  jz      loc_18000AF39
0x18000ae3d  sub     r8d, 2
0x18000ae41  jz      loc_18000AEEF
0x18000ae47  sub     r8d, 1
0x18000ae4b  jz      loc_18000AED5
0x18000ae51  sub     r8d, 1
0x18000ae55  jz      short loc_18000AEBB
0x18000ae57  sub     r8d, 1
0x18000ae5b  jz      short loc_18000AEA1
0x18000ae5d  sub     r8d, 1
0x18000ae61  jz      short loc_18000AE87
0x18000ae63  cmp     r8d, 1
0x18000ae67  jnz     loc_18000B007
0x18000ae6d  mov     rax, [rbp+arg_20]
0x18000ae71  mov     [rbp+var_10], rax
0x18000ae75  mov     [rbp+var_8], r8b
0x18000ae79  lea     rcx, [rbp+var_10]
0x18000ae7d  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ae82  jmp     loc_18000B007
0x18000ae87  mov     rax, [rbp+arg_20]
0x18000ae8b  mov     [rbp+var_10], rax
0x18000ae8f  mov     [rbp+var_8], 1
0x18000ae93  lea     rcx, [rbp+var_10]
0x18000ae97  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ae9c  jmp     loc_18000B007
0x18000aea1  mov     rax, [rbp+arg_20]
0x18000aea5  mov     [rbp+var_10], rax
0x18000aea9  mov     [rbp+var_8], 1
0x18000aead  lea     rcx, [rbp+var_10]
0x18000aeb1  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aeb6  jmp     loc_18000B007
0x18000aebb  mov     rax, [rbp+arg_20]
0x18000aebf  mov     [rbp+var_10], rax
0x18000aec3  mov     [rbp+var_8], 1
0x18000aec7  lea     rcx, [rbp+var_10]
0x18000aecb  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aed0  jmp     loc_18000B007
0x18000aed5  mov     rax, [rbp+arg_20]
0x18000aed9  mov     [rbp+var_10], rax
0x18000aedd  mov     [rbp+var_8], 1
0x18000aee1  lea     rcx, [rbp+var_10]
0x18000aee5  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aeea  jmp     loc_18000B007
0x18000aeef  mov     r8, [rbp+arg_20]
0x18000aef3  mov     [rbp+var_10], r8
0x18000aef7  mov     [rbp+var_8], 0
0x18000aefb  mov     eax, [r8+18h]
0x18000aeff  sub     eax, [r8+20h]
0x18000af03  cmp     eax, 1
0x18000af06  jnb     short loc_18000AF16
0x18000af08  mov     edx, 1; unsigned int
0x18000af0d  mov     rcx, r8; this
0x18000af10  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000af16  mov     edx, [r8+20h]
0x18000af1a  mov     rax, [r8+10h]
0x18000af1e  mov     rcx, [r9+8]
0x18000af22  mov     al, [rdx+rax]
0x18000af25  mov     [rcx], al
0x18000af27  inc     dword ptr [r8+20h]
0x18000af2b  lea     rcx, [rbp+var_10]
0x18000af2f  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000af34  jmp     loc_18000B007
0x18000af39  mov     rax, [rbp+arg_20]
0x18000af3d  mov     [rbp+var_10], rax
0x18000af41  mov     [rbp+var_8], 1
0x18000af45  lea     rcx, [rbp+var_10]
0x18000af49  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000af4e  jmp     loc_18000B007
0x18000af53  sub     r8d, 9
0x18000af57  jz      loc_18000AFF2
0x18000af5d  sub     r8d, 5
0x18000af61  jz      short loc_18000AFDB
0x18000af63  sub     r8d, 1
0x18000af67  jz      short loc_18000AFC4
0x18000af69  sub     r8d, 1
0x18000af6d  jz      short loc_18000AFAD
0x18000af6f  sub     r8d, 1
0x18000af73  jz      short loc_18000AF96
0x18000af75  cmp     r8d, 1
0x18000af79  jnz     loc_18000B007
0x18000af7f  mov     rax, [rbp+arg_20]
0x18000af83  mov     [rbp+var_10], rax
0x18000af87  mov     [rbp+var_8], r8b
0x18000af8b  lea     rcx, [rbp+var_10]
0x18000af8f  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000af94  jmp     short loc_18000B007
0x18000af96  mov     rax, [rbp+arg_20]
0x18000af9a  mov     [rbp+var_10], rax
0x18000af9e  mov     [rbp+var_8], 1
0x18000afa2  lea     rcx, [rbp+var_10]
0x18000afa6  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000afab  jmp     short loc_18000B007
0x18000afad  mov     rax, [rbp+arg_20]
0x18000afb1  mov     [rbp+var_10], rax
0x18000afb5  mov     [rbp+var_8], 1
0x18000afb9  lea     rcx, [rbp+var_10]
0x18000afbd  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000afc2  jmp     short loc_18000B007
0x18000afc4  mov     rax, [rbp+arg_20]
0x18000afc8  mov     [rbp+var_10], rax
0x18000afcc  mov     [rbp+var_8], 1
0x18000afd0  lea     rcx, [rbp+var_10]
0x18000afd4  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000afd9  jmp     short loc_18000B007
0x18000afdb  mov     rax, [rbp+arg_20]
0x18000afdf  mov     [rbp+var_10], rax
0x18000afe3  mov     [rbp+var_8], 1
0x18000afe7  lea     rcx, [rbp+var_10]
0x18000afeb  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aff0  jmp     short loc_18000B007
0x18000aff2  mov     rax, [rbp+arg_20]
0x18000aff6  mov     [rbp+var_10], rax
0x18000affa  mov     [rbp+var_8], 1
0x18000affe  lea     rcx, [rbp+var_10]
0x18000b002  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b007  xor     al, al
0x18000b009  add     rsp, 30h
0x18000b00d  pop     rbp
0x18000b00e  retn
```
