# UpdatePolicyProvider::RuntimeClassInitialize(Windows::Data::Json::IJsonObject *)

- ea: `0x180054618`
- end: `0x18005492f`
- name: `?RuntimeClassInitialize@UpdatePolicyProvider@@QEAAJPEAUIJsonObject@Json@Data@Windows@@@Z`
- size: `791`
- prototype: `__int64 __fastcall(UpdatePolicyProvider *__hidden this, struct Windows::Data::Json::IJsonObject *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800476e0`

## callees

- `0x180004b80`
- `0x18000aa48`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180053504`
- `0x180054618`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005485b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18005485b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054885`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548ef`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180054885`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800548ef`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054694`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005472e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800547a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054816`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054694`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18005472e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800547a6`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180054816`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800546a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800547ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005482a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800546a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180054742`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800547ba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18005482a`

## string_xrefs

- `0x18005487e`: `ReadPolicy`
- `0x1800548ac`: `ReadPolicyWithFallback`
- `0x1800548ca`: `ReleaseUpdatePolicyValue`
- `0x1800546cb`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x18005489b`: `onecore\base\flighting\flightsettings\broker\libs\ctac\updatepolicyprovider.cpp`
- `0x18005484e`: `updatepolicy.dll`

## pseudocode

```c
__int64 __fastcall UpdatePolicyProvider::RuntimeClassInitialize(
        UpdatePolicyProvider *this,
        struct Windows::Data::Json::IJsonObject *a2)
{
  __int64 v2; // rax
  unsigned __int64 v3; // rbx
  __int64 (__fastcall *v5)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // r15
  unsigned __int64 v7; // rcx
  int v8; // eax
  unsigned int v9; // esi
  unsigned __int64 v11; // rcx
  int (__fastcall *v12)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *); // r15
  bool v13; // sf
  int v14; // eax
  unsigned __int64 v15; // rcx
  __int64 v16; // rax
  int (__fastcall *v17)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r15
  __int64 v18; // rax
  int (__fastcall *v19)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *); // r15
  HMODULE *v20; // rbx
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  const char *v23; // r9
  __int64 v24; // rdx
  FARPROC v25; // rax
  FARPROC v26; // rax
  FARPROC v27; // rax
  UINT32 length; // [rsp+20h] [rbp-50h] BYREF
  double v29; // [rsp+28h] [rbp-48h] BYREF
  double v30; // [rsp+30h] [rbp-40h] BYREF
  HSTRING string; // [rsp+38h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+28h]

  v2 = *(_QWORD *)a2;
  v3 = -1;
  v29 = 0.0;
  length = 0;
  v5 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(v2 + 88);
  v7 = -1;
  do
    ++v7;
  while ( UpdatePolicyProvider::s_pszJsonTagPolicy[v7] );
  if ( (int)ULongLongToUInt(v7, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(UpdatePolicyProvider::s_pszJsonTagPolicy, length, &hstringHeader, &string);
  v8 = v5(a2, string, &v29);
  v9 = v8;
  if ( v8 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
      (const char *)(unsigned int)v8,
      length);
    return v9;
  }
  v11 = -1;
  length = 0;
  v30 = 0.0;
  *((_DWORD *)this + 14) = (int)v29;
  v12 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, double *))(*(_QWORD *)a2 + 88LL);
  do
    ++v11;
  while ( UpdatePolicyProvider::s_pszJsonTagVariantFlags[v11] );
  if ( (int)ULongLongToUInt(v11, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(UpdatePolicyProvider::s_pszJsonTagVariantFlags, length, &hstringHeader, &string);
  v13 = v12(a2, string, &v30) < 0;
  v14 = (int)v30;
  if ( v13 )
    LOWORD(v14) = 0;
  *((_WORD *)this + 30) = v14;
  v15 = -1;
  v16 = *(_QWORD *)a2;
  length = 0;
  v17 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(v16 + 96);
  do
    ++v15;
  while ( UpdatePolicyProvider::s_pszJsonTagEnterprise[v15] );
  if ( (int)ULongLongToUInt(v15, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(UpdatePolicyProvider::s_pszJsonTagEnterprise, length, &hstringHeader, &string);
  if ( v17(a2, string, (char *)this + 62) < 0 )
    *((_BYTE *)this + 62) = 0;
  v18 = *(_QWORD *)a2;
  length = 0;
  v19 = *(int (__fastcall **)(struct Windows::Data::Json::IJsonObject *, HSTRING, char *))(v18 + 96);
  do
    ++v3;
  while ( UpdatePolicyProvider::s_pszJsonTagUseSource[v3] );
  if ( (int)ULongLongToUInt(v3, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  WindowsCreateStringReference(UpdatePolicyProvider::s_pszJsonTagUseSource, length, &hstringHeader, &string);
  if ( v19(a2, string, (char *)this + 63) < 0 )
    *((_BYTE *)this + 63) = 0;
  v20 = (HMODULE *)((char *)this + 16);
  Library = LoadLibraryExW(L"updatepolicy.dll", 0, 0);
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    (char *)this + 16,
    Library);
  if ( !*((_QWORD *)this + 2) )
    return wil::details::GetLastErrorFailHr(0);
  ProcAddress = GetProcAddress(*((HMODULE *)this + 2), "ReadPolicy");
  *((_QWORD *)this + 3) = ProcAddress;
  if ( !ProcAddress )
  {
    v24 = 68;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v24,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
             v23);
  }
  v25 = GetProcAddress(*v20, "ReadPolicyWithFallback");
  *((_QWORD *)this + 4) = v25;
  if ( !v25 )
  {
    v24 = 71;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v24,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
             v23);
  }
  v26 = GetProcAddress(*v20, "ReleaseUpdatePolicyValue");
  *((_QWORD *)this + 5) = v26;
  if ( !v26 )
  {
    v24 = 74;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v24,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
             v23);
  }
  v27 = GetProcAddress(*v20, "ReleaseEnterprisePolicyValue");
  *((_QWORD *)this + 6) = v27;
  if ( !v27 )
  {
    v24 = 77;
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)v24,
             (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\ctac\\updatepolicyprovider.cpp",
             v23);
  }
  return 0;
}

```

## disassembly

```asm
0x180054618  mov     [rsp-28h+arg_10], rbx
0x18005461d  mov     [rsp-28h+arg_18], rsi
0x180054622  push    rbp
0x180054623  push    rdi
0x180054624  push    r12
0x180054626  push    r14
0x180054628  push    r15
0x18005462a  mov     rbp, rsp
0x18005462d  sub     rsp, 70h
0x180054631  movaps  [rsp+70h+var_10], xmm6
0x180054636  mov     rax, cs:__security_cookie
0x18005463d  xor     rax, rsp
0x180054640  mov     [rbp+var_18], rax
0x180054644  mov     rax, [rdx]
0x180054647  xor     r12d, r12d
0x18005464a  mov     rsi, cs:?s_pszJsonTagPolicy@UpdatePolicyProvider@@0QEBGEB; ushort const * const UpdatePolicyProvider::s_pszJsonTagPolicy
0x180054651  xorps   xmm6, xmm6
0x180054654  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180054658  movsd   [rbp+var_48], xmm6
0x18005465d  mov     rdi, rcx
0x180054660  mov     [rbp+length], r12d
0x180054664  mov     r15, [rax+58h]
0x180054668  mov     r14, rdx
0x18005466b  mov     rcx, rbx
0x18005466e  inc     rcx; unsigned __int64
0x180054671  cmp     [rsi+rcx*2], r12w
0x180054676  jnz     short loc_18005466E
0x180054678  lea     rdx, [rbp+length]; unsigned int *
0x18005467c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180054681  test    eax, eax
0x180054683  jns     short loc_18005469A
0x180054685  xor     r9d, r9d; lpArguments
0x180054688  xor     r8d, r8d; nNumberOfArguments
0x18005468b  mov     ecx, 0C000000Dh; dwExceptionCode
0x180054690  lea     edx, [r9+1]; dwExceptionFlags
0x180054694  call    cs:__imp_RaiseException
0x18005469a  mov     edx, [rbp+length]; length
0x18005469d  lea     r9, [rbp+string]; string
0x1800546a1  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800546a5  mov     rcx, rsi; sourceString
0x1800546a8  call    cs:__imp_WindowsCreateStringReference
0x1800546ae  mov     rdx, [rbp+string]
0x1800546b2  lea     r8, [rbp+var_48]
0x1800546b6  mov     rcx, r14
0x1800546b9  mov     rax, r15
0x1800546bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800546c1  mov     esi, eax
0x1800546c3  test    eax, eax
0x1800546c5  jns     short loc_1800546E6
0x1800546c7  mov     rcx, [rbp+28h]; this
0x1800546cb  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800546d2  mov     r9d, eax; char *
0x1800546d5  mov     edx, 2Ah ; '*'; void *
0x1800546da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800546df  mov     eax, esi
0x1800546e1  jmp     loc_180054905
0x1800546e6  cvttsd2si eax, [rbp+var_48]
0x1800546eb  mov     rcx, rbx
0x1800546ee  mov     [rbp+length], r12d
0x1800546f2  movsd   [rbp+var_40], xmm6
0x1800546f7  mov     [rdi+38h], eax
0x1800546fa  mov     rax, [r14]
0x1800546fd  mov     rsi, cs:?s_pszJsonTagVariantFlags@UpdatePolicyProvider@@0QEBGEB; ushort const * const UpdatePolicyProvider::s_pszJsonTagVariantFlags
0x180054704  mov     r15, [rax+58h]
0x180054708  inc     rcx; unsigned __int64
0x18005470b  cmp     [rsi+rcx*2], r12w
0x180054710  jnz     short loc_180054708
0x180054712  lea     rdx, [rbp+length]; unsigned int *
0x180054716  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x18005471b  test    eax, eax
0x18005471d  jns     short loc_180054734
0x18005471f  xor     r9d, r9d; lpArguments
0x180054722  xor     r8d, r8d; nNumberOfArguments
0x180054725  mov     ecx, 0C000000Dh; dwExceptionCode
0x18005472a  lea     edx, [r9+1]; dwExceptionFlags
0x18005472e  call    cs:__imp_RaiseException
0x180054734  mov     edx, [rbp+length]; length
0x180054737  lea     r9, [rbp+string]; string
0x18005473b  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18005473f  mov     rcx, rsi; sourceString
0x180054742  call    cs:__imp_WindowsCreateStringReference
0x180054748  mov     rdx, [rbp+string]
0x18005474c  lea     r8, [rbp+var_40]
0x180054750  mov     rcx, r14
0x180054753  mov     rax, r15
0x180054756  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005475b  test    eax, eax
0x18005475d  cvttsd2si eax, [rbp+var_40]
0x180054762  jns     short loc_180054767
0x180054764  mov     eax, r12d
0x180054767  mov     [rdi+3Ch], ax
0x18005476b  mov     rcx, rbx
0x18005476e  mov     rax, [r14]
0x180054771  mov     rsi, cs:?s_pszJsonTagEnterprise@UpdatePolicyProvider@@0QEBGEB; ushort const * const UpdatePolicyProvider::s_pszJsonTagEnterprise
0x180054778  mov     [rbp+length], r12d
0x18005477c  mov     r15, [rax+60h]
0x180054780  inc     rcx; unsigned __int64
0x180054783  cmp     [rsi+rcx*2], r12w
0x180054788  jnz     short loc_180054780
0x18005478a  lea     rdx, [rbp+length]; unsigned int *
0x18005478e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180054793  test    eax, eax
0x180054795  jns     short loc_1800547AC
0x180054797  xor     r9d, r9d; lpArguments
0x18005479a  xor     r8d, r8d; nNumberOfArguments
0x18005479d  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800547a2  lea     edx, [r9+1]; dwExceptionFlags
0x1800547a6  call    cs:__imp_RaiseException
0x1800547ac  mov     edx, [rbp+length]; length
0x1800547af  lea     r9, [rbp+string]; string
0x1800547b3  lea     r8, [rbp+hstringHeader]; hstringHeader
0x1800547b7  mov     rcx, rsi; sourceString
0x1800547ba  call    cs:__imp_WindowsCreateStringReference
0x1800547c0  mov     rdx, [rbp+string]
0x1800547c4  lea     r8, [rdi+3Eh]
0x1800547c8  mov     rcx, r14
0x1800547cb  mov     rax, r15
0x1800547ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800547d3  test    eax, eax
0x1800547d5  jns     short loc_1800547DB
0x1800547d7  mov     [rdi+3Eh], r12b
0x1800547db  mov     rax, [r14]
0x1800547de  mov     rsi, cs:?s_pszJsonTagUseSource@UpdatePolicyProvider@@0QEBGEB; ushort const * const UpdatePolicyProvider::s_pszJsonTagUseSource
0x1800547e5  mov     [rbp+length], r12d
0x1800547e9  mov     r15, [rax+60h]
0x1800547ed  inc     rbx
0x1800547f0  cmp     [rsi+rbx*2], r12w
0x1800547f5  jnz     short loc_1800547ED
0x1800547f7  lea     rdx, [rbp+length]; unsigned int *
0x1800547fb  mov     rcx, rbx; unsigned __int64
0x1800547fe  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x180054803  test    eax, eax
0x180054805  jns     short loc_18005481C
0x180054807  xor     r9d, r9d; lpArguments
0x18005480a  xor     r8d, r8d; nNumberOfArguments
0x18005480d  mov     ecx, 0C000000Dh; dwExceptionCode
0x180054812  lea     edx, [r9+1]; dwExceptionFlags
0x180054816  call    cs:__imp_RaiseException
0x18005481c  mov     edx, [rbp+length]; length
0x18005481f  lea     r9, [rbp+string]; string
0x180054823  lea     r8, [rbp+hstringHeader]; hstringHeader
0x180054827  mov     rcx, rsi; sourceString
0x18005482a  call    cs:__imp_WindowsCreateStringReference
0x180054830  mov     rdx, [rbp+string]
0x180054834  lea     r8, [rdi+3Fh]
0x180054838  mov     rcx, r14
0x18005483b  mov     rax, r15
0x18005483e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054843  test    eax, eax
0x180054845  jns     short loc_18005484B
0x180054847  mov     [rdi+3Fh], r12b
0x18005484b  xor     r8d, r8d; dwFlags
0x18005484e  lea     rcx, LibFileName; "updatepolicy.dll"
0x180054855  xor     edx, edx; hFile
0x180054857  lea     rbx, [rdi+10h]
0x18005485b  call    cs:__imp_LoadLibraryExW
0x180054861  mov     rdx, rax
0x180054864  mov     rcx, rbx
0x180054867  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18005486c  mov     rcx, [rbx]; this
0x18005486f  test    rcx, rcx
0x180054872  jnz     short loc_18005487E
0x180054874  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180054879  jmp     loc_180054905
0x18005487e  lea     rdx, ProcName; "ReadPolicy"
0x180054885  call    cs:__imp_GetProcAddress
0x18005488b  mov     [rdi+18h], rax
0x18005488f  test    rax, rax
0x180054892  jnz     short loc_1800548A9
0x180054894  lea     edx, [rax+44h]; void *
0x180054897  mov     rcx, [rbp+28h]; this
0x18005489b  lea     r8, aOnecoreBaseFli_94; "onecore\\base\\flighting\\flightsetting"...
0x1800548a2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800548a7  jmp     short loc_180054905
0x1800548a9  mov     rcx, [rbx]; hModule
0x1800548ac  lea     rdx, aReadpolicywith; "ReadPolicyWithFallback"
0x1800548b3  call    cs:__imp_GetProcAddress
0x1800548b9  mov     [rdi+20h], rax
0x1800548bd  test    rax, rax
0x1800548c0  jnz     short loc_1800548C7
0x1800548c2  lea     edx, [rax+47h]
0x1800548c5  jmp     short loc_180054897
0x1800548c7  mov     rcx, [rbx]; hModule
0x1800548ca  lea     rdx, aReleaseupdatep; "ReleaseUpdatePolicyValue"
0x1800548d1  call    cs:__imp_GetProcAddress
0x1800548d7  mov     [rdi+28h], rax
0x1800548db  test    rax, rax
0x1800548de  jnz     short loc_1800548E5
0x1800548e0  lea     edx, [rax+4Ah]
0x1800548e3  jmp     short loc_180054897
0x1800548e5  mov     rcx, [rbx]; hModule
0x1800548e8  lea     rdx, aReleaseenterpr; "ReleaseEnterprisePolicyValue"
0x1800548ef  call    cs:__imp_GetProcAddress
0x1800548f5  mov     [rdi+30h], rax
0x1800548f9  test    rax, rax
0x1800548fc  jnz     short loc_180054903
0x1800548fe  lea     edx, [rax+4Dh]
0x180054901  jmp     short loc_180054897
0x180054903  xor     eax, eax
0x180054905  mov     rcx, [rbp+var_18]
0x180054909  xor     rcx, rsp; StackCookie
0x18005490c  call    __security_check_cookie
0x180054911  lea     r11, [rsp+70h+var_s0]
0x180054916  mov     rbx, [r11+40h]
0x18005491a  mov     rsi, [r11+48h]
0x18005491e  movaps  xmm6, [rsp+70h+var_10]
0x180054923  mov     rsp, r11
0x180054926  pop     r15
0x180054928  pop     r14
0x18005492a  pop     r12
0x18005492c  pop     rdi
0x18005492d  pop     rbp
0x18005492e  retn
```
