# FSConfigurationKey::InternalInitialize(uchar const *,ulong)

- ea: `0x1800331c0`
- end: `0x1800337a2`
- name: `?InternalInitialize@FSConfigurationKey@@MEAAJPEBEK@Z`
- size: `1506`
- prototype: `int(FSConfigurationKey *__hidden this, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180004f34`
- `0x180005740`
- `0x180006a98`
- `0x180006cc0`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000d62c`
- `0x18000e25c`
- `0x18000e338`
- `0x18002fa3c`
- `0x18002fa70`
- `0x1800331c0`
- `0x180034c5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003349e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033526`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800335ae`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003349e`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033526`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800335ae`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitialize(void **this, const unsigned __int8 *a2, unsigned int a3)
{
  char v3; // al
  unsigned __int64 v4; // rbp
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
  __int64 v19; // rdx
  __int64 v20; // r10
  unsigned int v21; // eax
  unsigned __int64 v22; // rbx
  unsigned __int64 v23; // r12
  unsigned int v24; // r13d
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v26; // rdx
  char v27; // dl
  __int16 v28; // r8
  int v29; // r9d
  const struct std::nothrow_t *v30; // rax
  const struct std::nothrow_t *v31; // rdx
  char v32; // dl
  __int16 v33; // r8
  int v34; // r9d
  const struct std::nothrow_t *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  char v37; // dl
  __int16 v38; // r8
  int v39; // r9d
  char *v40; // rbx
  __int64 v41; // rdx
  __int64 i; // r8
  __int64 v43; // rdx
  char v44; // al
  const struct std::nothrow_t *v45; // rax
  const struct std::nothrow_t *v46; // rdx
  void *v47; // rcx
  __int64 v48; // rdx
  wchar_t v50; // [rsp+20h] [rbp-78h]
  wchar_t v51; // [rsp+20h] [rbp-78h]
  wchar_t v52; // [rsp+20h] [rbp-78h]
  long double v53; // [rsp+28h] [rbp-70h]
  long double v54; // [rsp+28h] [rbp-70h]
  long double v55; // [rsp+28h] [rbp-70h]
  void **v56; // [rsp+50h] [rbp-48h] BYREF
  _BYTE v57[24]; // [rsp+58h] [rbp-40h] BYREF
  void *v58; // [rsp+A8h] [rbp+10h] BYREF

  v3 = 0;
  v4 = a3;
  LODWORD(v58) = 0;
  if ( !a2 || a3 < 0x40 || a3 < *((_DWORD *)a2 + 1) )
  {
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 74;
    goto LABEL_70;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v7 = BlobTrace::BlobTrace((BlobTrace *)&v56, (void *)(a2 + 8), a3);
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
    v56 = &SensorGroupBlobHeaderTrace::`vftable';
    FSString::~FSString((FSString *)v57, (const struct std::nothrow_t *)a2);
  }
  v11 = *((_DWORD *)a2 + 11);
  v12 = v11 + 64;
  if ( v11 >= 0xFFFFFFC0 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( !g_wppLevels )
      goto LABEL_71;
    v15 = 76;
    goto LABEL_11;
  }
  v16 = *((_DWORD *)a2 + 13);
  v17 = v16 + v12;
  if ( v16 + v12 < v12 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( g_wppLevels )
    {
      v15 = 77;
LABEL_11:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v13);
      goto LABEL_71;
    }
    goto LABEL_71;
  }
  v18 = *((_DWORD *)a2 + 15);
  if ( v18 + v17 < v17 )
  {
    v13 = -2147024362;
    v14 = -2147024362;
    if ( g_wppLevels )
    {
      v15 = 78;
      goto LABEL_11;
    }
LABEL_71:
    if ( byte_18005E5A5 )
    {
      v48 = 94;
      goto LABEL_73;
    }
    return v14;
  }
  if ( (unsigned int)v4 < v18 + v17 )
  {
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 79;
LABEL_70:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v19,
      &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
      this,
      -2147024809);
    goto LABEL_71;
  }
  v20 = *((unsigned int *)a2 + 10);
  if ( (unsigned int)v20 >= *((_DWORD *)a2 + 12)
    || (v21 = *((_DWORD *)a2 + 14), *((_DWORD *)a2 + 12) >= v21)
    || v21 >= (unsigned int)v4
    || a2[(unsigned int)(v4 - 1)]
    || a2[(unsigned int)(v4 - 2)]
    || (((unsigned __int8)v11 | (unsigned __int8)(v16 | v18)) & 1) != 0 )
  {
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_71;
    v19 = 80;
    goto LABEL_70;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      81,
      (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
      (_DWORD)this,
      (__int64)&a2[v20]);
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        82,
        (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        (_DWORD)this,
        (__int64)&a2[*((unsigned int *)a2 + 12)]);
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          83,
          (unsigned int)&WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
          (_DWORD)this,
          (__int64)&a2[*((unsigned int *)a2 + 14)]);
    }
  }
  v22 = (unsigned __int64)*((unsigned int *)a2 + 11) >> 1;
  v23 = *((_DWORD *)a2 + 13) >> 1;
  v24 = *((_DWORD *)a2 + 15) >> 1;
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, v22);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 28, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v58, v26);
  if ( !this[28] )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( g_wppLevels )
    {
      v15 = 84;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  v13 = StringCchCopyW((unsigned __int16 *)this[28], v22, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 10)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 85;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  o((wchar_t)this[28], v27, v28, v29, v50, v53);
  v30 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, v23);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 30, v30);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v58, v31);
  if ( !this[30] )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( g_wppLevels )
    {
      v15 = 86;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  v13 = StringCchCopyW((unsigned __int16 *)this[30], v23, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 12)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 87;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  o((wchar_t)this[30], v32, v33, v34, v51, v54);
  v35 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, v24);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 29, v35);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v58, v36);
  if ( !this[29] )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( g_wppLevels )
    {
      v15 = 88;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  v13 = StringCchCopyW((unsigned __int16 *)this[29], v24, (const unsigned __int16 *)&a2[*((unsigned int *)a2 + 14)]);
  v14 = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
    {
      v15 = 89;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  o((wchar_t)this[29], v37, v38, v39, v52, v55);
  v40 = (char *)(this + 7);
  if ( memcpy_s(this + 7, 0x20u, a2 + 8, 0x20u) )
  {
    v13 = -1072875845;
    v14 = -1072875845;
    if ( g_wppLevels )
    {
      v15 = 90;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  if ( this == (void **)-56LL )
  {
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        91,
        &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        -56,
        -2147024809);
    v14 = -2147024809;
    goto LABEL_71;
  }
  v41 = 0;
  for ( i = 0; i != 32; ++i )
  {
    *((_WORD *)this + v41 + 44) = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v40[i] >> 4];
    v43 = (unsigned int)(v41 + 1);
    v44 = v40[i];
    *((_WORD *)this + v43 + 44) = a0123456789abcd_0[v44 & 0xF];
    v41 = (unsigned int)(v43 + 1);
  }
  *((_WORD *)this + v41 + 44) = 0;
  v45 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned char [0]>(&v58, v4);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(this + 31, v45);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v58, v46);
  v47 = this[31];
  if ( !v47 )
  {
    v13 = -2147024882;
    v14 = -2147024882;
    if ( g_wppLevels )
    {
      v15 = 92;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  if ( memcpy_s(v47, v4, a2, v4) )
  {
    v13 = -1072875845;
    v14 = -1072875845;
    if ( g_wppLevels )
    {
      v15 = 93;
      goto LABEL_11;
    }
    goto LABEL_71;
  }
  v14 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v48 = 95;
LABEL_73:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v48, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v14);
  }
  return v14;
}

```

## disassembly

```asm
0x1800331c0  mov     [rsp+arg_0], rbx
0x1800331c5  mov     [rsp+arg_10], rbp
0x1800331ca  push    rsi
0x1800331cb  push    r12
0x1800331cd  push    r13
0x1800331cf  push    r14
0x1800331d1  push    r15
0x1800331d3  sub     rsp, 70h
0x1800331d7  xor     eax, eax
0x1800331d9  mov     ebp, r8d
0x1800331dc  mov     dword ptr [rsp+98h+arg_8], eax
0x1800331e3  mov     r14, rdx
0x1800331e6  mov     rsi, rcx
0x1800331e9  test    rdx, rdx
0x1800331ec  jz      loc_180033724
0x1800331f2  cmp     ebp, 40h ; '@'
0x1800331f5  jb      loc_180033724
0x1800331fb  cmp     ebp, [rdx+4]
0x1800331fe  jb      loc_180033724
0x180033204  mov     bl, 8
0x180033206  cmp     cs:byte_18005E5A5, bl
0x18003320c  jb      short loc_18003325D
0x18003320e  add     rdx, 8; void *
0x180033212  lea     rcx, [rsp+98h+var_48]; this
0x180033217  call    ??0BlobTrace@@QEAA@PEAXK@Z; BlobTrace::BlobTrace(void *,ulong)
0x18003321c  lea     rcx, [rax+8]; this
0x180033220  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x180033225  mov     rcx, cs:WPP_GLOBAL_Control
0x18003322c  mov     r9, rsi
0x18003322f  mov     [rsp+98h+var_58], rax
0x180033234  mov     eax, [r14+4]
0x180033238  mov     [rsp+98h+var_60], eax
0x18003323c  mov     eax, [r14]
0x18003323f  mov     rcx, [rcx+0D8h]
0x180033246  mov     [rsp+98h+var_68], eax
0x18003324a  mov     dword ptr [rsp+98h+var_70], ebp
0x18003324e  mov     [rsp+98h+var_78], r14
0x180033253  call    WPP_SF_qqddds
0x180033258  mov     eax, 1
0x18003325d  test    al, 1
0x18003325f  jz      short loc_180033277
0x180033261  lea     rax, ??_7SensorGroupBlobHeaderTrace@@6B@; const SensorGroupBlobHeaderTrace::`vftable'
0x180033268  lea     rcx, [rsp+98h+var_40]; this
0x18003326d  mov     [rsp+98h+var_48], rax
0x180033272  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x180033277  mov     r8d, [r14+2Ch]
0x18003327b  lea     eax, [r8+40h]
0x18003327f  cmp     eax, 40h ; '@'
0x180033282  jnb     short loc_1800332A6
0x180033284  mov     eax, 80070216h
0x180033289  mov     ebx, eax
0x18003328b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033292  jb      loc_180033757
0x180033298  mov     edx, 4Ch ; 'L'
0x18003329d  mov     dword ptr [rsp+98h+var_78], eax
0x1800332a1  jmp     loc_18003373D
0x1800332a6  mov     r9d, [r14+34h]
0x1800332aa  lea     ecx, [r9+rax]
0x1800332ae  cmp     ecx, eax
0x1800332b0  jnb     short loc_1800332CD
0x1800332b2  mov     eax, 80070216h
0x1800332b7  mov     ebx, eax
0x1800332b9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800332c0  jb      loc_180033757
0x1800332c6  mov     edx, 4Dh ; 'M'
0x1800332cb  jmp     short loc_18003329D
0x1800332cd  mov     edx, [r14+3Ch]
0x1800332d1  lea     eax, [rdx+rcx]
0x1800332d4  cmp     eax, ecx
0x1800332d6  jnb     short loc_1800332F3
0x1800332d8  mov     eax, 80070216h
0x1800332dd  mov     ebx, eax
0x1800332df  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800332e6  jb      loc_180033757
0x1800332ec  mov     edx, 4Eh ; 'N'
0x1800332f1  jmp     short loc_18003329D
0x1800332f3  cmp     ebp, eax
0x1800332f5  jnb     short loc_180033315
0x1800332f7  mov     ebp, 80070057h
0x1800332fc  mov     ebx, ebp
0x1800332fe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033305  jb      loc_180033757
0x18003330b  mov     edx, 4Fh ; 'O'
0x180033310  jmp     loc_180033739
0x180033315  mov     r10d, [r14+28h]
0x180033319  cmp     r10d, [r14+30h]
0x18003331d  jnb     loc_18003370D
0x180033323  mov     eax, [r14+38h]
0x180033327  cmp     [r14+30h], eax
0x18003332b  jnb     loc_18003370D
0x180033331  cmp     eax, ebp
0x180033333  jnb     loc_18003370D
0x180033339  lea     eax, [rbp-1]
0x18003333c  cmp     byte ptr [rax+r14], 0
0x180033341  jnz     loc_18003370D
0x180033347  lea     eax, [rbp-2]
0x18003334a  cmp     byte ptr [rax+r14], 0
0x18003334f  jnz     loc_18003370D
0x180033355  or      edx, r9d
0x180033358  or      edx, r8d
0x18003335b  test    dl, 1
0x18003335e  jnz     loc_18003370D
0x180033364  cmp     cs:byte_18005E5A5, bl
0x18003336a  jb      loc_180033407
0x180033370  mov     rcx, cs:WPP_GLOBAL_Control
0x180033377  lea     rax, [r14+r10]
0x18003337b  mov     edx, 51h ; 'Q'
0x180033380  mov     [rsp+98h+var_78], rax
0x180033385  mov     r9, rsi
0x180033388  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x18003338f  mov     rcx, [rcx+0D8h]
0x180033396  call    WPP_SF_qS
0x18003339b  cmp     cs:byte_18005E5A5, bl
0x1800333a1  jb      short loc_180033407
0x1800333a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333aa  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x1800333b1  mov     eax, [r14+30h]
0x1800333b5  mov     edx, 52h ; 'R'
0x1800333ba  add     rax, r14
0x1800333bd  mov     r9, rsi
0x1800333c0  mov     [rsp+98h+var_78], rax
0x1800333c5  mov     rcx, [rcx+0D8h]
0x1800333cc  call    WPP_SF_qS
0x1800333d1  cmp     cs:byte_18005E5A5, bl
0x1800333d7  jb      short loc_180033407
0x1800333d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800333e0  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x1800333e7  mov     eax, [r14+38h]
0x1800333eb  mov     edx, 53h ; 'S'
0x1800333f0  add     rax, r14
0x1800333f3  mov     r9, rsi
0x1800333f6  mov     [rsp+98h+var_78], rax
0x1800333fb  mov     rcx, [rcx+0D8h]
0x180033402  call    WPP_SF_qS
0x180033407  mov     ebx, [r14+2Ch]
0x18003340b  lea     rcx, [rsp+98h+arg_8]
0x180033413  mov     r12d, [r14+34h]
0x180033417  lea     r15, [rsi+0E0h]
0x18003341e  mov     r13d, [r14+3Ch]
0x180033422  shr     rbx, 1
0x180033425  mov     rdx, rbx
0x180033428  shr     r12d, 1
0x18003342b  shr     r13d, 1
0x18003342e  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033433  mov     rdx, rax
0x180033436  mov     rcx, r15
0x180033439  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003343e  lea     rcx, [rsp+98h+arg_8]
0x180033446  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003344b  mov     rcx, [r15]; unsigned __int16 *
0x18003344e  test    rcx, rcx
0x180033451  jnz     short loc_18003346F
0x180033453  mov     eax, 8007000Eh
0x180033458  mov     ebx, eax
0x18003345a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033461  jb      loc_180033757
0x180033467  lea     edx, [rcx+54h]
0x18003346a  jmp     loc_18003329D
0x18003346f  mov     r8d, [r14+28h]
0x180033473  mov     rdx, rbx; unsigned __int64
0x180033476  add     r8, r14; unsigned __int16 *
0x180033479  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003347e  mov     ebx, eax
0x180033480  test    eax, eax
0x180033482  jns     short loc_18003349B
0x180033484  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003348b  jb      loc_180033757
0x180033491  mov     edx, 55h ; 'U'
0x180033496  jmp     loc_18003329D
0x18003349b  mov     rcx, [r15]
0x18003349e  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800334a4  mov     rdx, r12
0x1800334a7  lea     rcx, [rsp+98h+arg_8]
0x1800334af  lea     r15, [rsi+0F0h]
0x1800334b6  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800334bb  mov     rdx, rax
0x1800334be  mov     rcx, r15
0x1800334c1  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800334c6  lea     rcx, [rsp+98h+arg_8]
0x1800334ce  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x1800334d3  mov     rcx, [r15]; unsigned __int16 *
0x1800334d6  test    rcx, rcx
0x1800334d9  jnz     short loc_1800334F7
0x1800334db  mov     eax, 8007000Eh
0x1800334e0  mov     ebx, eax
0x1800334e2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800334e9  jb      loc_180033757
0x1800334ef  lea     edx, [rcx+56h]
0x1800334f2  jmp     loc_18003329D
0x1800334f7  mov     r8d, [r14+30h]
0x1800334fb  mov     rdx, r12; unsigned __int64
0x1800334fe  add     r8, r14; unsigned __int16 *
0x180033501  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033506  mov     ebx, eax
0x180033508  test    eax, eax
0x18003350a  jns     short loc_180033523
0x18003350c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033513  jb      loc_180033757
0x180033519  mov     edx, 57h ; 'W'
0x18003351e  jmp     loc_18003329D
0x180033523  mov     rcx, [r15]
0x180033526  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003352c  mov     rdx, r13
0x18003352f  lea     rcx, [rsp+98h+arg_8]
0x180033537  lea     r15, [rsi+0E8h]
0x18003353e  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033543  mov     rdx, rax
0x180033546  mov     rcx, r15
0x180033549  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003354e  lea     rcx, [rsp+98h+arg_8]
0x180033556  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003355b  mov     rcx, [r15]; unsigned __int16 *
0x18003355e  test    rcx, rcx
0x180033561  jnz     short loc_18003357F
0x180033563  mov     eax, 8007000Eh
0x180033568  mov     ebx, eax
0x18003356a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033571  jb      loc_180033757
0x180033577  lea     edx, [rcx+58h]
0x18003357a  jmp     loc_18003329D
0x18003357f  mov     r8d, [r14+38h]
0x180033583  mov     rdx, r13; unsigned __int64
0x180033586  add     r8, r14; unsigned __int16 *
0x180033589  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003358e  mov     ebx, eax
0x180033590  test    eax, eax
0x180033592  jns     short loc_1800335AB
0x180033594  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003359b  jb      loc_180033757
0x1800335a1  mov     edx, 59h ; 'Y'
0x1800335a6  jmp     loc_18003329D
0x1800335ab  mov     rcx, [r15]
0x1800335ae  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800335b4  mov     r15d, 20h ; ' '
0x1800335ba  lea     rbx, [rsi+38h]
0x1800335be  mov     r9d, r15d; SourceSize
0x1800335c1  lea     r8, [r14+8]; Source
0x1800335c5  mov     edx, r15d; DestinationSize
0x1800335c8  mov     rcx, rbx; Destination
0x1800335cb  call    memcpy_s
0x1800335d0  test    eax, eax
0x1800335d2  jz      short loc_1800335F1
0x1800335d4  mov     eax, 0C00D36BBh
0x1800335d9  mov     ebx, eax
0x1800335db  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800335e2  jb      loc_180033757
0x1800335e8  lea     edx, [r15+3Ah]
0x1800335ec  jmp     loc_18003329D
0x1800335f1  test    rbx, rbx
0x1800335f4  jz      loc_1800336D8
0x1800335fa  xor     edx, edx
0x1800335fc  lea     r9, a0123456789abcd_0; "0123456789ABCDEF"
0x180033603  xor     r8d, r8d
0x180033606  movzx   eax, byte ptr [r8+rbx]
0x18003360b  shr     rax, 4
0x18003360f  movzx   eax, word ptr [r9+rax*2]
0x180033614  mov     [rsi+rdx*2+58h], ax
0x180033619  inc     edx
0x18003361b  movzx   eax, byte ptr [r8+rbx]
0x180033620  inc     r8
0x180033623  and     eax, 0Fh
0x180033626  movzx   eax, word ptr [r9+rax*2]
0x18003362b  mov     [rsi+rdx*2+58h], ax
0x180033630  inc     edx
0x180033632  cmp     r8, r15
0x180033635  jnz     short loc_180033606
0x180033637  xor     eax, eax
0x180033639  mov     [rsi+rdx*2+58h], ax
0x18003363e  mov     rdx, rbp
0x180033641  lea     rcx, [rsp+98h+arg_8]
0x180033649  lea     rbx, [rsi+0F8h]
0x180033650  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180033655  mov     rdx, rax
0x180033658  mov     rcx, rbx
0x18003365b  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033660  lea     rcx, [rsp+98h+arg_8]
0x180033668  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003366d  mov     rcx, [rbx]; Destination
0x180033670  test    rcx, rcx
0x180033673  jnz     short loc_180033691
0x180033675  mov     eax, 8007000Eh
0x18003367a  mov     ebx, eax
0x18003367c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033683  jb      loc_180033757
0x180033689  lea     edx, [rcx+5Ch]
0x18003368c  jmp     loc_18003329D
0x180033691  mov     r9, rbp; SourceSize
0x180033694  mov     r8, r14; Source
0x180033697  mov     rdx, rbp; DestinationSize
0x18003369a  call    memcpy_s
0x18003369f  test    eax, eax
0x1800336a1  jz      short loc_1800336C1
0x1800336a3  mov     eax, 0C00D36BBh
0x1800336a8  mov     ebx, eax
0x1800336aa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800336b1  jb      loc_180033757
0x1800336b7  mov     edx, 5Dh ; ']'
0x1800336bc  jmp     loc_18003329D
0x1800336c1  xor     ebx, ebx
0x1800336c3  cmp     cs:byte_18005E5A5, 8
  ... truncated ...
```
