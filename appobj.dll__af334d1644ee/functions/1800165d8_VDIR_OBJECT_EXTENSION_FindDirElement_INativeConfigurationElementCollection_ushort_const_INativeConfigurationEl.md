# VDIR_OBJECT_EXTENSION::FindDirElement(INativeConfigurationElementCollection *,ushort const *,INativeConfigurationElement * *,INativeConfigurationElement * *)

- ea: `0x1800165d8`
- end: `0x180016c27`
- name: `?FindDirElement@VDIR_OBJECT_EXTENSION@@AEAAJPEAVINativeConfigurationElementCollection@@PEBGPEAPEAVINativeConfigurationElement@@2@Z`
- size: `1615`
- prototype: `__int64 __fastcall(VDIR_OBJECT_EXTENSION *this, struct INativeConfigurationElementCollection *, const unsigned __int16 *, struct INativeConfigurationElement **, struct INativeConfigurationElement **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180015ab0`

## callees

- `0x180001fb0`
- `0x180002640`
- `0x180002e60`
- `0x180002e90`
- `0x1800049b0`
- `0x1800165d8`
- `0x18002bb20`
- `0x180034cbe`
- `0x180034d00`
- `0x180036010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x180016835`
- `msvcrt!_wcsnicmp` at `0x180016a98`
- `msvcrt!_wcsnicmp` at `0x180016835`
- `msvcrt!_wcsnicmp` at `0x180016a98`

## pseudocode

```c
__int64 __fastcall VDIR_OBJECT_EXTENSION::FindDirElement(
        VDIR_OBJECT_EXTENSION *this,
        struct INativeConfigurationElementCollection *a2,
        const unsigned __int16 *a3,
        struct INativeConfigurationElement **a4,
        struct INativeConfigurationElement **a5)
{
  struct INativeConfigurationElement *v8; // rdi
  APP_OBJECT_UTILS *v9; // rcx
  struct INativeConfigurationElement *v10; // rsi
  int v11; // ebx
  unsigned int i; // r12d
  __int64 v13; // rdx
  wchar_t *v14; // r14
  __int64 v15; // r15
  int v16; // edx
  unsigned __int16 *v17; // r12
  unsigned int j; // r13d
  unsigned __int16 *v19; // rdx
  unsigned __int16 *v20; // r14
  int v21; // edx
  unsigned __int16 *v22; // rdx
  int v23; // eax
  int v24; // edx
  unsigned int v25; // ecx
  wchar_t *v26; // r14
  __int64 v27; // rdx
  __int64 v28; // r15
  int v29; // edx
  unsigned int v31; // [rsp+30h] [rbp-D0h]
  unsigned int v32; // [rsp+30h] [rbp-D0h]
  struct INativeConfigurationElement *v33; // [rsp+38h] [rbp-C8h] BYREF
  struct INativeConfigurationElement *v34; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  unsigned int v36; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v37; // [rsp+54h] [rbp-ACh] BYREF
  __int64 v38; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 *v39; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int16 *v40; // [rsp+68h] [rbp-98h] BYREF
  struct INativeConfigurationElement **v41; // [rsp+70h] [rbp-90h]
  struct INativeConfigurationElement **v42; // [rsp+78h] [rbp-88h]
  _BYTE v43[32]; // [rsp+80h] [rbp-80h] BYREF
  wchar_t *v44; // [rsp+A0h] [rbp-60h]
  int v45; // [rsp+A8h] [rbp-58h]
  __int16 v46; // [rsp+ACh] [rbp-54h]
  size_t v47; // [rsp+B0h] [rbp-50h]
  const unsigned __int8 *v48[4]; // [rsp+B8h] [rbp-48h] BYREF
  wchar_t *String1; // [rsp+D8h] [rbp-28h]
  int v50; // [rsp+E0h] [rbp-20h]
  __int16 v51; // [rsp+E4h] [rbp-1Ch]
  size_t MaxCount; // [rsp+E8h] [rbp-18h]
  _BYTE v53[32]; // [rsp+F0h] [rbp-10h] BYREF
  unsigned __int16 *v54; // [rsp+110h] [rbp+10h]
  int v55; // [rsp+118h] [rbp+18h]
  __int16 v56; // [rsp+11Ch] [rbp+1Ch]
  int v57; // [rsp+120h] [rbp+20h]
  _BYTE v58[32]; // [rsp+128h] [rbp+28h] BYREF
  unsigned __int16 *v59; // [rsp+148h] [rbp+48h]
  int v60; // [rsp+150h] [rbp+50h]
  __int16 v61; // [rsp+154h] [rbp+54h]
  int v62; // [rsp+158h] [rbp+58h]
  __int16 v63; // [rsp+160h] [rbp+60h] BYREF
  char v64[510]; // [rsp+162h] [rbp+62h] BYREF
  __int16 v65; // [rsp+360h] [rbp+260h] BYREF
  char v66[510]; // [rsp+362h] [rbp+262h] BYREF
  __int16 v67; // [rsp+560h] [rbp+460h] BYREF
  char v68[510]; // [rsp+562h] [rbp+462h] BYREF
  __int16 v69; // [rsp+760h] [rbp+660h] BYREF
  char v70[510]; // [rsp+762h] [rbp+662h] BYREF

  v41 = a4;
  v42 = a5;
  v36 = 0;
  v37 = 0;
  v33 = 0;
  v40 = 0;
  v39 = 0;
  v8 = 0;
  memset_0(v64, 0, sizeof(v64));
  v51 = 256;
  LODWORD(MaxCount) = 0;
  v63 = 0;
  String1 = (wchar_t *)&v63;
  v50 = 512;
  memset_0(v66, 0, sizeof(v66));
  v55 = 512;
  v54 = (unsigned __int16 *)&v65;
  v56 = 256;
  v57 = 0;
  v65 = 0;
  memset_0(v68, 0, sizeof(v68));
  v60 = 512;
  v59 = (unsigned __int16 *)&v67;
  v61 = 256;
  v62 = 0;
  v67 = 0;
  memset_0(v70, 0, sizeof(v70));
  v45 = 512;
  v46 = 256;
  v44 = (wchar_t *)&v69;
  v10 = 0;
  LODWORD(v47) = 0;
  v69 = 0;
  v38 = 0;
  v34 = 0;
  String2 = 0;
  if ( !a2 || !a3 || !a5 || !a4 )
  {
    v11 = -2147024809;
    goto LABEL_70;
  }
  v11 = APP_OBJECT_UTILS::ResolveUrl(v9, a3, 0, (const unsigned __int16 **)&String2, 0);
  if ( v11 < 0 )
    goto LABEL_70;
  if ( !String2 )
  {
    v11 = -2147024894;
    goto LABEL_70;
  }
  v31 = 0;
  (*(void (__fastcall **)(struct INativeConfigurationElementCollection *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
    a2,
    &v36);
  for ( i = 0; i < v36; ++i )
  {
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElementCollection *, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)a2 + 32LL))(
            a2,
            i,
            &v33);
    if ( v11 < 0 )
      goto LABEL_70;
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v33 + 64LL))(
            v33,
            L"path",
            &v40,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_70;
    v11 = STRU::Copy((STRU *)v48, (const unsigned __int8 *)v40);
    if ( v11 < 0 )
      goto LABEL_70;
    while ( 1 )
    {
      v14 = String1;
      if ( (unsigned int)MaxCount <= 1 )
        break;
      v13 = (unsigned int)(MaxCount - 1);
      if ( String1[v13] != 47 )
        break;
      STRU::SetLen((STRU *)v48, v13);
    }
    v15 = (unsigned int)MaxCount;
    if ( !_wcsnicmp(String1, String2, (unsigned int)MaxCount) && (unsigned int)v15 > v31 )
    {
      v16 = *v14 - 47;
      if ( *v14 == 47 )
        v16 = v14[1];
      if ( !v16 || !String2[v15] || String2[v15] == 47 )
      {
        if ( v8 )
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v8 + 16LL))(v8);
        v8 = v33;
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v33 + 8LL))(v33);
        v11 = STRU::Copy((STRU *)v58, v48);
        if ( v11 < 0 )
          goto LABEL_70;
        v31 = v15;
      }
    }
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( !v8 )
    goto LABEL_70;
  v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v8 + 40LL))(v8, &v38);
  if ( v11 < 0 )
    goto LABEL_70;
  v32 = 0;
  (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v38 + 24LL))(v38, &v37);
  v17 = v59;
  for ( j = 0; j < v37; ++j )
  {
    v11 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct INativeConfigurationElement **))(*(_QWORD *)v38 + 32LL))(
            v38,
            j,
            &v34);
    if ( v11 < 0 )
      goto LABEL_70;
    v57 = 0;
    *v54 = 0;
    v11 = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, const unsigned __int16 *, unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v34 + 64LL))(
            v34,
            L"path",
            &v39,
            0,
            0);
    if ( v11 < 0 )
      goto LABEL_70;
    v19 = v39;
    if ( *v39 != 47 )
    {
      v11 = STRU::Copy((STRU *)v53, (const unsigned __int8 *)L"/");
      if ( v11 < 0 )
        goto LABEL_70;
      v19 = v39;
    }
    v11 = STRU::Append((STRU *)v53, (const unsigned __int8 *)v19);
    if ( v11 < 0 )
      goto LABEL_70;
    v20 = v54;
    v21 = *v54 - 47;
    if ( *v54 == 47 )
      v21 = v54[1];
    if ( !v21 )
    {
      v22 = v17;
LABEL_43:
      v23 = STRU::Copy((STRU *)v43, (const unsigned __int8 *)v22);
      goto LABEL_50;
    }
    v24 = *v17 - 47;
    if ( *v17 == 47 )
      v24 = v17[1];
    if ( !v24 )
    {
      v22 = v54;
      goto LABEL_43;
    }
    v11 = STRU::Copy((STRU *)v43, (const unsigned __int8 *)v17);
    if ( v11 < 0 )
      goto LABEL_70;
    v23 = STRU::Append((STRU *)v43, (const unsigned __int8 *)v20);
LABEL_50:
    v11 = v23;
    if ( v23 < 0 )
      goto LABEL_70;
    v25 = v47;
    if ( (unsigned int)v47 <= 1 )
    {
LABEL_54:
      v26 = v44;
    }
    else
    {
      while ( 1 )
      {
        v26 = v44;
        v27 = v25 - 1;
        if ( v44[v27] != 47 )
          break;
        STRU::SetLen((STRU *)v43, v27);
        v25 = v47;
        if ( (unsigned int)v47 <= 1 )
          goto LABEL_54;
      }
    }
    v28 = v25;
    if ( !_wcsnicmp(v26, String2, v25) && (unsigned int)v28 > v32 )
    {
      v29 = *v26 - 47;
      if ( *v26 == 47 )
        v29 = v26[1];
      if ( !v29 || !String2[v28] || String2[v28] == 47 )
      {
        if ( v10 )
          (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v10 + 16LL))(v10);
        v10 = v34;
        (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v34 + 8LL))(v34);
        v32 = v28;
      }
    }
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  if ( v10 )
  {
    *v41 = v8;
    v8 = 0;
    *v42 = v10;
    v10 = 0;
  }
LABEL_70:
  if ( v38 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
    v38 = 0;
  }
  if ( v8 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v10 )
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v10 + 16LL))(v10);
  if ( v33 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v33 + 16LL))(v33);
    v33 = 0;
  }
  if ( v34 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v34 + 16LL))(v34);
    v34 = 0;
  }
  BUFFER::~BUFFER((BUFFER *)v43);
  BUFFER::~BUFFER((BUFFER *)v58);
  BUFFER::~BUFFER((BUFFER *)v53);
  BUFFER::~BUFFER((BUFFER *)v48);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x1800165d8  mov     [rsp-8+arg_0], rbx
0x1800165dd  push    rbp
0x1800165de  push    rsi
0x1800165df  push    rdi
0x1800165e0  push    r12
0x1800165e2  push    r13
0x1800165e4  push    r14
0x1800165e6  push    r15
0x1800165e8  lea     rbp, [rsp-870h]
0x1800165f0  sub     rsp, 970h
0x1800165f7  mov     rax, cs:__security_cookie
0x1800165fe  xor     rax, rsp
0x180016601  mov     [rbp+8A0h+var_40], rax
0x180016608  mov     r12, [rbp+8A0h+arg_20]
0x18001660f  lea     rcx, [rbp+8A0h+var_83E]; void *
0x180016613  xor     eax, eax
0x180016615  mov     [rsp+9A0h+var_930], r9
0x18001661a  mov     rbx, r8
0x18001661d  mov     [rsp+9A0h+var_928], r12
0x180016622  mov     r13, rdx
0x180016625  mov     [rsp+9A0h+var_950], eax
0x180016629  mov     r14d, 1FEh
0x18001662f  mov     [rsp+9A0h+var_94C], eax
0x180016633  mov     r8d, r14d; Size
0x180016636  mov     [rsp+9A0h+var_968], rax
0x18001663b  xor     edx, edx; Val
0x18001663d  mov     [rsp+9A0h+var_938], rax
0x180016642  mov     r15, r9
0x180016645  mov     [rsp+9A0h+var_940], rax
0x18001664a  mov     edi, eax
0x18001664c  call    memset_0
0x180016651  xor     ecx, ecx
0x180016653  mov     [rbp+8A0h+var_8BC], 100h
0x180016659  mov     dword ptr [rbp+8A0h+MaxCount], ecx
0x18001665c  lea     rax, [rbp+8A0h+var_840]
0x180016660  mov     [rbp+8A0h+var_840], cx
0x180016664  lea     esi, [r14+2]
0x180016668  lea     rcx, [rbp+8A0h+var_63E]; void *
0x18001666f  mov     [rbp+8A0h+String1], rax
0x180016673  mov     r8d, r14d; Size
0x180016676  mov     [rbp+8A0h+var_8C0], esi
0x180016679  xor     edx, edx; Val
0x18001667b  call    memset_0
0x180016680  lea     r14, [rbp+8A0h+var_640]
0x180016687  mov     [rbp+8A0h+var_888], esi
0x18001668a  xor     eax, eax
0x18001668c  mov     [rbp+8A0h+var_890], r14
0x180016690  lea     r14d, [rsi-2]
0x180016694  mov     [rbp+8A0h+var_884], 100h
0x18001669a  mov     r8d, r14d; Size
0x18001669d  mov     [rbp+8A0h+var_880], eax
0x1800166a0  xor     edx, edx; Val
0x1800166a2  mov     [rbp+8A0h+var_640], ax
0x1800166a9  lea     rcx, [rbp+8A0h+var_43E]; void *
0x1800166b0  call    memset_0
0x1800166b5  lea     rax, [rbp+8A0h+var_440]
0x1800166bc  mov     [rbp+8A0h+var_850], esi
0x1800166bf  mov     [rbp+8A0h+var_858], rax
0x1800166c3  lea     rcx, [rbp+8A0h+var_23E]; void *
0x1800166ca  xor     eax, eax
0x1800166cc  mov     [rbp+8A0h+var_84C], 100h
0x1800166d2  mov     r8d, r14d; Size
0x1800166d5  mov     [rbp+8A0h+var_848], eax
0x1800166d8  xor     edx, edx; Val
0x1800166da  mov     [rbp+8A0h+var_440], ax
0x1800166e1  call    memset_0
0x1800166e6  xor     r14d, r14d
0x1800166e9  mov     [rbp+8A0h+var_8F8], esi
0x1800166ec  mov     [rbp+8A0h+var_8F4], 100h
0x1800166f2  lea     rax, [rbp+8A0h+var_240]
0x1800166f9  mov     [rbp+8A0h+var_900], rax
0x1800166fd  mov     esi, r14d
0x180016700  mov     dword ptr [rbp+8A0h+var_8F0], r14d
0x180016704  mov     [rbp+8A0h+var_240], r14w
0x18001670c  mov     [rsp+9A0h+var_948], r14
0x180016711  mov     [rsp+9A0h+var_960], r14
0x180016716  mov     [rsp+9A0h+String2], r14
0x18001671b  test    r13, r13
0x18001671e  jz      loc_180016B59
0x180016724  test    rbx, rbx
0x180016727  jz      loc_180016B59
0x18001672d  test    r12, r12
0x180016730  jz      loc_180016B59
0x180016736  test    r15, r15
0x180016739  jz      loc_180016B59
0x18001673f  lea     r9, [rsp+9A0h+String2]; unsigned __int16 **
0x180016744  mov     [rsp+9A0h+var_980], r14; int *
0x180016749  xor     r8d, r8d; struct STRU *
0x18001674c  mov     rdx, rbx; unsigned __int16 *
0x18001674f  call    ?ResolveUrl@APP_OBJECT_UTILS@@QEAAJPEBGPEAVSTRU@@PEAPEBGPEAH@Z; APP_OBJECT_UTILS::ResolveUrl(ushort const *,STRU *,ushort const * *,int *)
0x180016754  mov     ebx, eax
0x180016756  test    eax, eax
0x180016758  js      loc_180016B5E
0x18001675e  cmp     [rsp+9A0h+String2], r14
0x180016763  jnz     short loc_18001676F
0x180016765  mov     ebx, 80070002h
0x18001676a  jmp     loc_180016B5E
0x18001676f  mov     rax, [r13+0]
0x180016773  lea     rdx, [rsp+9A0h+var_950]
0x180016778  mov     rcx, r13
0x18001677b  mov     [rsp+9A0h+var_970], r14d
0x180016780  mov     rax, [rax+18h]
0x180016784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016789  mov     r12d, r14d
0x18001678c  mov     r15d, 2Fh ; '/'
0x180016792  cmp     r12d, [rsp+9A0h+var_950]
0x180016797  jnb     loc_1800168E9
0x18001679d  mov     rax, [r13+0]
0x1800167a1  lea     r8, [rsp+9A0h+var_968]
0x1800167a6  mov     edx, r12d
0x1800167a9  mov     rcx, r13
0x1800167ac  mov     rax, [rax+20h]
0x1800167b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167b5  mov     ebx, eax
0x1800167b7  test    eax, eax
0x1800167b9  js      loc_180016B5E
0x1800167bf  mov     rcx, [rsp+9A0h+var_968]
0x1800167c4  lea     r8, [rsp+9A0h+var_938]
0x1800167c9  xor     r9d, r9d
0x1800167cc  mov     [rsp+9A0h+var_980], r14
0x1800167d1  lea     rdx, aPath_1; "path"
0x1800167d8  mov     rax, [rcx]
0x1800167db  mov     rax, [rax+40h]
0x1800167df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800167e4  mov     ebx, eax
0x1800167e6  test    eax, eax
0x1800167e8  js      loc_180016B5E
0x1800167ee  mov     rdx, [rsp+9A0h+var_938]; unsigned __int16 *
0x1800167f3  lea     rcx, [rbp+8A0h+var_8E8]; this
0x1800167f7  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800167fc  mov     ebx, eax
0x1800167fe  test    eax, eax
0x180016800  js      loc_180016B5E
0x180016806  jmp     short loc_18001681B
0x180016808  lea     edx, [rcx-1]; unsigned int
0x18001680b  cmp     [r14+rdx*2], r15w
0x180016810  jnz     short loc_180016827
0x180016812  lea     rcx, [rbp+8A0h+var_8E8]; this
0x180016816  call    ?SetLen@STRU@@QEAA_NK@Z; STRU::SetLen(ulong)
0x18001681b  mov     ecx, dword ptr [rbp+8A0h+MaxCount]
0x18001681e  mov     r14, [rbp+8A0h+String1]
0x180016822  cmp     ecx, 1
0x180016825  ja      short loc_180016808
0x180016827  mov     rdx, [rsp+9A0h+String2]; String2
0x18001682c  mov     r15d, ecx
0x18001682f  mov     r8d, ecx; MaxCount
0x180016832  mov     rcx, r14; String1
0x180016835  call    cs:__imp__wcsnicmp
0x18001683b  test    eax, eax
0x18001683d  jnz     loc_1800168C8
0x180016843  cmp     r15d, [rsp+9A0h+var_970]
0x180016848  jbe     short loc_1800168C8
0x18001684a  movzx   edx, word ptr [r14]
0x18001684e  lea     ecx, [rax+2Fh]
0x180016851  sub     edx, ecx
0x180016853  jnz     short loc_180016868
0x180016855  movzx   edx, word ptr [r14+2]
0x18001685a  xor     r14d, r14d
0x18001685d  movzx   ecx, r14w
0x180016861  sub     edx, ecx
0x180016863  lea     ecx, [rax+2Fh]
0x180016866  jmp     short loc_18001686B
0x180016868  xor     r14d, r14d
0x18001686b  test    edx, edx
0x18001686d  jz      short loc_180016882
0x18001686f  mov     rax, [rsp+9A0h+String2]
0x180016874  cmp     [rax+r15*2], r14w
0x180016879  jz      short loc_180016882
0x18001687b  cmp     [rax+r15*2], cx
0x180016880  jnz     short loc_1800168CB
0x180016882  test    rdi, rdi
0x180016885  jz      short loc_180016896
0x180016887  mov     rax, [rdi]
0x18001688a  mov     rcx, rdi
0x18001688d  mov     rax, [rax+10h]
0x180016891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016896  mov     rdi, [rsp+9A0h+var_968]
0x18001689b  mov     rcx, rdi
0x18001689e  mov     rax, [rdi]
0x1800168a1  mov     rax, [rax+8]
0x1800168a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168aa  lea     rdx, [rbp+8A0h+var_8E8]; struct STRU *
0x1800168ae  lea     rcx, [rbp+8A0h+var_878]; this
0x1800168b2  call    ?Copy@STRU@@QEAAJAEBV1@@Z; STRU::Copy(STRU const &)
0x1800168b7  mov     ebx, eax
0x1800168b9  test    eax, eax
0x1800168bb  js      loc_180016B5E
0x1800168c1  mov     [rsp+9A0h+var_970], r15d
0x1800168c6  jmp     short loc_1800168CB
0x1800168c8  xor     r14d, r14d
0x1800168cb  mov     rcx, [rsp+9A0h+var_968]
0x1800168d0  mov     rax, [rcx]
0x1800168d3  mov     rax, [rax+10h]
0x1800168d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168dc  inc     r12d
0x1800168df  mov     [rsp+9A0h+var_968], r14
0x1800168e4  jmp     loc_18001678C
0x1800168e9  test    rdi, rdi
0x1800168ec  jz      loc_180016B5E
0x1800168f2  mov     rax, [rdi]
0x1800168f5  lea     rdx, [rsp+9A0h+var_948]
0x1800168fa  mov     rcx, rdi
0x1800168fd  mov     rax, [rax+28h]
0x180016901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016906  mov     ebx, eax
0x180016908  test    eax, eax
0x18001690a  js      loc_180016B5E
0x180016910  mov     rcx, [rsp+9A0h+var_948]
0x180016915  lea     rdx, [rsp+9A0h+var_94C]
0x18001691a  mov     [rsp+9A0h+var_970], r14d
0x18001691f  mov     rax, [rcx]
0x180016922  mov     rax, [rax+18h]
0x180016926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001692b  mov     r12, [rbp+8A0h+var_858]
0x18001692f  mov     r13d, r14d
0x180016932  cmp     r13d, [rsp+9A0h+var_94C]
0x180016937  jnb     loc_180016B3C
0x18001693d  mov     rcx, [rsp+9A0h+var_948]
0x180016942  lea     r8, [rsp+9A0h+var_960]
0x180016947  mov     edx, r13d
0x18001694a  mov     rax, [rcx]
0x18001694d  mov     rax, [rax+20h]
0x180016951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016956  mov     ebx, eax
0x180016958  test    eax, eax
0x18001695a  js      loc_180016B5E
0x180016960  mov     rcx, [rbp+8A0h+var_890]
0x180016964  lea     r8, [rsp+9A0h+var_940]
0x180016969  xor     r9d, r9d
0x18001696c  mov     [rbp+8A0h+var_880], r14d
0x180016970  lea     rdx, aPath_1; "path"
0x180016977  mov     [rsp+9A0h+var_980], r14
0x18001697c  mov     [rcx], r14w
0x180016980  mov     rcx, [rsp+9A0h+var_960]
0x180016985  mov     rax, [rcx]
0x180016988  mov     rax, [rax+40h]
0x18001698c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016991  mov     ebx, eax
0x180016993  test    eax, eax
0x180016995  js      loc_180016B5E
0x18001699b  mov     rdx, [rsp+9A0h+var_940]
0x1800169a0  cmp     [rdx], r15w
0x1800169a4  jz      short loc_1800169C5
0x1800169a6  lea     rdx, SubStr; "/"
0x1800169ad  lea     rcx, [rbp+8A0h+var_8B0]; this
0x1800169b1  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800169b6  mov     ebx, eax
0x1800169b8  test    eax, eax
0x1800169ba  js      loc_180016B5E
0x1800169c0  mov     rdx, [rsp+9A0h+var_940]; unsigned __int16 *
0x1800169c5  lea     rcx, [rbp+8A0h+var_8B0]; this
0x1800169c9  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800169ce  mov     ebx, eax
0x1800169d0  test    eax, eax
0x1800169d2  js      loc_180016B5E
0x1800169d8  mov     r14, [rbp+8A0h+var_890]
0x1800169dc  movzx   eax, r15w
0x1800169e0  movzx   edx, word ptr [r14]
0x1800169e4  sub     edx, eax
0x1800169e6  jnz     short loc_1800169F8
0x1800169e8  movzx   edx, word ptr [r14+2]
0x1800169ed  xor     r15d, r15d
0x1800169f0  movzx   ecx, r15w
0x1800169f4  sub     edx, ecx
0x1800169f6  jmp     short loc_1800169FB
0x1800169f8  xor     r15d, r15d
0x1800169fb  test    edx, edx
0x1800169fd  jnz     short loc_180016A0D
0x1800169ff  mov     rdx, r12; unsigned __int16 *
0x180016a02  lea     rcx, [rbp+8A0h+var_920]; this
0x180016a06  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016a0b  jmp     short loc_180016A4E
0x180016a0d  movzx   edx, word ptr [r12]
0x180016a12  sub     edx, 2Fh ; '/'
0x180016a15  jnz     short loc_180016A23
0x180016a17  movzx   edx, word ptr [r12+2]
0x180016a1d  movzx   ecx, r15w
0x180016a21  sub     edx, ecx
0x180016a23  lea     rcx, [rbp+8A0h+var_920]; this
0x180016a27  test    edx, edx
0x180016a29  jnz     short loc_180016A30
0x180016a2b  mov     rdx, r14
0x180016a2e  jmp     short loc_180016A06
0x180016a30  mov     rdx, r12; unsigned __int16 *
0x180016a33  call    ?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180016a38  mov     ebx, eax
0x180016a3a  test    eax, eax
0x180016a3c  js      loc_180016B37
0x180016a42  mov     rdx, r14; unsigned __int16 *
0x180016a45  lea     rcx, [rbp+8A0h+var_920]; this
0x180016a49  call    ?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180016a4e  xor     r14d, r14d
0x180016a51  mov     ebx, eax
0x180016a53  test    eax, eax
0x180016a55  js      loc_180016B5E
0x180016a5b  mov     ecx, dword ptr [rbp+8A0h+var_8F0]
0x180016a5e  cmp     ecx, 1
0x180016a61  jbe     short loc_180016A86
0x180016a63  lea     r15d, [r14+2Fh]
0x180016a67  mov     r14, [rbp+8A0h+var_900]
  ... truncated ...
```
