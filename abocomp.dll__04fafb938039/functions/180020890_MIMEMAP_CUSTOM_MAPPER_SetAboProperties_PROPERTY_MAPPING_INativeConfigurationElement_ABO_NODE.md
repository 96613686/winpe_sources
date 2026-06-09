# MIMEMAP_CUSTOM_MAPPER::SetAboProperties(PROPERTY_MAPPING *,INativeConfigurationElement *,ABO_NODE *)

- ea: `0x180020890`
- end: `0x180020dc1`
- name: `?SetAboProperties@MIMEMAP_CUSTOM_MAPPER@@UEAAJPEAVPROPERTY_MAPPING@@PEAVINativeConfigurationElement@@PEAVABO_NODE@@@Z`
- size: `1329`
- prototype: `__int64 __fastcall(MIMEMAP_CUSTOM_MAPPER *__hidden this, struct PROPERTY_MAPPING *, struct INativeConfigurationElement *, struct ABO_NODE *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x18000341a`
- `0x180003426`
- `0x180003460`
- `0x18000473c`
- `0x180007148`
- `0x180009818`
- `0x18000a6fc`
- `0x18001d190`
- `0x180020890`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180020c8a`
- `msvcrt!_wcsicmp` at `0x180020c8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b2e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b2e`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020acb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020c66`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020acb`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180020c66`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180020bc6`
- `iisutil!?Reset@MULTISZ@@QEAAXXZ` at `0x180020bc6`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020905`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002092a`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180020905`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18002092a`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020d85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020d8f`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020d85`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180020d8f`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020b13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020c59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020c7a`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020b13`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020c59`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x180020c7a`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180020ae6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180020aff`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180020ae6`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x180020aff`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002093a`
- `iisutil!??0MULTISZ@@QEAA@XZ` at `0x18002093a`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180020c3b`
- `iisutil!?QueryStr@MULTISZ@@QEBAPEAGXZ` at `0x180020c3b`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180020b20`
- `iisutil!?Append@MULTISZ@@QEAAHPEBG@Z` at `0x180020b20`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x180020c49`
- `iisutil!?QueryCB@MULTISZ@@QEBAIXZ` at `0x180020c49`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180020d7b`
- `iisutil!??1MULTISZ@@QEAA@XZ` at `0x180020d7b`

## string_xrefs

- `0x180020a4f`: `fileExtension`
- `0x180020b6b`: `fileExtension`
- `0x180020b4c`: `remove`

## pseudocode

```c
__int64 __fastcall MIMEMAP_CUSTOM_MAPPER::SetAboProperties(
        MIMEMAP_CUSTOM_MAPPER *this,
        struct PROPERTY_MAPPING *a2,
        struct INativeConfigurationElement *a3,
        struct ABO_NODE *a4)
{
  ABO_NODE *v8; // rdi
  int MergedConfigElement; // ebx
  unsigned int v10; // eax
  unsigned int v11; // r14d
  wchar_t *v12; // rsi
  int v13; // eax
  const unsigned __int16 *Str; // rax
  signed int LastError; // eax
  __int64 v16; // rcx
  const unsigned __int16 *v17; // rax
  const wchar_t *v18; // rax
  struct ABO_NODE *v19; // rcx
  __int64 v21; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v22; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t *String2; // [rsp+48h] [rbp-B8h] BYREF
  struct INativeConfigurationElement *v25; // [rsp+50h] [rbp-B0h] BYREF
  ABO_NODE *v26; // [rsp+58h] [rbp-A8h] BYREF
  wchar_t *String1; // [rsp+60h] [rbp-A0h] BYREF
  const unsigned __int16 *v28; // [rsp+68h] [rbp-98h] BYREF
  struct _METADATA_RECORD v29; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v30[56]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v31[56]; // [rsp+D0h] [rbp-30h] BYREF
  _BYTE v32[56]; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int16 v33[256]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v34[256]; // [rsp+340h] [rbp+240h] BYREF

  v25 = 0;
  v21 = 0;
  String1 = 0;
  v23 = 0;
  memset_0(v33, 0, sizeof(v33));
  STRU::STRU((STRU *)v31, v33, 0x100u);
  memset_0(v34, 0, sizeof(v34));
  STRU::STRU((STRU *)v32, v34, 0x100u);
  v22 = 0;
  MULTISZ::MULTISZ((MULTISZ *)v30);
  String2 = 0;
  v8 = 0;
  v28 = 0;
  v26 = 0;
  if ( !a2 || !a3 || !a4 )
  {
    MergedConfigElement = -2147024809;
    goto LABEL_40;
  }
  MergedConfigElement = ABO_NODE::GetMergedConfigElement(
                          a4,
                          L"system.webServer/staticContent",
                          &v25,
                          *((_DWORD *)a2 + 43) & 1);
  if ( MergedConfigElement < 0
    || (MergedConfigElement = (*(__int64 (__fastcall **)(struct INativeConfigurationElement *, __int64 *))(*(_QWORD *)v25 + 40LL))(
                                v25,
                                &v23),
        MergedConfigElement < 0)
    || (MergedConfigElement = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v23 + 72LL))(v23, &v22),
        MergedConfigElement < 0) )
  {
LABEL_42:
    v16 = v21;
    goto LABEL_43;
  }
  v10 = v22;
  v11 = 0;
  if ( v22 )
  {
    while ( 1 )
    {
      MergedConfigElement = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v23 + 80LL))(
                              v23,
                              v11,
                              &v21);
      if ( MergedConfigElement < 0 )
        goto LABEL_42;
      MergedConfigElement = (*(__int64 (__fastcall **)(__int64, wchar_t **))(*(_QWORD *)v21 + 24LL))(v21, &String1);
      if ( MergedConfigElement < 0 )
        goto LABEL_42;
      v12 = String1;
      if ( !wcscmp_0(String1, L"mimeMap") )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                                v21,
                                L"fileExtension",
                                &String2,
                                0,
                                0);
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
        v13 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, const unsigned __int16 **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                v21,
                L"mimeType",
                &v28,
                0,
                0);
        MergedConfigElement = v13;
        if ( v13 < 0 )
        {
          if ( v13 != -2147023483 )
            goto LABEL_42;
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
          MergedConfigElement = 0;
          goto LABEL_28;
        }
        MergedConfigElement = STRU::Copy((STRU *)v31, String2);
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
        MergedConfigElement = STRU::Append((STRU *)v31, L",");
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
        MergedConfigElement = STRU::Append((STRU *)v31, v28);
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
        Str = STRU::QueryStr((STRU *)v31);
        if ( !MULTISZ::Append((MULTISZ *)v30, Str) )
        {
          LastError = GetLastError();
          MergedConfigElement = LastError;
          if ( LastError > 0 )
            MergedConfigElement = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_42;
        }
      }
      else if ( !wcscmp_0(v12, L"remove") )
      {
        MergedConfigElement = (*(__int64 (__fastcall **)(__int64, const wchar_t *, wchar_t **, _QWORD, _QWORD))(*(_QWORD *)v21 + 64LL))(
                                v21,
                                L"fileExtension",
                                &String2,
                                0,
                                0);
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
        MergedConfigElement = MIMEMAP_CUSTOM_MAPPER::RemoveMimeMap(this, (struct MULTISZ *)v30, String2);
        if ( MergedConfigElement < 0 )
          goto LABEL_42;
      }
      else if ( !wcscmp_0(v12, L"clear") )
      {
        MULTISZ::Reset((MULTISZ *)v30);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
LABEL_28:
      v10 = v22;
      ++v11;
      v16 = 0;
      v21 = 0;
      if ( v11 >= v22 )
        goto LABEL_31;
    }
  }
  v16 = v21;
LABEL_31:
  if ( v10 )
  {
    v29.dwMDIdentifier = *((_DWORD *)a2 + 36);
    v29.dwMDUserType = *((_DWORD *)a2 + 37);
    v29.dwMDDataType = *((_DWORD *)a2 + 38);
    v29.dwMDAttributes = *((_DWORD *)a2 + 39);
    *(&v29.dwMDDataLen + 1) = 0;
    *(_QWORD *)&v29.dwMDDataTag = 0;
    v29.pbMDData = (unsigned __int8 *)MULTISZ::QueryStr((MULTISZ *)v30);
    v29.dwMDDataLen = MULTISZ::QueryCB((MULTISZ *)v30);
    v17 = STRU::QueryStr((struct ABO_NODE *)((char *)a4 + 256));
    MergedConfigElement = STRU::Copy((STRU *)v32, v17);
    if ( MergedConfigElement >= 0 )
    {
      v18 = STRU::QueryStr((STRU *)v32);
      if ( _wcsicmp(v18, L"/LM/W3SVC") )
      {
        v19 = a4;
      }
      else
      {
        MergedConfigElement = ABO_NODE::CreateNode(
                                *(struct ABO_TREE ***)(*((_QWORD *)a4 + 22) + 16LL),
                                L"/LM/MIMEMAP",
                                1,
                                &v26,
                                0);
        if ( MergedConfigElement < 0 )
        {
          v8 = v26;
          goto LABEL_40;
        }
        v8 = v26;
        v19 = v26;
      }
      MergedConfigElement = ABO_NODE::SetData(v19, &v29, 1);
LABEL_40:
      if ( v8 )
        ABO_NODE::DereferenceAboNode(v8);
      goto LABEL_42;
    }
    goto LABEL_42;
  }
LABEL_43:
  if ( v23 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v16 = v21;
    v23 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v16 = 0;
    v21 = 0;
  }
  if ( v25 )
  {
    (*(void (__fastcall **)(struct INativeConfigurationElement *))(*(_QWORD *)v25 + 16LL))(v25);
    v16 = v21;
    v25 = 0;
  }
  if ( v16 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v21 = 0;
  }
  MULTISZ::~MULTISZ((MULTISZ *)v30);
  STRU::~STRU((STRU *)v32);
  STRU::~STRU((STRU *)v31);
  return (unsigned int)MergedConfigElement;
}

```

## disassembly

```asm
0x180020890  mov     [rsp-8+arg_8], rbx
0x180020895  push    rbp
0x180020896  push    rsi
0x180020897  push    rdi
0x180020898  push    r12
0x18002089a  push    r13
0x18002089c  push    r14
0x18002089e  push    r15
0x1800208a0  lea     rbp, [rsp-450h]
0x1800208a8  sub     rsp, 550h
0x1800208af  mov     rax, cs:__security_cookie
0x1800208b6  xor     rax, rsp
0x1800208b9  mov     [rbp+480h+var_40], rax
0x1800208c0  xor     eax, eax
0x1800208c2  mov     rbx, r8
0x1800208c5  mov     r13, rdx
0x1800208c8  mov     [rsp+580h+var_530], rax
0x1800208cd  mov     r12, rcx
0x1800208d0  mov     [rsp+580h+var_550], rax
0x1800208d5  mov     esi, 200h
0x1800208da  mov     [rsp+580h+String1], rax
0x1800208df  mov     r8d, esi; Size
0x1800208e2  mov     [rsp+580h+var_540], rax
0x1800208e7  xor     edx, edx; Val
0x1800208e9  lea     rcx, [rbp+480h+var_440]; void *
0x1800208ed  mov     r15, r9
0x1800208f0  call    memset_0
0x1800208f5  mov     edi, 100h
0x1800208fa  lea     rdx, [rbp+480h+var_440]
0x1800208fe  mov     r8d, edi
0x180020901  lea     rcx, [rbp+480h+var_4B0]
0x180020905  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18002090b  mov     r8d, esi; Size
0x18002090e  lea     rcx, [rbp+480h+var_240]; void *
0x180020915  xor     edx, edx; Val
0x180020917  call    memset_0
0x18002091c  mov     r8d, edi
0x18002091f  lea     rdx, [rbp+480h+var_240]
0x180020926  lea     rcx, [rbp+480h+var_478]
0x18002092a  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x180020930  xor     esi, esi
0x180020932  lea     rcx, [rbp+480h+var_4E8]
0x180020936  mov     [rsp+580h+var_548], esi
0x18002093a  call    cs:__imp_??0MULTISZ@@QEAA@XZ; MULTISZ::MULTISZ(void)
0x180020940  mov     [rsp+580h+String2], rsi
0x180020945  mov     edi, esi
0x180020947  mov     [rsp+580h+var_518], rsi
0x18002094c  mov     [rsp+580h+var_528], rsi
0x180020951  test    r13, r13
0x180020954  jz      loc_180020CEB
0x18002095a  test    rbx, rbx
0x18002095d  jz      loc_180020CEB
0x180020963  test    r15, r15
0x180020966  jz      loc_180020CEB
0x18002096c  mov     r9d, [r13+0ACh]
0x180020973  lea     r8, [rsp+580h+var_530]; struct INativeConfigurationElement **
0x180020978  and     r9d, 1; int
0x18002097c  lea     rdx, aSystemWebserve_0; "system.webServer/staticContent"
0x180020983  mov     rcx, r15; this
0x180020986  call    ?GetMergedConfigElement@ABO_NODE@@QEAAJPEBGPEAPEAVINativeConfigurationElement@@H@Z; ABO_NODE::GetMergedConfigElement(ushort const *,INativeConfigurationElement * *,int)
0x18002098b  mov     ebx, eax
0x18002098d  test    eax, eax
0x18002098f  js      loc_180020CFD
0x180020995  mov     rcx, [rsp+580h+var_530]
0x18002099a  lea     rdx, [rsp+580h+var_540]
0x18002099f  mov     rax, [rcx]
0x1800209a2  mov     rax, [rax+28h]
0x1800209a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209ab  mov     ebx, eax
0x1800209ad  test    eax, eax
0x1800209af  js      loc_180020CFD
0x1800209b5  mov     rcx, [rsp+580h+var_540]
0x1800209ba  lea     rdx, [rsp+580h+var_548]
0x1800209bf  mov     rax, [rcx]
0x1800209c2  mov     rax, [rax+48h]
0x1800209c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209cb  mov     ebx, eax
0x1800209cd  test    eax, eax
0x1800209cf  js      loc_180020CFD
0x1800209d5  mov     eax, [rsp+580h+var_548]
0x1800209d9  mov     r14d, esi
0x1800209dc  test    eax, eax
0x1800209de  jz      loc_180020BF7
0x1800209e4  mov     rcx, [rsp+580h+var_540]
0x1800209e9  lea     r8, [rsp+580h+var_550]
0x1800209ee  mov     edx, r14d
0x1800209f1  mov     rax, [rcx]
0x1800209f4  mov     rax, [rax+50h]
0x1800209f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800209fd  mov     ebx, eax
0x1800209ff  test    eax, eax
0x180020a01  js      loc_180020CFD
0x180020a07  mov     rcx, [rsp+580h+var_550]
0x180020a0c  lea     rdx, [rsp+580h+String1]
0x180020a11  mov     rax, [rcx]
0x180020a14  mov     rax, [rax+18h]
0x180020a18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a1d  mov     ebx, eax
0x180020a1f  test    eax, eax
0x180020a21  js      loc_180020CFD
0x180020a27  mov     rsi, [rsp+580h+String1]
0x180020a2c  lea     rdx, aMimemap_0; "mimeMap"
0x180020a33  mov     rcx, rsi; String1
0x180020a36  call    wcscmp_0
0x180020a3b  test    eax, eax
0x180020a3d  jnz     loc_180020B4C
0x180020a43  mov     rcx, [rsp+580h+var_550]
0x180020a48  lea     r8, [rsp+580h+String2]
0x180020a4d  xor     esi, esi
0x180020a4f  lea     rdx, aFileextension; "fileExtension"
0x180020a56  xor     r9d, r9d
0x180020a59  mov     qword ptr [rsp+580h+var_560], rsi
0x180020a5e  mov     rax, [rcx]
0x180020a61  mov     rax, [rax+40h]
0x180020a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a6a  mov     ebx, eax
0x180020a6c  test    eax, eax
0x180020a6e  js      loc_180020CFD
0x180020a74  mov     rcx, [rsp+580h+var_550]
0x180020a79  lea     r8, [rsp+580h+var_518]
0x180020a7e  xor     r9d, r9d
0x180020a81  mov     qword ptr [rsp+580h+var_560], rsi
0x180020a86  lea     rdx, aMimetype; "mimeType"
0x180020a8d  mov     rax, [rcx]
0x180020a90  mov     rax, [rax+40h]
0x180020a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a99  mov     ebx, eax
0x180020a9b  test    eax, eax
0x180020a9d  jns     short loc_180020AC2
0x180020a9f  cmp     eax, 80070585h
0x180020aa4  jnz     loc_180020CFD
0x180020aaa  mov     rcx, [rsp+580h+var_550]
0x180020aaf  mov     rax, [rcx]
0x180020ab2  mov     rax, [rax+10h]
0x180020ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020abb  mov     ebx, esi
0x180020abd  jmp     loc_180020BDD
0x180020ac2  mov     rdx, [rsp+580h+String2]
0x180020ac7  lea     rcx, [rbp+480h+var_4B0]
0x180020acb  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180020ad1  mov     ebx, eax
0x180020ad3  test    eax, eax
0x180020ad5  js      loc_180020CFD
0x180020adb  lea     rdx, asc_180032E60; ","
0x180020ae2  lea     rcx, [rbp+480h+var_4B0]
0x180020ae6  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180020aec  mov     ebx, eax
0x180020aee  test    eax, eax
0x180020af0  js      loc_180020CFD
0x180020af6  mov     rdx, [rsp+580h+var_518]
0x180020afb  lea     rcx, [rbp+480h+var_4B0]
0x180020aff  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x180020b05  mov     ebx, eax
0x180020b07  test    eax, eax
0x180020b09  js      loc_180020CFD
0x180020b0f  lea     rcx, [rbp+480h+var_4B0]
0x180020b13  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180020b19  mov     rdx, rax
0x180020b1c  lea     rcx, [rbp+480h+var_4E8]
0x180020b20  call    cs:__imp_?Append@MULTISZ@@QEAAHPEBG@Z; MULTISZ::Append(ushort const *)
0x180020b26  test    eax, eax
0x180020b28  jnz     loc_180020BCC
0x180020b2e  call    cs:__imp_GetLastError
0x180020b34  mov     ebx, eax
0x180020b36  test    eax, eax
0x180020b38  jle     loc_180020CFD
0x180020b3e  movzx   ebx, ax
0x180020b41  or      ebx, 80070000h
0x180020b47  jmp     loc_180020CFD
0x180020b4c  lea     rdx, aRemove; "remove"
0x180020b53  mov     rcx, rsi; String1
0x180020b56  call    wcscmp_0
0x180020b5b  test    eax, eax
0x180020b5d  jnz     short loc_180020BAD
0x180020b5f  mov     rcx, [rsp+580h+var_550]
0x180020b64  lea     r8, [rsp+580h+String2]
0x180020b69  xor     esi, esi
0x180020b6b  lea     rdx, aFileextension; "fileExtension"
0x180020b72  xor     r9d, r9d
0x180020b75  mov     qword ptr [rsp+580h+var_560], rsi
0x180020b7a  mov     rax, [rcx]
0x180020b7d  mov     rax, [rax+40h]
0x180020b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b86  mov     ebx, eax
0x180020b88  test    eax, eax
0x180020b8a  js      loc_180020CFD
0x180020b90  mov     r8, [rsp+580h+String2]; String2
0x180020b95  lea     rdx, [rbp+480h+var_4E8]; struct MULTISZ *
0x180020b99  mov     rcx, r12; this
0x180020b9c  call    ?RemoveMimeMap@MIMEMAP_CUSTOM_MAPPER@@AEAAJPEAVMULTISZ@@PEBG@Z; MIMEMAP_CUSTOM_MAPPER::RemoveMimeMap(MULTISZ *,ushort const *)
0x180020ba1  mov     ebx, eax
0x180020ba3  test    eax, eax
0x180020ba5  js      loc_180020CFD
0x180020bab  jmp     short loc_180020BCC
0x180020bad  lea     rdx, aClear; "clear"
0x180020bb4  mov     rcx, rsi; String1
0x180020bb7  call    wcscmp_0
0x180020bbc  xor     esi, esi
0x180020bbe  test    eax, eax
0x180020bc0  jnz     short loc_180020BCC
0x180020bc2  lea     rcx, [rbp+480h+var_4E8]
0x180020bc6  call    cs:__imp_?Reset@MULTISZ@@QEAAXXZ; MULTISZ::Reset(void)
0x180020bcc  mov     rcx, [rsp+580h+var_550]
0x180020bd1  mov     rax, [rcx]
0x180020bd4  mov     rax, [rax+10h]
0x180020bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bdd  mov     eax, [rsp+580h+var_548]
0x180020be1  inc     r14d
0x180020be4  mov     rcx, rsi
0x180020be7  mov     [rsp+580h+var_550], rcx
0x180020bec  cmp     r14d, eax
0x180020bef  jb      loc_1800209E4
0x180020bf5  jmp     short loc_180020BFC
0x180020bf7  mov     rcx, [rsp+580h+var_550]
0x180020bfc  test    eax, eax
0x180020bfe  jz      loc_180020D02
0x180020c04  mov     eax, [r13+90h]
0x180020c0b  lea     rcx, [rbp+480h+var_4E8]
0x180020c0f  mov     [rsp+580h+var_510.dwMDIdentifier], eax
0x180020c13  mov     eax, [r13+94h]
0x180020c1a  mov     [rsp+580h+var_510.dwMDUserType], eax
0x180020c1e  mov     eax, [r13+98h]
0x180020c25  mov     [rsp+580h+var_510.dwMDDataType], eax
0x180020c29  mov     eax, [r13+9Ch]
0x180020c30  mov     [rsp+580h+var_510.dwMDAttributes], eax
0x180020c34  mov     dword ptr [rbp+480h+var_510+14h], esi
0x180020c37  mov     qword ptr [rbp+480h+var_510.dwMDDataTag], rsi
0x180020c3b  call    cs:__imp_?QueryStr@MULTISZ@@QEBAPEAGXZ; MULTISZ::QueryStr(void)
0x180020c41  lea     rcx, [rbp+480h+var_4E8]
0x180020c45  mov     [rbp+480h+var_510.pbMDData], rax
0x180020c49  call    cs:__imp_?QueryCB@MULTISZ@@QEBAIXZ; MULTISZ::QueryCB(void)
0x180020c4f  lea     rcx, [r15+100h]
0x180020c56  mov     [rbp+480h+var_510.dwMDDataLen], eax
0x180020c59  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180020c5f  mov     rdx, rax
0x180020c62  lea     rcx, [rbp+480h+var_478]
0x180020c66  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180020c6c  mov     ebx, eax
0x180020c6e  test    eax, eax
0x180020c70  js      loc_180020CFD
0x180020c76  lea     rcx, [rbp+480h+var_478]
0x180020c7a  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x180020c80  mov     rcx, rax; String1
0x180020c83  lea     rdx, aLmW3svc_0; "/LM/W3SVC"
0x180020c8a  call    cs:__imp__wcsicmp
0x180020c90  test    eax, eax
0x180020c92  jnz     short loc_180020CD4
0x180020c94  mov     rcx, [r15+0B0h]
0x180020c9b  lea     edi, [rax+1]
0x180020c9e  lea     r9, [rsp+580h+var_528]; struct ABO_NODE **
0x180020ca3  mov     [rsp+580h+var_560], esi; int
0x180020ca7  mov     r8d, edi; int
0x180020caa  lea     rdx, aLmMimemap_0; "/LM/MIMEMAP"
0x180020cb1  mov     rcx, [rcx+10h]; this
0x180020cb5  call    ?CreateNode@ABO_NODE@@QEAAJPEBGHPEAPEAV1@H@Z; ABO_NODE::CreateNode(ushort const *,int,ABO_NODE * *,int)
0x180020cba  mov     ebx, eax
0x180020cbc  test    eax, eax
0x180020cbe  js      short loc_180020CCD
0x180020cc0  mov     r8d, edi
0x180020cc3  mov     rdi, [rsp+580h+var_528]
0x180020cc8  mov     rcx, rdi
0x180020ccb  jmp     short loc_180020CDD
0x180020ccd  mov     rdi, [rsp+580h+var_528]
0x180020cd2  jmp     short loc_180020CF0
0x180020cd4  mov     r8d, 1; int
0x180020cda  mov     rcx, r15; this
0x180020cdd  lea     rdx, [rsp+580h+var_510]; struct _METADATA_RECORD *
0x180020ce2  call    ?SetData@ABO_NODE@@QEAAJPEAU_METADATA_RECORD@@H@Z; ABO_NODE::SetData(_METADATA_RECORD *,int)
0x180020ce7  mov     ebx, eax
0x180020ce9  jmp     short loc_180020CF0
0x180020ceb  mov     ebx, 80070057h
0x180020cf0  test    rdi, rdi
0x180020cf3  jz      short loc_180020CFD
0x180020cf5  mov     rcx, rdi; this
0x180020cf8  call    ?DereferenceAboNode@ABO_NODE@@QEAAXXZ; ABO_NODE::DereferenceAboNode(void)
0x180020cfd  mov     rcx, [rsp+580h+var_550]
0x180020d02  mov     rdx, [rsp+580h+var_540]
0x180020d07  test    rdx, rdx
0x180020d0a  jz      short loc_180020D25
0x180020d0c  mov     rax, [rdx]
0x180020d0f  mov     rcx, rdx
0x180020d12  mov     rax, [rax+10h]
0x180020d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d1b  mov     rcx, [rsp+580h+var_550]
0x180020d20  mov     [rsp+580h+var_540], rsi
0x180020d25  test    rcx, rcx
0x180020d28  jz      short loc_180020D3E
0x180020d2a  mov     rax, [rcx]
0x180020d2d  mov     rax, [rax+10h]
0x180020d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d36  mov     rcx, rsi
0x180020d39  mov     [rsp+580h+var_550], rcx
0x180020d3e  mov     rdx, [rsp+580h+var_530]
0x180020d43  test    rdx, rdx
0x180020d46  jz      short loc_180020D61
0x180020d48  mov     rax, [rdx]
0x180020d4b  mov     rcx, rdx
0x180020d4e  mov     rax, [rax+10h]
0x180020d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d57  mov     rcx, [rsp+580h+var_550]
  ... truncated ...
```
