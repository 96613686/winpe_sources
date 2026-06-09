# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000b79c`
- end: `0x18000ba04`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `616`
- prototype: `char __fastcall(__int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800110c0`
- `0x180011b34`

## callees

- `0x18000b79c`
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
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
        __int16 a1,
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

  if ( a3 <= 8 )
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
    v17 = 1;
    if ( a1 == 1 )
    {
      v17 = 0;
      if ( *((_DWORD *)a5 + 6) != *((_DWORD *)a5 + 8) )
      {
        *(_BYTE *)(*(_QWORD *)(a4 + 8) + 1LL) = *(_BYTE *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
LABEL_19:
        ++*((_DWORD *)a5 + 8);
        goto LABEL_20;
      }
    }
    else
    {
      if ( a1 )
      {
LABEL_20:
        bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v16);
        return 0;
      }
      v17 = 0;
      if ( *((_DWORD *)a5 + 6) != *((_DWORD *)a5 + 8) )
      {
        **(_BYTE **)(a4 + 8) = *(_BYTE *)(*((unsigned int *)a5 + 8) + *((_QWORD *)a5 + 2));
        goto LABEL_19;
      }
    }
    bond::InputBuffer::EofException(a5, 1u);
  }
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
  return 0;
}

```

## disassembly

```asm
0x18000b79c  push    rbp
0x18000b79e  mov     rbp, rsp
0x18000b7a1  sub     rsp, 30h
0x18000b7a5  mov     r10, r9
0x18000b7a8  cmp     r8d, 8
0x18000b7ac  jg      loc_18000B923
0x18000b7b2  jz      loc_18000B903
0x18000b7b8  sub     r8d, 2
0x18000b7bc  jz      loc_18000B882
0x18000b7c2  sub     r8d, 1
0x18000b7c6  jz      loc_18000B862
0x18000b7cc  sub     r8d, 1
0x18000b7d0  jz      short loc_18000B842
0x18000b7d2  sub     r8d, 1
0x18000b7d6  jz      short loc_18000B822
0x18000b7d8  sub     r8d, 1
0x18000b7dc  jz      short loc_18000B802
0x18000b7de  cmp     r8d, 1
0x18000b7e2  jnz     loc_18000B9FC
0x18000b7e8  mov     rax, [rbp+arg_20]
0x18000b7ec  mov     [rbp+var_10], rax
0x18000b7f0  mov     [rbp+var_8], r8b
0x18000b7f4  lea     rcx, [rbp+var_10]
0x18000b7f8  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b7fd  jmp     loc_18000B9FC
0x18000b802  mov     rax, [rbp+arg_20]
0x18000b806  mov     [rbp+var_10], rax
0x18000b80a  mov     r8d, 1
0x18000b810  mov     [rbp+var_8], r8b
0x18000b814  lea     rcx, [rbp+var_10]
0x18000b818  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b81d  jmp     loc_18000B9FC
0x18000b822  mov     rax, [rbp+arg_20]
0x18000b826  mov     [rbp+var_10], rax
0x18000b82a  mov     r8d, 1
0x18000b830  mov     [rbp+var_8], r8b
0x18000b834  lea     rcx, [rbp+var_10]
0x18000b838  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b83d  jmp     loc_18000B9FC
0x18000b842  mov     rax, [rbp+arg_20]
0x18000b846  mov     [rbp+var_10], rax
0x18000b84a  mov     r8d, 1
0x18000b850  mov     [rbp+var_8], r8b
0x18000b854  lea     rcx, [rbp+var_10]
0x18000b858  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b85d  jmp     loc_18000B9FC
0x18000b862  mov     rax, [rbp+arg_20]
0x18000b866  mov     [rbp+var_10], rax
0x18000b86a  mov     r8d, 1
0x18000b870  mov     [rbp+var_8], r8b
0x18000b874  lea     rcx, [rbp+var_10]
0x18000b878  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b87d  jmp     loc_18000B9FC
0x18000b882  mov     r9, [rbp+arg_20]
0x18000b886  mov     [rbp+var_10], r9
0x18000b88a  mov     r8d, 1
0x18000b890  mov     [rbp+var_8], r8b
0x18000b894  cmp     cx, r8w
0x18000b898  jnz     short loc_18000B8BF
0x18000b89a  mov     [rbp+var_8], 0
0x18000b89e  mov     eax, [r9+18h]
0x18000b8a2  sub     eax, [r9+20h]
0x18000b8a6  cmp     eax, r8d
0x18000b8a9  jb      short loc_18000B8D4
0x18000b8ab  mov     edx, [r9+20h]
0x18000b8af  mov     rax, [r9+10h]
0x18000b8b3  mov     rcx, [r10+8]
0x18000b8b7  mov     al, [rdx+rax]
0x18000b8ba  mov     [rcx+1], al
0x18000b8bd  jmp     short loc_18000B8F1
0x18000b8bf  test    cx, cx
0x18000b8c2  jnz     short loc_18000B8F5
0x18000b8c4  mov     [rbp+var_8], cl
0x18000b8c7  mov     eax, [r9+18h]
0x18000b8cb  sub     eax, [r9+20h]
0x18000b8cf  cmp     eax, r8d
0x18000b8d2  jnb     short loc_18000B8E0
0x18000b8d4  mov     edx, r8d; unsigned int
0x18000b8d7  mov     rcx, r9; this
0x18000b8da  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000b8e0  mov     edx, [r9+20h]
0x18000b8e4  mov     rax, [r9+10h]
0x18000b8e8  mov     rcx, [r10+8]
0x18000b8ec  mov     al, [rdx+rax]
0x18000b8ef  mov     [rcx], al
0x18000b8f1  add     [r9+20h], r8d
0x18000b8f5  lea     rcx, [rbp+var_10]
0x18000b8f9  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b8fe  jmp     loc_18000B9FC
0x18000b903  mov     rax, [rbp+arg_20]
0x18000b907  mov     [rbp+var_10], rax
0x18000b90b  mov     r8d, 1
0x18000b911  mov     [rbp+var_8], r8b
0x18000b915  lea     rcx, [rbp+var_10]
0x18000b919  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b91e  jmp     loc_18000B9FC
0x18000b923  sub     r8d, 9
0x18000b927  jz      loc_18000B9E1
0x18000b92d  sub     r8d, 5
0x18000b931  jz      loc_18000B9C4
0x18000b937  sub     r8d, 1
0x18000b93b  jz      short loc_18000B9A7
0x18000b93d  sub     r8d, 1
0x18000b941  jz      short loc_18000B98A
0x18000b943  sub     r8d, 1
0x18000b947  jz      short loc_18000B96D
0x18000b949  cmp     r8d, 1
0x18000b94d  jnz     loc_18000B9FC
0x18000b953  mov     rax, [rbp+arg_20]
0x18000b957  mov     [rbp+var_10], rax
0x18000b95b  mov     [rbp+var_8], r8b
0x18000b95f  lea     rcx, [rbp+var_10]
0x18000b963  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b968  jmp     loc_18000B9FC
0x18000b96d  mov     rax, [rbp+arg_20]
0x18000b971  mov     [rbp+var_10], rax
0x18000b975  mov     r8d, 1
0x18000b97b  mov     [rbp+var_8], r8b
0x18000b97f  lea     rcx, [rbp+var_10]
0x18000b983  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b988  jmp     short loc_18000B9FC
0x18000b98a  mov     rax, [rbp+arg_20]
0x18000b98e  mov     [rbp+var_10], rax
0x18000b992  mov     r8d, 1
0x18000b998  mov     [rbp+var_8], r8b
0x18000b99c  lea     rcx, [rbp+var_10]
0x18000b9a0  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b9a5  jmp     short loc_18000B9FC
0x18000b9a7  mov     rax, [rbp+arg_20]
0x18000b9ab  mov     [rbp+var_10], rax
0x18000b9af  mov     r8d, 1
0x18000b9b5  mov     [rbp+var_8], r8b
0x18000b9b9  lea     rcx, [rbp+var_10]
0x18000b9bd  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b9c2  jmp     short loc_18000B9FC
0x18000b9c4  mov     rax, [rbp+arg_20]
0x18000b9c8  mov     [rbp+var_10], rax
0x18000b9cc  mov     r8d, 1
0x18000b9d2  mov     [rbp+var_8], r8b
0x18000b9d6  lea     rcx, [rbp+var_10]
0x18000b9da  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b9df  jmp     short loc_18000B9FC
0x18000b9e1  mov     rax, [rbp+arg_20]
0x18000b9e5  mov     [rbp+var_10], rax
0x18000b9e9  mov     r8d, 1
0x18000b9ef  mov     [rbp+var_8], r8b
0x18000b9f3  lea     rcx, [rbp+var_10]
0x18000b9f7  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000b9fc  xor     al, al
0x18000b9fe  add     rsp, 30h
0x18000ba02  pop     rbp
0x18000ba03  retn
```
