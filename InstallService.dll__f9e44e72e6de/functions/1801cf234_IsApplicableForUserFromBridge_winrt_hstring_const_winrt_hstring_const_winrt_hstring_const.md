# IsApplicableForUserFromBridge(winrt::hstring const &,winrt::hstring const &,winrt::hstring const &)

- ea: `0x1801cf234`
- end: `0x1801cf6d4`
- name: `?IsApplicableForUserFromBridge@@YA_NAEBUhstring@winrt@@00@Z`
- size: `1184`
- prototype: `bool __fastcall(const struct winrt::hstring *, const struct winrt::hstring *, const struct winrt::hstring *)`
- caller_count: `1`
- callee_count: `27`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801c2500`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180014f18`
- `0x18001bf24`
- `0x18001f784`
- `0x180020868`
- `0x180020960`
- `0x180022298`
- `0x1800309b0`
- `0x180031d3c`
- `0x180037200`
- `0x1800453a0`
- `0x1800453bc`
- `0x180045588`
- `0x18006cc00`
- `0x180073110`
- `0x180076628`
- `0x180095b68`
- `0x1800b063c`
- `0x1800b7b08`
- `0x1801020b4`
- `0x18014da2c`
- `0x1801c7728`
- `0x1801cf234`
- `0x1801db144`
- `0x1801db1b0`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1801cf289`
- `api-ms-win-crt-private-l1-1-0!_o_wcstombs` at `0x1801cf289`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf5a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf48a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf536`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf5a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801cf697`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf4a8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf276`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf336`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1801cf4a8`

## string_xrefs

- `0x1801cf4e1`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801cf5f0`: `onecoreuap\enduser\winstore\installservice\libqueue2\uwainstallworkbridge.cpp`
- `0x1801cf4bd`: `Found update in applicability check.`
- `0x1801cf5cc`: `No update found in applicability check.`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
char __fastcall IsApplicableForUserFromBridge(
        HSTRING *a1,
        const struct winrt::hstring *a2,
        const struct winrt::hstring *a3)
{
  PCWSTR StringRawBuffer; // rax
  __int64 v7; // rbx
  unsigned int v8; // eax
  TokenHelpers *v9; // rcx
  HSTRING *LocalSystemSidString; // rax
  PCWSTR v11; // rax
  HSTRING *TokenForSid; // rax
  char v13; // bl
  unsigned int v14; // eax
  unsigned int i; // esi
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  unsigned int v18; // eax
  PCWSTR v19; // rax
  int v21; // edx
  int v22; // r9d
  HSTRING v23; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING string[2]; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h] BYREF
  Microsoft::WRL::Wrappers::HString *v26; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v29[4]; // [rsp+6Ch] [rbp-94h] BYREF
  __int64 v30; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v31[8]; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+80h] [rbp-80h] BYREF
  __int128 v33; // [rsp+88h] [rbp-78h]
  void **v34; // [rsp+98h] [rbp-68h] BYREF
  HSTRING v35; // [rsp+A0h] [rbp-60h]
  _QWORD v36[2]; // [rsp+A8h] [rbp-58h] BYREF
  int v37[8]; // [rsp+B8h] [rbp-48h] BYREF
  int v38[2]; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v39[144]; // [rsp+100h] [rbp+0h] BYREF

  LODWORD(v25) = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(*a1, 0);
  _o_wcstombs(v39, StringRawBuffer, 129);
  *(_QWORD *)v38 = *(_QWORD *)a3;
  v7 = winrt::Windows::Data::Json::JsonObject::Parse((const struct winrt::param::hstring *)string);
  winrt::param::hstring::hstring((winrt::param::hstring *)v37, L"WuCategoryId");
  winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(
    v7,
    v31,
    v37);
  winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(string);
  v23 = 0;
  LODWORD(v32) = 0;
  v33 = 0;
  string[0] = (HSTRING)winrt::hstring::c_str((winrt::hstring *)v31);
  v8 = Microsoft::WRL::Wrappers::HString::Set<unsigned short *>(&v23, string);
  winrt::check_hresult(v29, v8, &v32);
  std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(&v26);
  std::vector<Microsoft::WRL::Wrappers::HString>::push_back(&v26, &v23);
  LocalSystemSidString = (HSTRING *)TokenHelpers::GetLocalSystemSidString(v9);
  v11 = WindowsGetStringRawBuffer(*LocalSystemSidString, 0);
  if ( (unsigned __int8)winrt::operator==(a2, v11) )
  {
    string[0] = (HSTRING)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    string[1] = 0;
    TokenForSid = string;
    v13 = 1;
  }
  else
  {
    TokenForSid = (HSTRING *)TokenHelpers::GetTokenForSid(v36, *(_QWORD *)a2);
    v13 = 2;
  }
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  v35 = TokenForSid[1];
  TokenForSid[1] = 0;
  if ( (v13 & 2) != 0 )
  {
    v13 &= ~2u;
    v36[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v36);
  }
  if ( (v13 & 1) != 0 )
  {
    string[0] = (HSTRING)&Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(string);
  }
  ScanForUpdates((unsigned int)&v30, (_DWORD)v35, (unsigned int)&v26, 6, 0, (__int64)v39);
  if ( v30 )
  {
    v28 = 0;
    LODWORD(v32) = 0;
    v33 = 0;
    v14 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v30 + 80LL))(v30, &v28);
    winrt::check_hresult(v29, v14, &v32);
    for ( i = 0; (int)i < v28; ++i )
    {
      v25 = 0;
      LODWORD(v32) = 0;
      v33 = 0;
      v16 = v30;
      v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 56LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
      v18 = v17(v16, i, &v25);
      winrt::check_hresult(v29, v18, &v32);
      AppIdFromUpdateOrEmpty(string, v25);
      if ( string[0] )
      {
        v19 = WindowsGetStringRawBuffer(string[0], 0);
        v36[0] = L"CategoryId";
        v36[1] = v19;
        v32 = (__int64)L"Found update in applicability check.";
        *(_QWORD *)&v33 = 36;
        std::string::string(v38, "IsApplicableForUserFromBridge");
        std::string::string(v37, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp");
        Logging::Log<std::pair<unsigned short const *,unsigned short const *>>(
          (unsigned int)v37,
          1954,
          (unsigned int)v38,
          3,
          (__int64)&v32,
          (__int64)v36);
        std::string::~string(v37);
        std::string::~string(v38);
        WindowsDeleteString(string[0]);
        string[0] = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
        v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v34);
        if ( v26 )
        {
          std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v26);
          std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFF8uLL);
          v26 = 0;
          v27 = 0;
        }
        WindowsDeleteString(v23);
        v23 = 0;
        winrt::handle_type<winrt::impl::hstring_traits>::close(v31);
        return 1;
      }
      WindowsDeleteString(0);
      string[0] = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v25);
    }
  }
  else
  {
    winrt::hstring::hstring((winrt::hstring *)string, (const struct winrt::hstring *)a1);
    v32 = (__int64)L"No update found in applicability check.";
    *(_QWORD *)&v33 = 39;
    std::string::string(v37, "IsApplicableForUserFromBridge");
    std::string::string(v38, "onecoreuap\\enduser\\winstore\\installservice\\libqueue2\\uwainstallworkbridge.cpp");
    Logging::Log<Logging::CorrelationVectorAsString>(
      (int)v38,
      v21,
      (int)v37,
      v22,
      (__int64)&v32,
      (winrt::hstring *)string);
    std::string::~string(v38);
    std::string::~string(v37);
    winrt::handle_type<winrt::impl::hstring_traits>::close(string);
  }
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v30);
  v34 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(&v34);
  if ( v26 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(v26);
    std::_Deallocate<16>(v26, (*((_QWORD *)&v27 + 1) - (_QWORD)v26) & 0xFFFFFFFFFFFFFFF8uLL);
    v26 = 0;
    v27 = 0;
  }
  WindowsDeleteString(v23);
  v23 = 0;
  winrt::handle_type<winrt::impl::hstring_traits>::close(v31);
  return 0;
}

```

## disassembly

```asm
0x1801cf234  mov     [rsp-8+arg_10], rbx
0x1801cf239  push    rbp
0x1801cf23a  push    rsi
0x1801cf23b  push    rdi
0x1801cf23c  push    r14
0x1801cf23e  push    r15
0x1801cf240  lea     rbp, [rsp-0A0h]
0x1801cf248  sub     rsp, 1A0h
0x1801cf24f  mov     rax, cs:__security_cookie
0x1801cf256  xor     rax, rsp
0x1801cf259  mov     [rbp+0C0h+var_30], rax
0x1801cf260  mov     rbx, r8
0x1801cf263  mov     rdi, rdx
0x1801cf266  mov     rsi, rcx
0x1801cf269  xor     r14d, r14d
0x1801cf26c  mov     dword ptr [rsp+1C0h+var_178], r14d
0x1801cf271  xor     edx, edx; length
0x1801cf273  mov     rcx, [rcx]; string
0x1801cf276  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cf27c  mov     rdx, rax
0x1801cf27f  mov     r8d, 81h
0x1801cf285  lea     rcx, [rbp+0C0h+var_C0]
0x1801cf289  call    cs:__imp__o_wcstombs
0x1801cf28f  mov     rax, [rbx]
0x1801cf292  mov     qword ptr [rbp+0C0h+var_E8], rax
0x1801cf296  lea     rdx, [rbp+0C0h+var_E8]
0x1801cf29a  lea     rcx, [rsp+1C0h+string]; struct winrt::param::hstring *
0x1801cf29f  call    ?Parse@JsonObject@Json@Data@Windows@winrt@@SA@AEBUhstring@param@5@@Z; winrt::Windows::Data::Json::JsonObject::Parse(winrt::param::hstring const &)
0x1801cf2a4  mov     rbx, rax
0x1801cf2a7  lea     rdx, aWucategoryid_0; "WuCategoryId"
0x1801cf2ae  lea     rcx, [rbp+0C0h+var_108]; this
0x1801cf2b2  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1801cf2b7  lea     r8, [rbp+0C0h+var_108]
0x1801cf2bb  lea     rdx, [rsp+1C0h+var_148]
0x1801cf2c0  mov     rcx, rbx
0x1801cf2c3  call    ?GetNamedString@?$consume_Windows_Data_Json_IJsonObject@UIJsonObject@Json@Data@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@@Z; winrt::impl::consume_Windows_Data_Json_IJsonObject<winrt::Windows::Data::Json::IJsonObject>::GetNamedString(winrt::param::hstring const &)
0x1801cf2c8  nop
0x1801cf2c9  lea     rcx, [rsp+1C0h+string]; void *
0x1801cf2ce  call    ??1?$com_ptr@UIWeakReferenceSource@impl@winrt@@@winrt@@QEAA@XZ; winrt::com_ptr<winrt::impl::IWeakReferenceSource>::~com_ptr<winrt::impl::IWeakReferenceSource>(void)
0x1801cf2d3  mov     [rsp+1C0h+var_190], r14
0x1801cf2d8  mov     dword ptr [rbp+0C0h+var_140], r14d
0x1801cf2dc  xorps   xmm0, xmm0
0x1801cf2df  movdqu  [rbp+0C0h+var_138], xmm0
0x1801cf2e4  lea     rcx, [rsp+1C0h+var_148]; this
0x1801cf2e9  call    ?c_str@hstring@winrt@@QEBAPEBGXZ; winrt::hstring::c_str(void)
0x1801cf2ee  mov     [rsp+1C0h+string], rax
0x1801cf2f3  lea     rdx, [rsp+1C0h+string]
0x1801cf2f8  lea     rcx, [rsp+1C0h+var_190]
0x1801cf2fd  call    ??$Set@PEAG@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HString::Set<ushort *>(ushort * const &,Microsoft::WRL::Details::Dummy)
0x1801cf302  lea     r8, [rbp+0C0h+var_140]
0x1801cf306  mov     edx, eax
0x1801cf308  lea     rcx, [rsp+1C0h+var_154]
0x1801cf30d  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1801cf312  lea     rcx, [rsp+1C0h+var_170]; void *
0x1801cf317  call    ??0?$vector@USubTaskCheckpointData@ChainedInstallServiceWork@@V?$allocator@USubTaskCheckpointData@ChainedInstallServiceWork@@@std@@@std@@QEAA@XZ; std::vector<ChainedInstallServiceWork::SubTaskCheckpointData>::vector<ChainedInstallServiceWork::SubTaskCheckpointData>(void)
0x1801cf31c  nop
0x1801cf31d  lea     rdx, [rsp+1C0h+var_190]
0x1801cf322  lea     rcx, [rsp+1C0h+var_170]
0x1801cf327  call    ?push_back@?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@QEAAX$$QEAVHString@Wrappers@WRL@Microsoft@@@Z; std::vector<Microsoft::WRL::Wrappers::HString>::push_back(Microsoft::WRL::Wrappers::HString &&)
0x1801cf32c  call    ?GetLocalSystemSidString@TokenHelpers@@YAAEBVHString@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetLocalSystemSidString(void)
0x1801cf331  xor     edx, edx; length
0x1801cf333  mov     rcx, [rax]; string
0x1801cf336  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cf33c  mov     rdx, rax
0x1801cf33f  mov     rcx, rdi
0x1801cf342  call    ??8winrt@@YA_NAEBUhstring@0@PEBG@Z; winrt::operator==(winrt::hstring const &,ushort const *)
0x1801cf347  lea     r15, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1801cf34e  test    al, al
0x1801cf350  jz      short loc_1801CF367
0x1801cf352  mov     [rsp+1C0h+string], r15
0x1801cf357  mov     [rsp+1C0h+var_180], r14
0x1801cf35c  lea     rax, [rsp+1C0h+string]
0x1801cf361  lea     ebx, [r14+1]
0x1801cf365  jmp     short loc_1801CF378
0x1801cf367  mov     rdx, [rdi]
0x1801cf36a  lea     rcx, [rbp+0C0h+var_118]
0x1801cf36e  call    ?GetTokenForSid@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z; TokenHelpers::GetTokenForSid(HSTRING__ *)
0x1801cf373  mov     ebx, 2
0x1801cf378  mov     [rbp+0C0h+var_128], r15
0x1801cf37c  mov     rcx, [rax+8]
0x1801cf380  mov     [rbp+0C0h+var_120], rcx
0x1801cf384  mov     [rax+8], r14
0x1801cf388  test    bl, 2
0x1801cf38b  jz      short loc_1801CF39E
0x1801cf38d  and     ebx, 0FFFFFFFDh
0x1801cf390  mov     [rbp+0C0h+var_118], r15
0x1801cf394  lea     rcx, [rbp+0C0h+var_118]
0x1801cf398  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801cf39d  nop
0x1801cf39e  test    bl, 1
0x1801cf3a1  jz      short loc_1801CF3B2
0x1801cf3a3  mov     [rsp+1C0h+string], r15
0x1801cf3a8  lea     rcx, [rsp+1C0h+string]
0x1801cf3ad  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801cf3b2  lea     rax, [rbp+0C0h+var_C0]
0x1801cf3b6  mov     [rsp+1C0h+var_198], rax
0x1801cf3bb  mov     [rsp+1C0h+var_1A0], r14
0x1801cf3c0  mov     r9d, 6
0x1801cf3c6  lea     r8, [rsp+1C0h+var_170]
0x1801cf3cb  mov     rdx, [rbp+0C0h+var_120]
0x1801cf3cf  lea     rcx, [rsp+1C0h+var_150]
0x1801cf3d4  call    ?ScanForUpdates@@YA?AV?$ComPtr@UIUpdateCollection@@@WRL@Microsoft@@PEAXAEAV?$vector@VHString@Wrappers@WRL@Microsoft@@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@KPEAUHSTRING__@@PEBD@Z; ScanForUpdates(void *,std::vector<Microsoft::WRL::Wrappers::HString> &,ulong,HSTRING__ *,char const *)
0x1801cf3d9  nop
0x1801cf3da  mov     rcx, [rsp+1C0h+var_150]
0x1801cf3df  test    rcx, rcx
0x1801cf3e2  jz      loc_1801CF5BE
0x1801cf3e8  mov     [rsp+1C0h+var_158], r14d
0x1801cf3ed  mov     dword ptr [rbp+0C0h+var_140], r14d
0x1801cf3f1  xorps   xmm0, xmm0
0x1801cf3f4  movdqu  [rbp+0C0h+var_138], xmm0
0x1801cf3f9  mov     rax, [rcx]
0x1801cf3fc  lea     rdx, [rsp+1C0h+var_158]
0x1801cf401  mov     rax, [rax+50h]
0x1801cf405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf40a  lea     r8, [rbp+0C0h+var_140]
0x1801cf40e  mov     edx, eax
0x1801cf410  lea     rcx, [rsp+1C0h+var_154]
0x1801cf415  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1801cf41a  mov     esi, r14d
0x1801cf41d  cmp     esi, [rsp+1C0h+var_158]
0x1801cf421  jge     loc_1801CF641
0x1801cf427  mov     [rsp+1C0h+var_178], r14
0x1801cf42c  mov     dword ptr [rbp+0C0h+var_140], r14d
0x1801cf430  xorps   xmm0, xmm0
0x1801cf433  movdqu  [rbp+0C0h+var_138], xmm0
0x1801cf438  mov     rdi, [rsp+1C0h+var_150]
0x1801cf43d  mov     rax, [rdi]
0x1801cf440  mov     rbx, [rax+38h]
0x1801cf444  lea     rcx, [rsp+1C0h+var_178]
0x1801cf449  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801cf44e  lea     r8, [rsp+1C0h+var_178]
0x1801cf453  mov     edx, esi
0x1801cf455  mov     rcx, rdi
0x1801cf458  mov     rax, rbx
0x1801cf45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801cf460  lea     r8, [rbp+0C0h+var_140]
0x1801cf464  mov     edx, eax
0x1801cf466  lea     rcx, [rsp+1C0h+var_154]
0x1801cf46b  call    ?check_hresult@winrt@@YA?AUhresult@1@U21@AEBUslim_source_location@impl@1@@Z; winrt::check_hresult(winrt::hresult,winrt::impl::slim_source_location const &)
0x1801cf470  mov     rdx, [rsp+1C0h+var_178]
0x1801cf475  lea     rcx, [rsp+1C0h+string]
0x1801cf47a  call    ?AppIdFromUpdateOrEmpty@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUIUpdate@@@Z; AppIdFromUpdateOrEmpty(IUpdate *)
0x1801cf47f  nop
0x1801cf480  mov     rcx, [rsp+1C0h+string]; string
0x1801cf485  test    rcx, rcx
0x1801cf488  jnz     short loc_1801CF4A6
0x1801cf48a  call    cs:__imp_WindowsDeleteString
0x1801cf490  mov     [rsp+1C0h+string], r14
0x1801cf495  lea     rcx, [rsp+1C0h+var_178]
0x1801cf49a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801cf49f  inc     esi
0x1801cf4a1  jmp     loc_1801CF41D
0x1801cf4a6  xor     edx, edx; length
0x1801cf4a8  call    cs:__imp_WindowsGetStringRawBuffer
0x1801cf4ae  lea     rcx, aCategoryid; "CategoryId"
0x1801cf4b5  mov     [rbp+0C0h+var_118], rcx
0x1801cf4b9  mov     [rbp+0C0h+var_110], rax
0x1801cf4bd  lea     rax, aFoundUpdateInA; "Found update in applicability check."
0x1801cf4c4  mov     [rbp+0C0h+var_140], rax
0x1801cf4c8  mov     qword ptr [rbp+0C0h+var_138], 24h ; '$'
0x1801cf4d0  lea     rdx, aIsapplicablefo; "IsApplicableForUserFromBridge"
0x1801cf4d7  lea     rcx, [rbp+0C0h+var_E8]
0x1801cf4db  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801cf4e0  nop
0x1801cf4e1  lea     rdx, aOnecoreuapEndu_81; "onecoreuap\\enduser\\winstore\\installs"...
0x1801cf4e8  lea     rcx, [rbp+0C0h+var_108]
0x1801cf4ec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801cf4f1  nop
0x1801cf4f2  lea     rax, [rbp+0C0h+var_118]
0x1801cf4f6  mov     [rsp+1C0h+var_198], rax
0x1801cf4fb  lea     rax, [rbp+0C0h+var_140]
0x1801cf4ff  mov     [rsp+1C0h+var_1A0], rax
0x1801cf504  mov     r9d, 3
0x1801cf50a  lea     r8, [rbp+0C0h+var_E8]
0x1801cf50e  mov     edx, 7A2h
0x1801cf513  lea     rcx, [rbp+0C0h+var_108]
0x1801cf517  call    ??$Log@U?$pair@PEBGPEBG@std@@@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@$$QEAU?$pair@PEBGPEBG@2@@Z; Logging::Log<std::pair<ushort const *,ushort const *>>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &,std::pair<ushort const *,ushort const *> &&)
0x1801cf51c  nop
0x1801cf51d  lea     rcx, [rbp+0C0h+var_108]
0x1801cf521  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801cf526  nop
0x1801cf527  lea     rcx, [rbp+0C0h+var_E8]
0x1801cf52b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801cf530  nop
0x1801cf531  mov     rcx, [rsp+1C0h+string]; string
0x1801cf536  call    cs:__imp_WindowsDeleteString
0x1801cf53c  mov     [rsp+1C0h+string], r14
0x1801cf541  lea     rcx, [rsp+1C0h+var_178]
0x1801cf546  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801cf54b  nop
0x1801cf54c  lea     rcx, [rsp+1C0h+var_150]
0x1801cf551  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801cf556  nop
0x1801cf557  mov     [rbp+0C0h+var_128], r15
0x1801cf55b  lea     rcx, [rbp+0C0h+var_128]
0x1801cf55f  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801cf564  nop
0x1801cf565  mov     rcx, [rsp+1C0h+var_170]; this
0x1801cf56a  test    rcx, rcx
0x1801cf56d  jz      short loc_1801CF59D
0x1801cf56f  mov     rdx, qword ptr [rsp+1C0h+var_168]
0x1801cf574  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x1801cf579  mov     rcx, [rsp+1C0h+var_170]
0x1801cf57e  mov     rdx, qword ptr [rsp+1C0h+var_168+8]
0x1801cf583  sub     rdx, rcx
0x1801cf586  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1801cf58a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801cf58f  mov     [rsp+1C0h+var_170], r14
0x1801cf594  xorps   xmm0, xmm0
0x1801cf597  movdqu  [rsp+1C0h+var_168], xmm0
0x1801cf59d  mov     rcx, [rsp+1C0h+var_190]; string
0x1801cf5a2  call    cs:__imp_WindowsDeleteString
0x1801cf5a8  mov     [rsp+1C0h+var_190], r14
0x1801cf5ad  lea     rcx, [rsp+1C0h+var_148]
0x1801cf5b2  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801cf5b7  mov     al, 1
0x1801cf5b9  jmp     loc_1801CF6AE
0x1801cf5be  mov     rdx, rsi; struct winrt::hstring *
0x1801cf5c1  lea     rcx, [rsp+1C0h+string]; this
0x1801cf5c6  call    ??0hstring@winrt@@QEAA@AEBU01@@Z; winrt::hstring::hstring(winrt::hstring const &)
0x1801cf5cb  nop
0x1801cf5cc  lea     rax, aNoUpdateFoundI; "No update found in applicability check."
0x1801cf5d3  mov     [rbp+0C0h+var_140], rax
0x1801cf5d7  mov     qword ptr [rbp+0C0h+var_138], 27h ; '''
0x1801cf5df  lea     rdx, aIsapplicablefo; "IsApplicableForUserFromBridge"
0x1801cf5e6  lea     rcx, [rbp+0C0h+var_108]
0x1801cf5ea  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801cf5ef  nop
0x1801cf5f0  lea     rdx, aOnecoreuapEndu_81; "onecoreuap\\enduser\\winstore\\installs"...
0x1801cf5f7  lea     rcx, [rbp+0C0h+var_E8]
0x1801cf5fb  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1801cf600  nop
0x1801cf601  lea     rax, [rsp+1C0h+string]
0x1801cf606  mov     [rsp+1C0h+var_198], rax; winrt::hstring *
0x1801cf60b  lea     rax, [rbp+0C0h+var_140]
0x1801cf60f  mov     [rsp+1C0h+var_1A0], rax; __int64
0x1801cf614  lea     r8, [rbp+0C0h+var_108]; int
0x1801cf618  lea     rcx, [rbp+0C0h+var_E8]; int
0x1801cf61c  call    ??$Log@UCorrelationVectorAsString@Logging@@@Logging@@YAXAEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@I0W4Level@0@AEBV?$basic_string_view@GU?$char_traits@G@std@@@2@$$QEAUCorrelationVectorAsString@0@@Z; Logging::Log<Logging::CorrelationVectorAsString>(std::string const &,uint,std::string const &,Logging::Level,std::basic_string_view<ushort> const &,Logging::CorrelationVectorAsString &&)
0x1801cf621  nop
0x1801cf622  lea     rcx, [rbp+0C0h+var_E8]
0x1801cf626  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801cf62b  nop
0x1801cf62c  lea     rcx, [rbp+0C0h+var_108]
0x1801cf630  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1801cf635  nop
0x1801cf636  lea     rcx, [rsp+1C0h+string]
0x1801cf63b  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801cf640  nop
0x1801cf641  lea     rcx, [rsp+1C0h+var_150]
0x1801cf646  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1801cf64b  nop
0x1801cf64c  mov     [rbp+0C0h+var_128], r15
0x1801cf650  lea     rcx, [rbp+0C0h+var_128]
0x1801cf654  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x1801cf659  nop
0x1801cf65a  mov     rcx, [rsp+1C0h+var_170]; this
0x1801cf65f  test    rcx, rcx
0x1801cf662  jz      short loc_1801CF692
0x1801cf664  mov     rdx, qword ptr [rsp+1C0h+var_168]
0x1801cf669  call    ??$_Destroy_range@V?$allocator@VHString@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAVHString@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@VHString@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HString>>(Microsoft::WRL::Wrappers::HString *,Microsoft::WRL::Wrappers::HString * const,std::allocator<Microsoft::WRL::Wrappers::HString> &)
0x1801cf66e  mov     rcx, [rsp+1C0h+var_170]
0x1801cf673  mov     rdx, qword ptr [rsp+1C0h+var_168+8]
0x1801cf678  sub     rdx, rcx
0x1801cf67b  and     rdx, 0FFFFFFFFFFFFFFF8h
0x1801cf67f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x1801cf684  xorps   xmm0, xmm0
0x1801cf687  mov     [rsp+1C0h+var_170], r14
0x1801cf68c  movdqu  [rsp+1C0h+var_168], xmm0
0x1801cf692  mov     rcx, [rsp+1C0h+var_190]; string
0x1801cf697  call    cs:__imp_WindowsDeleteString
0x1801cf69d  mov     [rsp+1C0h+var_190], r14
0x1801cf6a2  lea     rcx, [rsp+1C0h+var_148]
0x1801cf6a7  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1801cf6ac  xor     al, al
0x1801cf6ae  mov     rcx, [rbp+0C0h+var_30]
0x1801cf6b5  xor     rcx, rsp; StackCookie
0x1801cf6b8  call    __security_check_cookie
0x1801cf6bd  mov     rbx, [rsp+1C0h+arg_10]
0x1801cf6c5  add     rsp, 1A0h
0x1801cf6cc  pop     r15
0x1801cf6ce  pop     r14
0x1801cf6d0  pop     rdi
0x1801cf6d1  pop     rsi
0x1801cf6d2  pop     rbp
0x1801cf6d3  retn
```
