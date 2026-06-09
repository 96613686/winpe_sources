# FSConfigurationKey::InternalInitialize(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong)

- ea: `0x18003aab0`
- end: `0x18003b0e2`
- name: `?InternalInitialize@FSConfigurationKey@@MEAAJPEBGK0K0K@Z`
- size: `1586`
- prototype: `__int64 __fastcall(FSConfigurationKey *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, registry_config`

## callees

- `0x1800031fc`
- `0x180005fa0`
- `0x18000aa08`
- `0x180015e80`
- `0x180016328`
- `0x18001635c`
- `0x18002943c`
- `0x18003aab0`
- `0x18003c8c0`
- `0x18003d064`
- `0x180044b28`
- `0x180045900`
- `0x180073930`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003ab60`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003abe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003ac73`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003ab60`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003abe9`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003ac73`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitialize(
        FSConfigurationKey *this,
        unsigned __int16 *a2,
        unsigned int a3,
        unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  unsigned __int64 v8; // rbx
  void **v10; // r13
  PUCHAR v11; // rsi
  void **unique; // rax
  void *v14; // rcx
  int v15; // eax
  unsigned int v16; // ebx
  __int64 v17; // rdx
  char v18; // dl
  __int16 v19; // r8
  int v20; // r9d
  unsigned __int64 v21; // rbx
  unsigned __int16 **v22; // r12
  void **v23; // rax
  void *v24; // rcx
  char v25; // dl
  __int16 v26; // r8
  int v27; // r9d
  unsigned __int64 v28; // r14
  unsigned __int16 **v29; // r15
  void **v30; // rax
  void *v31; // rcx
  char v32; // dl
  __int16 v33; // r8
  int v34; // r9d
  unsigned __int64 v35; // rax
  UCHAR *v36; // rbx
  __int64 v37; // r14
  void **v38; // rax
  void *v39; // rcx
  const unsigned __int16 *v40; // r8
  unsigned __int64 v41; // rax
  UCHAR *v42; // rbx
  void **v43; // rax
  void *v44; // rcx
  const unsigned __int16 *v45; // r8
  char *v46; // r15
  __int64 v47; // r8
  __int64 i; // r9
  __int64 v49; // r8
  char v50; // al
  __int64 v51; // rdx
  wchar_t v53; // [rsp+20h] [rbp-30h]
  wchar_t v54; // [rsp+20h] [rbp-30h]
  wchar_t v55; // [rsp+20h] [rbp-30h]
  unsigned int *v56; // [rsp+28h] [rbp-28h]
  unsigned int *v57; // [rsp+28h] [rbp-28h]
  unsigned int *v58; // [rsp+28h] [rbp-28h]
  unsigned int v59; // [rsp+28h] [rbp-28h]
  unsigned int v60; // [rsp+28h] [rbp-28h]
  unsigned int v61; // [rsp+28h] [rbp-28h]
  unsigned int v62; // [rsp+28h] [rbp-28h]
  void *Block[2]; // [rsp+40h] [rbp-10h] BYREF
  PUCHAR pbInput; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v65; // [rsp+A0h] [rbp+50h] BYREF

  v65 = a3;
  v8 = a3;
  v10 = (void **)((char *)this + 224);
  v11 = 0;
  pbInput = 0;
  unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, a3);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(v10, unique);
  v14 = Block[0];
  Block[0] = 0;
  if ( v14 )
    operator delete(v14);
  if ( *v10 )
  {
    v15 = StringCchCopyW((unsigned __int16 *)*v10, v8, a2);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 33;
      goto LABEL_6;
    }
    o((wchar_t)*v10, v18, v19, v20, v53, *(long double *)&v56);
    v21 = a5;
    v22 = (unsigned __int16 **)((char *)this + 232);
    v23 = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, a5);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 29, v23);
    v24 = Block[0];
    Block[0] = 0;
    if ( v24 )
      operator delete(v24);
    if ( !*v22 )
    {
      v15 = -2147024882;
      v16 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 34;
      goto LABEL_6;
    }
    v15 = StringCchCopyW(*v22, v21, a4);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 35;
      goto LABEL_6;
    }
    o((wchar_t)*v22, v25, v26, v27, v54, *(long double *)&v57);
    v28 = a7;
    v29 = (unsigned __int16 **)((char *)this + 240);
    v30 = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, a7);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 30, v30);
    v31 = Block[0];
    Block[0] = 0;
    if ( v31 )
      operator delete(v31);
    if ( !*v29 )
    {
      v15 = -2147024882;
      v16 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 36;
      goto LABEL_6;
    }
    v15 = StringCchCopyW(*v29, v28, a6);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 37;
      goto LABEL_6;
    }
    o((wchar_t)*v29, v32, v33, v34, v55, *(long double *)&v58);
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)*v29, (__int64)*v22, (__int64)*v10);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
    {
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 39, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this);
      v35 = (unsigned int)v28 + a5;
      v36 = (UCHAR *)v35;
      if ( !((_DWORD)v28 + a5) )
      {
        v15 = -2147024362;
        v16 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 40;
        goto LABEL_6;
      }
      v37 = 2 * v35;
      if ( !(2 * v35) )
      {
        v15 = -2147024362;
        v16 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 41;
        goto LABEL_6;
      }
      v38 = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, v35);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&pbInput, v38);
      v39 = Block[0];
      Block[0] = 0;
      if ( v39 )
        operator delete(v39);
      v11 = pbInput;
      if ( !pbInput )
      {
        v15 = -2147024882;
        v16 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = (unsigned int)((_DWORD)pbInput + 42);
        goto LABEL_6;
      }
      memset_0(pbInput, 0, v37);
      v40 = *v22;
      Block[0] = v11;
      pbInput = v36;
      v15 = StringCchCopyExW(
              (unsigned __int16 *)v11,
              (unsigned __int64)v36,
              v40,
              (unsigned __int16 **)Block,
              (unsigned __int64 *)&pbInput,
              v59);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 43;
        goto LABEL_6;
      }
      v15 = StringCchCopyExW(
              (unsigned __int16 *)Block[0],
              (unsigned __int64)pbInput,
              *v29,
              (unsigned __int16 **)Block,
              (unsigned __int64 *)&pbInput,
              v60);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 44;
        goto LABEL_6;
      }
    }
    else
    {
      v41 = (unsigned int)v28 + v65 + a5;
      v42 = (UCHAR *)v41;
      if ( !((_DWORD)v28 + v65 + a5) )
      {
        v15 = -2147024362;
        v16 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 45;
        goto LABEL_6;
      }
      v37 = 2 * v41;
      if ( !(2 * v41) )
      {
        v15 = -2147024362;
        v16 = -2147024362;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 46;
        goto LABEL_6;
      }
      v43 = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, v41);
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&pbInput, v43);
      v44 = Block[0];
      Block[0] = 0;
      if ( v44 )
        operator delete(v44);
      v11 = pbInput;
      if ( !pbInput )
      {
        v15 = -2147024882;
        v16 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = (unsigned int)((_DWORD)pbInput + 47);
        goto LABEL_6;
      }
      memset_0(pbInput, 0, v37);
      v45 = (const unsigned __int16 *)*v10;
      Block[0] = v11;
      pbInput = v42;
      v15 = StringCchCopyExW(
              (unsigned __int16 *)v11,
              (unsigned __int64)v42,
              v45,
              (unsigned __int16 **)Block,
              (unsigned __int64 *)&pbInput,
              v59);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 48;
        goto LABEL_6;
      }
      v15 = StringCchCopyExW(
              (unsigned __int16 *)Block[0],
              (unsigned __int64)pbInput,
              *v22,
              (unsigned __int16 **)Block,
              (unsigned __int64 *)&pbInput,
              v61);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 49;
        goto LABEL_6;
      }
      v15 = StringCchCopyExW(
              (unsigned __int16 *)Block[0],
              (unsigned __int64)pbInput,
              *v29,
              (unsigned __int16 **)Block,
              (unsigned __int64 *)&pbInput,
              v62);
      v16 = v15;
      if ( v15 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_82;
        v17 = 50;
        goto LABEL_6;
      }
    }
    v46 = (char *)this + 56;
    v15 = FSCreateHash(0, v11, v37, (PUCHAR)this + 56, 0x20u, &v65);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_82;
      v17 = 51;
      goto LABEL_6;
    }
    if ( this == (FSConfigurationKey *)-56LL )
    {
      v16 = -2147024809;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          52,
          &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
          -56,
          -2147024809);
      goto LABEL_82;
    }
    v47 = 0;
    for ( i = 0; i != 32; ++i )
    {
      *((_WORD *)this + v47 + 44) = a0123456789abcd[(unsigned __int64)(unsigned __int8)v46[i] >> 4];
      v49 = (unsigned int)(v47 + 1);
      v50 = v46[i];
      *((_WORD *)this + v49 + 44) = a0123456789abcd[v50 & 0xF];
      v47 = (unsigned int)(v49 + 1);
    }
    *((_WORD *)this + v47 + 44) = 0;
    v16 = 0;
    if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl)
      || (v15 = FSConfigurationKey::InternalSerialize(this), v16 = v15, v15 >= 0) )
    {
      if ( (unsigned __int8)byte_18008D62D < 8u )
        goto LABEL_85;
      v51 = 55;
      goto LABEL_84;
    }
    if ( g_wppLevels )
    {
      v17 = 53;
      goto LABEL_6;
    }
  }
  else
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = 32;
LABEL_6:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v15);
    }
  }
LABEL_82:
  if ( !byte_18008D62D )
    goto LABEL_85;
  v51 = 54;
LABEL_84:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v51, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v16);
LABEL_85:
  if ( v11 )
    operator delete(v11);
  return v16;
}

```

## disassembly

```asm
0x18003aab0  mov     [rsp-38h+arg_8], rbx
0x18003aab5  mov     [rsp-38h+arg_10], r8d
0x18003aaba  push    rbp
0x18003aabb  push    rsi
0x18003aabc  push    rdi
0x18003aabd  push    r12
0x18003aabf  push    r13
0x18003aac1  push    r14
0x18003aac3  push    r15
0x18003aac5  mov     rbp, rsp
0x18003aac8  sub     rsp, 50h
0x18003aacc  mov     r14, rdx
0x18003aacf  mov     ebx, r8d
0x18003aad2  mov     rdi, rcx
0x18003aad5  mov     edx, r8d
0x18003aad8  lea     r13, [rcx+0E0h]
0x18003aadf  xor     esi, esi
0x18003aae1  lea     rcx, [rbp+Block]
0x18003aae5  mov     [rbp+pbInput], rsi
0x18003aae9  mov     r15, r9
0x18003aaec  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003aaf1  mov     rdx, rax
0x18003aaf4  mov     rcx, r13
0x18003aaf7  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003aafc  mov     rcx, [rbp+Block]; Block
0x18003ab00  mov     [rbp+Block], rsi
0x18003ab04  test    rcx, rcx
0x18003ab07  jz      short loc_18003AB0E
0x18003ab09  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ab0e  mov     rcx, [r13+0]; unsigned __int16 *
0x18003ab12  test    rcx, rcx
0x18003ab15  jnz     short loc_18003AB37
0x18003ab17  mov     eax, 8007000Eh
0x18003ab1c  mov     ebx, eax
0x18003ab1e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ab25  jb      loc_18003B08C
0x18003ab2b  lea     edx, [rcx+20h]
0x18003ab2e  mov     dword ptr [rsp+50h+var_30], eax
0x18003ab32  jmp     loc_18003B072
0x18003ab37  mov     r8, r14; unsigned __int16 *
0x18003ab3a  mov     rdx, rbx; unsigned __int64
0x18003ab3d  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ab42  mov     ebx, eax
0x18003ab44  test    eax, eax
0x18003ab46  jns     short loc_18003AB5C
0x18003ab48  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ab4f  jb      loc_18003B08C
0x18003ab55  mov     edx, 21h ; '!'
0x18003ab5a  jmp     short loc_18003AB2E
0x18003ab5c  mov     rcx, [r13+0]
0x18003ab60  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003ab66  mov     ebx, [rbp+arg_20]
0x18003ab69  lea     rcx, [rbp+Block]
0x18003ab6d  mov     edx, ebx
0x18003ab6f  lea     r12, [rdi+0E8h]
0x18003ab76  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003ab7b  mov     rdx, rax
0x18003ab7e  mov     rcx, r12
0x18003ab81  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003ab86  mov     rcx, [rbp+Block]; Block
0x18003ab8a  mov     [rbp+Block], rsi
0x18003ab8e  test    rcx, rcx
0x18003ab91  jz      short loc_18003AB98
0x18003ab93  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ab98  mov     rcx, [r12]; unsigned __int16 *
0x18003ab9c  test    rcx, rcx
0x18003ab9f  jnz     short loc_18003ABBD
0x18003aba1  mov     eax, 8007000Eh
0x18003aba6  mov     ebx, eax
0x18003aba8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003abaf  jb      loc_18003B08C
0x18003abb5  lea     edx, [rcx+22h]
0x18003abb8  jmp     loc_18003AB2E
0x18003abbd  mov     r8, r15; unsigned __int16 *
0x18003abc0  mov     rdx, rbx; unsigned __int64
0x18003abc3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003abc8  mov     ebx, eax
0x18003abca  test    eax, eax
0x18003abcc  jns     short loc_18003ABE5
0x18003abce  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003abd5  jb      loc_18003B08C
0x18003abdb  mov     edx, 23h ; '#'
0x18003abe0  jmp     loc_18003AB2E
0x18003abe5  mov     rcx, [r12]
0x18003abe9  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003abef  mov     r14d, [rbp+arg_30]
0x18003abf3  lea     rcx, [rbp+Block]
0x18003abf7  mov     edx, r14d
0x18003abfa  lea     r15, [rdi+0F0h]
0x18003ac01  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003ac06  mov     rdx, rax
0x18003ac09  mov     rcx, r15
0x18003ac0c  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003ac11  mov     rcx, [rbp+Block]; Block
0x18003ac15  mov     [rbp+Block], rsi
0x18003ac19  test    rcx, rcx
0x18003ac1c  jz      short loc_18003AC23
0x18003ac1e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ac23  mov     rcx, [r15]; unsigned __int16 *
0x18003ac26  test    rcx, rcx
0x18003ac29  jnz     short loc_18003AC47
0x18003ac2b  mov     eax, 8007000Eh
0x18003ac30  mov     ebx, eax
0x18003ac32  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ac39  jb      loc_18003B08C
0x18003ac3f  lea     edx, [rcx+24h]
0x18003ac42  jmp     loc_18003AB2E
0x18003ac47  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x18003ac4b  mov     rdx, r14; unsigned __int64
0x18003ac4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003ac53  mov     ebx, eax
0x18003ac55  test    eax, eax
0x18003ac57  jns     short loc_18003AC70
0x18003ac59  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ac60  jb      loc_18003B08C
0x18003ac66  mov     edx, 25h ; '%'
0x18003ac6b  jmp     loc_18003AB2E
0x18003ac70  mov     rcx, [r15]
0x18003ac73  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003ac79  cmp     cs:byte_18008D62D, 8
0x18003ac80  jb      short loc_18003ACB7
0x18003ac82  mov     rax, [r13+0]
0x18003ac86  mov     edx, 26h ; '&'
0x18003ac8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac92  mov     r9, rdi
0x18003ac95  mov     [rsp+50h+var_20], rax; __int64
0x18003ac9a  mov     rax, [r12]
0x18003ac9e  mov     [rsp+50h+var_28], rax; unsigned int
0x18003aca3  mov     rax, [r15]
0x18003aca6  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003acad  mov     [rsp+50h+var_30], rax; __int64
0x18003acb2  call    WPP_SF_qSSS
0x18003acb7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x18003acbe  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x18003acc3  test    al, al
0x18003acc5  jz      loc_18003AE1F
0x18003accb  cmp     cs:byte_18008D62D, 8
0x18003acd2  jb      short loc_18003ACF6
0x18003acd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acdb  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x18003ace2  mov     edx, 27h ; '''
0x18003ace7  mov     r9, rdi
0x18003acea  mov     rcx, [rcx+0D8h]
0x18003acf1  call    WPP_SF_q
0x18003acf6  mov     eax, [rbp+arg_20]
0x18003acf9  add     eax, r14d
0x18003acfc  mov     ebx, eax
0x18003acfe  jnz     short loc_18003AD1E
0x18003ad00  mov     eax, 80070216h
0x18003ad05  mov     ebx, eax
0x18003ad07  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad0e  jb      loc_18003B08C
0x18003ad14  mov     edx, 28h ; '('
0x18003ad19  jmp     loc_18003AB2E
0x18003ad1e  lea     r14, [rax+rax]
0x18003ad22  test    r14, r14
0x18003ad25  jnz     short loc_18003AD44
0x18003ad27  mov     eax, 80070216h
0x18003ad2c  mov     ebx, eax
0x18003ad2e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad35  jb      loc_18003B08C
0x18003ad3b  lea     edx, [r14+29h]
0x18003ad3f  jmp     loc_18003AB2E
0x18003ad44  mov     rdx, rbx
0x18003ad47  lea     rcx, [rbp+Block]
0x18003ad4b  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003ad50  mov     rdx, rax
0x18003ad53  lea     rcx, [rbp+pbInput]
0x18003ad57  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003ad5c  mov     rcx, [rbp+Block]; Block
0x18003ad60  mov     [rbp+Block], rsi
0x18003ad64  test    rcx, rcx
0x18003ad67  jz      short loc_18003AD6E
0x18003ad69  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ad6e  mov     rsi, [rbp+pbInput]
0x18003ad72  test    rsi, rsi
0x18003ad75  jnz     short loc_18003AD93
0x18003ad77  mov     eax, 8007000Eh
0x18003ad7c  mov     ebx, eax
0x18003ad7e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad85  jb      loc_18003B08C
0x18003ad8b  lea     edx, [rsi+2Ah]
0x18003ad8e  jmp     loc_18003AB2E
0x18003ad93  mov     r8, r14; Size
0x18003ad96  xor     edx, edx; Val
0x18003ad98  mov     rcx, rsi; void *
0x18003ad9b  call    memset_0
0x18003ada0  mov     r8, [r12]; unsigned __int16 *
0x18003ada4  lea     rax, [rbp+pbInput]
0x18003ada8  lea     r9, [rbp+Block]; unsigned __int16 **
0x18003adac  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003adb1  mov     rdx, rbx; unsigned __int64
0x18003adb4  mov     [rbp+Block], rsi
0x18003adb8  mov     rcx, rsi; unsigned __int16 *
0x18003adbb  mov     [rbp+pbInput], rbx
0x18003adbf  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003adc4  mov     ebx, eax
0x18003adc6  test    eax, eax
0x18003adc8  jns     short loc_18003ADE1
0x18003adca  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003add1  jb      loc_18003B08C
0x18003add7  mov     edx, 2Bh ; '+'
0x18003addc  jmp     loc_18003AB2E
0x18003ade1  mov     r8, [r15]; unsigned __int16 *
0x18003ade4  lea     rax, [rbp+pbInput]
0x18003ade8  mov     rdx, [rbp+pbInput]; unsigned __int64
0x18003adec  lea     r9, [rbp+Block]; unsigned __int16 **
0x18003adf0  mov     rcx, [rbp+Block]; unsigned __int16 *
0x18003adf4  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003adf9  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003adfe  mov     ebx, eax
0x18003ae00  test    eax, eax
0x18003ae02  jns     loc_18003AF82
0x18003ae08  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ae0f  jb      loc_18003B08C
0x18003ae15  mov     edx, 2Ch ; ','
0x18003ae1a  jmp     loc_18003AB2E
0x18003ae1f  mov     eax, [rbp+arg_20]
0x18003ae22  add     eax, [rbp+arg_10]
0x18003ae25  add     eax, r14d
0x18003ae28  mov     ebx, eax
0x18003ae2a  jnz     short loc_18003AE4A
0x18003ae2c  mov     eax, 80070216h
0x18003ae31  mov     ebx, eax
0x18003ae33  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ae3a  jb      loc_18003B08C
0x18003ae40  mov     edx, 2Dh ; '-'
0x18003ae45  jmp     loc_18003AB2E
0x18003ae4a  lea     r14, [rax+rax]
0x18003ae4e  test    r14, r14
0x18003ae51  jnz     short loc_18003AE70
0x18003ae53  mov     eax, 80070216h
0x18003ae58  mov     ebx, eax
0x18003ae5a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ae61  jb      loc_18003B08C
0x18003ae67  lea     edx, [r14+2Eh]
0x18003ae6b  jmp     loc_18003AB2E
0x18003ae70  mov     rdx, rbx
0x18003ae73  lea     rcx, [rbp+Block]
0x18003ae77  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x18003ae7c  mov     rdx, rax
0x18003ae7f  lea     rcx, [rbp+pbInput]
0x18003ae83  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003ae88  mov     rcx, [rbp+Block]; Block
0x18003ae8c  mov     [rbp+Block], rsi
0x18003ae90  test    rcx, rcx
0x18003ae93  jz      short loc_18003AE9A
0x18003ae95  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18003ae9a  mov     rsi, [rbp+pbInput]
0x18003ae9e  test    rsi, rsi
0x18003aea1  jnz     short loc_18003AEBF
0x18003aea3  mov     eax, 8007000Eh
0x18003aea8  mov     ebx, eax
0x18003aeaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003aeb1  jb      loc_18003B08C
0x18003aeb7  lea     edx, [rsi+2Fh]
0x18003aeba  jmp     loc_18003AB2E
0x18003aebf  mov     r8, r14; Size
0x18003aec2  xor     edx, edx; Val
0x18003aec4  mov     rcx, rsi; void *
0x18003aec7  call    memset_0
0x18003aecc  mov     r8, [r13+0]; unsigned __int16 *
0x18003aed0  lea     rax, [rbp+pbInput]
0x18003aed4  lea     r9, [rbp+Block]; unsigned __int16 **
0x18003aed8  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003aedd  mov     rdx, rbx; unsigned __int64
0x18003aee0  mov     [rbp+Block], rsi
0x18003aee4  mov     rcx, rsi; unsigned __int16 *
0x18003aee7  mov     [rbp+pbInput], rbx
0x18003aeeb  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003aef0  mov     ebx, eax
0x18003aef2  test    eax, eax
0x18003aef4  jns     short loc_18003AF0D
0x18003aef6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003aefd  jb      loc_18003B08C
0x18003af03  mov     edx, 30h ; '0'
0x18003af08  jmp     loc_18003AB2E
0x18003af0d  mov     r8, [r12]; unsigned __int16 *
0x18003af11  lea     rax, [rbp+pbInput]
0x18003af15  mov     rdx, [rbp+pbInput]; unsigned __int64
0x18003af19  lea     r9, [rbp+Block]; unsigned __int16 **
0x18003af1d  mov     rcx, [rbp+Block]; unsigned __int16 *
0x18003af21  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003af26  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003af2b  mov     ebx, eax
0x18003af2d  test    eax, eax
0x18003af2f  jns     short loc_18003AF48
0x18003af31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003af38  jb      loc_18003B08C
0x18003af3e  mov     edx, 31h ; '1'
0x18003af43  jmp     loc_18003AB2E
0x18003af48  mov     r8, [r15]; unsigned __int16 *
0x18003af4b  lea     rax, [rbp+pbInput]
0x18003af4f  mov     rdx, [rbp+pbInput]; unsigned __int64
0x18003af53  lea     r9, [rbp+Block]; unsigned __int16 **
0x18003af57  mov     rcx, [rbp+Block]; unsigned __int16 *
0x18003af5b  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003af60  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003af65  mov     ebx, eax
0x18003af67  test    eax, eax
  ... truncated ...
```
