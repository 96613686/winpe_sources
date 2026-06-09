# UnDecorator::getTemplateArgumentList(void)

- ea: `0x180332924`
- end: `0x180332c3e`
- name: `?getTemplateArgumentList@UnDecorator@@CA?AVDName@@XZ`
- size: `794`
- prototype: ``
- caller_count: `2`
- callee_count: `16`
- tags: ``

## callers

- `0x180331260`
- `0x180332fe0`

## callees

- `0x18030c3f0`
- `0x18032d94c`
- `0x18032db4c`
- `0x18032db84`
- `0x18032dbc4`
- `0x18032dc1c`
- `0x18032dc74`
- `0x18032dcb8`
- `0x18032dd38`
- `0x18032de30`
- `0x1803319d0`
- `0x1803325ac`
- `0x180332924`
- `0x180332c40`
- `0x18033a83c`
- `0x180358070`

## string_xrefs

- `0x180332b04`: ``template-parameter`
- `0x180332b3b`: ``template-parameter`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateArgumentList(DName *a1, __int64 a2)
{
  char v2; // si
  char *v4; // rcx
  int v5; // eax
  char v6; // r14
  __int64 v7; // rax
  char *v8; // rdi
  char *v9; // r8
  char v10; // r9
  char v11; // al
  char *v12; // rcx
  __int64 TemplateConstant; // rax
  unsigned int v14; // eax
  DName *v15; // rax
  char *v16; // rdx
  _BYTE *v17; // rcx
  DName *v18; // rax
  __int64 v20; // [rsp+28h] [rbp-99h] BYREF
  __int64 v21; // [rsp+30h] [rbp-91h]
  _QWORD v22[2]; // [rsp+38h] [rbp-89h] BYREF
  __int64 v23; // [rsp+48h] [rbp-79h] BYREF
  int v24; // [rsp+50h] [rbp-71h]
  _BYTE v25[16]; // [rsp+58h] [rbp-69h] BYREF
  _BYTE v26[16]; // [rsp+68h] [rbp-59h] BYREF
  _BYTE v27[16]; // [rsp+78h] [rbp-49h] BYREF
  _BYTE v28[16]; // [rsp+88h] [rbp-39h] BYREF
  _BYTE v29[16]; // [rsp+98h] [rbp-29h] BYREF
  char v30; // [rsp+A8h] [rbp-19h] BYREF
  _BYTE v31[16]; // [rsp+B8h] [rbp-9h] BYREF
  char v32; // [rsp+C8h] [rbp+7h] BYREF
  _BYTE v33[16]; // [rsp+D8h] [rbp+17h] BYREF
  char String[15]; // [rsp+E8h] [rbp+27h] BYREF
  char v35; // [rsp+F7h] [rbp+36h] BYREF

  v2 = 1;
  *((_DWORD *)a1 + 2) = 0;
  *(_QWORD *)a1 = 0;
  UnDecorator::fGetTemplateArgumentList = 1;
  if ( !*((_BYTE *)a1 + 8) )
  {
    v4 = UnDecorator::gName;
    do
    {
      if ( (*v4 & 0xBF) == 0 )
        break;
      v5 = *v4;
      v6 = 0;
      v20 = 0;
      LODWORD(v21) = 0;
      if ( (unsigned int)(v5 - 48) <= 9 )
      {
        UnDecorator::gName = v4 + 1;
        v7 = Replicator::operator[](UnDecorator::pTemplateArgList, v27);
        v20 = *(_QWORD *)v7;
        LODWORD(v21) = *(_DWORD *)(v7 + 8);
        goto LABEL_40;
      }
      v8 = v4;
      v9 = v4;
      if ( *v4 != 36 || v4[1] != 36 )
        goto LABEL_19;
      v10 = 0;
      a2 = (unsigned int)(v4[2] - 36);
      if ( v4[2] == 36 )
      {
        if ( v4[3] == 86 )
        {
          v4 += 4;
          v10 = 1;
          UnDecorator::gName = v4;
          v9 = v4;
        }
      }
      else
      {
        a2 = (unsigned int)(v4[2] - 85);
        if ( v4[2] == 85 )
          goto LABEL_15;
        a2 = (unsigned int)(v4[2] - 86);
        if ( v4[2] == 86 )
          goto LABEL_13;
        a2 = (unsigned int)(v4[2] - 87);
        if ( v4[2] == 87 )
        {
          v6 = 1;
LABEL_15:
          v4 += 3;
          UnDecorator::gName = v4;
          v9 = v4;
LABEL_19:
          v11 = *v4;
          if ( *v4 == 88 )
          {
            UnDecorator::gName = v9 + 1;
            goto LABEL_21;
          }
          if ( v11 == 36 )
          {
            v12 = v4 + 1;
            if ( *v12 != 36 )
            {
              UnDecorator::gName = v12;
              TemplateConstant = UnDecorator::getTemplateConstant(v28, a2, v9);
              goto LABEL_36;
            }
          }
          if ( v11 == 63 )
          {
            UnDecorator::getSignedDimension(v22, a2, v9);
            if ( (UnDecorator::disableFlags & 0x4000) != 0 && UnDecorator::m_pGetParameter )
            {
              if ( v22[0] )
                *(_BYTE *)(*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)v22[0] + 16LL))(
                            v22[0],
                            String,
                            &v35) = 0;
              else
                String[0] = 0;
              v14 = atol(String);
              if ( !((__int64 (__fastcall *)(_QWORD))UnDecorator::m_pGetParameter)(v14) )
              {
                v15 = DName::DName((DName *)v29, "`template-parameter");
                DName::operator+(v15, v25, v22);
                v16 = &v30;
                v17 = v25;
                goto LABEL_33;
              }
LABEL_21:
              DName::operator=((DName *)&v20);
LABEL_37:
              v4 = UnDecorator::gName;
              if ( UnDecorator::gName - v8 > 1 && *(_DWORD *)UnDecorator::pTemplateArgList != 9 )
              {
                Replicator::operator+=(UnDecorator::pTemplateArgList, &v20);
LABEL_40:
                v4 = UnDecorator::gName;
              }
              if ( v20 )
              {
                if ( !v2 )
                  DName::operator+=(a1);
                DName::operator+=(a1, &v20);
                if ( v6 )
                  DName::operator+=(a1, "...");
                v4 = UnDecorator::gName;
              }
              goto LABEL_47;
            }
            v18 = DName::DName((DName *)v31, "`template-parameter");
            DName::operator+(v18, v26, v22);
            v16 = &v32;
            v17 = v26;
LABEL_33:
            TemplateConstant = DName::operator+(v17, v16, "'");
          }
          else
          {
            v23 = 0;
            v24 = 0;
            TemplateConstant = UnDecorator::getPrimaryDataType(v33, &v23, v9);
          }
LABEL_36:
          v20 = *(_QWORD *)TemplateConstant;
          LODWORD(v21) = *(_DWORD *)(TemplateConstant + 8);
          goto LABEL_37;
        }
        if ( v4[2] == 90 )
        {
LABEL_13:
          v4 += 3;
          UnDecorator::gName = v4;
          goto LABEL_47;
        }
      }
      if ( !v10 )
        goto LABEL_19;
LABEL_47:
      v2 = 0;
    }
    while ( !*((_BYTE *)a1 + 8) );
  }
  UnDecorator::fGetTemplateArgumentList = 0;
  return a1;
}

```

## disassembly

```asm
0x180332924  mov     rax, rsp
0x180332927  mov     [rax+10h], rbx
0x18033292b  mov     [rax+18h], rsi
0x18033292f  mov     [rax+20h], rdi
0x180332933  push    rbp
0x180332934  push    r14
0x180332936  push    r15
0x180332938  lea     rbp, [rax-5Fh]
0x18033293c  sub     rsp, 100h
0x180332943  mov     rax, cs:__security_cookie
0x18033294a  xor     rax, rsp
0x18033294d  mov     [rbp+57h+var_20], rax
0x180332951  xor     r15d, r15d
0x180332954  mov     sil, 1
0x180332957  mov     [rcx+8], r15d
0x18033295b  mov     rbx, rcx
0x18033295e  mov     [rcx], r15
0x180332961  mov     cs:?fGetTemplateArgumentList@UnDecorator@@0_NA, sil
0x180332968  cmp     [rcx+8], r15b
0x18033296c  jnz     loc_180332C0B
0x180332972  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB
0x180332979  test    byte ptr [rcx], 0BFh
0x18033297c  jz      loc_180332C0B
0x180332982  movsx   eax, byte ptr [rcx]
0x180332985  mov     r14b, r15b
0x180332988  mov     [rsp+110h+var_F0], r15
0x18033298d  mov     dword ptr [rsp+110h+var_E8], r15d
0x180332992  lea     r8d, [rax-30h]
0x180332996  cmp     r8d, 9
0x18033299a  ja      short loc_1803329CD
0x18033299c  inc     rcx
0x18033299f  lea     rdx, [rbp+57h+var_A0]
0x1803329a3  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x1803329aa  mov     rcx, cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA
0x1803329b1  call    ??AReplicator@@QEBA?AVDName@@H@Z
0x1803329b6  mov     rcx, rax
0x1803329b9  mov     rax, [rax]
0x1803329bc  mov     [rsp+110h+var_F0], rax
0x1803329c1  mov     eax, [rcx+8]
0x1803329c4  mov     dword ptr [rsp+110h+var_E8], eax
0x1803329c8  jmp     loc_180332BB9
0x1803329cd  cmp     byte ptr [rcx], 24h ; '$'
0x1803329d0  mov     rdi, rcx
0x1803329d3  mov     r8, rcx
0x1803329d6  jnz     short loc_180332A41
0x1803329d8  cmp     byte ptr [rcx+1], 24h ; '$'
0x1803329dc  jnz     short loc_180332A41
0x1803329de  movsx   edx, byte ptr [rcx+2]
0x1803329e2  mov     r9b, r15b
0x1803329e5  sub     edx, 24h ; '$'
0x1803329e8  jz      short loc_180332A21
0x1803329ea  sub     edx, 31h ; '1'
0x1803329ed  jz      short loc_180332A11
0x1803329ef  sub     edx, 1
0x1803329f2  jz      short loc_1803329FE
0x1803329f4  sub     edx, 1
0x1803329f7  jz      short loc_180332A0E
0x1803329f9  cmp     edx, 3
0x1803329fc  jnz     short loc_180332A38
0x1803329fe  add     rcx, 3
0x180332a02  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x180332a09  jmp     loc_180332BFE
0x180332a0e  mov     r14b, 1
0x180332a11  add     rcx, 3
0x180332a15  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x180332a1c  mov     r8, rcx
0x180332a1f  jmp     short loc_180332A41
0x180332a21  cmp     byte ptr [rcx+3], 56h ; 'V'
0x180332a25  jnz     short loc_180332A38
0x180332a27  add     rcx, 4
0x180332a2b  mov     r9b, 1
0x180332a2e  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x180332a35  mov     r8, rcx
0x180332a38  test    r9b, r9b
0x180332a3b  jnz     loc_180332BFE
0x180332a41  mov     al, [rcx]
0x180332a43  cmp     al, 58h ; 'X'
0x180332a45  jnz     short loc_180332A68
0x180332a47  lea     rax, [r8+1]
0x180332a4b  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x180332a52  lea     rdx, aVoid_0
0x180332a59  lea     rcx, [rsp+110h+var_F0]; this
0x180332a5e  call    ??4DName@@QEAAAEAV0@PEBD@Z
0x180332a63  jmp     loc_180332B8D
0x180332a68  cmp     al, 24h ; '$'
0x180332a6a  jnz     short loc_180332A88
0x180332a6c  inc     rcx
0x180332a6f  cmp     [rcx], al
0x180332a71  jz      short loc_180332A88
0x180332a73  mov     cs:?gName@UnDecorator@@0PEBDEB, rcx
0x180332a7a  lea     rcx, [rbp+57h+var_90]
0x180332a7e  call    ?getTemplateConstant@UnDecorator@@CA?AVDName@@XZ
0x180332a83  jmp     loc_180332B7B
0x180332a88  cmp     al, 3Fh ; '?'
0x180332a8a  jnz     loc_180332B66
0x180332a90  lea     rcx, [rsp+110h+var_E0]
0x180332a95  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x180332a9a  test    cs:?disableFlags@UnDecorator@@0KA, 4000h
0x180332aa4  jz      loc_180332B3B
0x180332aaa  cmp     cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA, r15
0x180332ab1  jz      loc_180332B3B
0x180332ab7  mov     rcx, [rsp+110h+var_E0]
0x180332abc  test    rcx, rcx
0x180332abf  jz      short loc_180332ADB
0x180332ac1  mov     rax, [rcx]
0x180332ac4  lea     r8, [rbp+57h+var_21]
0x180332ac8  lea     rdx, [rbp+57h+String]
0x180332acc  mov     rax, [rax+10h]
0x180332ad0  call    cs:__guard_dispatch_icall_fptr
0x180332ad6  mov     [rax], r15b
0x180332ad9  jmp     short loc_180332ADF
0x180332adb  mov     [rbp+57h+String], r15b
0x180332adf  lea     rcx, [rbp+57h+String]; String
0x180332ae3  call    atol
0x180332ae8  mov     ecx, eax
0x180332aea  mov     rax, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA
0x180332af1  call    cs:__guard_dispatch_icall_fptr
0x180332af7  test    rax, rax
0x180332afa  jz      short loc_180332B04
0x180332afc  mov     rdx, rax
0x180332aff  jmp     loc_180332A59
0x180332b04  lea     rdx, aTemplateParame
0x180332b0b  lea     rcx, [rbp+57h+var_80]; this
0x180332b0f  call    ??0DName@@QEAA@PEBD@Z
0x180332b14  lea     r8, [rsp+110h+var_E0]
0x180332b19  mov     rcx, rax
0x180332b1c  lea     rdx, [rbp+57h+var_C0]
0x180332b20  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180332b25  lea     rdx, [rbp+57h+var_70]
0x180332b29  lea     rcx, [rbp+57h+var_C0]
0x180332b2d  lea     r8, asc_1803822B8
0x180332b34  call    ??HDName@@QEBA?AV0@PEBD@Z
0x180332b39  jmp     short loc_180332B7B
0x180332b3b  lea     rdx, aTemplateParame
0x180332b42  lea     rcx, [rbp+57h+var_60]; this
0x180332b46  call    ??0DName@@QEAA@PEBD@Z
0x180332b4b  lea     r8, [rsp+110h+var_E0]
0x180332b50  mov     rcx, rax
0x180332b53  lea     rdx, [rbp+57h+var_B0]
0x180332b57  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180332b5c  lea     rdx, [rbp+57h+var_50]
0x180332b60  lea     rcx, [rbp+57h+var_B0]
0x180332b64  jmp     short loc_180332B2D
0x180332b66  lea     rdx, [rbp+57h+var_D0]
0x180332b6a  mov     [rbp+57h+var_D0], r15
0x180332b6e  lea     rcx, [rbp+57h+var_40]
0x180332b72  mov     [rbp+57h+var_C8], r15d
0x180332b76  call    ?getPrimaryDataType@UnDecorator@@CA?AVDName@@AEBV2@@Z
0x180332b7b  mov     rcx, rax
0x180332b7e  mov     rax, [rax]
0x180332b81  mov     [rsp+110h+var_F0], rax
0x180332b86  mov     eax, [rcx+8]
0x180332b89  mov     dword ptr [rsp+110h+var_E8], eax
0x180332b8d  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB
0x180332b94  mov     rax, rcx
0x180332b97  sub     rax, rdi
0x180332b9a  cmp     rax, 1
0x180332b9e  jle     short loc_180332BC0
0x180332ba0  mov     rax, cs:?pTemplateArgList@UnDecorator@@0PEAVReplicator@@EA
0x180332ba7  cmp     dword ptr [rax], 9
0x180332baa  jz      short loc_180332BC0
0x180332bac  lea     rdx, [rsp+110h+var_F0]
0x180332bb1  mov     rcx, rax
0x180332bb4  call    ??YReplicator@@QEAAAEAV0@AEBVDName@@@Z
0x180332bb9  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB
0x180332bc0  cmp     [rsp+110h+var_F0], r15
0x180332bc5  jz      short loc_180332BFE
0x180332bc7  test    sil, sil
0x180332bca  jnz     short loc_180332BD6
0x180332bcc  mov     dl, 2Ch ; ','
0x180332bce  mov     rcx, rbx; this
0x180332bd1  call    ??YDName@@QEAAAEAV0@D@Z
0x180332bd6  lea     rdx, [rsp+110h+var_F0]
0x180332bdb  mov     rcx, rbx
0x180332bde  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180332be3  test    r14b, r14b
0x180332be6  jz      short loc_180332BF7
0x180332be8  lea     rdx, asc_180390650
0x180332bef  mov     rcx, rbx; this
0x180332bf2  call    ??YDName@@QEAAAEAV0@PEBD@Z
0x180332bf7  mov     rcx, cs:?gName@UnDecorator@@0PEBDEB
0x180332bfe  mov     sil, r15b
0x180332c01  cmp     [rbx+8], r15b
0x180332c05  jz      loc_180332979
0x180332c0b  mov     cs:?fGetTemplateArgumentList@UnDecorator@@0_NA, r15b
0x180332c12  mov     rax, rbx
0x180332c15  mov     rcx, [rbp+57h+var_20]
0x180332c19  xor     rcx, rsp; StackCookie
0x180332c1c  call    __security_check_cookie
0x180332c21  lea     r11, [rsp+110h+var_10]
0x180332c29  mov     rbx, [r11+28h]
0x180332c2d  mov     rsi, [r11+30h]
0x180332c31  mov     rdi, [r11+38h]
0x180332c35  mov     rsp, r11
0x180332c38  pop     r15
0x180332c3a  pop     r14
0x180332c3c  pop     rbp
0x180332c3d  retn
```
