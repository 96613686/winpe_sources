# CCodecFactory::InitializeWriterFromReaderWithGetSetValue(IWICMetadataWriter *,_GUID const *,IWICMetadataReader *)

- ea: `0x1800bf3c0`
- end: `0x1800bf909`
- name: `?InitializeWriterFromReaderWithGetSetValue@CCodecFactory@@QEAAJPEAUIWICMetadataWriter@@PEBU_GUID@@PEAUIWICMetadataReader@@@Z`
- size: `1353`
- prototype: `__int64 __fastcall(CCodecFactory *__hidden this, struct IWICMetadataWriter *, const struct _GUID *, struct IWICMetadataReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180088040`

## callees

- `0x180042ae8`
- `0x180045174`
- `0x180088040`
- `0x1800bd9d4`
- `0x1800bf3c0`
- `0x1800e6af4`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf5b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bf5b8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf757`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf782`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf7ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf7d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8e6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf757`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf782`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf7ad`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf7d8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8b6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8c6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8d6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf8e6`

## pseudocode

```c
__int64 __fastcall CCodecFactory::InitializeWriterFromReaderWithGetSetValue(
        CCodecFactory *this,
        struct IWICMetadataWriter *a2,
        const struct _GUID *a3,
        struct IWICMetadataReader *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  int v9; // ecx
  __int64 v10; // r9
  void *v11; // r9
  int v12; // r9d
  unsigned int i; // edi
  __int64 (__fastcall ***v14)(_QWORD, GUID *, struct IWICMetadataReader **); // rcx
  struct IWICMetadataWriter *v16; // [rsp+40h] [rbp-79h] BYREF
  struct IWICMetadataReader *v17; // [rsp+48h] [rbp-71h] BYREF
  int v18; // [rsp+50h] [rbp-69h] BYREF
  struct IWICEnumMetadataItem *v19; // [rsp+58h] [rbp-61h] BYREF
  ULONGLONG ullMultiplier[2]; // [rsp+60h] [rbp-59h] BYREF
  __int64 v21; // [rsp+70h] [rbp-49h]
  PROPVARIANT v22[2]; // [rsp+78h] [rbp-41h] BYREF
  char *v23; // [rsp+88h] [rbp-31h]
  ULONGLONG pullResult; // [rsp+90h] [rbp-29h] BYREF
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-21h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-11h]
  PROPVARIANT v27[2]; // [rsp+B0h] [rbp-9h] BYREF
  __int64 v28; // [rsp+C0h] [rbp+7h]

  v19 = 0;
  v16 = 0;
  v17 = 0;
  v18 = 0;
  v26 = 0;
  v28 = 0;
  *(_OWORD *)pvar = 0;
  v21 = 0;
  *(_OWORD *)v27 = 0;
  v23 = 0;
  *(_OWORD *)ullMultiplier = 0;
  *(_OWORD *)v22 = 0;
  v7 = GetOrCreateEnumerator(a4, &v19);
  v8 = v7;
  if ( v7 < 0
    || (v7 = ((__int64 (__fastcall *)(struct IWICEnumMetadataItem *, __int64, PROPVARIANT *, PROPVARIANT *, ULONGLONG *, int *))v19->lpVtbl->Next)(
               v19,
               1,
               pvar,
               v27,
               ullMultiplier,
               &v18),
        v8 = v7,
        v7 < 0) )
  {
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_70;
LABEL_3:
    v9 = v7;
    goto LABEL_68;
  }
  v10 = (unsigned int)g_doStackCaptures;
  while ( 1 )
  {
    if ( !v18 )
    {
      v8 = 0;
      goto LABEL_70;
    }
    if ( LOWORD(ullMultiplier[0]) == 13 )
    {
      v7 = (**(__int64 (__fastcall ***)(ULONGLONG, GUID *, struct IWICMetadataReader **, __int64))ullMultiplier[1])(
             ullMultiplier[1],
             &IID_IWICMetadataReader,
             &v17,
             v10);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_3;
        goto LABEL_70;
      }
      v7 = CCodecFactory::CreateMetadataWriterFromReader(this, v17, a3, &v16);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_3;
        goto LABEL_70;
      }
      v7 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, GUID *, PROPVARIANT *))v16->lpVtbl->QueryInterface)(
             v16,
             &IID_IUnknown,
             &v22[1]);
      v8 = v7;
      if ( v7 < 0 )
      {
        if ( (_DWORD)g_doStackCaptures )
          goto LABEL_3;
        goto LABEL_70;
      }
      LOWORD(v22[0]) = 13;
      if ( v17 )
      {
        ((void (__fastcall *)(struct IWICMetadataReader *))v17->lpVtbl->Release)(v17);
        v17 = 0;
      }
      if ( v16 )
      {
        ((void (__fastcall *)(struct IWICMetadataWriter *))v16->lpVtbl->Release)(v16);
        v16 = 0;
      }
      v11 = v22;
      goto LABEL_48;
    }
    if ( LOWORD(ullMultiplier[0]) == 4108 )
      break;
    v11 = ullMultiplier;
LABEL_48:
    v7 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, PROPVARIANT *, PROPVARIANT *, void *))a2->lpVtbl->SetValue)(
           a2,
           pvar,
           v27,
           v11);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
LABEL_51:
    v7 = PropVariantClear(pvar);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = PropVariantClear(v27);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = PropVariantClear((PROPVARIANT *)ullMultiplier);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = PropVariantClear(v22);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = ((__int64 (__fastcall *)(struct IWICEnumMetadataItem *, __int64, PROPVARIANT *, PROPVARIANT *, ULONGLONG *, int *))v19->lpVtbl->Next)(
           v19,
           1,
           pvar,
           v27,
           ullMultiplier,
           &v18);
    v10 = (unsigned int)g_doStackCaptures;
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
  }
  LOWORD(v22[0]) = 4108;
  LODWORD(v22[1]) = ullMultiplier[1];
  pullResult = 0;
  v7 = ULongLongMult(0x18u, LODWORD(ullMultiplier[1]), &pullResult);
  v8 = v7;
  if ( v7 < 0 )
  {
    if ( v12 )
      goto LABEL_3;
    goto LABEL_70;
  }
  v23 = (char *)CoTaskMemAlloc(pullResult);
  if ( !v23 )
  {
    v8 = -2147024882;
    if ( !(_DWORD)g_doStackCaptures )
      goto LABEL_70;
    v9 = -2147024882;
LABEL_68:
    DoStackCapture(v9);
    goto LABEL_70;
  }
  memset_0(v23, 0, 24LL * LODWORD(ullMultiplier[1]));
  for ( i = 0; i < LODWORD(ullMultiplier[1]); ++i )
  {
    v14 = *(__int64 (__fastcall ****)(_QWORD, GUID *, struct IWICMetadataReader **))(v21 + 24LL * i + 8);
    v7 = (**v14)(v14, &IID_IWICMetadataReader, &v17);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = CCodecFactory::CreateMetadataWriterFromReader(this, v17, a3, &v16);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    v7 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, GUID *, char *))v16->lpVtbl->QueryInterface)(
           v16,
           &IID_IUnknown,
           &v23[24 * i + 8]);
    v8 = v7;
    if ( v7 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        goto LABEL_3;
      goto LABEL_70;
    }
    *(_WORD *)&v23[24 * i] = 13;
    if ( v17 )
    {
      ((void (__fastcall *)(struct IWICMetadataReader *))v17->lpVtbl->Release)(v17);
      v17 = 0;
    }
    if ( v16 )
    {
      ((void (__fastcall *)(struct IWICMetadataWriter *))v16->lpVtbl->Release)(v16);
      v16 = 0;
    }
  }
  v7 = ((__int64 (__fastcall *)(struct IWICMetadataWriter *, PROPVARIANT *, PROPVARIANT *, PROPVARIANT *))a2->lpVtbl->SetValue)(
         a2,
         pvar,
         v27,
         v22);
  v8 = v7;
  if ( v7 >= 0 )
    goto LABEL_51;
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_3;
LABEL_70:
  if ( v19 )
  {
    ((void (__fastcall *)(struct IWICEnumMetadataItem *))v19->lpVtbl->Release)(v19);
    v19 = 0;
  }
  if ( v16 )
  {
    ((void (__fastcall *)(struct IWICMetadataWriter *))v16->lpVtbl->Release)(v16);
    v16 = 0;
  }
  if ( v17 )
  {
    ((void (__fastcall *)(struct IWICMetadataReader *))v17->lpVtbl->Release)(v17);
    v17 = 0;
  }
  PropVariantClear(pvar);
  PropVariantClear(v27);
  PropVariantClear((PROPVARIANT *)ullMultiplier);
  PropVariantClear(v22);
  return v8;
}

```

## disassembly

```asm
0x1800bf3c0  push    rbp
0x1800bf3c2  push    rbx
0x1800bf3c3  push    rsi
0x1800bf3c4  push    rdi
0x1800bf3c5  push    r12
0x1800bf3c7  push    r13
0x1800bf3c9  push    r14
0x1800bf3cb  push    r15
0x1800bf3cd  lea     rbp, [rsp-1Fh]
0x1800bf3d2  sub     rsp, 0D8h
0x1800bf3d9  xor     eax, eax
0x1800bf3db  xor     r13d, r13d
0x1800bf3de  xorps   xmm0, xmm0
0x1800bf3e1  mov     [rbp+57h+var_B8], r13
0x1800bf3e5  xorps   xmm1, xmm1
0x1800bf3e8  mov     [rbp+57h+var_D0], r13
0x1800bf3ec  mov     r14, rdx
0x1800bf3ef  mov     [rbp+57h+var_C8], r13
0x1800bf3f3  mov     r12, rcx
0x1800bf3f6  mov     [rbp+57h+var_C0], r13d
0x1800bf3fa  lea     rdx, [rbp+57h+var_B8]; struct IWICEnumMetadataItem **
0x1800bf3fe  mov     [rbp+57h+var_68], rax
0x1800bf402  mov     rcx, r9; struct IWICMetadataReader *
0x1800bf405  mov     [rbp+57h+var_50], rax
0x1800bf409  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bf40d  mov     [rbp+57h+var_A0], rax
0x1800bf411  mov     r15, r8
0x1800bf414  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800bf418  mov     [rbp+57h+var_88], rax
0x1800bf41c  movups  xmmword ptr [rbp+57h+ullMultiplier], xmm0
0x1800bf420  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x1800bf424  call    ?GetOrCreateEnumerator@@YAJPEAUIWICMetadataReader@@PEAPEAUIWICEnumMetadataItem@@@Z; GetOrCreateEnumerator(IWICMetadataReader *,IWICEnumMetadataItem * *)
0x1800bf429  mov     ebx, eax
0x1800bf42b  test    eax, eax
0x1800bf42d  jns     short loc_1800BF443
0x1800bf42f  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf436  jz      loc_1800BF867
0x1800bf43c  mov     ecx, eax
0x1800bf43e  jmp     loc_1800BF85D
0x1800bf443  mov     rcx, [rbp+57h+var_B8]
0x1800bf447  lea     rdx, [rbp+57h+var_C0]
0x1800bf44b  mov     [rsp+110h+var_E8], rdx
0x1800bf450  lea     r9, [rbp+57h+var_60]
0x1800bf454  lea     rdx, [rbp+57h+ullMultiplier]
0x1800bf458  mov     [rsp+110h+var_F0], rdx
0x1800bf45d  lea     r8, [rbp+57h+pvar]
0x1800bf461  mov     rax, [rcx]
0x1800bf464  mov     edx, 1
0x1800bf469  mov     rax, [rax+18h]
0x1800bf46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf472  mov     ebx, eax
0x1800bf474  test    eax, eax
0x1800bf476  js      short loc_1800BF42F
0x1800bf478  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bf47f  mov     edi, 0Dh
0x1800bf484  mov     eax, 100Ch
0x1800bf489  cmp     [rbp+57h+var_C0], r13d
0x1800bf48d  jbe     loc_1800BF864
0x1800bf493  cmp     word ptr [rbp+57h+ullMultiplier], di
0x1800bf497  jnz     loc_1800BF574
0x1800bf49d  mov     rcx, [rbp+57h+ullMultiplier+8]
0x1800bf4a1  lea     r8, [rbp+57h+var_C8]
0x1800bf4a5  lea     rdx, IID_IWICMetadataReader
0x1800bf4ac  mov     rax, [rcx]
0x1800bf4af  mov     rax, [rax]
0x1800bf4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf4b7  mov     ebx, eax
0x1800bf4b9  test    eax, eax
0x1800bf4bb  jns     short loc_1800BF4D2
0x1800bf4bd  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf4c4  jnz     loc_1800BF43C
0x1800bf4ca  test    eax, eax
0x1800bf4cc  js      loc_1800BF867
0x1800bf4d2  mov     rdx, [rbp+57h+var_C8]; struct IWICMetadataReader *
0x1800bf4d6  lea     r9, [rbp+57h+var_D0]; struct IWICMetadataWriter **
0x1800bf4da  mov     r8, r15; struct _GUID *
0x1800bf4dd  mov     rcx, r12; this
0x1800bf4e0  call    ?CreateMetadataWriterFromReader@CCodecFactory@@UEAAJPEAUIWICMetadataReader@@PEBU_GUID@@PEAPEAUIWICMetadataWriter@@@Z; CCodecFactory::CreateMetadataWriterFromReader(IWICMetadataReader *,_GUID const *,IWICMetadataWriter * *)
0x1800bf4e5  mov     ebx, eax
0x1800bf4e7  test    eax, eax
0x1800bf4e9  jns     short loc_1800BF500
0x1800bf4eb  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf4f2  jnz     loc_1800BF43C
0x1800bf4f8  test    eax, eax
0x1800bf4fa  js      loc_1800BF867
0x1800bf500  mov     rcx, [rbp+57h+var_D0]
0x1800bf504  lea     r8, [rbp+57h+var_98+8]
0x1800bf508  lea     rdx, IID_IUnknown
0x1800bf50f  mov     rax, [rcx]
0x1800bf512  mov     rax, [rax]
0x1800bf515  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf51a  mov     ebx, eax
0x1800bf51c  test    eax, eax
0x1800bf51e  jns     short loc_1800BF535
0x1800bf520  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf527  jnz     loc_1800BF43C
0x1800bf52d  test    eax, eax
0x1800bf52f  js      loc_1800BF867
0x1800bf535  mov     rcx, [rbp+57h+var_C8]
0x1800bf539  mov     word ptr [rbp+57h+var_98], di
0x1800bf53d  test    rcx, rcx
0x1800bf540  jz      short loc_1800BF552
0x1800bf542  mov     rax, [rcx]
0x1800bf545  mov     rax, [rax+10h]
0x1800bf549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf54e  mov     [rbp+57h+var_C8], r13
0x1800bf552  mov     rcx, [rbp+57h+var_D0]
0x1800bf556  test    rcx, rcx
0x1800bf559  jz      short loc_1800BF56B
0x1800bf55b  mov     rax, [rcx]
0x1800bf55e  mov     rax, [rax+10h]
0x1800bf562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf567  mov     [rbp+57h+var_D0], r13
0x1800bf56b  lea     r9, [rbp+57h+var_98]
0x1800bf56f  jmp     loc_1800BF721
0x1800bf574  cmp     word ptr [rbp+57h+ullMultiplier], ax
0x1800bf578  jnz     loc_1800BF71D
0x1800bf57e  mov     word ptr [rbp+57h+var_98], ax
0x1800bf582  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800bf586  mov     rax, [rbp+57h+ullMultiplier+8]
0x1800bf58a  mov     ecx, 18h; ullMultiplicand
0x1800bf58f  mov     edx, eax; ullMultiplier
0x1800bf591  mov     dword ptr [rbp+57h+var_98+8], eax
0x1800bf594  mov     [rbp+57h+pullResult], r13
0x1800bf598  call    ULongLongMult
0x1800bf59d  mov     ebx, eax
0x1800bf59f  test    eax, eax
0x1800bf5a1  jns     short loc_1800BF5B4
0x1800bf5a3  test    r9d, r9d
0x1800bf5a6  jnz     loc_1800BF43C
0x1800bf5ac  test    eax, eax
0x1800bf5ae  js      loc_1800BF867
0x1800bf5b4  mov     rcx, [rbp+57h+pullResult]; cb
0x1800bf5b8  call    cs:__imp_CoTaskMemAlloc
0x1800bf5bf  nop     dword ptr [rax+rax+00h]
0x1800bf5c4  mov     [rbp+57h+var_88], rax
0x1800bf5c8  mov     rcx, rax; void *
0x1800bf5cb  test    rax, rax
0x1800bf5ce  jz      loc_1800BF84D
0x1800bf5d4  mov     eax, dword ptr [rbp+57h+ullMultiplier+8]
0x1800bf5d7  xor     edx, edx; Val
0x1800bf5d9  lea     r8, [rax+rax*2]
0x1800bf5dd  shl     r8, 3; Size
0x1800bf5e1  call    memset_0
0x1800bf5e6  mov     edi, r13d
0x1800bf5e9  cmp     edi, dword ptr [rbp+57h+ullMultiplier+8]
0x1800bf5ec  jnb     loc_1800BF6E0
0x1800bf5f2  mov     eax, edi
0x1800bf5f4  lea     r8, [rbp+57h+var_C8]
0x1800bf5f8  lea     rdx, IID_IWICMetadataReader
0x1800bf5ff  lea     rsi, [rax+rax*2]
0x1800bf603  mov     rax, [rbp+57h+var_A0]
0x1800bf607  mov     rcx, [rax+rsi*8+8]
0x1800bf60c  mov     rax, [rcx]
0x1800bf60f  mov     rax, [rax]
0x1800bf612  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf617  mov     ebx, eax
0x1800bf619  test    eax, eax
0x1800bf61b  jns     short loc_1800BF632
0x1800bf61d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf624  jnz     loc_1800BF43C
0x1800bf62a  test    eax, eax
0x1800bf62c  js      loc_1800BF867
0x1800bf632  mov     rdx, [rbp+57h+var_C8]; struct IWICMetadataReader *
0x1800bf636  lea     r9, [rbp+57h+var_D0]; struct IWICMetadataWriter **
0x1800bf63a  mov     r8, r15; struct _GUID *
0x1800bf63d  mov     rcx, r12; this
0x1800bf640  call    ?CreateMetadataWriterFromReader@CCodecFactory@@UEAAJPEAUIWICMetadataReader@@PEBU_GUID@@PEAPEAUIWICMetadataWriter@@@Z; CCodecFactory::CreateMetadataWriterFromReader(IWICMetadataReader *,_GUID const *,IWICMetadataWriter * *)
0x1800bf645  mov     ebx, eax
0x1800bf647  test    eax, eax
0x1800bf649  jns     short loc_1800BF660
0x1800bf64b  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf652  jnz     loc_1800BF43C
0x1800bf658  test    eax, eax
0x1800bf65a  js      loc_1800BF867
0x1800bf660  mov     rcx, [rbp+57h+var_D0]
0x1800bf664  mov     r8, [rbp+57h+var_88]
0x1800bf668  add     r8, 8
0x1800bf66c  mov     rdx, [rcx]
0x1800bf66f  lea     r8, [r8+rsi*8]
0x1800bf673  mov     rax, [rdx]
0x1800bf676  lea     rdx, IID_IUnknown
0x1800bf67d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf682  mov     ebx, eax
0x1800bf684  test    eax, eax
0x1800bf686  jns     short loc_1800BF69D
0x1800bf688  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf68f  jnz     loc_1800BF43C
0x1800bf695  test    eax, eax
0x1800bf697  js      loc_1800BF867
0x1800bf69d  mov     rax, [rbp+57h+var_88]
0x1800bf6a1  mov     word ptr [rax+rsi*8], 0Dh
0x1800bf6a7  mov     rcx, [rbp+57h+var_C8]
0x1800bf6ab  test    rcx, rcx
0x1800bf6ae  jz      short loc_1800BF6C0
0x1800bf6b0  mov     rax, [rcx]
0x1800bf6b3  mov     rax, [rax+10h]
0x1800bf6b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6bc  mov     [rbp+57h+var_C8], r13
0x1800bf6c0  mov     rcx, [rbp+57h+var_D0]
0x1800bf6c4  test    rcx, rcx
0x1800bf6c7  jz      short loc_1800BF6D9
0x1800bf6c9  mov     rax, [rcx]
0x1800bf6cc  mov     rax, [rax+10h]
0x1800bf6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6d5  mov     [rbp+57h+var_D0], r13
0x1800bf6d9  inc     edi
0x1800bf6db  jmp     loc_1800BF5E9
0x1800bf6e0  mov     rax, [r14]
0x1800bf6e3  lea     r9, [rbp+57h+var_98]
0x1800bf6e7  lea     r8, [rbp+57h+var_60]
0x1800bf6eb  mov     rcx, r14
0x1800bf6ee  lea     rdx, [rbp+57h+pvar]
0x1800bf6f2  mov     rax, [rax+48h]
0x1800bf6f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf6fb  mov     ebx, eax
0x1800bf6fd  test    eax, eax
0x1800bf6ff  jns     short loc_1800BF716
0x1800bf701  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf708  jnz     loc_1800BF43C
0x1800bf70e  test    eax, eax
0x1800bf710  js      loc_1800BF867
0x1800bf716  mov     edi, 0Dh
0x1800bf71b  jmp     short loc_1800BF753
0x1800bf71d  lea     r9, [rbp+57h+ullMultiplier]
0x1800bf721  mov     rax, [r14]
0x1800bf724  lea     r8, [rbp+57h+var_60]
0x1800bf728  lea     rdx, [rbp+57h+pvar]
0x1800bf72c  mov     rcx, r14
0x1800bf72f  mov     rax, [rax+48h]
0x1800bf733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf738  mov     ebx, eax
0x1800bf73a  test    eax, eax
0x1800bf73c  jns     short loc_1800BF753
0x1800bf73e  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf745  jnz     loc_1800BF43C
0x1800bf74b  test    eax, eax
0x1800bf74d  js      loc_1800BF867
0x1800bf753  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bf757  call    cs:__imp_PropVariantClear
0x1800bf75e  nop     dword ptr [rax+rax+00h]
0x1800bf763  mov     ebx, eax
0x1800bf765  test    eax, eax
0x1800bf767  jns     short loc_1800BF77E
0x1800bf769  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf770  jnz     loc_1800BF43C
0x1800bf776  test    eax, eax
0x1800bf778  js      loc_1800BF867
0x1800bf77e  lea     rcx, [rbp+57h+var_60]; pvar
0x1800bf782  call    cs:__imp_PropVariantClear
0x1800bf789  nop     dword ptr [rax+rax+00h]
0x1800bf78e  mov     ebx, eax
0x1800bf790  test    eax, eax
0x1800bf792  jns     short loc_1800BF7A9
0x1800bf794  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf79b  jnz     loc_1800BF43C
0x1800bf7a1  test    eax, eax
0x1800bf7a3  js      loc_1800BF867
0x1800bf7a9  lea     rcx, [rbp+57h+ullMultiplier]; pvar
0x1800bf7ad  call    cs:__imp_PropVariantClear
0x1800bf7b4  nop     dword ptr [rax+rax+00h]
0x1800bf7b9  mov     ebx, eax
0x1800bf7bb  test    eax, eax
0x1800bf7bd  jns     short loc_1800BF7D4
0x1800bf7bf  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf7c6  jnz     loc_1800BF43C
0x1800bf7cc  test    eax, eax
0x1800bf7ce  js      loc_1800BF867
0x1800bf7d4  lea     rcx, [rbp+57h+var_98]; pvar
0x1800bf7d8  call    cs:__imp_PropVariantClear
0x1800bf7df  nop     dword ptr [rax+rax+00h]
0x1800bf7e4  mov     ebx, eax
0x1800bf7e6  test    eax, eax
0x1800bf7e8  jns     short loc_1800BF7FB
0x1800bf7ea  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf7f1  jnz     loc_1800BF43C
0x1800bf7f7  test    eax, eax
0x1800bf7f9  js      short loc_1800BF867
0x1800bf7fb  mov     rcx, [rbp+57h+var_B8]
0x1800bf7ff  lea     rdx, [rbp+57h+var_C0]
0x1800bf803  mov     [rsp+110h+var_E8], rdx
0x1800bf808  lea     r9, [rbp+57h+var_60]
0x1800bf80c  lea     rdx, [rbp+57h+ullMultiplier]
0x1800bf810  mov     [rsp+110h+var_F0], rdx
0x1800bf815  lea     r8, [rbp+57h+pvar]
0x1800bf819  mov     rax, [rcx]
0x1800bf81c  mov     edx, 1
0x1800bf821  mov     rax, [rax+18h]
0x1800bf825  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf82a  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bf831  mov     ebx, eax
0x1800bf833  test    eax, eax
0x1800bf835  jns     loc_1800BF484
0x1800bf83b  test    r9d, r9d
0x1800bf83e  jnz     loc_1800BF43C
0x1800bf844  test    eax, eax
0x1800bf846  js      short loc_1800BF867
0x1800bf848  jmp     loc_1800BF484
0x1800bf84d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bf854  mov     ebx, 8007000Eh
  ... truncated ...
```
