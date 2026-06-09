# bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)

- ea: `0x180019b6c`
- end: `0x180019d79`
- name: `?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z`
- size: `525`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `16`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000260c`
- `0x180002834`
- `0x180002e70`
- `0x180003d6c`
- `0x180019b6c`
- `0x1800282c0`
- `0x1800287e4`
- `0x18002ef74`
- `0x18002ef90`
- `0x18002efac`
- `0x18002efc8`
- `0x18002efe4`
- `0x180033880`
- `0x1800338d0`
- `0x180033920`
- `0x18003396c`

## callees

- `0x1800029c4`
- `0x180002a00`
- `0x1800031d4`
- `0x180019b6c`
- `0x180019d80`
- `0x180031360`
- `0x1800313c4`

## pseudocode

```c
void __fastcall bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::InputBuffer *this, int a2)
{
  int v3; // edx
  int v4; // edx
  int v5; // edx
  int v6; // edx
  int v7; // edx
  int v8; // edx
  int v9; // edx
  unsigned int v10; // ecx
  int v11; // edx
  int v12; // eax
  int v13; // ecx
  int v14; // ecx
  int v15; // eax
  int v16; // edx
  int v17; // edx
  int v18; // edx
  int v19; // edx
  int v20; // edx
  int v21; // edx
  int v22; // edx
  int v23; // ecx
  unsigned int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // [rsp+38h] [rbp+18h] BYREF
  unsigned __int64 v27; // [rsp+40h] [rbp+20h] BYREF

  if ( a2 > 10 )
  {
    v16 = a2 - 11;
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      v25 = 0;
      LODWORD(v27) = 0;
      v26 = 0;
      bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(this, &v26, &v27);
      if ( v26 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          ++v25;
        }
        while ( v25 < v26 );
      }
      return;
    }
    v18 = v17 - 1;
    if ( !v18 )
    {
      v24 = 0;
      v27 = 0;
      v26 = 0;
      bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(this);
      if ( v26 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          ++v24;
        }
        while ( v24 < v26 );
      }
      return;
    }
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_35;
    v20 = v19 - 1;
    if ( !v20 || (v21 = v20 - 1) == 0 || (v22 = v21 - 1) == 0 )
    {
LABEL_34:
      v27 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(this, &v27);
      return;
    }
    if ( v22 == 1 )
    {
      v26 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>((__int64)this, (int *)&v26);
      v10 = 2 * v26;
      goto LABEL_12;
    }
  }
  else
  {
    if ( a2 != 10 )
    {
      v3 = a2 - 2;
      if ( v3 )
      {
        v4 = v3 - 1;
        if ( v4 )
        {
          v5 = v4 - 1;
          if ( v5 )
          {
            v6 = v5 - 1;
            if ( v6 )
            {
              v7 = v6 - 1;
              if ( v7 )
              {
                v8 = v7 - 1;
                if ( !v8 )
                {
                  v14 = *((_DWORD *)this + 8);
                  if ( (unsigned int)(*((_DWORD *)this + 6) - v14) < 4 )
                    return;
                  v12 = v14 + 4;
                  goto LABEL_18;
                }
                v9 = v8 - 1;
                if ( !v9 )
                {
                  v13 = *((_DWORD *)this + 8);
                  if ( (unsigned int)(*((_DWORD *)this + 6) - v13) < 8 )
                    return;
                  v12 = v13 + 8;
                  goto LABEL_18;
                }
                if ( v9 != 1 )
                  return;
                goto LABEL_11;
              }
            }
          }
          goto LABEL_34;
        }
      }
LABEL_35:
      v23 = *((_DWORD *)this + 8);
      if ( *((_DWORD *)this + 6) != v23 )
      {
        v12 = v23 + 1;
LABEL_18:
        *((_DWORD *)this + 8) = v12;
        return;
      }
      return;
    }
    if ( *((_WORD *)this + 20) == 2 )
    {
LABEL_11:
      v26 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>((__int64)this, (int *)&v26);
      v10 = v26;
LABEL_12:
      v11 = *((_DWORD *)this + 8);
      if ( v10 > *((_DWORD *)this + 6) - v11 )
        return;
      v12 = v11 + v10;
      goto LABEL_18;
    }
    do
    {
      bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(this, 0);
      LOWORD(v26) = 0;
      LODWORD(v27) = 0;
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
      v15 = v27;
      if ( !(_DWORD)v27 )
        break;
      do
      {
        if ( v15 == 1 )
          break;
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
        bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
        v15 = v27;
      }
      while ( (_DWORD)v27 );
    }
    while ( v15 );
  }
}

```

## disassembly

```asm
0x180019b6c  mov     [rsp-8+arg_0], rbx
0x180019b71  mov     [rsp-8+arg_18], rdi
0x180019b76  push    rbp
0x180019b77  mov     rbp, rsp
0x180019b7a  sub     rsp, 20h
0x180019b7e  mov     rbx, rcx
0x180019b81  cmp     edx, 0Ah
0x180019b84  jg      loc_180019C90
0x180019b8a  jz      loc_180019C28
0x180019b90  sub     edx, 2
0x180019b93  jz      loc_180019CEE
0x180019b99  sub     edx, 1
0x180019b9c  jz      loc_180019CEE
0x180019ba2  sub     edx, 1
0x180019ba5  jz      loc_180019CDD
0x180019bab  sub     edx, 1
0x180019bae  jz      loc_180019CDD
0x180019bb4  sub     edx, 1
0x180019bb7  jz      loc_180019CDD
0x180019bbd  sub     edx, 1
0x180019bc0  jz      short loc_180019C0C
0x180019bc2  sub     edx, 1
0x180019bc5  jz      short loc_180019BF6
0x180019bc7  cmp     edx, 1
0x180019bca  jnz     loc_180019D69
0x180019bd0  xor     edi, edi
0x180019bd2  lea     rdx, [rbp+arg_8]
0x180019bd6  mov     [rbp+arg_8], edi
0x180019bd9  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180019bde  mov     ecx, [rbp+arg_8]
0x180019be1  mov     eax, [rbx+18h]
0x180019be4  mov     edx, [rbx+20h]
0x180019be7  sub     eax, edx
0x180019be9  cmp     ecx, eax
0x180019beb  ja      loc_180019D69
0x180019bf1  lea     eax, [rdx+rcx]
0x180019bf4  jmp     short loc_180019C20
0x180019bf6  mov     eax, [rbx+18h]
0x180019bf9  mov     ecx, [rcx+20h]
0x180019bfc  sub     eax, ecx
0x180019bfe  cmp     eax, 8
0x180019c01  jb      loc_180019D69
0x180019c07  lea     eax, [rcx+8]
0x180019c0a  jmp     short loc_180019C20
0x180019c0c  mov     eax, [rbx+18h]
0x180019c0f  mov     ecx, [rcx+20h]
0x180019c12  sub     eax, ecx
0x180019c14  cmp     eax, 4
0x180019c17  jb      loc_180019D69
0x180019c1d  lea     eax, [rcx+4]
0x180019c20  mov     [rbx+20h], eax
0x180019c23  jmp     loc_180019D69
0x180019c28  mov     eax, 2
0x180019c2d  xor     edi, edi
0x180019c2f  cmp     ax, [rcx+28h]
0x180019c33  jz      short loc_180019BD2
0x180019c35  xor     edx, edx
0x180019c37  mov     rcx, rbx
0x180019c3a  call    ?ReadStructBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAX_N@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadStructBegin(bool)
0x180019c3f  lea     r8, [rbp+arg_8]
0x180019c43  mov     word ptr [rbp+arg_8], di
0x180019c47  lea     rdx, [rbp+arg_10]
0x180019c4b  mov     dword ptr [rbp+arg_10], edi
0x180019c4e  mov     rcx, rbx; this
0x180019c51  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180019c56  mov     eax, dword ptr [rbp+arg_10]
0x180019c59  test    eax, eax
0x180019c5b  jz      loc_180019D69
0x180019c61  cmp     eax, 1
0x180019c64  jz      short loc_180019C87
0x180019c66  mov     edx, eax
0x180019c68  mov     rcx, rbx; this
0x180019c6b  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180019c70  lea     r8, [rbp+arg_8]
0x180019c74  mov     rcx, rbx; this
0x180019c77  lea     rdx, [rbp+arg_10]
0x180019c7b  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180019c80  mov     eax, dword ptr [rbp+arg_10]
0x180019c83  test    eax, eax
0x180019c85  jnz     short loc_180019C61
0x180019c87  test    eax, eax
0x180019c89  jnz     short loc_180019C35
0x180019c8b  jmp     loc_180019D69
0x180019c90  sub     edx, 0Bh
0x180019c93  jz      loc_180019D3D
0x180019c99  sub     edx, 1
0x180019c9c  jz      loc_180019D3D
0x180019ca2  sub     edx, 1
0x180019ca5  jz      short loc_180019D03
0x180019ca7  sub     edx, 1
0x180019caa  jz      short loc_180019CEE
0x180019cac  sub     edx, 1
0x180019caf  jz      short loc_180019CDD
0x180019cb1  sub     edx, 1
0x180019cb4  jz      short loc_180019CDD
0x180019cb6  sub     edx, 1
0x180019cb9  jz      short loc_180019CDD
0x180019cbb  cmp     edx, 1
0x180019cbe  jnz     loc_180019D69
0x180019cc4  xor     edi, edi
0x180019cc6  lea     rdx, [rbp+arg_8]
0x180019cca  mov     [rbp+arg_8], edi
0x180019ccd  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180019cd2  mov     eax, [rbp+arg_8]
0x180019cd5  lea     ecx, [rax+rax]
0x180019cd8  jmp     loc_180019BE1
0x180019cdd  xor     edi, edi
0x180019cdf  lea     rdx, [rbp+arg_10]
0x180019ce3  mov     [rbp+arg_10], rdi
0x180019ce7  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180019cec  jmp     short loc_180019D69
0x180019cee  mov     eax, [rbx+18h]
0x180019cf1  mov     ecx, [rcx+20h]
0x180019cf4  sub     eax, ecx
0x180019cf6  cmp     eax, 1
0x180019cf9  jb      short loc_180019D69
0x180019cfb  lea     eax, [rcx+1]
0x180019cfe  jmp     loc_180019C20
0x180019d03  xor     edi, edi
0x180019d05  lea     r8, [rbp+arg_10]
0x180019d09  lea     rdx, [rbp+arg_8]
0x180019d0d  mov     [rbp+arg_10], rdi
0x180019d11  mov     [rbp+arg_8], edi
0x180019d14  call    ?ReadContainerBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAIAEAU?$pair@W4BondDataType@1_bond_enumerators@bond@@W41123@@std@@@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(uint &,std::pair<bond::_bond_enumerators::BondDataType::BondDataType,bond::_bond_enumerators::BondDataType::BondDataType> &)
0x180019d19  cmp     [rbp+arg_8], edi
0x180019d1c  jbe     short loc_180019D69
0x180019d1e  mov     edx, dword ptr [rbp+arg_10]
0x180019d21  mov     rcx, rbx; this
0x180019d24  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180019d29  mov     edx, dword ptr [rbp+arg_10+4]
0x180019d2c  mov     rcx, rbx; this
0x180019d2f  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180019d34  inc     edi
0x180019d36  cmp     edi, [rbp+arg_8]
0x180019d39  jb      short loc_180019D1E
0x180019d3b  jmp     short loc_180019D69
0x180019d3d  xor     edi, edi
0x180019d3f  lea     r8, [rbp+arg_10]
0x180019d43  lea     rdx, [rbp+arg_8]
0x180019d47  mov     dword ptr [rbp+arg_10], edi
0x180019d4a  mov     [rbp+arg_8], edi
0x180019d4d  call    ?ReadContainerBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAIAEAW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(uint &,bond::_bond_enumerators::BondDataType::BondDataType &)
0x180019d52  cmp     [rbp+arg_8], edi
0x180019d55  jbe     short loc_180019D69
0x180019d57  mov     edx, dword ptr [rbp+arg_10]
0x180019d5a  mov     rcx, rbx; this
0x180019d5d  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180019d62  inc     edi
0x180019d64  cmp     edi, [rbp+arg_8]
0x180019d67  jb      short loc_180019D57
0x180019d69  mov     rbx, [rsp+20h+arg_0]
0x180019d6e  mov     rdi, [rsp+20h+arg_18]
0x180019d73  add     rsp, 20h
0x180019d77  pop     rbp
0x180019d78  retn
```
