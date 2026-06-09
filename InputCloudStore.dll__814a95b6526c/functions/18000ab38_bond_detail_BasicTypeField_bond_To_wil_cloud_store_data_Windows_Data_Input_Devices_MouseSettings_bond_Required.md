# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000ab38`
- end: `0x18000ae1e`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UMouseSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `742`
- prototype: `char __fastcall(__int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `4`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180010f80`
- `0x180011160`
- `0x1800112f0`
- `0x1800119bc`

## callees

- `0x18000ab38`
- `0x18000f934`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`
- `0x18001f55c`
- `0x180020960`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::MouseSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        __int16 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        bond::InputBuffer *a5)
{
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  int v10; // r8d
  __int64 v11; // rdx
  __int64 v12; // rbx
  _WORD *v13; // rbx
  bond::InputBuffer *v14; // r9
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  bond::InputBuffer *v21; // [rsp+20h] [rbp-10h] BYREF
  char v22; // [rsp+28h] [rbp-8h]
  unsigned __int8 v23; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 > 8 )
  {
    v15 = a3 - 9;
    if ( !v15 )
    {
      v21 = a5;
      v22 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
      return 0;
    }
    v16 = v15 - 5;
    if ( !v16 )
    {
      v21 = a5;
      v22 = 1;
      bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
      return 0;
    }
    v17 = v16 - 1;
    if ( !v17 )
      goto LABEL_40;
    v18 = v17 - 1;
    if ( !v18 )
      goto LABEL_40;
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_40;
    if ( v19 == 1 )
    {
      v21 = a5;
      v22 = 1;
      bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    }
    return 0;
  }
  if ( a3 == 8 )
  {
    v21 = a5;
    v22 = 1;
    bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
    return 0;
  }
  v6 = a3 - 2;
  if ( !v6 )
  {
    v14 = a5;
    v21 = a5;
    v22 = 1;
    if ( a1 == 3 )
    {
      v22 = 0;
      if ( *((_DWORD *)a5 + 6) != *((_DWORD *)a5 + 8) )
      {
        *(_BYTE *)(*(_QWORD *)(a4 + 8) + 6LL) = *(_BYTE *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
LABEL_30:
        ++*((_DWORD *)v14 + 8);
        goto LABEL_31;
      }
    }
    else
    {
      if ( a1 != 1 )
      {
LABEL_31:
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
        return 0;
      }
      v22 = 0;
      if ( *((_DWORD *)a5 + 6) != *((_DWORD *)a5 + 8) )
      {
        *(_BYTE *)(*(_QWORD *)(a4 + 8) + 2LL) = *(_BYTE *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
        goto LABEL_30;
      }
    }
    bond::InputBuffer::EofException(a5, 1u);
  }
  v7 = v6 - 1;
  if ( v7 )
  {
    v8 = v7 - 1;
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( v9 )
      {
        v10 = v9 - 1;
        if ( v10 )
        {
          if ( v10 == 1 )
          {
            v21 = a5;
            v22 = 1;
            bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
          }
          return 0;
        }
      }
LABEL_40:
      v21 = a5;
      v22 = 1;
      bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
      return 0;
    }
    v21 = a5;
    v22 = 1;
    if ( a1 == 2 )
    {
      v11 = *(_QWORD *)(a4 + 8) + 4LL;
    }
    else
    {
      if ( a1 )
      {
LABEL_17:
        bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
        return 0;
      }
      v11 = *(_QWORD *)(a4 + 8);
    }
    v22 = 0;
    bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, v11);
    goto LABEL_17;
  }
  v21 = a5;
  v22 = 1;
  if ( a1 == 2 )
  {
    v12 = *(_QWORD *)(a4 + 8);
    v23 = 0;
    v22 = 0;
    bond::InputBuffer::Read(a5, &v23);
    *(_WORD *)(v12 + 4) = v23;
  }
  else if ( !a1 )
  {
    v13 = *(_WORD **)(a4 + 8);
    v23 = 0;
    v22 = 0;
    bond::InputBuffer::Read(a5, &v23);
    *v13 = v23;
  }
  bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v21);
  return 0;
}

```

## disassembly

```asm
0x18000ab38  mov     [rsp-8+arg_0], rbx
0x18000ab3d  push    rbp
0x18000ab3e  mov     rbp, rsp
0x18000ab41  sub     rsp, 30h
0x18000ab45  mov     r10, r9
0x18000ab48  cmp     r8d, 8
0x18000ab4c  jg      loc_18000AD38
0x18000ab52  jz      loc_18000AD18
0x18000ab58  mov     edx, 2
0x18000ab5d  sub     r8d, edx
0x18000ab60  jz      loc_18000AC94
0x18000ab66  sub     r8d, 1
0x18000ab6a  jz      loc_18000AC2B
0x18000ab70  sub     r8d, 1
0x18000ab74  jz      short loc_18000ABE6
0x18000ab76  sub     r8d, 1
0x18000ab7a  jz      short loc_18000ABC6
0x18000ab7c  sub     r8d, 1
0x18000ab80  jz      short loc_18000ABA6
0x18000ab82  cmp     r8d, 1
0x18000ab86  jnz     loc_18000AE11
0x18000ab8c  mov     rax, [rbp+arg_20]
0x18000ab90  mov     [rbp+var_10], rax
0x18000ab94  mov     [rbp+var_8], r8b
0x18000ab98  lea     rcx, [rbp+var_10]
0x18000ab9c  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000aba1  jmp     loc_18000AE11
0x18000aba6  mov     rax, [rbp+arg_20]
0x18000abaa  mov     [rbp+var_10], rax
0x18000abae  mov     r8d, 1
0x18000abb4  mov     [rbp+var_8], r8b
0x18000abb8  lea     rcx, [rbp+var_10]
0x18000abbc  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000abc1  jmp     loc_18000AE11
0x18000abc6  mov     rax, [rbp+arg_20]
0x18000abca  mov     [rbp+var_10], rax
0x18000abce  mov     r8d, 1
0x18000abd4  mov     [rbp+var_8], r8b
0x18000abd8  lea     rcx, [rbp+var_10]
0x18000abdc  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000abe1  jmp     loc_18000AE11
0x18000abe6  mov     rax, [rbp+arg_20]
0x18000abea  mov     [rbp+var_10], rax
0x18000abee  mov     r8d, 1
0x18000abf4  mov     [rbp+var_8], r8b
0x18000abf8  cmp     cx, dx
0x18000abfb  jnz     short loc_18000AC07
0x18000abfd  mov     rdx, [r9+8]
0x18000ac01  add     rdx, 4
0x18000ac05  jmp     short loc_18000AC10
0x18000ac07  test    cx, cx
0x18000ac0a  jnz     short loc_18000AC1D
0x18000ac0c  mov     rdx, [r9+8]
0x18000ac10  mov     [rbp+var_8], 0
0x18000ac14  mov     rcx, rax
0x18000ac17  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000ac1c  nop
0x18000ac1d  lea     rcx, [rbp+var_10]
0x18000ac21  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ac26  jmp     loc_18000AE11
0x18000ac2b  mov     rax, [rbp+arg_20]
0x18000ac2f  mov     [rbp+var_10], rax
0x18000ac33  mov     r8d, 1
0x18000ac39  mov     [rbp+var_8], r8b
0x18000ac3d  cmp     cx, dx
0x18000ac40  jnz     short loc_18000AC64
0x18000ac42  mov     rbx, [r9+8]
0x18000ac46  mov     [rbp+arg_10], 0
0x18000ac4a  mov     [rbp+var_8], 0
0x18000ac4e  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000ac52  mov     rcx, rax; this
0x18000ac55  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000ac5a  movzx   eax, [rbp+arg_10]
0x18000ac5e  mov     [rbx+4], ax
0x18000ac62  jmp     short loc_18000AC86
0x18000ac64  test    cx, cx
0x18000ac67  jnz     short loc_18000AC86
0x18000ac69  mov     rbx, [r9+8]
0x18000ac6d  mov     [rbp+arg_10], cl
0x18000ac70  mov     [rbp+var_8], cl
0x18000ac73  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000ac77  mov     rcx, rax; this
0x18000ac7a  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000ac7f  movzx   eax, [rbp+arg_10]
0x18000ac83  mov     [rbx], ax
0x18000ac86  lea     rcx, [rbp+var_10]
0x18000ac8a  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ac8f  jmp     loc_18000AE11
0x18000ac94  mov     r9, [rbp+arg_20]
0x18000ac98  mov     [rbp+var_10], r9
0x18000ac9c  mov     r8d, 1
0x18000aca2  mov     [rbp+var_8], r8b
0x18000aca6  cmp     cx, 3
0x18000acaa  jnz     short loc_18000ACD1
0x18000acac  mov     [rbp+var_8], 0
0x18000acb0  mov     eax, [r9+18h]
0x18000acb4  sub     eax, [r9+20h]
0x18000acb8  cmp     eax, r8d
0x18000acbb  jb      short loc_18000ACE8
0x18000acbd  mov     edx, [r9+20h]
0x18000acc1  mov     rax, [r9+10h]
0x18000acc5  mov     rcx, [r10+8]
0x18000acc9  mov     al, [rdx+rax]
0x18000accc  mov     [rcx+6], al
0x18000accf  jmp     short loc_18000AD06
0x18000acd1  cmp     cx, r8w
0x18000acd5  jnz     short loc_18000AD0A
0x18000acd7  mov     [rbp+var_8], 0
0x18000acdb  mov     eax, [r9+18h]
0x18000acdf  sub     eax, [r9+20h]
0x18000ace3  cmp     eax, r8d
0x18000ace6  jnb     short loc_18000ACF4
0x18000ace8  mov     edx, r8d; unsigned int
0x18000aceb  mov     rcx, r9; this
0x18000acee  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000acf4  mov     edx, [r9+20h]
0x18000acf8  mov     rax, [r9+10h]
0x18000acfc  mov     rcx, [r10+8]
0x18000ad00  mov     al, [rdx+rax]
0x18000ad03  mov     [rcx+2], al
0x18000ad06  add     [r9+20h], r8d
0x18000ad0a  lea     rcx, [rbp+var_10]
0x18000ad0e  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ad13  jmp     loc_18000AE11
0x18000ad18  mov     rax, [rbp+arg_20]
0x18000ad1c  mov     [rbp+var_10], rax
0x18000ad20  mov     r8d, 1
0x18000ad26  mov     [rbp+var_8], r8b
0x18000ad2a  lea     rcx, [rbp+var_10]
0x18000ad2e  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ad33  jmp     loc_18000AE11
0x18000ad38  sub     r8d, 9
0x18000ad3c  jz      loc_18000ADF6
0x18000ad42  sub     r8d, 5
0x18000ad46  jz      loc_18000ADD9
0x18000ad4c  sub     r8d, 1
0x18000ad50  jz      short loc_18000ADBC
0x18000ad52  sub     r8d, 1
0x18000ad56  jz      short loc_18000AD9F
0x18000ad58  sub     r8d, 1
0x18000ad5c  jz      short loc_18000AD82
0x18000ad5e  cmp     r8d, 1
0x18000ad62  jnz     loc_18000AE11
0x18000ad68  mov     rax, [rbp+arg_20]
0x18000ad6c  mov     [rbp+var_10], rax
0x18000ad70  mov     [rbp+var_8], r8b
0x18000ad74  lea     rcx, [rbp+var_10]
0x18000ad78  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ad7d  jmp     loc_18000AE11
0x18000ad82  mov     rax, [rbp+arg_20]
0x18000ad86  mov     [rbp+var_10], rax
0x18000ad8a  mov     r8d, 1
0x18000ad90  mov     [rbp+var_8], r8b
0x18000ad94  lea     rcx, [rbp+var_10]
0x18000ad98  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ad9d  jmp     short loc_18000AE11
0x18000ad9f  mov     rax, [rbp+arg_20]
0x18000ada3  mov     [rbp+var_10], rax
0x18000ada7  mov     r8d, 1
0x18000adad  mov     [rbp+var_8], r8b
0x18000adb1  lea     rcx, [rbp+var_10]
0x18000adb5  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000adba  jmp     short loc_18000AE11
0x18000adbc  mov     rax, [rbp+arg_20]
0x18000adc0  mov     [rbp+var_10], rax
0x18000adc4  mov     r8d, 1
0x18000adca  mov     [rbp+var_8], r8b
0x18000adce  lea     rcx, [rbp+var_10]
0x18000add2  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000add7  jmp     short loc_18000AE11
0x18000add9  mov     rax, [rbp+arg_20]
0x18000addd  mov     [rbp+var_10], rax
0x18000ade1  mov     r8d, 1
0x18000ade7  mov     [rbp+var_8], r8b
0x18000adeb  lea     rcx, [rbp+var_10]
0x18000adef  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000adf4  jmp     short loc_18000AE11
0x18000adf6  mov     rax, [rbp+arg_20]
0x18000adfa  mov     [rbp+var_10], rax
0x18000adfe  mov     r8d, 1
0x18000ae04  mov     [rbp+var_8], r8b
0x18000ae08  lea     rcx, [rbp+var_10]
0x18000ae0c  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ae11  xor     al, al
0x18000ae13  mov     rbx, [rsp+30h+arg_0]
0x18000ae18  add     rsp, 30h
0x18000ae1c  pop     rbp
0x18000ae1d  retn
```
