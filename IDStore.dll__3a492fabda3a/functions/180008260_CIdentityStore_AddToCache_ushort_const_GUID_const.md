# CIdentityStore::AddToCache(ushort const *,_GUID const &)

- ea: `0x180008260`
- end: `0x1800088fd`
- name: `?AddToCache@CIdentityStore@@UEAAJPEBGAEBU_GUID@@@Z`
- size: `1693`
- prototype: `__int64 __fastcall(CIdentityStore *this, const unsigned __int16 *, const struct _GUID *)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180003560`
- `0x180008260`
- `0x18000a120`
- `0x18000f088`
- `0x180012a08`
- `0x180013ab0`
- `0x180013b00`
- `0x180013ff4`
- `0x18001448c`
- `0x1800144b4`
- `0x180014540`
- `0x1800145a0`
- `0x1800178a4`
- `0x1800191ac`
- `0x180019722`
- `0x180019750`
- `0x18001b010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x1800088f2`
- `msvcrt!??3@YAXPEAX@Z` at `0x1800088f2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083fc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008424`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000842e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180008424`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18000842e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800084de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000840c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000840c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800087e0`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800087e0`

## string_xrefs

- `0x1800082f0`: `CIdentityStore::AddToCache`

## pseudocode

```c
__int64 __fastcall CIdentityStore::AddToCache(CIdentityStore *this, const unsigned __int16 *a2, const struct _GUID *a3)
{
  CCachedIdentity *v6; // rbx
  struct IPropertyStore *v7; // rdx
  __int64 v8; // r8
  CIdentityProfileHandler *v9; // rcx
  __int64 v10; // rdi
  __int64 v11; // rax
  signed int LastError; // eax
  int Property; // eax
  int v14; // eax
  unsigned int v15; // esi
  void *v16; // rdi
  HANDLE ProcessHeap; // rax
  __int64 v19; // rdx
  __int64 v20; // r9
  const unsigned __int16 *String; // rax
  const unsigned __int16 *v22; // r15
  __int64 v23; // rcx
  unsigned int v24; // edx
  const unsigned __int16 *v25; // r14
  CCachedIdentity *v26; // rax
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v28; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL hMem; // [rsp+48h] [rbp-B8h] BYREF
  struct IPropertyStore *v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  struct IUnknown *v32; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpMem; // [rsp+68h] [rbp-98h] BYREF
  __int64 v34; // [rsp+70h] [rbp-90h]
  int v35; // [rsp+80h] [rbp-80h]
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  PROPVARIANT v38[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h]
  _QWORD v40[3]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE Sid[112]; // [rsp+D0h] [rbp-30h] BYREF

  v27 = -2147467259;
  v32 = 0;
  v31 = 0;
  v30 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  *(_OWORD *)pvar = 0;
  v37 = 0;
  v6 = 0;
  hMem = 0;
  memset_0(Sid, 0, 0x64u);
  v28 = 0;
  lpMem = 0;
  v34 = 0;
  v35 = 0;
  v40[1] = "CIdentityStore::AddToCache";
  v40[0] = &v27;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v8, "CIdentityStore::AddToCache");
    v9 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
    goto LABEL_28;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a2[v11] );
  if ( !v11 )
  {
LABEL_28:
    v27 = -2147024809;
    if ( v9 == (CIdentityProfileHandler *)&WPP_GLOBAL_Control || (*((_BYTE *)v9 + 28) & 4) == 0 )
      goto LABEL_15;
    v19 = 15;
    v20 = 2147942487LL;
LABEL_31:
    WPP_SF_d(*((_QWORD *)v9 + 2), v19, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, v20);
    goto LABEL_15;
  }
  LastError = CIdentityStore::VerifyAndLoadProvider(v9, a3, &v32, (struct CDynamicString *)&lpMem);
  v27 = LastError;
  if ( LastError < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 16;
    goto LABEL_40;
  }
  if ( !(_DWORD)v34 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids);
    }
    v27 = -2147024809;
    goto LABEL_15;
  }
  Property = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))v32->lpVtbl->QueryInterface)(
               v32,
               &GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5,
               &v31);
  v27 = Property;
  if ( Property < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 18;
    goto LABEL_48;
  }
  v14 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, struct IPropertyStore **))(*(_QWORD *)v31 + 56LL))(
          v31,
          a2,
          &v30);
  v27 = v14;
  if ( v14 < 0 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        19,
        (unsigned int)WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids,
        (_DWORD)a2,
        v14);
    }
    goto LABEL_15;
  }
  v7 = v30;
  if ( !v30 )
  {
    if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids, a2);
    }
    v27 = -2147467259;
    goto LABEL_15;
  }
  Property = CPropVariant::GetProperty((CPropVariant *)v38, v30, &PKEY_Identity_DisplayName);
  v27 = Property;
  if ( Property < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 21;
LABEL_48:
    v20 = (unsigned int)Property;
    goto LABEL_31;
  }
  String = CPropVariant::GetString((CPropVariant *)v38, (unsigned int)v7);
  v22 = String;
  if ( !String )
    goto LABEL_87;
  v23 = -1;
  do
    ++v23;
  while ( String[v23] );
  if ( !v23 )
  {
LABEL_87:
    v20 = 2147549183LL;
    v27 = -2147418113;
    v9 = WPP_GLOBAL_Control;
    v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 22;
    goto LABEL_31;
  }
  Property = CPropVariant::GetProperty((CPropVariant *)pvar, v30, &PKEY_Identity_UserName);
  v27 = Property;
  if ( Property < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 23;
    goto LABEL_48;
  }
  v25 = CPropVariant::GetString((CPropVariant *)pvar, v24);
  if ( !v25 )
    goto LABEL_84;
  do
    ++v10;
  while ( v25[v10] );
  if ( !v10 )
  {
LABEL_84:
    v20 = 2147549183LL;
    v27 = -2147418113;
    v9 = WPP_GLOBAL_Control;
    v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 24;
    goto LABEL_31;
  }
  v26 = (CCachedIdentity *)operator new(0xB0u);
  v6 = v26;
  if ( !v26 )
  {
    v6 = 0;
    goto LABEL_15;
  }
  *((_QWORD *)v26 + 2) = 0;
  *((_QWORD *)v26 + 3) = 0;
  *((_DWORD *)v26 + 10) = 0;
  *((_QWORD *)v26 + 6) = 0;
  *((_QWORD *)v26 + 7) = 0;
  *((_DWORD *)v26 + 18) = 0;
  *((_QWORD *)v26 + 10) = 0;
  *((_QWORD *)v26 + 11) = 0;
  *((_DWORD *)v26 + 26) = 0;
  *((_QWORD *)v26 + 14) = 0;
  *((_QWORD *)v26 + 15) = 0;
  *((_DWORD *)v26 + 34) = 0;
  *((_QWORD *)v26 + 18) = 0;
  *((_QWORD *)v26 + 19) = 0;
  *((_DWORD *)v26 + 42) = 0;
  *(_OWORD *)v26 = 0;
  LastError = (*(__int64 (__fastcall **)(CIdentityStore *, const unsigned __int16 *, const struct _GUID *, __int64, _BYTE *, __int16 *))(*(_QWORD *)this + 48LL))(
                this,
                a2,
                a3,
                100,
                Sid,
                &v28);
  v27 = LastError;
  if ( LastError < 0 )
  {
    v9 = WPP_GLOBAL_Control;
    v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 25;
    goto LABEL_40;
  }
  if ( ConvertSidToStringSidW(Sid, (LPWSTR *)&hMem) )
  {
    LastError = CCachedIdentity::Initialize(
                  v6,
                  a3,
                  (const unsigned __int16 *)lpMem,
                  v22,
                  v25,
                  (const unsigned __int16 *)hMem);
    v27 = LastError;
    if ( LastError >= 0 )
    {
      Property = CCachedIdentity::WriteToRegistry((struct _GUID *)v6);
      v27 = Property;
      if ( Property >= 0 )
        goto LABEL_15;
      v9 = WPP_GLOBAL_Control;
      v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
        goto LABEL_15;
      }
      v19 = 28;
      goto LABEL_48;
    }
    v9 = WPP_GLOBAL_Control;
    v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CIdentityProfileHandler *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
    {
      goto LABEL_15;
    }
    v19 = 27;
    goto LABEL_40;
  }
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  v27 = LastError;
  v9 = WPP_GLOBAL_Control;
  v7 = (struct IPropertyStore *)&WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CIdentityProfileHandler *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v19 = 26;
LABEL_40:
    v20 = (unsigned int)LastError;
    goto LABEL_31;
  }
LABEL_15:
  v15 = v27;
  CLogBlock::~CLogBlock((CLogBlock *)v40, (__int64)v7, v8);
  v16 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v16);
  }
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  if ( v6 )
  {
    CCachedIdentity::~CCachedIdentity(v6);
    operator delete(v6);
  }
  PropVariantClear(pvar);
  PropVariantClear(v38);
  if ( v30 )
    ((void (__fastcall *)(struct IPropertyStore *))v30->lpVtbl->Release)(v30);
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  if ( v32 )
    ((void (__fastcall *)(struct IUnknown *))v32->lpVtbl->Release)(v32);
  return v15;
}

```

## disassembly

```asm
0x180008260  mov     [rsp-8+arg_18], rbx
0x180008265  push    rbp
0x180008266  push    rsi
0x180008267  push    rdi
0x180008268  push    r12
0x18000826a  push    r13
0x18000826c  push    r14
0x18000826e  push    r15
0x180008270  lea     rbp, [rsp-50h]
0x180008275  sub     rsp, 150h
0x18000827c  mov     rax, cs:__security_cookie
0x180008283  xor     rax, rsp
0x180008286  mov     [rbp+80h+var_40], rax
0x18000828a  mov     r12, r8
0x18000828d  mov     rsi, rdx
0x180008290  mov     r13, rcx
0x180008293  mov     [rsp+180h+var_140], 80004005h
0x18000829b  xor     r14d, r14d
0x18000829e  mov     [rsp+180h+var_120], r14
0x1800082a3  mov     [rsp+180h+var_128], r14
0x1800082a8  mov     [rsp+180h+var_130], r14
0x1800082ad  xorps   xmm0, xmm0
0x1800082b0  xor     eax, eax
0x1800082b2  movups  xmmword ptr [rbp+80h+var_E0], xmm0
0x1800082b6  mov     [rbp+80h+var_D0], rax
0x1800082ba  xorps   xmm1, xmm1
0x1800082bd  movups  xmmword ptr [rbp+80h+pvar], xmm1
0x1800082c1  mov     [rbp+80h+var_E8], rax
0x1800082c5  mov     ebx, r14d
0x1800082c8  mov     [rsp+180h+hMem], r14
0x1800082cd  xor     edx, edx; Val
0x1800082cf  lea     r8d, [r14+64h]; Size
0x1800082d3  lea     rcx, [rbp+80h+Sid]; void *
0x1800082d7  call    memset_0
0x1800082dc  mov     [rsp+180h+var_13C], r14w
0x1800082e2  mov     [rsp+180h+lpMem], r14
0x1800082e7  mov     [rsp+180h+var_110], r14
0x1800082ec  mov     [rbp+80h+var_100], r14d
0x1800082f0  lea     r9, aCidentitystore_3; "CIdentityStore::AddToCache"
0x1800082f7  mov     [rbp+80h+var_C0], r9
0x1800082fb  lea     rax, [rsp+180h+var_140]
0x180008300  mov     [rbp+80h+var_C8], rax
0x180008304  lea     r15, WPP_GLOBAL_Control
0x18000830b  mov     rcx, cs:WPP_GLOBAL_Control; this
0x180008312  cmp     rcx, r15
0x180008315  jz      short loc_180008324
0x180008317  test    dword ptr [rcx+1Ch], 400h
0x18000831e  jnz     loc_18000851C
0x180008324  test    rsi, rsi
0x180008327  jz      loc_1800084A3
0x18000832d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180008331  mov     rax, rdi
0x180008334  inc     rax
0x180008337  cmp     [rsi+rax*2], r14w
0x18000833c  jnz     short loc_180008334
0x18000833e  test    rax, rax
0x180008341  jz      loc_1800084A3
0x180008347  lea     r9, [rsp+180h+lpMem]; struct CDynamicString *
0x18000834c  lea     r8, [rsp+180h+var_120]; struct IUnknown **
0x180008351  mov     rdx, r12; struct _GUID *
0x180008354  call    ?VerifyAndLoadProvider@CIdentityStore@@AEAAJPEBU_GUID@@PEAPEAUIUnknown@@PEAVCDynamicString@@@Z; CIdentityStore::VerifyAndLoadProvider(_GUID const *,IUnknown * *,CDynamicString *)
0x180008359  mov     [rsp+180h+var_140], eax
0x18000835d  test    eax, eax
0x18000835f  js      loc_180008536
0x180008365  cmp     dword ptr [rsp+180h+var_110], r14d
0x18000836a  jz      loc_180008564
0x180008370  mov     rcx, [rsp+180h+var_120]
0x180008375  mov     rax, [rcx]
0x180008378  lea     r8, [rsp+180h+var_128]
0x18000837d  lea     rdx, _GUID_0d1b9e0c_e8ba_4f55_a81b_bce934b948f5
0x180008384  mov     rax, [rax]
0x180008387  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000838c  nop
0x18000838d  mov     [rsp+180h+var_140], eax
0x180008391  test    eax, eax
0x180008393  js      loc_180008598
0x180008399  mov     rcx, [rsp+180h+var_128]
0x18000839e  mov     rax, [rcx]
0x1800083a1  lea     r8, [rsp+180h+var_130]
0x1800083a6  mov     rdx, rsi
0x1800083a9  mov     rax, [rax+38h]
0x1800083ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083b2  mov     [rsp+180h+var_140], eax
0x1800083b6  test    eax, eax
0x1800083b8  jns     loc_1800085FE
0x1800083be  mov     rcx, cs:WPP_GLOBAL_Control
0x1800083c5  cmp     rcx, r15
0x1800083c8  jz      short loc_1800083D4
0x1800083ca  test    byte ptr [rcx+1Ch], 4
0x1800083ce  jnz     loc_1800085DD
0x1800083d4  mov     esi, [rsp+180h+var_140]
0x1800083d8  lea     rcx, [rbp+80h+var_C8]; this
0x1800083dc  call    ??1CLogBlock@@QEAA@XZ; CLogBlock::~CLogBlock(void)
0x1800083e1  mov     rdi, [rsp+180h+lpMem]
0x1800083e6  xor     r14d, r14d
0x1800083e9  test    rdi, rdi
0x1800083ec  jz      short loc_180008402
0x1800083ee  call    cs:__imp_GetProcessHeap
0x1800083f4  mov     r8, rdi; lpMem
0x1800083f7  xor     edx, edx; dwFlags
0x1800083f9  mov     rcx, rax; hHeap
0x1800083fc  call    cs:__imp_HeapFree
0x180008402  mov     rcx, [rsp+180h+hMem]; hMem
0x180008407  test    rcx, rcx
0x18000840a  jz      short loc_180008417
0x18000840c  call    cs:__imp_LocalFree
0x180008412  mov     [rsp+180h+hMem], r14
0x180008417  test    rbx, rbx
0x18000841a  jnz     loc_1800088E7
0x180008420  lea     rcx, [rbp+80h+pvar]; pvar
0x180008424  call    cs:__imp_PropVariantClear
0x18000842a  lea     rcx, [rbp+80h+var_E0]; pvar
0x18000842e  call    cs:__imp_PropVariantClear
0x180008434  nop
0x180008435  mov     rcx, [rsp+180h+var_130]
0x18000843a  test    rcx, rcx
0x18000843d  jz      short loc_18000844C
0x18000843f  mov     rax, [rcx]
0x180008442  mov     rax, [rax+10h]
0x180008446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000844b  nop
0x18000844c  mov     rcx, [rsp+180h+var_128]
0x180008451  test    rcx, rcx
0x180008454  jz      short loc_180008463
0x180008456  mov     rax, [rcx]
0x180008459  mov     rax, [rax+10h]
0x18000845d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008462  nop
0x180008463  mov     rcx, [rsp+180h+var_120]
0x180008468  test    rcx, rcx
0x18000846b  jz      short loc_18000847A
0x18000846d  mov     rdx, [rcx]
0x180008470  mov     rax, [rdx+10h]
0x180008474  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008479  nop
0x18000847a  mov     eax, esi
0x18000847c  mov     rcx, [rbp+80h+var_40]
0x180008480  xor     rcx, rsp; StackCookie
0x180008483  call    __security_check_cookie
0x180008488  mov     rbx, [rsp+180h+arg_18]
0x180008490  add     rsp, 150h
0x180008497  pop     r15
0x180008499  pop     r14
0x18000849b  pop     r13
0x18000849d  pop     r12
0x18000849f  pop     rdi
0x1800084a0  pop     rsi
0x1800084a1  pop     rbp
0x1800084a2  retn
0x1800084a3  mov     [rsp+180h+var_140], 80070057h
0x1800084ab  cmp     rcx, r15
0x1800084ae  jz      loc_1800083D4
0x1800084b4  test    byte ptr [rcx+1Ch], 4
0x1800084b8  jz      loc_1800083D4
0x1800084be  mov     edx, 0Fh
0x1800084c3  mov     r9d, 80070057h
0x1800084c9  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800084d0  mov     rcx, [rcx+10h]
0x1800084d4  call    WPP_SF_d
0x1800084d9  jmp     loc_1800083D4
0x1800084de  call    cs:__imp_GetLastError
0x1800084e4  test    eax, eax
0x1800084e6  jle     short loc_1800084F0
0x1800084e8  movzx   eax, ax
0x1800084eb  or      eax, 80070000h
0x1800084f0  mov     [rsp+180h+var_140], eax
0x1800084f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800084fb  lea     rdx, WPP_GLOBAL_Control
0x180008502  cmp     rcx, rdx
0x180008505  jz      loc_1800083D4
0x18000850b  test    byte ptr [rcx+1Ch], 4
0x18000850f  jz      loc_1800083D4
0x180008515  mov     edx, 1Ah
0x18000851a  jmp     short loc_18000855C
0x18000851c  mov     edx, 0Ah
0x180008521  mov     rcx, [rcx+10h]
0x180008525  call    WPP_SF_s
0x18000852a  mov     rcx, cs:WPP_GLOBAL_Control
0x180008531  jmp     loc_180008324
0x180008536  mov     rcx, cs:WPP_GLOBAL_Control
0x18000853d  cmp     rcx, r15
0x180008540  jz      loc_1800083D4
0x180008546  test    byte ptr [rcx+1Ch], 4
0x18000854a  jz      loc_1800083D4
0x180008550  mov     edx, 10h
0x180008555  jmp     short loc_18000855C
0x180008557  mov     edx, 1Bh
0x18000855c  mov     r9d, eax
0x18000855f  jmp     loc_1800084C9
0x180008564  mov     rcx, cs:WPP_GLOBAL_Control
0x18000856b  cmp     rcx, r15
0x18000856e  jz      short loc_18000858B
0x180008570  test    byte ptr [rcx+1Ch], 4
0x180008574  jz      short loc_18000858B
0x180008576  mov     edx, 11h
0x18000857b  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180008582  mov     rcx, [rcx+10h]
0x180008586  call    WPP_SF_
0x18000858b  mov     [rsp+180h+var_140], 80070057h
0x180008593  jmp     loc_1800083D4
0x180008598  mov     rcx, cs:WPP_GLOBAL_Control
0x18000859f  cmp     rcx, r15
0x1800085a2  jz      loc_1800083D4
0x1800085a8  test    byte ptr [rcx+1Ch], 4
0x1800085ac  jz      loc_1800083D4
0x1800085b2  mov     edx, 12h
0x1800085b7  jmp     short loc_1800085BE
0x1800085b9  mov     edx, 1Ch
0x1800085be  mov     r9d, eax
0x1800085c1  jmp     short loc_1800085C8
0x1800085c3  mov     edx, 18h
0x1800085c8  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800085cf  mov     rcx, [rcx+10h]
0x1800085d3  call    WPP_SF_d
0x1800085d8  jmp     loc_1800083D4
0x1800085dd  mov     edx, 13h
0x1800085e2  mov     dword ptr [rsp+180h+var_160], eax
0x1800085e6  mov     r9, rsi
0x1800085e9  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x1800085f0  mov     rcx, [rcx+10h]
0x1800085f4  call    WPP_SF_Sd
0x1800085f9  jmp     loc_1800083D4
0x1800085fe  mov     rdx, [rsp+180h+var_130]; struct IPropertyStore *
0x180008603  test    rdx, rdx
0x180008606  jnz     short loc_18000863F
0x180008608  mov     rcx, cs:WPP_GLOBAL_Control
0x18000860f  cmp     rcx, r15
0x180008612  jz      short loc_180008632
0x180008614  test    byte ptr [rcx+1Ch], 4
0x180008618  jz      short loc_180008632
0x18000861a  mov     edx, 14h
0x18000861f  mov     r9, rsi
0x180008622  lea     r8, WPP_1f14484c8e8b36d0bb5abfbf243c1474_Traceguids
0x180008629  mov     rcx, [rcx+10h]
0x18000862d  call    WPP_SF_S
0x180008632  mov     [rsp+180h+var_140], 80004005h
0x18000863a  jmp     loc_1800083D4
0x18000863f  lea     r8, PKEY_Identity_DisplayName; struct _tagpropertykey *
0x180008646  lea     rcx, [rbp+80h+var_E0]; this
0x18000864a  call    ?GetProperty@CPropVariant@@QEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; CPropVariant::GetProperty(IPropertyStore *,_tagpropertykey const &)
0x18000864f  mov     [rsp+180h+var_140], eax
0x180008653  test    eax, eax
0x180008655  jns     short loc_18000867B
0x180008657  mov     rcx, cs:WPP_GLOBAL_Control
0x18000865e  cmp     rcx, r15
0x180008661  jz      loc_1800083D4
0x180008667  test    byte ptr [rcx+1Ch], 4
0x18000866b  jz      loc_1800083D4
0x180008671  mov     edx, 15h
0x180008676  jmp     loc_1800085BE
0x18000867b  lea     rcx, [rbp+80h+var_E0]; this
0x18000867f  call    ?GetString@CPropVariant@@QEBAPEBGK@Z; CPropVariant::GetString(ulong)
0x180008684  mov     r15, rax
0x180008687  test    rax, rax
0x18000868a  jz      loc_1800088B1
0x180008690  mov     rcx, rdi
0x180008693  inc     rcx
0x180008696  cmp     [rax+rcx*2], r14w
0x18000869b  jnz     short loc_180008693
0x18000869d  test    rcx, rcx
0x1800086a0  jz      loc_1800088B1
0x1800086a6  lea     r8, PKEY_Identity_UserName; struct _tagpropertykey *
0x1800086ad  mov     rdx, [rsp+180h+var_130]; struct IPropertyStore *
0x1800086b2  lea     rcx, [rbp+80h+pvar]; this
0x1800086b6  call    ?GetProperty@CPropVariant@@QEAAJPEAUIPropertyStore@@AEBU_tagpropertykey@@@Z; CPropVariant::GetProperty(IPropertyStore *,_tagpropertykey const &)
0x1800086bb  mov     [rsp+180h+var_140], eax
0x1800086bf  test    eax, eax
0x1800086c1  jns     short loc_1800086EE
0x1800086c3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800086ca  lea     rdx, WPP_GLOBAL_Control
0x1800086d1  cmp     rcx, rdx
0x1800086d4  jz      loc_1800083D4
0x1800086da  test    byte ptr [rcx+1Ch], 4
0x1800086de  jz      loc_1800083D4
0x1800086e4  mov     edx, 17h
0x1800086e9  jmp     loc_1800085BE
0x1800086ee  lea     rcx, [rbp+80h+pvar]; this
0x1800086f2  call    ?GetString@CPropVariant@@QEBAPEBGK@Z; CPropVariant::GetString(ulong)
0x1800086f7  mov     r14, rax
0x1800086fa  xor     eax, eax
0x1800086fc  test    r14, r14
0x1800086ff  jz      loc_180008880
0x180008705  inc     rdi
0x180008708  cmp     [r14+rdi*2], ax
0x18000870d  jnz     short loc_180008705
0x18000870f  test    rdi, rdi
0x180008712  jz      loc_180008880
0x180008718  mov     ecx, 0B0h; Size
0x18000871d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180008722  mov     rbx, rax
0x180008725  xor     edi, edi
0x180008727  test    rax, rax
0x18000872a  jz      loc_180008878
0x180008730  mov     [rax+10h], rdi
0x180008734  mov     [rax+18h], rdi
0x180008738  mov     [rax+28h], edi
0x18000873b  mov     [rax+30h], rdi
0x18000873f  mov     [rax+38h], rdi
0x180008743  mov     [rax+48h], edi
0x180008746  mov     [rax+50h], rdi
  ... truncated ...
```
