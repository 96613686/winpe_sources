# Windows::ChangeTracking::CClientFileChangeClientStateStore::_StoreConfigToRegistry(std::shared_ptr<Windows::ChangeTracking::CFileChangeClientState const>)

- ea: `0x18005408c`
- end: `0x180054727`
- name: `?_StoreConfigToRegistry@CClientFileChangeClientStateStore@ChangeTracking@Windows@@AEAAXV?$shared_ptr@$$CBVCFileChangeClientState@ChangeTracking@Windows@@@std@@@Z`
- size: `1691`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `18`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180101fa0`

## callees

- `0x180012318`
- `0x1800269b0`
- `0x180026a18`
- `0x180027164`
- `0x18005408c`
- `0x180054730`
- `0x180054e14`
- `0x1800555f0`
- `0x18006a040`
- `0x18006a618`
- `0x1800bbc90`
- `0x1800cae14`
- `0x1800e2374`
- `0x1800e95f0`
- `0x18010ff58`
- `0x1801244c0`
- `0x18012540e`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054389`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054398`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005456c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800545a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054389`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054398`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054409`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054418`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054489`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180054498`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005456c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800545a9`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005437d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800543fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005447d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054599`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005437d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800543fd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x18005447d`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180054599`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180054121`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180054676`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180054121`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x180054676`

## string_xrefs

- `0x1800542f9`: `ConfigFlags`
- `0x1800543f2`: `MonitoredPathRegularExpressionExclusion`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall Windows::ChangeTracking::CClientFileChangeClientStateStore::_StoreConfigToRegistry(
        __int64 a1,
        __int64 a2)
{
  unsigned int Error; // eax
  const char *v5; // r9
  _QWORD *v6; // rdx
  _QWORD *v7; // rdx
  _QWORD *v8; // rdx
  int v9; // eax
  int v10; // eax
  int v11; // eax
  int v12; // eax
  int v13; // eax
  int v14; // esi
  DWORD v15; // ecx
  int v16; // ebx
  const BYTE *Buffer; // rax
  LSTATUS v18; // eax
  int v19; // eax
  DWORD v20; // ecx
  int v21; // ebx
  const BYTE *v22; // rax
  LSTATUS v23; // eax
  int v24; // eax
  DWORD v25; // ecx
  int v26; // ebx
  const BYTE *v27; // rax
  LSTATUS v28; // eax
  int v29; // eax
  int v30; // eax
  int v31; // eax
  DWORD v32; // ecx
  const char *v33; // r9
  LSTATUS v34; // eax
  const wchar_t *v35; // r8
  int v36; // eax
  const GUID *v37; // rbx
  __int64 v38; // rax
  int v39; // eax
  std::_Ref_count_base *v40; // rcx
  int lpData; // [rsp+20h] [rbp-E0h]
  int lpDataa; // [rsp+20h] [rbp-E0h]
  BYTE Data[8]; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v44; // [rsp+38h] [rbp-C8h]
  _QWORD v45[4]; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v46; // [rsp+60h] [rbp-A0h] BYREF
  int v47; // [rsp+E8h] [rbp-18h]
  HKEY hKey; // [rsp+F0h] [rbp-10h]
  _BYTE v49[20]; // [rsp+100h] [rbp+0h] BYREF
  int v50; // [rsp+114h] [rbp+14h]
  _BYTE v51[20]; // [rsp+160h] [rbp+60h] BYREF
  int v52; // [rsp+174h] [rbp+74h]
  _BYTE v53[20]; // [rsp+1C0h] [rbp+C0h] BYREF
  int v54; // [rsp+1D4h] [rbp+D4h]
  OLECHAR sz[40]; // [rsp+260h] [rbp+160h] BYREF
  OLECHAR v56[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4E8h] [rbp+3E8h]

  v44 = a2;
  v45[2] = &v46;
  v45[3] = 65;
  v46 = 0;
  v45[1] = &CCICommonPathString::`vftable';
  v45[0] = &CRegistry::`vftable';
  v47 = 0;
  hKey = 0;
  memset_0(sz, 0, sizeof(sz));
  StringFromGUID2(*(const GUID *const *)a2, sz, 40);
  if ( !sz[0] )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  if ( (*(unsigned int (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)(a1 + 8) + 24LL))(a1 + 8, sz) )
    Error = 0;
  else
    Error = ResultFromKnownLastError();
  v5 = 0;
  if ( Error != -2147024713 )
    v5 = (const char *)Error;
  if ( (int)v5 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xA9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      v5,
      lpData);
  v6 = (_QWORD *)(*(_QWORD *)a2 + 24LL);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 48LL) > 7u )
    v6 = (_QWORD *)*v6;
  TLMString<64,64,32767>::TLMString<64,64,32767>(v53, v6);
  v7 = (_QWORD *)(*(_QWORD *)a2 + 56LL);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 80LL) > 7u )
    v7 = (_QWORD *)*v7;
  TLMString<32,32,1024>::TLMString<32,32,1024>(v51, v7);
  v8 = (_QWORD *)(*(_QWORD *)a2 + 104LL);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 128LL) > 7u )
    v8 = (_QWORD *)*v8;
  TLMString<32,32,1024>::TLMString<32,32,1024>(v49, v8);
  v9 = CRegistry::Init((CRegistry *)v45, *(HKEY *)(a1 + 184), sz, 0xF003Fu, *(const wchar_t **)(a1 + 24));
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v9,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue(
                       (CRegistry *)v45,
                       L"FileAttributesFilteredOut",
                       *(_DWORD *)(*(_QWORD *)a2 + 88LL)) )
    v10 = 0;
  else
    v10 = ResultFromKnownLastError();
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v10,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue((CRegistry *)v45, L"UsnSourceFilteredOut", *(_DWORD *)(*(_QWORD *)a2 + 92LL)) )
    v11 = 0;
  else
    v11 = ResultFromKnownLastError();
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB4,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v11,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue((CRegistry *)v45, L"UsnReasonFilteredOut", *(_DWORD *)(*(_QWORD *)a2 + 96LL)) )
    v12 = 0;
  else
    v12 = ResultFromKnownLastError();
  if ( v12 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v12,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue((CRegistry *)v45, L"ConfigFlags", *(_DWORD *)(*(_QWORD *)a2 + 100LL)) )
    v13 = 0;
  else
    v13 = ResultFromKnownLastError();
  if ( v13 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v13,
      lpDataa);
  v14 = 1;
  if ( !hKey )
  {
    v15 = 6;
LABEL_42:
    SetLastError(v15);
    v19 = ResultFromKnownLastError();
    goto LABEL_44;
  }
  v16 = v54;
  Buffer = (const BYTE *)CLMString::GetBuffer((CLMString *)v53, 0);
  v18 = RegSetValueExW(hKey, L"ScopeToMonitor", 0, 1u, Buffer, 2 * v16 + 2);
  if ( v18 )
  {
    v15 = v18;
    goto LABEL_42;
  }
  SetLastError(0);
  v19 = 0;
LABEL_44:
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v19,
      lpDataa);
  if ( !hKey )
  {
    v20 = 6;
LABEL_50:
    SetLastError(v20);
    v24 = ResultFromKnownLastError();
    goto LABEL_52;
  }
  v21 = v52;
  v22 = (const BYTE *)CLMString::GetBuffer((CLMString *)v51, 0);
  v23 = RegSetValueExW(hKey, L"MonitoredPathRegularExpressionExclusion", 0, 1u, v22, 2 * v21 + 2);
  if ( v23 )
  {
    v20 = v23;
    goto LABEL_50;
  }
  SetLastError(0);
  v24 = 0;
LABEL_52:
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v24,
      lpDataa);
  if ( !hKey )
  {
    v25 = 6;
LABEL_58:
    SetLastError(v25);
    v29 = ResultFromKnownLastError();
    goto LABEL_60;
  }
  v26 = v50;
  v27 = (const BYTE *)CLMString::GetBuffer((CLMString *)v49, 0);
  v28 = RegSetValueExW(hKey, L"ApplicationName", 0, 1u, v27, 2 * v26 + 2);
  if ( v28 )
  {
    v25 = v28;
    goto LABEL_58;
  }
  SetLastError(0);
  v29 = 0;
LABEL_60:
  if ( v29 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBC,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v29,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue((CRegistry *)v45, L"ClientId", *(unsigned __int16 *)(*(_QWORD *)a2 + 16LL)) )
    v30 = 0;
  else
    v30 = ResultFromKnownLastError();
  if ( v30 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xBE,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v30,
      lpDataa);
  if ( (unsigned int)CRegistry::SetValue((CRegistry *)v45, L"VolumeIndex", *(unsigned __int16 *)(*(_QWORD *)a2 + 18LL)) )
    v31 = 0;
  else
    v31 = ResultFromKnownLastError();
  if ( v31 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xC0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      (const char *)(unsigned int)v31,
      lpDataa);
  *(_QWORD *)Data = *(_QWORD *)(*(_QWORD *)a2 + 192LL);
  if ( !hKey )
  {
    v32 = 6;
LABEL_74:
    SetLastError(v32);
    v14 = 0;
    goto LABEL_78;
  }
  v34 = RegSetValueExW(hKey, L"LastChangeId", 0, 3u, Data, 8u);
  if ( v34 )
  {
    v32 = v34;
    goto LABEL_74;
  }
  SetLastError(0);
LABEL_78:
  if ( !v14 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0xC3,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
      v33);
  if ( *(_QWORD *)(*(_QWORD *)a2 + 152LL) )
  {
    v35 = (const wchar_t *)(*(_QWORD *)a2 + 136LL);
    if ( *(_QWORD *)(*(_QWORD *)a2 + 160LL) > 7u )
      v35 = *(const wchar_t **)v35;
    if ( CRegistry::SetValue((CRegistry *)v45, L"PackageFamilyName", v35) )
      v36 = 0;
    else
      v36 = ResultFromKnownLastError();
    if ( v36 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
        (const char *)(unsigned int)v36,
        lpDataa);
  }
  v37 = *(const GUID **)a2;
  v38 = *(_QWORD *)(*(_QWORD *)a2 + 172LL) - *(_QWORD *)&GUID_NULL.Data1;
  if ( !v38 )
    v38 = *(_QWORD *)&v37[11].Data2 - *(_QWORD *)GUID_NULL.Data4;
  if ( v38 )
  {
    memset_0(v56, 0, 0x208u);
    if ( StringFromGUID2((const GUID *)((char *)v37 + 172), v56, 260) )
    {
      v39 = CRegistry::SetValue((CRegistry *)v45, L"BackgroundEventId", v56) ? 0 : ResultFromKnownLastError();
      if ( v39 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\changetracking\\client\\clientchangetrackingstatestore.cxx",
          (const char *)(unsigned int)v39,
          lpDataa);
    }
  }
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v49);
  TLMString<32,32,1024>::~TLMString<32,32,1024>(v51);
  TLMString<64,64,32767>::~TLMString<64,64,32767>(v53);
  CRegistry::~CRegistry((CRegistry *)v45);
  v40 = *(std::_Ref_count_base **)(a2 + 8);
  if ( v40 )
    std::_Ref_count_base::_Decref(v40);
}

```

## disassembly

```asm
0x18005408c  mov     [rsp-8+arg_10], rbx
0x180054091  mov     [rsp-8+arg_18], rsi
0x180054096  push    rbp
0x180054097  push    rdi
0x180054098  push    r14
0x18005409a  lea     rbp, [rsp-3D0h]
0x1800540a2  sub     rsp, 4D0h
0x1800540a9  mov     rax, cs:__security_cookie
0x1800540b0  xor     rax, rsp
0x1800540b3  mov     [rbp+3E0h+var_20], rax
0x1800540ba  mov     rdi, rdx
0x1800540bd  mov     rbx, rcx
0x1800540c0  mov     [rsp+4E0h+var_4A8], rdx
0x1800540c5  lea     rax, [rsp+4E0h+var_480]
0x1800540ca  mov     [rsp+4E0h+var_490], rax
0x1800540cf  mov     [rsp+4E0h+var_488], 41h ; 'A'
0x1800540d8  xor     r14d, r14d
0x1800540db  mov     [rsp+4E0h+var_480], r14w
0x1800540e1  lea     rax, ??_7CCICommonPathString@@6B@; const CCICommonPathString::`vftable'
0x1800540e8  mov     [rsp+4E0h+var_498], rax
0x1800540ed  lea     rax, ??_7CRegistry@@6B@; const CRegistry::`vftable'
0x1800540f4  mov     [rsp+4E0h+var_4A0], rax
0x1800540f9  mov     [rbp+3E0h+var_3F8], r14d
0x1800540fd  mov     [rbp+3E0h+hKey], r14
0x180054101  xor     edx, edx; Val
0x180054103  lea     r8d, [r14+50h]; Size
0x180054107  lea     rcx, [rbp+3E0h+sz]; void *
0x18005410e  call    memset_0
0x180054113  lea     r8d, [r14+28h]; cchMax
0x180054117  lea     rdx, [rbp+3E0h+sz]; lpsz
0x18005411e  mov     rcx, [rdi]; rguid
0x180054121  call    cs:__imp_StringFromGUID2
0x180054127  cmp     [rbp+3E0h+sz], r14w
0x18005412f  jnz     short loc_180054136
0x180054131  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180054136  lea     rcx, [rbx+8]
0x18005413a  mov     rax, [rcx]
0x18005413d  lea     rdx, [rbp+3E0h+sz]
0x180054144  mov     rax, [rax+18h]
0x180054148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005414d  test    eax, eax
0x18005414f  jz      short loc_180054156
0x180054151  mov     eax, r14d
0x180054154  jmp     short loc_18005415B
0x180054156  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005415b  mov     r9d, r14d
0x18005415e  cmp     eax, 800700B7h
0x180054163  cmovnz  r9d, eax; char *
0x180054167  mov     rcx, [rbp+3E8h]; this
0x18005416e  test    r9d, r9d
0x180054171  jns     short loc_180054185
0x180054173  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18005417a  mov     edx, 0A9h; void *
0x18005417f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054185  mov     rdx, [rdi]
0x180054188  add     rdx, 18h
0x18005418c  cmp     qword ptr [rdx+18h], 7
0x180054191  jbe     short loc_180054196
0x180054193  mov     rdx, [rdx]
0x180054196  lea     rcx, [rbp+3E0h+var_320]
0x18005419d  call    ??0?$TLMString@$0EA@$0EA@$0HPPP@@@QEAA@PEB_W@Z; TLMString<64,64,32767>::TLMString<64,64,32767>(wchar_t const *)
0x1800541a2  nop
0x1800541a3  mov     rdx, [rdi]
0x1800541a6  add     rdx, 38h ; '8'
0x1800541aa  cmp     qword ptr [rdx+18h], 7
0x1800541af  jbe     short loc_1800541B4
0x1800541b1  mov     rdx, [rdx]
0x1800541b4  lea     rcx, [rbp+3E0h+var_380]
0x1800541b8  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800541bd  nop
0x1800541be  mov     rdx, [rdi]
0x1800541c1  add     rdx, 68h ; 'h'
0x1800541c5  cmp     qword ptr [rdx+18h], 7
0x1800541ca  jbe     short loc_1800541CF
0x1800541cc  mov     rdx, [rdx]
0x1800541cf  lea     rcx, [rbp+3E0h+var_3E0]
0x1800541d3  call    ??0?$TLMString@$0CA@$0CA@$0EAA@@@QEAA@PEB_W@Z; TLMString<32,32,1024>::TLMString<32,32,1024>(wchar_t const *)
0x1800541d8  nop
0x1800541d9  mov     rax, [rbx+18h]
0x1800541dd  mov     [rsp+4E0h+lpData], rax; int
0x1800541e2  mov     r9d, 0F003Fh; unsigned int
0x1800541e8  lea     r8, [rbp+3E0h+sz]; wchar_t *
0x1800541ef  mov     rdx, [rbx+0B8h]; HKEY
0x1800541f6  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800541fb  call    ?Init@CRegistry@@QEAAJPEAUHKEY__@@PEB_WK1@Z; CRegistry::Init(HKEY__ *,wchar_t const *,ulong,wchar_t const *)
0x180054200  mov     rcx, [rbp+3E8h]; this
0x180054207  test    eax, eax
0x180054209  jns     short loc_180054220
0x18005420b  mov     r9d, eax; char *
0x18005420e  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180054215  mov     edx, 0B0h; void *
0x18005421a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054220  mov     r8, [rdi]
0x180054223  mov     r8d, [r8+58h]; unsigned int
0x180054227  lea     rdx, aFileattributes; "FileAttributesFilteredOut"
0x18005422e  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180054233  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x180054238  test    eax, eax
0x18005423a  jz      short loc_180054241
0x18005423c  mov     eax, r14d
0x18005423f  jmp     short loc_180054246
0x180054241  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054246  mov     rcx, [rbp+3E8h]; this
0x18005424d  test    eax, eax
0x18005424f  jns     short loc_180054266
0x180054251  mov     r9d, eax; char *
0x180054254  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18005425b  mov     edx, 0B2h; void *
0x180054260  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054266  mov     r8, [rdi]
0x180054269  mov     r8d, [r8+5Ch]; unsigned int
0x18005426d  lea     rdx, aUsnsourcefilte; "UsnSourceFilteredOut"
0x180054274  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180054279  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x18005427e  test    eax, eax
0x180054280  jz      short loc_180054287
0x180054282  mov     eax, r14d
0x180054285  jmp     short loc_18005428C
0x180054287  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005428c  mov     rcx, [rbp+3E8h]; this
0x180054293  test    eax, eax
0x180054295  jns     short loc_1800542AC
0x180054297  mov     r9d, eax; char *
0x18005429a  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800542a1  mov     edx, 0B4h; void *
0x1800542a6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800542ac  mov     r8, [rdi]
0x1800542af  mov     r8d, [r8+60h]; unsigned int
0x1800542b3  lea     rdx, aUsnreasonfilte; "UsnReasonFilteredOut"
0x1800542ba  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800542bf  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1800542c4  test    eax, eax
0x1800542c6  jz      short loc_1800542CD
0x1800542c8  mov     eax, r14d
0x1800542cb  jmp     short loc_1800542D2
0x1800542cd  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800542d2  mov     rcx, [rbp+3E8h]; this
0x1800542d9  test    eax, eax
0x1800542db  jns     short loc_1800542F2
0x1800542dd  mov     r9d, eax; char *
0x1800542e0  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800542e7  mov     edx, 0B6h; void *
0x1800542ec  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800542f2  mov     r8, [rdi]
0x1800542f5  mov     r8d, [r8+64h]; unsigned int
0x1800542f9  lea     rdx, aConfigflags; "ConfigFlags"
0x180054300  lea     rcx, [rsp+4E0h+var_4A0]; this
0x180054305  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x18005430a  test    eax, eax
0x18005430c  jz      short loc_180054313
0x18005430e  mov     eax, r14d
0x180054311  jmp     short loc_180054318
0x180054313  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054318  mov     rcx, [rbp+3E8h]; this
0x18005431f  test    eax, eax
0x180054321  jns     short loc_180054338
0x180054323  mov     r9d, eax; char *
0x180054326  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18005432d  mov     edx, 0B8h; void *
0x180054332  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054338  mov     esi, 1
0x18005433d  cmp     [rbp+3E0h+hKey], r14
0x180054341  jnz     short loc_180054348
0x180054343  lea     ecx, [rsi+5]
0x180054346  jmp     short loc_180054389
0x180054348  mov     ebx, [rbp+3E0h+var_30C]
0x18005434e  xor     edx, edx; int
0x180054350  lea     rcx, [rbp+3E0h+var_320]; this
0x180054357  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18005435c  lea     edx, ds:2[rbx*2]
0x180054363  mov     [rsp+4E0h+cbData], edx; cbData
0x180054367  mov     [rsp+4E0h+lpData], rax; int
0x18005436c  mov     r9d, esi; dwType
0x18005436f  xor     r8d, r8d; Reserved
0x180054372  lea     rdx, aScopetomonitor; "ScopeToMonitor"
0x180054379  mov     rcx, [rbp+3E0h+hKey]; hKey
0x18005437d  call    cs:__imp_RegSetValueExW
0x180054383  test    eax, eax
0x180054385  jz      short loc_180054396
0x180054387  mov     ecx, eax; dwErrCode
0x180054389  call    cs:__imp_SetLastError
0x18005438f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054394  jmp     short loc_1800543A1
0x180054396  xor     ecx, ecx; dwErrCode
0x180054398  call    cs:__imp_SetLastError
0x18005439e  mov     eax, r14d
0x1800543a1  mov     rcx, [rbp+3E8h]; this
0x1800543a8  test    eax, eax
0x1800543aa  jns     short loc_1800543C1
0x1800543ac  mov     r9d, eax; char *
0x1800543af  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800543b6  mov     edx, 0B9h; void *
0x1800543bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800543c1  cmp     [rbp+3E0h+hKey], r14
0x1800543c5  jnz     short loc_1800543CE
0x1800543c7  mov     ecx, 6
0x1800543cc  jmp     short loc_180054409
0x1800543ce  mov     ebx, [rbp+3E0h+var_36C]
0x1800543d1  xor     edx, edx; int
0x1800543d3  lea     rcx, [rbp+3E0h+var_380]; this
0x1800543d7  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x1800543dc  lea     edx, ds:2[rbx*2]
0x1800543e3  mov     [rsp+4E0h+cbData], edx; cbData
0x1800543e7  mov     [rsp+4E0h+lpData], rax; int
0x1800543ec  mov     r9d, esi; dwType
0x1800543ef  xor     r8d, r8d; Reserved
0x1800543f2  lea     rdx, aMonitoredpathr; "MonitoredPathRegularExpressionExclusion"
0x1800543f9  mov     rcx, [rbp+3E0h+hKey]; hKey
0x1800543fd  call    cs:__imp_RegSetValueExW
0x180054403  test    eax, eax
0x180054405  jz      short loc_180054416
0x180054407  mov     ecx, eax; dwErrCode
0x180054409  call    cs:__imp_SetLastError
0x18005440f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054414  jmp     short loc_180054421
0x180054416  xor     ecx, ecx; dwErrCode
0x180054418  call    cs:__imp_SetLastError
0x18005441e  mov     eax, r14d
0x180054421  mov     rcx, [rbp+3E8h]; this
0x180054428  test    eax, eax
0x18005442a  jns     short loc_180054441
0x18005442c  mov     r9d, eax; char *
0x18005442f  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180054436  mov     edx, 0BBh; void *
0x18005443b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054441  cmp     [rbp+3E0h+hKey], r14
0x180054445  jnz     short loc_18005444E
0x180054447  mov     ecx, 6
0x18005444c  jmp     short loc_180054489
0x18005444e  mov     ebx, [rbp+3E0h+var_3CC]
0x180054451  xor     edx, edx; int
0x180054453  lea     rcx, [rbp+3E0h+var_3E0]; this
0x180054457  call    ?GetBuffer@CLMString@@QEAAPEA_WH@Z; CLMString::GetBuffer(int)
0x18005445c  lea     edx, ds:2[rbx*2]
0x180054463  mov     [rsp+4E0h+cbData], edx; cbData
0x180054467  mov     [rsp+4E0h+lpData], rax; int
0x18005446c  mov     r9d, esi; dwType
0x18005446f  xor     r8d, r8d; Reserved
0x180054472  lea     rdx, aApplicationnam; "ApplicationName"
0x180054479  mov     rcx, [rbp+3E0h+hKey]; hKey
0x18005447d  call    cs:__imp_RegSetValueExW
0x180054483  test    eax, eax
0x180054485  jz      short loc_180054496
0x180054487  mov     ecx, eax; dwErrCode
0x180054489  call    cs:__imp_SetLastError
0x18005448f  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180054494  jmp     short loc_1800544A1
0x180054496  xor     ecx, ecx; dwErrCode
0x180054498  call    cs:__imp_SetLastError
0x18005449e  mov     eax, r14d
0x1800544a1  mov     rcx, [rbp+3E8h]; this
0x1800544a8  test    eax, eax
0x1800544aa  jns     short loc_1800544C1
0x1800544ac  mov     r9d, eax; char *
0x1800544af  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800544b6  mov     edx, 0BCh; void *
0x1800544bb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800544c1  mov     rax, [rdi]
0x1800544c4  movzx   r8d, word ptr [rax+10h]; unsigned int
0x1800544c9  lea     rdx, aClientid_0; "ClientId"
0x1800544d0  lea     rcx, [rsp+4E0h+var_4A0]; this
0x1800544d5  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x1800544da  test    eax, eax
0x1800544dc  jz      short loc_1800544E3
0x1800544de  mov     eax, r14d
0x1800544e1  jmp     short loc_1800544E8
0x1800544e3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800544e8  mov     rcx, [rbp+3E8h]; this
0x1800544ef  test    eax, eax
0x1800544f1  jns     short loc_180054508
0x1800544f3  mov     r9d, eax; char *
0x1800544f6  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1800544fd  mov     edx, 0BEh; void *
0x180054502  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180054508  mov     rax, [rdi]
0x18005450b  movzx   r8d, word ptr [rax+12h]; unsigned int
0x180054510  lea     rdx, aVolumeindex; "VolumeIndex"
0x180054517  lea     rcx, [rsp+4E0h+var_4A0]; this
0x18005451c  call    ?SetValue@CRegistry@@QEAAHPEB_WK@Z; CRegistry::SetValue(wchar_t const *,ulong)
0x180054521  test    eax, eax
0x180054523  jz      short loc_18005452A
0x180054525  mov     eax, r14d
0x180054528  jmp     short loc_18005452F
0x18005452a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005452f  mov     rcx, [rbp+3E8h]; this
0x180054536  test    eax, eax
0x180054538  jns     short loc_18005454F
0x18005453a  mov     r9d, eax; char *
0x18005453d  lea     r8, aOnecoreuapBase_109; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180054544  mov     edx, 0C0h; void *
0x180054549  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18005454f  mov     rax, [rdi]
0x180054552  mov     rdx, [rax+0C0h]
0x180054559  mov     qword ptr [rsp+4E0h+Data], rdx
0x18005455e  mov     rcx, [rbp+3E0h+hKey]; hKey
0x180054562  test    rcx, rcx
0x180054565  jnz     short loc_180054577
0x180054567  mov     ecx, 6; dwErrCode
0x18005456c  call    cs:__imp_SetLastError
0x180054572  mov     esi, r14d
  ... truncated ...
```
