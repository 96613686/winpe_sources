# winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore::AppendData(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &,winrt::array_view<winrt::hstring const>,winrt::array_view<winrt::hstring const>)

- ea: `0x1800142e8`
- end: `0x1800146af`
- name: `?AppendData@ActionFxCustomEntityStore@implementation@ActionFx@AggregatedDataPlatform@Internal@Windows@winrt@@QEAAXAEBUhstring@7@00U?$array_view@$$CBUhstring@winrt@@@7@1@Z`
- size: `967`
- prototype: `int __fastcall(__int64, AggregatorsCommon::Utilities *, AggregatorsCommon::Utilities *, AggregatorsCommon::Utilities *, __int128 *, __int128 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180014250`

## callees

- `0x180002250`
- `0x180002d60`
- `0x180002e00`
- `0x180002e10`
- `0x180011f94`
- `0x180012fa0`
- `0x180013830`
- `0x1800142e8`
- `0x180016ae4`
- `0x180017960`
- `0x1800218dc`
- `0x180021aa8`
- `0x1800261b8`
- `0x180028224`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800146a8`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x1800146a8`

## pseudocode

```c
int __fastcall winrt::Windows::Internal::AggregatedDataPlatform::ActionFx::implementation::ActionFxCustomEntityStore::AppendData(
        __int64 a1,
        AggregatorsCommon::Utilities *a2,
        AggregatorsCommon::Utilities *a3,
        AggregatorsCommon::Utilities *a4,
        __int128 *a5,
        __int128 *a6)
{
  unsigned int v10; // r8d
  unsigned int v11; // r8d
  const WCHAR *v12; // rdi
  LPVOID v13; // rbx
  const wchar_t *v14; // rax
  const wchar_t *v15; // rax
  const wchar_t *v16; // rax
  CHAR *v17; // rcx
  CHAR *v18; // rcx
  __int64 v19; // rax
  CHAR *v20; // rcx
  __int64 v21; // rax
  CHAR *v22; // rcx
  __int64 v23; // rax
  int v24; // esi
  int v25; // eax
  __int64 v26; // r8
  int cbMultiByte; // r14d
  CHAR *lpMultiByteStr; // rax
  int result; // eax
  HANDLE ProcessHeap; // rax
  volatile signed __int32 *v31; // rbx
  __int128 v32; // [rsp+40h] [rbp-C0h] BYREF
  LPVOID lpMem; // [rsp+50h] [rbp-B0h] BYREF
  const wchar_t *v34; // [rsp+58h] [rbp-A8h] BYREF
  const wchar_t *v35; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v36; // [rsp+70h] [rbp-90h] BYREF
  LPSTR v37[2]; // [rsp+80h] [rbp-80h] BYREF
  __m128i si128; // [rsp+90h] [rbp-70h]
  __int128 v39; // [rsp+A0h] [rbp-60h] BYREF
  __m128i v40; // [rsp+B0h] [rbp-50h]
  _OWORD v41[2]; // [rsp+C0h] [rbp-40h] BYREF
  _OWORD v42[2]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v43[2]; // [rsp+100h] [rbp+0h] BYREF

  AggregatorsCommon::Utilities::ValidateText(a2, (const struct winrt::hstring *)0x100, (unsigned int)a3);
  AggregatorsCommon::Utilities::ValidateText(a3, (const struct winrt::hstring *)0x100, v10);
  AggregatorsCommon::Utilities::ValidateText(a4, (const struct winrt::hstring *)0x100, v11);
  v32 = *a5;
  AggregatorsCommon::Utilities::ValidateArray(&v32);
  v32 = *a6;
  AggregatorsCommon::Utilities::ValidateArray(&v32);
  CustomEntityDatabase::GetCustomEntitiesTable(*(_QWORD *)(a1 + 24), &v32);
  *(_OWORD *)v37 = *a6;
  v36 = *a5;
  anonymous_namespace_::SerializePropertiesToJsonString(&lpMem, &v36, v37);
  v12 = &S2;
  v13 = lpMem;
  if ( lpMem )
    v14 = (const wchar_t *)*((_QWORD *)lpMem + 2);
  else
    v14 = &S2;
  v34 = v14;
  if ( *(_QWORD *)a4 )
    v15 = *(const wchar_t **)(*(_QWORD *)a4 + 16LL);
  else
    v15 = &S2;
  v35 = v15;
  if ( *(_QWORD *)a3 )
    v16 = *(const wchar_t **)(*(_QWORD *)a3 + 16LL);
  else
    v16 = &S2;
  *(_QWORD *)&v36 = v16;
  if ( *(_QWORD *)a2 )
    v17 = *(CHAR **)(*(_QWORD *)a2 + 16LL);
  else
    v17 = (CHAR *)&S2;
  v37[0] = v17;
  ADPTraceLoggingProvider::ActionFxCustomEntityStore_AppendData<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(
    v37,
    &v36,
    &v35,
    &v34);
  v43[0] = 0;
  v43[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v43[0]) = 0;
  if ( *(_QWORD *)a2 )
    v18 = *(CHAR **)(*(_QWORD *)a2 + 16LL);
  else
    v18 = (CHAR *)&S2;
  v19 = -1;
  do
    ++v19;
  while ( *(_WORD *)&v18[2 * v19] );
  v37[0] = v18;
  v37[1] = (LPSTR)v19;
  to_utf8(v37, v43);
  v42[0] = 0;
  v42[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v42[0]) = 0;
  if ( *(_QWORD *)a3 )
    v20 = *(CHAR **)(*(_QWORD *)a3 + 16LL);
  else
    v20 = (CHAR *)&S2;
  v21 = -1;
  do
    ++v21;
  while ( *(_WORD *)&v20[2 * v21] );
  v37[0] = v20;
  v37[1] = (LPSTR)v21;
  to_utf8(v37, v42);
  v41[0] = 0;
  v41[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v41[0]) = 0;
  if ( *(_QWORD *)a4 )
    v22 = *(CHAR **)(*(_QWORD *)a4 + 16LL);
  else
    v22 = (CHAR *)&S2;
  v23 = -1;
  do
    ++v23;
  while ( *(_WORD *)&v22[2 * v23] );
  v37[0] = v22;
  v37[1] = (LPSTR)v23;
  to_utf8(v37, v41);
  if ( v13 )
  {
    v12 = (const WCHAR *)*((_QWORD *)v13 + 2);
    v24 = *((_DWORD *)v13 + 1);
  }
  else
  {
    v24 = 0;
  }
  v25 = WINRT_IMPL_WideCharToMultiByte(0xFDE9u, 0, v12, v24, 0, 0, 0, 0);
  cbMultiByte = v25;
  if ( v25 )
  {
    LOBYTE(v26) = 63;
    std::string::string(v37, v25, v26);
    lpMultiByteStr = (CHAR *)v37;
    if ( si128.m128i_i64[1] > 0xFuLL )
      lpMultiByteStr = v37[0];
    WINRT_IMPL_WideCharToMultiByte(0xFDE9u, 0, v12, v24, lpMultiByteStr, cbMultiByte, 0, 0);
    v39 = *(_OWORD *)v37;
    v40 = si128;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v37[0]) = 0;
    std::string::~string(v37);
  }
  else
  {
    v39 = 0;
    v40 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v39) = 0;
  }
  CustomEntityTable::UpdateData(v32, (unsigned int)v43, (unsigned int)v42, (unsigned int)v41, (__int64)&v39);
  std::string::~string(&v39);
  std::string::~string(v41);
  std::string::~string(v42);
  result = std::string::~string(v43);
  if ( v13 )
  {
    result = _InterlockedDecrement((volatile signed __int32 *)v13 + 6);
    if ( result )
    {
      if ( result < 0 )
        abort();
    }
    else
    {
      ProcessHeap = WINRT_IMPL_GetProcessHeap();
      result = WINRT_IMPL_HeapFree(ProcessHeap, 0, v13);
    }
  }
  v31 = (volatile signed __int32 *)*((_QWORD *)&v32 + 1);
  if ( *((_QWORD *)&v32 + 1) )
  {
    result = _InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v32 + 1) + 8LL));
    if ( !result )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v31)(v31);
      result = _InterlockedDecrement(v31 + 3);
      if ( !result )
        return (*(__int64 (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v31 + 8LL))(v31);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800142e8  push    rbp
0x1800142ea  push    rbx
0x1800142eb  push    rsi
0x1800142ec  push    rdi
0x1800142ed  push    r12
0x1800142ef  push    r13
0x1800142f1  push    r14
0x1800142f3  push    r15
0x1800142f5  lea     rbp, [rsp-38h]
0x1800142fa  sub     rsp, 138h
0x180014301  mov     rax, cs:__security_cookie
0x180014308  xor     rax, rsp
0x18001430b  mov     [rbp+70h+var_50], rax
0x18001430f  mov     r12, r9
0x180014312  mov     r15, r8
0x180014315  mov     r14, rdx
0x180014318  mov     rsi, rcx
0x18001431b  mov     rdi, [rbp+70h+arg_20]
0x180014322  mov     rbx, [rbp+70h+arg_28]
0x180014329  mov     r13d, 100h
0x18001432f  mov     edx, r13d; struct winrt::hstring *
0x180014332  mov     rcx, r14; this
0x180014335  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x18001433a  mov     edx, r13d; struct winrt::hstring *
0x18001433d  mov     rcx, r15; this
0x180014340  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x180014345  mov     edx, r13d; struct winrt::hstring *
0x180014348  mov     rcx, r12; this
0x18001434b  call    ?ValidateText@Utilities@AggregatorsCommon@@YAXAEBUhstring@winrt@@I@Z; AggregatorsCommon::Utilities::ValidateText(winrt::hstring const &,uint)
0x180014350  movaps  xmm0, xmmword ptr [rdi]
0x180014353  movdqa  [rsp+170h+var_130], xmm0
0x180014359  lea     rcx, [rsp+170h+var_130]
0x18001435e  call    ?ValidateArray@Utilities@AggregatorsCommon@@YAXU?$array_view@$$CBUhstring@winrt@@@winrt@@II@Z; AggregatorsCommon::Utilities::ValidateArray(winrt::array_view<winrt::hstring const>,uint,uint)
0x180014363  movaps  xmm0, xmmword ptr [rbx]
0x180014366  movdqa  [rsp+170h+var_130], xmm0
0x18001436c  lea     rcx, [rsp+170h+var_130]
0x180014371  call    ?ValidateArray@Utilities@AggregatorsCommon@@YAXU?$array_view@$$CBUhstring@winrt@@@winrt@@II@Z; AggregatorsCommon::Utilities::ValidateArray(winrt::array_view<winrt::hstring const>,uint,uint)
0x180014376  lea     rdx, [rsp+170h+var_130]
0x18001437b  mov     rcx, [rsi+18h]
0x18001437f  call    ?GetCustomEntitiesTable@CustomEntityDatabase@@QEAA?AV?$shared_ptr@UCustomEntityTable@@@std@@XZ; CustomEntityDatabase::GetCustomEntitiesTable(void)
0x180014384  nop
0x180014385  movaps  xmm0, xmmword ptr [rbx]
0x180014388  movdqa  xmmword ptr [rbp+70h+var_F0], xmm0
0x18001438d  movaps  xmm1, xmmword ptr [rdi]
0x180014390  movdqa  [rsp+170h+var_100], xmm1
0x180014396  lea     r8, [rbp+70h+var_F0]
0x18001439a  lea     rdx, [rsp+170h+var_100]
0x18001439f  lea     rcx, [rsp+170h+lpMem]
0x1800143a4  call    _anonymous_namespace___SerializePropertiesToJsonString
0x1800143a9  nop
0x1800143aa  lea     rdi, S2
0x1800143b1  mov     rbx, [rsp+170h+lpMem]
0x1800143b6  xor     r13d, r13d
0x1800143b9  test    rbx, rbx
0x1800143bc  jz      short loc_1800143C4
0x1800143be  mov     rax, [rbx+10h]
0x1800143c2  jmp     short loc_1800143C7
0x1800143c4  mov     rax, rdi
0x1800143c7  mov     [rsp+170h+var_118], rax
0x1800143cc  mov     rax, [r12]
0x1800143d0  test    rax, rax
0x1800143d3  jz      short loc_1800143DB
0x1800143d5  mov     rax, [rax+10h]
0x1800143d9  jmp     short loc_1800143DE
0x1800143db  mov     rax, rdi
0x1800143de  mov     [rsp+170h+var_110], rax
0x1800143e3  mov     rax, [r15]
0x1800143e6  test    rax, rax
0x1800143e9  jz      short loc_1800143F1
0x1800143eb  mov     rax, [rax+10h]
0x1800143ef  jmp     short loc_1800143F4
0x1800143f1  mov     rax, rdi
0x1800143f4  mov     qword ptr [rsp+170h+var_100], rax
0x1800143f9  mov     rax, [r14]
0x1800143fc  test    rax, rax
0x1800143ff  jz      short loc_180014407
0x180014401  mov     rcx, [rax+10h]
0x180014405  jmp     short loc_18001440A
0x180014407  mov     rcx, rdi
0x18001440a  mov     [rbp+70h+var_F0], rcx
0x18001440e  lea     r9, [rsp+170h+var_118]
0x180014413  lea     r8, [rsp+170h+var_110]
0x180014418  lea     rdx, [rsp+170h+var_100]
0x18001441d  lea     rcx, [rbp+70h+var_F0]
0x180014421  call    ??$ActionFxCustomEntityStore_AppendData@PEB_WPEB_WPEB_WPEB_W@ADPTraceLoggingProvider@@SAX$$QEAPEB_W000@Z; ADPTraceLoggingProvider::ActionFxCustomEntityStore_AppendData<wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *>(wchar_t const * &&,wchar_t const * &&,wchar_t const * &&,wchar_t const * &&)
0x180014426  xorps   xmm0, xmm0
0x180014429  movups  [rbp+70h+var_70], xmm0
0x18001442d  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180014435  movdqu  [rbp+70h+var_60], xmm1
0x18001443a  mov     byte ptr [rbp+70h+var_70], r13b
0x18001443e  mov     rcx, [r14]
0x180014441  test    rcx, rcx
0x180014444  jz      short loc_18001444C
0x180014446  mov     rcx, [rcx+10h]
0x18001444a  jmp     short loc_18001444F
0x18001444c  mov     rcx, rdi
0x18001444f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180014453  inc     rax
0x180014456  cmp     [rcx+rax*2], r13w
0x18001445b  jnz     short loc_180014453
0x18001445d  mov     [rbp+70h+var_F0], rcx
0x180014461  mov     [rbp+70h+var_F0+8], rax
0x180014465  lea     rdx, [rbp+70h+var_70]
0x180014469  lea     rcx, [rbp+70h+var_F0]
0x18001446d  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x180014472  xorps   xmm0, xmm0
0x180014475  movups  [rbp+70h+var_90], xmm0
0x180014479  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x180014481  movdqu  [rbp+70h+var_80], xmm1
0x180014486  mov     byte ptr [rbp+70h+var_90], r13b
0x18001448a  mov     rcx, [r15]
0x18001448d  test    rcx, rcx
0x180014490  jz      short loc_180014498
0x180014492  mov     rcx, [rcx+10h]
0x180014496  jmp     short loc_18001449B
0x180014498  mov     rcx, rdi
0x18001449b  or      r15, 0FFFFFFFFFFFFFFFFh
0x18001449f  mov     rax, r15
0x1800144a2  inc     rax
0x1800144a5  cmp     [rcx+rax*2], r13w
0x1800144aa  jnz     short loc_1800144A2
0x1800144ac  mov     [rbp+70h+var_F0], rcx
0x1800144b0  mov     [rbp+70h+var_F0+8], rax
0x1800144b4  lea     rdx, [rbp+70h+var_90]
0x1800144b8  lea     rcx, [rbp+70h+var_F0]
0x1800144bc  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x1800144c1  xorps   xmm0, xmm0
0x1800144c4  movups  [rbp+70h+var_B0], xmm0
0x1800144c8  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x1800144d0  movdqu  [rbp+70h+var_A0], xmm1
0x1800144d5  mov     byte ptr [rbp+70h+var_B0], r13b
0x1800144d9  mov     rcx, [r12]
0x1800144dd  test    rcx, rcx
0x1800144e0  jz      short loc_1800144E8
0x1800144e2  mov     rcx, [rcx+10h]
0x1800144e6  jmp     short loc_1800144EB
0x1800144e8  mov     rcx, rdi
0x1800144eb  mov     rax, r15
0x1800144ee  inc     rax
0x1800144f1  cmp     [rcx+rax*2], r13w
0x1800144f6  jnz     short loc_1800144EE
0x1800144f8  mov     [rbp+70h+var_F0], rcx
0x1800144fc  mov     [rbp+70h+var_F0+8], rax
0x180014500  lea     rdx, [rbp+70h+var_B0]
0x180014504  lea     rcx, [rbp+70h+var_F0]
0x180014508  call    ?to_utf8@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEAV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@@Z; to_utf8(std::wstring_view,std::string &)
0x18001450d  test    rbx, rbx
0x180014510  jz      short loc_18001451B
0x180014512  mov     rdi, [rbx+10h]
0x180014516  mov     esi, [rbx+4]
0x180014519  jmp     short loc_18001451E
0x18001451b  mov     rsi, r13
0x18001451e  mov     [rsp+170h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x180014523  mov     [rsp+170h+lpDefaultChar], r13; lpDefaultChar
0x180014528  mov     [rsp+170h+cbMultiByte], r13d; cbMultiByte
0x18001452d  mov     [rsp+170h+lpMultiByteStr], r13; lpMultiByteStr
0x180014532  mov     r9d, esi; cchWideChar
0x180014535  mov     r8, rdi; lpWideCharStr
0x180014538  xor     edx, edx; dwFlags
0x18001453a  mov     r12d, 0FDE9h
0x180014540  mov     ecx, r12d; CodePage
0x180014543  call    WINRT_IMPL_WideCharToMultiByte
0x180014548  movsxd  r14, eax
0x18001454b  test    eax, eax
0x18001454d  jnz     short loc_180014569
0x18001454f  xorps   xmm0, xmm0
0x180014552  movups  [rbp+70h+var_D0], xmm0
0x180014556  movdqa  xmm1, cs:__xmm@000000000000000f0000000000000000
0x18001455e  movdqu  [rbp+70h+var_C0], xmm1
0x180014563  mov     byte ptr [rbp+70h+var_D0], r13b
0x180014567  jmp     short loc_1800145D5
0x180014569  mov     rdx, r14
0x18001456c  mov     r8b, 3Fh ; '?'
0x18001456f  lea     rcx, [rbp+70h+var_F0]
0x180014573  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@_KD@Z; std::string::string(unsigned __int64,char)
0x180014578  lea     rax, [rbp+70h+var_F0]
0x18001457c  cmp     [rbp+70h+var_D8], 0Fh
0x180014581  cmova   rax, [rbp+70h+var_F0]
0x180014586  mov     [rsp+170h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x18001458b  mov     [rsp+170h+lpDefaultChar], r13; lpDefaultChar
0x180014590  mov     [rsp+170h+cbMultiByte], r14d; cbMultiByte
0x180014595  mov     [rsp+170h+lpMultiByteStr], rax; lpMultiByteStr
0x18001459a  mov     r9d, esi; cchWideChar
0x18001459d  mov     r8, rdi; lpWideCharStr
0x1800145a0  xor     edx, edx; dwFlags
0x1800145a2  mov     ecx, r12d; CodePage
0x1800145a5  call    WINRT_IMPL_WideCharToMultiByte
0x1800145aa  movups  xmm0, xmmword ptr [rbp+70h+var_F0]
0x1800145ae  movups  [rbp+70h+var_D0], xmm0
0x1800145b2  movups  xmm1, xmmword ptr [rbp-70h]
0x1800145b6  movups  [rbp+70h+var_C0], xmm1
0x1800145ba  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800145c2  movdqu  xmmword ptr [rbp-70h], xmm0
0x1800145c7  mov     byte ptr [rbp+70h+var_F0], r13b
0x1800145cb  lea     rcx, [rbp+70h+var_F0]
0x1800145cf  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800145d4  nop
0x1800145d5  lea     rax, [rbp+70h+var_D0]
0x1800145d9  mov     [rsp+170h+lpMultiByteStr], rax
0x1800145de  lea     r9, [rbp+70h+var_B0]
0x1800145e2  lea     r8, [rbp+70h+var_90]
0x1800145e6  lea     rdx, [rbp+70h+var_70]
0x1800145ea  mov     rcx, qword ptr [rsp+170h+var_130]
0x1800145ef  call    ?UpdateData@CustomEntityTable@@QEAAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@000@Z; CustomEntityTable::UpdateData(std::string const &,std::string const &,std::string const &,std::string const &)
0x1800145f4  nop
0x1800145f5  lea     rcx, [rbp+70h+var_D0]
0x1800145f9  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1800145fe  nop
0x1800145ff  lea     rcx, [rbp+70h+var_B0]
0x180014603  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180014608  nop
0x180014609  lea     rcx, [rbp+70h+var_90]
0x18001460d  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180014612  nop
0x180014613  lea     rcx, [rbp+70h+var_70]
0x180014617  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x18001461c  nop
0x18001461d  test    rbx, rbx
0x180014620  jz      short loc_180014643
0x180014622  mov     eax, r15d
0x180014625  lock xadd [rbx+18h], eax
0x18001462a  sub     eax, 1
0x18001462d  jnz     short loc_1800146A4
0x18001462f  nop
0x180014630  call    WINRT_IMPL_GetProcessHeap
0x180014635  mov     rcx, rax; hHeap
0x180014638  mov     r8, rbx; lpMem
0x18001463b  xor     edx, edx; dwFlags
0x18001463d  call    WINRT_IMPL_HeapFree
0x180014642  nop
0x180014643  mov     rbx, qword ptr [rsp+170h+var_130+8]
0x180014648  test    rbx, rbx
0x18001464b  jz      short loc_180014684
0x18001464d  mov     eax, r15d
0x180014650  lock xadd [rbx+8], eax
0x180014655  add     eax, r15d
0x180014658  jnz     short loc_180014684
0x18001465a  mov     rax, [rbx]
0x18001465d  mov     rcx, rbx
0x180014660  mov     rax, [rax]
0x180014663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014668  mov     eax, r15d
0x18001466b  lock xadd [rbx+0Ch], eax
0x180014670  add     eax, r15d
0x180014673  jnz     short loc_180014684
0x180014675  mov     rax, [rbx]
0x180014678  mov     rcx, rbx
0x18001467b  mov     rax, [rax+8]
0x18001467f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014684  mov     rcx, [rbp+70h+var_50]
0x180014688  xor     rcx, rsp; StackCookie
0x18001468b  call    __security_check_cookie
0x180014690  add     rsp, 138h
0x180014697  pop     r15
0x180014699  pop     r14
0x18001469b  pop     r13
0x18001469d  pop     r12
0x18001469f  pop     rdi
0x1800146a0  pop     rsi
0x1800146a1  pop     rbx
0x1800146a2  pop     rbp
0x1800146a3  retn
0x1800146a4  test    eax, eax
0x1800146a6  jns     short loc_180014643
0x1800146a8  call    cs:__imp_abort
```
