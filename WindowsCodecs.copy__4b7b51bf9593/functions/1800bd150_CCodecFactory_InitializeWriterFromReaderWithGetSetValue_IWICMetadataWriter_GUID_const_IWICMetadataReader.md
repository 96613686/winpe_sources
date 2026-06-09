# CCodecFactory::InitializeWriterFromReaderWithGetSetValue(IWICMetadataWriter *,_GUID const *,IWICMetadataReader *)

- ea: `0x1800bd150`
- end: `0x1800bd662`
- name: `?InitializeWriterFromReaderWithGetSetValue@CCodecFactory@@QEAAJPEAUIWICMetadataWriter@@PEBU_GUID@@PEAUIWICMetadataReader@@@Z`
- size: `1298`
- prototype: `__int64 __fastcall(CCodecFactory *__hidden this, struct IWICMetadataWriter *, const struct _GUID *, struct IWICMetadataReader *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x180087bf0`

## callees

- `0x18001dd10`
- `0x18001dd40`
- `0x180087bf0`
- `0x1800bb784`
- `0x1800bd150`
- `0x1800e3c04`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd348`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800bd348`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd4e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd506`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd52b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd550`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd628`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd632`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd63c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd646`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd4e1`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd506`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd52b`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd550`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd628`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd632`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd63c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bd646`

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
0x1800bd150  push    rbp
0x1800bd152  push    rbx
0x1800bd153  push    rsi
0x1800bd154  push    rdi
0x1800bd155  push    r12
0x1800bd157  push    r13
0x1800bd159  push    r14
0x1800bd15b  push    r15
0x1800bd15d  lea     rbp, [rsp-1Fh]
0x1800bd162  sub     rsp, 0D8h
0x1800bd169  xor     eax, eax
0x1800bd16b  xor     r13d, r13d
0x1800bd16e  xorps   xmm0, xmm0
0x1800bd171  mov     [rbp+57h+var_B8], r13
0x1800bd175  xorps   xmm1, xmm1
0x1800bd178  mov     [rbp+57h+var_D0], r13
0x1800bd17c  mov     r14, rdx
0x1800bd17f  mov     [rbp+57h+var_C8], r13
0x1800bd183  mov     r12, rcx
0x1800bd186  mov     [rbp+57h+var_C0], r13d
0x1800bd18a  lea     rdx, [rbp+57h+var_B8]; struct IWICEnumMetadataItem **
0x1800bd18e  mov     [rbp+57h+var_68], rax
0x1800bd192  mov     rcx, r9; struct IWICMetadataReader *
0x1800bd195  mov     [rbp+57h+var_50], rax
0x1800bd199  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800bd19d  mov     [rbp+57h+var_A0], rax
0x1800bd1a1  mov     r15, r8
0x1800bd1a4  movups  xmmword ptr [rbp+57h+var_60], xmm1
0x1800bd1a8  mov     [rbp+57h+var_88], rax
0x1800bd1ac  movups  xmmword ptr [rbp+57h+ullMultiplier], xmm0
0x1800bd1b0  movups  xmmword ptr [rbp+57h+var_98], xmm1
0x1800bd1b4  call    ?GetOrCreateEnumerator@@YAJPEAUIWICMetadataReader@@PEAPEAUIWICEnumMetadataItem@@@Z; GetOrCreateEnumerator(IWICMetadataReader *,IWICEnumMetadataItem * *)
0x1800bd1b9  mov     ebx, eax
0x1800bd1bb  test    eax, eax
0x1800bd1bd  jns     short loc_1800BD1D3
0x1800bd1bf  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd1c6  jz      loc_1800BD5D9
0x1800bd1cc  mov     ecx, eax
0x1800bd1ce  jmp     loc_1800BD5CF
0x1800bd1d3  mov     rcx, [rbp+57h+var_B8]
0x1800bd1d7  lea     rdx, [rbp+57h+var_C0]
0x1800bd1db  mov     [rsp+110h+var_E8], rdx
0x1800bd1e0  lea     r9, [rbp+57h+var_60]
0x1800bd1e4  lea     rdx, [rbp+57h+ullMultiplier]
0x1800bd1e8  mov     [rsp+110h+var_F0], rdx
0x1800bd1ed  lea     r8, [rbp+57h+pvar]
0x1800bd1f1  mov     rax, [rcx]
0x1800bd1f4  mov     edx, 1
0x1800bd1f9  mov     rax, [rax+18h]
0x1800bd1fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd202  mov     ebx, eax
0x1800bd204  test    eax, eax
0x1800bd206  js      short loc_1800BD1BF
0x1800bd208  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bd20f  mov     edi, 0Dh
0x1800bd214  mov     eax, 100Ch
0x1800bd219  cmp     [rbp+57h+var_C0], r13d
0x1800bd21d  jbe     loc_1800BD5D6
0x1800bd223  cmp     word ptr [rbp+57h+ullMultiplier], di
0x1800bd227  jnz     loc_1800BD304
0x1800bd22d  mov     rcx, [rbp+57h+ullMultiplier+8]
0x1800bd231  lea     r8, [rbp+57h+var_C8]
0x1800bd235  lea     rdx, IID_IWICMetadataReader
0x1800bd23c  mov     rax, [rcx]
0x1800bd23f  mov     rax, [rax]
0x1800bd242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd247  mov     ebx, eax
0x1800bd249  test    eax, eax
0x1800bd24b  jns     short loc_1800BD262
0x1800bd24d  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd254  jnz     loc_1800BD1CC
0x1800bd25a  test    eax, eax
0x1800bd25c  js      loc_1800BD5D9
0x1800bd262  mov     rdx, [rbp+57h+var_C8]; struct IWICMetadataReader *
0x1800bd266  lea     r9, [rbp+57h+var_D0]; struct IWICMetadataWriter **
0x1800bd26a  mov     r8, r15; struct _GUID *
0x1800bd26d  mov     rcx, r12; this
0x1800bd270  call    ?CreateMetadataWriterFromReader@CCodecFactory@@UEAAJPEAUIWICMetadataReader@@PEBU_GUID@@PEAPEAUIWICMetadataWriter@@@Z; CCodecFactory::CreateMetadataWriterFromReader(IWICMetadataReader *,_GUID const *,IWICMetadataWriter * *)
0x1800bd275  mov     ebx, eax
0x1800bd277  test    eax, eax
0x1800bd279  jns     short loc_1800BD290
0x1800bd27b  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd282  jnz     loc_1800BD1CC
0x1800bd288  test    eax, eax
0x1800bd28a  js      loc_1800BD5D9
0x1800bd290  mov     rcx, [rbp+57h+var_D0]
0x1800bd294  lea     r8, [rbp+57h+var_98+8]
0x1800bd298  lea     rdx, IID_IUnknown
0x1800bd29f  mov     rax, [rcx]
0x1800bd2a2  mov     rax, [rax]
0x1800bd2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2aa  mov     ebx, eax
0x1800bd2ac  test    eax, eax
0x1800bd2ae  jns     short loc_1800BD2C5
0x1800bd2b0  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd2b7  jnz     loc_1800BD1CC
0x1800bd2bd  test    eax, eax
0x1800bd2bf  js      loc_1800BD5D9
0x1800bd2c5  mov     rcx, [rbp+57h+var_C8]
0x1800bd2c9  mov     word ptr [rbp+57h+var_98], di
0x1800bd2cd  test    rcx, rcx
0x1800bd2d0  jz      short loc_1800BD2E2
0x1800bd2d2  mov     rax, [rcx]
0x1800bd2d5  mov     rax, [rax+10h]
0x1800bd2d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2de  mov     [rbp+57h+var_C8], r13
0x1800bd2e2  mov     rcx, [rbp+57h+var_D0]
0x1800bd2e6  test    rcx, rcx
0x1800bd2e9  jz      short loc_1800BD2FB
0x1800bd2eb  mov     rax, [rcx]
0x1800bd2ee  mov     rax, [rax+10h]
0x1800bd2f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd2f7  mov     [rbp+57h+var_D0], r13
0x1800bd2fb  lea     r9, [rbp+57h+var_98]
0x1800bd2ff  jmp     loc_1800BD4AB
0x1800bd304  cmp     word ptr [rbp+57h+ullMultiplier], ax
0x1800bd308  jnz     loc_1800BD4A7
0x1800bd30e  mov     word ptr [rbp+57h+var_98], ax
0x1800bd312  lea     r8, [rbp+57h+pullResult]; pullResult
0x1800bd316  mov     rax, [rbp+57h+ullMultiplier+8]
0x1800bd31a  mov     ecx, 18h; ullMultiplicand
0x1800bd31f  mov     edx, eax; ullMultiplier
0x1800bd321  mov     dword ptr [rbp+57h+var_98+8], eax
0x1800bd324  mov     [rbp+57h+pullResult], r13
0x1800bd328  call    ULongLongMult
0x1800bd32d  mov     ebx, eax
0x1800bd32f  test    eax, eax
0x1800bd331  jns     short loc_1800BD344
0x1800bd333  test    r9d, r9d
0x1800bd336  jnz     loc_1800BD1CC
0x1800bd33c  test    eax, eax
0x1800bd33e  js      loc_1800BD5D9
0x1800bd344  mov     rcx, [rbp+57h+pullResult]; cb
0x1800bd348  call    cs:__imp_CoTaskMemAlloc
0x1800bd34e  mov     [rbp+57h+var_88], rax
0x1800bd352  mov     rcx, rax; void *
0x1800bd355  test    rax, rax
0x1800bd358  jz      loc_1800BD5BF
0x1800bd35e  mov     eax, dword ptr [rbp+57h+ullMultiplier+8]
0x1800bd361  xor     edx, edx; Val
0x1800bd363  lea     r8, [rax+rax*2]
0x1800bd367  shl     r8, 3; Size
0x1800bd36b  call    memset_0
0x1800bd370  mov     edi, r13d
0x1800bd373  cmp     edi, dword ptr [rbp+57h+ullMultiplier+8]
0x1800bd376  jnb     loc_1800BD46A
0x1800bd37c  mov     eax, edi
0x1800bd37e  lea     r8, [rbp+57h+var_C8]
0x1800bd382  lea     rdx, IID_IWICMetadataReader
0x1800bd389  lea     rsi, [rax+rax*2]
0x1800bd38d  mov     rax, [rbp+57h+var_A0]
0x1800bd391  mov     rcx, [rax+rsi*8+8]
0x1800bd396  mov     rax, [rcx]
0x1800bd399  mov     rax, [rax]
0x1800bd39c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd3a1  mov     ebx, eax
0x1800bd3a3  test    eax, eax
0x1800bd3a5  jns     short loc_1800BD3BC
0x1800bd3a7  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd3ae  jnz     loc_1800BD1CC
0x1800bd3b4  test    eax, eax
0x1800bd3b6  js      loc_1800BD5D9
0x1800bd3bc  mov     rdx, [rbp+57h+var_C8]; struct IWICMetadataReader *
0x1800bd3c0  lea     r9, [rbp+57h+var_D0]; struct IWICMetadataWriter **
0x1800bd3c4  mov     r8, r15; struct _GUID *
0x1800bd3c7  mov     rcx, r12; this
0x1800bd3ca  call    ?CreateMetadataWriterFromReader@CCodecFactory@@UEAAJPEAUIWICMetadataReader@@PEBU_GUID@@PEAPEAUIWICMetadataWriter@@@Z; CCodecFactory::CreateMetadataWriterFromReader(IWICMetadataReader *,_GUID const *,IWICMetadataWriter * *)
0x1800bd3cf  mov     ebx, eax
0x1800bd3d1  test    eax, eax
0x1800bd3d3  jns     short loc_1800BD3EA
0x1800bd3d5  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd3dc  jnz     loc_1800BD1CC
0x1800bd3e2  test    eax, eax
0x1800bd3e4  js      loc_1800BD5D9
0x1800bd3ea  mov     rcx, [rbp+57h+var_D0]
0x1800bd3ee  mov     r8, [rbp+57h+var_88]
0x1800bd3f2  add     r8, 8
0x1800bd3f6  mov     rdx, [rcx]
0x1800bd3f9  lea     r8, [r8+rsi*8]
0x1800bd3fd  mov     rax, [rdx]
0x1800bd400  lea     rdx, IID_IUnknown
0x1800bd407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd40c  mov     ebx, eax
0x1800bd40e  test    eax, eax
0x1800bd410  jns     short loc_1800BD427
0x1800bd412  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd419  jnz     loc_1800BD1CC
0x1800bd41f  test    eax, eax
0x1800bd421  js      loc_1800BD5D9
0x1800bd427  mov     rax, [rbp+57h+var_88]
0x1800bd42b  mov     word ptr [rax+rsi*8], 0Dh
0x1800bd431  mov     rcx, [rbp+57h+var_C8]
0x1800bd435  test    rcx, rcx
0x1800bd438  jz      short loc_1800BD44A
0x1800bd43a  mov     rax, [rcx]
0x1800bd43d  mov     rax, [rax+10h]
0x1800bd441  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd446  mov     [rbp+57h+var_C8], r13
0x1800bd44a  mov     rcx, [rbp+57h+var_D0]
0x1800bd44e  test    rcx, rcx
0x1800bd451  jz      short loc_1800BD463
0x1800bd453  mov     rax, [rcx]
0x1800bd456  mov     rax, [rax+10h]
0x1800bd45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd45f  mov     [rbp+57h+var_D0], r13
0x1800bd463  inc     edi
0x1800bd465  jmp     loc_1800BD373
0x1800bd46a  mov     rax, [r14]
0x1800bd46d  lea     r9, [rbp+57h+var_98]
0x1800bd471  lea     r8, [rbp+57h+var_60]
0x1800bd475  mov     rcx, r14
0x1800bd478  lea     rdx, [rbp+57h+pvar]
0x1800bd47c  mov     rax, [rax+48h]
0x1800bd480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd485  mov     ebx, eax
0x1800bd487  test    eax, eax
0x1800bd489  jns     short loc_1800BD4A0
0x1800bd48b  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd492  jnz     loc_1800BD1CC
0x1800bd498  test    eax, eax
0x1800bd49a  js      loc_1800BD5D9
0x1800bd4a0  mov     edi, 0Dh
0x1800bd4a5  jmp     short loc_1800BD4DD
0x1800bd4a7  lea     r9, [rbp+57h+ullMultiplier]
0x1800bd4ab  mov     rax, [r14]
0x1800bd4ae  lea     r8, [rbp+57h+var_60]
0x1800bd4b2  lea     rdx, [rbp+57h+pvar]
0x1800bd4b6  mov     rcx, r14
0x1800bd4b9  mov     rax, [rax+48h]
0x1800bd4bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd4c2  mov     ebx, eax
0x1800bd4c4  test    eax, eax
0x1800bd4c6  jns     short loc_1800BD4DD
0x1800bd4c8  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd4cf  jnz     loc_1800BD1CC
0x1800bd4d5  test    eax, eax
0x1800bd4d7  js      loc_1800BD5D9
0x1800bd4dd  lea     rcx, [rbp+57h+pvar]; pvar
0x1800bd4e1  call    cs:__imp_PropVariantClear
0x1800bd4e7  mov     ebx, eax
0x1800bd4e9  test    eax, eax
0x1800bd4eb  jns     short loc_1800BD502
0x1800bd4ed  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd4f4  jnz     loc_1800BD1CC
0x1800bd4fa  test    eax, eax
0x1800bd4fc  js      loc_1800BD5D9
0x1800bd502  lea     rcx, [rbp+57h+var_60]; pvar
0x1800bd506  call    cs:__imp_PropVariantClear
0x1800bd50c  mov     ebx, eax
0x1800bd50e  test    eax, eax
0x1800bd510  jns     short loc_1800BD527
0x1800bd512  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd519  jnz     loc_1800BD1CC
0x1800bd51f  test    eax, eax
0x1800bd521  js      loc_1800BD5D9
0x1800bd527  lea     rcx, [rbp+57h+ullMultiplier]; pvar
0x1800bd52b  call    cs:__imp_PropVariantClear
0x1800bd531  mov     ebx, eax
0x1800bd533  test    eax, eax
0x1800bd535  jns     short loc_1800BD54C
0x1800bd537  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd53e  jnz     loc_1800BD1CC
0x1800bd544  test    eax, eax
0x1800bd546  js      loc_1800BD5D9
0x1800bd54c  lea     rcx, [rbp+57h+var_98]; pvar
0x1800bd550  call    cs:__imp_PropVariantClear
0x1800bd556  mov     ebx, eax
0x1800bd558  test    eax, eax
0x1800bd55a  jns     short loc_1800BD56D
0x1800bd55c  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd563  jnz     loc_1800BD1CC
0x1800bd569  test    eax, eax
0x1800bd56b  js      short loc_1800BD5D9
0x1800bd56d  mov     rcx, [rbp+57h+var_B8]
0x1800bd571  lea     rdx, [rbp+57h+var_C0]
0x1800bd575  mov     [rsp+110h+var_E8], rdx
0x1800bd57a  lea     r9, [rbp+57h+var_60]
0x1800bd57e  lea     rdx, [rbp+57h+ullMultiplier]
0x1800bd582  mov     [rsp+110h+var_F0], rdx
0x1800bd587  lea     r8, [rbp+57h+pvar]
0x1800bd58b  mov     rax, [rcx]
0x1800bd58e  mov     edx, 1
0x1800bd593  mov     rax, [rax+18h]
0x1800bd597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bd59c  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x1800bd5a3  mov     ebx, eax
0x1800bd5a5  test    eax, eax
0x1800bd5a7  jns     loc_1800BD214
0x1800bd5ad  test    r9d, r9d
0x1800bd5b0  jnz     loc_1800BD1CC
0x1800bd5b6  test    eax, eax
0x1800bd5b8  js      short loc_1800BD5D9
0x1800bd5ba  jmp     loc_1800BD214
0x1800bd5bf  cmp     cs:?g_doStackCaptures@@3HA, r13d; int g_doStackCaptures
0x1800bd5c6  mov     ebx, 8007000Eh
0x1800bd5cb  jz      short loc_1800BD5D9
0x1800bd5cd  mov     ecx, ebx; int
0x1800bd5cf  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800bd5d4  jmp     short loc_1800BD5D9
0x1800bd5d6  mov     ebx, r13d
  ... truncated ...
```
