# UnDecorator::getTemplateTypeArgument(void)

- ea: `0x18002cc84`
- end: `0x18002ce00`
- name: `?getTemplateTypeArgument@UnDecorator@@AEAA?AVDName@@XZ`
- size: `380`
- prototype: ``
- caller_count: `5`
- callee_count: `10`
- tags: ``

## callers

- `0x180026f28`
- `0x18002c25c`
- `0x18002c7dc`
- `0x18002d380`
- `0x18002d528`

## callees

- `0x180002810`
- `0x180020bb0`
- `0x180024480`
- `0x180024bd4`
- `0x180025270`
- `0x1800252a4`
- `0x18002ad90`
- `0x18002bd0c`
- `0x18002cc84`
- `0x1800603f0`

## string_xrefs

- `0x18002cd79`: ``template-parameter`

## pseudocode

```c
DName *__fastcall UnDecorator::getTemplateTypeArgument(__int64 a1, DName *a2)
{
  _BYTE *v2; // rax
  __int64 (__fastcall *v5)(_QWORD); // rbx
  unsigned int v6; // eax
  __int64 v7; // rax
  DName *v8; // rax
  __int64 v9; // r8
  __int128 v11; // [rsp+20h] [rbp-39h] BYREF
  __int64 v12; // [rsp+30h] [rbp-29h] BYREF
  struct UnDecorator *v13; // [rsp+38h] [rbp-21h]
  int v14; // [rsp+40h] [rbp-19h]
  _BYTE v15[24]; // [rsp+48h] [rbp-11h] BYREF
  _BYTE v16[32]; // [rsp+60h] [rbp+7h] BYREF
  char String[16]; // [rsp+80h] [rbp+27h] BYREF

  v2 = *(_BYTE **)(a1 + 256);
  if ( *v2 == 88 )
  {
    *(_DWORD *)&String[8] = 4;
    *(_QWORD *)(a1 + 256) = v2 + 1;
    *(_QWORD *)String = "void";
    v11 = *(_OWORD *)String;
    DName::DName(a2, (struct UnDecorator *)a1, (const struct StringLiteral *)&v11);
  }
  else if ( *v2 == 63 )
  {
    UnDecorator::getSignedDimension(a1, &v12);
    if ( (*(_DWORD *)(a1 + 272) & 0x4000) == 0 || !*(_QWORD *)(a1 + 280) )
      goto LABEL_10;
    *(_OWORD *)String = 0;
    if ( v12 )
      *(_BYTE *)(*(__int64 (__fastcall **)(__int64, char *, char *))(*(_QWORD *)v12 + 24LL))(v12, String, &String[15]) = 0;
    v5 = *(__int64 (__fastcall **)(_QWORD))(a1 + 280);
    v6 = atol(String);
    v7 = v5(v6);
    if ( v7 )
    {
      DName::DName(a2, a1, v7, 0);
    }
    else
    {
LABEL_10:
      *(_QWORD *)&v11 = "`template-parameter";
      DWORD2(v11) = 19;
      v8 = DName::DName((DName *)v16, v13, (const struct StringLiteral *)&v11);
      DName::operator+(v8, v15, &v12);
      LOBYTE(v9) = 39;
      DName::operator+(v15, a2, v9);
    }
  }
  else
  {
    v13 = (struct UnDecorator *)a1;
    v12 = 0;
    v14 = 0;
    UnDecorator::getPrimaryDataType(a1, a2, &v12);
  }
  return a2;
}

```

## disassembly

```asm
0x18002cc84  mov     [rsp-8+arg_10], rbx
0x18002cc89  push    rbp
0x18002cc8a  push    rsi
0x18002cc8b  push    rdi
0x18002cc8c  lea     rbp, [rsp-47h]
0x18002cc91  sub     rsp, 0A0h
0x18002cc98  mov     rax, cs:__security_cookie
0x18002cc9f  xor     rax, rsp
0x18002cca2  mov     [rbp+57h+var_20], rax
0x18002cca6  mov     rax, [rcx+100h]
0x18002ccad  mov     rsi, rdx
0x18002ccb0  mov     rdi, rcx
0x18002ccb3  cmp     byte ptr [rax], 58h ; 'X'
0x18002ccb6  jnz     short loc_18002CCF2
0x18002ccb8  lea     rcx, [rax+1]
0x18002ccbc  mov     dword ptr [rbp+57h+String+8], 4
0x18002ccc3  lea     rax, aVoid_0; "void"
0x18002ccca  mov     [rdi+100h], rcx
0x18002ccd1  mov     qword ptr [rbp+57h+String], rax
0x18002ccd5  lea     r8, [rbp+57h+var_90]; struct StringLiteral *
0x18002ccd9  movaps  xmm0, xmmword ptr [rbp+57h+String]
0x18002ccdd  mov     rdx, rdi; struct UnDecorator *
0x18002cce0  mov     rcx, rsi; this
0x18002cce3  movdqa  [rbp+57h+var_90], xmm0
0x18002cce8  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002cced  jmp     loc_18002CDDE
0x18002ccf2  cmp     byte ptr [rax], 3Fh ; '?'
0x18002ccf5  jnz     loc_18002CDC2
0x18002ccfb  lea     rdx, [rbp+57h+var_80]
0x18002ccff  call    ?getSignedDimension@UnDecorator@@AEAA?AVDName@@XZ; UnDecorator::getSignedDimension(void)
0x18002cd04  test    dword ptr [rdi+110h], 4000h
0x18002cd0e  jz      short loc_18002CD75
0x18002cd10  cmp     qword ptr [rdi+118h], 0
0x18002cd18  jz      short loc_18002CD75
0x18002cd1a  mov     rcx, [rbp+57h+var_80]
0x18002cd1e  xorps   xmm0, xmm0
0x18002cd21  movups  xmmword ptr [rbp+57h+String], xmm0
0x18002cd25  test    rcx, rcx
0x18002cd28  jz      short loc_18002CD42
0x18002cd2a  mov     rax, [rcx]
0x18002cd2d  lea     r8, [rbp+57h+String+0Fh]
0x18002cd31  lea     rdx, [rbp+57h+String]
0x18002cd35  mov     rax, [rax+18h]
0x18002cd39  call    cs:__guard_dispatch_icall_fptr
0x18002cd3f  mov     byte ptr [rax], 0
0x18002cd42  mov     rbx, [rdi+118h]
0x18002cd49  lea     rcx, [rbp+57h+String]; String
0x18002cd4d  call    atol
0x18002cd52  mov     ecx, eax
0x18002cd54  mov     rax, rbx
0x18002cd57  call    cs:__guard_dispatch_icall_fptr
0x18002cd5d  test    rax, rax
0x18002cd60  jz      short loc_18002CD75
0x18002cd62  xor     r9d, r9d
0x18002cd65  mov     r8, rax
0x18002cd68  mov     rdx, rdi
0x18002cd6b  mov     rcx, rsi
0x18002cd6e  call    ??$?0$0A@@DName@@QEAA@PEAVUnDecorator@@PEBDU?$StringLifeSelector@$0A@@@@Z; DName::DName(UnDecorator *,char const *,StringLifeSelector<0>)
0x18002cd73  jmp     short loc_18002CDDE
0x18002cd75  mov     rdx, [rbp+57h+var_78]; struct UnDecorator *
0x18002cd79  lea     rax, aTemplateParame; "`template-parameter"
0x18002cd80  mov     qword ptr [rbp+57h+var_90], rax
0x18002cd84  lea     r8, [rbp+57h+var_90]; struct StringLiteral *
0x18002cd88  mov     dword ptr [rbp+57h+var_90+8], 13h
0x18002cd8f  lea     rcx, [rbp+57h+var_50]; this
0x18002cd93  movaps  xmm0, [rbp+57h+var_90]
0x18002cd97  movdqa  [rbp+57h+var_90], xmm0
0x18002cd9c  call    ??0DName@@QEAA@PEAVUnDecorator@@AEBUStringLiteral@@@Z; DName::DName(UnDecorator *,StringLiteral const &)
0x18002cda1  lea     r8, [rbp+57h+var_80]
0x18002cda5  mov     rcx, rax
0x18002cda8  lea     rdx, [rbp+57h+var_68]
0x18002cdac  call    ??HDName@@QEBA?AV0@AEBV0@@Z; DName::operator+(DName const &)
0x18002cdb1  mov     r8b, 27h ; '''
0x18002cdb4  lea     rcx, [rbp+57h+var_68]
0x18002cdb8  mov     rdx, rsi
0x18002cdbb  call    ??HDName@@QEBA?AV0@D@Z; DName::operator+(char)
0x18002cdc0  jmp     short loc_18002CDDE
0x18002cdc2  lea     r8, [rbp+57h+var_80]
0x18002cdc6  mov     [rbp+57h+var_78], rdi
0x18002cdca  mov     [rbp+57h+var_80], 0
0x18002cdd2  mov     [rbp+57h+var_70], 0
0x18002cdd9  call    ?getPrimaryDataType@UnDecorator@@AEAA?AVDName@@AEBV2@@Z; UnDecorator::getPrimaryDataType(DName const &)
0x18002cdde  mov     rax, rsi
0x18002cde1  mov     rcx, [rbp+57h+var_20]
0x18002cde5  xor     rcx, rsp; StackCookie
0x18002cde8  call    __security_check_cookie
0x18002cded  mov     rbx, [rsp+0B0h+arg_10]
0x18002cdf5  add     rsp, 0A0h
0x18002cdfc  pop     rdi
0x18002cdfd  pop     rsi
0x18002cdfe  pop     rbp
0x18002cdff  retn
```
