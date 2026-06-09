# bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)

- ea: `0x180015e78`
- end: `0x1800160b9`
- name: `?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z`
- size: `577`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `38`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000f0c8`
- `0x18000fbc0`
- `0x1800105e0`
- `0x1800105fc`
- `0x180010618`
- `0x180010634`
- `0x180010650`
- `0x18001066c`
- `0x180010688`
- `0x1800106d8`
- `0x180010728`
- `0x180010778`
- `0x1800107c8`
- `0x180015e78`
- `0x180017784`
- `0x180017dd8`
- `0x180018608`
- `0x180018658`
- `0x1800186a8`
- `0x1800186f8`
- `0x180018748`
- `0x180018798`
- `0x1800187e8`
- `0x18001a9d8`
- `0x18001aa78`
- `0x18001ab18`
- `0x18001ba7c`
- `0x18001bfdc`
- `0x18001c0a0`
- `0x18001c218`
- `0x18001cc34`
- `0x18001cc78`
- `0x18001cc94`
- `0x18001cce4`
- `0x18001cd34`
- `0x18001cd80`
- `0x18001cd9c`
- `0x18001cde8`

## callees

- `0x180010150`
- `0x1800101a4`
- `0x180015508`
- `0x180015544`
- `0x1800155b8`
- `0x180015e78`

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
  unsigned int v26; // [rsp+48h] [rbp+28h] BYREF
  __int64 v27; // [rsp+50h] [rbp+30h]

  if ( a2 > 10 )
  {
    v16 = a2 - 11;
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      v25 = 0;
      LODWORD(v27) = 0;
      v26 = 0;
      bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(this);
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
      LODWORD(v27) = 0;
      LOBYTE(v26) = 0;
      bond::InputBuffer::Read(this, (unsigned __int8 *)&v26);
      bond::InputBuffer::Read(this, (unsigned __int8 *)&v26);
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this);
      if ( (_DWORD)v27 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          ++v24;
        }
        while ( v24 < (unsigned int)v27 );
      }
      return;
    }
    v19 = v18 - 1;
    if ( !v19 )
      goto LABEL_37;
    v20 = v19 - 1;
    if ( !v20 || (v21 = v20 - 1) == 0 || (v22 = v21 - 1) == 0 )
    {
LABEL_36:
      v27 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(this);
      return;
    }
    if ( v22 == 1 )
    {
      v26 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this);
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
          goto LABEL_36;
        }
      }
LABEL_37:
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
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this);
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
      if ( *((_WORD *)this + 20) == 2 )
      {
        v26 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this);
      }
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
0x180015e78  mov     [rsp-18h+arg_0], rbx
0x180015e7d  mov     [rsp-18h+arg_18], rsi
0x180015e82  push    rbp
0x180015e83  push    rdi
0x180015e84  push    r14
0x180015e86  mov     rbp, rsp
0x180015e89  sub     rsp, 20h
0x180015e8d  mov     rbx, rcx
0x180015e90  cmp     edx, 0Ah
0x180015e93  jg      loc_180015FAA
0x180015e99  jz      loc_180015F37
0x180015e9f  sub     edx, 2
0x180015ea2  jz      loc_18001600B
0x180015ea8  sub     edx, 1
0x180015eab  jz      loc_18001600B
0x180015eb1  sub     edx, 1
0x180015eb4  jz      loc_180015FF7
0x180015eba  sub     edx, 1
0x180015ebd  jz      loc_180015FF7
0x180015ec3  sub     edx, 1
0x180015ec6  jz      loc_180015FF7
0x180015ecc  sub     edx, 1
0x180015ecf  jz      short loc_180015F1B
0x180015ed1  sub     edx, 1
0x180015ed4  jz      short loc_180015F05
0x180015ed6  cmp     edx, 1
0x180015ed9  jnz     loc_1800160A6
0x180015edf  xor     edi, edi
0x180015ee1  lea     rdx, [rbp+arg_8]
0x180015ee5  mov     [rbp+arg_8], edi
0x180015ee8  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180015eed  mov     ecx, [rbp+arg_8]
0x180015ef0  mov     eax, [rbx+18h]
0x180015ef3  mov     edx, [rbx+20h]
0x180015ef6  sub     eax, edx
0x180015ef8  cmp     ecx, eax
0x180015efa  ja      loc_1800160A6
0x180015f00  lea     eax, [rdx+rcx]
0x180015f03  jmp     short loc_180015F2F
0x180015f05  mov     eax, [rbx+18h]
0x180015f08  mov     ecx, [rcx+20h]
0x180015f0b  sub     eax, ecx
0x180015f0d  cmp     eax, 8
0x180015f10  jb      loc_1800160A6
0x180015f16  lea     eax, [rcx+8]
0x180015f19  jmp     short loc_180015F2F
0x180015f1b  mov     eax, [rbx+18h]
0x180015f1e  mov     ecx, [rcx+20h]
0x180015f21  sub     eax, ecx
0x180015f23  cmp     eax, 4
0x180015f26  jb      loc_1800160A6
0x180015f2c  lea     eax, [rcx+4]
0x180015f2f  mov     [rbx+20h], eax
0x180015f32  jmp     loc_1800160A6
0x180015f37  mov     esi, 2
0x180015f3c  xor     edi, edi
0x180015f3e  cmp     si, [rcx+28h]
0x180015f42  jz      short loc_180015EE1
0x180015f44  cmp     si, [rbx+28h]
0x180015f48  jnz     short loc_180015F59
0x180015f4a  lea     rdx, [rbp+arg_8]
0x180015f4e  mov     [rbp+arg_8], edi
0x180015f51  mov     rcx, rbx; this
0x180015f54  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180015f59  lea     r8, [rbp+arg_8]
0x180015f5d  mov     word ptr [rbp+arg_8], di
0x180015f61  lea     rdx, [rbp+arg_10]
0x180015f65  mov     dword ptr [rbp+arg_10], edi
0x180015f68  mov     rcx, rbx; this
0x180015f6b  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180015f70  mov     eax, dword ptr [rbp+arg_10]
0x180015f73  test    eax, eax
0x180015f75  jz      loc_1800160A6
0x180015f7b  cmp     eax, 1
0x180015f7e  jz      short loc_180015FA1
0x180015f80  mov     edx, eax
0x180015f82  mov     rcx, rbx; this
0x180015f85  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180015f8a  lea     r8, [rbp+arg_8]
0x180015f8e  mov     rcx, rbx; this
0x180015f91  lea     rdx, [rbp+arg_10]
0x180015f95  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180015f9a  mov     eax, dword ptr [rbp+arg_10]
0x180015f9d  test    eax, eax
0x180015f9f  jnz     short loc_180015F7B
0x180015fa1  test    eax, eax
0x180015fa3  jnz     short loc_180015F44
0x180015fa5  jmp     loc_1800160A6
0x180015faa  sub     edx, 0Bh
0x180015fad  jz      loc_18001607A
0x180015fb3  sub     edx, 1
0x180015fb6  jz      loc_18001607A
0x180015fbc  sub     edx, 1
0x180015fbf  jz      short loc_180016024
0x180015fc1  sub     edx, 1
0x180015fc4  jz      short loc_18001600B
0x180015fc6  sub     edx, 1
0x180015fc9  jz      short loc_180015FF7
0x180015fcb  sub     edx, 1
0x180015fce  jz      short loc_180015FF7
0x180015fd0  sub     edx, 1
0x180015fd3  jz      short loc_180015FF7
0x180015fd5  cmp     edx, 1
0x180015fd8  jnz     loc_1800160A6
0x180015fde  xor     edi, edi
0x180015fe0  lea     rdx, [rbp+arg_8]
0x180015fe4  mov     [rbp+arg_8], edi
0x180015fe7  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180015fec  mov     eax, [rbp+arg_8]
0x180015fef  lea     ecx, [rax+rax]
0x180015ff2  jmp     loc_180015EF0
0x180015ff7  xor     edi, edi
0x180015ff9  lea     rdx, [rbp+arg_10]
0x180015ffd  mov     [rbp+arg_10], rdi
0x180016001  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x180016006  jmp     loc_1800160A6
0x18001600b  mov     eax, [rbx+18h]
0x18001600e  mov     ecx, [rcx+20h]
0x180016011  sub     eax, ecx
0x180016013  cmp     eax, 1
0x180016016  jb      loc_1800160A6
0x18001601c  lea     eax, [rcx+1]
0x18001601f  jmp     loc_180015F2F
0x180016024  xor     edi, edi
0x180016026  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x18001602a  mov     dword ptr [rbp+arg_10], edi
0x18001602d  mov     byte ptr [rbp+arg_8], dil
0x180016031  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180016036  movzx   esi, byte ptr [rbp+arg_8]
0x18001603a  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x18001603e  mov     rcx, rbx; this
0x180016041  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180016046  movzx   r14d, byte ptr [rbp+arg_8]
0x18001604b  lea     rdx, [rbp+arg_10]
0x18001604f  mov     rcx, rbx; this
0x180016052  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180016057  cmp     dword ptr [rbp+arg_10], edi
0x18001605a  jbe     short loc_1800160A6
0x18001605c  mov     edx, esi
0x18001605e  mov     rcx, rbx; this
0x180016061  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180016066  mov     edx, r14d
0x180016069  mov     rcx, rbx; this
0x18001606c  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180016071  inc     edi
0x180016073  cmp     edi, dword ptr [rbp+arg_10]
0x180016076  jb      short loc_18001605C
0x180016078  jmp     short loc_1800160A6
0x18001607a  xor     edi, edi
0x18001607c  lea     r8, [rbp+arg_10]
0x180016080  lea     rdx, [rbp+arg_8]
0x180016084  mov     dword ptr [rbp+arg_10], edi
0x180016087  mov     [rbp+arg_8], edi
0x18001608a  call    ?ReadContainerBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAIAEAW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadContainerBegin(uint &,bond::_bond_enumerators::BondDataType::BondDataType &)
0x18001608f  cmp     [rbp+arg_8], edi
0x180016092  jbe     short loc_1800160A6
0x180016094  mov     edx, dword ptr [rbp+arg_10]
0x180016097  mov     rcx, rbx; this
0x18001609a  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x18001609f  inc     edi
0x1800160a1  cmp     edi, [rbp+arg_8]
0x1800160a4  jb      short loc_180016094
0x1800160a6  mov     rbx, [rsp+20h+arg_0]
0x1800160ab  mov     rsi, [rsp+20h+arg_18]
0x1800160b0  add     rsp, 20h
0x1800160b4  pop     r14
0x1800160b6  pop     rdi
0x1800160b7  pop     rbp
0x1800160b8  retn
```
