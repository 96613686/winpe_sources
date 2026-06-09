# FSConfigurationKey::InternalInitialize(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong)

- ea: `0x1800337b0`
- end: `0x180033db6`
- name: `?InternalInitialize@FSConfigurationKey@@MEAAJPEBGK0K0K@Z`
- size: `1542`
- prototype: `__int64 __fastcall(FSConfigurationKey *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config`

## callees

- `0x180002346`
- `0x180004f34`
- `0x180006a98`
- `0x18000723c`
- `0x18000d024`
- `0x18000d1e0`
- `0x18000d4f8`
- `0x18000e25c`
- `0x1800337b0`
- `0x180034258`
- `0x180034810`
- `0x18003490c`
- `0x18003fcdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033859`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800338db`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003395a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033859`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x1800338db`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x18003395a`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitialize(
        FSConfigurationKey *this,
        const unsigned __int16 *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        unsigned __int16 *a6,
        unsigned int a7)
{
  void **v9; // r13
  unsigned __int64 v10; // rbx
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v13; // rdx
  const struct std::nothrow_t *v14; // rdx
  int v15; // eax
  unsigned int v16; // edi
  __int64 v17; // rdx
  __int16 v18; // r8
  int v19; // r9d
  unsigned __int64 v20; // r14
  __int64 *v21; // r12
  const struct std::nothrow_t *v22; // rax
  const struct std::nothrow_t *v23; // rdx
  __int16 v24; // r8
  int v25; // r9d
  unsigned __int64 v26; // rbx
  __int64 *v27; // r15
  const struct std::nothrow_t *v28; // rax
  const struct std::nothrow_t *v29; // rdx
  __int16 v30; // r8
  int v31; // r9d
  __int64 v32; // rax
  unsigned __int64 v33; // rdi
  __int64 v34; // r14
  const struct std::nothrow_t *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  unsigned __int16 *v37; // rbx
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // rcx
  unsigned __int64 v40; // rax
  unsigned __int64 v41; // rdi
  const struct std::nothrow_t *v42; // rax
  const struct std::nothrow_t *v43; // rdx
  const unsigned __int16 *v44; // r8
  char *v45; // r15
  __int64 v46; // r8
  __int64 i; // r9
  __int64 v48; // r8
  char v49; // al
  __int64 v50; // rdx
  wchar_t v52; // [rsp+20h] [rbp-30h]
  wchar_t v53; // [rsp+20h] [rbp-30h]
  wchar_t v54; // [rsp+20h] [rbp-30h]
  ULONG v55; // [rsp+20h] [rbp-30h]
  unsigned int *v56; // [rsp+28h] [rbp-28h]
  unsigned int *v57; // [rsp+28h] [rbp-28h]
  unsigned int *v58; // [rsp+28h] [rbp-28h]
  unsigned int v59; // [rsp+28h] [rbp-28h]
  unsigned int v60; // [rsp+28h] [rbp-28h]
  unsigned int v61; // [rsp+28h] [rbp-28h]
  unsigned int v62; // [rsp+28h] [rbp-28h]
  unsigned __int16 *v63; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v64; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int64 v65; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v66; // [rsp+A0h] [rbp+50h] BYREF

  v66 = a3;
  v64 = 0;
  v9 = (void **)((char *)this + 224);
  v10 = a3;
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v65, a3);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(v9, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v65, v13);
  if ( !*v9 )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_72;
    v17 = 32;
    goto LABEL_4;
  }
  v15 = StringCchCopyW((unsigned __int16 *)*v9, v10, a2);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 33;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v15);
      goto LABEL_72;
    }
    goto LABEL_72;
  }
  o((wchar_t)*v9, (char)v14, v18, v19, v52, *(long double *)&v56);
  v20 = a5;
  v21 = (__int64 *)((char *)this + 232);
  v22 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v65, a5);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 29, v22);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v65, v23);
  if ( !*((_QWORD *)this + 29) )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = 34;
      goto LABEL_4;
    }
LABEL_72:
    if ( byte_18005E5A5 )
    {
      v50 = 54;
      goto LABEL_74;
    }
    goto LABEL_75;
  }
  v15 = StringCchCopyW(*((unsigned __int16 **)this + 29), v20, a4);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 35;
      goto LABEL_4;
    }
    goto LABEL_72;
  }
  o(*v21, (char)v14, v24, v25, v53, *(long double *)&v57);
  v26 = a7;
  v27 = (__int64 *)((char *)this + 240);
  v28 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v65, a7);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 30, v28);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v65, v29);
  if ( !*((_QWORD *)this + 30) )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = 36;
      goto LABEL_4;
    }
    goto LABEL_72;
  }
  v15 = StringCchCopyW(*((unsigned __int16 **)this + 30), v26, a6);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 37;
      goto LABEL_4;
    }
    goto LABEL_72;
  }
  o(*v27, (char)v14, v30, v31, v54, *(long double *)&v58);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), *v27, *v21, (__int64)*v9);
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 39, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this);
    v32 = (unsigned int)(v20 + v26);
    v33 = (unsigned int)v32;
    if ( !(_DWORD)v32 )
    {
      v15 = -2147024362;
      v16 = -2147024362;
      if ( g_wppLevels )
      {
        v17 = 40;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v34 = 2 * v32;
    if ( !(2 * v32) )
    {
      v15 = -2147024362;
      v16 = -2147024362;
      if ( g_wppLevels )
      {
        v17 = 41;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v35 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v65, (unsigned int)v32);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v64, v35);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v65, v36);
    v37 = v64;
    if ( !v64 )
    {
      v15 = -2147024882;
      v16 = -2147024882;
      if ( g_wppLevels )
      {
        v17 = (unsigned int)((_DWORD)v64 + 42);
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    memset_0(v64, 0, v34);
    v38 = (const unsigned __int16 *)*v21;
    v63 = v37;
    v65 = v33;
    v15 = StringCchCopyExW(v37, v33, v38, &v63, &v65, v59);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 43;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v15 = StringCchCopyExW(v63, v65, (const unsigned __int16 *)*v27, &v63, &v65, v60);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 44;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
  }
  else
  {
    v40 = (unsigned int)v26 + (_DWORD)v20 + v66;
    v41 = v40;
    if ( !((_DWORD)v26 + (_DWORD)v20 + v66) )
    {
      v15 = -2147024362;
      v16 = -2147024362;
      if ( g_wppLevels )
      {
        v17 = 45;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v34 = 2 * v40;
    if ( !(2 * v40) )
    {
      v15 = -2147024362;
      v16 = -2147024362;
      if ( g_wppLevels )
      {
        v17 = 46;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v42 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v65, v40);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v64, v42);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v65, v43);
    v37 = v64;
    if ( !v64 )
    {
      v15 = -2147024882;
      v16 = -2147024882;
      if ( g_wppLevels )
      {
        v17 = (unsigned int)((_DWORD)v64 + 47);
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    memset_0(v64, 0, v34);
    v44 = (const unsigned __int16 *)*v9;
    v63 = v37;
    v65 = v41;
    v15 = StringCchCopyExW(v37, v41, v44, &v63, &v65, v59);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 48;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v15 = StringCchCopyExW(v63, v65, (const unsigned __int16 *)*v21, &v63, &v65, v61);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 49;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
    v15 = StringCchCopyExW(v63, v65, (const unsigned __int16 *)*v27, &v63, &v65, v62);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 50;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
  }
  v66 = 0;
  v45 = (char *)this + 56;
  v15 = FSCreateHash(v39, (unsigned __int8 *)v37, v34, (unsigned __int8 *)this + 56, v55, &v66);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 51;
      goto LABEL_4;
    }
    goto LABEL_72;
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
    goto LABEL_72;
  }
  v46 = 0;
  for ( i = 0; i != 32; ++i )
  {
    *((_WORD *)this + v46 + 44) = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v45[i] >> 4];
    v48 = (unsigned int)(v46 + 1);
    v49 = v45[i];
    *((_WORD *)this + v48 + 44) = a0123456789abcd_0[v49 & 0xF];
    v46 = (unsigned int)(v48 + 1);
  }
  *((_WORD *)this + v46 + 44) = 0;
  v16 = 0;
  if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl'::`2'::impl) )
  {
    v15 = FSConfigurationKey::InternalSerialize(this);
    v16 = v15;
    if ( v15 < 0 )
    {
      if ( g_wppLevels )
      {
        v17 = 53;
        goto LABEL_4;
      }
      goto LABEL_72;
    }
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v50 = 55;
LABEL_74:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v50, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v16);
  }
LABEL_75:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v64, v14);
  return v16;
}

```

## disassembly

```asm
0x1800337b0  mov     [rsp-38h+arg_8], rbx
0x1800337b5  mov     [rsp-38h+arg_10], r8d
0x1800337ba  push    rbp
0x1800337bb  push    rsi
0x1800337bc  push    rdi
0x1800337bd  push    r12
0x1800337bf  push    r13
0x1800337c1  push    r14
0x1800337c3  push    r15
0x1800337c5  mov     rbp, rsp
0x1800337c8  sub     rsp, 50h
0x1800337cc  mov     rdi, rdx
0x1800337cf  mov     [rbp+var_8], 0
0x1800337d7  mov     rsi, rcx
0x1800337da  mov     edx, r8d
0x1800337dd  lea     r13, [rcx+0E0h]
0x1800337e4  mov     ebx, r8d
0x1800337e7  lea     rcx, [rbp+arg_0]
0x1800337eb  mov     r15, r9
0x1800337ee  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800337f3  mov     rdx, rax
0x1800337f6  mov     rcx, r13
0x1800337f9  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x1800337fe  lea     rcx, [rbp+arg_0]
0x180033802  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033807  mov     rcx, [r13+0]; unsigned __int16 *
0x18003380b  test    rcx, rcx
0x18003380e  jnz     short loc_180033830
0x180033810  mov     eax, 8007000Eh
0x180033815  mov     edi, eax
0x180033817  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003381e  jb      loc_180033D64
0x180033824  lea     edx, [rcx+20h]
0x180033827  mov     dword ptr [rsp+50h+var_30], eax
0x18003382b  jmp     loc_180033D4A
0x180033830  mov     r8, rdi; unsigned __int16 *
0x180033833  mov     rdx, rbx; unsigned __int64
0x180033836  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003383b  mov     edi, eax
0x18003383d  test    eax, eax
0x18003383f  jns     short loc_180033855
0x180033841  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033848  jb      loc_180033D64
0x18003384e  mov     edx, 21h ; '!'
0x180033853  jmp     short loc_180033827
0x180033855  mov     rcx, [r13+0]
0x180033859  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x18003385f  mov     r14d, [rbp+arg_20]
0x180033863  lea     rcx, [rbp+arg_0]
0x180033867  mov     edx, r14d
0x18003386a  lea     r12, [rsi+0E8h]
0x180033871  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033876  mov     rdx, rax
0x180033879  mov     rcx, r12
0x18003387c  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033881  lea     rcx, [rbp+arg_0]
0x180033885  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003388a  mov     rcx, [r12]; unsigned __int16 *
0x18003388e  test    rcx, rcx
0x180033891  jnz     short loc_1800338AF
0x180033893  mov     eax, 8007000Eh
0x180033898  mov     edi, eax
0x18003389a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800338a1  jb      loc_180033D64
0x1800338a7  lea     edx, [rcx+22h]
0x1800338aa  jmp     loc_180033827
0x1800338af  mov     r8, r15; unsigned __int16 *
0x1800338b2  mov     rdx, r14; unsigned __int64
0x1800338b5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800338ba  mov     edi, eax
0x1800338bc  test    eax, eax
0x1800338be  jns     short loc_1800338D7
0x1800338c0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800338c7  jb      loc_180033D64
0x1800338cd  mov     edx, 23h ; '#'
0x1800338d2  jmp     loc_180033827
0x1800338d7  mov     rcx, [r12]
0x1800338db  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x1800338e1  mov     ebx, [rbp+arg_30]
0x1800338e4  lea     rcx, [rbp+arg_0]
0x1800338e8  mov     edx, ebx
0x1800338ea  lea     r15, [rsi+0F0h]
0x1800338f1  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800338f6  mov     rdx, rax
0x1800338f9  mov     rcx, r15
0x1800338fc  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033901  lea     rcx, [rbp+arg_0]
0x180033905  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x18003390a  mov     rcx, [r15]; unsigned __int16 *
0x18003390d  test    rcx, rcx
0x180033910  jnz     short loc_18003392E
0x180033912  mov     eax, 8007000Eh
0x180033917  mov     edi, eax
0x180033919  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033920  jb      loc_180033D64
0x180033926  lea     edx, [rcx+24h]
0x180033929  jmp     loc_180033827
0x18003392e  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x180033932  mov     rdx, rbx; unsigned __int64
0x180033935  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18003393a  mov     edi, eax
0x18003393c  test    eax, eax
0x18003393e  jns     short loc_180033957
0x180033940  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033947  jb      loc_180033D64
0x18003394d  mov     edx, 25h ; '%'
0x180033952  jmp     loc_180033827
0x180033957  mov     rcx, [r15]
0x18003395a  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180033960  cmp     cs:byte_18005E5A5, 8
0x180033967  jb      short loc_1800339A5
0x180033969  mov     rax, [r13+0]
0x18003396d  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180033974  mov     rcx, cs:WPP_GLOBAL_Control
0x18003397b  mov     edx, 26h ; '&'
0x180033980  mov     [rsp+50h+var_20], rax; __int64
0x180033985  mov     r9, rsi
0x180033988  mov     rax, [r12]
0x18003398c  mov     [rsp+50h+var_28], rax; unsigned int
0x180033991  mov     rax, [r15]
0x180033994  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003399b  mov     [rsp+50h+var_30], rax; __int64
0x1800339a0  call    WPP_SF_qSSS
0x1800339a5  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_39449421@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421> `wil::Feature<__WilFeatureTraits_Feature_39449421>::GetImpl(void)'::`2'::impl
0x1800339ac  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_39449421@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_39449421>::__private_IsEnabled(void)
0x1800339b1  test    al, al
0x1800339b3  jz      loc_180033B04
0x1800339b9  cmp     cs:byte_18005E5A5, 8
0x1800339c0  jb      short loc_1800339E4
0x1800339c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800339c9  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x1800339d0  mov     edx, 27h ; '''
0x1800339d5  mov     r9, rsi
0x1800339d8  mov     rcx, [rcx+0D8h]
0x1800339df  call    WPP_SF_q
0x1800339e4  lea     eax, [r14+rbx]
0x1800339e8  mov     edi, eax
0x1800339ea  test    eax, eax
0x1800339ec  jnz     short loc_180033A0C
0x1800339ee  mov     eax, 80070216h
0x1800339f3  mov     edi, eax
0x1800339f5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800339fc  jb      loc_180033D64
0x180033a02  mov     edx, 28h ; '('
0x180033a07  jmp     loc_180033827
0x180033a0c  lea     r14, [rax+rax]
0x180033a10  test    r14, r14
0x180033a13  jnz     short loc_180033A32
0x180033a15  mov     eax, 80070216h
0x180033a1a  mov     edi, eax
0x180033a1c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033a23  jb      loc_180033D64
0x180033a29  lea     edx, [r14+29h]
0x180033a2d  jmp     loc_180033827
0x180033a32  mov     rdx, rdi
0x180033a35  lea     rcx, [rbp+arg_0]
0x180033a39  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033a3e  mov     rdx, rax
0x180033a41  lea     rcx, [rbp+var_8]
0x180033a45  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033a4a  lea     rcx, [rbp+arg_0]
0x180033a4e  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033a53  mov     rbx, [rbp+var_8]
0x180033a57  test    rbx, rbx
0x180033a5a  jnz     short loc_180033A78
0x180033a5c  mov     eax, 8007000Eh
0x180033a61  mov     edi, eax
0x180033a63  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033a6a  jb      loc_180033D64
0x180033a70  lea     edx, [rbx+2Ah]
0x180033a73  jmp     loc_180033827
0x180033a78  mov     r8, r14; Size
0x180033a7b  xor     edx, edx; Val
0x180033a7d  mov     rcx, rbx; void *
0x180033a80  call    memset_0
0x180033a85  mov     r8, [r12]; unsigned __int16 *
0x180033a89  lea     rax, [rbp+arg_0]
0x180033a8d  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180033a91  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180033a96  mov     rdx, rdi; unsigned __int64
0x180033a99  mov     [rbp+var_10], rbx
0x180033a9d  mov     rcx, rbx; unsigned __int16 *
0x180033aa0  mov     [rbp+arg_0], rdi
0x180033aa4  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180033aa9  mov     edi, eax
0x180033aab  test    eax, eax
0x180033aad  jns     short loc_180033AC6
0x180033aaf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033ab6  jb      loc_180033D64
0x180033abc  mov     edx, 2Bh ; '+'
0x180033ac1  jmp     loc_180033827
0x180033ac6  mov     r8, [r15]; unsigned __int16 *
0x180033ac9  lea     rax, [rbp+arg_0]
0x180033acd  mov     rdx, [rbp+arg_0]; unsigned __int64
0x180033ad1  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180033ad5  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180033ad9  mov     [rsp+50h+var_30], rax; unsigned int
0x180033ade  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180033ae3  mov     edi, eax
0x180033ae5  test    eax, eax
0x180033ae7  jns     loc_180033C5D
0x180033aed  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033af4  jb      loc_180033D64
0x180033afa  mov     edx, 2Ch ; ','
0x180033aff  jmp     loc_180033827
0x180033b04  mov     eax, [rbp+arg_10]
0x180033b07  add     eax, r14d
0x180033b0a  add     eax, ebx
0x180033b0c  mov     edi, eax
0x180033b0e  jnz     short loc_180033B2E
0x180033b10  mov     eax, 80070216h
0x180033b15  mov     edi, eax
0x180033b17  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033b1e  jb      loc_180033D64
0x180033b24  mov     edx, 2Dh ; '-'
0x180033b29  jmp     loc_180033827
0x180033b2e  lea     r14, [rax+rax]
0x180033b32  test    r14, r14
0x180033b35  jnz     short loc_180033B54
0x180033b37  mov     eax, 80070216h
0x180033b3c  mov     edi, eax
0x180033b3e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033b45  jb      loc_180033D64
0x180033b4b  lea     edx, [r14+2Eh]
0x180033b4f  jmp     loc_180033827
0x180033b54  mov     rdx, rdi
0x180033b57  lea     rcx, [rbp+arg_0]
0x180033b5b  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033b60  mov     rdx, rax
0x180033b63  lea     rcx, [rbp+var_8]
0x180033b67  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033b6c  lea     rcx, [rbp+arg_0]
0x180033b70  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033b75  mov     rbx, [rbp+var_8]
0x180033b79  test    rbx, rbx
0x180033b7c  jnz     short loc_180033B9A
0x180033b7e  mov     eax, 8007000Eh
0x180033b83  mov     edi, eax
0x180033b85  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033b8c  jb      loc_180033D64
0x180033b92  lea     edx, [rbx+2Fh]
0x180033b95  jmp     loc_180033827
0x180033b9a  mov     r8, r14; Size
0x180033b9d  xor     edx, edx; Val
0x180033b9f  mov     rcx, rbx; void *
0x180033ba2  call    memset_0
0x180033ba7  mov     r8, [r13+0]; unsigned __int16 *
0x180033bab  lea     rax, [rbp+arg_0]
0x180033baf  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180033bb3  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180033bb8  mov     rdx, rdi; unsigned __int64
0x180033bbb  mov     [rbp+var_10], rbx
0x180033bbf  mov     rcx, rbx; unsigned __int16 *
0x180033bc2  mov     [rbp+arg_0], rdi
0x180033bc6  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180033bcb  mov     edi, eax
0x180033bcd  test    eax, eax
0x180033bcf  jns     short loc_180033BE8
0x180033bd1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033bd8  jb      loc_180033D64
0x180033bde  mov     edx, 30h ; '0'
0x180033be3  jmp     loc_180033827
0x180033be8  mov     r8, [r12]; unsigned __int16 *
0x180033bec  lea     rax, [rbp+arg_0]
0x180033bf0  mov     rdx, [rbp+arg_0]; unsigned __int64
0x180033bf4  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180033bf8  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180033bfc  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180033c01  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180033c06  mov     edi, eax
0x180033c08  test    eax, eax
0x180033c0a  jns     short loc_180033C23
0x180033c0c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033c13  jb      loc_180033D64
0x180033c19  mov     edx, 31h ; '1'
0x180033c1e  jmp     loc_180033827
0x180033c23  mov     r8, [r15]; unsigned __int16 *
0x180033c26  lea     rax, [rbp+arg_0]
0x180033c2a  mov     rdx, [rbp+arg_0]; unsigned __int64
0x180033c2e  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180033c32  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x180033c36  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x180033c3b  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x180033c40  mov     edi, eax
0x180033c42  test    eax, eax
0x180033c44  jns     short loc_180033C5D
0x180033c46  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033c4d  jb      loc_180033D64
0x180033c53  mov     edx, 32h ; '2'
0x180033c58  jmp     loc_180033827
0x180033c5d  lea     rax, [rbp+arg_10]
0x180033c61  mov     [rbp+arg_10], 0
0x180033c68  lea     r15, [rsi+38h]
0x180033c6c  mov     [rsp+50h+var_28], rax; unsigned int *
0x180033c71  mov     r9, r15; unsigned __int8 *
0x180033c74  mov     r8d, r14d; unsigned int
0x180033c77  mov     rdx, rbx; unsigned __int8 *
0x180033c7a  call    ?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z; FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)
0x180033c7f  mov     edi, eax
0x180033c81  test    eax, eax
  ... truncated ...
```
