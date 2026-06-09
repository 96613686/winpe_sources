# bond::detail::BasicTypeField<bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18001adac`
- end: `0x18001afd3`
- name: `??$BasicTypeField@V?$To@UFocusSession@Shell@Data@Windows@@V?$RequiredFieldValiadator@UFocusSession@Shell@Data@Windows@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@UFocusSession@Shell@Data@Windows@@V?$RequiredFieldValiadator@UFocusSession@Shell@Data@Windows@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `551`
- prototype: `__int64 __fastcall(int, int, int, int, bond::InputBuffer *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18001cde8`

## callees

- `0x180010150`
- `0x1800101a4`
- `0x18001357c`
- `0x18001359c`
- `0x1800135bc`
- `0x1800135dc`
- `0x1800135fc`
- `0x18001361c`
- `0x18001363c`
- `0x180015508`
- `0x18001adac`
- `0x18001c810`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
char __fastcall bond::detail::BasicTypeField<bond::To<Windows::Data::Shell::FocusSession,bond::RequiredFieldValiadator<Windows::Data::Shell::FocusSession>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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
            v10 = *(_QWORD *)(a4 + 8);
            v21 = 0;
            v20 = 0;
            bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5);
            *(_QWORD *)(v10 + 32) = v21;
            bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
          }
        }
        else
        {
          v19 = a5;
          v11 = *(_QWORD *)(a4 + 8);
          LOWORD(v21) = 0;
          v20 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v21);
          *(_QWORD *)(v11 + 32) = (unsigned __int16)v21;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
        }
      }
      else
      {
        v19 = a5;
        v12 = *(_QWORD *)(a4 + 8);
        LOBYTE(v21) = 0;
        v20 = 0;
        bond::InputBuffer::Read(a5, (unsigned __int8 *)&v21);
        *(_QWORD *)(v12 + 32) = (unsigned __int8)v21;
        bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v19);
      }
    }
    else
    {
      v19 = a5;
      v20 = 1;
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>((__int64)&v19);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001adac  mov     [rsp-8+arg_8], rbx
0x18001adb1  mov     word ptr [rsp-8+arg_0], cx
0x18001adb6  push    rbp
0x18001adb7  mov     rbp, rsp
0x18001adba  sub     rsp, 30h
0x18001adbe  cmp     r8d, 8
0x18001adc2  jg      loc_18001AF12
0x18001adc8  jz      loc_18001AEF8
0x18001adce  sub     r8d, 2
0x18001add2  jz      loc_18001AEDE
0x18001add8  sub     r8d, 1
0x18001addc  jz      loc_18001AEAB
0x18001ade2  sub     r8d, 1
0x18001ade6  jz      loc_18001AE77
0x18001adec  sub     r8d, 1
0x18001adf0  jz      short loc_18001AE45
0x18001adf2  sub     r8d, 1
0x18001adf6  jz      short loc_18001AE1C
0x18001adf8  cmp     r8d, 1
0x18001adfc  jnz     loc_18001AFC6
0x18001ae02  mov     rax, [rbp+arg_20]
0x18001ae06  mov     [rbp+var_10], rax
0x18001ae0a  mov     [rbp+var_8], r8b
0x18001ae0e  lea     rcx, [rbp+var_10]
0x18001ae12  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001ae17  jmp     loc_18001AFC6
0x18001ae1c  mov     rcx, [rbp+arg_20]; this
0x18001ae20  mov     [rbp+var_10], rcx
0x18001ae24  xor     eax, eax
0x18001ae26  mov     [rbp+var_8], al
0x18001ae29  mov     rdx, [r9+8]
0x18001ae2d  add     rdx, 20h ; ' '
0x18001ae31  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x18001ae36  nop
0x18001ae37  lea     rcx, [rbp+var_10]
0x18001ae3b  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001ae40  jmp     loc_18001AFC6
0x18001ae45  mov     rcx, [rbp+arg_20]; this
0x18001ae49  mov     [rbp+var_10], rcx
0x18001ae4d  mov     rbx, [r9+8]
0x18001ae51  xor     eax, eax
0x18001ae53  mov     [rbp+arg_0], eax
0x18001ae56  mov     [rbp+var_8], al
0x18001ae59  lea     rdx, [rbp+arg_0]
0x18001ae5d  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18001ae62  mov     eax, [rbp+arg_0]
0x18001ae65  mov     [rbx+20h], rax
0x18001ae69  lea     rcx, [rbp+var_10]
0x18001ae6d  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001ae72  jmp     loc_18001AFC6
0x18001ae77  mov     rcx, [rbp+arg_20]
0x18001ae7b  mov     [rbp+var_10], rcx
0x18001ae7f  mov     rbx, [r9+8]
0x18001ae83  xor     eax, eax
0x18001ae85  mov     word ptr [rbp+arg_0], ax
0x18001ae89  mov     [rbp+var_8], al
0x18001ae8c  lea     rdx, [rbp+arg_0]
0x18001ae90  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18001ae95  movzx   eax, word ptr [rbp+arg_0]
0x18001ae99  mov     [rbx+20h], rax
0x18001ae9d  lea     rcx, [rbp+var_10]
0x18001aea1  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001aea6  jmp     loc_18001AFC6
0x18001aeab  mov     rcx, [rbp+arg_20]; this
0x18001aeaf  mov     [rbp+var_10], rcx
0x18001aeb3  mov     rbx, [r9+8]
0x18001aeb7  xor     eax, eax
0x18001aeb9  mov     byte ptr [rbp+arg_0], al
0x18001aebc  mov     [rbp+var_8], al
0x18001aebf  lea     rdx, [rbp+arg_0]; unsigned __int8 *
0x18001aec3  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18001aec8  movzx   eax, byte ptr [rbp+arg_0]
0x18001aecc  mov     [rbx+20h], rax
0x18001aed0  lea     rcx, [rbp+var_10]
0x18001aed4  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001aed9  jmp     loc_18001AFC6
0x18001aede  mov     rax, [rbp+arg_20]
0x18001aee2  mov     [rbp+var_10], rax
0x18001aee6  mov     [rbp+var_8], 1
0x18001aeea  lea     rcx, [rbp+var_10]
0x18001aeee  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001aef3  jmp     loc_18001AFC6
0x18001aef8  mov     rax, [rbp+arg_20]
0x18001aefc  mov     [rbp+var_10], rax
0x18001af00  mov     [rbp+var_8], 1
0x18001af04  lea     rcx, [rbp+var_10]
0x18001af08  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001af0d  jmp     loc_18001AFC6
0x18001af12  sub     r8d, 9
0x18001af16  jz      loc_18001AFB1
0x18001af1c  sub     r8d, 5
0x18001af20  jz      short loc_18001AF9A
0x18001af22  sub     r8d, 1
0x18001af26  jz      short loc_18001AF83
0x18001af28  sub     r8d, 1
0x18001af2c  jz      short loc_18001AF6C
0x18001af2e  sub     r8d, 1
0x18001af32  jz      short loc_18001AF55
0x18001af34  cmp     r8d, 1
0x18001af38  jnz     loc_18001AFC6
0x18001af3e  mov     rax, [rbp+arg_20]
0x18001af42  mov     [rbp+var_10], rax
0x18001af46  mov     [rbp+var_8], r8b
0x18001af4a  lea     rcx, [rbp+var_10]
0x18001af4e  call    ??1?$value_common@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001af53  jmp     short loc_18001AFC6
0x18001af55  mov     rax, [rbp+arg_20]
0x18001af59  mov     [rbp+var_10], rax
0x18001af5d  mov     [rbp+var_8], 1
0x18001af61  lea     rcx, [rbp+var_10]
0x18001af65  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001af6a  jmp     short loc_18001AFC6
0x18001af6c  mov     rax, [rbp+arg_20]
0x18001af70  mov     [rbp+var_10], rax
0x18001af74  mov     [rbp+var_8], 1
0x18001af78  lea     rcx, [rbp+var_10]
0x18001af7c  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001af81  jmp     short loc_18001AFC6
0x18001af83  mov     rax, [rbp+arg_20]
0x18001af87  mov     [rbp+var_10], rax
0x18001af8b  mov     [rbp+var_8], 1
0x18001af8f  lea     rcx, [rbp+var_10]
0x18001af93  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001af98  jmp     short loc_18001AFC6
0x18001af9a  mov     rax, [rbp+arg_20]
0x18001af9e  mov     [rbp+var_10], rax
0x18001afa2  mov     [rbp+var_8], 1
0x18001afa6  lea     rcx, [rbp+var_10]
0x18001afaa  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001afaf  jmp     short loc_18001AFC6
0x18001afb1  mov     rax, [rbp+arg_20]
0x18001afb5  mov     [rbp+var_10], rax
0x18001afb9  mov     [rbp+var_8], 1
0x18001afbd  lea     rcx, [rbp+var_10]
0x18001afc1  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18001afc6  xor     al, al
0x18001afc8  mov     rbx, [rsp+30h+arg_8]
0x18001afcd  add     rsp, 30h
0x18001afd1  pop     rbp
0x18001afd2  retn
```
