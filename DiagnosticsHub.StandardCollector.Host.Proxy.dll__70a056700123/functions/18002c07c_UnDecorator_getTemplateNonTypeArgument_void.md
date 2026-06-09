# UnDecorator::getTemplateNonTypeArgument(void)

- ea: `0x18002c07c`
- end: `0x18002c522`
- name: `?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `1190`
- prototype: ``
- caller_count: `8`
- callee_count: `26`
- tags: ``

## callers

- `0x180026360`
- `0x180026718`
- `0x1800267c8`
- `0x180029704`
- `0x18002bafc`
- `0x18002c07c`
- `0x18002cc20`
- `0x18002cdc8`

## callees

- `0x180020450`
- `0x180023c68`
- `0x180023d20`
- `0x180024474`
- `0x1800244b0`
- `0x180024564`
- `0x180024b10`
- `0x180024b44`
- `0x180024c70`
- `0x180024d28`
- `0x180026360`
- `0x180026718`
- `0x180028264`
- `0x1800285a0`
- `0x180028ec4`
- `0x180029704`
- `0x18002a4e0`
- `0x18002b5ac`
- `0x18002ba04`
- `0x18002c07c`
- `0x18002c524`
- `0x18002cc20`
- `0x18002cdc8`
- `0x18002db6c`
- `0x180032370`
- `0x180060110`

## string_xrefs

- `0x18002c519`: ``template-type-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getTemplateNonTypeArgument(__int64 a1, __int64 a2)
{
  _BYTE *v4; // rcx
  int v5; // eax
  int v6; // edi
  struct UnDecorator *v7; // rdx
  const char *v8; // rax
  DName *v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 DecoratedName; // rax
  __int64 v14; // r8
  __int64 v15; // r9
  __int64 v16; // rdx
  int v17; // edi
  int v18; // edi
  int v19; // edi
  int v20; // edi
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rdx
  __int64 v25; // rax
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 SignedDimension; // rax
  __int64 v30; // r8
  __int64 v31; // r9
  _BYTE *v32; // rcx
  __int16 v34; // bx
  __int64 (__fastcall *v35)(_QWORD); // rax
  __int64 v36; // rax
  int v37; // edi
  int v38; // edi
  int v39; // edi
  const char *v40; // rax
  DName *v41; // rax
  _OWORD v42[2]; // [rsp+20h] [rbp-59h] BYREF
  _BYTE v43[24]; // [rsp+40h] [rbp-39h] BYREF
  char v44[8]; // [rsp+58h] [rbp-21h] BYREF
  struct UnDecorator *v45; // [rsp+60h] [rbp-19h]
  char v46; // [rsp+68h] [rbp-11h]
  _QWORD v47[3]; // [rsp+70h] [rbp-9h] BYREF
  char v48[24]; // [rsp+88h] [rbp+Fh] BYREF
  char String[16]; // [rsp+A0h] [rbp+27h] BYREF

  v4 = *(_BYTE **)(a1 + 256);
  v5 = (char)*v4;
  if ( *v4 )
    *(_QWORD *)(a1 + 256) = ++v4;
  v6 = v5;
  if ( v5 > 70 )
  {
    if ( v5 <= 80 )
    {
      switch ( v5 )
      {
        case 'P':
          UnDecorator::getDimension(a1, v43, 0);
          v8 = "lambda";
          *(_DWORD *)&String[8] = 6;
          goto LABEL_43;
        case 'G':
        case 'H':
        case 'I':
        case 'J':
LABEL_46:
          DName::DName((DName *)v42, (struct UnDecorator *)a1, 123);
          if ( v6 == 72 || (unsigned int)(v6 - 73) <= 1 )
          {
            DecoratedName = UnDecorator::getDecoratedName(a1, v43);
            DName::operator+=(v42, DecoratedName, v14, v15);
            LOBYTE(v16) = 44;
            DName::operator+=(v42, v16);
          }
          v17 = v6 - 70;
          if ( !v17 )
            goto LABEL_55;
          v18 = v17 - 1;
          if ( v18 )
          {
            v19 = v18 - 1;
            if ( !v19 )
            {
LABEL_56:
              SignedDimension = UnDecorator::getSignedDimension(a1, v43);
              DName::operator+=(v42, SignedDimension, v30, v31);
              goto LABEL_57;
            }
            v20 = v19 - 1;
            if ( !v20 )
            {
LABEL_55:
              v25 = UnDecorator::getSignedDimension(a1, v43);
              DName::operator+=(v42, v25, v26, v27);
              LOBYTE(v28) = 44;
              DName::operator+=(v42, v28);
              goto LABEL_56;
            }
            if ( v20 != 1 )
            {
LABEL_57:
              LOBYTE(v12) = 125;
              v32 = v42;
LABEL_58:
              DName::operator+(v32, a2, v12);
              return a2;
            }
          }
          v21 = UnDecorator::getSignedDimension(a1, v43);
          DName::operator+=(v42, v21, v22, v23);
          LOBYTE(v24) = 44;
          DName::operator+=(v42, v24);
          goto LABEL_55;
        case 'M':
          UnDecorator::getTemplateTypeArgument(a1, v44);
          if ( v46 <= 1 )
          {
            UnDecorator::getTemplateNonTypeArgument(a1, a2);
            return a2;
          }
          break;
        case 'N':
          v8 = "nullptr";
          *(_DWORD *)&String[8] = 7;
LABEL_43:
          v7 = (struct UnDecorator *)a1;
LABEL_18:
          *(_QWORD *)String = v8;
          v42[0] = *(_OWORD *)String;
          DName::DName((DName *)a2, v7, (const struct StringLiteral *)v42);
          return a2;
      }
LABEL_65:
      v11 = 2;
      goto LABEL_66;
    }
    if ( v5 == 81 )
      goto LABEL_65;
    if ( v5 != 82 )
    {
      if ( v5 == 83 )
      {
        *(_QWORD *)(a2 + 8) = a1;
        *(_QWORD *)a2 = 0;
        *(_DWORD *)(a2 + 16) = 0;
        return a2;
      }
      if ( v5 != 84 && (unsigned int)(v5 - 85) >= 2 )
        goto LABEL_65;
    }
    UnDecorator::getSignedDimension(a1, v47);
    *(_OWORD *)String = 0;
    if ( v47[0] )
      *(_BYTE *)(*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)v47[0] + 24LL))(
                  v47[0],
                  String,
                  &String[15]) = 0;
    v34 = atol(String);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) != 0 )
    {
      v35 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
      if ( v35 )
      {
        v36 = v35(v34 & 0xFFF);
        if ( v36 )
        {
          DName::DName(a2, a1, v36, 0);
          return a2;
        }
      }
    }
    sprintf_s(String, 0x10u, "%d", v34 & 0xFFF);
    DName::DName(v44, a1, String, 0);
    v37 = v6 - 82;
    if ( v37 && (v38 = v37 - 2) != 0 )
    {
      v39 = v38 - 1;
      if ( v39 )
      {
        if ( v39 != 1 )
          goto LABEL_65;
        v40 = "`generic-method-parameter-";
        DWORD2(v42[0]) = 26;
LABEL_80:
        *(_QWORD *)&v42[0] = v40;
        v41 = DName::DName((DName *)v48, v45, (const struct StringLiteral *)v42);
        DName::operator+(v41, v43, v44);
        LOBYTE(v12) = 39;
        v32 = v43;
        goto LABEL_58;
      }
      v40 = "`generic-class-parameter-";
    }
    else
    {
      v40 = "`template-type-parameter-";
    }
    DWORD2(v42[0]) = 25;
    goto LABEL_80;
  }
  if ( v5 == 70 )
    goto LABEL_46;
  if ( v5 > 54 )
  {
    switch ( v5 )
    {
      case '7':
        UnDecorator::getUnionObject(a1);
        return a2;
      case '8':
        UnDecorator::getPointerToMember(a1);
        return a2;
      case 'A':
      case 'B':
        _mm_lfence();
        UnDecorator::getFloatingPoint(a1, a2, (unsigned int)v5);
        return a2;
      case 'C':
        UnDecorator::getArrayAccess(a1);
        return a2;
      case 'E':
        UnDecorator::getDecoratedName(a1, a2);
        return a2;
    }
    goto LABEL_65;
  }
  if ( v5 == 54 )
  {
    UnDecorator::getMemberAccess(a1);
    return a2;
  }
  if ( !(_BYTE)v5 )
  {
    v11 = 1;
LABEL_66:
    DName::DName(a2, a1, v11);
    return a2;
  }
  switch ( v5 )
  {
    case '0':
      UnDecorator::getSignedDimension(a1, a2);
      return a2;
    case '1':
      v7 = (struct UnDecorator *)a1;
      if ( *v4 != 64 )
      {
        v9 = DName::DName((DName *)v43, (struct UnDecorator *)a1, 38);
        v10 = UnDecorator::getDecoratedName(a1, v47);
        DName::operator+(v9, a2, v10);
        return a2;
      }
      *(_DWORD *)&String[8] = 4;
      *(_QWORD *)(a1 + 256) = v4 + 1;
      v8 = "NULL";
      goto LABEL_18;
    case '2':
      UnDecorator::getValueObject(a1);
      return a2;
    case '4':
      UnDecorator::getStringObject(a1);
      return a2;
  }
  if ( v5 != 53 )
    goto LABEL_65;
  UnDecorator::getAddressOf(a1);
  return a2;
}

```

## disassembly

```asm
0x18002c07c  mov     [rsp-8+arg_10], rbx
0x18002c081  mov     [rsp-8+arg_18], rsi
0x18002c086  push    rbp
0x18002c087  push    rdi
0x18002c088  push    r14
0x18002c08a  lea     rbp, [rsp-47h]
0x18002c08f  sub     rsp, 0C0h
0x18002c096  mov     rax, cs:__security_cookie
0x18002c09d  xor     rax, rsp
0x18002c0a0  mov     [rbp+57h+var_20], rax
0x18002c0a4  mov     r14, rcx
0x18002c0a7  mov     rsi, rdx
0x18002c0aa  mov     rcx, [rcx+100h]
0x18002c0b1  movsx   eax, byte ptr [rcx]
0x18002c0b4  test    al, al
0x18002c0b6  jz      short loc_18002C0C2
0x18002c0b8  inc     rcx
0x18002c0bb  mov     [r14+100h], rcx
0x18002c0c2  mov     edi, eax
0x18002c0c4  cmp     eax, 46h ; 'F'
0x18002c0c7  jg      loc_18002C22F
0x18002c0cd  jz      loc_18002C29E
0x18002c0d3  cmp     eax, 36h ; '6'
0x18002c0d6  jg      loc_18002C1C4
0x18002c0dc  jz      loc_18002C1B7
0x18002c0e2  test    al, al
0x18002c0e4  jz      loc_18002C1AC
0x18002c0ea  sub     edi, 30h ; '0'
0x18002c0ed  jz      loc_18002C19F
0x18002c0f3  sub     edi, 1
0x18002c0f6  jz      short loc_18002C132
0x18002c0f8  sub     edi, 1
0x18002c0fb  jz      short loc_18002C125
0x18002c0fd  sub     edi, 2
0x18002c100  jz      short loc_18002C118
0x18002c102  cmp     edi, 1
0x18002c105  jnz     loc_18002C3AB
0x18002c10b  mov     rcx, r14
0x18002c10e  call    ?getAddressOf@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getAddressOf(void)
0x18002c113  jmp     loc_18002C3BC
0x18002c118  mov     rcx, r14
0x18002c11b  call    ?getStringObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getStringObject(void)
0x18002c120  jmp     loc_18002C3BC
0x18002c125  mov     rcx, r14
0x18002c128  call    ?getValueObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getValueObject(void)
0x18002c12d  jmp     loc_18002C3BC
0x18002c132  cmp     byte ptr [rcx], 40h ; '@'
0x18002c135  mov     rdx, r14; struct UnDecorator *
0x18002c138  jnz     short loc_18002C171
0x18002c13a  lea     rax, [rcx+1]
0x18002c13e  mov     dword ptr [rbp+57h+String+8], 4
0x18002c145  mov     [r14+100h], rax
0x18002c14c  lea     rax, aNull; "NULL"
0x18002c153  mov     qword ptr [rbp+57h+String], rax
0x18002c157  lea     r8, [rbp+57h+var_B0]; struct StringLiteral *
0x18002c15b  movaps  xmm0, xmmword ptr [rbp+57h+String]
0x18002c15f  mov     rcx, rsi; this
0x18002c162  movdqa  [rbp+57h+var_B0], xmm0
0x18002c167  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002c16c  jmp     loc_18002C3BC
0x18002c171  mov     r8b, 26h ; '&'; char
0x18002c174  lea     rcx, [rbp+57h+var_90]; this
0x18002c178  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x18002c17d  lea     rdx, [rbp+57h+var_60]
0x18002c181  mov     rcx, r14
0x18002c184  mov     rbx, rax
0x18002c187  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002c18c  mov     r8, rax
0x18002c18f  mov     rdx, rsi
0x18002c192  mov     rcx, rbx
0x18002c195  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002c19a  jmp     loc_18002C3BC
0x18002c19f  mov     rcx, r14
0x18002c1a2  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c1a7  jmp     loc_18002C3BC
0x18002c1ac  mov     r8d, 1
0x18002c1b2  jmp     loc_18002C3B1
0x18002c1b7  mov     rcx, r14
0x18002c1ba  call    ?getMemberAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getMemberAccess(void)
0x18002c1bf  jmp     loc_18002C3BC
0x18002c1c4  mov     ecx, edi
0x18002c1c6  sub     ecx, 37h ; '7'
0x18002c1c9  jz      short loc_18002C222
0x18002c1cb  sub     ecx, 1
0x18002c1ce  jz      short loc_18002C215
0x18002c1d0  sub     ecx, 9
0x18002c1d3  jz      short loc_18002C202
0x18002c1d5  sub     ecx, 1
0x18002c1d8  jz      short loc_18002C202
0x18002c1da  sub     ecx, 1
0x18002c1dd  jz      short loc_18002C1F5
0x18002c1df  cmp     ecx, 2
0x18002c1e2  jnz     loc_18002C3AB
0x18002c1e8  mov     rcx, r14
0x18002c1eb  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002c1f0  jmp     loc_18002C3BC
0x18002c1f5  mov     rcx, r14
0x18002c1f8  call    ?getArrayAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getArrayAccess(void)
0x18002c1fd  jmp     loc_18002C3BC
0x18002c202  lfence
0x18002c205  mov     r8d, edi
0x18002c208  mov     rcx, r14
0x18002c20b  call    ?getFloatingPoint@UnDecorator@@AEAA?AVDName@@H@Z; UnDecorator::getFloatingPoint(int)
0x18002c210  jmp     loc_18002C3BC
0x18002c215  mov     rcx, r14
0x18002c218  call    ?getPointerToMember@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getPointerToMember(void)
0x18002c21d  jmp     loc_18002C3BC
0x18002c222  mov     rcx, r14
0x18002c225  call    ?getUnionObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getUnionObject(void)
0x18002c22a  jmp     loc_18002C3BC
0x18002c22f  cmp     edi, 50h ; 'P'
0x18002c232  jg      loc_18002C38B
0x18002c238  jz      loc_18002C369
0x18002c23e  mov     ecx, edi
0x18002c240  sub     ecx, 47h ; 'G'
0x18002c243  jz      short loc_18002C29E
0x18002c245  sub     ecx, 1
0x18002c248  jz      short loc_18002C29E
0x18002c24a  sub     ecx, 1
0x18002c24d  jz      short loc_18002C29E
0x18002c24f  sub     ecx, 1
0x18002c252  jz      short loc_18002C29E
0x18002c254  sub     ecx, 3
0x18002c257  jz      short loc_18002C278
0x18002c259  cmp     ecx, 1
0x18002c25c  jnz     loc_18002C3AB
0x18002c262  lea     rax, aNullptr; "nullptr"
0x18002c269  mov     dword ptr [rbp+57h+String+8], 7
0x18002c270  mov     rdx, r14
0x18002c273  jmp     loc_18002C153
0x18002c278  lea     rdx, [rbp+57h+var_78]
0x18002c27c  mov     rcx, r14
0x18002c27f  call    ?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateTypeArgument(void)
0x18002c284  cmp     [rbp+57h+var_68], 1
0x18002c288  jg      loc_18002C3AB
0x18002c28e  mov     rdx, rsi
0x18002c291  mov     rcx, r14
0x18002c294  call    ?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateNonTypeArgument(void)
0x18002c299  jmp     loc_18002C3BC
0x18002c29e  mov     r8b, 7Bh ; '{'; char
0x18002c2a1  lea     rcx, [rbp+57h+var_B0]; this
0x18002c2a5  mov     rdx, r14; struct UnDecorator *
0x18002c2a8  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x18002c2ad  mov     ecx, edi
0x18002c2af  sub     ecx, 48h ; 'H'
0x18002c2b2  jz      short loc_18002C2BE
0x18002c2b4  sub     ecx, 1
0x18002c2b7  jz      short loc_18002C2BE
0x18002c2b9  cmp     ecx, 1
0x18002c2bc  jnz     short loc_18002C2E1
0x18002c2be  lea     rdx, [rbp+57h+var_90]
0x18002c2c2  mov     rcx, r14
0x18002c2c5  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002c2ca  mov     rdx, rax
0x18002c2cd  lea     rcx, [rbp+57h+var_B0]
0x18002c2d1  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c2d6  mov     dl, 2Ch ; ','
0x18002c2d8  lea     rcx, [rbp+57h+var_B0]
0x18002c2dc  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002c2e1  sub     edi, 46h ; 'F'
0x18002c2e4  jz      short loc_18002C31D
0x18002c2e6  sub     edi, 1
0x18002c2e9  jz      short loc_18002C2FA
0x18002c2eb  sub     edi, 1
0x18002c2ee  jz      short loc_18002C340
0x18002c2f0  sub     edi, 1
0x18002c2f3  jz      short loc_18002C31D
0x18002c2f5  cmp     edi, 1
0x18002c2f8  jnz     short loc_18002C358
0x18002c2fa  lea     rdx, [rbp+57h+var_90]
0x18002c2fe  mov     rcx, r14
0x18002c301  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c306  mov     rdx, rax
0x18002c309  lea     rcx, [rbp+57h+var_B0]
0x18002c30d  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c312  mov     dl, 2Ch ; ','
0x18002c314  lea     rcx, [rbp+57h+var_B0]
0x18002c318  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002c31d  lea     rdx, [rbp+57h+var_90]
0x18002c321  mov     rcx, r14
0x18002c324  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c329  mov     rdx, rax
0x18002c32c  lea     rcx, [rbp+57h+var_B0]
0x18002c330  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c335  mov     dl, 2Ch ; ','
0x18002c337  lea     rcx, [rbp+57h+var_B0]
0x18002c33b  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002c340  lea     rdx, [rbp+57h+var_90]
0x18002c344  mov     rcx, r14
0x18002c347  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c34c  mov     rdx, rax
0x18002c34f  lea     rcx, [rbp+57h+var_B0]
0x18002c353  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002c358  mov     r8b, 7Dh ; '}'
0x18002c35b  lea     rcx, [rbp+57h+var_B0]
0x18002c35f  mov     rdx, rsi
0x18002c362  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002c367  jmp     short loc_18002C3BC
0x18002c369  xor     r8d, r8d
0x18002c36c  lea     rdx, [rbp+57h+var_90]
0x18002c370  mov     rcx, r14
0x18002c373  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x18002c378  lea     rax, aLambda; "lambda"
0x18002c37f  mov     dword ptr [rbp+57h+String+8], 6
0x18002c386  jmp     loc_18002C270
0x18002c38b  mov     ecx, edi
0x18002c38d  sub     ecx, 51h ; 'Q'
0x18002c390  jz      short loc_18002C3AB
0x18002c392  sub     ecx, 1
0x18002c395  jz      short loc_18002C3F7
0x18002c397  sub     ecx, 1
0x18002c39a  jz      short loc_18002C3E3
0x18002c39c  sub     ecx, 1
0x18002c39f  jz      short loc_18002C3F7
0x18002c3a1  sub     ecx, 1
0x18002c3a4  jz      short loc_18002C3F7
0x18002c3a6  cmp     ecx, 1
0x18002c3a9  jz      short loc_18002C3F7
0x18002c3ab  mov     r8d, 2
0x18002c3b1  mov     rdx, r14
0x18002c3b4  mov     rcx, rsi
0x18002c3b7  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002c3bc  mov     rax, rsi
0x18002c3bf  mov     rcx, [rbp+57h+var_20]
0x18002c3c3  xor     rcx, rsp; StackCookie
0x18002c3c6  call    __security_check_cookie
0x18002c3cb  lea     r11, [rsp+0D0h+var_10]
0x18002c3d3  mov     rbx, [r11+30h]
0x18002c3d7  mov     rsi, [r11+38h]
0x18002c3db  mov     rsp, r11
0x18002c3de  pop     r14
0x18002c3e0  pop     rdi
0x18002c3e1  pop     rbp
0x18002c3e2  retn
0x18002c3e3  mov     [rdx+8], r14
0x18002c3e7  mov     qword ptr [rdx], 0
0x18002c3ee  mov     dword ptr [rdx+10h], 0
0x18002c3f5  jmp     short loc_18002C3BC
0x18002c3f7  lea     rdx, [rbp+57h+var_60]
0x18002c3fb  mov     rcx, r14
0x18002c3fe  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c403  mov     rcx, [rbp+57h+var_60]
0x18002c407  xorps   xmm0, xmm0
0x18002c40a  movups  xmmword ptr [rbp+57h+String], xmm0
0x18002c40e  test    rcx, rcx
0x18002c411  jz      short loc_18002C42B
0x18002c413  mov     rax, [rcx]
0x18002c416  lea     r8, [rbp+57h+String+0Fh]
0x18002c41a  lea     rdx, [rbp+57h+String]
0x18002c41e  mov     rax, [rax+18h]
0x18002c422  call    cs:__guard_dispatch_icall_fptr
0x18002c428  mov     byte ptr [rax], 0
0x18002c42b  lea     rcx, [rbp+57h+String]; String
0x18002c42f  call    atol
0x18002c434  test    dword ptr [r14+110h], 4000h
0x18002c43f  mov     ebx, eax
0x18002c441  jz      short loc_18002C478
0x18002c443  mov     rax, [r14+118h]
0x18002c44a  test    rax, rax
0x18002c44d  jz      short loc_18002C478
0x18002c44f  mov     ecx, ebx
0x18002c451  and     ecx, 0FFFh
0x18002c457  call    cs:__guard_dispatch_icall_fptr
0x18002c45d  test    rax, rax
0x18002c460  jz      short loc_18002C478
0x18002c462  xor     r9d, r9d
0x18002c465  mov     r8, rax
0x18002c468  mov     rdx, r14
0x18002c46b  mov     rcx, rsi
0x18002c46e  call    ??$?0$0A@@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$0A@@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<0>)
0x18002c473  jmp     loc_18002C3BC
0x18002c478  and     ebx, 0FFFh
0x18002c47e  lea     r8, aD; "%d"
0x18002c485  mov     r9d, ebx
0x18002c488  lea     rcx, [rbp+57h+String]; Buffer
0x18002c48c  mov     edx, 10h; BufferCount
0x18002c491  call    sprintf_s
0x18002c496  xor     r9d, r9d
0x18002c499  lea     r8, [rbp+57h+String]
0x18002c49d  mov     rdx, r14
0x18002c4a0  lea     rcx, [rbp+57h+var_78]
0x18002c4a4  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x18002c4a9  sub     edi, 52h ; 'R'
0x18002c4ac  jz      short loc_18002C519
0x18002c4ae  sub     edi, 2
0x18002c4b1  jz      short loc_18002C519
0x18002c4b3  sub     edi, 1
0x18002c4b6  jz      short loc_18002C509
0x18002c4b8  cmp     edi, 1
0x18002c4bb  jnz     loc_18002C3AB
0x18002c4c1  lea     rax, aGenericMethodP; "`generic-method-parameter-"
0x18002c4c8  mov     dword ptr [rbp+57h+var_B0+8], 1Ah
0x18002c4cf  mov     rdx, [rbp+57h+var_70]; struct UnDecorator *
0x18002c4d3  lea     r8, [rbp+57h+var_B0]; struct StringLiteral *
0x18002c4d7  mov     qword ptr [rbp+57h+var_B0], rax
0x18002c4db  lea     rcx, [rbp+57h+var_48]; this
0x18002c4df  movaps  xmm0, [rbp+57h+var_B0]
0x18002c4e3  movdqa  [rbp+57h+var_B0], xmm0
0x18002c4e8  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002c4ed  lea     r8, [rbp+57h+var_78]
  ... truncated ...
```
