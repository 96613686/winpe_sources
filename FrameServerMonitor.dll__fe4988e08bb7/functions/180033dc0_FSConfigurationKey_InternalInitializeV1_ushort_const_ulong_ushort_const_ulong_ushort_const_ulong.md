# FSConfigurationKey::InternalInitializeV1(ushort const *,ulong,ushort const *,ulong,ushort const *,ulong)

- ea: `0x180033dc0`
- end: `0x180034250`
- name: `?InternalInitializeV1@FSConfigurationKey@@MEAAJPEBGK0K0K@Z`
- size: `1168`
- prototype: `__int64 __fastcall(FSConfigurationKey *__hidden this, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned int)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x180002346`
- `0x180004f34`
- `0x180006a98`
- `0x18000723c`
- `0x18000d1e0`
- `0x18000e25c`
- `0x180033dc0`
- `0x180034258`
- `0x180034810`
- `0x18003490c`
- `0x18003fcdc`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033e69`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033eeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033f6a`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033e69`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033eeb`
- `api-ms-win-crt-private-l1-1-0!_o__wcslwr` at `0x180033f6a`

## pseudocode

```c
__int64 __fastcall FSConfigurationKey::InternalInitializeV1(
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
  unsigned __int64 v20; // r15
  __int64 *v21; // r12
  const struct std::nothrow_t *v22; // rax
  const struct std::nothrow_t *v23; // rdx
  __int16 v24; // r8
  int v25; // r9d
  unsigned __int64 v26; // rbx
  __int64 *v27; // r14
  const struct std::nothrow_t *v28; // rax
  const struct std::nothrow_t *v29; // rdx
  __int16 v30; // r8
  int v31; // r9d
  unsigned __int64 v32; // rax
  unsigned __int64 v33; // rdi
  __int64 v34; // r15
  const struct std::nothrow_t *v35; // rax
  const struct std::nothrow_t *v36; // rdx
  unsigned __int16 *v37; // rbx
  const unsigned __int16 *v38; // r8
  const unsigned __int16 *v39; // rcx
  char *v40; // r14
  __int64 v41; // rdx
  __int64 i; // r8
  __int64 v43; // rdx
  char v44; // al
  wchar_t v46; // [rsp+20h] [rbp-30h]
  wchar_t v47; // [rsp+20h] [rbp-30h]
  wchar_t v48; // [rsp+20h] [rbp-30h]
  ULONG v49; // [rsp+20h] [rbp-30h]
  unsigned int *v50; // [rsp+28h] [rbp-28h]
  unsigned int *v51; // [rsp+28h] [rbp-28h]
  unsigned int *v52; // [rsp+28h] [rbp-28h]
  unsigned int v53; // [rsp+28h] [rbp-28h]
  unsigned int v54; // [rsp+28h] [rbp-28h]
  unsigned int v55; // [rsp+28h] [rbp-28h]
  unsigned __int16 *v56; // [rsp+40h] [rbp-10h] BYREF
  unsigned __int16 *v57; // [rsp+48h] [rbp-8h] BYREF
  unsigned __int64 v58; // [rsp+90h] [rbp+40h] BYREF
  unsigned int v59; // [rsp+A0h] [rbp+50h] BYREF

  v59 = a3;
  v57 = 0;
  v9 = (void **)((char *)this + 224);
  v10 = a3;
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, a3);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(v9, unique);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v58, v13);
  if ( !*v9 )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_53;
    v17 = 56;
    goto LABEL_4;
  }
  v15 = StringCchCopyW((unsigned __int16 *)*v9, v10, a2);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 57;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v17, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v15);
      goto LABEL_53;
    }
    goto LABEL_53;
  }
  o((wchar_t)*v9, (char)v14, v18, v19, v46, *(long double *)&v50);
  v20 = a5;
  v21 = (__int64 *)((char *)this + 232);
  v22 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, a5);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 29, v22);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v58, v23);
  if ( !*((_QWORD *)this + 29) )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = 58;
      goto LABEL_4;
    }
LABEL_53:
    if ( byte_18005E5A5 )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 72, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v16);
    goto LABEL_55;
  }
  v15 = StringCchCopyW(*((unsigned __int16 **)this + 29), v20, a4);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 59;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  o(*v21, (char)v14, v24, v25, v47, *(long double *)&v51);
  v26 = a7;
  v27 = (__int64 *)((char *)this + 240);
  v28 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, a7);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 30, v28);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v58, v29);
  if ( !*((_QWORD *)this + 30) )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = 60;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v15 = StringCchCopyW(*((unsigned __int16 **)this + 30), v26, a6);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 61;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  o(*v27, (char)v14, v30, v31, v48, *(long double *)&v52);
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qSSS(*((_QWORD *)WPP_GLOBAL_Control + 27), *v27, *v21, (__int64)*v9);
  v32 = a7 + (_DWORD)v20 + v59;
  v33 = v32;
  if ( !(a7 + (_DWORD)v20 + v59) )
  {
    v15 = -2147024362;
    v16 = -2147024362;
    if ( g_wppLevels )
    {
      v17 = 63;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v34 = 2 * v32;
  if ( !(2 * v32) )
  {
    v15 = -2147024362;
    v16 = -2147024362;
    if ( g_wppLevels )
    {
      v17 = 64;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v35 = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v58, v32);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)&v57, v35);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v58, v36);
  v37 = v57;
  if ( !v57 )
  {
    v15 = -2147024882;
    v16 = -2147024882;
    if ( g_wppLevels )
    {
      v17 = (unsigned int)((_DWORD)v57 + 65);
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  memset_0(v57, 0, v34);
  v38 = (const unsigned __int16 *)*v9;
  v56 = v37;
  v58 = v33;
  v15 = StringCchCopyExW(v37, v33, v38, &v56, &v58, v53);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 66;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v15 = StringCchCopyExW(v56, v58, (const unsigned __int16 *)*v21, &v56, &v58, v54);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 67;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v15 = StringCchCopyExW(v56, v58, (const unsigned __int16 *)*v27, &v56, &v58, v55);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 68;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  v59 = 0;
  v40 = (char *)this + 56;
  v15 = FSCreateHash(v39, (unsigned __int8 *)v37, v34, (unsigned __int8 *)this + 56, v49, &v59);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 69;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  if ( this == (FSConfigurationKey *)-56LL )
  {
    v16 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        70,
        &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids,
        -56,
        -2147024809);
    goto LABEL_53;
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
  v15 = FSConfigurationKey::InternalSerialize(this);
  v16 = v15;
  if ( v15 < 0 )
  {
    if ( g_wppLevels )
    {
      v17 = 71;
      goto LABEL_4;
    }
    goto LABEL_53;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), 73, &WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids, this, v15);
LABEL_55:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)&v57, v14);
  return v16;
}

```

## disassembly

```asm
0x180033dc0  mov     [rsp-38h+arg_8], rbx
0x180033dc5  mov     [rsp-38h+arg_10], r8d
0x180033dca  push    rbp
0x180033dcb  push    rsi
0x180033dcc  push    rdi
0x180033dcd  push    r12
0x180033dcf  push    r13
0x180033dd1  push    r14
0x180033dd3  push    r15
0x180033dd5  mov     rbp, rsp
0x180033dd8  sub     rsp, 50h
0x180033ddc  mov     rdi, rdx
0x180033ddf  mov     [rbp+var_8], 0
0x180033de7  mov     rsi, rcx
0x180033dea  mov     edx, r8d
0x180033ded  lea     r13, [rcx+0E0h]
0x180033df4  mov     ebx, r8d
0x180033df7  lea     rcx, [rbp+arg_0]
0x180033dfb  mov     r14, r9
0x180033dfe  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033e03  mov     rdx, rax
0x180033e06  mov     rcx, r13
0x180033e09  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033e0e  lea     rcx, [rbp+arg_0]
0x180033e12  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033e17  mov     rcx, [r13+0]; unsigned __int16 *
0x180033e1b  test    rcx, rcx
0x180033e1e  jnz     short loc_180033E40
0x180033e20  mov     eax, 8007000Eh
0x180033e25  mov     edi, eax
0x180033e27  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033e2e  jb      loc_1800341FE
0x180033e34  lea     edx, [rcx+38h]
0x180033e37  mov     dword ptr [rsp+50h+var_30], eax
0x180033e3b  jmp     loc_1800341E4
0x180033e40  mov     r8, rdi; unsigned __int16 *
0x180033e43  mov     rdx, rbx; unsigned __int64
0x180033e46  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033e4b  mov     edi, eax
0x180033e4d  test    eax, eax
0x180033e4f  jns     short loc_180033E65
0x180033e51  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033e58  jb      loc_1800341FE
0x180033e5e  mov     edx, 39h ; '9'
0x180033e63  jmp     short loc_180033E37
0x180033e65  mov     rcx, [r13+0]
0x180033e69  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180033e6f  mov     r15d, [rbp+arg_20]
0x180033e73  lea     rcx, [rbp+arg_0]
0x180033e77  mov     edx, r15d
0x180033e7a  lea     r12, [rsi+0E8h]
0x180033e81  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033e86  mov     rdx, rax
0x180033e89  mov     rcx, r12
0x180033e8c  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033e91  lea     rcx, [rbp+arg_0]
0x180033e95  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033e9a  mov     rcx, [r12]; unsigned __int16 *
0x180033e9e  test    rcx, rcx
0x180033ea1  jnz     short loc_180033EBF
0x180033ea3  mov     eax, 8007000Eh
0x180033ea8  mov     edi, eax
0x180033eaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033eb1  jb      loc_1800341FE
0x180033eb7  lea     edx, [rcx+3Ah]
0x180033eba  jmp     loc_180033E37
0x180033ebf  mov     r8, r14; unsigned __int16 *
0x180033ec2  mov     rdx, r15; unsigned __int64
0x180033ec5  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033eca  mov     edi, eax
0x180033ecc  test    eax, eax
0x180033ece  jns     short loc_180033EE7
0x180033ed0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033ed7  jb      loc_1800341FE
0x180033edd  mov     edx, 3Bh ; ';'
0x180033ee2  jmp     loc_180033E37
0x180033ee7  mov     rcx, [r12]
0x180033eeb  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180033ef1  mov     ebx, [rbp+arg_30]
0x180033ef4  lea     rcx, [rbp+arg_0]
0x180033ef8  mov     edx, ebx
0x180033efa  lea     r14, [rsi+0F0h]
0x180033f01  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180033f06  mov     rdx, rax
0x180033f09  mov     rcx, r14
0x180033f0c  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x180033f11  lea     rcx, [rbp+arg_0]
0x180033f15  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180033f1a  mov     rcx, [r14]; unsigned __int16 *
0x180033f1d  test    rcx, rcx
0x180033f20  jnz     short loc_180033F3E
0x180033f22  mov     eax, 8007000Eh
0x180033f27  mov     edi, eax
0x180033f29  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033f30  jb      loc_1800341FE
0x180033f36  lea     edx, [rcx+3Ch]
0x180033f39  jmp     loc_180033E37
0x180033f3e  mov     r8, [rbp+arg_28]; unsigned __int16 *
0x180033f42  mov     rdx, rbx; unsigned __int64
0x180033f45  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180033f4a  mov     edi, eax
0x180033f4c  test    eax, eax
0x180033f4e  jns     short loc_180033F67
0x180033f50  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033f57  jb      loc_1800341FE
0x180033f5d  mov     edx, 3Dh ; '='
0x180033f62  jmp     loc_180033E37
0x180033f67  mov     rcx, [r14]
0x180033f6a  call    cs:__imp__o__wcslwr; o(wchar_t,char,short,long,wchar_t,long double)
0x180033f70  cmp     cs:byte_18005E5A5, 8
0x180033f77  jb      short loc_180033FB5
0x180033f79  mov     rax, [r13+0]
0x180033f7d  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x180033f84  mov     rcx, cs:WPP_GLOBAL_Control
0x180033f8b  mov     edx, 3Eh ; '>'
0x180033f90  mov     [rsp+50h+var_20], rax; __int64
0x180033f95  mov     r9, rsi
0x180033f98  mov     rax, [r12]
0x180033f9c  mov     [rsp+50h+var_28], rax; unsigned int
0x180033fa1  mov     rax, [r14]
0x180033fa4  mov     rcx, [rcx+0D8h]; LoggerHandle
0x180033fab  mov     [rsp+50h+var_30], rax; __int64
0x180033fb0  call    WPP_SF_qSSS
0x180033fb5  mov     eax, [rbp+arg_10]
0x180033fb8  add     eax, r15d
0x180033fbb  add     eax, [rbp+arg_30]
0x180033fbe  mov     edi, eax
0x180033fc0  jnz     short loc_180033FE0
0x180033fc2  mov     eax, 80070216h
0x180033fc7  mov     edi, eax
0x180033fc9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033fd0  jb      loc_1800341FE
0x180033fd6  mov     edx, 3Fh ; '?'
0x180033fdb  jmp     loc_180033E37
0x180033fe0  lea     r15, [rax+rax]
0x180033fe4  test    r15, r15
0x180033fe7  jnz     short loc_180034006
0x180033fe9  mov     eax, 80070216h
0x180033fee  mov     edi, eax
0x180033ff0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180033ff7  jb      loc_1800341FE
0x180033ffd  lea     edx, [r15+40h]
0x180034001  jmp     loc_180033E37
0x180034006  mov     rdx, rdi
0x180034009  lea     rcx, [rbp+arg_0]
0x18003400d  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180034012  mov     rdx, rax
0x180034015  lea     rcx, [rbp+var_8]
0x180034019  call    ??4?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::operator=(wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &&)
0x18003401e  lea     rcx, [rbp+arg_0]
0x180034022  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180034027  mov     rbx, [rbp+var_8]
0x18003402b  test    rbx, rbx
0x18003402e  jnz     short loc_18003404C
0x180034030  mov     eax, 8007000Eh
0x180034035  mov     edi, eax
0x180034037  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003403e  jb      loc_1800341FE
0x180034044  lea     edx, [rbx+41h]
0x180034047  jmp     loc_180033E37
0x18003404c  mov     r8, r15; Size
0x18003404f  xor     edx, edx; Val
0x180034051  mov     rcx, rbx; void *
0x180034054  call    memset_0
0x180034059  mov     r8, [r13+0]; unsigned __int16 *
0x18003405d  lea     rax, [rbp+arg_0]
0x180034061  lea     r9, [rbp+var_10]; unsigned __int16 **
0x180034065  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x18003406a  mov     rdx, rdi; unsigned __int64
0x18003406d  mov     [rbp+var_10], rbx
0x180034071  mov     rcx, rbx; unsigned __int16 *
0x180034074  mov     [rbp+arg_0], rdi
0x180034078  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x18003407d  mov     edi, eax
0x18003407f  test    eax, eax
0x180034081  jns     short loc_18003409A
0x180034083  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003408a  jb      loc_1800341FE
0x180034090  mov     edx, 42h ; 'B'
0x180034095  jmp     loc_180033E37
0x18003409a  mov     r8, [r12]; unsigned __int16 *
0x18003409e  lea     rax, [rbp+arg_0]
0x1800340a2  mov     rdx, [rbp+arg_0]; unsigned __int64
0x1800340a6  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800340aa  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x1800340ae  mov     [rsp+50h+var_30], rax; unsigned __int64 *
0x1800340b3  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800340b8  mov     edi, eax
0x1800340ba  test    eax, eax
0x1800340bc  jns     short loc_1800340D5
0x1800340be  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800340c5  jb      loc_1800341FE
0x1800340cb  mov     edx, 43h ; 'C'
0x1800340d0  jmp     loc_180033E37
0x1800340d5  mov     r8, [r14]; unsigned __int16 *
0x1800340d8  lea     rax, [rbp+arg_0]
0x1800340dc  mov     rdx, [rbp+arg_0]; unsigned __int64
0x1800340e0  lea     r9, [rbp+var_10]; unsigned __int16 **
0x1800340e4  mov     rcx, [rbp+var_10]; unsigned __int16 *
0x1800340e8  mov     [rsp+50h+var_30], rax; unsigned int
0x1800340ed  call    ?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z; StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)
0x1800340f2  mov     edi, eax
0x1800340f4  test    eax, eax
0x1800340f6  jns     short loc_18003410F
0x1800340f8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800340ff  jb      loc_1800341FE
0x180034105  mov     edx, 44h ; 'D'
0x18003410a  jmp     loc_180033E37
0x18003410f  lea     rax, [rbp+arg_10]
0x180034113  mov     [rbp+arg_10], 0
0x18003411a  lea     r14, [rsi+38h]
0x18003411e  mov     [rsp+50h+var_28], rax; unsigned int *
0x180034123  mov     r9, r14; unsigned __int8 *
0x180034126  mov     r8d, r15d; unsigned int
0x180034129  mov     rdx, rbx; unsigned __int8 *
0x18003412c  call    ?FSCreateHash@@YAJPEBGPEAEK1KPEAK@Z; FSCreateHash(ushort const *,uchar *,ulong,uchar *,ulong,ulong *)
0x180034131  mov     edi, eax
0x180034133  test    eax, eax
0x180034135  jns     short loc_18003414E
0x180034137  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003413e  jb      loc_1800341FE
0x180034144  mov     edx, 45h ; 'E'
0x180034149  jmp     loc_180033E37
0x18003414e  test    r14, r14
0x180034151  jz      short loc_1800341CD
0x180034153  xor     edx, edx
0x180034155  lea     r9, a0123456789abcd_0; "0123456789ABCDEF"
0x18003415c  xor     r8d, r8d
0x18003415f  movzx   eax, byte ptr [r14+r8]
0x180034164  shr     rax, 4
0x180034168  movzx   eax, word ptr [r9+rax*2]
0x18003416d  mov     [rsi+rdx*2+58h], ax
0x180034172  inc     edx
0x180034174  movzx   eax, byte ptr [r14+r8]
0x180034179  inc     r8
0x18003417c  and     eax, 0Fh
0x18003417f  movzx   eax, word ptr [r9+rax*2]
0x180034184  mov     [rsi+rdx*2+58h], ax
0x180034189  inc     edx
0x18003418b  cmp     r8, 20h ; ' '
0x18003418f  jnz     short loc_18003415F
0x180034191  xor     eax, eax
0x180034193  mov     [rsi+rdx*2+58h], ax
0x180034198  mov     rcx, rsi; this
0x18003419b  call    ?InternalSerialize@FSConfigurationKey@@IEAAJXZ; FSConfigurationKey::InternalSerialize(void)
0x1800341a0  mov     edi, eax
0x1800341a2  test    eax, eax
0x1800341a4  jns     short loc_1800341B9
0x1800341a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800341ad  jb      short loc_1800341FE
0x1800341af  mov     edx, 47h ; 'G'
0x1800341b4  jmp     loc_180033E37
0x1800341b9  cmp     cs:byte_18005E5A5, 8
0x1800341c0  jb      short loc_18003422D
0x1800341c2  mov     edx, 49h ; 'I'
0x1800341c7  mov     dword ptr [rsp+50h+var_30], eax
0x1800341cb  jmp     short loc_180034210
0x1800341cd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800341d4  mov     edi, 80070057h
0x1800341d9  jb      short loc_1800341FE
0x1800341db  mov     edx, 46h ; 'F'
0x1800341e0  mov     dword ptr [rsp+50h+var_30], edi
0x1800341e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800341eb  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x1800341f2  mov     r9, rsi
0x1800341f5  mov     rcx, [rcx+10h]
0x1800341f9  call    WPP_SF_qD
0x1800341fe  cmp     cs:byte_18005E5A5, 1
0x180034205  jb      short loc_18003422D
0x180034207  mov     edx, 48h ; 'H'
0x18003420c  mov     dword ptr [rsp+50h+var_30], edi
0x180034210  mov     rcx, cs:WPP_GLOBAL_Control
0x180034217  lea     r8, WPP_72cf6ba4cbe23f0a9b7a240d5b293351_Traceguids
0x18003421e  mov     r9, rsi
0x180034221  mov     rcx, [rcx+0D8h]
0x180034228  call    WPP_SF_qD
0x18003422d  lea     rcx, [rbp+var_8]
0x180034231  call    ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
0x180034236  mov     rbx, [rsp+50h+arg_8]
0x18003423e  mov     eax, edi
0x180034240  add     rsp, 50h
0x180034244  pop     r15
0x180034246  pop     r14
0x180034248  pop     r13
0x18003424a  pop     r12
0x18003424c  pop     rdi
0x18003424d  pop     rsi
0x18003424e  pop     rbp
0x18003424f  retn
```
