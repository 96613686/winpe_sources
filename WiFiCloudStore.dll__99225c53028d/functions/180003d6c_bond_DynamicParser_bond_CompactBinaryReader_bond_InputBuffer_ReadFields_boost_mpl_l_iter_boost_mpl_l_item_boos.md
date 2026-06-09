# bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>> const &,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>> const &)

- ea: `0x180003d6c`
- end: `0x18000403d`
- name: `??$ReadFields@U?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@V?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@bond@@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$l_iter@U?$l_item@U?$long_@$00@mpl@boost@@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@Ul_end@23@@mpl@boost@@@mpl@boost@@AEBV?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@1@@Z`
- size: `721`
- prototype: `char __fastcall(bond::InputBuffer **, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180004050`

## callees

- `0x180002a00`
- `0x1800031d4`
- `0x180003d6c`
- `0x180019b6c`
- `0x18001aa20`
- `0x1800282c0`
- `0x18003071c`

## pseudocode

```c
char __fastcall bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::ReadFields<boost::mpl::l_iter<boost::mpl::l_item<boost::mpl::long_<1>,bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&private: static bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,boost::mpl::l_end>>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(
        bond::InputBuffer **a1,
        __int64 a2,
        __int64 a3)
{
  bond::InputBuffer *v5; // r9
  __int64 v6; // r10
  __int64 v7; // rdx
  __int64 v8; // r11
  char v9; // cl
  __int64 v10; // r10
  unsigned int v11; // ebx
  unsigned __int8 v12; // cl
  __int64 v13; // r8
  bond::InputBuffer *v15; // r8
  __int64 v16; // r10
  int v17; // r9d
  char v18; // dl
  __int16 v19; // cx
  bond::InputBuffer *v20; // r9
  __int64 v21; // r10
  __int64 v22; // r11
  char v23; // cl
  __int64 v24; // r10
  unsigned __int8 v25; // cl
  unsigned int v26; // [rsp+70h] [rbp+30h]
  __int64 v27; // [rsp+78h] [rbp+38h] BYREF

  v27 = a2;
  v5 = *a1;
  v6 = *((unsigned int *)*a1 + 8);
  v7 = *((unsigned int *)*a1 + 6);
  if ( (_DWORD)v7 == (_DWORD)v6 )
    bond::InputBuffer::EofException(*a1, 1u);
  v8 = *((_QWORD *)v5 + 2);
  v9 = *(_BYTE *)(v6 + v8);
  v10 = (unsigned int)(v6 + 1);
  *((_DWORD *)v5 + 8) = v10;
  v11 = v9 & 0x1F;
  v26 = v11;
  v12 = v9 & 0xE0;
  v13 = v12;
  LOWORD(v27) = v12;
  if ( v12 == 224 )
  {
    v7 = (unsigned int)(v7 - v10);
    if ( (unsigned int)v7 < 2 )
      bond::InputBuffer::EofException(v5, 2u);
    v13 = *(unsigned __int16 *)(v10 + v8);
    *((_DWORD *)v5 + 8) = v10 + 2;
    goto LABEL_5;
  }
  if ( v12 != 192 )
  {
    LOWORD(v13) = v12 >> 5;
LABEL_5:
    LOWORD(v27) = v13;
    goto LABEL_6;
  }
  bond::InputBuffer::Read(v5, (unsigned __int8 *)&v27);
  v13 = (unsigned __int16)v27;
LABEL_6:
  while ( !(_WORD)v13 )
  {
    switch ( v11 )
    {
      case 6u:
        bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(*a1);
        break;
      case 0u:
        goto LABEL_9;
      case 1u:
        goto LABEL_43;
      default:
        bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&private: static bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(
          a1,
          v7,
          v13,
          v11,
          a3);
        break;
    }
    v20 = *a1;
    v21 = *((unsigned int *)*a1 + 8);
    v7 = *((unsigned int *)*a1 + 6);
    if ( (_DWORD)v7 == (_DWORD)v21 )
      bond::InputBuffer::EofException(*a1, 1u);
    v22 = *((_QWORD *)v20 + 2);
    v23 = *(_BYTE *)(v21 + v22);
    v24 = (unsigned int)(v21 + 1);
    *((_DWORD *)v20 + 8) = v24;
    v11 = v23 & 0x1F;
    v26 = v11;
    v25 = v23 & 0xE0;
    v13 = v25;
    LOWORD(v27) = v25;
    if ( v25 == 224 )
    {
      v7 = (unsigned int)(v7 - v24);
      if ( (unsigned int)v7 < 2 )
        bond::InputBuffer::EofException(v20, 2u);
      v13 = *(unsigned __int16 *)(v24 + v22);
      *((_DWORD *)v20 + 8) = v24 + 2;
      goto LABEL_23;
    }
    if ( v25 != 192 )
    {
      LOWORD(v13) = v25 >> 5;
LABEL_23:
      LOWORD(v27) = v13;
      goto LABEL_24;
    }
    bond::InputBuffer::Read(v20, (unsigned __int8 *)&v27);
    v13 = (unsigned __int16)v27;
LABEL_24:
    if ( (_WORD)v13 || v11 < 2 )
      break;
  }
LABEL_43:
  while ( v11 > 1 )
  {
    bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
    bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(*a1);
    v11 = v26;
  }
LABEL_9:
  if ( !*((_BYTE *)a1 + 8) )
  {
    while ( v11 )
    {
      if ( v11 != 1 )
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(*a1);
      v15 = *a1;
      v16 = *((unsigned int *)*a1 + 8);
      v17 = *((_DWORD *)*a1 + 6);
      if ( v17 == (_DWORD)v16 )
        bond::InputBuffer::EofException(*a1, 1u);
      v18 = *(_BYTE *)(v16 + *((_QWORD *)v15 + 2));
      *((_DWORD *)v15 + 8) = v16 + 1;
      v11 = v18 & 0x1F;
      v19 = v18 & 0xE0;
      LOWORD(v27) = v19;
      if ( v19 == 224 )
      {
        if ( (unsigned int)(v17 - (v16 + 1)) < 2 )
          bond::InputBuffer::EofException(v15, 2u);
        *((_DWORD *)v15 + 8) = v16 + 3;
      }
      else if ( v19 == 192 )
      {
        bond::InputBuffer::Read(v15, (unsigned __int8 *)&v27);
      }
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180003d6c  mov     [rsp-28h+arg_10], rbx
0x180003d71  mov     [rsp-28h+arg_8], rdx
0x180003d76  push    rbp
0x180003d77  push    rsi
0x180003d78  push    r12
0x180003d7a  push    r13
0x180003d7c  push    r14
0x180003d7e  mov     rbp, rsp
0x180003d81  sub     rsp, 40h
0x180003d85  mov     r14, r8
0x180003d88  mov     rsi, rcx
0x180003d8b  mov     r9, [rcx]
0x180003d8e  mov     r10d, [r9+20h]
0x180003d92  mov     edx, [r9+18h]
0x180003d96  cmp     edx, r10d
0x180003d99  jz      loc_180003F7F
0x180003d9f  mov     r11, [r9+10h]
0x180003da3  movzx   ecx, byte ptr [r10+r11]
0x180003da8  inc     r10d
0x180003dab  mov     [r9+20h], r10d
0x180003daf  mov     ebx, ecx
0x180003db1  and     ebx, 1Fh
0x180003db4  mov     [rbp+arg_0], ebx
0x180003db7  mov     r13d, 0E0h
0x180003dbd  and     cl, r13b
0x180003dc0  movzx   r8d, cl
0x180003dc4  mov     word ptr [rbp+arg_8], r8w
0x180003dc9  lea     r12d, [r13-20h]
0x180003dcd  cmp     r8w, r13w
0x180003dd1  jz      loc_180003F14
0x180003dd7  cmp     r8w, r12w
0x180003ddb  jz      loc_180003F9B
0x180003de1  shr     r8w, 5
0x180003de6  mov     word ptr [rbp+arg_8], r8w
0x180003deb  xor     eax, eax
0x180003ded  cmp     ax, r8w
0x180003df1  jnz     loc_180003F09
0x180003df7  cmp     ebx, 6
0x180003dfa  jz      loc_180003E84
0x180003e00  test    ebx, ebx
0x180003e02  jnz     loc_180003F47
0x180003e08  cmp     byte ptr [rsi+8], 0
0x180003e0c  jnz     short loc_180003E12
0x180003e0e  test    ebx, ebx
0x180003e10  jnz     short loc_180003E29
0x180003e12  xor     al, al
0x180003e14  mov     rbx, [rsp+40h+arg_10]
0x180003e1c  add     rsp, 40h
0x180003e20  pop     r14
0x180003e22  pop     r13
0x180003e24  pop     r12
0x180003e26  pop     rsi
0x180003e27  pop     rbp
0x180003e28  retn
0x180003e29  cmp     ebx, 1
0x180003e2c  jnz     loc_180004012
0x180003e32  mov     r8, [rsi]
0x180003e35  mov     r10d, [r8+20h]
0x180003e39  mov     r9d, [r8+18h]
0x180003e3d  cmp     r9d, r10d
0x180003e40  jz      loc_18000402F
0x180003e46  mov     rax, [r8+10h]
0x180003e4a  movzx   edx, byte ptr [r10+rax]
0x180003e4f  lea     eax, [r10+1]
0x180003e53  mov     [r8+20h], eax
0x180003e57  mov     ebx, edx
0x180003e59  and     ebx, 1Fh
0x180003e5c  and     dl, r13b
0x180003e5f  movzx   ecx, dl
0x180003e62  mov     word ptr [rbp+arg_8], cx
0x180003e66  cmp     cx, r13w
0x180003e6a  jz      loc_180003F2E
0x180003e70  cmp     cx, r12w
0x180003e74  jnz     short loc_180003E0E
0x180003e76  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180003e7a  mov     rcx, r8; this
0x180003e7d  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180003e82  jmp     short loc_180003E0E
0x180003e84  mov     rcx, [rsi]; this
0x180003e87  mov     [rbp+var_10], rcx
0x180003e8b  mov     [rbp+var_8], 0
0x180003e8f  mov     rdx, [r14+8]
0x180003e93  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180003e98  nop
0x180003e99  mov     r9, [rsi]
0x180003e9c  mov     r10d, [r9+20h]
0x180003ea0  mov     edx, [r9+18h]
0x180003ea4  cmp     edx, r10d
0x180003ea7  jz      loc_180003FD5
0x180003ead  mov     r11, [r9+10h]
0x180003eb1  movzx   ecx, byte ptr [r10+r11]
0x180003eb6  inc     r10d
0x180003eb9  mov     [r9+20h], r10d
0x180003ebd  mov     ebx, ecx
0x180003ebf  and     ebx, 1Fh
0x180003ec2  mov     [rbp+arg_0], ebx
0x180003ec5  and     cl, r13b
0x180003ec8  movzx   r8d, cl
0x180003ecc  mov     word ptr [rbp+arg_8], r8w
0x180003ed1  cmp     r8w, r13w
0x180003ed5  jz      loc_180003F65
0x180003edb  cmp     r8w, r12w
0x180003edf  jz      loc_180003FB1
0x180003ee5  shr     r8w, 5
0x180003eea  mov     word ptr [rbp+arg_8], r8w
0x180003eef  xor     eax, eax
0x180003ef1  cmp     ax, r8w
0x180003ef5  jb      loc_180004009
0x180003efb  cmp     ebx, 2
0x180003efe  jnb     loc_180003DEB
0x180003f04  jmp     loc_180004009
0x180003f09  jnb     loc_180003E00
0x180003f0f  jmp     loc_180004009
0x180003f14  sub     edx, r10d
0x180003f17  cmp     edx, 2
0x180003f1a  jb      short loc_180003F8D
0x180003f1c  movzx   r8d, word ptr [r10+r11]
0x180003f21  lea     eax, [r10+2]
0x180003f25  mov     [r9+20h], eax
0x180003f29  jmp     loc_180003DE6
0x180003f2e  sub     r9d, eax
0x180003f31  cmp     r9d, 2
0x180003f35  jb      loc_180004021
0x180003f3b  add     eax, 2
0x180003f3e  mov     [r8+20h], eax
0x180003f42  jmp     loc_180003E0E
0x180003f47  cmp     ebx, 1
0x180003f4a  jz      loc_180004009
0x180003f50  mov     [rsp+40h+var_20], r14
0x180003f55  mov     r9d, ebx
0x180003f58  mov     rcx, rsi
0x180003f5b  call    ??$UnknownFieldOrTypeMismatch@U?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@bond@@V?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@3@@?$DynamicParser@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@AEAA_NAEBU?$FieldTemplate@$0A@Uoptional_field_modifier@reflection@bond@@UNlmSignature@Nlm@Data@Windows@@_K$0A@$1?s_category_metadata@Schema@NlmSignature@Nlm@Data@Windows@@0UMetadata@bond@@B@reflection@1@GW4BondDataType@4_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@1@@Z; bond::DynamicParser<bond::CompactBinaryReader<bond::InputBuffer> &>::UnknownFieldOrTypeMismatch<bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata>,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>>(bond::reflection::FieldTemplate<0,bond::reflection::optional_field_modifier,Windows::Data::Nlm::NlmSignature,unsigned __int64,0,&bond::Metadata const Windows::Data::Nlm::NlmSignature::Schema::s_category_metadata> const &,ushort,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>> const &)
0x180003f60  jmp     loc_180003E99
0x180003f65  sub     edx, r10d
0x180003f68  cmp     edx, 2
0x180003f6b  jb      short loc_180003FC7
0x180003f6d  movzx   r8d, word ptr [r10+r11]
0x180003f72  lea     eax, [r10+2]
0x180003f76  mov     [r9+20h], eax
0x180003f7a  jmp     loc_180003EEA
0x180003f7f  mov     edx, 1; unsigned int
0x180003f84  mov     rcx, r9; this
0x180003f87  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003f8d  mov     edx, 2; unsigned int
0x180003f92  mov     rcx, r9; this
0x180003f95  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003f9b  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180003f9f  mov     rcx, r9; this
0x180003fa2  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180003fa7  movzx   r8d, word ptr [rbp+arg_8]
0x180003fac  jmp     loc_180003DEB
0x180003fb1  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180003fb5  mov     rcx, r9; this
0x180003fb8  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180003fbd  movzx   r8d, word ptr [rbp+arg_8]
0x180003fc2  jmp     loc_180003EEF
0x180003fc7  mov     edx, 2; unsigned int
0x180003fcc  mov     rcx, r9; this
0x180003fcf  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003fd5  mov     edx, 1; unsigned int
0x180003fda  mov     rcx, r9; this
0x180003fdd  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x180003fe3  cmp     ebx, 1
0x180003fe6  jz      loc_180003E08
0x180003fec  mov     edx, ebx
0x180003fee  mov     rcx, [rsi]; this
0x180003ff1  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180003ff6  lea     r8, [rbp+arg_8]
0x180003ffa  lea     rdx, [rbp+arg_0]
0x180003ffe  mov     rcx, [rsi]; this
0x180004001  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180004006  mov     ebx, [rbp+arg_0]
0x180004009  test    ebx, ebx
0x18000400b  jnz     short loc_180003FE3
0x18000400d  jmp     loc_180003E08
0x180004012  mov     edx, ebx
0x180004014  mov     rcx, [rsi]; this
0x180004017  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18000401c  jmp     loc_180003E32
0x180004021  mov     edx, 2; unsigned int
0x180004026  mov     rcx, r8; this
0x180004029  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000402f  mov     edx, 1; unsigned int
0x180004034  mov     rcx, r8; this
0x180004037  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
```
