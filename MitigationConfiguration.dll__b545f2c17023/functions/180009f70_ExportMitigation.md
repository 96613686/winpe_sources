# ExportMitigation

- ea: `0x180009f70`
- end: `0x18000a5e2`
- name: `ExportMitigation`
- size: `1650`
- prototype: `__int64 __fastcall(const WCHAR *)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x180001c00`
- `0x180005db4`
- `0x180007768`
- `0x180007918`
- `0x180009f70`
- `0x180011b90`
- `0x1800121a0`
- `0x180012530`
- `0x1800127a8`
- `0x180013a60`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a351`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a2cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a346`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a351`
- `XmlLite!CreateXmlWriter` at `0x18000a049`
- `XmlLite!CreateXmlWriter` at `0x18000a049`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180009fb7`
- `api-ms-win-downlevel-shlwapi-l2-1-0!SHCreateStreamOnFileW` at `0x180009fb7`

## string_xrefs

- `0x180009fcd`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a05f`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a0d4`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a14c`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a1c1`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a240`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a47f`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a508`: `onecore\ds\security\exploitguard\dll\mitigationconfiguration.cpp`
- `0x18000a44b`: `AppConfig`
- `0x18000a3ee`: `SystemConfig`

## pseudocode

```c
__int64 __fastcall ExportMitigation(const WCHAR *a1)
{
  HRESULT v1; // eax
  unsigned int v2; // ebx
  IStream *v3; // rcx
  HRESULT v5; // eax
  void *v6; // rcx
  IStream *v7; // rcx
  int v8; // eax
  void *v9; // rcx
  IStream *v10; // rcx
  int v11; // eax
  void *v12; // rcx
  IStream *v13; // rcx
  int v14; // eax
  void *v15; // rcx
  IStream *v16; // rcx
  int v17; // eax
  void *v18; // rcx
  IStream *v19; // rcx
  signed int LastError; // eax
  void *v21; // rcx
  IStream *v22; // rcx
  signed int v23; // eax
  void *v24; // rcx
  IStream *v25; // rcx
  MitigationOptionsPolicy::ImagePolicy *i; // rbx
  __int64 v27; // r9
  int v28; // eax
  void *v29; // rcx
  IStream *v30; // rcx
  int v31; // eax
  void *v32; // rcx
  IStream *v33; // rcx
  void *v34; // rcx
  IStream *v35; // rcx
  void *ppvObject; // [rsp+30h] [rbp-D0h] BYREF
  IStream *ppstm; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v38[2]; // [rsp+40h] [rbp-C0h] BYREF
  char *v39[424]; // [rsp+50h] [rbp-B0h] BYREF
  MitigationOptionsPolicy::ImagePolicy *v40[2]; // [rsp+D90h] [rbp+C90h] BYREF
  __int64 v41; // [rsp+DA0h] [rbp+CA0h]
  _BYTE v42[3392]; // [rsp+DA8h] [rbp+CA8h] BYREF
  _BYTE v43[3400]; // [rsp+1AE8h] [rbp+19E8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2848h] [rbp+2748h]

  ppstm = 0;
  ppvObject = 0;
  v1 = SHCreateStreamOnFileW(a1, 0x1001u, &ppstm);
  v2 = v1;
  if ( v1 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x51F,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v1);
    v3 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v3 + 16LL))(v3);
    }
    return v2;
  }
  v5 = CreateXmlWriter(&GUID_7279fc88_709d_4095_b63d_69fe4b0d9030, &ppvObject, 0);
  v2 = v5;
  if ( v5 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x520,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v5);
    v6 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v6 + 16LL))(v6);
    }
    v7 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    return v2;
  }
  v8 = (*(__int64 (__fastcall **)(void *, IStream *))(*(_QWORD *)ppvObject + 24LL))(ppvObject, ppstm);
  v2 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x521,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v8);
    v9 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v9 + 16LL))(v9);
    }
    v10 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v10 + 16LL))(v10);
    }
    return v2;
  }
  v11 = (*(__int64 (__fastcall **)(void *, __int64, __int64))(*(_QWORD *)ppvObject + 40LL))(ppvObject, 1, 1);
  v2 = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x523,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v11);
    v12 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v12 + 16LL))(v12);
    }
    v13 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v13 + 16LL))(v13);
    }
    return v2;
  }
  v14 = (*(__int64 (__fastcall **)(void *, _QWORD))(*(_QWORD *)ppvObject + 208LL))(ppvObject, 0);
  v2 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x524,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v14);
    v15 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v15 + 16LL))(v15);
    }
    v16 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v16 + 16LL))(v16);
    }
    return v2;
  }
  v17 = (*(__int64 (__fastcall **)(void *, _QWORD, const wchar_t *, _QWORD))(*(_QWORD *)ppvObject + 216LL))(
          ppvObject,
          0,
          L"MitigationPolicy",
          0);
  v2 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x525,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v17);
    v18 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v18 + 16LL))(v18);
    }
    v19 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v19 + 16LL))(v19);
    }
    return v2;
  }
  *(_OWORD *)v40 = 0;
  v41 = 0;
  MitigationOptionsPolicy::ImagePolicy::ImagePolicy((MitigationOptionsPolicy::ImagePolicy *)v42, 0);
  MitigationOptionsPolicy::ImagePolicy::ImagePolicy((MitigationOptionsPolicy::ImagePolicy *)v43, 1);
  if ( !MitigationOptionsPolicy::MitigationPolicy::Refresh(v40) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      v2 = (unsigned __int16)LastError | 0x80070000;
    MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy((MitigationOptionsPolicy::MitigationPolicy *)v40);
    v21 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v21 + 16LL))(v21);
    }
    v22 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v22 + 16LL))(v22);
    }
    return v2;
  }
  MitigationOptionsPolicy::ImagePolicy::ImagePolicy((MitigationOptionsPolicy::ImagePolicy *)v39, 0);
  if ( !MitigationOptionsPolicy::ImagePolicy::Load((MitigationOptionsPolicy::ImagePolicy *)v39) && GetLastError() != 2 )
  {
    v23 = GetLastError();
    v2 = v23;
    if ( v23 > 0 )
      v2 = (unsigned __int16)v23 | 0x80070000;
    if ( v2 != -2147024891 )
    {
      MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v39);
      MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy((MitigationOptionsPolicy::MitigationPolicy *)v40);
      v24 = ppvObject;
      if ( ppvObject )
      {
        ppvObject = 0;
        (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
      }
      v25 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        (*(void (__fastcall **)(IStream *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      return v2;
    }
  }
  v38[0] = (__int64)ppvObject;
  if ( ppvObject )
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvObject + 8LL))(ppvObject);
  BuildExportXML((MitigationOptionsPolicy::ImagePolicy *)v39, (__int64)L"SystemConfig", 0, 0, v38);
  for ( i = v40[0]; i != v40[1]; i = (MitigationOptionsPolicy::ImagePolicy *)((char *)i + 3392) )
  {
    v38[0] = (__int64)ppvObject;
    if ( ppvObject )
      (*(void (**)(void))(*(_QWORD *)ppvObject + 8LL))();
    if ( *((_QWORD *)i + 3) <= 7u )
      v27 = (__int64)i;
    else
      v27 = *(_QWORD *)i;
    BuildExportXML(i, (__int64)L"AppConfig", (__int64)L"Executable", v27, v38);
  }
  v28 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 112LL))(ppvObject);
  v2 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x547,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v28);
    MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v39);
    MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy((MitigationOptionsPolicy::MitigationPolicy *)v40);
    v29 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v29 + 16LL))(v29);
    }
    v30 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v30 + 16LL))(v30);
    }
    return v2;
  }
  v31 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)ppvObject + 248LL))(ppvObject);
  v2 = v31;
  if ( v31 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x548,
      (int)"onecore\\ds\\security\\exploitguard\\dll\\mitigationconfiguration.cpp",
      (const char *)(unsigned int)v31);
    MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v39);
    MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy((MitigationOptionsPolicy::MitigationPolicy *)v40);
    v32 = ppvObject;
    if ( ppvObject )
    {
      ppvObject = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v32 + 16LL))(v32);
    }
    v33 = ppstm;
    if ( ppstm )
    {
      ppstm = 0;
      (*(void (__fastcall **)(IStream *))(*(_QWORD *)v33 + 16LL))(v33);
    }
    return v2;
  }
  MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(v39);
  MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy((MitigationOptionsPolicy::MitigationPolicy *)v40);
  v34 = ppvObject;
  if ( ppvObject )
  {
    ppvObject = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v34 + 16LL))(v34);
  }
  v35 = ppstm;
  if ( ppstm )
  {
    ppstm = 0;
    (*(void (__fastcall **)(IStream *))(*(_QWORD *)v35 + 16LL))(v35);
  }
  return 0;
}

```

## disassembly

```asm
0x180009f70  mov     [rsp-8+arg_8], rbx
0x180009f75  mov     [rsp-8+arg_10], rdi
0x180009f7a  push    rbp
0x180009f7b  lea     rbp, [rsp-2740h]
0x180009f83  mov     eax, 2840h
0x180009f88  call    _alloca_probe
0x180009f8d  sub     rsp, rax
0x180009f90  mov     rax, cs:__security_cookie
0x180009f97  xor     rax, rsp
0x180009f9a  mov     [rbp+2740h+var_10], rax
0x180009fa1  xor     edi, edi
0x180009fa3  mov     [rsp+2840h+ppstm], rdi
0x180009fa8  mov     [rsp+2840h+ppvObject], rdi
0x180009fad  lea     r8, [rsp+2840h+ppstm]; ppstm
0x180009fb2  mov     edx, 1001h; grfMode
0x180009fb7  call    cs:__imp_SHCreateStreamOnFileW
0x180009fbd  mov     ebx, eax
0x180009fbf  test    eax, eax
0x180009fc1  jns     short loc_18000A01E
0x180009fc3  mov     rcx, [rbp+2748h]; this
0x180009fca  mov     r9d, eax; char *
0x180009fcd  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x180009fd4  mov     edx, 51Fh; void *
0x180009fd9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180009fde  nop
0x180009fdf  mov     rcx, [rsp+2840h+ppvObject]
0x180009fe4  test    rcx, rcx
0x180009fe7  jz      short loc_180009FFB
0x180009fe9  mov     [rsp+2840h+ppvObject], rdi
0x180009fee  mov     rax, [rcx]
0x180009ff1  mov     rax, [rax+10h]
0x180009ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ffa  nop
0x180009ffb  mov     rcx, [rsp+2840h+ppstm]
0x18000a000  test    rcx, rcx
0x18000a003  jz      short loc_18000A017
0x18000a005  mov     [rsp+2840h+ppstm], rdi
0x18000a00a  mov     rax, [rcx]
0x18000a00d  mov     rax, [rax+10h]
0x18000a011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a016  nop
0x18000a017  mov     eax, ebx
0x18000a019  jmp     loc_18000A5BE
0x18000a01e  mov     rcx, [rsp+2840h+ppvObject]
0x18000a023  test    rcx, rcx
0x18000a026  jz      short loc_18000A03A
0x18000a028  mov     [rsp+2840h+ppvObject], rdi
0x18000a02d  mov     rax, [rcx]
0x18000a030  mov     rax, [rax+10h]
0x18000a034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a039  nop
0x18000a03a  xor     r8d, r8d; pMalloc
0x18000a03d  lea     rdx, [rsp+2840h+ppvObject]; ppvObject
0x18000a042  lea     rcx, _GUID_7279fc88_709d_4095_b63d_69fe4b0d9030; riid
0x18000a049  call    cs:__imp_CreateXmlWriter
0x18000a04f  mov     ebx, eax
0x18000a051  test    eax, eax
0x18000a053  jns     short loc_18000A0AE
0x18000a055  mov     rcx, [rbp+2748h]; this
0x18000a05c  mov     r9d, eax; char *
0x18000a05f  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000a066  mov     edx, 520h; void *
0x18000a06b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a070  nop
0x18000a071  mov     rcx, [rsp+2840h+ppvObject]
0x18000a076  test    rcx, rcx
0x18000a079  jz      short loc_18000A08D
0x18000a07b  mov     [rsp+2840h+ppvObject], rdi
0x18000a080  mov     rax, [rcx]
0x18000a083  mov     rax, [rax+10h]
0x18000a087  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08c  nop
0x18000a08d  mov     rcx, [rsp+2840h+ppstm]
0x18000a092  test    rcx, rcx
0x18000a095  jz      short loc_18000A0A9
0x18000a097  mov     [rsp+2840h+ppstm], rdi
0x18000a09c  mov     rax, [rcx]
0x18000a09f  mov     rax, [rax+10h]
0x18000a0a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a8  nop
0x18000a0a9  jmp     loc_18000A017
0x18000a0ae  mov     rcx, [rsp+2840h+ppvObject]
0x18000a0b3  mov     rax, [rcx]
0x18000a0b6  mov     rdx, [rsp+2840h+ppstm]
0x18000a0bb  mov     rax, [rax+18h]
0x18000a0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c4  mov     ebx, eax
0x18000a0c6  test    eax, eax
0x18000a0c8  jns     short loc_18000A123
0x18000a0ca  mov     rcx, [rbp+2748h]; this
0x18000a0d1  mov     r9d, eax; char *
0x18000a0d4  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000a0db  mov     edx, 521h; void *
0x18000a0e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a0e5  nop
0x18000a0e6  mov     rcx, [rsp+2840h+ppvObject]
0x18000a0eb  test    rcx, rcx
0x18000a0ee  jz      short loc_18000A102
0x18000a0f0  mov     [rsp+2840h+ppvObject], rdi
0x18000a0f5  mov     rax, [rcx]
0x18000a0f8  mov     rax, [rax+10h]
0x18000a0fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a101  nop
0x18000a102  mov     rcx, [rsp+2840h+ppstm]
0x18000a107  test    rcx, rcx
0x18000a10a  jz      short loc_18000A11E
0x18000a10c  mov     [rsp+2840h+ppstm], rdi
0x18000a111  mov     rax, [rcx]
0x18000a114  mov     rax, [rax+10h]
0x18000a118  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a11d  nop
0x18000a11e  jmp     loc_18000A017
0x18000a123  mov     rcx, [rsp+2840h+ppvObject]
0x18000a128  mov     rax, [rcx]
0x18000a12b  mov     edx, 1
0x18000a130  mov     r8d, edx
0x18000a133  mov     rax, [rax+28h]
0x18000a137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a13c  mov     ebx, eax
0x18000a13e  test    eax, eax
0x18000a140  jns     short loc_18000A19B
0x18000a142  mov     rcx, [rbp+2748h]; this
0x18000a149  mov     r9d, eax; char *
0x18000a14c  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000a153  mov     edx, 523h; void *
0x18000a158  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a15d  nop
0x18000a15e  mov     rcx, [rsp+2840h+ppvObject]
0x18000a163  test    rcx, rcx
0x18000a166  jz      short loc_18000A17A
0x18000a168  mov     [rsp+2840h+ppvObject], rdi
0x18000a16d  mov     rax, [rcx]
0x18000a170  mov     rax, [rax+10h]
0x18000a174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a179  nop
0x18000a17a  mov     rcx, [rsp+2840h+ppstm]
0x18000a17f  test    rcx, rcx
0x18000a182  jz      short loc_18000A196
0x18000a184  mov     [rsp+2840h+ppstm], rdi
0x18000a189  mov     rax, [rcx]
0x18000a18c  mov     rax, [rax+10h]
0x18000a190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a195  nop
0x18000a196  jmp     loc_18000A017
0x18000a19b  mov     rcx, [rsp+2840h+ppvObject]
0x18000a1a0  mov     rax, [rcx]
0x18000a1a3  xor     edx, edx
0x18000a1a5  mov     rax, [rax+0D0h]
0x18000a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b1  mov     ebx, eax
0x18000a1b3  test    eax, eax
0x18000a1b5  jns     short loc_18000A210
0x18000a1b7  mov     rcx, [rbp+2748h]; this
0x18000a1be  mov     r9d, eax; char *
0x18000a1c1  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000a1c8  mov     edx, 524h; void *
0x18000a1cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a1d2  nop
0x18000a1d3  mov     rcx, [rsp+2840h+ppvObject]
0x18000a1d8  test    rcx, rcx
0x18000a1db  jz      short loc_18000A1EF
0x18000a1dd  mov     [rsp+2840h+ppvObject], rdi
0x18000a1e2  mov     rax, [rcx]
0x18000a1e5  mov     rax, [rax+10h]
0x18000a1e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1ee  nop
0x18000a1ef  mov     rcx, [rsp+2840h+ppstm]
0x18000a1f4  test    rcx, rcx
0x18000a1f7  jz      short loc_18000A20B
0x18000a1f9  mov     [rsp+2840h+ppstm], rdi
0x18000a1fe  mov     rax, [rcx]
0x18000a201  mov     rax, [rax+10h]
0x18000a205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20a  nop
0x18000a20b  jmp     loc_18000A017
0x18000a210  mov     rcx, [rsp+2840h+ppvObject]
0x18000a215  mov     rax, [rcx]
0x18000a218  xor     r9d, r9d
0x18000a21b  lea     r8, aMitigationpoli; "MitigationPolicy"
0x18000a222  xor     edx, edx
0x18000a224  mov     rax, [rax+0D8h]
0x18000a22b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a230  mov     ebx, eax
0x18000a232  test    eax, eax
0x18000a234  jns     short loc_18000A28F
0x18000a236  mov     rcx, [rbp+2748h]; this
0x18000a23d  mov     r9d, eax; char *
0x18000a240  lea     r8, aOnecoreDsSecur; "onecore\\ds\\security\\exploitguard\\dl"...
0x18000a247  mov     edx, 525h; void *
0x18000a24c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a251  nop
0x18000a252  mov     rcx, [rsp+2840h+ppvObject]
0x18000a257  test    rcx, rcx
0x18000a25a  jz      short loc_18000A26E
0x18000a25c  mov     [rsp+2840h+ppvObject], rdi
0x18000a261  mov     rax, [rcx]
0x18000a264  mov     rax, [rax+10h]
0x18000a268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a26d  nop
0x18000a26e  mov     rcx, [rsp+2840h+ppstm]
0x18000a273  test    rcx, rcx
0x18000a276  jz      short loc_18000A28A
0x18000a278  mov     [rsp+2840h+ppstm], rdi
0x18000a27d  mov     rax, [rcx]
0x18000a280  mov     rax, [rax+10h]
0x18000a284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a289  nop
0x18000a28a  jmp     loc_18000A017
0x18000a28f  xorps   xmm0, xmm0
0x18000a292  movdqa  xmmword ptr [rbp+2740h+var_1AB0], xmm0
0x18000a29a  mov     [rbp+2740h+var_1AA0], rdi
0x18000a2a1  xor     edx, edx; bool
0x18000a2a3  lea     rcx, [rbp+2740h+var_1A98]; this
0x18000a2aa  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@_N@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(bool)
0x18000a2af  mov     dl, 1; bool
0x18000a2b1  lea     rcx, [rbp+2740h+var_D58]; this
0x18000a2b8  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@_N@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(bool)
0x18000a2bd  lea     rcx, [rbp+2740h+var_1AB0]; this
0x18000a2c4  call    ?Refresh@MitigationPolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::MitigationPolicy::Refresh(void)
0x18000a2c9  test    al, al
0x18000a2cb  jnz     short loc_18000A32C
0x18000a2cd  call    cs:__imp_GetLastError
0x18000a2d3  mov     ebx, eax
0x18000a2d5  test    eax, eax
0x18000a2d7  jle     short loc_18000A2E2
0x18000a2d9  movzx   ebx, ax
0x18000a2dc  or      ebx, 80070000h
0x18000a2e2  lea     rcx, [rbp+2740h+var_1AB0]; this
0x18000a2e9  call    ??1MitigationPolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy(void)
0x18000a2ee  nop
0x18000a2ef  mov     rcx, [rsp+2840h+ppvObject]
0x18000a2f4  test    rcx, rcx
0x18000a2f7  jz      short loc_18000A30B
0x18000a2f9  mov     [rsp+2840h+ppvObject], rdi
0x18000a2fe  mov     rax, [rcx]
0x18000a301  mov     rax, [rax+10h]
0x18000a305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a30a  nop
0x18000a30b  mov     rcx, [rsp+2840h+ppstm]
0x18000a310  test    rcx, rcx
0x18000a313  jz      short loc_18000A327
0x18000a315  mov     [rsp+2840h+ppstm], rdi
0x18000a31a  mov     rdx, [rcx]
0x18000a31d  mov     rax, [rdx+10h]
0x18000a321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a326  nop
0x18000a327  jmp     loc_18000A017
0x18000a32c  xor     edx, edx; bool
0x18000a32e  lea     rcx, [rsp+2840h+var_27F0]; this
0x18000a333  call    ??0ImagePolicy@MitigationOptionsPolicy@@QEAA@_N@Z; MitigationOptionsPolicy::ImagePolicy::ImagePolicy(bool)
0x18000a338  lea     rcx, [rsp+2840h+var_27F0]; this
0x18000a33d  call    ?Load@ImagePolicy@MitigationOptionsPolicy@@QEAA_NXZ; MitigationOptionsPolicy::ImagePolicy::Load(void)
0x18000a342  test    al, al
0x18000a344  jnz     short loc_18000A3C2
0x18000a346  call    cs:__imp_GetLastError
0x18000a34c  cmp     eax, 2
0x18000a34f  jz      short loc_18000A3C2
0x18000a351  call    cs:__imp_GetLastError
0x18000a357  mov     ebx, eax
0x18000a359  test    eax, eax
0x18000a35b  jle     short loc_18000A366
0x18000a35d  movzx   ebx, ax
0x18000a360  or      ebx, 80070000h
0x18000a366  cmp     ebx, 80070005h
0x18000a36c  jz      short loc_18000A3C2
0x18000a36e  lea     rcx, [rsp+2840h+var_27F0]; this
0x18000a373  call    ??1ImagePolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::ImagePolicy::~ImagePolicy(void)
0x18000a378  lea     rcx, [rbp+2740h+var_1AB0]; this
0x18000a37f  call    ??1MitigationPolicy@MitigationOptionsPolicy@@QEAA@XZ; MitigationOptionsPolicy::MitigationPolicy::~MitigationPolicy(void)
0x18000a384  nop
0x18000a385  mov     rcx, [rsp+2840h+ppvObject]
0x18000a38a  test    rcx, rcx
0x18000a38d  jz      short loc_18000A3A1
0x18000a38f  mov     [rsp+2840h+ppvObject], rdi
0x18000a394  mov     rax, [rcx]
0x18000a397  mov     rax, [rax+10h]
0x18000a39b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3a0  nop
0x18000a3a1  mov     rcx, [rsp+2840h+ppstm]
0x18000a3a6  test    rcx, rcx
0x18000a3a9  jz      short loc_18000A3BD
0x18000a3ab  mov     [rsp+2840h+ppstm], rdi
0x18000a3b0  mov     rdx, [rcx]
0x18000a3b3  mov     rax, [rdx+10h]
0x18000a3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bc  nop
0x18000a3bd  jmp     loc_18000A017
0x18000a3c2  mov     rcx, [rsp+2840h+ppvObject]
0x18000a3c7  mov     [rsp+2840h+var_2800], rcx
0x18000a3cc  test    rcx, rcx
0x18000a3cf  jz      short loc_18000A3DE
0x18000a3d1  mov     rax, [rcx]
0x18000a3d4  mov     rax, [rax+8]
0x18000a3d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3dd  nop
0x18000a3de  lea     rax, [rsp+2840h+var_2800]
0x18000a3e3  mov     [rsp+2840h+var_2820], rax; int
0x18000a3e8  xor     r9d, r9d
0x18000a3eb  xor     r8d, r8d
0x18000a3ee  lea     rdx, aSystemconfig; "SystemConfig"
  ... truncated ...
```
