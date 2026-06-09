# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x180017910`
- end: `0x180017aeb`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UFocusSessionOffTheme@Shell@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `475`
- prototype: ``
- caller_count: `7`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180018608`
- `0x180018658`
- `0x1800186a8`
- `0x1800186f8`
- `0x180018748`
- `0x180018798`
- `0x1800187e8`

## callees

- `0x18001357c`
- `0x18001359c`
- `0x1800135bc`
- `0x1800135dc`
- `0x1800135fc`
- `0x18001361c`
- `0x18001363c`
- `0x180017910`
- `0x180019860`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Shell::FocusSessionOffTheme>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        unsigned __int16 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5)
{
  int v5; // r8d
  int v6; // r8d
  int v7; // r8d
  int v8; // r8d
  int v9; // r8d
  char v10; // bl
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  __int64 v17; // [rsp+20h] [rbp-10h] BYREF
  char v18; // [rsp+28h] [rbp-8h]

  if ( a3 <= 8 )
  {
    if ( a3 == 8 )
    {
      v17 = a5;
      v18 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      return 0;
    }
    v5 = a3 - 2;
    if ( !v5 )
    {
      v17 = a5;
      v18 = 1;
      v10 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64 *))___dee754617986e5828f4c19a6433c5ff2_)(
              a4,
              a2,
              a1,
              &v17);
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
      return v10;
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
              v17 = a5;
              v18 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
            }
            return 0;
          }
        }
      }
      goto LABEL_10;
    }
LABEL_11:
    v17 = a5;
    v18 = 1;
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
    return 0;
  }
  v12 = a3 - 9;
  if ( !v12 )
  {
    v17 = a5;
    v18 = 1;
    bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
    return 0;
  }
  v13 = v12 - 5;
  if ( !v13 )
    goto LABEL_11;
  v14 = v13 - 1;
  if ( v14 )
  {
    v15 = v14 - 1;
    if ( v15 )
    {
      v16 = v15 - 1;
      if ( v16 )
      {
        if ( v16 == 1 )
        {
          v17 = a5;
          v18 = 1;
          bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
        }
        return 0;
      }
    }
  }
LABEL_10:
  v17 = a5;
  v18 = 1;
  bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v17);
  return 0;
}

```

## disassembly

```asm
0x180017910  mov     [rsp-8+arg_0], rbx
0x180017915  push    rbp
0x180017916  mov     rbp, rsp
0x180017919  sub     rsp, 30h
0x18001791d  mov     r10, r9
0x180017920  cmp     r8d, 8
0x180017924  jg      loc_180017A2A
0x18001792a  jz      loc_180017A10
0x180017930  sub     r8d, 2
0x180017934  jz      loc_1800179E2
0x18001793a  sub     r8d, 1
0x18001793e  jz      loc_1800179C8
0x180017944  sub     r8d, 1
0x180017948  jz      short loc_1800179AE
0x18001794a  sub     r8d, 1
0x18001794e  jz      short loc_180017994
0x180017950  sub     r8d, 1
0x180017954  jz      short loc_18001797A
0x180017956  cmp     r8d, 1
0x18001795a  jnz     loc_180017ADE
0x180017960  mov     rax, [rbp+arg_20]
0x180017964  mov     [rbp+var_10], rax
0x180017968  mov     [rbp+var_8], r8b
0x18001796c  lea     rcx, [rbp+var_10]
0x180017970  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017975  jmp     loc_180017ADE
0x18001797a  mov     rax, [rbp+arg_20]
0x18001797e  mov     [rbp+var_10], rax
0x180017982  mov     [rbp+var_8], 1
0x180017986  lea     rcx, [rbp+var_10]
0x18001798a  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001798f  jmp     loc_180017ADE
0x180017994  mov     rax, [rbp+arg_20]
0x180017998  mov     [rbp+var_10], rax
0x18001799c  mov     [rbp+var_8], 1
0x1800179a0  lea     rcx, [rbp+var_10]
0x1800179a4  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800179a9  jmp     loc_180017ADE
0x1800179ae  mov     rax, [rbp+arg_20]
0x1800179b2  mov     [rbp+var_10], rax
0x1800179b6  mov     [rbp+var_8], 1
0x1800179ba  lea     rcx, [rbp+var_10]
0x1800179be  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800179c3  jmp     loc_180017ADE
0x1800179c8  mov     rax, [rbp+arg_20]
0x1800179cc  mov     [rbp+var_10], rax
0x1800179d0  mov     [rbp+var_8], 1
0x1800179d4  lea     rcx, [rbp+var_10]
0x1800179d8  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x1800179dd  jmp     loc_180017ADE
0x1800179e2  mov     rax, [rbp+arg_20]
0x1800179e6  mov     [rbp+var_10], rax
0x1800179ea  mov     [rbp+var_8], 1
0x1800179ee  lea     r9, [rbp+var_10]
0x1800179f2  movzx   r8d, cx
0x1800179f6  mov     rcx, r10
0x1800179f9  call    ??@dee754617986e5828f4c19a6433c5ff2@
0x1800179fe  mov     bl, al
0x180017a00  lea     rcx, [rbp+var_10]
0x180017a04  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017a09  mov     al, bl
0x180017a0b  jmp     loc_180017AE0
0x180017a10  mov     rax, [rbp+arg_20]
0x180017a14  mov     [rbp+var_10], rax
0x180017a18  mov     [rbp+var_8], 1
0x180017a1c  lea     rcx, [rbp+var_10]
0x180017a20  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017a25  jmp     loc_180017ADE
0x180017a2a  sub     r8d, 9
0x180017a2e  jz      loc_180017AC9
0x180017a34  sub     r8d, 5
0x180017a38  jz      short loc_180017AB2
0x180017a3a  sub     r8d, 1
0x180017a3e  jz      short loc_180017A9B
0x180017a40  sub     r8d, 1
0x180017a44  jz      short loc_180017A84
0x180017a46  sub     r8d, 1
0x180017a4a  jz      short loc_180017A6D
0x180017a4c  cmp     r8d, 1
0x180017a50  jnz     loc_180017ADE
0x180017a56  mov     rax, [rbp+arg_20]
0x180017a5a  mov     [rbp+var_10], rax
0x180017a5e  mov     [rbp+var_8], r8b
0x180017a62  lea     rcx, [rbp+var_10]
0x180017a66  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017a6b  jmp     short loc_180017ADE
0x180017a6d  mov     rax, [rbp+arg_20]
0x180017a71  mov     [rbp+var_10], rax
0x180017a75  mov     [rbp+var_8], 1
0x180017a79  lea     rcx, [rbp+var_10]
0x180017a7d  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017a82  jmp     short loc_180017ADE
0x180017a84  mov     rax, [rbp+arg_20]
0x180017a88  mov     [rbp+var_10], rax
0x180017a8c  mov     [rbp+var_8], 1
0x180017a90  lea     rcx, [rbp+var_10]
0x180017a94  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017a99  jmp     short loc_180017ADE
0x180017a9b  mov     rax, [rbp+arg_20]
0x180017a9f  mov     [rbp+var_10], rax
0x180017aa3  mov     [rbp+var_8], 1
0x180017aa7  lea     rcx, [rbp+var_10]
0x180017aab  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017ab0  jmp     short loc_180017ADE
0x180017ab2  mov     rax, [rbp+arg_20]
0x180017ab6  mov     [rbp+var_10], rax
0x180017aba  mov     [rbp+var_8], 1
0x180017abe  lea     rcx, [rbp+var_10]
0x180017ac2  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017ac7  jmp     short loc_180017ADE
0x180017ac9  mov     rax, [rbp+arg_20]
0x180017acd  mov     [rbp+var_10], rax
0x180017ad1  mov     [rbp+var_8], 1
0x180017ad5  lea     rcx, [rbp+var_10]
0x180017ad9  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180017ade  xor     al, al
0x180017ae0  mov     rbx, [rsp+30h+arg_0]
0x180017ae5  add     rsp, 30h
0x180017ae9  pop     rbp
0x180017aea  retn
```
