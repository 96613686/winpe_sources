# UnDecorator::getTemplateNonTypeArgument(void)

- ea: `0x18002c7dc`
- end: `0x18002cc82`
- name: `?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `1190`
- prototype: ``
- caller_count: `8`
- callee_count: `26`
- tags: ``

## callers

- `0x180026ac0`
- `0x180026e78`
- `0x180026f28`
- `0x180029e64`
- `0x18002c25c`
- `0x18002c7dc`
- `0x18002d380`
- `0x18002d528`

## callees

- `0x180002810`
- `0x180020bb0`
- `0x1800243c8`
- `0x180024480`
- `0x180024bd4`
- `0x180024c10`
- `0x180024cc4`
- `0x180025270`
- `0x1800252a4`
- `0x1800253d0`
- `0x180025488`
- `0x180026ac0`
- `0x180026e78`
- `0x1800289c4`
- `0x180028d00`
- `0x180029624`
- `0x180029e64`
- `0x18002ac40`
- `0x18002bd0c`
- `0x18002c164`
- `0x18002c7dc`
- `0x18002cc84`
- `0x18002d380`
- `0x18002d528`
- `0x18002e2cc`
- `0x1800603f0`

## string_xrefs

- `0x18002cc79`: ``template-type-parameter-`

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
0x18002c7dc  mov     [rsp-8+arg_10], rbx
0x18002c7e1  mov     [rsp-8+arg_18], rsi
0x18002c7e6  push    rbp
0x18002c7e7  push    rdi
0x18002c7e8  push    r14
0x18002c7ea  lea     rbp, [rsp-47h]
0x18002c7ef  sub     rsp, 0C0h
0x18002c7f6  mov     rax, cs:__security_cookie
0x18002c7fd  xor     rax, rsp
0x18002c800  mov     [rbp+57h+var_20], rax
0x18002c804  mov     r14, rcx
0x18002c807  mov     rsi, rdx
0x18002c80a  mov     rcx, [rcx+100h]
0x18002c811  movsx   eax, byte ptr [rcx]
0x18002c814  test    al, al
0x18002c816  jz      short loc_18002C822
0x18002c818  inc     rcx
0x18002c81b  mov     [r14+100h], rcx
0x18002c822  mov     edi, eax
0x18002c824  cmp     eax, 46h ; 'F'
0x18002c827  jg      loc_18002C98F
0x18002c82d  jz      loc_18002C9FE
0x18002c833  cmp     eax, 36h ; '6'
0x18002c836  jg      loc_18002C924
0x18002c83c  jz      loc_18002C917
0x18002c842  test    al, al
0x18002c844  jz      loc_18002C90C
0x18002c84a  sub     edi, 30h ; '0'
0x18002c84d  jz      loc_18002C8FF
0x18002c853  sub     edi, 1
0x18002c856  jz      short loc_18002C892
0x18002c858  sub     edi, 1
0x18002c85b  jz      short loc_18002C885
0x18002c85d  sub     edi, 2
0x18002c860  jz      short loc_18002C878
0x18002c862  cmp     edi, 1
0x18002c865  jnz     loc_18002CB0B
0x18002c86b  mov     rcx, r14
0x18002c86e  call    ?getAddressOf@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getAddressOf(void)
0x18002c873  jmp     loc_18002CB1C
0x18002c878  mov     rcx, r14
0x18002c87b  call    ?getStringObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getStringObject(void)
0x18002c880  jmp     loc_18002CB1C
0x18002c885  mov     rcx, r14
0x18002c888  call    ?getValueObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getValueObject(void)
0x18002c88d  jmp     loc_18002CB1C
0x18002c892  cmp     byte ptr [rcx], 40h ; '@'
0x18002c895  mov     rdx, r14; struct UnDecorator *
0x18002c898  jnz     short loc_18002C8D1
0x18002c89a  lea     rax, [rcx+1]
0x18002c89e  mov     dword ptr [rbp+57h+String+8], 4
0x18002c8a5  mov     [r14+100h], rax
0x18002c8ac  lea     rax, aNull; "NULL"
0x18002c8b3  mov     qword ptr [rbp+57h+String], rax
0x18002c8b7  lea     r8, [rbp+57h+var_B0]; struct StringLiteral *
0x18002c8bb  movaps  xmm0, xmmword ptr [rbp+57h+String]
0x18002c8bf  mov     rcx, rsi; this
0x18002c8c2  movdqa  [rbp+57h+var_B0], xmm0
0x18002c8c7  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002c8cc  jmp     loc_18002CB1C
0x18002c8d1  mov     r8b, 26h ; '&'; char
0x18002c8d4  lea     rcx, [rbp+57h+var_90]; this
0x18002c8d8  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x18002c8dd  lea     rdx, [rbp+57h+var_60]
0x18002c8e1  mov     rcx, r14
0x18002c8e4  mov     rbx, rax
0x18002c8e7  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002c8ec  mov     r8, rax
0x18002c8ef  mov     rdx, rsi
0x18002c8f2  mov     rcx, rbx
0x18002c8f5  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002c8fa  jmp     loc_18002CB1C
0x18002c8ff  mov     rcx, r14
0x18002c902  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002c907  jmp     loc_18002CB1C
0x18002c90c  mov     r8d, 1
0x18002c912  jmp     loc_18002CB11
0x18002c917  mov     rcx, r14
0x18002c91a  call    ?getMemberAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getMemberAccess(void)
0x18002c91f  jmp     loc_18002CB1C
0x18002c924  mov     ecx, edi
0x18002c926  sub     ecx, 37h ; '7'
0x18002c929  jz      short loc_18002C982
0x18002c92b  sub     ecx, 1
0x18002c92e  jz      short loc_18002C975
0x18002c930  sub     ecx, 9
0x18002c933  jz      short loc_18002C962
0x18002c935  sub     ecx, 1
0x18002c938  jz      short loc_18002C962
0x18002c93a  sub     ecx, 1
0x18002c93d  jz      short loc_18002C955
0x18002c93f  cmp     ecx, 2
0x18002c942  jnz     loc_18002CB0B
0x18002c948  mov     rcx, r14
0x18002c94b  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002c950  jmp     loc_18002CB1C
0x18002c955  mov     rcx, r14
0x18002c958  call    ?getArrayAccess@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getArrayAccess(void)
0x18002c95d  jmp     loc_18002CB1C
0x18002c962  lfence
0x18002c965  mov     r8d, edi
0x18002c968  mov     rcx, r14
0x18002c96b  call    ?getFloatingPoint@UnDecorator@@AEAA?AVDName@@H@Z; UnDecorator::getFloatingPoint(int)
0x18002c970  jmp     loc_18002CB1C
0x18002c975  mov     rcx, r14
0x18002c978  call    ?getPointerToMember@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getPointerToMember(void)
0x18002c97d  jmp     loc_18002CB1C
0x18002c982  mov     rcx, r14
0x18002c985  call    ?getUnionObject@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getUnionObject(void)
0x18002c98a  jmp     loc_18002CB1C
0x18002c98f  cmp     edi, 50h ; 'P'
0x18002c992  jg      loc_18002CAEB
0x18002c998  jz      loc_18002CAC9
0x18002c99e  mov     ecx, edi
0x18002c9a0  sub     ecx, 47h ; 'G'
0x18002c9a3  jz      short loc_18002C9FE
0x18002c9a5  sub     ecx, 1
0x18002c9a8  jz      short loc_18002C9FE
0x18002c9aa  sub     ecx, 1
0x18002c9ad  jz      short loc_18002C9FE
0x18002c9af  sub     ecx, 1
0x18002c9b2  jz      short loc_18002C9FE
0x18002c9b4  sub     ecx, 3
0x18002c9b7  jz      short loc_18002C9D8
0x18002c9b9  cmp     ecx, 1
0x18002c9bc  jnz     loc_18002CB0B
0x18002c9c2  lea     rax, aNullptr; "nullptr"
0x18002c9c9  mov     dword ptr [rbp+57h+String+8], 7
0x18002c9d0  mov     rdx, r14
0x18002c9d3  jmp     loc_18002C8B3
0x18002c9d8  lea     rdx, [rbp+57h+var_78]
0x18002c9dc  mov     rcx, r14
0x18002c9df  call    ?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateTypeArgument(void)
0x18002c9e4  cmp     [rbp+57h+var_68], 1
0x18002c9e8  jg      loc_18002CB0B
0x18002c9ee  mov     rdx, rsi
0x18002c9f1  mov     rcx, r14
0x18002c9f4  call    ?getTemplateNonTypeArgument@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getTemplateNonTypeArgument(void)
0x18002c9f9  jmp     loc_18002CB1C
0x18002c9fe  mov     r8b, 7Bh ; '{'; char
0x18002ca01  lea     rcx, [rbp+57h+var_B0]; this
0x18002ca05  mov     rdx, r14; struct UnDecorator *
0x18002ca08  call    ??0DName@@QEAA@PEAVUnDecorator@@D@Z; DName::DName(UnDecorator *,char)
0x18002ca0d  mov     ecx, edi
0x18002ca0f  sub     ecx, 48h ; 'H'
0x18002ca12  jz      short loc_18002CA1E
0x18002ca14  sub     ecx, 1
0x18002ca17  jz      short loc_18002CA1E
0x18002ca19  cmp     ecx, 1
0x18002ca1c  jnz     short loc_18002CA41
0x18002ca1e  lea     rdx, [rbp+57h+var_90]
0x18002ca22  mov     rcx, r14
0x18002ca25  call    ?getDecoratedName@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getDecoratedName(void)
0x18002ca2a  mov     rdx, rax
0x18002ca2d  lea     rcx, [rbp+57h+var_B0]
0x18002ca31  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002ca36  mov     dl, 2Ch ; ','
0x18002ca38  lea     rcx, [rbp+57h+var_B0]
0x18002ca3c  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002ca41  sub     edi, 46h ; 'F'
0x18002ca44  jz      short loc_18002CA7D
0x18002ca46  sub     edi, 1
0x18002ca49  jz      short loc_18002CA5A
0x18002ca4b  sub     edi, 1
0x18002ca4e  jz      short loc_18002CAA0
0x18002ca50  sub     edi, 1
0x18002ca53  jz      short loc_18002CA7D
0x18002ca55  cmp     edi, 1
0x18002ca58  jnz     short loc_18002CAB8
0x18002ca5a  lea     rdx, [rbp+57h+var_90]
0x18002ca5e  mov     rcx, r14
0x18002ca61  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002ca66  mov     rdx, rax
0x18002ca69  lea     rcx, [rbp+57h+var_B0]
0x18002ca6d  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002ca72  mov     dl, 2Ch ; ','
0x18002ca74  lea     rcx, [rbp+57h+var_B0]
0x18002ca78  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002ca7d  lea     rdx, [rbp+57h+var_90]
0x18002ca81  mov     rcx, r14
0x18002ca84  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002ca89  mov     rdx, rax
0x18002ca8c  lea     rcx, [rbp+57h+var_B0]
0x18002ca90  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002ca95  mov     dl, 2Ch ; ','
0x18002ca97  lea     rcx, [rbp+57h+var_B0]
0x18002ca9b  call    ??YDName@@QEAAAEAV0@D@Z; DName::operator+=(char)
0x18002caa0  lea     rdx, [rbp+57h+var_90]
0x18002caa4  mov     rcx, r14
0x18002caa7  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002caac  mov     rdx, rax
0x18002caaf  lea     rcx, [rbp+57h+var_B0]
0x18002cab3  call    ??YDName@@QEAAAEAV0@AEBV0@@Z; DName::operator+=(DName const &)
0x18002cab8  mov     r8b, 7Dh ; '}'
0x18002cabb  lea     rcx, [rbp+57h+var_B0]
0x18002cabf  mov     rdx, rsi
0x18002cac2  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002cac7  jmp     short loc_18002CB1C
0x18002cac9  xor     r8d, r8d
0x18002cacc  lea     rdx, [rbp+57h+var_90]
0x18002cad0  mov     rcx, r14
0x18002cad3  call    ?getDimension@UnDecorator@@AEAA?AVDName@@_N@Z; UnDecorator::getDimension(bool)
0x18002cad8  lea     rax, aLambda; "lambda"
0x18002cadf  mov     dword ptr [rbp+57h+String+8], 6
0x18002cae6  jmp     loc_18002C9D0
0x18002caeb  mov     ecx, edi
0x18002caed  sub     ecx, 51h ; 'Q'
0x18002caf0  jz      short loc_18002CB0B
0x18002caf2  sub     ecx, 1
0x18002caf5  jz      short loc_18002CB57
0x18002caf7  sub     ecx, 1
0x18002cafa  jz      short loc_18002CB43
0x18002cafc  sub     ecx, 1
0x18002caff  jz      short loc_18002CB57
0x18002cb01  sub     ecx, 1
0x18002cb04  jz      short loc_18002CB57
0x18002cb06  cmp     ecx, 1
0x18002cb09  jz      short loc_18002CB57
0x18002cb0b  mov     r8d, 2
0x18002cb11  mov     rdx, r14
0x18002cb14  mov     rcx, rsi
0x18002cb17  call    ??0DName@@QEAA@PEAVUnDecorator@@W4DNameStatus@@@Z; DName::DName(UnDecorator *,DNameStatus)
0x18002cb1c  mov     rax, rsi
0x18002cb1f  mov     rcx, [rbp+57h+var_20]
0x18002cb23  xor     rcx, rsp; StackCookie
0x18002cb26  call    __security_check_cookie
0x18002cb2b  lea     r11, [rsp+0D0h+var_10]
0x18002cb33  mov     rbx, [r11+30h]
0x18002cb37  mov     rsi, [r11+38h]
0x18002cb3b  mov     rsp, r11
0x18002cb3e  pop     r14
0x18002cb40  pop     rdi
0x18002cb41  pop     rbp
0x18002cb42  retn
0x18002cb43  mov     [rdx+8], r14
0x18002cb47  mov     qword ptr [rdx], 0
0x18002cb4e  mov     dword ptr [rdx+10h], 0
0x18002cb55  jmp     short loc_18002CB1C
0x18002cb57  lea     rdx, [rbp+57h+var_60]
0x18002cb5b  mov     rcx, r14
0x18002cb5e  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002cb63  mov     rcx, [rbp+57h+var_60]
0x18002cb67  xorps   xmm0, xmm0
0x18002cb6a  movups  xmmword ptr [rbp+57h+String], xmm0
0x18002cb6e  test    rcx, rcx
0x18002cb71  jz      short loc_18002CB8B
0x18002cb73  mov     rax, [rcx]
0x18002cb76  lea     r8, [rbp+57h+String+0Fh]
0x18002cb7a  lea     rdx, [rbp+57h+String]
0x18002cb7e  mov     rax, [rax+18h]
0x18002cb82  call    cs:__guard_dispatch_icall_fptr
0x18002cb88  mov     byte ptr [rax], 0
0x18002cb8b  lea     rcx, [rbp+57h+String]; String
0x18002cb8f  call    atol
0x18002cb94  test    dword ptr [r14+110h], 4000h
0x18002cb9f  mov     ebx, eax
0x18002cba1  jz      short loc_18002CBD8
0x18002cba3  mov     rax, [r14+118h]
0x18002cbaa  test    rax, rax
0x18002cbad  jz      short loc_18002CBD8
0x18002cbaf  mov     ecx, ebx
0x18002cbb1  and     ecx, 0FFFh
0x18002cbb7  call    cs:__guard_dispatch_icall_fptr
0x18002cbbd  test    rax, rax
0x18002cbc0  jz      short loc_18002CBD8
0x18002cbc2  xor     r9d, r9d
0x18002cbc5  mov     r8, rax
0x18002cbc8  mov     rdx, r14
0x18002cbcb  mov     rcx, rsi
0x18002cbce  call    ??$?0$0A@@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$0A@@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<0>)
0x18002cbd3  jmp     loc_18002CB1C
0x18002cbd8  and     ebx, 0FFFh
0x18002cbde  lea     r8, aD; "%d"
0x18002cbe5  mov     r9d, ebx
0x18002cbe8  lea     rcx, [rbp+57h+String]; Buffer
0x18002cbec  mov     edx, 10h; BufferCount
0x18002cbf1  call    sprintf_s
0x18002cbf6  xor     r9d, r9d
0x18002cbf9  lea     r8, [rbp+57h+String]
0x18002cbfd  mov     rdx, r14
0x18002cc00  lea     rcx, [rbp+57h+var_78]
0x18002cc04  call    ??$?0$01@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$01@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<2>)
0x18002cc09  sub     edi, 52h ; 'R'
0x18002cc0c  jz      short loc_18002CC79
0x18002cc0e  sub     edi, 2
0x18002cc11  jz      short loc_18002CC79
0x18002cc13  sub     edi, 1
0x18002cc16  jz      short loc_18002CC69
0x18002cc18  cmp     edi, 1
0x18002cc1b  jnz     loc_18002CB0B
0x18002cc21  lea     rax, aGenericMethodP; "`generic-method-parameter-"
0x18002cc28  mov     dword ptr [rbp+57h+var_B0+8], 1Ah
0x18002cc2f  mov     rdx, [rbp+57h+var_70]; struct UnDecorator *
0x18002cc33  lea     r8, [rbp+57h+var_B0]; struct StringLiteral *
0x18002cc37  mov     qword ptr [rbp+57h+var_B0], rax
0x18002cc3b  lea     rcx, [rbp+57h+var_48]; this
0x18002cc3f  movaps  xmm0, [rbp+57h+var_B0]
0x18002cc43  movdqa  [rbp+57h+var_B0], xmm0
0x18002cc48  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002cc4d  lea     r8, [rbp+57h+var_78]
  ... truncated ...
```
