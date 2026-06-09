# UnDecorator::getZName(bool,bool)

- ea: `0x18033386c`
- end: `0x180333b45`
- name: `?getZName@UnDecorator@@CA?AVDName@@_N0@Z`
- size: `729`
- prototype: ``
- caller_count: `6`
- callee_count: `14`
- tags: ``

## callers

- `0x1803300dc`
- `0x180331260`
- `0x180332030`
- `0x1803324a8`
- `0x1803328d8`
- `0x180332fe0`

## callees

- `0x18030c3f0`
- `0x18032d7fc`
- `0x18032d94c`
- `0x18032db4c`
- `0x18032db84`
- `0x18032dbc4`
- `0x18032dc1c`
- `0x18032dc74`
- `0x18032de30`
- `0x1803325ac`
- `0x180332fe0`
- `0x18033386c`
- `0x18033a83c`
- `0x180358070`

## string_xrefs

- `0x180333944`: `template-parameter-`

## pseudocode

```c
__int64 __fastcall UnDecorator::getZName(__int64 a1, __int64 a2, char a3)
{
  char v4; // si
  bool v6; // zf
  __int64 TemplateName; // rax
  void ***v8; // rcx
  char *v9; // rax
  char v10; // dl
  void ***v11; // rax
  const char *v12; // rdi
  char *v13; // rcx
  const char *v14; // rax
  __int64 v15; // r8
  char *v16; // r9
  char *v17; // rcx
  const char *v18; // rax
  unsigned int v19; // eax
  DName *v20; // rax
  char *v21; // rdx
  DName *v22; // rax
  __int64 v23; // rax
  DName *v24; // rax
  void ***v25; // rcx
  void ***v27; // [rsp+20h] [rbp-29h] BYREF
  int v28; // [rsp+28h] [rbp-21h]
  _BYTE v29[16]; // [rsp+38h] [rbp-11h] BYREF
  _QWORD v30[2]; // [rsp+48h] [rbp-1h] BYREF
  _BYTE v31[16]; // [rsp+58h] [rbp+Fh] BYREF
  char v32[16]; // [rsp+68h] [rbp+1Fh] BYREF
  char String[15]; // [rsp+78h] [rbp+2Fh] BYREF
  char v34; // [rsp+87h] [rbp+3Eh] BYREF

  v4 = a2;
  if ( (unsigned int)(*UnDecorator::gName - 48) <= 9 )
  {
    ++UnDecorator::gName;
    Replicator::operator[](UnDecorator::pZNameList, a1);
    return a1;
  }
  v6 = *UnDecorator::gName == 63;
  v27 = 0;
  v28 = 0;
  if ( v6 )
  {
    TemplateName = UnDecorator::getTemplateName(v29, 0);
    v8 = *(void ****)TemplateName;
    v28 = *(_DWORD *)(TemplateName + 8);
    v27 = v8;
    LOBYTE(v8) = *UnDecorator::gName;
    v9 = ++UnDecorator::gName;
    if ( (_BYTE)v8 != 64 )
    {
      UnDecorator::gName = v9 - 1;
      v10 = *(v9 - 1);
      v11 = &off_1803FB120;
      v28 = (v10 != 0) + 1;
      if ( v10 )
        v11 = 0;
      v27 = v11;
    }
    goto LABEL_34;
  }
  v12 = "template-parameter-";
  v13 = UnDecorator::gName;
  v14 = "template-parameter-";
  v15 = 18;
  do
  {
    LOBYTE(a2) = *v13;
    if ( !*v13 )
      break;
    if ( (_BYTE)a2 != *v14 )
      break;
    ++v13;
    ++v14;
    v15 = (unsigned int)(v15 - 1);
  }
  while ( (_DWORD)v15 );
  if ( *v13 == *v14 )
  {
    v16 = UnDecorator::gName + 19;
  }
  else
  {
    v12 = "generic-type-";
    v17 = UnDecorator::gName;
    v18 = "generic-type-";
    v15 = 12;
    do
    {
      LOBYTE(a2) = *v17;
      if ( !*v17 )
        break;
      if ( (_BYTE)a2 != *v18 )
        break;
      ++v17;
      ++v18;
      v15 = (unsigned int)(v15 - 1);
    }
    while ( (_DWORD)v15 );
    if ( *v17 != *v18 )
    {
      if ( a3 && *UnDecorator::gName == 64 )
      {
        v27 = 0;
        ++UnDecorator::gName;
        v28 = 0;
      }
      else
      {
        v24 = DName::DName((DName *)v31, (const char **)&UnDecorator::gName, 64);
        v25 = *(void ****)v24;
        LODWORD(v24) = *((_DWORD *)v24 + 2);
        v27 = v25;
        v28 = (int)v24;
      }
      goto LABEL_34;
    }
    v16 = UnDecorator::gName + 13;
  }
  UnDecorator::gName = v16;
  UnDecorator::getSignedDimension(v30, a2, v15);
  if ( (UnDecorator::disableFlags & 0x4000) != 0 && UnDecorator::m_pGetParameter )
  {
    if ( v30[0] )
      *(_BYTE *)(*(__int64 (__fastcall **)(_QWORD, char *, char *))(*(_QWORD *)v30[0] + 16LL))(v30[0], String, &v34) = 0;
    else
      String[0] = 0;
    v19 = atol(String);
    if ( ((__int64 (__fastcall *)(_QWORD))UnDecorator::m_pGetParameter)(v19) )
    {
      DName::operator=((DName *)&v27);
      goto LABEL_34;
    }
    DName::operator=((DName *)&v27);
    v20 = DName::DName((DName *)v32, v12);
    DName::operator+(v20, v29, v30);
    v21 = v31;
  }
  else
  {
    DName::operator=((DName *)&v27);
    v22 = DName::DName((DName *)v31, v12);
    DName::operator+(v22, v29, v30);
    v21 = v32;
  }
  v23 = DName::operator+(v29, v21, "'");
  DName::operator+=(&v27, v23);
LABEL_34:
  if ( v4 && *(_DWORD *)UnDecorator::pZNameList != 9 )
    Replicator::operator+=(UnDecorator::pZNameList, &v27);
  *(_QWORD *)a1 = v27;
  *(_DWORD *)(a1 + 8) = v28;
  return a1;
}

```

## disassembly

```asm
0x18033386c  mov     [rsp-8+arg_8], rbx
0x180333871  mov     [rsp-8+arg_10], rsi
0x180333876  push    rbp
0x180333877  push    rdi
0x180333878  push    r14
0x18033387a  lea     rbp, [rsp-47h]
0x18033387f  sub     rsp, 90h
0x180333886  mov     rax, cs:__security_cookie
0x18033388d  xor     rax, rsp
0x180333890  mov     [rbp+57h+var_18], rax
0x180333894  mov     r9, cs:?gName@UnDecorator@@0PEBDEB
0x18033389b  mov     r10b, r8b
0x18033389e  mov     sil, dl
0x1803338a1  mov     rbx, rcx
0x1803338a4  movsx   r8d, byte ptr [r9]
0x1803338a8  add     r8d, 0FFFFFFD0h
0x1803338ac  cmp     r8d, 9
0x1803338b0  ja      short loc_1803338D0
0x1803338b2  inc     r9
0x1803338b5  mov     rdx, rcx
0x1803338b8  mov     rcx, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA
0x1803338bf  mov     cs:?gName@UnDecorator@@0PEBDEB, r9
0x1803338c6  call    ??AReplicator@@QEBA?AVDName@@H@Z
0x1803338cb  jmp     loc_180333B1E
0x1803338d0  xor     r14d, r14d
0x1803338d3  cmp     byte ptr [r9], 3Fh ; '?'
0x1803338d7  mov     [rbp+57h+var_80], r14
0x1803338db  mov     [rbp+57h+var_78], r14d
0x1803338df  jnz     short loc_180333944
0x1803338e1  xor     edx, edx
0x1803338e3  lea     rcx, [rbp+57h+var_68]
0x1803338e7  call    ?getTemplateName@UnDecorator@@CA?AVDName@@_N@Z
0x1803338ec  mov     rcx, [rax]
0x1803338ef  mov     eax, [rax+8]
0x1803338f2  mov     [rbp+57h+var_78], eax
0x1803338f5  mov     rax, cs:?gName@UnDecorator@@0PEBDEB
0x1803338fc  mov     [rbp+57h+var_80], rcx
0x180333900  mov     cl, [rax]
0x180333902  inc     rax
0x180333905  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x18033390c  cmp     cl, 40h ; '@'
0x18033390f  jz      loc_180333AF7
0x180333915  dec     rax
0x180333918  mov     cs:?gName@UnDecorator@@0PEBDEB, rax
0x18033391f  mov     dl, [rax]
0x180333921  mov     al, dl
0x180333923  neg     al
0x180333925  lea     rax, off_1803FB120
0x18033392c  sbb     ecx, ecx
0x18033392e  neg     ecx
0x180333930  inc     ecx
0x180333932  test    dl, dl
0x180333934  mov     [rbp+57h+var_78], ecx
0x180333937  cmovnz  rax, r14
0x18033393b  mov     [rbp+57h+var_80], rax
0x18033393f  jmp     loc_180333AF7
0x180333944  lea     rdi, aTemplateParame_0
0x18033394b  mov     rcx, r9
0x18033394e  mov     rax, rdi
0x180333951  mov     r8d, 12h
0x180333957  or      r11d, 0FFFFFFFFh
0x18033395b  mov     dl, [rcx]
0x18033395d  test    dl, dl
0x18033395f  jz      short loc_180333970
0x180333961  cmp     dl, [rax]
0x180333963  jnz     short loc_180333970
0x180333965  inc     rcx
0x180333968  inc     rax
0x18033396b  add     r8d, r11d
0x18033396e  jnz     short loc_18033395B
0x180333970  movzx   ecx, byte ptr [rcx]
0x180333973  movzx   eax, byte ptr [rax]
0x180333976  cmp     ecx, eax
0x180333978  jnz     short loc_180333980
0x18033397a  add     r9, 13h
0x18033397e  jmp     short loc_1803339BA
0x180333980  lea     rdi, aGenericType
0x180333987  mov     rcx, r9
0x18033398a  mov     rax, rdi
0x18033398d  mov     r8d, 0Ch
0x180333993  mov     dl, [rcx]
0x180333995  test    dl, dl
0x180333997  jz      short loc_1803339A8
0x180333999  cmp     dl, [rax]
0x18033399b  jnz     short loc_1803339A8
0x18033399d  inc     rcx
0x1803339a0  inc     rax
0x1803339a3  add     r8d, r11d
0x1803339a6  jnz     short loc_180333993
0x1803339a8  movzx   ecx, byte ptr [rcx]
0x1803339ab  movzx   eax, byte ptr [rax]
0x1803339ae  cmp     ecx, eax
0x1803339b0  jnz     loc_180333AB8
0x1803339b6  add     r9, 0Dh
0x1803339ba  lea     rcx, [rbp+57h+var_58]
0x1803339be  mov     cs:?gName@UnDecorator@@0PEBDEB, r9
0x1803339c5  call    ?getSignedDimension@UnDecorator@@CA?AVDName@@XZ
0x1803339ca  test    cs:?disableFlags@UnDecorator@@0KA, 4000h
0x1803339d4  jz      loc_180333A6A
0x1803339da  cmp     cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA, r14
0x1803339e1  jz      loc_180333A6A
0x1803339e7  mov     rcx, [rbp+57h+var_58]
0x1803339eb  test    rcx, rcx
0x1803339ee  jz      short loc_180333A0A
0x1803339f0  mov     rax, [rcx]
0x1803339f3  lea     r8, [rbp+57h+var_19]
0x1803339f7  lea     rdx, [rbp+57h+String]
0x1803339fb  mov     rax, [rax+10h]
0x1803339ff  call    cs:__guard_dispatch_icall_fptr
0x180333a05  mov     [rax], r14b
0x180333a08  jmp     short loc_180333A0E
0x180333a0a  mov     [rbp+57h+String], r14b
0x180333a0e  lea     rcx, [rbp+57h+String]; String
0x180333a12  call    atol
0x180333a17  mov     ecx, eax
0x180333a19  mov     rax, cs:?m_pGetParameter@UnDecorator@@0P6APEADJ@ZEA
0x180333a20  call    cs:__guard_dispatch_icall_fptr
0x180333a26  lea     rcx, [rbp+57h+var_80]; this
0x180333a2a  test    rax, rax
0x180333a2d  jz      short loc_180333A3C
0x180333a2f  mov     rdx, rax
0x180333a32  call    ??4DName@@QEAAAEAV0@PEBD@Z
0x180333a37  jmp     loc_180333AF7
0x180333a3c  lea     rdx, asc_1803FAC68
0x180333a43  call    ??4DName@@QEAAAEAV0@PEBD@Z
0x180333a48  mov     rdx, rdi; char *
0x180333a4b  lea     rcx, [rbp+57h+var_38]; this
0x180333a4f  call    ??0DName@@QEAA@PEBD@Z
0x180333a54  lea     r8, [rbp+57h+var_58]
0x180333a58  mov     rcx, rax
0x180333a5b  lea     rdx, [rbp+57h+var_68]
0x180333a5f  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180333a64  lea     rdx, [rbp+57h+var_48]
0x180333a68  jmp     short loc_180333A9A
0x180333a6a  lea     rdx, asc_1803FAC68
0x180333a71  lea     rcx, [rbp+57h+var_80]; this
0x180333a75  call    ??4DName@@QEAAAEAV0@PEBD@Z
0x180333a7a  mov     rdx, rdi; char *
0x180333a7d  lea     rcx, [rbp+57h+var_48]; this
0x180333a81  call    ??0DName@@QEAA@PEBD@Z
0x180333a86  lea     r8, [rbp+57h+var_58]
0x180333a8a  mov     rcx, rax
0x180333a8d  lea     rdx, [rbp+57h+var_68]
0x180333a91  call    ??HDName@@QEBA?AV0@AEBV0@@Z
0x180333a96  lea     rdx, [rbp+57h+var_38]
0x180333a9a  lea     r8, asc_1803822B8
0x180333aa1  lea     rcx, [rbp+57h+var_68]
0x180333aa5  call    ??HDName@@QEBA?AV0@PEBD@Z
0x180333aaa  mov     rdx, rax
0x180333aad  lea     rcx, [rbp+57h+var_80]
0x180333ab1  call    ??YDName@@QEAAAEAV0@AEBV0@@Z
0x180333ab6  jmp     short loc_180333AF7
0x180333ab8  test    r10b, r10b
0x180333abb  jz      short loc_180333AD7
0x180333abd  cmp     byte ptr [r9], 40h ; '@'
0x180333ac1  jnz     short loc_180333AD7
0x180333ac3  inc     r9
0x180333ac6  mov     [rbp+57h+var_80], r14
0x180333aca  mov     cs:?gName@UnDecorator@@0PEBDEB, r9
0x180333ad1  mov     [rbp+57h+var_78], r14d
0x180333ad5  jmp     short loc_180333AF7
0x180333ad7  mov     r8b, 40h ; '@'; char
0x180333ada  lea     rdx, ?gName@UnDecorator@@0PEBDEB; char **
0x180333ae1  lea     rcx, [rbp+57h+var_48]; this
0x180333ae5  call    ??0DName@@QEAA@AEAPEBDD@Z
0x180333aea  mov     rcx, [rax]
0x180333aed  mov     eax, [rax+8]
0x180333af0  mov     [rbp+57h+var_80], rcx
0x180333af4  mov     [rbp+57h+var_78], eax
0x180333af7  test    sil, sil
0x180333afa  jz      short loc_180333B11
0x180333afc  mov     rcx, cs:?pZNameList@UnDecorator@@0PEAVReplicator@@EA
0x180333b03  cmp     dword ptr [rcx], 9
0x180333b06  jz      short loc_180333B11
0x180333b08  lea     rdx, [rbp+57h+var_80]
0x180333b0c  call    ??YReplicator@@QEAAAEAV0@AEBVDName@@@Z
0x180333b11  mov     rax, [rbp+57h+var_80]
0x180333b15  mov     [rbx], rax
0x180333b18  mov     eax, [rbp+57h+var_78]
0x180333b1b  mov     [rbx+8], eax
0x180333b1e  mov     rax, rbx
0x180333b21  mov     rcx, [rbp+57h+var_18]
0x180333b25  xor     rcx, rsp; StackCookie
0x180333b28  call    __security_check_cookie
0x180333b2d  lea     r11, [rsp+0A0h+var_10]
0x180333b35  mov     rbx, [r11+28h]
0x180333b39  mov     rsi, [r11+30h]
0x180333b3d  mov     rsp, r11
0x180333b40  pop     r14
0x180333b42  pop     rdi
0x180333b43  pop     rbp
0x180333b44  retn
```
