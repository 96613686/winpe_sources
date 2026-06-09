# SessionManagerBrokerImpl::CopyDriverToLocalStorage(wchar_t const *,SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate *,TelemetryLogger::UpdateModelCacheOnDriverUpdateStart &)

- ea: `0x18005c8dc`
- end: `0x18005cdc7`
- name: `?CopyDriverToLocalStorage@SessionManagerBrokerImpl@@AEAAJPEB_WPEAUUpdateModelCacheOnDriverUpdate@1@AEAVUpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@@Z`
- size: `1259`
- prototype: `__int64 __fastcall(SessionManagerBrokerImpl *__hidden this, const wchar_t *, struct SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate *, struct TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180065ea0`

## callees

- `0x180004ca0`
- `0x180006da4`
- `0x180007f5a`
- `0x18000b064`
- `0x180012444`
- `0x180014428`
- `0x180022d14`
- `0x180024a1c`
- `0x180029c88`
- `0x180049a80`
- `0x1800580f4`
- `0x1800584e4`
- `0x18005a8f4`
- `0x18005b204`
- `0x18005c8dc`
- `0x18006c328`

## string_xrefs

- `0x18005c9d1`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x18005ca50`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x18005cd82`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\sessionmanagerbrokerimpl.cpp`
- `0x18005cd6e`: `The offline compiler parent folder path is invalid.`
- `0x18005c9c5`: `The offline compiler parent folder doesn't exist.`
- `0x18005cb50`: `The offline driver source compiler doesn't exist.`
- `0x18005c9b3`: `Failed to determine whether the offline compiler parent folder exists.`
- `0x18005cce1`: `Failed to copy the offline driver to the local storage temp folder.`
- `0x18005cb5c`: `Failed to determine whether the offline driver source compiler exists.`
- `0x18005cc35`: `Failed to create the offline driver local storage temp folder.`

## pseudocode

```c
__int64 __fastcall SessionManagerBrokerImpl::CopyDriverToLocalStorage(
        SessionManagerBrokerImpl *this,
        const wchar_t *a2,
        struct SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate *a3,
        struct TelemetryLogger::UpdateModelCacheOnDriverUpdateStart *a4)
{
  bool v4; // al
  __int64 v5; // rdx
  const char *v6; // r10
  unsigned int v7; // ebx
  __int64 v8; // r14
  __int64 v9; // r8
  struct std::error_code *v10; // r8
  bool v11; // al
  int v12; // esi
  __int64 v13; // r8
  int v14; // eax
  __int64 v15; // rax
  void **v16; // rcx
  const char *v17; // rax
  __int64 v18; // rdx
  unsigned int v19; // eax
  __int64 v20; // r8
  void **v21; // rcx
  unsigned __int64 v22; // rdx
  void **v23; // r9
  char *v24; // rdi
  __int64 v25; // rbx
  int v27; // [rsp+28h] [rbp-E0h]
  int v28; // [rsp+28h] [rbp-E0h]
  char *v29; // [rsp+30h] [rbp-D8h]
  __int64 v30; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v31; // [rsp+40h] [rbp-C8h] BYREF
  void ***v32; // [rsp+48h] [rbp-C0h]
  __int64 *directory; // [rsp+50h] [rbp-B8h] BYREF
  struct SessionManagerBrokerImpl::UpdateModelCacheOnDriverUpdate *v34; // [rsp+58h] [rbp-B0h] BYREF
  __int64 v35; // [rsp+60h] [rbp-A8h] BYREF
  _QWORD v36[7]; // [rsp+68h] [rbp-A0h] BYREF
  char v37; // [rsp+A0h] [rbp-68h]
  __int128 v38; // [rsp+A8h] [rbp-60h] BYREF
  __int128 v39; // [rsp+B8h] [rbp-50h]
  void *Src[2]; // [rsp+C8h] [rbp-40h] BYREF
  unsigned __int64 v41; // [rsp+D8h] [rbp-30h]
  unsigned __int64 v42; // [rsp+E0h] [rbp-28h]
  _OWORD v43[2]; // [rsp+E8h] [rbp-20h] BYREF
  _BYTE v44[32]; // [rsp+108h] [rbp+0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+160h] [rbp+58h]
  const wchar_t *v46; // [rsp+170h] [rbp+68h] BYREF

  v46 = a2;
  v34 = a3;
  LOWORD(v30) = 0;
  BYTE2(v30) = 0;
  LODWORD(v31) = 0;
  v32 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v36[0] = (char *)&v30 + 3;
  v36[1] = &v30;
  v36[2] = (char *)&v30 + 1;
  v36[3] = (char *)&v30 + 2;
  v36[4] = &v31;
  v36[5] = a4;
  v36[6] = &v34;
  v37 = 1;
  directory = &v31;
  if ( !qword_1800AED50 )
  {
    BYTE3(v30) = 0;
    v7 = -2147024893;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070003LL,
      (int)"The offline compiler parent folder path is invalid.",
      v29);
    goto LABEL_46;
  }
  BYTE3(v30) = 1;
  v4 = std::filesystem::exists(
         (std::filesystem *)SessionManagerBrokerImpl::s_offlineCompilerFolder,
         (const struct std::filesystem::path *)&v31,
         a3);
  LOBYTE(v30) = v4;
  if ( (_DWORD)v31 )
  {
    v5 = 943;
    v6 = L"Failed to determine whether the offline compiler parent folder exists.";
LABEL_6:
    v7 = -2147024893;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v5,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070003LL,
      (int)"%s",
      v6,
      v30);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B7,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070003LL,
      v28);
    goto LABEL_46;
  }
  if ( !v4 )
  {
    v5 = 944;
    v6 = (const char *)L"The offline compiler parent folder doesn't exist.";
    goto LABEL_6;
  }
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v46[v9] );
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v38, v46);
  v11 = std::filesystem::exists((std::filesystem *)&v38, (const struct std::filesystem::path *)&v31, v10);
  BYTE1(v30) = v11;
  v7 = -2147024893;
  if ( (_DWORD)v31 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3AF,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070003LL,
      (int)"%s",
      L"Failed to determine whether the offline driver source folder exists.",
      v30);
LABEL_11:
    v12 = -2147024893;
    goto LABEL_15;
  }
  if ( !v11 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x3B0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)0x80070003LL,
      (int)"%s",
      (const char *)L"The offline driver source folder doesn't exist.",
      v30);
    goto LABEL_11;
  }
  v12 = 0;
LABEL_15:
  std::wstring::~wstring(&v38);
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3B8,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)(unsigned int)v12,
      v27);
LABEL_17:
    v7 = v12;
    goto LABEL_46;
  }
  v13 = -1;
  do
    ++v13;
  while ( SessionManagerBrokerImpl::s_offlineCompilerFileName[v13] );
  memset(v43, 0, sizeof(v43));
  std::wstring::_Construct<1,wchar_t const *>(v43, SessionManagerBrokerImpl::s_offlineCompilerFileName);
  do
    ++v8;
  while ( v46[v8] );
  v38 = 0;
  v39 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&v38, v46);
  std::filesystem::operator/(v44, &v38, (std::filesystem *)v43);
  std::wstring::~wstring(&v38);
  std::wstring::~wstring(v43);
  LODWORD(v29) = -2147024846;
  v14 = lambda_b3465f2f485da275758dc84f55b83a41_::operator()(
          &directory,
          (char *)&v30 + 2,
          v44,
          L"Failed to determine whether the offline driver source compiler exists.");
  v12 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BB,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)(unsigned int)v14,
      (int)L"The offline driver source compiler doesn't exist.");
    std::wstring::~wstring(v44);
    goto LABEL_17;
  }
  v15 = std::to_wstring(v43);
  v38 = 0;
  v39 = 0;
  v38 = *(_OWORD *)v15;
  v39 = *(_OWORD *)(v15 + 16);
  *(_QWORD *)(v15 + 16) = 0;
  *(_QWORD *)(v15 + 24) = 7;
  *(_WORD *)v15 = 0;
  std::filesystem::operator/(Src, SessionManagerBrokerImpl::s_offlineCompilerFolder, (std::filesystem *)&v38);
  std::wstring::~wstring(&v38);
  std::wstring::~wstring(v43);
  v16 = Src;
  if ( v42 > 7 )
    v16 = (void **)Src[0];
  directory = (__int64 *)_std_fs_create_directory((LPCWSTR)v16);
  LODWORD(v31) = HIDWORD(directory);
  v32 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  if ( HIDWORD(directory) )
  {
    v17 = "Failed to create the offline driver local storage temp folder.";
    v18 = 959;
LABEL_28:
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\sessionmanagerbrokerimpl.cpp",
      (const char *)v7,
      (int)v17,
      v29);
    std::wstring::~wstring(Src);
    std::wstring::~wstring(v44);
    goto LABEL_46;
  }
  *(_QWORD *)&v38 = &v46;
  *((_QWORD *)&v38 + 1) = Src;
  *(_QWORD *)&v39 = &v31;
  v35 = TimeFunctionMilliseconds__lambda_63df111e707d6f0970ba17382aa59b3d____(&v38);
  v19 = v31;
  if ( (int)v31 > 0 )
    v19 = WORD2(directory) | 0x80070000;
  LODWORD(directory) = v19;
  TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::UpdateModelCacheOnDriverUpdateCopyDriverDuration<long,unsigned __int64 const &>(
    &directory,
    &v35);
  if ( (_DWORD)v31 )
  {
    v7 = -2147024894;
    if ( (_DWORD)v31 == 112 )
      v7 = -2147024784;
    v17 = "Failed to copy the offline driver to the local storage temp folder.";
    v18 = 965;
    goto LABEL_28;
  }
  v21 = (void **)((char *)v34 + 176);
  if ( (void **)((char *)v34 + 176) != Src )
  {
    v22 = v41;
    v23 = Src;
    if ( v42 > 7 )
      v23 = (void **)Src[0];
    if ( v41 > *((_QWORD *)v34 + 25) )
    {
      std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(v21, v41, v20, v23);
    }
    else
    {
      if ( *((_QWORD *)v34 + 25) <= 7u )
        v24 = (char *)v34 + 176;
      else
        v24 = (char *)*v21;
      *((_QWORD *)v34 + 24) = v41;
      v25 = 2 * v22;
      memmove_0(v24, v23, 2 * v22);
      *(_WORD *)&v24[v25] = 0;
    }
  }
  std::wstring::~wstring(Src);
  std::wstring::~wstring(v44);
  v7 = 0;
LABEL_46:
  wil::details::lambda_call__lambda_42114efe16f156b8c691d83e66155a9e___::_lambda_call__lambda_42114efe16f156b8c691d83e66155a9e___(v36);
  return v7;
}

```

## disassembly

```asm
0x18005c8dc  mov     rax, rsp
0x18005c8df  mov     [rax+8], rbx
0x18005c8e3  mov     [rax+20h], rsi
0x18005c8e7  mov     [rax+10h], rdx
0x18005c8eb  push    rbp
0x18005c8ec  push    rdi
0x18005c8ed  push    r12
0x18005c8ef  push    r14
0x18005c8f1  push    r15
0x18005c8f3  lea     rbp, [rax-58h]
0x18005c8f7  sub     rsp, 130h
0x18005c8fe  mov     rax, cs:__security_cookie
0x18005c905  xor     rax, rsp
0x18005c908  mov     [rbp+50h+var_30], rax
0x18005c90c  mov     [rsp+150h+var_100], r8
0x18005c911  xor     r15d, r15d
0x18005c914  mov     byte ptr [rsp+150h+var_120], r15b
0x18005c919  mov     byte ptr [rsp+150h+var_120+1], r15b
0x18005c91e  mov     byte ptr [rsp+150h+var_120+2], r15b
0x18005c923  mov     dword ptr [rsp+150h+var_118], r15d
0x18005c928  lea     r12, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18005c92f  mov     [rsp+150h+var_110], r12
0x18005c934  lea     rax, [rsp+150h+var_120+3]
0x18005c939  mov     [rsp+150h+var_F0], rax
0x18005c93e  lea     rax, [rsp+150h+var_120]
0x18005c943  mov     [rsp+150h+var_E8], rax
0x18005c948  lea     rax, [rsp+150h+var_120+1]
0x18005c94d  mov     [rsp+150h+var_E0], rax
0x18005c952  lea     rax, [rsp+150h+var_120+2]
0x18005c957  mov     [rsp+150h+var_D8], rax
0x18005c95c  lea     rax, [rsp+150h+var_118]
0x18005c961  mov     [rbp+50h+var_D0], rax
0x18005c965  mov     [rbp+50h+var_C8], r9
0x18005c969  lea     rax, [rsp+150h+var_100]
0x18005c96e  mov     [rbp+50h+var_C0], rax
0x18005c972  mov     [rbp+50h+var_B8], 1
0x18005c976  lea     rax, [rsp+150h+var_118]
0x18005c97b  mov     [rsp+150h+var_108], rax
0x18005c980  cmp     cs:qword_1800AED50, r15
0x18005c987  jz      loc_18005CD65
0x18005c98d  mov     byte ptr [rsp+150h+var_120+3], 1
0x18005c992  lea     rdx, [rsp+150h+var_118]; struct std::filesystem::path *
0x18005c997  lea     rcx, ?s_offlineCompilerFolder@SessionManagerBrokerImpl@@0Vpath@filesystem@std@@A; this
0x18005c99e  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18005c9a3  mov     byte ptr [rsp+150h+var_120], al
0x18005c9a7  cmp     dword ptr [rsp+150h+var_118], r15d
0x18005c9ac  jz      short loc_18005C9BC
0x18005c9ae  mov     edx, 3AFh
0x18005c9b3  lea     r10, aFailedToDeterm_1; "Failed to determine whether the offline"...
0x18005c9ba  jmp     short loc_18005C9CC
0x18005c9bc  test    al, al
0x18005c9be  jnz     short loc_18005CA11
0x18005c9c0  mov     edx, 3B0h; void *
0x18005c9c5  lea     r10, aTheOfflineComp_0; "The offline compiler parent folder does"...
0x18005c9cc  mov     ebx, 80070003h
0x18005c9d1  lea     rdi, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18005c9d8  lea     rax, aS; "%s"
0x18005c9df  mov     r9d, ebx; char *
0x18005c9e2  mov     r8, rdi; unsigned int
0x18005c9e5  mov     rcx, [rbp+58h]; this
0x18005c9e9  mov     [rsp+150h+var_128], r10; char *
0x18005c9ee  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005c9f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005c9f8  mov     rcx, [rbp+58h]; this
0x18005c9fc  mov     r9d, ebx; char *
0x18005c9ff  mov     r8, rdi; unsigned int
0x18005ca02  mov     edx, 3B7h; void *
0x18005ca07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005ca0c  jmp     loc_18005CD93
0x18005ca11  mov     rdx, [rbp+50h+arg_8]
0x18005ca15  or      r14, 0FFFFFFFFFFFFFFFFh
0x18005ca19  mov     r8, r14
0x18005ca1c  inc     r8
0x18005ca1f  cmp     [rdx+r8*2], r15w
0x18005ca24  jnz     short loc_18005CA1C
0x18005ca26  xorps   xmm0, xmm0
0x18005ca29  movups  [rbp+50h+var_B0], xmm0
0x18005ca2d  xorps   xmm1, xmm1
0x18005ca30  movdqu  [rbp+50h+var_A0], xmm1
0x18005ca35  lea     rcx, [rbp+50h+var_B0]
0x18005ca39  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005ca3e  lea     rdx, [rsp+150h+var_118]; struct std::filesystem::path *
0x18005ca43  lea     rcx, [rbp+50h+var_B0]; this
0x18005ca47  call    ?exists@filesystem@std@@YA_NAEBVpath@12@AEAVerror_code@2@@Z; std::filesystem::exists(std::filesystem::path const &,std::error_code &)
0x18005ca4c  mov     byte ptr [rsp+150h+var_120+1], al
0x18005ca50  lea     rdi, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18005ca57  mov     ebx, 80070003h
0x18005ca5c  cmp     dword ptr [rsp+150h+var_118], r15d
0x18005ca61  jz      short loc_18005CA93
0x18005ca63  lea     rax, aFailedToDeterm_0; "Failed to determine whether the offline"...
0x18005ca6a  mov     edx, 3AFh; void *
0x18005ca6f  mov     [rsp+150h+var_128], rax; char *
0x18005ca74  lea     rax, aS; "%s"
0x18005ca7b  mov     r8, rdi; unsigned int
0x18005ca7e  mov     r9d, ebx; char *
0x18005ca81  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005ca86  mov     rcx, [rbp+58h]; this
0x18005ca8a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005ca8f  mov     esi, ebx
0x18005ca91  jmp     short loc_18005CAA8
0x18005ca93  test    al, al
0x18005ca95  jnz     short loc_18005CAA5
0x18005ca97  lea     rax, aTheOfflineDriv_0; "The offline driver source folder doesn'"...
0x18005ca9e  mov     edx, 3B0h
0x18005caa3  jmp     short loc_18005CA6F
0x18005caa5  mov     esi, r15d
0x18005caa8  lea     rcx, [rbp+50h+var_B0]
0x18005caac  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cab1  test    esi, esi
0x18005cab3  jns     short loc_18005CAD0
0x18005cab5  mov     rcx, [rbp+58h]; this
0x18005cab9  mov     r9d, esi; char *
0x18005cabc  mov     r8, rdi; unsigned int
0x18005cabf  mov     edx, 3B8h; void *
0x18005cac4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cac9  mov     ebx, esi
0x18005cacb  jmp     loc_18005CD93
0x18005cad0  mov     rdx, cs:?s_offlineCompilerFileName@SessionManagerBrokerImpl@@0QEB_WEB; wchar_t const * const SessionManagerBrokerImpl::s_offlineCompilerFileName
0x18005cad7  mov     r8, r14
0x18005cada  inc     r8
0x18005cadd  cmp     [rdx+r8*2], r15w
0x18005cae2  jnz     short loc_18005CADA
0x18005cae4  xorps   xmm0, xmm0
0x18005cae7  movups  [rbp+50h+var_70], xmm0
0x18005caeb  xorps   xmm1, xmm1
0x18005caee  movdqu  [rbp+50h+var_60], xmm1
0x18005caf3  lea     rcx, [rbp+50h+var_70]
0x18005caf7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005cafc  mov     rdx, [rbp+50h+arg_8]
0x18005cb00  inc     r14
0x18005cb03  cmp     [rdx+r14*2], r15w
0x18005cb08  jnz     short loc_18005CB00
0x18005cb0a  xorps   xmm0, xmm0
0x18005cb0d  movups  [rbp+50h+var_B0], xmm0
0x18005cb11  xorps   xmm1, xmm1
0x18005cb14  movdqu  [rbp+50h+var_A0], xmm1
0x18005cb19  mov     r8, r14
0x18005cb1c  lea     rcx, [rbp+50h+var_B0]
0x18005cb20  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18005cb25  lea     r8, [rbp+50h+var_70]; this
0x18005cb29  lea     rdx, [rbp+50h+var_B0]; void *
0x18005cb2d  lea     rcx, [rbp+50h+var_50]; Src
0x18005cb31  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18005cb36  lea     rcx, [rbp+50h+var_B0]
0x18005cb3a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cb3f  lea     rcx, [rbp+50h+var_70]
0x18005cb43  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cb48  mov     dword ptr [rsp+150h+var_128], 80070032h; char *
0x18005cb50  lea     rax, aTheOfflineDriv; "The offline driver source compiler does"...
0x18005cb57  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005cb5c  lea     r9, aFailedToDeterm; "Failed to determine whether the offline"...
0x18005cb63  lea     r8, [rbp+50h+var_50]
0x18005cb67  lea     rdx, [rsp+150h+var_120+2]
0x18005cb6c  lea     rcx, [rsp+150h+var_108]
0x18005cb71  call    _lambda_b3465f2f485da275758dc84f55b83a41___operator__
0x18005cb76  mov     esi, eax
0x18005cb78  test    eax, eax
0x18005cb7a  jns     short loc_18005CB9E
0x18005cb7c  mov     rcx, [rbp+58h]; this
0x18005cb80  mov     r9d, eax; char *
0x18005cb83  mov     r8, rdi; unsigned int
0x18005cb86  mov     edx, 3BBh; void *
0x18005cb8b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005cb90  lea     rcx, [rbp+50h+var_50]
0x18005cb94  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cb99  jmp     loc_18005CAC9
0x18005cb9e  mov     rdx, [rsp+150h+var_100]
0x18005cba3  mov     rdx, [rdx+28h]
0x18005cba7  lea     rcx, [rbp+50h+var_70]; void *
0x18005cbab  call    ?to_wstring@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@_K@Z; std::to_wstring(unsigned __int64)
0x18005cbb0  xorps   xmm0, xmm0
0x18005cbb3  movups  [rbp+50h+var_B0], xmm0
0x18005cbb7  xorps   xmm1, xmm1
0x18005cbba  movdqu  [rbp+50h+var_A0], xmm1
0x18005cbbf  movups  xmm0, xmmword ptr [rax]
0x18005cbc2  movups  [rbp+50h+var_B0], xmm0
0x18005cbc6  movups  xmm1, xmmword ptr [rax+10h]
0x18005cbca  movups  [rbp+50h+var_A0], xmm1
0x18005cbce  mov     [rax+10h], r15
0x18005cbd2  mov     esi, 7
0x18005cbd7  mov     [rax+18h], rsi
0x18005cbdb  mov     [rax], r15w
0x18005cbdf  lea     r8, [rbp+50h+var_B0]; this
0x18005cbe3  lea     rdx, ?s_offlineCompilerFolder@SessionManagerBrokerImpl@@0Vpath@filesystem@std@@A; void *
0x18005cbea  lea     rcx, [rbp+50h+Src]; Src
0x18005cbee  call    ??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z; std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)
0x18005cbf3  lea     rcx, [rbp+50h+var_B0]
0x18005cbf7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cbfc  lea     rcx, [rbp+50h+var_70]
0x18005cc00  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cc05  lea     rcx, [rbp+50h+Src]
0x18005cc09  cmp     [rbp+50h+var_78], rsi
0x18005cc0d  cmova   rcx, [rbp+50h+Src]; lpFileName
0x18005cc12  call    __std_fs_create_directory
0x18005cc17  mov     [rsp+150h+var_108], rax
0x18005cc1c  shr     rax, 20h
0x18005cc20  mov     dword ptr [rsp+150h+var_118], eax
0x18005cc24  mov     ecx, dword ptr [rsp+150h+var_118+4]
0x18005cc28  mov     dword ptr [rsp+150h+var_118+4], ecx
0x18005cc2c  mov     [rsp+150h+var_110], r12
0x18005cc31  test    eax, eax
0x18005cc33  jz      short loc_18005CC6C
0x18005cc35  lea     rax, aFailedToCreate; "Failed to create the offline driver loc"...
0x18005cc3c  mov     edx, 3BFh; void *
0x18005cc41  mov     r8, rdi; unsigned int
0x18005cc44  mov     r9d, ebx; char *
0x18005cc47  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005cc4c  mov     rcx, [rbp+58h]; this
0x18005cc50  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005cc55  lea     rcx, [rbp+50h+Src]
0x18005cc59  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cc5e  lea     rcx, [rbp+50h+var_50]
0x18005cc62  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cc67  jmp     loc_18005CD93
0x18005cc6c  lea     rax, [rbp+50h+arg_8]
0x18005cc70  mov     qword ptr [rbp+50h+var_B0], rax
0x18005cc74  lea     rax, [rbp+50h+Src]
0x18005cc78  mov     qword ptr [rbp+50h+var_B0+8], rax
0x18005cc7c  lea     rax, [rsp+150h+var_118]
0x18005cc81  mov     qword ptr [rbp+50h+var_A0], rax
0x18005cc85  lea     rcx, [rbp+50h+var_B0]
0x18005cc89  call    TimeFunctionMilliseconds__lambda_63df111e707d6f0970ba17382aa59b3d____
0x18005cc8e  mov     [rsp+150h+var_F8], rax
0x18005cc93  mov     r8, [rsp+150h+var_100]
0x18005cc98  add     r8, 30h ; '0'
0x18005cc9c  cmp     qword ptr [r8+18h], 0Fh
0x18005cca1  jbe     short loc_18005CCA6
0x18005cca3  mov     r8, [r8]
0x18005cca6  mov     eax, dword ptr [rsp+150h+var_118]
0x18005ccaa  test    eax, eax
0x18005ccac  jle     short loc_18005CCB8
0x18005ccae  movzx   eax, word ptr [rsp+150h+var_108+4]
0x18005ccb3  or      eax, 80070000h
0x18005ccb8  mov     dword ptr [rsp+150h+var_108], eax
0x18005ccbc  lea     rdx, [rsp+150h+var_F8]
0x18005ccc1  lea     rcx, [rsp+150h+var_108]
0x18005ccc6  call    ??$UpdateModelCacheOnDriverUpdateCopyDriverDuration@JAEB_K@UpdateModelCacheOnDriverUpdateStart@TelemetryLogger@@SAX$$QEAJAEB_KPEBD@Z; TelemetryLogger::UpdateModelCacheOnDriverUpdateStart::UpdateModelCacheOnDriverUpdateCopyDriverDuration<long,unsigned __int64 const &>(long &&,unsigned __int64 const &,char const *)
0x18005cccb  mov     eax, dword ptr [rsp+150h+var_118]
0x18005cccf  test    eax, eax
0x18005ccd1  jz      short loc_18005CCF2
0x18005ccd3  mov     ebx, 80070002h
0x18005ccd8  lea     ecx, [rbx+6Eh]
0x18005ccdb  cmp     eax, 70h ; 'p'
0x18005ccde  cmovz   ebx, ecx
0x18005cce1  lea     rax, aFailedToCopyTh; "Failed to copy the offline driver to th"...
0x18005cce8  mov     edx, 3C5h
0x18005cced  jmp     loc_18005CC41
0x18005ccf2  mov     rcx, [rsp+150h+var_100]
0x18005ccf7  add     rcx, 0B0h
0x18005ccfe  lea     rax, [rbp+50h+Src]
0x18005cd02  cmp     rcx, rax
0x18005cd05  jz      short loc_18005CD4E
0x18005cd07  mov     rdx, [rbp+50h+var_80]
0x18005cd0b  lea     r9, [rbp+50h+Src]
0x18005cd0f  cmp     [rbp+50h+var_78], rsi
0x18005cd13  cmova   r9, [rbp+50h+Src]
0x18005cd18  cmp     rdx, [rcx+18h]
0x18005cd1c  ja      short loc_18005CD49
0x18005cd1e  cmp     [rcx+18h], rsi
0x18005cd22  jbe     short loc_18005CD29
0x18005cd24  mov     rdi, [rcx]
0x18005cd27  jmp     short loc_18005CD2C
0x18005cd29  mov     rdi, rcx
0x18005cd2c  mov     [rcx+10h], rdx
0x18005cd30  lea     rbx, [rdx+rdx]
0x18005cd34  mov     r8, rbx; Size
0x18005cd37  mov     rdx, r9; Src
0x18005cd3a  mov     rcx, rdi; void *
0x18005cd3d  call    memmove_0
0x18005cd42  mov     [rdi+rbx], r15w
0x18005cd47  jmp     short loc_18005CD4E
0x18005cd49  call    ??$_Reallocate_for@V_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAAEAV01@_KV_lambda_9fb449e582d5374755335d8f6d90ae34_@@PEB_W@Z; std::wstring::_Reallocate_for<_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *>(unsigned __int64,_lambda_9fb449e582d5374755335d8f6d90ae34_,wchar_t const *)
0x18005cd4e  lea     rcx, [rbp+50h+Src]
0x18005cd52  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cd57  lea     rcx, [rbp+50h+var_50]
0x18005cd5b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18005cd60  mov     ebx, r15d
0x18005cd63  jmp     short loc_18005CD93
0x18005cd65  mov     byte ptr [rsp+150h+var_120+3], r15b
0x18005cd6a  mov     rcx, [rbp+58h]; this
0x18005cd6e  lea     rax, aTheOfflineComp; "The offline compiler parent folder path"...
0x18005cd75  mov     qword ptr [rsp+150h+var_130], rax; int
0x18005cd7a  mov     ebx, 80070003h
0x18005cd7f  mov     r9d, ebx; char *
0x18005cd82  lea     r8, aOnecoreuapBase_11; "onecoreuap\\base\\appmodel\\search\\com"...
0x18005cd89  mov     edx, 3B5h; void *
0x18005cd8e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18005cd93  lea     rcx, [rsp+150h+var_F0]
0x18005cd98  call    wil__details__lambda_call__lambda_42114efe16f156b8c691d83e66155a9e______lambda_call__lambda_42114efe16f156b8c691d83e66155a9e___
0x18005cd9d  mov     eax, ebx
0x18005cd9f  mov     rcx, [rbp+50h+var_30]
0x18005cda3  xor     rcx, rsp; StackCookie
0x18005cda6  call    __security_check_cookie
0x18005cdab  lea     r11, [rsp+150h+var_20]
0x18005cdb3  mov     rbx, [r11+30h]
0x18005cdb7  mov     rsi, [r11+48h]
0x18005cdbb  mov     rsp, r11
0x18005cdbe  pop     r15
0x18005cdc0  pop     r14
0x18005cdc2  pop     r12
  ... truncated ...
```
