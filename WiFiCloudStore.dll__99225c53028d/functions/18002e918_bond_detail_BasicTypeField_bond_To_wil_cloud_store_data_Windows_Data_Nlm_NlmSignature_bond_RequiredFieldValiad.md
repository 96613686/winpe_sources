# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18002e918`
- end: `0x18002eb38`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UNlmSignature@Nlm@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `544`
- prototype: `char __fastcall(__int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800282c0`

## callees

- `0x1800031d4`
- `0x180019d80`
- `0x18001aa20`
- `0x180026ee0`
- `0x180026f0c`
- `0x18002e918`
- `0x18002ecb8`
- `0x18002fe40`
- `0x18002fe60`
- `0x18002fe80`
- `0x18002fea0`
- `0x18002fec0`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Nlm::NlmSignature>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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
  _QWORD *v10; // rbx
  _QWORD *v11; // rbx
  _QWORD *v12; // rbx
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  bond::InputBuffer *v19; // [rsp+20h] [rbp-10h] BYREF
  char v20; // [rsp+28h] [rbp-8h]
  unsigned int v21; // [rsp+40h] [rbp+10h] BYREF

  LOWORD(v21) = a1;
  if ( a3 > 8 )
  {
    v13 = a3 - 9;
    if ( v13 )
    {
      v14 = v13 - 5;
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 && (v16 = v15 - 1) != 0 && (v17 = v16 - 1) != 0 )
        {
          if ( v17 == 1 )
          {
            v19 = a5;
            v20 = 1;
            bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
          }
        }
        else
        {
          v19 = a5;
          v20 = 1;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
        }
      }
      else
      {
        v19 = a5;
        v20 = 1;
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
      }
    }
    else
    {
      v19 = a5;
      v20 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
    }
  }
  else if ( a3 == 8 )
  {
    v19 = a5;
    v20 = 1;
    bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
  }
  else
  {
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
                v19 = a5;
                v20 = 1;
                bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
              }
            }
            else
            {
              v19 = a5;
              v20 = 0;
              bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(a5);
              bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
            }
          }
          else
          {
            v19 = a5;
            v10 = *(_QWORD **)(a4 + 8);
            v21 = 0;
            v20 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5, &v21);
            *v10 = v21;
            bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
          }
        }
        else
        {
          v19 = a5;
          v11 = *(_QWORD **)(a4 + 8);
          LOWORD(v21) = 0;
          v20 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v21);
          *v11 = (unsigned __int16)v21;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
        }
      }
      else
      {
        v19 = a5;
        v12 = *(_QWORD **)(a4 + 8);
        LOBYTE(v21) = 0;
        v20 = 0;
        bond::InputBuffer::Read(a5, (unsigned __int8 *)&v21);
        *v12 = (unsigned __int8)v21;
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
      }
    }
    else
    {
      v19 = a5;
      v20 = 1;
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18002e918  mov     [rsp-8+arg_8], rbx
0x18002e91d  mov     word ptr [rsp-8+arg_0], cx
0x18002e922  push    rbp
0x18002e923  mov     rbp, rsp
0x18002e926  sub     rsp, 30h
0x18002e92a  cmp     r8d, 8
0x18002e92e  jg      loc_18002EA77
0x18002e934  jz      loc_18002EA5D
0x18002e93a  sub     r8d, 2
0x18002e93e  jz      loc_18002EA43
0x18002e944  sub     r8d, 1
0x18002e948  jz      loc_18002EA11
0x18002e94e  sub     r8d, 1
0x18002e952  jz      loc_18002E9DE
0x18002e958  sub     r8d, 1
0x18002e95c  jz      short loc_18002E9AD
0x18002e95e  sub     r8d, 1
0x18002e962  jz      short loc_18002E988
0x18002e964  cmp     r8d, 1
0x18002e968  jnz     loc_18002EB2B
0x18002e96e  mov     rax, [rbp+arg_20]
0x18002e972  mov     [rbp+var_10], rax
0x18002e976  mov     [rbp+var_8], r8b
0x18002e97a  lea     rcx, [rbp+var_10]
0x18002e97e  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002e983  jmp     loc_18002EB2B
0x18002e988  mov     rcx, [rbp+arg_20]; this
0x18002e98c  mov     [rbp+var_10], rcx
0x18002e990  xor     eax, eax
0x18002e992  mov     [rbp+var_8], al
0x18002e995  mov     rdx, [r9+8]
0x18002e999  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x18002e99e  nop
0x18002e99f  lea     rcx, [rbp+var_10]
0x18002e9a3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002e9a8  jmp     loc_18002EB2B
0x18002e9ad  mov     rcx, [rbp+arg_20]
0x18002e9b1  mov     [rbp+var_10], rcx
0x18002e9b5  mov     rbx, [r9+8]
0x18002e9b9  xor     eax, eax
0x18002e9bb  mov     [rbp+arg_0], eax
0x18002e9be  mov     [rbp+var_8], al
0x18002e9c1  lea     rdx, [rbp+arg_0]
0x18002e9c5  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18002e9ca  mov     eax, [rbp+arg_0]
0x18002e9cd  mov     [rbx], rax
0x18002e9d0  lea     rcx, [rbp+var_10]
0x18002e9d4  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002e9d9  jmp     loc_18002EB2B
0x18002e9de  mov     rcx, [rbp+arg_20]
0x18002e9e2  mov     [rbp+var_10], rcx
0x18002e9e6  mov     rbx, [r9+8]
0x18002e9ea  xor     eax, eax
0x18002e9ec  mov     word ptr [rbp+arg_0], ax
0x18002e9f0  mov     [rbp+var_8], al
0x18002e9f3  lea     rdx, [rbp+arg_0]
0x18002e9f7  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18002e9fc  movzx   eax, word ptr [rbp+arg_0]
0x18002ea00  mov     [rbx], rax
0x18002ea03  lea     rcx, [rbp+var_10]
0x18002ea07  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002ea0c  jmp     loc_18002EB2B
0x18002ea11  mov     rcx, [rbp+arg_20]; this
0x18002ea15  mov     [rbp+var_10], rcx
0x18002ea19  mov     rbx, [r9+8]
0x18002ea1d  xor     eax, eax
0x18002ea1f  mov     byte ptr [rbp+arg_0], al
0x18002ea22  mov     [rbp+var_8], al
0x18002ea25  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x18002ea29  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18002ea2e  movzx   eax, byte ptr [rbp+arg_0]
0x18002ea32  mov     [rbx], rax
0x18002ea35  lea     rcx, [rbp+var_10]
0x18002ea39  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002ea3e  jmp     loc_18002EB2B
0x18002ea43  mov     rax, [rbp+arg_20]
0x18002ea47  mov     [rbp+var_10], rax
0x18002ea4b  mov     [rbp+var_8], 1
0x18002ea4f  lea     rcx, [rbp+var_10]
0x18002ea53  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002ea58  jmp     loc_18002EB2B
0x18002ea5d  mov     rax, [rbp+arg_20]
0x18002ea61  mov     [rbp+var_10], rax
0x18002ea65  mov     [rbp+var_8], 1
0x18002ea69  lea     rcx, [rbp+var_10]
0x18002ea6d  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002ea72  jmp     loc_18002EB2B
0x18002ea77  sub     r8d, 9
0x18002ea7b  jz      loc_18002EB16
0x18002ea81  sub     r8d, 5
0x18002ea85  jz      short loc_18002EAFF
0x18002ea87  sub     r8d, 1
0x18002ea8b  jz      short loc_18002EAE8
0x18002ea8d  sub     r8d, 1
0x18002ea91  jz      short loc_18002EAD1
0x18002ea93  sub     r8d, 1
0x18002ea97  jz      short loc_18002EABA
0x18002ea99  cmp     r8d, 1
0x18002ea9d  jnz     loc_18002EB2B
0x18002eaa3  mov     rax, [rbp+arg_20]
0x18002eaa7  mov     [rbp+var_10], rax
0x18002eaab  mov     [rbp+var_8], r8b
0x18002eaaf  lea     rcx, [rbp+var_10]
0x18002eab3  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eab8  jmp     short loc_18002EB2B
0x18002eaba  mov     rax, [rbp+arg_20]
0x18002eabe  mov     [rbp+var_10], rax
0x18002eac2  mov     [rbp+var_8], 1
0x18002eac6  lea     rcx, [rbp+var_10]
0x18002eaca  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eacf  jmp     short loc_18002EB2B
0x18002ead1  mov     rax, [rbp+arg_20]
0x18002ead5  mov     [rbp+var_10], rax
0x18002ead9  mov     [rbp+var_8], 1
0x18002eadd  lea     rcx, [rbp+var_10]
0x18002eae1  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eae6  jmp     short loc_18002EB2B
0x18002eae8  mov     rax, [rbp+arg_20]
0x18002eaec  mov     [rbp+var_10], rax
0x18002eaf0  mov     [rbp+var_8], 1
0x18002eaf4  lea     rcx, [rbp+var_10]
0x18002eaf8  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eafd  jmp     short loc_18002EB2B
0x18002eaff  mov     rax, [rbp+arg_20]
0x18002eb03  mov     [rbp+var_10], rax
0x18002eb07  mov     [rbp+var_8], 1
0x18002eb0b  lea     rcx, [rbp+var_10]
0x18002eb0f  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eb14  jmp     short loc_18002EB2B
0x18002eb16  mov     rax, [rbp+arg_20]
0x18002eb1a  mov     [rbp+var_10], rax
0x18002eb1e  mov     [rbp+var_8], 1
0x18002eb22  lea     rcx, [rbp+var_10]
0x18002eb26  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18002eb2b  xor     al, al
0x18002eb2d  mov     rbx, [rsp+30h+arg_8]
0x18002eb32  add     rsp, 30h
0x18002eb36  pop     rbp
0x18002eb37  retn
```
