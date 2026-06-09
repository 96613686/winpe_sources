# CMetadataXMPReaderWriter::HrLoadEx(CExternalStream *,_GUID const *,ulong)

- ea: `0x18000a3b0`
- end: `0x18000ab53`
- name: `?HrLoadEx@CMetadataXMPReaderWriter@@UEAAJPEAVCExternalStream@@PEBU_GUID@@K@Z`
- size: `1955`
- prototype: `__int64 __fastcall(CMetadataXMPReaderWriter *this, struct CExternalStream *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x180009990`
- `0x18000a3b0`
- `0x18000ab60`
- `0x1800171c4`
- `0x1800215e8`
- `0x180021a30`
- `0x180022348`
- `0x180033010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000a407`
- `OLEAUT32!__imp_VariantInit` at `0x18000a693`
- `OLEAUT32!__imp_VariantInit` at `0x18000a407`
- `OLEAUT32!__imp_VariantInit` at `0x18000a693`
- `OLEAUT32!__imp_VariantClear` at `0x18000a8bf`
- `OLEAUT32!__imp_VariantClear` at `0x18000a8bf`

## pseudocode

```c
__int64 __fastcall CMetadataXMPReaderWriter::HrLoadEx(
        CMetadataXMPReaderWriter *this,
        struct CExternalStream *a2,
        const struct _GUID *a3)
{
  _DWORD *v4; // r15
  unsigned int v6; // edi
  char *v7; // rdx
  unsigned int v8; // ebx
  void (__fastcall ***v9)(_QWORD, __int64); // rcx
  __int64 v10; // rcx
  int v11; // esi
  bool v12; // zf
  int v13; // eax
  unsigned int v14; // edi
  unsigned int i; // ebx
  void (__fastcall ***v16)(_QWORD, __int64); // rcx
  __int64 v17; // rcx
  int v18; // eax
  int v20; // ecx
  unsigned int v21; // eax
  unsigned int *v22; // r12
  __int64 v23; // rbx
  int v24; // edi
  unsigned int v25; // edi
  char *v26; // r12
  __int64 v27; // rsi
  _DWORD *v28; // rax
  char *v29; // r12
  __int64 v30; // rcx
  int v31; // eax
  __int64 (__fastcall *v32)(__int64 *, const wchar_t *, VARIANTARG *); // rax
  LONGLONG v33; // rdx
  __int64 v34; // rax
  int v35; // esi
  int v36; // eax
  __int64 *v37; // rbx
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rbx
  __int64 v41; // rcx
  __int16 v42; // [rsp+30h] [rbp-D0h] BYREF
  __int64 *v43; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int v44; // [rsp+40h] [rbp-C0h] BYREF
  int v45; // [rsp+44h] [rbp-BCh]
  int v46; // [rsp+48h] [rbp-B8h]
  __int64 v47; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v48; // [rsp+58h] [rbp-A8h]
  unsigned int *v49; // [rsp+60h] [rbp-A0h]
  char *v50; // [rsp+68h] [rbp-98h]
  VARIANTARG v51; // [rsp+70h] [rbp-90h] BYREF
  VARIANTARG pvarg; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v53; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v54[16]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v55; // [rsp+D0h] [rbp-30h]

  v42 = 0;
  v43 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  v47 = 0;
  v4 = 0;
  VariantInit(&pvarg);
  v6 = *((_DWORD *)this + 72);
  v7 = (char *)this + 264;
  v50 = (char *)this + 264;
  v8 = 0;
  if ( v6 )
  {
    do
    {
      v9 = *(void (__fastcall ****)(_QWORD, __int64))(*(_QWORD *)v7 + 8LL * v8);
      if ( v9 )
      {
        (**v9)(v9, 1);
        v7 = (char *)this + 264;
      }
      ++v8;
    }
    while ( v8 < v6 );
  }
  else
  {
    v50 = (char *)this + 264;
  }
  *((_DWORD *)v7 + 6) = 0;
  v10 = *((_QWORD *)this + 31);
  if ( v10 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    *((_QWORD *)this + 31) = 0;
  }
  *((_QWORD *)this + 32) = 0;
  v11 = CMetadataRDFReaderWriter::ClearFields(this);
  if ( v11 < 0 )
  {
    if ( !g_doStackCaptures )
      goto LABEL_17;
    DoStackCapture(v11);
    v12 = g_doStackCaptures == 0;
    goto LABEL_16;
  }
  if ( !a2 )
    goto LABEL_90;
  v23 = *((unsigned int *)this + 34);
  v24 = *((_DWORD *)this + 32);
  v44 = 0;
  v25 = v24 - v23;
  v26 = (char *)a2 + 16;
  if ( (int)CBOMStream::DetectXMPEncoding((struct CExternalStream *)((char *)a2 + 16), &v44) < 0 )
  {
    v46 = 5;
    v49 = (unsigned int *)&unk_180037B30;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 112LL))((char *)a2 + 16);
    v13 = (*(__int64 (__fastcall **)(struct CExternalStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 104LL))(
            a2,
            v23,
            0,
            0);
    v11 = v13;
    if ( v13 < 0 && g_doStackCaptures )
      DoStackCapture(v13);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v26 + 120LL))((char *)a2 + 16);
    if ( v11 < 0 )
      goto LABEL_15;
    v21 = 5;
    v22 = (unsigned int *)&unk_180037B30;
  }
  else
  {
    v22 = &v44;
    v21 = 1;
    v49 = &v44;
    v46 = 1;
  }
  v27 = 0;
  while ( 1 )
  {
    v4 = 0;
    v45 = v27;
    if ( (unsigned int)v27 >= v21 )
      goto LABEL_76;
    memset(&v51, 0, sizeof(v51));
    VariantInit(&v51);
    v28 = operator new(0x50u);
    v4 = v28;
    if ( !v28 )
    {
      v11 = -2147024882;
      if ( g_doStackCaptures )
        DoStackCapture(-2147024882);
      v4 = 0;
      goto LABEL_17;
    }
    v28[2] = 0;
    *(_QWORD *)v28 = &CMILCOMBase::`vftable';
    _InterlockedIncrement(&g_cActiveObjects);
    *((_QWORD *)v28 + 3) = 0;
    *((_QWORD *)v28 + 7) = 0;
    *((_QWORD *)v28 + 2) = &CBOMStream::`vftable'{for `IStream'};
    *((_QWORD *)v28 + 6) = 0;
    *((_QWORD *)v28 + 4) = 0;
    v28[10] = 0;
    *(_QWORD *)v28 = &CBOMStream::`vftable'{for `CMILCOMBase'};
    CMILCOMBase::InternalAddRef((CMILCOMBase *)v28);
    v48 = v22[v27];
    v29 = (char *)a2 + 16;
    *((_BYTE *)v4 + 68) = 1;
    memset_0(v54, 0, 0x50u);
    v11 = (*(__int64 (__fastcall **)(char *, _BYTE *, __int64))(*((_QWORD *)a2 + 2) + 96LL))((char *)a2 + 16, v54, 1);
    if ( v11 < 0 )
    {
      if ( g_doStackCaptures )
LABEL_46:
        DoStackCapture(v11);
LABEL_54:
      if ( g_doStackCaptures )
        DoStackCapture(v11);
      goto LABEL_17;
    }
    *((_QWORD *)v4 + 7) = v55;
    *((_QWORD *)v4 + 6) = 0;
    v30 = *((_QWORD *)v4 + 3);
    if ( v30 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
    *((_QWORD *)v4 + 3) = v29;
    if ( a2 != (struct CExternalStream *)-16LL )
      (*(void (__fastcall **)(char *))(*(_QWORD *)v29 + 8LL))((char *)a2 + 16);
    v11 = (*(__int64 (__fastcall **)(_DWORD *, char *, _QWORD))(*(_QWORD *)v4 + 40LL))(v4, (char *)a2 + 16, v48);
    if ( v11 < 0 && g_doStackCaptures )
      goto LABEL_46;
    if ( v11 < 0 )
      goto LABEL_54;
    v31 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64 **))(*(_QWORD *)this + 264LL))(this, &v43);
    v11 = v31;
    if ( v31 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_17;
LABEL_35:
      v20 = v31;
      goto LABEL_36;
    }
    v53.pRecInfo = pvarg.pRecInfo;
    pvarg.vt = 11;
    pvarg.iVal = -1;
    v32 = *(__int64 (__fastcall **)(__int64 *, const wchar_t *, VARIANTARG *))(*v43 + 640);
    *(_OWORD *)&v53.vt = *(_OWORD *)&pvarg.vt;
    v31 = v32(v43, L"ProhibitDTD", &v53);
    v11 = v31;
    if ( v31 < 0 )
      break;
    v51.vt = 13;
    v33 = (unsigned __int64)(v4 + 4) & ((unsigned __int128)-(__int128)(unsigned __int64)v4 >> 64);
    v51.llVal = v33;
    if ( v33 )
      (*(void (__fastcall **)(LONGLONG))(*(_QWORD *)v33 + 8LL))(v33);
    v34 = *v43;
    v53 = v51;
    v35 = (*(__int64 (__fastcall **)(__int64 *, VARIANTARG *, __int16 *))(v34 + 464))(v43, &v53, &v42);
    VariantClear(&v51);
    if ( !v35 && v42 == -1 )
    {
      *((_DWORD *)this + 36) = v4[16];
      (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
      v4 = 0;
LABEL_76:
      if ( v43 )
      {
        v31 = (*(__int64 (__fastcall **)(CMetadataXMPReaderWriter *, __int64 *, __int64 *))(*(_QWORD *)this + 360LL))(
                this,
                v43,
                &v47);
        v11 = v31;
        if ( v31 < 0 )
        {
          if ( g_doStackCaptures )
            goto LABEL_35;
          goto LABEL_17;
        }
        v37 = v43;
        *((_QWORD *)this + 22) = v25;
        v38 = *((_QWORD *)this + 23);
        if ( v38 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
        *((_QWORD *)this + 23) = v37;
        if ( v37 )
          (*(void (__fastcall **)(__int64 *))(*v37 + 8))(v37);
        v39 = *((_QWORD *)this + 24);
        v40 = v47;
        if ( v39 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
        *((_QWORD *)this + 24) = v40;
        if ( v40 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 8LL))(v40);
        v41 = *((_QWORD *)this + 31);
        if ( v41 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
          *((_QWORD *)this + 31) = 0;
        }
LABEL_90:
        (*(void (__fastcall **)(CMetadataXMPReaderWriter *, _QWORD))(*(_QWORD *)this + 128LL))(this, 0);
        goto LABEL_17;
      }
      v11 = -2147024809;
LABEL_15:
      v12 = g_doStackCaptures == 0;
LABEL_16:
      if ( v12 )
        goto LABEL_17;
LABEL_34:
      v20 = v11;
LABEL_36:
      DoStackCapture(v20);
      goto LABEL_17;
    }
    (*(void (__fastcall **)(char *))(*((_QWORD *)a2 + 2) + 112LL))((char *)a2 + 16);
    v36 = (*(__int64 (__fastcall **)(struct CExternalStream *, __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 104LL))(
            a2,
            v23,
            0,
            0);
    v11 = v36;
    if ( v36 < 0 && g_doStackCaptures )
      DoStackCapture(v36);
    (*(void (__fastcall **)(char *))(*((_QWORD *)a2 + 2) + 120LL))((char *)a2 + 16);
    if ( v11 < 0 )
    {
      if ( !g_doStackCaptures )
        goto LABEL_17;
      goto LABEL_34;
    }
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
    if ( v43 )
    {
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
      v43 = 0;
    }
    v21 = v46;
    v27 = (unsigned int)(v45 + 1);
    v22 = v49;
  }
  if ( g_doStackCaptures )
    goto LABEL_35;
LABEL_17:
  if ( v43 )
  {
    (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    v43 = 0;
  }
  if ( v47 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
    v47 = 0;
  }
  if ( v4 )
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v4 + 16LL))(v4);
  if ( v11 < 0 )
  {
    v14 = *((_DWORD *)this + 72);
    for ( i = 0; i < v14; ++i )
    {
      v16 = *(void (__fastcall ****)(_QWORD, __int64))(*((_QWORD *)this + 33) + 8LL * i);
      if ( v16 )
        (**v16)(v16, 1);
    }
    *((_DWORD *)v50 + 6) = 0;
    v17 = *((_QWORD *)this + 31);
    if ( v17 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      *((_QWORD *)this + 31) = 0;
    }
    *((_QWORD *)this + 32) = 0;
    v18 = CMetadataRDFReaderWriter::ClearFields(this);
    if ( v18 < 0 && g_doStackCaptures )
      DoStackCapture(v18);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18000a3b0  mov     [rsp-8+arg_10], rbx
0x18000a3b5  push    rbp
0x18000a3b6  push    rsi
0x18000a3b7  push    rdi
0x18000a3b8  push    r12
0x18000a3ba  push    r13
0x18000a3bc  push    r14
0x18000a3be  push    r15
0x18000a3c0  lea     rbp, [rsp-20h]
0x18000a3c5  sub     rsp, 120h
0x18000a3cc  mov     rax, cs:__security_cookie
0x18000a3d3  xor     rax, rsp
0x18000a3d6  mov     [rbp+50h+var_40], rax
0x18000a3da  xor     r12d, r12d
0x18000a3dd  mov     r14, rcx
0x18000a3e0  xorps   xmm0, xmm0
0x18000a3e3  mov     [rsp+150h+var_120], r12w
0x18000a3e9  xor     eax, eax
0x18000a3eb  mov     [rsp+150h+var_118], r12
0x18000a3f0  lea     rcx, [rbp+50h+pvarg]; pvarg
0x18000a3f4  mov     qword ptr [rbp+50h+pvarg+10h], rax
0x18000a3f8  movups  xmmword ptr [rbp+50h+pvarg], xmm0
0x18000a3fc  mov     [rsp+150h+var_100], r12
0x18000a401  mov     r15d, r12d
0x18000a404  mov     r13, rdx
0x18000a407  call    cs:__imp_VariantInit
0x18000a40d  mov     edi, [r14+120h]
0x18000a414  lea     rdx, [r14+108h]
0x18000a41b  mov     [rsp+150h+var_E8], rdx
0x18000a420  mov     ebx, r12d
0x18000a423  test    edi, edi
0x18000a425  jz      short loc_18000A49E
0x18000a427  mov     rax, [rdx]
0x18000a42a  mov     ecx, ebx
0x18000a42c  mov     rcx, [rax+rcx*8]
0x18000a430  test    rcx, rcx
0x18000a433  jz      short loc_18000A44C
0x18000a435  mov     rax, [rcx]
0x18000a438  mov     edx, 1
0x18000a43d  mov     rax, [rax]
0x18000a440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a445  lea     rdx, [r14+108h]
0x18000a44c  inc     ebx
0x18000a44e  cmp     ebx, edi
0x18000a450  jb      short loc_18000A427
0x18000a452  mov     [rdx+18h], r12d
0x18000a456  mov     rcx, [r14+0F8h]
0x18000a45d  test    rcx, rcx
0x18000a460  jnz     loc_18000AAE9
0x18000a466  mov     rcx, r14; this
0x18000a469  mov     [r14+100h], r12
0x18000a470  call    ?ClearFields@CMetadataRDFReaderWriter@@MEAAJXZ; CMetadataRDFReaderWriter::ClearFields(void)
0x18000a475  mov     esi, eax
0x18000a477  test    eax, eax
0x18000a479  jns     loc_18000A625
0x18000a47f  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000a485  test    eax, eax
0x18000a487  jz      loc_18000A51D
0x18000a48d  mov     ecx, esi; int
0x18000a48f  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a494  mov     eax, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18000a49a  test    eax, eax
0x18000a49c  jmp     short loc_18000A517
0x18000a49e  mov     [rsp+150h+var_E8], rdx
0x18000a4a3  jmp     short loc_18000A452
0x18000a4a5  lea     rax, unk_180037B30
0x18000a4ac  mov     [rsp+150h+var_108], 5
0x18000a4b4  mov     [rsp+150h+var_F0], rax
0x18000a4b9  mov     rcx, r12
0x18000a4bc  mov     rax, [r12]
0x18000a4c0  mov     rax, [rax+70h]
0x18000a4c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4c9  mov     rax, [r13+0]
0x18000a4cd  xor     r9d, r9d
0x18000a4d0  xor     r8d, r8d
0x18000a4d3  mov     rdx, rbx
0x18000a4d6  mov     rcx, r13
0x18000a4d9  mov     rax, [rax+68h]
0x18000a4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e2  mov     esi, eax
0x18000a4e4  test    eax, eax
0x18000a4e6  jns     short loc_18000A4F5
0x18000a4e8  cmp     cs:?g_doStackCaptures@@3HA, r15d; int g_doStackCaptures
0x18000a4ef  jnz     loc_18000AAB1
0x18000a4f5  mov     rax, [r12]
0x18000a4f9  mov     rcx, r12
0x18000a4fc  mov     rax, [rax+78h]
0x18000a500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a505  xor     r12d, r12d
0x18000a508  test    esi, esi
0x18000a50a  jns     loc_18000A617
0x18000a510  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000a517  jnz     loc_18000A607
0x18000a51d  mov     rcx, [rsp+150h+var_118]
0x18000a522  test    rcx, rcx
0x18000a525  jz      short loc_18000A538
0x18000a527  mov     rax, [rcx]
0x18000a52a  mov     rax, [rax+10h]
0x18000a52e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a533  mov     [rsp+150h+var_118], r12
0x18000a538  mov     rcx, [rsp+150h+var_100]
0x18000a53d  test    rcx, rcx
0x18000a540  jz      short loc_18000A553
0x18000a542  mov     rax, [rcx]
0x18000a545  mov     rax, [rax+10h]
0x18000a549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54e  mov     [rsp+150h+var_100], r12
0x18000a553  test    r15, r15
0x18000a556  jz      short loc_18000A567
0x18000a558  mov     rax, [r15]
0x18000a55b  mov     rcx, r15
0x18000a55e  mov     rax, [rax+10h]
0x18000a562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a567  test    esi, esi
0x18000a569  jns     short loc_18000A5DE
0x18000a56b  mov     edi, [r14+120h]
0x18000a572  mov     ebx, r12d
0x18000a575  test    edi, edi
0x18000a577  jz      short loc_18000A5A1
0x18000a579  mov     rax, [r14+108h]
0x18000a580  mov     ecx, ebx
0x18000a582  mov     rcx, [rax+rcx*8]
0x18000a586  test    rcx, rcx
0x18000a589  jz      short loc_18000A59B
0x18000a58b  mov     rax, [rcx]
0x18000a58e  mov     edx, 1
0x18000a593  mov     rax, [rax]
0x18000a596  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a59b  inc     ebx
0x18000a59d  cmp     ebx, edi
0x18000a59f  jb      short loc_18000A579
0x18000a5a1  mov     rax, [rsp+150h+var_E8]
0x18000a5a6  mov     [rax+18h], r12d
0x18000a5aa  mov     rcx, [r14+0F8h]
0x18000a5b1  test    rcx, rcx
0x18000a5b4  jnz     loc_18000AB3B
0x18000a5ba  mov     rcx, r14; this
0x18000a5bd  mov     qword ptr [r14+100h], 0
0x18000a5c8  call    ?ClearFields@CMetadataRDFReaderWriter@@MEAAJXZ; CMetadataRDFReaderWriter::ClearFields(void)
0x18000a5cd  test    eax, eax
0x18000a5cf  jns     short loc_18000A5DE
0x18000a5d1  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000a5d8  jnz     loc_18000AABD
0x18000a5de  mov     eax, esi
0x18000a5e0  mov     rcx, [rbp+50h+var_40]
0x18000a5e4  xor     rcx, rsp; StackCookie
0x18000a5e7  call    __security_check_cookie
0x18000a5ec  mov     rbx, [rsp+150h+arg_10]
0x18000a5f4  add     rsp, 120h
0x18000a5fb  pop     r15
0x18000a5fd  pop     r14
0x18000a5ff  pop     r13
0x18000a601  pop     r12
0x18000a603  pop     rdi
0x18000a604  pop     rsi
0x18000a605  pop     rbp
0x18000a606  retn
0x18000a607  mov     ecx, esi
0x18000a609  jmp     short loc_18000A60D
0x18000a60b  mov     ecx, eax; int
0x18000a60d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a612  jmp     loc_18000A51D
0x18000a617  mov     eax, 5
0x18000a61c  lea     r12, unk_180037B30
0x18000a623  jmp     short loc_18000A66F
0x18000a625  test    r13, r13
0x18000a628  jz      loc_18000AA57
0x18000a62e  mov     ebx, [r14+88h]
0x18000a635  lea     rdx, [rsp+150h+var_110]; unsigned int *
0x18000a63a  mov     edi, [r14+80h]
0x18000a641  mov     [rsp+150h+var_110], r12d
0x18000a646  sub     edi, ebx
0x18000a648  lea     r12, [r13+10h]
0x18000a64c  mov     rcx, r12; struct IStream *
0x18000a64f  call    ?DetectXMPEncoding@CBOMStream@@SAJPEAUIStream@@PEAK@Z; CBOMStream::DetectXMPEncoding(IStream *,ulong *)
0x18000a654  test    eax, eax
0x18000a656  js      loc_18000A4A5
0x18000a65c  lea     r12, [rsp+150h+var_110]
0x18000a661  mov     eax, 1
0x18000a666  mov     [rsp+150h+var_F0], r12
0x18000a66b  mov     [rsp+150h+var_108], eax
0x18000a66f  xor     esi, esi
0x18000a671  xor     r15d, r15d
0x18000a674  mov     [rsp+150h+var_10C], esi
0x18000a678  cmp     esi, eax
0x18000a67a  jnb     loc_18000AA70
0x18000a680  xorps   xmm0, xmm0
0x18000a683  lea     rcx, [rsp+150h+var_E0]; pvarg
0x18000a688  xor     eax, eax
0x18000a68a  movups  xmmword ptr [rsp+150h+var_E0], xmm0
0x18000a68f  mov     qword ptr [rbp+50h+var_E0+10h], rax
0x18000a693  call    cs:__imp_VariantInit
0x18000a699  lea     ecx, [r15+50h]; Size
0x18000a69d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a6a2  xor     ecx, ecx
0x18000a6a4  mov     r15, rax
0x18000a6a7  test    rax, rax
0x18000a6aa  jz      loc_18000AAC9
0x18000a6b0  lea     rax, ??_7CMILCOMBase@@6B@; const CMILCOMBase::`vftable'
0x18000a6b7  mov     [r15+8], ecx
0x18000a6bb  mov     [r15], rax
0x18000a6be  lock inc cs:?g_cActiveObjects@@3JC; long volatile g_cActiveObjects
0x18000a6c5  lea     rdx, ??_7CBOMStream@@6BCMILCOMBase@@@; const CBOMStream::`vftable'{for `CMILCOMBase'}
0x18000a6cc  mov     [r15+18h], rcx
0x18000a6d0  lea     rax, ??_7CBOMStream@@6BIStream@@@; const CBOMStream::`vftable'{for `IStream'}
0x18000a6d7  mov     [r15+38h], rcx
0x18000a6db  mov     [r15+10h], rax
0x18000a6df  mov     rax, [rdx+8]
0x18000a6e3  mov     [r15+30h], rcx
0x18000a6e7  mov     [r15+20h], rcx
0x18000a6eb  mov     [r15+28h], ecx
0x18000a6ef  mov     rcx, r15
0x18000a6f2  mov     [r15], rdx
0x18000a6f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6fa  mov     eax, [r12+rsi*4]
0x18000a6fe  lea     rcx, [rbp+50h+var_90]; void *
0x18000a702  xor     edx, edx; Val
0x18000a704  mov     [rsp+150h+var_F8], eax
0x18000a708  lea     r12, [r13+10h]
0x18000a70c  mov     byte ptr [r15+44h], 1
0x18000a711  lea     r8d, [rdx+50h]; Size
0x18000a715  call    memset_0
0x18000a71a  mov     rax, [r12]
0x18000a71e  lea     rdx, [rbp+50h+var_90]
0x18000a722  mov     r8d, 1
0x18000a728  mov     rcx, r12
0x18000a72b  mov     rax, [rax+60h]
0x18000a72f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a734  mov     esi, eax
0x18000a736  test    eax, eax
0x18000a738  jns     short loc_18000A74C
0x18000a73a  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a741  jz      short loc_18000A7AF
0x18000a743  mov     ecx, esi; int
0x18000a745  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x18000a74a  jmp     short loc_18000A7AF
0x18000a74c  mov     rax, [rbp+50h+var_80]
0x18000a750  mov     [r15+38h], rax
0x18000a754  mov     qword ptr [r15+30h], 0
0x18000a75c  mov     rcx, [r15+18h]
0x18000a760  test    rcx, rcx
0x18000a763  jnz     loc_18000AB01
0x18000a769  mov     [r15+18h], r12
0x18000a76d  test    r12, r12
0x18000a770  jz      short loc_18000A782
0x18000a772  mov     rax, [r12]
0x18000a776  mov     rcx, r12
0x18000a779  mov     rax, [rax+8]
0x18000a77d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a782  mov     rax, [r15]
0x18000a785  mov     rdx, r12
0x18000a788  mov     r8d, [rsp+150h+var_F8]
0x18000a78d  mov     rcx, r15
0x18000a790  mov     rax, [rax+28h]
0x18000a794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a799  xor     r12d, r12d
0x18000a79c  mov     esi, eax
0x18000a79e  test    eax, eax
0x18000a7a0  jns     short loc_18000A7AB
0x18000a7a2  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000a7a9  jnz     short loc_18000A743
0x18000a7ab  test    esi, esi
0x18000a7ad  jns     short loc_18000A7CA
0x18000a7af  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x18000a7b6  mov     r12d, esi
0x18000a7b9  jnz     loc_18000AA78
0x18000a7bf  xor     r12d, r12d
0x18000a7c2  test    esi, esi
0x18000a7c4  js      loc_18000A51D
0x18000a7ca  mov     rax, [r14]
0x18000a7cd  lea     rdx, [rsp+150h+var_118]
0x18000a7d2  mov     rcx, r14
0x18000a7d5  mov     rax, [rax+108h]
0x18000a7dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7e1  mov     esi, eax
0x18000a7e3  test    eax, eax
0x18000a7e5  jns     short loc_18000A7FC
0x18000a7e7  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000a7ee  jnz     loc_18000A60B
0x18000a7f4  test    eax, eax
0x18000a7f6  js      loc_18000A51D
0x18000a7fc  mov     rcx, [rsp+150h+var_118]
0x18000a801  lea     r8, [rbp+50h+var_B0]
0x18000a805  movsd   xmm1, qword ptr [rbp+50h+pvarg+10h]
0x18000a80a  lea     rdx, aProhibitdtd; "ProhibitDTD"
0x18000a811  mov     eax, 0Bh
0x18000a816  movsd   [rbp+50h+var_A0], xmm1
0x18000a81b  mov     word ptr [rbp+50h+pvarg], ax
0x18000a81f  or      eax, 0FFFFFFFFh
0x18000a822  mov     word ptr [rbp+50h+pvarg+8], ax
0x18000a826  mov     rax, [rcx]
0x18000a829  movups  xmm0, xmmword ptr [rbp+50h+pvarg]
0x18000a82d  mov     rax, [rax+280h]
0x18000a834  movaps  [rbp+50h+var_B0], xmm0
0x18000a838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a83d  mov     esi, eax
0x18000a83f  test    eax, eax
0x18000a841  jns     short loc_18000A858
0x18000a843  cmp     cs:?g_doStackCaptures@@3HA, r12d; int g_doStackCaptures
0x18000a84a  jnz     loc_18000A60B
  ... truncated ...
```
