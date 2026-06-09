# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x180026c5c`
- end: `0x180026ecd`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UWiFiProfile@WiFi@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `625`
- prototype: `char __fastcall(__int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180033880`
- `0x180033920`

## callees

- `0x180002b30`
- `0x1800031d4`
- `0x180019d80`
- `0x18001aa20`
- `0x180026c5c`
- `0x180026ee0`
- `0x180026f0c`
- `0x18002ecb8`
- `0x18002fe40`
- `0x18002fe60`
- `0x18002fe80`
- `0x18002fea0`
- `0x18002fec0`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::WiFi::WiFiProfile>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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
  __int64 v10; // rbx
  __int64 v11; // rbx
  __int64 v12; // rbx
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  bond::InputBuffer *v19; // [rsp+20h] [rbp-10h] BYREF
  char v20; // [rsp+28h] [rbp-8h]
  unsigned int v21; // [rsp+50h] [rbp+20h] BYREF

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
            if ( !a1 )
            {
              v20 = 0;
              bond::CompactBinaryReader<bond::InputBuffer>::Read<std::wstring>(a5, *(bond::InputBuffer **)(a4 + 8));
            }
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
  else
  {
    if ( a3 == 8 )
    {
      v19 = a5;
      v20 = 1;
      bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
      return 0;
    }
    v5 = a3 - 2;
    if ( !v5 )
    {
      v19 = a5;
      v20 = 1;
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
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
              v19 = a5;
              v20 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
            }
            return 0;
          }
          v19 = a5;
          v20 = 1;
          if ( a1 == 1 )
          {
            v20 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(a5);
          }
        }
        else
        {
          v19 = a5;
          v20 = 1;
          if ( a1 == 1 )
          {
            v10 = *(_QWORD *)(a4 + 8);
            v21 = 0;
            v20 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5, &v21);
            *(_QWORD *)(v10 + 32) = v21;
          }
        }
      }
      else
      {
        v19 = a5;
        v20 = 1;
        if ( a1 == 1 )
        {
          v11 = *(_QWORD *)(a4 + 8);
          LOWORD(v21) = 0;
          v20 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v21);
          *(_QWORD *)(v11 + 32) = (unsigned __int16)v21;
        }
      }
      bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
      return 0;
    }
    v19 = a5;
    v20 = 1;
    if ( a1 == 1 )
    {
      v12 = *(_QWORD *)(a4 + 8);
      LOBYTE(v21) = 0;
      v20 = 0;
      bond::InputBuffer::Read(a5, (unsigned __int8 *)&v21);
      *(_QWORD *)(v12 + 32) = (unsigned __int8)v21;
    }
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
  }
  return 0;
}

```

## disassembly

```asm
0x180026c5c  mov     [rsp-8+arg_0], rbx
0x180026c61  push    rbp
0x180026c62  mov     rbp, rsp
0x180026c65  sub     rsp, 30h
0x180026c69  cmp     r8d, 8
0x180026c6d  jg      loc_180026DF1
0x180026c73  jz      loc_180026DD7
0x180026c79  sub     r8d, 2
0x180026c7d  jz      loc_180026DBD
0x180026c83  sub     r8d, 1
0x180026c87  jz      loc_180026D7D
0x180026c8d  sub     r8d, 1
0x180026c91  jz      loc_180026D3C
0x180026c97  sub     r8d, 1
0x180026c9b  jz      short loc_180026CFD
0x180026c9d  sub     r8d, 1
0x180026ca1  jz      short loc_180026CC7
0x180026ca3  cmp     r8d, 1
0x180026ca7  jnz     loc_180026EC0
0x180026cad  mov     rax, [rbp+arg_20]
0x180026cb1  mov     [rbp+var_10], rax
0x180026cb5  mov     [rbp+var_8], r8b
0x180026cb9  lea     rcx, [rbp+var_10]
0x180026cbd  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026cc2  jmp     loc_180026EC0
0x180026cc7  mov     r8, [rbp+arg_20]
0x180026ccb  mov     [rbp+var_10], r8
0x180026ccf  mov     [rbp+var_8], 1
0x180026cd3  cmp     cx, 1
0x180026cd7  jnz     short loc_180026CEF
0x180026cd9  xor     eax, eax
0x180026cdb  mov     [rbp+var_8], al
0x180026cde  mov     rdx, [r9+8]
0x180026ce2  add     rdx, 20h ; ' '
0x180026ce6  mov     rcx, r8; this
0x180026ce9  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180026cee  nop
0x180026cef  lea     rcx, [rbp+var_10]
0x180026cf3  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026cf8  jmp     loc_180026EC0
0x180026cfd  mov     r8, [rbp+arg_20]
0x180026d01  mov     [rbp+var_10], r8
0x180026d05  mov     [rbp+var_8], 1
0x180026d09  cmp     cx, 1
0x180026d0d  jnz     short loc_180026D2E
0x180026d0f  mov     rbx, [r9+8]
0x180026d13  xor     eax, eax
0x180026d15  mov     [rbp+arg_10], eax
0x180026d18  mov     [rbp+var_8], al
0x180026d1b  lea     rdx, [rbp+arg_10]
0x180026d1f  mov     rcx, r8
0x180026d22  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180026d27  mov     eax, [rbp+arg_10]
0x180026d2a  mov     [rbx+20h], rax
0x180026d2e  lea     rcx, [rbp+var_10]
0x180026d32  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026d37  jmp     loc_180026EC0
0x180026d3c  mov     r8, [rbp+arg_20]
0x180026d40  mov     [rbp+var_10], r8
0x180026d44  mov     [rbp+var_8], 1
0x180026d48  cmp     cx, 1
0x180026d4c  jnz     short loc_180026D6F
0x180026d4e  mov     rbx, [r9+8]
0x180026d52  xor     eax, eax
0x180026d54  mov     word ptr [rbp+arg_10], ax
0x180026d58  mov     [rbp+var_8], al
0x180026d5b  lea     rdx, [rbp+arg_10]
0x180026d5f  mov     rcx, r8
0x180026d62  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x180026d67  movzx   eax, word ptr [rbp+arg_10]
0x180026d6b  mov     [rbx+20h], rax
0x180026d6f  lea     rcx, [rbp+var_10]
0x180026d73  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026d78  jmp     loc_180026EC0
0x180026d7d  mov     r8, [rbp+arg_20]
0x180026d81  mov     [rbp+var_10], r8
0x180026d85  mov     [rbp+var_8], 1
0x180026d89  cmp     cx, 1
0x180026d8d  jnz     short loc_180026DAF
0x180026d8f  mov     rbx, [r9+8]
0x180026d93  xor     eax, eax
0x180026d95  mov     byte ptr [rbp+arg_10], al
0x180026d98  mov     [rbp+var_8], al
0x180026d9b  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x180026d9f  mov     rcx, r8; this
0x180026da2  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180026da7  movzx   eax, byte ptr [rbp+arg_10]
0x180026dab  mov     [rbx+20h], rax
0x180026daf  lea     rcx, [rbp+var_10]
0x180026db3  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026db8  jmp     loc_180026EC0
0x180026dbd  mov     rax, [rbp+arg_20]
0x180026dc1  mov     [rbp+var_10], rax
0x180026dc5  mov     [rbp+var_8], 1
0x180026dc9  lea     rcx, [rbp+var_10]
0x180026dcd  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026dd2  jmp     loc_180026EC0
0x180026dd7  mov     rax, [rbp+arg_20]
0x180026ddb  mov     [rbp+var_10], rax
0x180026ddf  mov     [rbp+var_8], 1
0x180026de3  lea     rcx, [rbp+var_10]
0x180026de7  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026dec  jmp     loc_180026EC0
0x180026df1  sub     r8d, 9
0x180026df5  jz      loc_180026EAB
0x180026dfb  sub     r8d, 5
0x180026dff  jz      loc_180026E94
0x180026e05  sub     r8d, 1
0x180026e09  jz      short loc_180026E7D
0x180026e0b  sub     r8d, 1
0x180026e0f  jz      short loc_180026E66
0x180026e11  sub     r8d, 1
0x180026e15  jz      short loc_180026E4F
0x180026e17  cmp     r8d, 1
0x180026e1b  jnz     loc_180026EC0
0x180026e21  mov     r8, [rbp+arg_20]
0x180026e25  mov     [rbp+var_10], r8
0x180026e29  mov     [rbp+var_8], 1
0x180026e2d  xor     eax, eax
0x180026e2f  test    cx, cx
0x180026e32  jnz     short loc_180026E44
0x180026e34  mov     [rbp+var_8], al
0x180026e37  mov     rdx, [r9+8]; bond::InputBuffer *
0x180026e3b  mov     rcx, r8; this
0x180026e3e  call    ??$Read@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Read<std::wstring>(std::wstring &)
0x180026e43  nop
0x180026e44  lea     rcx, [rbp+var_10]
0x180026e48  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026e4d  jmp     short loc_180026EC0
0x180026e4f  mov     rax, [rbp+arg_20]
0x180026e53  mov     [rbp+var_10], rax
0x180026e57  mov     [rbp+var_8], 1
0x180026e5b  lea     rcx, [rbp+var_10]
0x180026e5f  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026e64  jmp     short loc_180026EC0
0x180026e66  mov     rax, [rbp+arg_20]
0x180026e6a  mov     [rbp+var_10], rax
0x180026e6e  mov     [rbp+var_8], 1
0x180026e72  lea     rcx, [rbp+var_10]
0x180026e76  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026e7b  jmp     short loc_180026EC0
0x180026e7d  mov     rax, [rbp+arg_20]
0x180026e81  mov     [rbp+var_10], rax
0x180026e85  mov     [rbp+var_8], 1
0x180026e89  lea     rcx, [rbp+var_10]
0x180026e8d  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026e92  jmp     short loc_180026EC0
0x180026e94  mov     rax, [rbp+arg_20]
0x180026e98  mov     [rbp+var_10], rax
0x180026e9c  mov     [rbp+var_8], 1
0x180026ea0  lea     rcx, [rbp+var_10]
0x180026ea4  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026ea9  jmp     short loc_180026EC0
0x180026eab  mov     rax, [rbp+arg_20]
0x180026eaf  mov     [rbp+var_10], rax
0x180026eb3  mov     [rbp+var_8], 1
0x180026eb7  lea     rcx, [rbp+var_10]
0x180026ebb  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x180026ec0  xor     al, al
0x180026ec2  mov     rbx, [rsp+30h+arg_0]
0x180026ec7  add     rsp, 30h
0x180026ecb  pop     rbp
0x180026ecc  retn
```
