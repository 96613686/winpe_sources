# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(ulong,IMFMediaType *,ulong,CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType_Flag)

- ea: `0x18000676c`
- end: `0x180006bf9`
- name: `?MFTtoDMO_SetType@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJKPEAUIMFMediaType@@KW4MFTtoDMO_SetType_Flag@1@@Z`
- size: `1165`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180006690`
- `0x1800066b0`

## callees

- `0x1800018b0`
- `0x18000330c`
- `0x180003480`
- `0x18000676c`
- `0x180020ff9`
- `0x180022010`

## pseudocode

```c
__int64 __fastcall CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(
        __int64 a1,
        unsigned int a2,
        __int64 *a3,
        unsigned int a4,
        int a5)
{
  __int64 *v9; // rdi
  __int64 v10; // rax
  unsigned int v11; // edx
  __int64 v12; // rcx
  int v13; // ecx
  __int64 v14; // r8
  unsigned int v15; // eax
  char v16; // r13
  bool v17; // zf
  __int64 *v18; // rcx
  __int64 (__fastcall *v19)(__int64 *, GUID *, __int64 *); // rax
  __int64 v20; // rcx
  int v21; // ebx
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // rax
  __int64 v25; // r9
  int v26; // eax
  int v27; // edi
  __int64 v28; // rax
  __int64 (__fastcall *v29)(__int64 *, GUID *, __int64 *); // rax
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rax
  __int64 (__fastcall *v33)(__int64 *, GUID *, __int64 *); // rax
  __int64 v34; // rax
  int v35; // eax
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // ecx
  __int64 v41; // [rsp+30h] [rbp-41h] BYREF
  unsigned int v42; // [rsp+38h] [rbp-39h] BYREF
  unsigned int v43; // [rsp+3Ch] [rbp-35h] BYREF
  __int64 v44; // [rsp+40h] [rbp-31h]
  GUID Buf1; // [rsp+50h] [rbp-21h] BYREF
  GUID Buf2; // [rsp+60h] [rbp-11h] BYREF

  v44 = a1;
  v41 = 0;
  Buf2 = GUID_00000000_0000_0000_0000_000000000000;
  if ( (a4 & 0xFFFFFFFE) != 0 )
    return 2147942487LL;
  v9 = (__int64 *)(a1 + 48);
  v43 = 0;
  v10 = *(_QWORD *)(a1 + 48);
  v42 = 0;
  v11 = (*(__int64 (__fastcall **)(__int64, unsigned int *, unsigned int *))(v10 + 24))(a1 + 48, &v43, &v42);
  if ( (v11 & 0x80000000) != 0 )
  {
    v13 = 0;
    while ( 1 )
    {
      v14 = v13;
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v13]) == v11 )
        break;
      if ( (unsigned int)++v13 >= 6 )
        return v11;
    }
    return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v14]);
  }
  v15 = v42;
  if ( !a5 )
    v15 = v43;
  if ( a2 >= v15 )
    return 3222091443LL;
  Buf1 = GUID_00000000_0000_0000_0000_000000000000;
  if ( a3 )
  {
    (*(void (__fastcall **)(__int64 *, const GUID *, GUID *))(*a3 + 80))(a3, &MF_MT_SUBTYPE, &Buf1);
    if ( !memcmp_0(&Buf1, &MEDIASUBTYPE_ARGB32, 0x10u)
      || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB24, 0x10u)
      || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB32, 0x10u)
      || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB555, 0x10u)
      || !memcmp_0(&Buf1, &MEDIASUBTYPE_RGB565, 0x10u) )
    {
      v16 = 1;
      goto LABEL_19;
    }
  }
  CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(v12, a3);
  v16 = 0;
  if ( a3 )
  {
LABEL_19:
    (*(void (__fastcall **)(__int64 *, GUID *))(*a3 + 264))(a3, &Buf2);
    v17 = memcmp_0(&MEDIATYPE_Video, &Buf2, 0x10u) != 0;
    v18 = a3;
    v19 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
    if ( !v17 )
    {
      Buf1 = FORMAT_MFVideoFormat;
      v21 = v19(a3, &Buf1, &v41);
      if ( v21 >= 0 )
      {
        v22 = *v9;
        v23 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v22 + 72))(v9, a2, v41, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v22 + 64))(v9, a2, v41, a4);
        v21 = v23;
        v28 = *a3;
        Buf1 = FORMAT_MFVideoFormat;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v28 + 296))(a3, &Buf1, v41);
        if ( v21 >= 0 )
          goto LABEL_49;
      }
      if ( v21 == -1072861834 )
        goto LABEL_53;
      v29 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
      Buf1 = FORMAT_VideoInfo2;
      v21 = v29(a3, &Buf1, &v41);
      if ( v21 >= 0 )
      {
        v30 = *v9;
        v31 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v30 + 72))(v9, a2, v41, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v30 + 64))(v9, a2, v41, a4);
        v21 = v31;
        v32 = *a3;
        Buf1 = FORMAT_VideoInfo2;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v32 + 296))(a3, &Buf1, v41);
        if ( v21 >= 0 )
          goto LABEL_49;
      }
      if ( v21 == -1072861834 )
        goto LABEL_53;
      v33 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
      Buf1 = FORMAT_VideoInfo;
      v21 = v33(a3, &Buf1, &v41);
      if ( v21 >= 0 )
      {
        v34 = *v9;
        v35 = a5
            ? (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v34 + 72))(v9, a2, v41, a4)
            : (*(unsigned __int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v34 + 64))(v9, a2, v41, a4);
        v21 = v35;
        v36 = *a3;
        Buf1 = FORMAT_VideoInfo;
        (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v36 + 296))(a3, &Buf1, v41);
        if ( v21 >= 0 )
          goto LABEL_49;
      }
      if ( v21 == -1072861834 )
        goto LABEL_53;
      v18 = a3;
      v19 = *(__int64 (__fastcall **)(__int64 *, GUID *, __int64 *))(*a3 + 288);
    }
    Buf1 = AM_MEDIA_TYPE_REPRESENTATION;
    v21 = v19(v18, &Buf1, &v41);
    if ( v21 < 0
      || ((v37 = *v9, a5)
        ? (v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v37 + 72))(v9, a2, v41, a4))
        : (v38 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64, _QWORD))(v37 + 64))(v9, a2, v41, a4)),
          v21 = v38,
          v39 = *a3,
          Buf1 = AM_MEDIA_TYPE_REPRESENTATION,
          (*(void (__fastcall **)(__int64 *, GUID *, __int64))(v39 + 296))(a3, &Buf1, v41),
          v21 < 0) )
    {
LABEL_53:
      v27 = v21;
      if ( v16 )
        goto LABEL_55;
      goto LABEL_54;
    }
LABEL_49:
    if ( (a4 & 1) == 0 )
    {
      if ( a5 )
        *(_BYTE *)(v44 + 41) = v16;
      else
        *(_BYTE *)(v44 + 40) = v16;
    }
    goto LABEL_53;
  }
  v24 = *v9;
  v25 = a4 | 2;
  if ( a5 )
    v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v24 + 72))(v9, a2, 0, v25);
  else
    v26 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD, __int64))(v24 + 64))(v9, a2, 0, v25);
  v21 = v26;
  v27 = v26;
LABEL_54:
  CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(v20, a3);
LABEL_55:
  if ( v21 == 1 )
  {
    v27 = -1072875852;
    v11 = -1072875852;
    goto LABEL_58;
  }
  v11 = v27;
  if ( v27 )
  {
LABEL_58:
    v40 = 0;
    while ( 1 )
    {
      v14 = v40;
      if ( LODWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v40]) == v27 )
        break;
      if ( (unsigned int)++v40 >= 6 )
        return v11;
    }
    return HIDWORD(`CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr'::`2'::s_DMOtoMFMap[v14]);
  }
  return v11;
}

```

## disassembly

```asm
0x18000676c  push    rbp
0x18000676e  push    rbx
0x18000676f  push    rsi
0x180006770  push    rdi
0x180006771  push    r12
0x180006773  push    r13
0x180006775  push    r14
0x180006777  push    r15
0x180006779  lea     rbp, [rsp-17h]
0x18000677e  sub     rsp, 88h
0x180006785  mov     rax, cs:__security_cookie
0x18000678c  xor     rax, rsp
0x18000678f  mov     [rbp+4Fh+var_50], rax
0x180006793  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18000679a  xor     ebx, ebx
0x18000679c  mov     [rbp+4Fh+var_80], rcx
0x1800067a0  mov     [rbp+4Fh+var_90], rbx
0x1800067a4  mov     r14d, r9d
0x1800067a7  mov     rsi, r8
0x1800067aa  mov     r15d, edx
0x1800067ad  movdqu  [rbp+4Fh+Buf2], xmm0
0x1800067b2  test    r9d, 0FFFFFFFEh
0x1800067b9  jz      short loc_1800067C5
0x1800067bb  mov     eax, 80070057h
0x1800067c0  jmp     loc_180006BD9
0x1800067c5  lea     rdi, [rcx+30h]
0x1800067c9  mov     [rbp+4Fh+var_84], ebx
0x1800067cc  mov     rax, [rdi]
0x1800067cf  lea     r8, [rbp+4Fh+var_88]
0x1800067d3  lea     rdx, [rbp+4Fh+var_84]
0x1800067d7  mov     [rbp+4Fh+var_88], ebx
0x1800067da  mov     rcx, rdi
0x1800067dd  mov     rax, [rax+18h]
0x1800067e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067e6  mov     edx, eax
0x1800067e8  test    eax, eax
0x1800067ea  jns     short loc_18000680E
0x1800067ec  mov     ecx, ebx
0x1800067ee  lea     rax, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x1800067f5  movsxd  r8, ecx
0x1800067f8  cmp     [rax+r8*8], edx
0x1800067fc  jz      loc_180006BD2
0x180006802  inc     ecx
0x180006804  cmp     ecx, 6
0x180006807  jb      short loc_1800067F5
0x180006809  jmp     loc_180006BD7
0x18000680e  mov     r12d, [rbp+4Fh+arg_20]
0x180006812  test    r12d, r12d
0x180006815  mov     eax, [rbp+4Fh+var_88]
0x180006818  cmovz   eax, [rbp+4Fh+var_84]
0x18000681c  cmp     r15d, eax
0x18000681f  jb      short loc_18000682B
0x180006821  mov     eax, 0C00D36B3h
0x180006826  jmp     loc_180006BD9
0x18000682b  mov     r13d, 10h
0x180006831  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180006838  movdqu  [rbp+4Fh+Buf1], xmm0
0x18000683d  test    rsi, rsi
0x180006840  jz      loc_18000695E
0x180006846  mov     rax, [rsi]
0x180006849  lea     r8, [rbp+4Fh+Buf1]
0x18000684d  lea     rdx, MF_MT_SUBTYPE
0x180006854  mov     rcx, rsi
0x180006857  mov     rax, [rax+50h]
0x18000685b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006860  mov     r8d, r13d; Size
0x180006863  lea     rdx, MEDIASUBTYPE_ARGB32; Buf2
0x18000686a  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000686e  call    memcmp_0
0x180006873  test    eax, eax
0x180006875  jz      short loc_1800068D7
0x180006877  mov     r8d, r13d; Size
0x18000687a  lea     rdx, MEDIASUBTYPE_RGB24; Buf2
0x180006881  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x180006885  call    memcmp_0
0x18000688a  test    eax, eax
0x18000688c  jz      short loc_1800068D7
0x18000688e  mov     r8d, r13d; Size
0x180006891  lea     rdx, MEDIASUBTYPE_RGB32; Buf2
0x180006898  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000689c  call    memcmp_0
0x1800068a1  test    eax, eax
0x1800068a3  jz      short loc_1800068D7
0x1800068a5  mov     r8d, r13d; Size
0x1800068a8  lea     rdx, MEDIASUBTYPE_RGB555; Buf2
0x1800068af  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800068b3  call    memcmp_0
0x1800068b8  test    eax, eax
0x1800068ba  jz      short loc_1800068D7
0x1800068bc  mov     r8d, r13d; Size
0x1800068bf  lea     rdx, MEDIASUBTYPE_RGB565; Buf2
0x1800068c6  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800068ca  call    memcmp_0
0x1800068cf  test    eax, eax
0x1800068d1  jnz     loc_18000695E
0x1800068d7  mov     r13b, 1
0x1800068da  mov     rax, [rsi]
0x1800068dd  lea     rdx, [rbp+4Fh+Buf2]
0x1800068e1  mov     rcx, rsi
0x1800068e4  mov     rax, [rax+108h]
0x1800068eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068f0  mov     r8d, 10h; Size
0x1800068f6  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x1800068fa  lea     rcx, MEDIATYPE_Video; Buf1
0x180006901  call    memcmp_0
0x180006906  test    eax, eax
0x180006908  lea     r8, [rbp+4Fh+var_90]
0x18000690c  mov     rax, [rsi]
0x18000690f  lea     rdx, [rbp+4Fh+Buf1]
0x180006913  setz    cl
0x180006916  test    cl, cl
0x180006918  mov     rcx, rsi
0x18000691b  mov     rax, [rax+120h]
0x180006922  jz      loc_180006B14
0x180006928  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000692f  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006939  mov     ebx, eax
0x18000693b  test    eax, eax
0x18000693d  js      loc_1800069DB
0x180006943  mov     rax, [rdi]
0x180006946  mov     r9d, r14d
0x180006949  mov     r8, [rbp+4Fh+var_90]
0x18000694d  mov     edx, r15d
0x180006950  mov     rcx, rdi
0x180006953  test    r12d, r12d
0x180006956  jnz     short loc_1800069A2
0x180006958  mov     rax, [rax+40h]
0x18000695c  jmp     short loc_1800069A6
0x18000695e  mov     rdx, rsi
0x180006961  call    ?ConvertMFRGBFormatToDMORGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(IMFMediaType *)
0x180006966  mov     r13b, bl
0x180006969  test    rsi, rsi
0x18000696c  jnz     loc_1800068DA
0x180006972  mov     rax, [rdi]
0x180006975  or      r14d, 2
0x180006979  xor     r8d, r8d
0x18000697c  mov     r9d, r14d
0x18000697f  mov     edx, r15d
0x180006982  mov     rcx, rdi
0x180006985  test    r12d, r12d
0x180006988  jnz     short loc_180006990
0x18000698a  mov     rax, [rax+40h]
0x18000698e  jmp     short loc_180006994
0x180006990  mov     rax, [rax+48h]
0x180006994  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006999  mov     ebx, eax
0x18000699b  mov     edi, eax
0x18000699d  jmp     loc_180006B9B
0x1800069a2  mov     rax, [rax+48h]
0x1800069a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069ab  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800069b2  mov     r8, [rbp+4Fh+var_90]
0x1800069b6  lea     rdx, [rbp+4Fh+Buf1]
0x1800069ba  mov     ebx, eax
0x1800069bc  mov     rcx, rsi
0x1800069bf  mov     rax, [rsi]
0x1800069c2  movdqu  [rbp+4Fh+Buf1], xmm0
0x1800069c7  mov     rax, [rax+128h]
0x1800069ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d3  test    ebx, ebx
0x1800069d5  jns     loc_180006B7B
0x1800069db  cmp     ebx, 0C00D6D76h
0x1800069e1  jz      loc_180006B94
0x1800069e7  mov     rax, [rsi]
0x1800069ea  lea     r8, [rbp+4Fh+var_90]
0x1800069ee  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x1800069f5  lea     rdx, [rbp+4Fh+Buf1]
0x1800069f9  mov     rcx, rsi
0x1800069fc  mov     rax, [rax+120h]
0x180006a03  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a0d  mov     ebx, eax
0x180006a0f  test    eax, eax
0x180006a11  js      short loc_180006A67
0x180006a13  mov     rax, [rdi]
0x180006a16  mov     r9d, r14d
0x180006a19  mov     r8, [rbp+4Fh+var_90]
0x180006a1d  mov     edx, r15d
0x180006a20  mov     rcx, rdi
0x180006a23  test    r12d, r12d
0x180006a26  jnz     short loc_180006A2E
0x180006a28  mov     rax, [rax+40h]
0x180006a2c  jmp     short loc_180006A32
0x180006a2e  mov     rax, [rax+48h]
0x180006a32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a37  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180006a3e  mov     r8, [rbp+4Fh+var_90]
0x180006a42  lea     rdx, [rbp+4Fh+Buf1]
0x180006a46  mov     ebx, eax
0x180006a48  mov     rcx, rsi
0x180006a4b  mov     rax, [rsi]
0x180006a4e  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006a53  mov     rax, [rax+128h]
0x180006a5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a5f  test    ebx, ebx
0x180006a61  jns     loc_180006B7B
0x180006a67  cmp     ebx, 0C00D6D76h
0x180006a6d  jz      loc_180006B94
0x180006a73  mov     rax, [rsi]
0x180006a76  lea     r8, [rbp+4Fh+var_90]
0x180006a7a  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180006a81  lea     rdx, [rbp+4Fh+Buf1]
0x180006a85  mov     rcx, rsi
0x180006a88  mov     rax, [rax+120h]
0x180006a8f  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a99  mov     ebx, eax
0x180006a9b  test    eax, eax
0x180006a9d  js      short loc_180006AF3
0x180006a9f  mov     rax, [rdi]
0x180006aa2  mov     r9d, r14d
0x180006aa5  mov     r8, [rbp+4Fh+var_90]
0x180006aa9  mov     edx, r15d
0x180006aac  mov     rcx, rdi
0x180006aaf  test    r12d, r12d
0x180006ab2  jnz     short loc_180006ABA
0x180006ab4  mov     rax, [rax+40h]
0x180006ab8  jmp     short loc_180006ABE
0x180006aba  mov     rax, [rax+48h]
0x180006abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac3  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180006aca  mov     r8, [rbp+4Fh+var_90]
0x180006ace  lea     rdx, [rbp+4Fh+Buf1]
0x180006ad2  mov     ebx, eax
0x180006ad4  mov     rcx, rsi
0x180006ad7  mov     rax, [rsi]
0x180006ada  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006adf  mov     rax, [rax+128h]
0x180006ae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aeb  test    ebx, ebx
0x180006aed  jns     loc_180006B7B
0x180006af3  cmp     ebx, 0C00D6D76h
0x180006af9  jz      loc_180006B94
0x180006aff  mov     rax, [rsi]
0x180006b02  lea     r8, [rbp+4Fh+var_90]
0x180006b06  lea     rdx, [rbp+4Fh+Buf1]
0x180006b0a  mov     rcx, rsi
0x180006b0d  mov     rax, [rax+120h]
0x180006b14  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180006b1b  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006b20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b25  mov     ebx, eax
0x180006b27  test    eax, eax
0x180006b29  js      short loc_180006B94
0x180006b2b  mov     rax, [rdi]
0x180006b2e  mov     r9d, r14d
0x180006b31  mov     r8, [rbp+4Fh+var_90]
0x180006b35  mov     edx, r15d
0x180006b38  mov     rcx, rdi
0x180006b3b  test    r12d, r12d
0x180006b3e  jnz     short loc_180006B46
0x180006b40  mov     rax, [rax+40h]
0x180006b44  jmp     short loc_180006B4A
0x180006b46  mov     rax, [rax+48h]
0x180006b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b4f  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180006b56  mov     r8, [rbp+4Fh+var_90]
0x180006b5a  lea     rdx, [rbp+4Fh+Buf1]
0x180006b5e  mov     ebx, eax
0x180006b60  mov     rcx, rsi
0x180006b63  mov     rax, [rsi]
0x180006b66  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006b6b  mov     rax, [rax+128h]
0x180006b72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b77  test    ebx, ebx
0x180006b79  js      short loc_180006B94
0x180006b7b  test    r14b, 1
0x180006b7f  jnz     short loc_180006B94
0x180006b81  mov     rax, [rbp+4Fh+var_80]
0x180006b85  test    r12d, r12d
0x180006b88  jnz     short loc_180006B90
0x180006b8a  mov     [rax+28h], r13b
0x180006b8e  jmp     short loc_180006B94
0x180006b90  mov     [rax+29h], r13b
0x180006b94  mov     edi, ebx
0x180006b96  test    r13b, r13b
0x180006b99  jnz     short loc_180006BA3
0x180006b9b  mov     rdx, rsi
0x180006b9e  call    ?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)
0x180006ba3  cmp     ebx, 1
0x180006ba6  jnz     short loc_180006BB1
0x180006ba8  mov     edi, 0C00D36B4h
0x180006bad  mov     edx, edi
0x180006baf  jmp     short loc_180006BB7
0x180006bb1  mov     edx, edi
0x180006bb3  test    edi, edi
0x180006bb5  jz      short loc_180006BD7
0x180006bb7  xor     ecx, ecx
0x180006bb9  lea     rax, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180006bc0  movsxd  r8, ecx
0x180006bc3  cmp     [rax+r8*8], edi
0x180006bc7  jz      short loc_180006BD2
0x180006bc9  inc     ecx
0x180006bcb  cmp     ecx, 6
0x180006bce  jb      short loc_180006BC0
0x180006bd0  jmp     short loc_180006BD7
0x180006bd2  mov     edx, [rax+r8*8+4]
0x180006bd7  mov     eax, edx
0x180006bd9  mov     rcx, [rbp+4Fh+var_50]
  ... truncated ...
```
