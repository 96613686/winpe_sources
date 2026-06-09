# CPersistStreamInit::WriteColumnTypeInfo(CRowInfo &,ushort)

- ea: `0x18001d3b4`
- end: `0x18001d91e`
- name: `?WriteColumnTypeInfo@CPersistStreamInit@@AEAAJAEAVCRowInfo@@G@Z`
- size: `1386`
- prototype: `__int64 __fastcall(CPersistStreamInit *__hidden this, struct CRowInfo *, unsigned __int16)`
- caller_count: `1`
- callee_count: `17`
- tags: ``

## callers

- `0x18001ca70`

## callees

- `0x180003abc`
- `0x180004038`
- `0x1800040a8`
- `0x18000416c`
- `0x1800041ac`
- `0x1800041f8`
- `0x180015370`
- `0x180015f14`
- `0x18001b728`
- `0x18001c818`
- `0x18001d3b4`
- `0x18001e348`
- `0x18001f470`
- `0x18001f7b4`
- `0x18001f818`
- `0x180028dbc`
- `0x18002e060`

## import_xrefs

- `OLEAUT32!__imp_GetErrorInfo` at `0x18001d8a7`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001d8a7`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CPersistStreamInit::WriteColumnTypeInfo(
        CPersistStreamInit *this,
        struct CRowInfo *a2,
        unsigned __int16 a3)
{
  unsigned __int16 v6; // r15
  unsigned __int16 v7; // dx
  int v8; // ebx
  unsigned __int16 v9; // di
  int v10; // esi
  bool v11; // r9
  bool v12; // r9
  unsigned __int64 v13; // r9
  unsigned int Size; // edx
  bool v15; // r9
  unsigned int v16; // eax
  int v17; // ecx
  unsigned __int8 Scale; // al
  unsigned __int64 v19; // r9
  bool v20; // r9
  unsigned __int8 Precision; // al
  unsigned __int64 v22; // r9
  bool v23; // r9
  char v24; // bl
  unsigned __int16 *Name; // rax
  OLECHAR *v26; // r8
  int v28; // [rsp+20h] [rbp-E0h]
  unsigned int v29; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int Flags; // [rsp+34h] [rbp-CCh]
  _BYTE v31[8]; // [rsp+38h] [rbp-C8h] BYREF
  IErrorInfo *pperrinfo; // [rsp+40h] [rbp-C0h] BYREF
  int v33; // [rsp+48h] [rbp-B8h]
  __int64 v34; // [rsp+50h] [rbp-B0h]
  unsigned __int16 v35[256]; // [rsp+60h] [rbp-A0h] BYREF

  v29 = 0;
  v6 = CMetaData::mdGetType(a2, a3) & 0xBFFF;
  Flags = CMetaData::mdGetFlags(a2, v7);
  if ( (v6 & 0xB000) != 0 )
    goto LABEL_86;
  if ( v6 > 0x40u )
  {
    v8 = 72;
    switch ( v6 )
    {
      case 0x48u:
        v8 = 89;
        goto LABEL_54;
      case 0x80u:
        v8 = 74;
        goto LABEL_54;
      case 0x81u:
        v8 = 75;
        v9 = 93;
        goto LABEL_55;
      case 0x82u:
        goto LABEL_50;
      case 0x83u:
        v8 = 76;
        v9 = 99;
        goto LABEL_55;
      case 0x85u:
        v8 = 70;
        goto LABEL_54;
      case 0x86u:
        v8 = 71;
        goto LABEL_54;
      case 0x87u:
        v9 = 98;
        goto LABEL_55;
      case 0x8Bu:
        v8 = 76;
        v9 = 100;
        goto LABEL_55;
    }
LABEL_86:
    GetErrorInfo(0, &pperrinfo);
    v33 = 0;
    v34 = 0;
    Name = CMetaData::mdGetName(a2, a3);
    v26 = (OLECHAR *)&strIn;
    if ( Name )
      v26 = Name;
    v10 = -2147217891;
    CPersistErrorCache::AddInternalError((CPersistErrorCache *)v31, -2147217891, v26, 0x90u);
    CPersistErrorCache::~CPersistErrorCache((CPersistErrorCache *)v31);
    return (unsigned int)v10;
  }
  if ( v6 == 64 )
  {
    v8 = 72;
    v9 = 96;
    goto LABEL_55;
  }
  if ( v6 > 0xCu )
  {
    switch ( v6 )
    {
      case 0xEu:
        v8 = 76;
        v9 = 90;
        goto LABEL_55;
      case 0x10u:
        v8 = 84;
        goto LABEL_54;
      case 0x11u:
        v8 = 83;
        goto LABEL_54;
      case 0x12u:
        v8 = 85;
        goto LABEL_54;
      case 0x13u:
        v8 = 86;
        goto LABEL_54;
      case 0x14u:
        v8 = 87;
        goto LABEL_54;
      case 0x15u:
        v8 = 88;
        goto LABEL_54;
    }
    goto LABEL_86;
  }
  switch ( v6 )
  {
    case 0xCu:
      goto LABEL_50;
    case 2u:
      v8 = 79;
      goto LABEL_54;
    case 3u:
      v8 = 78;
      goto LABEL_54;
    case 4u:
      v8 = 81;
      goto LABEL_54;
    case 5u:
      v8 = 77;
      goto LABEL_54;
    case 6u:
      v8 = 76;
      v9 = 91;
      goto LABEL_55;
    case 7u:
      v8 = 72;
      v9 = 97;
      goto LABEL_55;
    case 8u:
LABEL_50:
      v8 = 75;
      goto LABEL_54;
  }
  if ( v6 != 11 )
    goto LABEL_86;
  v8 = 73;
LABEL_54:
  v9 = v8;
LABEL_55:
  CPersistStreamInit::Indent(this, *((_DWORD *)this + 12));
  v10 = CPersistStreamInit::WriteTag(this, 0x30u, &v29);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteNamespace(this, 0x3Fu);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteTag(this, 0xBu, &v29);
  if ( v10 < 0 )
    return (unsigned int)v10;
  v10 = CPersistStreamInit::WriteAttributeDefinition(
          this,
          *(void **)(*((_QWORD *)this + 9) + 64LL),
          *(unsigned __int16 **)(*((_QWORD *)this + 9) + 16LL * v8),
          v11,
          61,
          0);
  if ( v10 < 0 )
    return (unsigned int)v10;
  if ( v8 != v9 )
  {
    v10 = CPersistStreamInit::WriteAttributeDefinition(
            this,
            *(void **)(*((_QWORD *)this + 9) + 1632LL),
            *(unsigned __int16 **)(*((_QWORD *)this + 9) + 16LL * v9),
            v12,
            65,
            0);
    if ( v10 < 0 )
      return (unsigned int)v10;
  }
  if ( v6 == 12 )
  {
    v24 = Flags;
LABEL_82:
    if ( (v24 & 0x40) != 0
      || (v10 = CPersistStreamInit::WriteAttributeDefinition(
                  this,
                  *(void **)(*((_QWORD *)this + 9) + 1856LL),
                  *(unsigned __int16 **)(*((_QWORD *)this + 9) + 848LL),
                  v12,
                  65,
                  0),
          v10 >= 0) )
    {
      v10 = CPersistStreamInit::WriteTag(this, 0x32u, &v29);
      if ( v10 >= 0 )
        return (unsigned int)CPersistStreamInit::WriteTag(this, 0x28u, &v29);
    }
    return (unsigned int)v10;
  }
  if ( IsFixedLength(v6) && CMetaData::mdGetSize(a2, a3) == 255
    || (v6 == 7 || v6 == 64 ? (Size = 16) : (Size = CMetaData::mdGetSize(a2, a3)),
        CPersistStreamInit::_ulto(this, Size, v35, v13, v28),
        v10 = CPersistStreamInit::WriteAttributeDefinition(
                this,
                *(void **)(*((_QWORD *)this + 9) + 1616LL),
                v35,
                v15,
                61,
                0),
        v10 >= 0) )
  {
    if ( v6 == 14
      || (v16 = v6, (unsigned __int16)(v6 - 131) <= 8u) && (v17 = 273, LOWORD(v16) = v6 - 131, _bittest(&v17, v16)) )
    {
      Scale = CMetaData::mdGetScale(a2, a3);
      CPersistStreamInit::_ito(this, Scale, v35, v19, v28);
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1648LL),
              v35,
              v20,
              65,
              0);
      if ( v10 < 0 )
        return (unsigned int)v10;
      if ( v6 == 139 )
        goto LABEL_75;
    }
    if ( CMetaData::mdGetPrecision(a2, a3) != 0xFF )
    {
LABEL_75:
      Precision = CMetaData::mdGetPrecision(a2, a3);
      CPersistStreamInit::_ito(this, Precision, v35, v22, v28);
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1664LL),
              v35,
              v23,
              65,
              0);
      if ( v10 < 0 )
        return (unsigned int)v10;
    }
    v24 = Flags;
    if ( (Flags & 0x10) == 0
      || (v10 = CPersistStreamInit::WriteAttributeDefinition(
                  this,
                  *(void **)(*((_QWORD *)this + 9) + 1776LL),
                  *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
                  v12,
                  65,
                  0),
          v10 >= 0) )
    {
      if ( v24 >= 0 )
        goto LABEL_82;
      v10 = CPersistStreamInit::WriteAttributeDefinition(
              this,
              *(void **)(*((_QWORD *)this + 9) + 1792LL),
              *(unsigned __int16 **)(*((_QWORD *)this + 9) + 832LL),
              v12,
              65,
              0);
      if ( v10 >= 0 )
        goto LABEL_82;
    }
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18001d3b4  mov     [rsp-8+arg_18], rbx
0x18001d3b9  push    rbp
0x18001d3ba  push    rsi
0x18001d3bb  push    rdi
0x18001d3bc  push    r12
0x18001d3be  push    r13
0x18001d3c0  push    r14
0x18001d3c2  push    r15
0x18001d3c4  lea     rbp, [rsp-170h]
0x18001d3cc  sub     rsp, 270h
0x18001d3d3  mov     rax, cs:__security_cookie
0x18001d3da  xor     rax, rsp
0x18001d3dd  mov     [rbp+1A0h+var_40], rax
0x18001d3e4  movzx   r13d, r8w
0x18001d3e8  mov     r12, rdx
0x18001d3eb  mov     r14, rcx
0x18001d3ee  xor     edi, edi
0x18001d3f0  mov     [rsp+2A0h+var_270], edi
0x18001d3f4  movzx   edx, r8w; unsigned __int16
0x18001d3f8  mov     rcx, r12; this
0x18001d3fb  call    ?mdGetType@CMetaData@@QEAAGG@Z; CMetaData::mdGetType(ushort)
0x18001d400  movzx   r15d, ax
0x18001d404  mov     eax, 0BFFFh
0x18001d409  and     r15w, ax
0x18001d40d  mov     rcx, r12; this
0x18001d410  call    ?mdGetFlags@CMetaData@@QEAAKG@Z; CMetaData::mdGetFlags(ushort)
0x18001d415  mov     [rsp+2A0h+var_26C], eax
0x18001d419  mov     eax, 0B000h
0x18001d41e  test    ax, r15w
0x18001d422  jnz     loc_18001D8A0
0x18001d428  movzx   ecx, r15w
0x18001d42c  lea     eax, [rdi+0Ch]
0x18001d42f  lea     edx, [rdi+40h]
0x18001d432  cmp     ecx, edx
0x18001d434  ja      loc_18001D540
0x18001d43a  jz      loc_18001D536
0x18001d440  cmp     ecx, eax
0x18001d442  ja      loc_18001D4C8
0x18001d448  jz      loc_18001D59C
0x18001d44e  sub     ecx, 2
0x18001d451  jz      short loc_18001D4BE
0x18001d453  sub     ecx, 1
0x18001d456  jz      short loc_18001D4B4
0x18001d458  sub     ecx, 1
0x18001d45b  jz      short loc_18001D4AA
0x18001d45d  sub     ecx, 1
0x18001d460  jz      short loc_18001D4A0
0x18001d462  sub     ecx, 1
0x18001d465  jz      short loc_18001D493
0x18001d467  sub     ecx, 1
0x18001d46a  jz      short loc_18001D486
0x18001d46c  sub     ecx, 1
0x18001d46f  jz      loc_18001D59C
0x18001d475  cmp     ecx, 3
0x18001d478  jnz     loc_18001D8A0
0x18001d47e  lea     ebx, [rdi+49h]
0x18001d481  jmp     loc_18001D5B9
0x18001d486  mov     ebx, 48h ; 'H'
0x18001d48b  lea     edi, [rbx+19h]
0x18001d48e  jmp     loc_18001D5BC
0x18001d493  mov     ebx, 4Ch ; 'L'
0x18001d498  lea     edi, [rbx+0Fh]
0x18001d49b  jmp     loc_18001D5BC
0x18001d4a0  mov     ebx, 4Dh ; 'M'
0x18001d4a5  jmp     loc_18001D5B9
0x18001d4aa  mov     ebx, 51h ; 'Q'
0x18001d4af  jmp     loc_18001D5B9
0x18001d4b4  mov     ebx, 4Eh ; 'N'
0x18001d4b9  jmp     loc_18001D5B9
0x18001d4be  mov     ebx, 4Fh ; 'O'
0x18001d4c3  jmp     loc_18001D5B9
0x18001d4c8  sub     ecx, 0Eh
0x18001d4cb  jz      short loc_18001D529
0x18001d4cd  sub     ecx, 2
0x18001d4d0  jz      short loc_18001D51F
0x18001d4d2  sub     ecx, 1
0x18001d4d5  jz      short loc_18001D515
0x18001d4d7  sub     ecx, 1
0x18001d4da  jz      short loc_18001D50B
0x18001d4dc  sub     ecx, 1
0x18001d4df  jz      short loc_18001D501
0x18001d4e1  sub     ecx, 1
0x18001d4e4  jz      short loc_18001D4F7
0x18001d4e6  cmp     ecx, 1
0x18001d4e9  jnz     loc_18001D8A0
0x18001d4ef  lea     ebx, [rcx+57h]
0x18001d4f2  jmp     loc_18001D5B9
0x18001d4f7  mov     ebx, 57h ; 'W'
0x18001d4fc  jmp     loc_18001D5B9
0x18001d501  mov     ebx, 56h ; 'V'
0x18001d506  jmp     loc_18001D5B9
0x18001d50b  mov     ebx, 55h ; 'U'
0x18001d510  jmp     loc_18001D5B9
0x18001d515  mov     ebx, 53h ; 'S'
0x18001d51a  jmp     loc_18001D5B9
0x18001d51f  mov     ebx, 54h ; 'T'
0x18001d524  jmp     loc_18001D5B9
0x18001d529  mov     ebx, 4Ch ; 'L'
0x18001d52e  lea     edi, [rbx+0Eh]
0x18001d531  jmp     loc_18001D5BC
0x18001d536  mov     ebx, 48h ; 'H'
0x18001d53b  lea     edi, [rbx+18h]
0x18001d53e  jmp     short loc_18001D5BC
0x18001d540  mov     ebx, 48h ; 'H'
0x18001d545  sub     ecx, ebx
0x18001d547  jz      short loc_18001D5B4
0x18001d549  sub     ecx, 38h ; '8'
0x18001d54c  jz      short loc_18001D5AD
0x18001d54e  sub     ecx, 1
0x18001d551  jz      short loc_18001D5A3
0x18001d553  sub     ecx, 1
0x18001d556  jz      short loc_18001D59C
0x18001d558  sub     ecx, 1
0x18001d55b  jz      short loc_18001D592
0x18001d55d  sub     ecx, 2
0x18001d560  jz      short loc_18001D58B
0x18001d562  sub     ecx, 1
0x18001d565  jz      short loc_18001D584
0x18001d567  sub     ecx, 1
0x18001d56a  jz      short loc_18001D57D
0x18001d56c  cmp     ecx, 4
0x18001d56f  jnz     loc_18001D8A0
0x18001d575  lea     ebx, [rcx+48h]
0x18001d578  lea     edi, [rcx+60h]
0x18001d57b  jmp     short loc_18001D5BC
0x18001d57d  mov     edi, 62h ; 'b'
0x18001d582  jmp     short loc_18001D5BC
0x18001d584  mov     ebx, 47h ; 'G'
0x18001d589  jmp     short loc_18001D5B9
0x18001d58b  mov     ebx, 46h ; 'F'
0x18001d590  jmp     short loc_18001D5B9
0x18001d592  mov     ebx, 4Ch ; 'L'
0x18001d597  lea     edi, [rbx+17h]
0x18001d59a  jmp     short loc_18001D5BC
0x18001d59c  mov     ebx, 4Bh ; 'K'
0x18001d5a1  jmp     short loc_18001D5B9
0x18001d5a3  mov     ebx, 4Bh ; 'K'
0x18001d5a8  lea     edi, [rbx+12h]
0x18001d5ab  jmp     short loc_18001D5BC
0x18001d5ad  mov     ebx, 4Ah ; 'J'
0x18001d5b2  jmp     short loc_18001D5B9
0x18001d5b4  mov     ebx, 59h ; 'Y'
0x18001d5b9  movzx   edi, bx
0x18001d5bc  mov     edx, [r14+30h]; unsigned int
0x18001d5c0  mov     rcx, r14; this
0x18001d5c3  call    ?Indent@CPersistStreamInit@@AEAAJK@Z; CPersistStreamInit::Indent(ulong)
0x18001d5c8  lea     r8, [rsp+2A0h+var_270]; unsigned int *
0x18001d5cd  mov     dl, 30h ; '0'; unsigned __int8
0x18001d5cf  mov     rcx, r14; this
0x18001d5d2  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d5d7  mov     esi, eax
0x18001d5d9  test    eax, eax
0x18001d5db  js      loc_18001D8F2
0x18001d5e1  mov     dl, 3Fh ; '?'; unsigned __int8
0x18001d5e3  mov     rcx, r14; this
0x18001d5e6  call    ?WriteNamespace@CPersistStreamInit@@AEAAJE@Z; CPersistStreamInit::WriteNamespace(uchar)
0x18001d5eb  mov     esi, eax
0x18001d5ed  test    eax, eax
0x18001d5ef  js      loc_18001D8F2
0x18001d5f5  lea     r8, [rsp+2A0h+var_270]; unsigned int *
0x18001d5fa  mov     dl, 0Bh; unsigned __int8
0x18001d5fc  mov     rcx, r14; this
0x18001d5ff  call    ?WriteTag@CPersistStreamInit@@AEAAJEPEAK@Z; CPersistStreamInit::WriteTag(uchar,ulong *)
0x18001d604  mov     esi, eax
0x18001d606  test    eax, eax
0x18001d608  js      loc_18001D8F2
0x18001d60e  mov     rdx, [r14+48h]
0x18001d612  movsxd  r8, ebx
0x18001d615  add     r8, r8
0x18001d618  mov     [rsp+2A0h+var_278], 0; bool
0x18001d61d  mov     [rsp+2A0h+var_280], 3Dh ; '='; int
0x18001d622  mov     r8, [rdx+r8*8]; unsigned __int16 *
0x18001d626  mov     rdx, [rdx+40h]; void *
0x18001d62a  mov     rcx, r14; this
0x18001d62d  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d632  mov     esi, eax
0x18001d634  test    eax, eax
0x18001d636  js      loc_18001D8F2
0x18001d63c  movzx   eax, di
0x18001d63f  cmp     ebx, eax
0x18001d641  jz      short loc_18001D679
0x18001d643  mov     rdx, [r14+48h]
0x18001d647  movzx   r8d, di
0x18001d64b  add     r8, r8
0x18001d64e  xor     edi, edi
0x18001d650  mov     [rsp+2A0h+var_278], dil; bool
0x18001d655  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001d65a  mov     r8, [rdx+r8*8]; unsigned __int16 *
0x18001d65e  mov     rdx, [rdx+660h]; void *
0x18001d665  mov     rcx, r14; this
0x18001d668  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d66d  mov     esi, eax
0x18001d66f  test    eax, eax
0x18001d671  js      loc_18001D8F2
0x18001d677  jmp     short loc_18001D67B
0x18001d679  xor     edi, edi
0x18001d67b  mov     eax, 0Ch
0x18001d680  cmp     r15w, ax
0x18001d684  jz      loc_18001D845
0x18001d68a  movzx   ecx, r15w; unsigned __int16
0x18001d68e  call    ?IsFixedLength@@YA_NG@Z; IsFixedLength(ushort)
0x18001d693  test    al, al
0x18001d695  jz      short loc_18001D6AA
0x18001d697  movzx   edx, r13w; unsigned __int16
0x18001d69b  mov     rcx, r12; this
0x18001d69e  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x18001d6a3  cmp     eax, 0FFh
0x18001d6a8  jz      short loc_18001D70A
0x18001d6aa  cmp     r15w, 7
0x18001d6af  jz      short loc_18001D6CC
0x18001d6b1  mov     eax, 40h ; '@'
0x18001d6b6  cmp     r15w, ax
0x18001d6ba  jz      short loc_18001D6CC
0x18001d6bc  movzx   edx, r13w; unsigned __int16
0x18001d6c0  mov     rcx, r12; this
0x18001d6c3  call    ?mdGetSize@CMetaData@@QEAAKG@Z; CMetaData::mdGetSize(ushort)
0x18001d6c8  mov     edx, eax
0x18001d6ca  jmp     short loc_18001D6D1
0x18001d6cc  mov     edx, 10h; unsigned int
0x18001d6d1  lea     r8, [rsp+2A0h+var_240]; void *
0x18001d6d6  mov     rcx, r14; this
0x18001d6d9  call    ?_ulto@CPersistStreamInit@@AEBAXKPEAX_KH@Z; CPersistStreamInit::_ulto(ulong,void *,unsigned __int64,int)
0x18001d6de  mov     rdx, [r14+48h]
0x18001d6e2  mov     [rsp+2A0h+var_278], dil; bool
0x18001d6e7  mov     [rsp+2A0h+var_280], 3Dh ; '='; int
0x18001d6ec  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001d6f1  mov     rdx, [rdx+650h]; void *
0x18001d6f8  mov     rcx, r14; this
0x18001d6fb  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d700  mov     esi, eax
0x18001d702  test    eax, eax
0x18001d704  js      loc_18001D8F2
0x18001d70a  mov     eax, 0Eh
0x18001d70f  cmp     r15w, ax
0x18001d713  jz      short loc_18001D72F
0x18001d715  lea     ecx, [rax+75h]
0x18001d718  movzx   eax, r15w
0x18001d71c  sub     ax, cx
0x18001d71f  cmp     ax, 8
0x18001d723  ja      short loc_18001D782
0x18001d725  mov     ecx, 111h
0x18001d72a  bt      ecx, eax
0x18001d72d  jnb     short loc_18001D782
0x18001d72f  movzx   edx, r13w; unsigned __int16
0x18001d733  mov     rcx, r12; this
0x18001d736  call    ?mdGetScale@CMetaData@@QEAAEG@Z; CMetaData::mdGetScale(ushort)
0x18001d73b  movzx   edx, al; int
0x18001d73e  lea     r8, [rsp+2A0h+var_240]; void *
0x18001d743  mov     rcx, r14; this
0x18001d746  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001d74b  mov     rdx, [r14+48h]
0x18001d74f  mov     [rsp+2A0h+var_278], dil; bool
0x18001d754  mov     [rsp+2A0h+var_280], 41h ; 'A'; int
0x18001d759  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001d75e  mov     rdx, [rdx+670h]; void *
0x18001d765  mov     rcx, r14; this
0x18001d768  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d76d  mov     esi, eax
0x18001d76f  test    eax, eax
0x18001d771  js      loc_18001D8F2
0x18001d777  mov     eax, 8Bh
0x18001d77c  cmp     r15w, ax
0x18001d780  jz      short loc_18001D792
0x18001d782  movzx   edx, r13w; unsigned __int16
0x18001d786  mov     rcx, r12; this
0x18001d789  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18001d78e  cmp     al, 0FFh
0x18001d790  jz      short loc_18001D7DA
0x18001d792  movzx   edx, r13w; unsigned __int16
0x18001d796  mov     rcx, r12; this
0x18001d799  call    ?mdGetPrecision@CMetaData@@QEAAEG@Z; CMetaData::mdGetPrecision(ushort)
0x18001d79e  movzx   edx, al; int
0x18001d7a1  lea     r8, [rsp+2A0h+var_240]; void *
0x18001d7a6  mov     rcx, r14; this
0x18001d7a9  call    ?_ito@CPersistStreamInit@@AEBAXHPEAX_KH@Z; CPersistStreamInit::_ito(int,void *,unsigned __int64,int)
0x18001d7ae  mov     rdx, [r14+48h]
0x18001d7b2  mov     [rsp+2A0h+var_278], dil; bool
0x18001d7b7  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001d7bc  lea     r8, [rsp+2A0h+var_240]; unsigned __int16 *
0x18001d7c1  mov     rdx, [rdx+680h]; void *
0x18001d7c8  mov     rcx, r14; this
0x18001d7cb  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d7d0  mov     esi, eax
0x18001d7d2  test    eax, eax
0x18001d7d4  js      loc_18001D8F2
0x18001d7da  mov     ebx, [rsp+2A0h+var_26C]
0x18001d7de  test    bl, 10h
0x18001d7e1  jz      short loc_18001D811
0x18001d7e3  mov     rdx, [r14+48h]
0x18001d7e7  mov     [rsp+2A0h+var_278], dil; bool
0x18001d7ec  mov     [rsp+2A0h+var_280], 41h ; 'A'; char
0x18001d7f1  mov     r8, [rdx+340h]; unsigned __int16 *
0x18001d7f8  mov     rdx, [rdx+6F0h]; void *
0x18001d7ff  mov     rcx, r14; this
0x18001d802  call    ?WriteAttributeDefinition@CPersistStreamInit@@AEAAJPEAX0_NE1@Z; CPersistStreamInit::WriteAttributeDefinition(void *,void *,bool,uchar,bool)
0x18001d807  mov     esi, eax
0x18001d809  test    eax, eax
0x18001d80b  js      loc_18001D8F2
0x18001d811  test    bl, bl
0x18001d813  jns     short loc_18001D849
  ... truncated ...
```
