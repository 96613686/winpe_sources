# bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)

- ea: `0x180022000`
- end: `0x18002226d`
- name: `?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z`
- size: `621`
- prototype: `__int64 __fastcall(bond::InputBuffer *this)`
- caller_count: `62`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180009cb0`
- `0x180009d50`
- `0x180009df0`
- `0x180009e90`
- `0x180009f30`
- `0x18000d8e4`
- `0x18000d9c4`
- `0x18000daa8`
- `0x18000db90`
- `0x18000dc54`
- `0x18000dd18`
- `0x18000de00`
- `0x18000f590`
- `0x180010ebc`
- `0x180010ed8`
- `0x180010ef4`
- `0x180010f10`
- `0x180010f2c`
- `0x180010f48`
- `0x180010f64`
- `0x180010f80`
- `0x180010fd0`
- `0x180011020`
- `0x180011070`
- `0x1800110c0`
- `0x180011110`
- `0x180011160`
- `0x1800111b0`
- `0x180011200`
- `0x180011250`
- `0x1800112a0`
- `0x1800112f0`
- `0x18001133c`
- `0x180011388`
- `0x1800113d4`
- `0x180011420`
- `0x18001146c`
- `0x1800114bc`
- `0x18001150c`
- `0x18001155c`
- `0x1800115ac`
- `0x1800115fc`
- `0x18001164c`
- `0x18001169c`
- `0x1800116ec`
- `0x18001173c`
- `0x18001178c`
- `0x1800117dc`
- `0x18001182c`
- `0x18001187c`

## callees

- `0x18000f9c0`
- `0x18000fa14`
- `0x180020960`
- `0x18002099c`
- `0x180022000`

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
  unsigned int v26; // esi
  unsigned int v27; // [rsp+58h] [rbp+38h] BYREF
  unsigned __int64 v28; // [rsp+60h] [rbp+40h] BYREF

  if ( a2 > 10 )
  {
    v16 = a2 - 11;
    if ( !v16 || (v17 = v16 - 1) == 0 )
    {
      v25 = 0;
      LODWORD(v28) = 0;
      LOBYTE(v27) = 0;
      bond::InputBuffer::Read(this, (unsigned __int8 *)&v27);
      if ( *((_WORD *)this + 20) == 2 && (v27 & 0xE0) != 0 )
      {
        v26 = ((unsigned __int8)v27 >> 5) - 1;
      }
      else
      {
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this, &v28);
        v26 = v28;
      }
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
      LODWORD(v28) = 0;
      LOBYTE(v27) = 0;
      bond::InputBuffer::Read(this, (unsigned __int8 *)&v27);
      bond::InputBuffer::Read(this, (unsigned __int8 *)&v27);
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this, &v28);
      if ( (_DWORD)v28 )
      {
        do
        {
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
          ++v24;
        }
        while ( v24 < (unsigned int)v28 );
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
      v28 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(this, &v28);
      return;
    }
    if ( v22 == 1 )
    {
      v27 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this, &v27);
      v10 = 2 * v27;
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
      v27 = 0;
      bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this, &v27);
      v10 = v27;
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
        v27 = 0;
        bond::InputBuffer::ReadVariableUnsigned<unsigned int>(this, &v27);
      }
      LOWORD(v27) = 0;
      LODWORD(v28) = 0;
      bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
      v15 = v28;
      if ( !(_DWORD)v28 )
        break;
      do
      {
        if ( v15 == 1 )
          break;
        bond::CompactBinaryReader<bond::InputBuffer>::Skip(this);
        bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(this);
        v15 = v28;
      }
      while ( (_DWORD)v28 );
    }
    while ( v15 );
  }
}

```

## disassembly

```asm
0x180022000  mov     [rsp-28h+arg_0], rbx
0x180022005  push    rbp
0x180022006  push    rsi
0x180022007  push    rdi
0x180022008  push    r14
0x18002200a  push    r15
0x18002200c  mov     rbp, rsp
0x18002200f  sub     rsp, 20h
0x180022013  mov     rbx, rcx
0x180022016  cmp     edx, 0Ah
0x180022019  jg      loc_180022133
0x18002201f  jz      loc_1800220BD
0x180022025  sub     edx, 2
0x180022028  jz      loc_180022194
0x18002202e  sub     edx, 1
0x180022031  jz      loc_180022194
0x180022037  sub     edx, 1
0x18002203a  jz      loc_180022180
0x180022040  sub     edx, 1
0x180022043  jz      loc_180022180
0x180022049  sub     edx, 1
0x18002204c  jz      loc_180022180
0x180022052  sub     edx, 1
0x180022055  jz      short loc_1800220A1
0x180022057  sub     edx, 1
0x18002205a  jz      short loc_18002208B
0x18002205c  cmp     edx, 1
0x18002205f  jnz     loc_18002225C
0x180022065  xor     edi, edi
0x180022067  lea     rdx, [rbp+arg_8]
0x18002206b  mov     [rbp+arg_8], edi
0x18002206e  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180022073  mov     ecx, [rbp+arg_8]
0x180022076  mov     eax, [rbx+18h]
0x180022079  mov     edx, [rbx+20h]
0x18002207c  sub     eax, edx
0x18002207e  cmp     ecx, eax
0x180022080  ja      loc_18002225C
0x180022086  lea     eax, [rdx+rcx]
0x180022089  jmp     short loc_1800220B5
0x18002208b  mov     eax, [rbx+18h]
0x18002208e  mov     ecx, [rcx+20h]
0x180022091  sub     eax, ecx
0x180022093  cmp     eax, 8
0x180022096  jb      loc_18002225C
0x18002209c  lea     eax, [rcx+8]
0x18002209f  jmp     short loc_1800220B5
0x1800220a1  mov     eax, [rbx+18h]
0x1800220a4  mov     ecx, [rcx+20h]
0x1800220a7  sub     eax, ecx
0x1800220a9  cmp     eax, 4
0x1800220ac  jb      loc_18002225C
0x1800220b2  lea     eax, [rcx+4]
0x1800220b5  mov     [rbx+20h], eax
0x1800220b8  jmp     loc_18002225C
0x1800220bd  mov     r14d, 2
0x1800220c3  xor     edi, edi
0x1800220c5  cmp     r14w, [rcx+28h]
0x1800220ca  jz      short loc_180022067
0x1800220cc  cmp     r14w, [rbx+28h]
0x1800220d1  jnz     short loc_1800220E2
0x1800220d3  lea     rdx, [rbp+arg_8]
0x1800220d7  mov     [rbp+arg_8], edi
0x1800220da  mov     rcx, rbx; this
0x1800220dd  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x1800220e2  lea     r8, [rbp+arg_8]
0x1800220e6  mov     word ptr [rbp+arg_8], di
0x1800220ea  lea     rdx, [rbp+arg_10]
0x1800220ee  mov     dword ptr [rbp+arg_10], edi
0x1800220f1  mov     rcx, rbx; this
0x1800220f4  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x1800220f9  mov     eax, dword ptr [rbp+arg_10]
0x1800220fc  test    eax, eax
0x1800220fe  jz      loc_18002225C
0x180022104  cmp     eax, 1
0x180022107  jz      short loc_18002212A
0x180022109  mov     edx, eax
0x18002210b  mov     rcx, rbx; this
0x18002210e  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180022113  lea     r8, [rbp+arg_8]
0x180022117  mov     rcx, rbx; this
0x18002211a  lea     rdx, [rbp+arg_10]
0x18002211e  call    ?ReadFieldBegin@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXAEAW4BondDataType@3_bond_enumerators@2@AEAG@Z; bond::CompactBinaryReader<bond::InputBuffer>::ReadFieldBegin(bond::_bond_enumerators::BondDataType::BondDataType &,ushort &)
0x180022123  mov     eax, dword ptr [rbp+arg_10]
0x180022126  test    eax, eax
0x180022128  jnz     short loc_180022104
0x18002212a  test    eax, eax
0x18002212c  jnz     short loc_1800220CC
0x18002212e  jmp     loc_18002225C
0x180022133  sub     edx, 0Bh
0x180022136  jz      loc_180022203
0x18002213c  sub     edx, 1
0x18002213f  jz      loc_180022203
0x180022145  sub     edx, 1
0x180022148  jz      short loc_1800221AD
0x18002214a  sub     edx, 1
0x18002214d  jz      short loc_180022194
0x18002214f  sub     edx, 1
0x180022152  jz      short loc_180022180
0x180022154  sub     edx, 1
0x180022157  jz      short loc_180022180
0x180022159  sub     edx, 1
0x18002215c  jz      short loc_180022180
0x18002215e  cmp     edx, 1
0x180022161  jnz     loc_18002225C
0x180022167  xor     edi, edi
0x180022169  lea     rdx, [rbp+arg_8]
0x18002216d  mov     [rbp+arg_8], edi
0x180022170  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180022175  mov     eax, [rbp+arg_8]
0x180022178  lea     ecx, [rax+rax]
0x18002217b  jmp     loc_180022076
0x180022180  xor     edi, edi
0x180022182  lea     rdx, [rbp+arg_10]
0x180022186  mov     [rbp+arg_10], rdi
0x18002218a  call    ??$ReadVariableUnsigned@_K@InputBuffer@bond@@QEAAXAEA_K@Z; bond::InputBuffer::ReadVariableUnsigned<unsigned __int64>(unsigned __int64 &)
0x18002218f  jmp     loc_18002225C
0x180022194  mov     eax, [rbx+18h]
0x180022197  mov     ecx, [rcx+20h]
0x18002219a  sub     eax, ecx
0x18002219c  cmp     eax, 1
0x18002219f  jb      loc_18002225C
0x1800221a5  lea     eax, [rcx+1]
0x1800221a8  jmp     loc_1800220B5
0x1800221ad  xor     edi, edi
0x1800221af  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x1800221b3  mov     dword ptr [rbp+arg_10], edi
0x1800221b6  mov     byte ptr [rbp+arg_8], dil
0x1800221ba  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x1800221bf  movzx   esi, byte ptr [rbp+arg_8]
0x1800221c3  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x1800221c7  mov     rcx, rbx; this
0x1800221ca  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x1800221cf  movzx   r14d, byte ptr [rbp+arg_8]
0x1800221d4  lea     rdx, [rbp+arg_10]
0x1800221d8  mov     rcx, rbx; this
0x1800221db  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x1800221e0  cmp     dword ptr [rbp+arg_10], edi
0x1800221e3  jbe     short loc_18002225C
0x1800221e5  mov     edx, esi
0x1800221e7  mov     rcx, rbx; this
0x1800221ea  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x1800221ef  mov     edx, r14d
0x1800221f2  mov     rcx, rbx; this
0x1800221f5  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x1800221fa  inc     edi
0x1800221fc  cmp     edi, dword ptr [rbp+arg_10]
0x1800221ff  jb      short loc_1800221E5
0x180022201  jmp     short loc_18002225C
0x180022203  xor     edi, edi
0x180022205  lea     rdx, [rbp+arg_8]; unsigned __int8 *
0x180022209  mov     dword ptr [rbp+arg_10], edi
0x18002220c  mov     byte ptr [rbp+arg_8], dil
0x180022210  call    ?Read@InputBuffer@bond@@QEAAXAEAE@Z; bond::InputBuffer::Read(uchar &)
0x180022215  movzx   eax, byte ptr [rbp+arg_8]
0x180022219  lea     r14d, [rdi+2]
0x18002221d  mov     r15d, eax
0x180022220  mov     esi, eax
0x180022222  and     r15d, 1Fh
0x180022226  cmp     r14w, [rbx+28h]
0x18002222b  jnz     short loc_180022238
0x18002222d  test    al, 0E0h
0x18002222f  jz      short loc_180022238
0x180022231  shr     esi, 5
0x180022234  dec     esi
0x180022236  jmp     short loc_180022247
0x180022238  lea     rdx, [rbp+arg_10]
0x18002223c  mov     rcx, rbx; this
0x18002223f  call    ??$ReadVariableUnsigned@I@InputBuffer@bond@@QEAAXAEAI@Z; bond::InputBuffer::ReadVariableUnsigned<uint>(uint &)
0x180022244  mov     esi, dword ptr [rbp+arg_10]
0x180022247  test    esi, esi
0x180022249  jz      short loc_18002225C
0x18002224b  mov     edx, r15d
0x18002224e  mov     rcx, rbx; this
0x180022251  call    ?Skip@?$CompactBinaryReader@VInputBuffer@bond@@@bond@@QEAAXW4BondDataType@3_bond_enumerators@2@@Z; bond::CompactBinaryReader<bond::InputBuffer>::Skip(bond::_bond_enumerators::BondDataType::BondDataType)
0x180022256  inc     edi
0x180022258  cmp     edi, esi
0x18002225a  jb      short loc_18002224B
0x18002225c  mov     rbx, [rsp+20h+arg_0]
0x180022261  add     rsp, 20h
0x180022265  pop     r15
0x180022267  pop     r14
0x180022269  pop     rdi
0x18002226a  pop     rsi
0x18002226b  pop     rbp
0x18002226c  retn
```
