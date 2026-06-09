# UnDecorator::getTemplateConstant(void)

- ea: `0x180332c40`
- end: `0x180332fe0`
- name: `?getTemplateConstant@UnDecorator@@CA?AVDName@@XZ`
- size: `928`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: ``

## callers

- `0x180332924`

## callees

- `0x180026660`
- `0x18030c3f0`
- `0x18032d94c`
- `0x18032dbc4`
- `0x18032dbf0`
- `0x18032dc1c`
- `0x18032dc74`
- `0x18032dcb8`
- `0x18032ecb0`
- `0x1803300dc`
- `0x1803325ac`
- `0x180332640`
- `0x180332c40`
- `0x18033a83c`
- `0x180358070`

## string_xrefs

- `0x180332fd7`: ``template-type-parameter-`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateConstant(DName *a1, __int64 a2, __int64 a3)
{
  int v4; // ebx
  char *v5; // rcx
  int v6; // edi
  __int64 v7; // rdx
  __int64 v8; // r8
  DName *v9; // rax
  __int64 v10; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  char *v13; // r8
  __int64 v14; // rcx
  const char *v15; // rdx
  DName *v16; // rbx
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 DecoratedName; // rax
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 SignedDimension; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  __int16 v26; // bx
  char *Parameter; // rax
  int v28; // edi
  int v29; // edi
  int v30; // edi
  const char *v31; // rdx
  DName *v32; // rax
  char v33[8]; // [rsp+28h] [rbp-79h] BYREF
  _BYTE v34[16]; // [rsp+30h] [rbp-71h] BYREF
  __int64 v35; // [rsp+40h] [rbp-61h] BYREF
  char v36; // [rsp+48h] [rbp-59h]
  char v37[16]; // [rsp+50h] [rbp-51h] BYREF
  char String[8]; // [rsp+60h] [rbp-41h] BYREF
  int v39; // [rsp+68h] [rbp-39h]
  char v40[9]; // [rsp+6Fh] [rbp-32h] BYREF
  char v41; // [rsp+78h] [rbp-29h] BYREF
  char v42; // [rsp+79h] [rbp-28h] BYREF
  char v43; // [rsp+7Ah] [rbp-27h]

  v4 = *UnDecorator::gName;
  v5 = ++UnDecorator::gName;
  v6 = v4;
  if ( v4 > 74 )
  {
    if ( v4 == 81 )
      goto LABEL_37;
    if ( v4 != 82 )
    {
      if ( v4 == 83 )
      {
        *(_QWORD *)a1 = 0;
        *((_DWORD *)a1 + 2) = 0;
        return a1;
      }
      if ( (unsigned int)(v4 - 84) > 2 )
        goto LABEL_37;
    }
    UnDecorator::getSignedDimension(&v35, a2, a3);
    if ( v35 )
      *(_BYTE *)(*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v35 + 16LL))(v35, String, v40) = 0;
    else
      String[0] = 0;
    v26 = atol(String);
    if ( (UnDecorator::disableFlags & 0x4000) == 0
      || !UnDecorator::m_pGetParameter
      || (Parameter = UnDecorator::m_pGetParameter(v26 & 0xFFF)) == 0 )
    {
      sprintf_s(String, 0x10u, "%d", v26 & 0xFFF);
      DName::DName((DName *)&v35, String);
      v28 = v6 - 82;
      if ( v28 && (v29 = v28 - 2) != 0 )
      {
        v30 = v29 - 1;
        if ( v30 )
        {
          if ( v30 != 1 )
            goto LABEL_37;
          v31 = "`generic-method-parameter-";
        }
        else
        {
          v31 = "`generic-class-parameter-";
        }
      }
      else
      {
        v31 = "`template-type-parameter-";
      }
      v32 = DName::DName((DName *)v37, v31);
      DName::operator+(v32, v34, &v35);
      DName::operator+(v34, a1, "'");
      return a1;
    }
    v15 = Parameter;
    goto LABEL_19;
  }
  if ( v4 >= 70 )
  {
    *(_QWORD *)String = 0;
    v39 = 0;
    v33[0] = 123;
    DName::doPchar((DName *)String, v33, 1);
    if ( (unsigned __int8)(v4 - 72) <= 2u )
    {
      DecoratedName = UnDecorator::getDecoratedName(v34);
      DName::operator+=(String, DecoratedName);
      DName::operator+=((DName *)String);
    }
    if ( v4 != 70 )
    {
      if ( v4 == 71 )
        goto LABEL_30;
      if ( v4 == 72 )
      {
LABEL_32:
        SignedDimension = UnDecorator::getSignedDimension(v34, v17, v18);
        DName::operator+=(String, SignedDimension);
        LOBYTE(v23) = 125;
        DName::operator+(String, a1, v23, v24);
        return a1;
      }
      if ( v4 != 73 )
      {
LABEL_30:
        v20 = UnDecorator::getSignedDimension(v34, v17, v18);
        DName::operator+=(String, v20);
        DName::operator+=((DName *)String);
      }
    }
    v21 = UnDecorator::getSignedDimension(v34, v17, v18);
    DName::operator+=(String, v21);
    DName::operator+=((DName *)String);
    goto LABEL_32;
  }
  switch ( v4 )
  {
    case 0:
      UnDecorator::gName = v5 - 1;
      goto LABEL_23;
    case 48:
      UnDecorator::getSignedDimension(a1, a2, a3);
      return a1;
    case 49:
      if ( *v5 != 64 )
      {
        v16 = DName::DName((DName *)v34, "&");
        v13 = (char *)UnDecorator::getDecoratedName(&v35);
        v14 = (__int64)v16;
        goto LABEL_16;
      }
      UnDecorator::gName = v5 + 1;
      v15 = "NULL";
LABEL_19:
      DName::DName(a1, v15);
      return a1;
    case 50:
      UnDecorator::getSignedDimension(&v35, a2, a3);
      UnDecorator::getSignedDimension(String, v7, v8);
      if ( v36 <= 1 && (char)v39 <= 1 )
      {
        if ( !DName::getString((DName *)&v35, &v42, 99) )
          goto LABEL_37;
        v41 = v42;
        if ( v42 == 45 )
        {
          v42 = v43;
          v43 = 46;
        }
        else
        {
          v42 = 46;
        }
        v9 = DName::DName((DName *)v34, &v41);
        LOBYTE(v10) = 101;
        v12 = DName::operator+(v9, &v35, v10, v11);
        v13 = String;
        v14 = v12;
LABEL_16:
        DName::operator+(v14, a1, v13);
        return a1;
      }
LABEL_23:
      *((_DWORD *)a1 + 2) = 0;
      *(_QWORD *)a1 = &off_1803FB120;
      return a1;
  }
  if ( v4 != 69 )
  {
LABEL_37:
    *((_DWORD *)a1 + 2) = 0;
    *(_QWORD *)a1 = 0;
    *((_BYTE *)a1 + 8) = 2;
    return a1;
  }
  UnDecorator::getDecoratedName(a1);
  return a1;
}

```

## disassembly

```asm
0x180332c40  mov     rax, rsp
0x180332c43  mov     [rax+10h], rbx
0x180332c47  mov     [rax+18h], rsi
0x180332c4b  mov     [rax+20h], rdi
0x180332c4f  push    rbp
0x180332c50  lea     rbp, [rax-5Fh]
0x180332c54  sub     rsp, 0F0h
0x180332c5b  mov     rax, cs:__security_cookie
0x180332c62  xor     rax, rsp
0x180332c65  mov     [rbp+57h+var_10], rax
0x180332c69  mov     rax, cs:?gName@UnDecorator@@0PEBDEB
0x180332c70  mov     rsi, rcx
0x180332c73  movsx   ebx, byte ptr [rax]
0x180332c76  lea     rcx, [rax+1]
0x180332c7a  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x180332c81  mov     edi, ebx
0x180332c83  cmp     ebx, 4Ah ; 'J'
0x180332c86  jg      loc_180332E90
0x180332c8c  cmp     ebx, 46h ; 'F'
0x180332c8f  jge     loc_180332DC9
0x180332c95  test    ebx, ebx
0x180332c97  jz      loc_180332DAB
0x180332c9d  sub     edi, 30h ; '0'
0x180332ca0  jz      loc_180332D9E
0x180332ca6  sub     edi, 1
0x180332ca9  jz      loc_180332D56
0x180332caf  sub     edi, 1
0x180332cb2  jz      short loc_180332CCA
0x180332cb4  cmp     edi, 13h
0x180332cb7  jnz     loc_180332EA7
0x180332cbd  mov     rcx, rsi
0x180332cc0  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ
0x180332cc5  jmp     loc_180332EB3
0x180332cca  lea     rcx, [rbp+57h+var_B8]
0x180332cce  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332cd3  lea     rcx, [rbp+57h+String]
0x180332cd7  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332cdc  cmp     [rbp+57h+var_B0], 1
0x180332ce0  jg      loc_180332DB6
0x180332ce6  cmp     byte ptr [rbp+57h+var_90], 1
0x180332cea  jg      loc_180332DB6
0x180332cf0  mov     r8d, 63h ; 'c'; int
0x180332cf6  lea     rdx, [rbp+57h+var_7F]; char *
0x180332cfa  lea     rcx, [rbp+57h+var_B8]; this
0x180332cfe  call    ?getString@DName@@QEBAPEADPEADH@Z
0x180332d03  test    rax, rax
0x180332d06  jz      loc_180332EA7
0x180332d0c  mov     al, [rbp+57h+var_7F]
0x180332d0f  mov     [rbp+57h+var_80], al
0x180332d12  cmp     al, 2Dh ; '-'
0x180332d14  jnz     short loc_180332D22
0x180332d16  mov     al, [rbp+57h+var_7E]
0x180332d19  mov     [rbp+57h+var_7F], al
0x180332d1c  mov     [rbp+57h+var_7E], 2Eh ; '.'
0x180332d20  jmp     short loc_180332D26
0x180332d22  mov     [rbp+57h+var_7F], 2Eh ; '.'
0x180332d26  lea     rdx, [rbp+57h+var_80]; char *
0x180332d2a  lea     rcx, [rbp+57h+var_C8]; this
0x180332d2e  call    ??0DName@@QEAA@PEBD@Z
0x180332d33  mov     r8b, 65h ; 'e'
0x180332d36  lea     rdx, [rbp+57h+var_B8]
0x180332d3a  mov     rcx, rax
0x180332d3d  call    ??HDName@@QEBA?AV0@D@Z
0x180332d42  lea     r8, [rbp+57h+String]
0x180332d46  mov     rcx, rax
0x180332d49  mov     rdx, rsi
0x180332d4c  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180332d51  jmp     loc_180332EB3
0x180332d56  cmp     byte ptr [rcx], 40h ; '@'
0x180332d59  jnz     short loc_180332D7A
0x180332d5b  lea     rax, [rcx+1]
0x180332d5f  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x180332d66  lea     rdx, aNull_1
0x180332d6d  mov     rcx, rsi; this
0x180332d70  call    ??0DName@@QEAA@PEBD@Z
0x180332d75  jmp     loc_180332EB3
0x180332d7a  lea     rdx, asc_1803FA6B0
0x180332d81  lea     rcx, [rbp+57h+var_C8]; this
0x180332d85  call    ??0DName@@QEAA@PEBD@Z
0x180332d8a  lea     rcx, [rbp+57h+var_B8]
0x180332d8e  mov     rbx, rax
0x180332d91  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ
0x180332d96  mov     r8, rax
0x180332d99  mov     rcx, rbx
0x180332d9c  jmp     short loc_180332D49
0x180332d9e  mov     rcx, rsi
0x180332da1  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332da6  jmp     loc_180332EB3
0x180332dab  lea     rax, [rcx-1]
0x180332daf  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x180332db6  and     dword ptr [rsi+8], 0
0x180332dba  lea     rax, off_1803FB120
0x180332dc1  mov     [rsi], rax
0x180332dc4  jmp     loc_180332EB3
0x180332dc9  and     qword ptr [rbp+57h+String], 0
0x180332dce  lea     rdx, [rbp+57h+var_D0]; char *
0x180332dd2  and     [rbp+57h+var_90], 0
0x180332dd6  lea     rcx, [rbp+57h+String]; this
0x180332dda  mov     r8d, 1; int
0x180332de0  mov     [rbp+57h+var_D0], 7Bh ; '{'
0x180332de4  call    ?doPchar@DName@@AEAAXPEBDH@Z
0x180332de9  sub     bl, 48h ; 'H'
0x180332dec  cmp     bl, 2
0x180332def  ja      short loc_180332E11
0x180332df1  lea     rcx, [rbp+57h+var_C8]
0x180332df5  call    ?getDecoratedName@UnDecorator@@CA?AVDName@@XZ
0x180332dfa  mov     rdx, rax
0x180332dfd  lea     rcx, [rbp+57h+String]
0x180332e01  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180332e06  mov     dl, 2Ch ; ','
0x180332e08  lea     rcx, [rbp+57h+String]; this
0x180332e0c  call    ??YDName@@QEAAAEAV0@D@Z
0x180332e11  sub     edi, 46h ; 'F'
0x180332e14  jz      short loc_180332E4A
0x180332e16  sub     edi, 1
0x180332e19  jz      short loc_180332E2A
0x180332e1b  sub     edi, 1
0x180332e1e  jz      short loc_180332E6A
0x180332e20  sub     edi, 1
0x180332e23  jz      short loc_180332E4A
0x180332e25  cmp     edi, 1
0x180332e28  jnz     short loc_180332E7F
0x180332e2a  lea     rcx, [rbp+57h+var_C8]
0x180332e2e  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332e33  mov     rdx, rax
0x180332e36  lea     rcx, [rbp+57h+String]
0x180332e3a  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180332e3f  mov     dl, 2Ch ; ','
0x180332e41  lea     rcx, [rbp+57h+String]; this
0x180332e45  call    ??YDName@@QEAAAEAV0@D@Z
0x180332e4a  lea     rcx, [rbp+57h+var_C8]
0x180332e4e  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332e53  mov     rdx, rax
0x180332e56  lea     rcx, [rbp+57h+String]
0x180332e5a  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180332e5f  mov     dl, 2Ch ; ','
0x180332e61  lea     rcx, [rbp+57h+String]; this
0x180332e65  call    ??YDName@@QEAAAEAV0@D@Z
0x180332e6a  lea     rcx, [rbp+57h+var_C8]
0x180332e6e  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332e73  mov     rdx, rax
0x180332e76  lea     rcx, [rbp+57h+String]
0x180332e7a  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180332e7f  mov     r8b, 7Dh ; '}'
0x180332e82  lea     rcx, [rbp+57h+String]
0x180332e86  mov     rdx, rsi
0x180332e89  call    ??HDName@@QEBA?AV0@D@Z
0x180332e8e  jmp     short loc_180332EB3
0x180332e90  cmp     edi, 51h ; 'Q'
0x180332e93  jz      short loc_180332EA7
0x180332e95  cmp     edi, 52h ; 'R'
0x180332e98  jz      short loc_180332EE5
0x180332e9a  cmp     edi, 53h ; 'S'
0x180332e9d  jz      short loc_180332EDB
0x180332e9f  lea     eax, [rdi-54h]
0x180332ea2  cmp     eax, 2
0x180332ea5  jbe     short loc_180332EE5
0x180332ea7  and     dword ptr [rsi+8], 0
0x180332eab  and     qword ptr [rsi], 0
0x180332eaf  mov     byte ptr [rsi+8], 2
0x180332eb3  mov     rax, rsi
0x180332eb6  mov     rcx, [rbp+57h+var_10]
0x180332eba  xor     rcx, rsp; StackCookie
0x180332ebd  call    __security_check_cookie
0x180332ec2  lea     r11, [rsp+0F0h+var_s0]
0x180332eca  mov     rbx, [r11+18h]
0x180332ece  mov     rsi, [r11+20h]
0x180332ed2  mov     rdi, [r11+28h]
0x180332ed6  mov     rsp, r11
0x180332ed9  pop     rbp
0x180332eda  retn
0x180332edb  and     qword ptr [rsi], 0
0x180332edf  and     dword ptr [rsi+8], 0
0x180332ee3  jmp     short loc_180332EB3
0x180332ee5  lea     rcx, [rbp+57h+var_B8]
0x180332ee9  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332eee  mov     rcx, [rbp+57h+var_B8]
0x180332ef2  test    rcx, rcx
0x180332ef5  jz      short loc_180332F11
0x180332ef7  mov     rax, [rcx]
0x180332efa  lea     r8, [rbp+57h+var_89]
0x180332efe  lea     rdx, [rbp+57h+String]
0x180332f02  mov     rax, [rax+10h]
0x180332f06  call    cs:__guard_dispatch_icall_fptr
0x180332f0c  mov     byte ptr [rax], 0
0x180332f0f  jmp     short loc_180332F15
0x180332f11  mov     [rbp+57h+String], 0
0x180332f15  lea     rcx, [rbp+57h+String]; String
0x180332f19  call    atol
0x180332f1e  test    cs:?disableFlags@UnDecorator@@0KA, 4000h
0x180332f28  mov     ebx, eax
0x180332f2a  jz      short loc_180332F53
0x180332f2c  mov     rax, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA
0x180332f33  test    rax, rax
0x180332f36  jz      short loc_180332F53
0x180332f38  mov     ecx, ebx
0x180332f3a  and     ecx, 0FFFh
0x180332f40  call    cs:__guard_dispatch_icall_fptr
0x180332f46  test    rax, rax
0x180332f49  jz      short loc_180332F53
0x180332f4b  mov     rdx, rax
0x180332f4e  jmp     loc_180332D6D
0x180332f53  and     ebx, 0FFFh
0x180332f59  lea     r8, aD_0
0x180332f60  mov     r9d, ebx
0x180332f63  lea     rcx, [rbp+57h+String]; Buffer
0x180332f67  mov     edx, 10h; BufferCount
0x180332f6c  call    sprintf_s
0x180332f71  lea     rdx, [rbp+57h+String]; char *
0x180332f75  lea     rcx, [rbp+57h+var_B8]; this
0x180332f79  call    ??0DName@@QEAA@PEBD@Z
0x180332f7e  sub     edi, 52h ; 'R'
0x180332f81  jz      short loc_180332FD7
0x180332f83  sub     edi, 2
0x180332f86  jz      short loc_180332FD7
0x180332f88  sub     edi, 1
0x180332f8b  jz      short loc_180332FCE
0x180332f8d  cmp     edi, 1
0x180332f90  jnz     loc_180332EA7
0x180332f96  lea     rdx, aGenericMethodP
0x180332f9d  lea     rcx, [rbp+57h+var_A8]; this
0x180332fa1  call    ??0DName@@QEAA@PEBD@Z
0x180332fa6  lea     r8, [rbp+57h+var_B8]
0x180332faa  mov     rcx, rax
0x180332fad  lea     rdx, [rbp+57h+var_C8]
0x180332fb1  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180332fb6  lea     r8, asc_1803822B8
0x180332fbd  mov     rdx, rsi
0x180332fc0  lea     rcx, [rbp+57h+var_C8]
0x180332fc4  call    ??HDName@@QEBA?AV0@PEBD@Z
0x180332fc9  jmp     loc_180332EB3
0x180332fce  lea     rdx, aGenericClassPa
0x180332fd5  jmp     short loc_180332F9D
0x180332fd7  lea     rdx, aTemplateTypePa
0x180332fde  jmp     short loc_180332F9D
```
