# bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(ushort,bond::Metadata const &,bond::_bond_enumerators::BondDataType::BondDataType,bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>> const &,bond::CompactBinaryReader<bond::InputBuffer> &)

- ea: `0x18000ba0c`
- end: `0x18000bd5b`
- name: `??$BasicTypeField@V?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@bond@@V?$CompactBinaryReader@VInputBuffer@bond@@@2@@detail@bond@@YA_NGAEBUMetadata@1@W4BondDataType@3_bond_enumerators@1@AEBV?$To@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@V?$RequiredFieldValiadator@V?$cloud_store_data@UTouchpadSettings@Devices@Input@Data@Windows@@@wil@@@bond@@@1@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@1@@Z`
- size: `847`
- prototype: `char __fastcall(unsigned __int16, __int64, int, __int64, bond::InputBuffer *)`
- caller_count: `10`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011110`
- `0x1800112a0`
- `0x180011420`
- `0x18001155c`
- `0x18001164c`
- `0x18001173c`
- `0x1800117dc`
- `0x18001187c`
- `0x18001191c`
- `0x180011b80`

## callees

- `0x18000ba0c`
- `0x18000f934`
- `0x18000f9c0`
- `0x18001b468`
- `0x18001b488`
- `0x18001b4a8`
- `0x18001b4c8`
- `0x18001b4e8`
- `0x18001b508`
- `0x18001b528`
- `0x18001bc40`
- `0x18001f55c`
- `0x180020960`

## pseudocode

```c
char __fastcall bond::detail::BasicTypeField<bond::To<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>,bond::RequiredFieldValiadator<wil::cloud_store_data<Windows::Data::Input::Devices::TouchpadSettings>>>,bond::CompactBinaryReader<bond::InputBuffer>>(
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
  __int64 v10; // rdx
  __int64 v11; // rbx
  _WORD *v12; // rbx
  char v13; // bl
  int v15; // r8d
  int v16; // r8d
  int v17; // r8d
  int v18; // r8d
  int v19; // r8d
  __int64 v20; // rbx
  __int64 v21; // rbx
  __int64 v22; // r11
  __int64 v23; // r8
  int v24; // edx
  bond::InputBuffer *v25; // [rsp+20h] [rbp-10h] BYREF
  char v26; // [rsp+28h] [rbp-8h]
  unsigned int v27; // [rsp+50h] [rbp+20h] BYREF

  if ( a3 > 8 )
  {
    v15 = a3 - 9;
    if ( !v15 )
    {
      v25 = a5;
      v26 = 1;
      bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
      return 0;
    }
    v16 = v15 - 5;
    if ( v16 )
    {
      v17 = v16 - 1;
      if ( v17 )
      {
        v18 = v17 - 1;
        if ( v18 )
        {
          v19 = v18 - 1;
          if ( v19 )
          {
            if ( v19 == 1 )
            {
              v25 = a5;
              v26 = 1;
              bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
            }
            return 0;
          }
LABEL_32:
          v25 = a5;
          v26 = 1;
          bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
          return 0;
        }
        v25 = a5;
        v26 = 1;
        if ( a1 == 1 )
        {
          v20 = *(_QWORD *)(a4 + 8);
          v26 = 0;
          v27 = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned int>(a5);
          *(_DWORD *)(v20 + 4) = -(v27 & 1) ^ (v27 >> 1);
        }
      }
      else
      {
        v25 = a5;
        v26 = 1;
        if ( a1 == 1 )
        {
          v21 = *(_QWORD *)(a4 + 8);
          v26 = 0;
          LOWORD(v27) = 0;
          bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, &v27);
          *(_DWORD *)(v21 + 4) = (__int16)-(v27 & 1) ^ ((unsigned __int16)v27 >> 1);
        }
      }
      goto LABEL_38;
    }
    v25 = a5;
    v26 = 1;
    if ( a1 == 1 )
    {
      v26 = 0;
      v22 = *((unsigned int *)a5 + 8);
      if ( *((_DWORD *)a5 + 6) == (_DWORD)v22 )
        bond::InputBuffer::EofException(a5, 1u);
      v23 = *(_QWORD *)(a4 + 8);
      v24 = *(char *)(v22 + *((_QWORD *)a5 + 2));
      *((_DWORD *)a5 + 8) = v22 + 1;
      *(_DWORD *)(v23 + 4) = v24;
    }
LABEL_43:
    bond::value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned char,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
    return 0;
  }
  if ( a3 != 8 )
  {
    v5 = a3 - 2;
    if ( !v5 )
    {
      v25 = a5;
      v26 = 1;
      v13 = ((__int64 (__fastcall *)(__int64, __int64, _QWORD, bond::InputBuffer **))__)(a4, a2, a1, &v25);
      bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
      return v13;
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
              v25 = a5;
              v26 = 1;
              bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
            }
            return 0;
          }
        }
        goto LABEL_32;
      }
      v25 = a5;
      v26 = 1;
      if ( a1 == 9 )
      {
        v10 = *(_QWORD *)(a4 + 8) + 16LL;
LABEL_16:
        v26 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned short>(a5, v10);
        goto LABEL_38;
      }
      if ( !a1 )
      {
        v10 = *(_QWORD *)(a4 + 8);
        goto LABEL_16;
      }
LABEL_38:
      bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
      return 0;
    }
    v25 = a5;
    v26 = 1;
    if ( a1 == 9 )
    {
      v11 = *(_QWORD *)(a4 + 8);
      LOBYTE(v27) = 0;
      v26 = 0;
      bond::InputBuffer::Read(a5, (unsigned __int8 *)&v27);
      *(_WORD *)(v11 + 16) = (unsigned __int8)v27;
    }
    else if ( !a1 )
    {
      v12 = *(_WORD **)(a4 + 8);
      LOBYTE(v27) = 0;
      v26 = 0;
      bond::InputBuffer::Read(a5, (unsigned __int8 *)&v27);
      *v12 = (unsigned __int8)v27;
    }
    goto LABEL_43;
  }
  v25 = a5;
  v26 = 1;
  bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(&v25);
  return 0;
}

```

## disassembly

```asm
0x18000ba0c  mov     [rsp-8+arg_0], rbx
0x18000ba11  mov     [rsp-8+arg_8], rdi
0x18000ba16  push    rbp
0x18000ba17  mov     rbp, rsp
0x18000ba1a  sub     rsp, 30h
0x18000ba1e  mov     r10, r9
0x18000ba21  cmp     r8d, 8
0x18000ba25  jg      loc_18000BBC5
0x18000ba2b  jz      loc_18000BBA6
0x18000ba31  sub     r8d, 2
0x18000ba35  jz      loc_18000BB73
0x18000ba3b  sub     r8d, 1
0x18000ba3f  jz      loc_18000BB06
0x18000ba45  sub     r8d, 1
0x18000ba49  jz      short loc_18000BABC
0x18000ba4b  sub     r8d, 1
0x18000ba4f  jz      short loc_18000BA9D
0x18000ba51  sub     r8d, 1
0x18000ba55  jz      short loc_18000BA7E
0x18000ba57  cmp     r8d, 1
0x18000ba5b  jnz     loc_18000BD49
0x18000ba61  mov     rax, [rbp+arg_20]
0x18000ba65  mov     [rbp+var_10], rax
0x18000ba69  mov     edi, r8d
0x18000ba6c  mov     [rbp+var_8], dil
0x18000ba70  lea     rcx, [rbp+var_10]
0x18000ba74  call    ??1?$value_common@MAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<float,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ba79  jmp     loc_18000BD49
0x18000ba7e  mov     rax, [rbp+arg_20]
0x18000ba82  mov     [rbp+var_10], rax
0x18000ba86  mov     edi, 1
0x18000ba8b  mov     [rbp+var_8], dil
0x18000ba8f  lea     rcx, [rbp+var_10]
0x18000ba93  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000ba98  jmp     loc_18000BD49
0x18000ba9d  mov     rax, [rbp+arg_20]
0x18000baa1  mov     [rbp+var_10], rax
0x18000baa5  mov     edi, 1
0x18000baaa  mov     [rbp+var_8], dil
0x18000baae  lea     rcx, [rbp+var_10]
0x18000bab2  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bab7  jmp     loc_18000BD49
0x18000babc  mov     r8, [rbp+arg_20]
0x18000bac0  mov     [rbp+var_10], r8
0x18000bac4  mov     edi, 1
0x18000bac9  mov     [rbp+var_8], dil
0x18000bacd  lea     eax, [rdi+8]
0x18000bad0  cmp     cx, ax
0x18000bad3  jnz     short loc_18000BAE1
0x18000bad5  xor     eax, eax
0x18000bad7  mov     rdx, [r9+8]
0x18000badb  add     rdx, 10h
0x18000badf  jmp     short loc_18000BAEC
0x18000bae1  xor     eax, eax
0x18000bae3  test    cx, cx
0x18000bae6  jnz     short loc_18000BAF8
0x18000bae8  mov     rdx, [r9+8]
0x18000baec  mov     [rbp+var_8], al
0x18000baef  mov     rcx, r8
0x18000baf2  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000baf7  nop
0x18000baf8  lea     rcx, [rbp+var_10]
0x18000bafc  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bb01  jmp     loc_18000BD49
0x18000bb06  mov     r8, [rbp+arg_20]
0x18000bb0a  mov     [rbp+var_10], r8
0x18000bb0e  mov     edi, 1
0x18000bb13  mov     [rbp+var_8], dil
0x18000bb17  lea     eax, [rdi+8]
0x18000bb1a  cmp     cx, ax
0x18000bb1d  jnz     short loc_18000BB41
0x18000bb1f  mov     rbx, [r9+8]
0x18000bb23  xor     eax, eax
0x18000bb25  mov     byte ptr [rbp+arg_10], al
0x18000bb28  mov     [rbp+var_8], al
0x18000bb2b  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000bb2f  mov     rcx, r8; this
0x18000bb32  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000bb37  movzx   eax, byte ptr [rbp+arg_10]
0x18000bb3b  mov     [rbx+10h], ax
0x18000bb3f  jmp     short loc_18000BB65
0x18000bb41  xor     eax, eax
0x18000bb43  test    cx, cx
0x18000bb46  jnz     short loc_18000BB65
0x18000bb48  mov     rbx, [r9+8]
0x18000bb4c  mov     byte ptr [rbp+arg_10], al
0x18000bb4f  mov     [rbp+var_8], al
0x18000bb52  lea     rdx, [rbp+arg_10]; unsigned __int8 *
0x18000bb56  mov     rcx, r8; this
0x18000bb59  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x18000bb5e  movzx   eax, byte ptr [rbp+arg_10]
0x18000bb62  mov     [rbx], ax
0x18000bb65  lea     rcx, [rbp+var_10]
0x18000bb69  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bb6e  jmp     loc_18000BD49
0x18000bb73  mov     rax, [rbp+arg_20]
0x18000bb77  mov     [rbp+var_10], rax
0x18000bb7b  mov     edi, 1
0x18000bb80  mov     [rbp+var_8], dil
0x18000bb84  lea     r9, [rbp+var_10]
0x18000bb88  movzx   r8d, cx
0x18000bb8c  mov     rcx, r10
0x18000bb8f  call    ??@092679412d615fa802f1e4cfed5297f2@
0x18000bb94  mov     bl, al
0x18000bb96  lea     rcx, [rbp+var_10]
0x18000bb9a  call    ??1?$value_common@_NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<bool,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bb9f  mov     al, bl
0x18000bba1  jmp     loc_18000BD4B
0x18000bba6  mov     rax, [rbp+arg_20]
0x18000bbaa  mov     [rbp+var_10], rax
0x18000bbae  mov     edi, 1
0x18000bbb3  mov     [rbp+var_8], dil
0x18000bbb7  lea     rcx, [rbp+var_10]
0x18000bbbb  call    ??1?$value_common@NAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<double,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bbc0  jmp     loc_18000BD49
0x18000bbc5  sub     r8d, 9
0x18000bbc9  jz      loc_18000BD2F
0x18000bbcf  sub     r8d, 5
0x18000bbd3  jz      loc_18000BCD6
0x18000bbd9  sub     r8d, 1
0x18000bbdd  jz      loc_18000BC81
0x18000bbe3  sub     r8d, 1
0x18000bbe7  jz      short loc_18000BC35
0x18000bbe9  sub     r8d, 1
0x18000bbed  jz      short loc_18000BC16
0x18000bbef  cmp     r8d, 1
0x18000bbf3  jnz     loc_18000BD49
0x18000bbf9  mov     rax, [rbp+arg_20]
0x18000bbfd  mov     [rbp+var_10], rax
0x18000bc01  mov     edi, r8d
0x18000bc04  mov     [rbp+var_8], dil
0x18000bc08  lea     rcx, [rbp+var_10]
0x18000bc0c  call    ??1?$value_common@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::wstring,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bc11  jmp     loc_18000BD49
0x18000bc16  mov     rax, [rbp+arg_20]
0x18000bc1a  mov     [rbp+var_10], rax
0x18000bc1e  mov     edi, 1
0x18000bc23  mov     [rbp+var_8], dil
0x18000bc27  lea     rcx, [rbp+var_10]
0x18000bc2b  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bc30  jmp     loc_18000BD49
0x18000bc35  mov     r8, [rbp+arg_20]
0x18000bc39  mov     [rbp+var_10], r8
0x18000bc3d  mov     edi, 1
0x18000bc42  mov     [rbp+var_8], dil
0x18000bc46  cmp     cx, di
0x18000bc49  jnz     short loc_18000BC73
0x18000bc4b  mov     rbx, [r9+8]
0x18000bc4f  xor     eax, eax
0x18000bc51  mov     [rbp+var_8], al
0x18000bc54  mov     [rbp+arg_10], eax
0x18000bc57  lea     rdx, [rbp+arg_10]
0x18000bc5b  mov     rcx, r8; this
0x18000bc5e  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x18000bc63  mov     eax, [rbp+arg_10]
0x18000bc66  mov     ecx, eax
0x18000bc68  shr     ecx, 1
0x18000bc6a  and     eax, edi
0x18000bc6c  neg     eax
0x18000bc6e  xor     ecx, eax
0x18000bc70  mov     [rbx+4], ecx
0x18000bc73  lea     rcx, [rbp+var_10]
0x18000bc77  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bc7c  jmp     loc_18000BD49
0x18000bc81  mov     r8, [rbp+arg_20]
0x18000bc85  mov     [rbp+var_10], r8
0x18000bc89  mov     edi, 1
0x18000bc8e  mov     [rbp+var_8], dil
0x18000bc92  cmp     cx, di
0x18000bc95  jnz     short loc_18000BCCB
0x18000bc97  mov     rbx, [r9+8]
0x18000bc9b  xor     eax, eax
0x18000bc9d  mov     [rbp+var_8], al
0x18000bca0  mov     word ptr [rbp+arg_10], ax
0x18000bca4  lea     rdx, [rbp+arg_10]
0x18000bca8  mov     rcx, r8
0x18000bcab  call    ??$ReadVariableUnsigned@G@InputBuffer@bond@@QEAAXAEAG@Z; bond::InputBuffer::ReadVariableUnsigned<ushort>(ushort &)
0x18000bcb0  movzx   edx, word ptr [rbp+arg_10]
0x18000bcb4  movzx   eax, dx
0x18000bcb7  shr     ax, 1
0x18000bcba  movzx   ecx, ax
0x18000bcbd  and     dx, di
0x18000bcc0  neg     dx
0x18000bcc3  movsx   eax, dx
0x18000bcc6  xor     ecx, eax
0x18000bcc8  mov     [rbx+4], ecx
0x18000bccb  lea     rcx, [rbp+var_10]
0x18000bccf  call    ??1?$value_common@_KAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<unsigned __int64,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bcd4  jmp     short loc_18000BD49
0x18000bcd6  mov     r9, [rbp+arg_20]
0x18000bcda  mov     [rbp+var_10], r9
0x18000bcde  mov     edi, 1
0x18000bce3  mov     [rbp+var_8], dil
0x18000bce7  cmp     cx, di
0x18000bcea  jnz     short loc_18000BD24
0x18000bcec  xor     eax, eax
0x18000bcee  mov     [rbp+var_8], al
0x18000bcf1  mov     r11d, [r9+20h]
0x18000bcf5  mov     eax, [r9+18h]
0x18000bcf9  sub     eax, r11d
0x18000bcfc  cmp     eax, edi
0x18000bcfe  jnb     short loc_18000BD0B
0x18000bd00  mov     edx, edi; unsigned int
0x18000bd02  mov     rcx, r9; this
0x18000bd05  call    ?EofException@InputBuffer@bond@@IEBAXI@Z; bond::InputBuffer::EofException(uint)
0x18000bd0b  mov     r8, [r10+8]
0x18000bd0f  mov     rax, [r9+10h]
0x18000bd13  movsx   edx, byte ptr [r11+rax]
0x18000bd18  lea     eax, [r11+1]
0x18000bd1c  mov     [r9+20h], eax
0x18000bd20  mov     [r8+4], edx
0x18000bd24  lea     rcx, [rbp+var_10]
0x18000bd28  call    ??1?$value_common@EAEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<uchar,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bd2d  jmp     short loc_18000BD49
0x18000bd2f  mov     rax, [rbp+arg_20]
0x18000bd33  mov     [rbp+var_10], rax
0x18000bd37  mov     edi, 1
0x18000bd3c  mov     [rbp+var_8], dil
0x18000bd40  lea     rcx, [rbp+var_10]
0x18000bd44  call    ??1?$value_common@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAV?$CompactBinaryReader@VInputBuffer@bond@@@bond@@@bond@@QEAA@XZ; bond::value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>::~value_common<std::string,bond::CompactBinaryReader<bond::InputBuffer> &>(void)
0x18000bd49  xor     al, al
0x18000bd4b  mov     rbx, [rsp+30h+arg_0]
0x18000bd50  mov     rdi, [rsp+30h+arg_8]
0x18000bd55  add     rsp, 30h
0x18000bd59  pop     rbp
0x18000bd5a  retn
```
