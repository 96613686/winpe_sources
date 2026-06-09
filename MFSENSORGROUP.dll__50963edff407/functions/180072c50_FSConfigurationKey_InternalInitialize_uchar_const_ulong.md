# FSConfigurationKey::InternalInitialize(uchar const *,ulong)

- ea: `0x180072c50`
- end: `0x180073231`
- name: `?InternalInitialize@FSConfigurationKey@@MEAAJPEBEK@Z`
- size: `1505`
- prototype: `int(FSConfigurationKey *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, registry_config`

## callees

- `0x180005fa0`
- `0x18000c94c`
- `0x18000f5a0`
- `0x1800133fc`
- `0x180015e80`
- `0x180016328`
- `0x18001635c`
- `0x18001c854`
- `0x18001c96c`
- `0x180028eb4`
- `0x180037220`
- `0x18003cc5c`
- `0x180044b28`
- `0x180072c50`
- `0x180073c6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180072f40`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180072fd1`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18007305e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180072f40`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180072fd1`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18007305e`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitialize(void **this, const unsigned __int8 *a2, unsigned int a3)
{
  char v3; // al
  unsigned __int64 v4; // r15
  BlobTrace *v7; // rax
  const char *String; // rax
  int v9; // edx
  int v10; // r8d
  unsigned int v11; // r8d
  unsigned int v12; // eax
  int v13; // eax
  unsigned int v14; // ebx
  __int64 v15; // rdx
  int v16; // r9d
  unsigned int v17; // ecx
  int v18; // edx
  __int64 v19; // r10
  unsigned int v20; // eax
  unsigned __int16 **v21; // r12
  unsigned __int64 v22; // rbx
  unsigned int v23; // r13d
  void **unique; // rax
  void *v25; // rcx
  char v26; // dl
  __int16 v27; // r8
  int v28; // r9d
  unsigned __int16 **v29; // r12
  void **v30; // rax
  void *v31; // rcx
  char v32; // dl
  __int16 v33; // r8
  int v34; // r9d
  unsigned __int64 v35; // rbx
  unsigned __int16 **v36; // r12
  void **v37; // rax
  void *v38; // rcx
  char v39; // dl
  __int16 v40; // r8
  int v41; // r9d
  char *v42; // rbx
  __int64 v43; // rdx
  __int64 i; // r8
  __int64 v45; // rcx
  __int64 v46; // rdx
  char v47; // al
  void **v48; // rax
  void *v49; // rcx
  wchar_t v51; // [rsp+20h] [rbp-50h]
  wchar_t v52; // [rsp+20h] [rbp-50h]
  wchar_t v53; // [rsp+20h] [rbp-50h]
  long double v54; // [rsp+28h] [rbp-48h]
  long double v55; // [rsp+28h] [rbp-48h]
  long double v56; // [rsp+28h] [rbp-48h]
  void **v57; // [rsp+50h] [rbp-20h] BYREF
  _BYTE v58[24]; // [rsp+58h] [rbp-18h] BYREF
  void *Block; // [rsp+A8h] [rbp+38h] BYREF
  unsigned __int64 v60; // [rsp+B8h] [rbp+48h]

  v3 = 0;
  v4 = a3;
  LODWORD(Block) = 0;
  if ( !a2 || a3 < 0x40 || a3 < *((_DWORD *)a2 + 1) )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 74;
LABEL_74:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v13);
LABEL_75:
    if ( byte_18008D62D )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 94, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v14);
    return v14;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v7 = BlobTrace::BlobTrace((BlobTrace *)&v57, (void *)(a2 + 8), 0x20u);
    String = FSString::GetString((BlobTrace *)((char *)v7 + 8));
    WPP_SF_qqddds(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v9,
      v10,
      (_DWORD)this,
      (char)a2,
      v4,
      *(_DWORD *)a2,
      *((_DWORD *)a2 + 1),
      (__int64)String);
    v3 = 1;
  }
  if ( (v3 & 1) != 0 )
  {
    v57 = &BlobTrace::`vftable';
    FSString::~FSString((FSString *)v58);
  }
  v11 = *((_DWORD *)a2 + 11);
  v12 = v11 + 64;
  if ( v11 >= 0xFFFFFFC0 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 76;
    goto LABEL_74;
  }
  v16 = *((_DWORD *)a2 + 13);
  v17 = v16 + v12;
  if ( v16 + v12 < v12 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 77;
    goto LABEL_74;
  }
  v18 = *((_DWORD *)a2 + 15);
  if ( v18 + v17 < v17 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 78;
    goto LABEL_74;
  }
  if ( (unsigned int)v4 < v18 + v17 )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 79;
    goto LABEL_74;
  }
  v19 = *((unsigned int *)a2 + 10);
  if ( (unsigned int)v19 >= *((_DWORD *)a2 + 12)
    || (v20 = *((_DWORD *)a2 + 14), *((_DWORD *)a2 + 12) >= v20)
    || v20 >= (unsigned int)v4
    || a2[(unsigned int)(v4 - 1)]
    || a2[(unsigned int)(v4 - 2)]
    || (((unsigned __int8)v11 | (unsigned __int8)(v16 | v18)) & 1) != 0 )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 80;
    goto LABEL_74;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      81,
      (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
      (_DWORD)this,
      (__int64)&a2[v19]);
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        82,
        (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        (_DWORD)this,
        (__int64)&a2[*((unsigned int *)a2 + 12)]);
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          83,
          (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
          (_DWORD)this,
          (__int64)&a2[*((unsigned int *)a2 + 14)]);
    }
  }
  v21 = (unsigned __int16 **)(this + 28);
  v22 = (unsigned __int64)*((unsigned int *)a2 + 11) >> 1;
  v23 = *((_DWORD *)a2 + 13) >> 1;
  LODWORD(v60) = *((_DWORD *)a2 + 15) >> 1;
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v22);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 28, unique);
  v25 = Block;
  Block = 0;
  if ( v25 )
    operator delete(v25);
  if ( !*v21 )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 84;
    goto LABEL_74;
  }
  v13 = StringCchCopyW(*v21, v22, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 10)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 85;
    goto LABEL_74;
  }
  o((wchar_t)*v21, v26, v27, v28, v51, v54);
  v29 = (unsigned __int16 **)(this + 30);
  v30 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, v23);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 30, v30);
  v31 = Block;
  Block = 0;
  if ( v31 )
    operator delete(v31);
  if ( !*v29 )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 86;
    goto LABEL_74;
  }
  v13 = StringCchCopyW(*v29, v23, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 12)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 87;
    goto LABEL_74;
  }
  o((wchar_t)*v29, v32, v33, v34, v52, v55);
  v35 = (unsigned int)v60;
  v36 = (unsigned __int16 **)(this + 29);
  v37 = (void **)wil::make_unique_nothrow<unsigned short [0]>(&Block, (unsigned int)v60);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 29, v37);
  v38 = Block;
  Block = 0;
  if ( v38 )
    operator delete(v38);
  if ( !*v36 )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 88;
    goto LABEL_74;
  }
  v13 = StringCchCopyW(*v36, v35, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 14)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 89;
    goto LABEL_74;
  }
  o((wchar_t)*v36, v39, v40, v41, v53, v56);
  v42 = (char *)(this + 7);
  if ( memcpy_s_1(this + 7, 0x20u, a2 + 8, 0x20u) )
  {
    v13 = -1072875845;
    v14 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 90;
    goto LABEL_74;
  }
  if ( this == (void **)-56LL )
  {
    v13 = -2147024809;
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 91;
    goto LABEL_74;
  }
  LODWORD(v43) = 0;
  for ( i = 0; i != 32; ++i )
  {
    v45 = (unsigned int)v43;
    v46 = (unsigned int)(v43 + 1);
    *((_WORD *)this + v45 + 44) = a0123456789abcd[(unsigned __int64)(unsigned __int8)v42[i] >> 4];
    v47 = v42[i];
    *((_WORD *)this + v46 + 44) = a0123456789abcd[v47 & 0xF];
    v43 = (unsigned int)(v46 + 1);
  }
  *((_WORD *)this + v43 + 44) = 0;
  v48 = (void **)wil::make_unique_nothrow<unsigned char [0]>(&Block, v4);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=(this + 31, v48);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&Block);
  v49 = this[31];
  if ( !v49 )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 92;
    goto LABEL_74;
  }
  if ( memcpy_s_1(v49, v4, a2, v4) )
  {
    v13 = -1072875845;
    v14 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_75;
    v15 = 93;
    goto LABEL_74;
  }
  v14 = 0;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 95, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, 0);
  return v14;
}

```

## disassembly

```asm
0x180072c50  mov     [rsp-28h+arg_0], rbx
0x180072c55  mov     [rsp-28h+arg_10], rsi
0x180072c5a  push    rbp
0x180072c5b  push    r12
0x180072c5d  push    r13
0x180072c5f  push    r14
0x180072c61  push    r15
0x180072c63  mov     rbp, rsp
0x180072c66  sub     rsp, 70h
0x180072c6a  xor     eax, eax
0x180072c6c  mov     r15d, r8d
0x180072c6f  mov     dword ptr [rbp+Block], eax
0x180072c72  mov     r14, rdx
0x180072c75  mov     rsi, rcx
0x180072c78  test    rdx, rdx
0x180072c7b  jz      loc_1800731B3
0x180072c81  cmp     r15d, 40h ; '@'
0x180072c85  jb      loc_1800731B3
0x180072c8b  cmp     r15d, [rdx+4]
0x180072c8f  jb      loc_1800731B3
0x180072c95  mov     bl, 8
0x180072c97  cmp     cs:byte_18008D62D, bl
0x180072c9d  jb      short loc_180072CF2
0x180072c9f  add     rdx, 8; void *
0x180072ca3  lea     r8d, [rax+20h]; unsigned int
0x180072ca7  lea     rcx, [rbp+var_20]; this
0x180072cab  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x180072cb0  lea     rcx, [rax+8]; this
0x180072cb4  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180072cb9  mov     rcx, cs:WPP_GLOBAL_Control
0x180072cc0  mov     r9, rsi
0x180072cc3  mov     [rsp+70h+var_30], rax
0x180072cc8  mov     eax, [r14+4]
0x180072ccc  mov     [rsp+70h+var_38], eax
0x180072cd0  mov     eax, [r14]
0x180072cd3  mov     rcx, [rcx+0D8h]
0x180072cda  mov     [rsp+70h+var_40], eax
0x180072cde  mov     dword ptr [rsp+70h+var_48], r15d
0x180072ce3  mov     [rsp+70h+var_50], r14
0x180072ce8  call    WPP_SF_qqddds
0x180072ced  mov     eax, 1
0x180072cf2  test    al, 1
0x180072cf4  jz      short loc_180072D0A
0x180072cf6  lea     rax, ??_7BlobTrace@@6B@; const BlobTrace::`vftable'
0x180072cfd  lea     rcx, [rbp+var_18]; this
0x180072d01  mov     [rbp+var_20], rax
0x180072d05  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180072d0a  mov     r8d, [r14+2Ch]
0x180072d0e  lea     eax, [r8+40h]
0x180072d12  cmp     eax, 40h ; '@'
0x180072d15  jnb     short loc_180072D35
0x180072d17  mov     eax, 80070216h
0x180072d1c  mov     ebx, eax
0x180072d1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d25  jb      loc_1800731E6
0x180072d2b  mov     edx, 4Ch ; 'L'
0x180072d30  jmp     loc_1800731C8
0x180072d35  mov     r9d, [r14+34h]
0x180072d39  lea     ecx, [r9+rax]
0x180072d3d  cmp     ecx, eax
0x180072d3f  jnb     short loc_180072D5F
0x180072d41  mov     eax, 80070216h
0x180072d46  mov     ebx, eax
0x180072d48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d4f  jb      loc_1800731E6
0x180072d55  mov     edx, 4Dh ; 'M'
0x180072d5a  jmp     loc_1800731C8
0x180072d5f  mov     edx, [r14+3Ch]
0x180072d63  lea     eax, [rdx+rcx]
0x180072d66  cmp     eax, ecx
0x180072d68  jnb     short loc_180072D88
0x180072d6a  mov     eax, 80070216h
0x180072d6f  mov     ebx, eax
0x180072d71  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d78  jb      loc_1800731E6
0x180072d7e  mov     edx, 4Eh ; 'N'
0x180072d83  jmp     loc_1800731C8
0x180072d88  cmp     r15d, eax
0x180072d8b  jnb     short loc_180072DAB
0x180072d8d  mov     eax, 80070057h
0x180072d92  mov     ebx, eax
0x180072d94  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072d9b  jb      loc_1800731E6
0x180072da1  mov     edx, 4Fh ; 'O'
0x180072da6  jmp     loc_1800731C8
0x180072dab  mov     r10d, [r14+28h]
0x180072daf  cmp     r10d, [r14+30h]
0x180072db3  jnb     loc_18007319C
0x180072db9  mov     eax, [r14+38h]
0x180072dbd  cmp     [r14+30h], eax
0x180072dc1  jnb     loc_18007319C
0x180072dc7  cmp     eax, r15d
0x180072dca  jnb     loc_18007319C
0x180072dd0  lea     eax, [r15-1]
0x180072dd4  cmp     byte ptr [rax+r14], 0
0x180072dd9  jnz     loc_18007319C
0x180072ddf  lea     eax, [r15-2]
0x180072de3  cmp     byte ptr [rax+r14], 0
0x180072de8  jnz     loc_18007319C
0x180072dee  or      edx, r9d
0x180072df1  or      edx, r8d
0x180072df4  test    dl, 1
0x180072df7  jnz     loc_18007319C
0x180072dfd  cmp     cs:byte_18008D62D, bl
0x180072e03  jb      loc_180072EA0
0x180072e09  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e10  lea     rax, [r14+r10]
0x180072e14  mov     edx, 51h ; 'Q'
0x180072e19  mov     [rsp+70h+var_50], rax
0x180072e1e  mov     r9, rsi
0x180072e21  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180072e28  mov     rcx, [rcx+0D8h]
0x180072e2f  call    WPP_SF_qS
0x180072e34  cmp     cs:byte_18008D62D, bl
0x180072e3a  jb      short loc_180072EA0
0x180072e3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e43  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180072e4a  mov     eax, [r14+30h]
0x180072e4e  mov     edx, 52h ; 'R'
0x180072e53  add     rax, r14
0x180072e56  mov     r9, rsi
0x180072e59  mov     [rsp+70h+var_50], rax
0x180072e5e  mov     rcx, [rcx+0D8h]
0x180072e65  call    WPP_SF_qS
0x180072e6a  cmp     cs:byte_18008D62D, bl
0x180072e70  jb      short loc_180072EA0
0x180072e72  mov     rcx, cs:WPP_GLOBAL_Control
0x180072e79  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180072e80  mov     eax, [r14+38h]
0x180072e84  mov     edx, 53h ; 'S'
0x180072e89  add     rax, r14
0x180072e8c  mov     r9, rsi
0x180072e8f  mov     [rsp+70h+var_50], rax
0x180072e94  mov     rcx, [rcx+0D8h]
0x180072e9b  call    WPP_SF_qS
0x180072ea0  mov     ebx, [r14+2Ch]
0x180072ea4  lea     rcx, [rbp+Block]
0x180072ea8  mov     eax, [r14+3Ch]
0x180072eac  lea     r12, [rsi+0E0h]
0x180072eb3  mov     r13d, [r14+34h]
0x180072eb7  shr     eax, 1
0x180072eb9  shr     rbx, 1
0x180072ebc  mov     rdx, rbx
0x180072ebf  shr     r13d, 1
0x180072ec2  mov     dword ptr [rbp+arg_18], eax
0x180072ec5  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180072eca  mov     rdx, rax
0x180072ecd  mov     rcx, r12
0x180072ed0  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180072ed5  mov     rcx, [rbp+Block]; Block
0x180072ed9  mov     [rbp+Block], 0
0x180072ee1  test    rcx, rcx
0x180072ee4  jz      short loc_180072EEB
0x180072ee6  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072eeb  mov     rcx, [r12]; unsigned __int16 *
0x180072eef  test    rcx, rcx
0x180072ef2  jnz     short loc_180072F10
0x180072ef4  mov     eax, 8007000Eh
0x180072ef9  mov     ebx, eax
0x180072efb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072f02  jb      loc_1800731E6
0x180072f08  lea     edx, [rcx+54h]
0x180072f0b  jmp     loc_1800731C8
0x180072f10  mov     r8d, [r14+28h]
0x180072f14  mov     rdx, rbx; unsigned __int64
0x180072f17  add     r8, r14; unsigned __int16 *
0x180072f1a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072f1f  mov     ebx, eax
0x180072f21  test    eax, eax
0x180072f23  jns     short loc_180072F3C
0x180072f25  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072f2c  jb      loc_1800731E6
0x180072f32  mov     edx, 55h ; 'U'
0x180072f37  jmp     loc_1800731C8
0x180072f3c  mov     rcx, [r12]
0x180072f40  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180072f46  mov     rdx, r13
0x180072f49  lea     rcx, [rbp+Block]
0x180072f4d  mov     rbx, r13
0x180072f50  lea     r12, [rsi+0F0h]
0x180072f57  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180072f5c  mov     rdx, rax
0x180072f5f  mov     rcx, r12
0x180072f62  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180072f67  mov     rcx, [rbp+Block]; Block
0x180072f6b  xor     r13d, r13d
0x180072f6e  mov     [rbp+Block], r13
0x180072f72  test    rcx, rcx
0x180072f75  jz      short loc_180072F7C
0x180072f77  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180072f7c  mov     rcx, [r12]; unsigned __int16 *
0x180072f80  test    rcx, rcx
0x180072f83  jnz     short loc_180072FA1
0x180072f85  mov     eax, 8007000Eh
0x180072f8a  mov     ebx, eax
0x180072f8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072f93  jb      loc_1800731E6
0x180072f99  lea     edx, [rcx+56h]
0x180072f9c  jmp     loc_1800731C8
0x180072fa1  mov     r8d, [r14+30h]
0x180072fa5  mov     rdx, rbx; unsigned __int64
0x180072fa8  add     r8, r14; unsigned __int16 *
0x180072fab  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180072fb0  mov     ebx, eax
0x180072fb2  test    eax, eax
0x180072fb4  jns     short loc_180072FCD
0x180072fb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180072fbd  jb      loc_1800731E6
0x180072fc3  mov     edx, 57h ; 'W'
0x180072fc8  jmp     loc_1800731C8
0x180072fcd  mov     rcx, [r12]
0x180072fd1  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180072fd7  mov     ebx, dword ptr [rbp+arg_18]
0x180072fda  lea     rcx, [rbp+Block]
0x180072fde  mov     edx, ebx
0x180072fe0  lea     r12, [rsi+0E8h]
0x180072fe7  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180072fec  mov     rdx, rax
0x180072fef  mov     rcx, r12
0x180072ff2  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180072ff7  mov     rcx, [rbp+Block]; Block
0x180072ffb  mov     [rbp+Block], r13
0x180072fff  test    rcx, rcx
0x180073002  jz      short loc_180073009
0x180073004  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180073009  mov     rcx, [r12]; unsigned __int16 *
0x18007300d  test    rcx, rcx
0x180073010  jnz     short loc_18007302E
0x180073012  mov     eax, 8007000Eh
0x180073017  mov     ebx, eax
0x180073019  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073020  jb      loc_1800731E6
0x180073026  lea     edx, [rcx+58h]
0x180073029  jmp     loc_1800731C8
0x18007302e  mov     r8d, [r14+38h]
0x180073032  mov     rdx, rbx; unsigned __int64
0x180073035  add     r8, r14; unsigned __int16 *
0x180073038  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007303d  mov     ebx, eax
0x18007303f  test    eax, eax
0x180073041  jns     short loc_18007305A
0x180073043  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007304a  jb      loc_1800731E6
0x180073050  mov     edx, 59h ; 'Y'
0x180073055  jmp     loc_1800731C8
0x18007305a  mov     rcx, [r12]
0x18007305e  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180073064  mov     r12d, 20h ; ' '
0x18007306a  lea     rbx, [rsi+38h]
0x18007306e  mov     r9d, r12d; SourceSize
0x180073071  lea     r8, [r14+8]; Source
0x180073075  mov     edx, r12d; DestinationSize
0x180073078  mov     rcx, rbx; Destination
0x18007307b  call    memcpy_s_1
0x180073080  test    eax, eax
0x180073082  jz      short loc_1800730A2
0x180073084  mov     eax, 0C00D36BBh
0x180073089  mov     ebx, eax
0x18007308b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180073092  jb      loc_1800731E6
0x180073098  lea     edx, [r12+3Ah]
0x18007309d  jmp     loc_1800731C8
0x1800730a2  test    rbx, rbx
0x1800730a5  jz      loc_180073185
0x1800730ab  mov     edx, r13d
0x1800730ae  lea     r9, a0123456789abcd; "0123456789ABCDEF"
0x1800730b5  mov     r8, r13
0x1800730b8  movzx   eax, byte ptr [rbx+r8]
0x1800730bd  shr     rax, 4
0x1800730c1  mov     ecx, edx
0x1800730c3  inc     edx
0x1800730c5  movzx   eax, word ptr [r9+rax*2]
0x1800730ca  mov     [rsi+rcx*2+58h], ax
0x1800730cf  movzx   eax, byte ptr [rbx+r8]
0x1800730d4  inc     r8
0x1800730d7  and     eax, 0Fh
0x1800730da  movzx   eax, word ptr [r9+rax*2]
0x1800730df  mov     [rsi+rdx*2+58h], ax
0x1800730e4  inc     edx
0x1800730e6  cmp     r8, r12
0x1800730e9  jnz     short loc_1800730B8
0x1800730eb  mov     [rsi+rdx*2+58h], r13w
0x1800730f1  mov     rdx, r15
0x1800730f4  lea     rcx, [rbp+Block]
0x1800730f8  lea     rbx, [rsi+0F8h]
0x1800730ff  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180073104  mov     rdx, rax
0x180073107  mov     rcx, rbx
0x18007310a  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18007310f  lea     rcx, [rbp+Block]
0x180073113  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180073118  mov     rcx, [rbx]; Destination
0x18007311b  test    rcx, rcx
0x18007311e  jnz     short loc_18007313C
0x180073120  mov     eax, 8007000Eh
0x180073125  mov     ebx, eax
0x180073127  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007312e  jb      loc_1800731E6
0x180073134  lea     edx, [rcx+5Ch]
0x180073137  jmp     loc_1800731C8
  ... truncated ...
```
