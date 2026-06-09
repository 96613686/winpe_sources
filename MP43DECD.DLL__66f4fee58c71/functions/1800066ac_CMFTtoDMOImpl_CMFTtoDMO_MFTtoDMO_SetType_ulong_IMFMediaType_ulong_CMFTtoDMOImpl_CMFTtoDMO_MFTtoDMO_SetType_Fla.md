# CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType(ulong,IMFMediaType *,ulong,CMFTtoDMOImpl<CMFTtoDMO>::MFTtoDMO_SetType_Flag)

- ea: `0x1800066ac`
- end: `0x180006b39`
- name: `?MFTtoDMO_SetType@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAJKPEAUIMFMediaType@@KW4MFTtoDMO_SetType_Flag@1@@Z`
- size: `1165`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x1800065d0`
- `0x1800065f0`

## callees

- `0x180001880`
- `0x18000324c`
- `0x1800033c0`
- `0x1800066ac`
- `0x180020f39`
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
0x1800066ac  push    rbp
0x1800066ae  push    rbx
0x1800066af  push    rsi
0x1800066b0  push    rdi
0x1800066b1  push    r12
0x1800066b3  push    r13
0x1800066b5  push    r14
0x1800066b7  push    r15
0x1800066b9  lea     rbp, [rsp-17h]
0x1800066be  sub     rsp, 88h
0x1800066c5  mov     rax, cs:__security_cookie
0x1800066cc  xor     rax, rsp
0x1800066cf  mov     [rbp+4Fh+var_50], rax
0x1800066d3  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x1800066da  xor     ebx, ebx
0x1800066dc  mov     [rbp+4Fh+var_80], rcx
0x1800066e0  mov     [rbp+4Fh+var_90], rbx
0x1800066e4  mov     r14d, r9d
0x1800066e7  mov     rsi, r8
0x1800066ea  mov     r15d, edx
0x1800066ed  movdqu  [rbp+4Fh+Buf2], xmm0
0x1800066f2  test    r9d, 0FFFFFFFEh
0x1800066f9  jz      short loc_180006705
0x1800066fb  mov     eax, 80070057h
0x180006700  jmp     loc_180006B19
0x180006705  lea     rdi, [rcx+30h]
0x180006709  mov     [rbp+4Fh+var_84], ebx
0x18000670c  mov     rax, [rdi]
0x18000670f  lea     r8, [rbp+4Fh+var_88]
0x180006713  lea     rdx, [rbp+4Fh+var_84]
0x180006717  mov     [rbp+4Fh+var_88], ebx
0x18000671a  mov     rcx, rdi
0x18000671d  mov     rax, [rax+18h]
0x180006721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006726  mov     edx, eax
0x180006728  test    eax, eax
0x18000672a  jns     short loc_18000674E
0x18000672c  mov     ecx, ebx
0x18000672e  lea     rax, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180006735  movsxd  r8, ecx
0x180006738  cmp     [rax+r8*8], edx
0x18000673c  jz      loc_180006B12
0x180006742  inc     ecx
0x180006744  cmp     ecx, 6
0x180006747  jb      short loc_180006735
0x180006749  jmp     loc_180006B17
0x18000674e  mov     r12d, [rbp+4Fh+arg_20]
0x180006752  test    r12d, r12d
0x180006755  mov     eax, [rbp+4Fh+var_88]
0x180006758  cmovz   eax, [rbp+4Fh+var_84]
0x18000675c  cmp     r15d, eax
0x18000675f  jb      short loc_18000676B
0x180006761  mov     eax, 0C00D36B3h
0x180006766  jmp     loc_180006B19
0x18000676b  mov     r13d, 10h
0x180006771  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x180006778  movdqu  [rbp+4Fh+Buf1], xmm0
0x18000677d  test    rsi, rsi
0x180006780  jz      loc_18000689E
0x180006786  mov     rax, [rsi]
0x180006789  lea     r8, [rbp+4Fh+Buf1]
0x18000678d  lea     rdx, MF_MT_SUBTYPE
0x180006794  mov     rcx, rsi
0x180006797  mov     rax, [rax+50h]
0x18000679b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a0  mov     r8d, r13d; Size
0x1800067a3  lea     rdx, MEDIASUBTYPE_ARGB32; Buf2
0x1800067aa  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800067ae  call    memcmp_0
0x1800067b3  test    eax, eax
0x1800067b5  jz      short loc_180006817
0x1800067b7  mov     r8d, r13d; Size
0x1800067ba  lea     rdx, MEDIASUBTYPE_RGB24; Buf2
0x1800067c1  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800067c5  call    memcmp_0
0x1800067ca  test    eax, eax
0x1800067cc  jz      short loc_180006817
0x1800067ce  mov     r8d, r13d; Size
0x1800067d1  lea     rdx, MEDIASUBTYPE_RGB32; Buf2
0x1800067d8  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800067dc  call    memcmp_0
0x1800067e1  test    eax, eax
0x1800067e3  jz      short loc_180006817
0x1800067e5  mov     r8d, r13d; Size
0x1800067e8  lea     rdx, MEDIASUBTYPE_RGB555; Buf2
0x1800067ef  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x1800067f3  call    memcmp_0
0x1800067f8  test    eax, eax
0x1800067fa  jz      short loc_180006817
0x1800067fc  mov     r8d, r13d; Size
0x1800067ff  lea     rdx, MEDIASUBTYPE_RGB565; Buf2
0x180006806  lea     rcx, [rbp+4Fh+Buf1]; Buf1
0x18000680a  call    memcmp_0
0x18000680f  test    eax, eax
0x180006811  jnz     loc_18000689E
0x180006817  mov     r13b, 1
0x18000681a  mov     rax, [rsi]
0x18000681d  lea     rdx, [rbp+4Fh+Buf2]
0x180006821  mov     rcx, rsi
0x180006824  mov     rax, [rax+108h]
0x18000682b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006830  mov     r8d, 10h; Size
0x180006836  lea     rdx, [rbp+4Fh+Buf2]; Buf2
0x18000683a  lea     rcx, MEDIATYPE_Video; Buf1
0x180006841  call    memcmp_0
0x180006846  test    eax, eax
0x180006848  lea     r8, [rbp+4Fh+var_90]
0x18000684c  mov     rax, [rsi]
0x18000684f  lea     rdx, [rbp+4Fh+Buf1]
0x180006853  setz    cl
0x180006856  test    cl, cl
0x180006858  mov     rcx, rsi
0x18000685b  mov     rax, [rax+120h]
0x180006862  jz      loc_180006A54
0x180006868  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x18000686f  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006874  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006879  mov     ebx, eax
0x18000687b  test    eax, eax
0x18000687d  js      loc_18000691B
0x180006883  mov     rax, [rdi]
0x180006886  mov     r9d, r14d
0x180006889  mov     r8, [rbp+4Fh+var_90]
0x18000688d  mov     edx, r15d
0x180006890  mov     rcx, rdi
0x180006893  test    r12d, r12d
0x180006896  jnz     short loc_1800068E2
0x180006898  mov     rax, [rax+40h]
0x18000689c  jmp     short loc_1800068E6
0x18000689e  mov     rdx, rsi
0x1800068a1  call    ?ConvertMFRGBFormatToDMORGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertMFRGBFormatToDMORGBFormat(IMFMediaType *)
0x1800068a6  mov     r13b, bl
0x1800068a9  test    rsi, rsi
0x1800068ac  jnz     loc_18000681A
0x1800068b2  mov     rax, [rdi]
0x1800068b5  or      r14d, 2
0x1800068b9  xor     r8d, r8d
0x1800068bc  mov     r9d, r14d
0x1800068bf  mov     edx, r15d
0x1800068c2  mov     rcx, rdi
0x1800068c5  test    r12d, r12d
0x1800068c8  jnz     short loc_1800068D0
0x1800068ca  mov     rax, [rax+40h]
0x1800068ce  jmp     short loc_1800068D4
0x1800068d0  mov     rax, [rax+48h]
0x1800068d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068d9  mov     ebx, eax
0x1800068db  mov     edi, eax
0x1800068dd  jmp     loc_180006ADB
0x1800068e2  mov     rax, [rax+48h]
0x1800068e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068eb  movups  xmm0, xmmword ptr cs:FORMAT_MFVideoFormat.Data1
0x1800068f2  mov     r8, [rbp+4Fh+var_90]
0x1800068f6  lea     rdx, [rbp+4Fh+Buf1]
0x1800068fa  mov     ebx, eax
0x1800068fc  mov     rcx, rsi
0x1800068ff  mov     rax, [rsi]
0x180006902  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006907  mov     rax, [rax+128h]
0x18000690e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006913  test    ebx, ebx
0x180006915  jns     loc_180006ABB
0x18000691b  cmp     ebx, 0C00D6D76h
0x180006921  jz      loc_180006AD4
0x180006927  mov     rax, [rsi]
0x18000692a  lea     r8, [rbp+4Fh+var_90]
0x18000692e  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x180006935  lea     rdx, [rbp+4Fh+Buf1]
0x180006939  mov     rcx, rsi
0x18000693c  mov     rax, [rax+120h]
0x180006943  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006948  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000694d  mov     ebx, eax
0x18000694f  test    eax, eax
0x180006951  js      short loc_1800069A7
0x180006953  mov     rax, [rdi]
0x180006956  mov     r9d, r14d
0x180006959  mov     r8, [rbp+4Fh+var_90]
0x18000695d  mov     edx, r15d
0x180006960  mov     rcx, rdi
0x180006963  test    r12d, r12d
0x180006966  jnz     short loc_18000696E
0x180006968  mov     rax, [rax+40h]
0x18000696c  jmp     short loc_180006972
0x18000696e  mov     rax, [rax+48h]
0x180006972  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006977  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo2.Data1
0x18000697e  mov     r8, [rbp+4Fh+var_90]
0x180006982  lea     rdx, [rbp+4Fh+Buf1]
0x180006986  mov     ebx, eax
0x180006988  mov     rcx, rsi
0x18000698b  mov     rax, [rsi]
0x18000698e  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006993  mov     rax, [rax+128h]
0x18000699a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000699f  test    ebx, ebx
0x1800069a1  jns     loc_180006ABB
0x1800069a7  cmp     ebx, 0C00D6D76h
0x1800069ad  jz      loc_180006AD4
0x1800069b3  mov     rax, [rsi]
0x1800069b6  lea     r8, [rbp+4Fh+var_90]
0x1800069ba  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x1800069c1  lea     rdx, [rbp+4Fh+Buf1]
0x1800069c5  mov     rcx, rsi
0x1800069c8  mov     rax, [rax+120h]
0x1800069cf  movdqu  [rbp+4Fh+Buf1], xmm0
0x1800069d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069d9  mov     ebx, eax
0x1800069db  test    eax, eax
0x1800069dd  js      short loc_180006A33
0x1800069df  mov     rax, [rdi]
0x1800069e2  mov     r9d, r14d
0x1800069e5  mov     r8, [rbp+4Fh+var_90]
0x1800069e9  mov     edx, r15d
0x1800069ec  mov     rcx, rdi
0x1800069ef  test    r12d, r12d
0x1800069f2  jnz     short loc_1800069FA
0x1800069f4  mov     rax, [rax+40h]
0x1800069f8  jmp     short loc_1800069FE
0x1800069fa  mov     rax, [rax+48h]
0x1800069fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a03  movups  xmm0, xmmword ptr cs:FORMAT_VideoInfo.Data1
0x180006a0a  mov     r8, [rbp+4Fh+var_90]
0x180006a0e  lea     rdx, [rbp+4Fh+Buf1]
0x180006a12  mov     ebx, eax
0x180006a14  mov     rcx, rsi
0x180006a17  mov     rax, [rsi]
0x180006a1a  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006a1f  mov     rax, [rax+128h]
0x180006a26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a2b  test    ebx, ebx
0x180006a2d  jns     loc_180006ABB
0x180006a33  cmp     ebx, 0C00D6D76h
0x180006a39  jz      loc_180006AD4
0x180006a3f  mov     rax, [rsi]
0x180006a42  lea     r8, [rbp+4Fh+var_90]
0x180006a46  lea     rdx, [rbp+4Fh+Buf1]
0x180006a4a  mov     rcx, rsi
0x180006a4d  mov     rax, [rax+120h]
0x180006a54  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180006a5b  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006a60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a65  mov     ebx, eax
0x180006a67  test    eax, eax
0x180006a69  js      short loc_180006AD4
0x180006a6b  mov     rax, [rdi]
0x180006a6e  mov     r9d, r14d
0x180006a71  mov     r8, [rbp+4Fh+var_90]
0x180006a75  mov     edx, r15d
0x180006a78  mov     rcx, rdi
0x180006a7b  test    r12d, r12d
0x180006a7e  jnz     short loc_180006A86
0x180006a80  mov     rax, [rax+40h]
0x180006a84  jmp     short loc_180006A8A
0x180006a86  mov     rax, [rax+48h]
0x180006a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a8f  movups  xmm0, xmmword ptr cs:AM_MEDIA_TYPE_REPRESENTATION.Data1
0x180006a96  mov     r8, [rbp+4Fh+var_90]
0x180006a9a  lea     rdx, [rbp+4Fh+Buf1]
0x180006a9e  mov     ebx, eax
0x180006aa0  mov     rcx, rsi
0x180006aa3  mov     rax, [rsi]
0x180006aa6  movdqu  [rbp+4Fh+Buf1], xmm0
0x180006aab  mov     rax, [rax+128h]
0x180006ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab7  test    ebx, ebx
0x180006ab9  js      short loc_180006AD4
0x180006abb  test    r14b, 1
0x180006abf  jnz     short loc_180006AD4
0x180006ac1  mov     rax, [rbp+4Fh+var_80]
0x180006ac5  test    r12d, r12d
0x180006ac8  jnz     short loc_180006AD0
0x180006aca  mov     [rax+28h], r13b
0x180006ace  jmp     short loc_180006AD4
0x180006ad0  mov     [rax+29h], r13b
0x180006ad4  mov     edi, ebx
0x180006ad6  test    r13b, r13b
0x180006ad9  jnz     short loc_180006AE3
0x180006adb  mov     rdx, rsi
0x180006ade  call    ?ConvertDMORGBFormatToMFRGBFormat@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@AEAAXPEAUIMFMediaType@@@Z; CMFTtoDMOImpl<CMFTtoDMO>::ConvertDMORGBFormatToMFRGBFormat(IMFMediaType *)
0x180006ae3  cmp     ebx, 1
0x180006ae6  jnz     short loc_180006AF1
0x180006ae8  mov     edi, 0C00D36B4h
0x180006aed  mov     edx, edi
0x180006aef  jmp     short loc_180006AF7
0x180006af1  mov     edx, edi
0x180006af3  test    edi, edi
0x180006af5  jz      short loc_180006B17
0x180006af7  xor     ecx, ecx
0x180006af9  lea     rax, ?s_DMOtoMFMap@?1??DMOErrToMFErr@?$CMFTtoDMOImpl@VCMFTtoDMO@@@@IEAAJJ@Z@4QBU_DMOtoMFMap@?1??12@IEAAJJ@Z@B; `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::_DMOtoMFMap const near * const `CMFTtoDMOImpl<CMFTtoDMO>::DMOErrToMFErr(long)'::`2'::s_DMOtoMFMap
0x180006b00  movsxd  r8, ecx
0x180006b03  cmp     [rax+r8*8], edi
0x180006b07  jz      short loc_180006B12
0x180006b09  inc     ecx
0x180006b0b  cmp     ecx, 6
0x180006b0e  jb      short loc_180006B00
0x180006b10  jmp     short loc_180006B17
0x180006b12  mov     edx, [rax+r8*8+4]
0x180006b17  mov     eax, edx
0x180006b19  mov     rcx, [rbp+4Fh+var_50]
  ... truncated ...
```
