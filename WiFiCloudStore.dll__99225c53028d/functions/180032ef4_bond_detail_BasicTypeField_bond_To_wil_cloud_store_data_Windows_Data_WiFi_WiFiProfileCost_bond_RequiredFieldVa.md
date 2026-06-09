# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x180032ef4`
- end: `0x1800331c1`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfileCost@WiFi@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `717`
- prototype: `char __fastcall(unsigned __int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `2`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800338d0`
- `0x18003396c`

## callees

- `0x1800031d4`
- `0x180019d80`
- `0x18001aa20`
- `0x180026ee0`
- `0x180026f0c`
- `0x18002ecb8`
- `0x18002fe40`
- `0x18002fe60`
- `0x18002fe80`
- `0x18002fea0`
- `0x18002fec0`
- `0x180032ef4`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfileCost>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        unsigned __int16 a1,
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
  __int64 v10; // rbx
  _QWORD *v11; // rbx
  __int64 v12; // rbx
  _QWORD *v13; // rbx
  __int64 v14; // rbx
  _QWORD *v15; // rbx
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  int v20; // r8d
  bond::InputBuffer *v22; // [rsp+20h] [rbp-10h] BYREF
  char v23; // [rsp+28h] [rbp-8h]
  unsigned int v24; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 > 8 )
  {
    v16 = a3 - 9;
    if ( v16 )
    {
      v17 = v16 - 5;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 && (v19 = v18 - 1) != 0 && (v20 = v19 - 1) != 0 )
        {
          if ( v20 == 1 )
          {
            v22 = a5;
            v23 = 1;
            bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
          }
        }
        else
        {
          v22 = a5;
          v23 = 1;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
        }
      }
      else
      {
        v22 = a5;
        v23 = 1;
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
      }
    }
    else
    {
      v22 = a5;
      v23 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
    }
  }
  else
  {
    if ( a3 == 8 )
    {
      v22 = a5;
      v23 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
      return 0;
    }
    v5 = a3 - 2;
    if ( !v5 )
    {
      v22 = a5;
      v23 = 1;
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
      return 0;
    }
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
              v22 = a5;
              v23 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
            }
            return 0;
          }
          v22 = a5;
          v23 = 1;
          if ( a1 <= 1u )
          {
            v23 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(a5);
          }
        }
        else
        {
          v22 = a5;
          v23 = 1;
          if ( a1 == 1 )
          {
            v10 = *(_QWORD *)(a4 + 8);
            v24 = 0;
            v23 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5, &v24);
            *(_QWORD *)(v10 + 8) = v24;
          }
          else if ( !a1 )
          {
            v11 = *(_QWORD **)(a4 + 8);
            v24 = 0;
            v23 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5, &v24);
            *v11 = v24;
          }
        }
      }
      else
      {
        v22 = a5;
        v23 = 1;
        if ( a1 == 1 )
        {
          v12 = *(_QWORD *)(a4 + 8);
          LOWORD(v24) = 0;
          v23 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v24);
          *(_QWORD *)(v12 + 8) = (unsigned __int16)v24;
        }
        else if ( !a1 )
        {
          v13 = *(_QWORD **)(a4 + 8);
          LOWORD(v24) = 0;
          v23 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v24);
          *v13 = (unsigned __int16)v24;
        }
      }
      bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
      return 0;
    }
    v22 = a5;
    v23 = 1;
    if ( a1 == 1 )
    {
      v14 = *(_QWORD *)(a4 + 8);
      LOBYTE(v24) = 0;
      v23 = 0;
      bond::InputBuffer::Read(a5, (unsigned __int8 *)&v24);
      *(_QWORD *)(v14 + 8) = (unsigned __int8)v24;
    }
    else if ( !a1 )
    {
      v15 = *(_QWORD **)(a4 + 8);
      LOBYTE(v24) = 0;
      v23 = 0;
      bond::InputBuffer::Read(a5, (unsigned __int8 *)&v24);
      *v15 = (unsigned __int8)v24;
    }
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v22);
  }
  return 0;
}

```

## disassembly

```asm
0x180032ef4  mov     [rsp-8+arg_0], rbx
0x180032ef9  push    rbp
0x180032efa  mov     rbp, rsp
0x180032efd  sub     rsp, 30h
0x180032f01  cmp     r8d, 8
0x180032f05  jg      loc_180033100
0x180032f0b  jz      loc_1800330E6
0x180032f11  sub     r8d, 2
0x180032f15  jz      loc_1800330CC
0x180032f1b  sub     r8d, 1
0x180032f1f  jz      loc_180033068
0x180032f25  sub     r8d, 1
0x180032f29  jz      loc_180033002
0x180032f2f  sub     r8d, 1
0x180032f33  jz      short loc_180032FA0
0x180032f35  sub     r8d, 1
0x180032f39  jz      short loc_180032F5F
0x180032f3b  cmp     r8d, 1
0x180032f3f  jnz     loc_1800331B4
0x180032f45  mov     rax, [rbp+arg_20]
0x180032f49  mov     [rbp+var_10], rax
0x180032f4d  mov     [rbp+var_8], r8b
0x180032f51  lea     rcx, [rbp+var_10]
0x180032f55  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180032f5a  jmp     loc_1800331B4
0x180032f5f  mov     r8, [rbp+arg_20]
0x180032f63  mov     [rbp+var_10], r8
0x180032f67  mov     [rbp+var_8], 1
0x180032f6b  xor     eax, eax
0x180032f6d  cmp     cx, 1
0x180032f71  jnz     short loc_180032F7D
0x180032f73  mov     rdx, [r9+8]
0x180032f77  add     rdx, 8
0x180032f7b  jmp     short loc_180032F86
0x180032f7d  test    cx, cx
0x180032f80  jnz     short loc_180032F92
0x180032f82  mov     rdx, [r9+8]
0x180032f86  mov     [rbp+var_8], al
0x180032f89  mov     rcx, r8; this
0x180032f8c  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180032f91  nop
0x180032f92  lea     rcx, [rbp+var_10]
0x180032f96  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180032f9b  jmp     loc_1800331B4
0x180032fa0  mov     r8, [rbp+arg_20]
0x180032fa4  mov     [rbp+var_10], r8
0x180032fa8  mov     [rbp+var_8], 1
0x180032fac  xor     eax, eax
0x180032fae  cmp     cx, 1
0x180032fb2  jnz     short loc_180032FD3
0x180032fb4  mov     rbx, [r9+8]
0x180032fb8  mov     [rbp+arg_10], eax
0x180032fbb  mov     [rbp+var_8], al
0x180032fbe  lea     rdx, [rbp+arg_10]
0x180032fc2  mov     rcx, r8
0x180032fc5  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180032fca  mov     eax, [rbp+arg_10]
0x180032fcd  mov     [rbx+8], rax
0x180032fd1  jmp     short loc_180032FF4
0x180032fd3  test    cx, cx
0x180032fd6  jnz     short loc_180032FF4
0x180032fd8  mov     rbx, [r9+8]
0x180032fdc  mov     [rbp+arg_10], eax
0x180032fdf  mov     [rbp+var_8], al
0x180032fe2  lea     rdx, [rbp+arg_10]
0x180032fe6  mov     rcx, r8
0x180032fe9  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180032fee  mov     eax, [rbp+arg_10]
0x180032ff1  mov     [rbx], rax
0x180032ff4  lea     rcx, [rbp+var_10]
0x180032ff8  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180032ffd  jmp     loc_1800331B4
0x180033002  mov     r8, [rbp+arg_20]
0x180033006  mov     [rbp+var_10], r8
0x18003300a  mov     [rbp+var_8], 1
0x18003300e  xor     eax, eax
0x180033010  cmp     cx, 1
0x180033014  jnz     short loc_180033037
0x180033016  mov     rbx, [r9+8]
0x18003301a  mov     word ptr [rbp+arg_10], ax
0x18003301e  mov     [rbp+var_8], al
0x180033021  lea     rdx, [rbp+arg_10]
0x180033025  mov     rcx, r8
0x180033028  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18003302d  movzx   eax, word ptr [rbp+arg_10]
0x180033031  mov     [rbx+8], rax
0x180033035  jmp     short loc_18003305A
0x180033037  test    cx, cx
0x18003303a  jnz     short loc_18003305A
0x18003303c  mov     rbx, [r9+8]
0x180033040  mov     word ptr [rbp+arg_10], ax
0x180033044  mov     [rbp+var_8], al
0x180033047  lea     rdx, [rbp+arg_10]
0x18003304b  mov     rcx, r8
0x18003304e  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x180033053  movzx   eax, word ptr [rbp+arg_10]
0x180033057  mov     [rbx], rax
0x18003305a  lea     rcx, [rbp+var_10]
0x18003305e  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180033063  jmp     loc_1800331B4
0x180033068  mov     r8, [rbp+arg_20]
0x18003306c  mov     [rbp+var_10], r8
0x180033070  mov     [rbp+var_8], 1
0x180033074  xor     eax, eax
0x180033076  cmp     cx, 1
0x18003307a  jnz     short loc_18003309C
0x18003307c  mov     rbx, [r9+8]
0x180033080  mov     byte ptr [rbp+arg_10], al
0x180033083  mov     [rbp+var_8], al
0x180033086  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18003308a  mov     rcx, r8; this
0x18003308d  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180033092  movzx   eax, byte ptr [rbp+arg_10]
0x180033096  mov     [rbx+8], rax
0x18003309a  jmp     short loc_1800330BE
0x18003309c  test    cx, cx
0x18003309f  jnz     short loc_1800330BE
0x1800330a1  mov     rbx, [r9+8]
0x1800330a5  mov     byte ptr [rbp+arg_10], al
0x1800330a8  mov     [rbp+var_8], al
0x1800330ab  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x1800330af  mov     rcx, r8; this
0x1800330b2  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x1800330b7  movzx   eax, byte ptr [rbp+arg_10]
0x1800330bb  mov     [rbx], rax
0x1800330be  lea     rcx, [rbp+var_10]
0x1800330c2  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800330c7  jmp     loc_1800331B4
0x1800330cc  mov     rax, [rbp+arg_20]
0x1800330d0  mov     [rbp+var_10], rax
0x1800330d4  mov     [rbp+var_8], 1
0x1800330d8  lea     rcx, [rbp+var_10]
0x1800330dc  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800330e1  jmp     loc_1800331B4
0x1800330e6  mov     rax, [rbp+arg_20]
0x1800330ea  mov     [rbp+var_10], rax
0x1800330ee  mov     [rbp+var_8], 1
0x1800330f2  lea     rcx, [rbp+var_10]
0x1800330f6  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800330fb  jmp     loc_1800331B4
0x180033100  sub     r8d, 9
0x180033104  jz      loc_18003319F
0x18003310a  sub     r8d, 5
0x18003310e  jz      short loc_180033188
0x180033110  sub     r8d, 1
0x180033114  jz      short loc_180033171
0x180033116  sub     r8d, 1
0x18003311a  jz      short loc_18003315A
0x18003311c  sub     r8d, 1
0x180033120  jz      short loc_180033143
0x180033122  cmp     r8d, 1
0x180033126  jnz     loc_1800331B4
0x18003312c  mov     rax, [rbp+arg_20]
0x180033130  mov     [rbp+var_10], rax
0x180033134  mov     [rbp+var_8], r8b
0x180033138  lea     rcx, [rbp+var_10]
0x18003313c  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180033141  jmp     short loc_1800331B4
0x180033143  mov     rax, [rbp+arg_20]
0x180033147  mov     [rbp+var_10], rax
0x18003314b  mov     [rbp+var_8], 1
0x18003314f  lea     rcx, [rbp+var_10]
0x180033153  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180033158  jmp     short loc_1800331B4
0x18003315a  mov     rax, [rbp+arg_20]
0x18003315e  mov     [rbp+var_10], rax
0x180033162  mov     [rbp+var_8], 1
0x180033166  lea     rcx, [rbp+var_10]
0x18003316a  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18003316f  jmp     short loc_1800331B4
0x180033171  mov     rax, [rbp+arg_20]
0x180033175  mov     [rbp+var_10], rax
0x180033179  mov     [rbp+var_8], 1
0x18003317d  lea     rcx, [rbp+var_10]
0x180033181  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180033186  jmp     short loc_1800331B4
0x180033188  mov     rax, [rbp+arg_20]
0x18003318c  mov     [rbp+var_10], rax
0x180033190  mov     [rbp+var_8], 1
0x180033194  lea     rcx, [rbp+var_10]
0x180033198  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18003319d  jmp     short loc_1800331B4
0x18003319f  mov     rax, [rbp+arg_20]
0x1800331a3  mov     [rbp+var_10], rax
0x1800331a7  mov     [rbp+var_8], 1
0x1800331ab  lea     rcx, [rbp+var_10]
0x1800331af  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800331b4  xor     al, al
0x1800331b6  mov     rbx, [rsp+30h+arg_0]
0x1800331bb  add     rsp, 30h
0x1800331bf  pop     rbp
0x1800331c0  retn
```
