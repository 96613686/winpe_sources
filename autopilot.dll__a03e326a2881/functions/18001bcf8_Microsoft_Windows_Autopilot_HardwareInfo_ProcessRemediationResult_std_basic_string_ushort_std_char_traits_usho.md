# Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001bcf8`
- end: `0x18001c06b`
- name: `?ProcessRemediationResult@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `883`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800193e4`

## callees

- `0x1800045b0`
- `0x1800132d8`
- `0x180013a40`
- `0x180015ed0`
- `0x1800166dc`
- `0x1800174f0`
- `0x1800180a8`
- `0x18001b938`
- `0x18001bcf8`
- `0x18001c894`
- `0x18001eee0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bdb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001bdb1`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bfce`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001bfce`

## string_xrefs

- `0x18001bd4a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001bef4`: `ParseJSON`
- `0x18001bf09`: `ParseJSON`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(_QWORD *a1)
{
  int v1; // esi
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx
  __int64 v5; // rdi
  __int64 (__fastcall *v6)(__int64, _QWORD, HSTRING *); // rbx
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rcx
  unsigned int v10; // ebx
  PCWSTR StringRawBuffer; // rax
  __int64 v12; // r8
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, double *); // rbx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  int ContactTime; // eax
  __int64 v21; // rcx
  unsigned int v22; // ebx
  unsigned int v23; // eax
  int v24; // eax
  __int64 v25; // rcx
  unsigned int v26; // ebx
  int lpData; // [rsp+20h] [rbp-39h]
  unsigned int lpDataa; // [rsp+20h] [rbp-39h]
  int lpDatab; // [rsp+20h] [rbp-39h]
  __int64 Data; // [rsp+30h] [rbp-29h] BYREF
  HSTRING string; // [rsp+38h] [rbp-21h] BYREF
  double v33; // [rsp+40h] [rbp-19h] BYREF
  __int128 v34; // [rsp+48h] [rbp-11h] BYREF
  __m128i v35; // [rsp+58h] [rbp-1h]
  __int128 v36; // [rsp+68h] [rbp+Fh] BYREF
  __m128i si128; // [rsp+78h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  v36 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v36) = 0;
  v1 = 0;
  if ( !a1[2] )
    goto LABEL_23;
  Data = 0;
  v2 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(a1, &Data);
  v4 = v2;
  if ( v2 < 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        v3,
        AutopilotRestorationHardwareProcessRemediationFailure,
        (unsigned int)v2,
        L"ParseJSON");
    Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
      L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
      L"ParseJSON",
      v4);
    v18 = 739;
    goto LABEL_20;
  }
  string = 0;
  v5 = Data;
  v6 = *(__int64 (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)Data + 80LL);
  v7 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         &v34,
         &Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonNextContactTime);
  v8 = v6(v5, *(_QWORD *)(v7 + 24), &string);
  v10 = v8;
  if ( v8 < 0 )
  {
    if ( v8 != -2089484279 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(
          v9,
          AutopilotRestorationHardwareProcessRemediationFailure,
          (unsigned int)v8,
          L"GetNextContactTime");
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
        L"GetNextContactTime",
        v10);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2C9,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v10,
        lpData);
    }
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v34 = 0;
    v35 = 0;
    v12 = -1;
    do
      ++v12;
    while ( StringRawBuffer[v12] );
    std::wstring::_Construct<1,unsigned short const *>(&v34, StringRawBuffer, v12);
    std::wstring::_Tidy_deallocate(&v36);
    v36 = v34;
    si128 = v35;
    v35 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v34) = 0;
    std::wstring::_Tidy_deallocate(&v34);
  }
  v33 = 0.0;
  v13 = Data;
  v14 = *(__int64 (__fastcall **)(__int64, _QWORD, double *))(*(_QWORD *)Data + 88LL);
  v15 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          &v34,
          &Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter);
  v16 = v14(v13, *(_QWORD *)(v15 + 24), &v33);
  v4 = v16;
  if ( v16 >= 0 )
  {
    v1 = (int)v33;
    goto LABEL_21;
  }
  if ( v16 != -2089484279 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        v17,
        AutopilotRestorationHardwareProcessRemediationFailure,
        (unsigned int)v16,
        L"GetHardwareFilter");
    Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
      L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
      L"GetHardwareFilter",
      v4);
    v18 = 730;
LABEL_20:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v4,
      lpData);
  }
LABEL_21:
  v19 = Data;
  if ( Data )
  {
    Data = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  }
LABEL_23:
  ContactTime = Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime((__int64)&v36);
  v22 = ContactTime;
  if ( ContactTime < 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        v21,
        AutopilotRestorationHardwareProcessRemediationFailure,
        (unsigned int)ContactTime,
        L"StoreContactTime");
    Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
      L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
      L"StoreContactTime",
      v22);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x2EE,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v22,
      lpData);
  }
  LODWORD(Data) = v1;
  v23 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Provisioning\\HardwareInfo",
          L"HardwareIgnoreFilter",
          4u,
          &Data,
          4u);
  if ( v23 )
  {
    v24 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x328,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)v23,
            lpDataa);
    v26 = v24;
    if ( v24 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(
          v25,
          AutopilotRestorationHardwareProcessRemediationFailure,
          (unsigned int)v24,
          L"StoreHardwareFilter");
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
        L"StoreHardwareFilter",
        v26);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2F7,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v26,
        lpDatab);
    }
  }
  std::wstring::_Tidy_deallocate(&v36);
  return 0;
}

```

## disassembly

```asm
0x18001bcf8  mov     [rsp-8+arg_8], rbx
0x18001bcfd  mov     [rsp-8+arg_10], rsi
0x18001bd02  push    rbp
0x18001bd03  push    rdi
0x18001bd04  push    r12
0x18001bd06  push    r13
0x18001bd08  push    r14
0x18001bd0a  lea     rbp, [rsp-37h]
0x18001bd0f  sub     rsp, 90h
0x18001bd16  mov     rax, cs:__security_cookie
0x18001bd1d  xor     rax, rsp
0x18001bd20  mov     [rbp+57h+var_28], rax
0x18001bd24  xorps   xmm0, xmm0
0x18001bd27  movups  [rbp+57h+var_48], xmm0
0x18001bd2b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001bd33  movdqu  [rbp+57h+var_38], xmm1
0x18001bd38  xor     r14d, r14d
0x18001bd3b  mov     word ptr [rbp+57h+var_48], r14w
0x18001bd40  mov     esi, r14d
0x18001bd43  lea     r12, AutopilotRestorationHardwareProcessRemediationFailure
0x18001bd4a  lea     r13, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001bd51  cmp     [rcx+10h], r14
0x18001bd55  jz      loc_18001BF4B
0x18001bd5b  mov     [rbp+57h+Data], r14
0x18001bd5f  lea     rdx, [rbp+57h+Data]
0x18001bd63  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(std::wstring const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001bd68  mov     ebx, eax
0x18001bd6a  test    eax, eax
0x18001bd6c  js      loc_18001BEEB
0x18001bd72  mov     [rbp+57h+string], r14
0x18001bd76  mov     rdi, [rbp+57h+Data]
0x18001bd7a  mov     rax, [rdi]
0x18001bd7d  mov     rbx, [rax+50h]
0x18001bd81  lea     rdx, ?c_remediationResponseJsonNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonNextContactTime
0x18001bd88  lea     rcx, [rbp+57h+var_68]
0x18001bd8c  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001bd91  nop
0x18001bd92  lea     r8, [rbp+57h+string]
0x18001bd96  mov     rdx, [rax+18h]
0x18001bd9a  mov     rcx, rdi
0x18001bd9d  mov     rax, rbx
0x18001bda0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bda5  mov     ebx, eax
0x18001bda7  test    eax, eax
0x18001bda9  js      short loc_18001BE16
0x18001bdab  xor     edx, edx; length
0x18001bdad  mov     rcx, [rbp+57h+string]; string
0x18001bdb1  call    cs:__imp_WindowsGetStringRawBuffer
0x18001bdb7  xorps   xmm0, xmm0
0x18001bdba  movups  [rbp+57h+var_68], xmm0
0x18001bdbe  xorps   xmm1, xmm1
0x18001bdc1  movdqu  [rbp+57h+var_58], xmm1
0x18001bdc6  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001bdca  inc     r8
0x18001bdcd  cmp     [rax+r8*2], r14w
0x18001bdd2  jnz     short loc_18001BDCA
0x18001bdd4  mov     rdx, rax
0x18001bdd7  lea     rcx, [rbp+57h+var_68]
0x18001bddb  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001bde0  lea     rcx, [rbp+57h+var_48]
0x18001bde4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001bde9  movups  xmm0, [rbp+57h+var_68]
0x18001bded  movups  [rbp+57h+var_48], xmm0
0x18001bdf1  movups  xmm1, [rbp+57h+var_58]
0x18001bdf5  movups  [rbp+57h+var_38], xmm1
0x18001bdf9  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001be01  movdqu  [rbp+57h+var_58], xmm0
0x18001be06  mov     word ptr [rbp+57h+var_68], r14w
0x18001be0b  lea     rcx, [rbp+57h+var_68]
0x18001be0f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001be14  jmp     short loc_18001BE63
0x18001be16  cmp     ebx, 83750009h
0x18001be1c  jz      short loc_18001BE63
0x18001be1e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001be25  jz      short loc_18001BE39
0x18001be27  lea     r9, aGetnextcontact; "GetNextContactTime"
0x18001be2e  mov     r8d, ebx
0x18001be31  mov     rdx, r12
0x18001be34  call    McTemplateU0dz_EventWriteTransfer
0x18001be39  mov     r8d, ebx; int
0x18001be3c  lea     rdx, aGetnextcontact; "GetNextContactTime"
0x18001be43  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001be4a  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001be4f  mov     rcx, [rbp+5Fh]; this
0x18001be53  mov     r9d, ebx; char *
0x18001be56  mov     r8, r13; unsigned int
0x18001be59  mov     edx, 2C9h; void *
0x18001be5e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001be63  xorps   xmm0, xmm0
0x18001be66  movsd   [rbp+57h+var_70], xmm0
0x18001be6b  mov     rdi, [rbp+57h+Data]
0x18001be6f  mov     rax, [rdi]
0x18001be72  mov     rbx, [rax+58h]
0x18001be76  lea     rdx, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x18001be7d  lea     rcx, [rbp+57h+var_68]
0x18001be81  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001be86  nop
0x18001be87  lea     r8, [rbp+57h+var_70]
0x18001be8b  mov     rdx, [rax+18h]
0x18001be8f  mov     rcx, rdi
0x18001be92  mov     rax, rbx
0x18001be95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001be9a  mov     ebx, eax
0x18001be9c  test    eax, eax
0x18001be9e  js      short loc_18001BEAB
0x18001bea0  cvttsd2si rsi, [rbp+57h+var_70]
0x18001bea6  jmp     loc_18001BF31
0x18001beab  cmp     ebx, 83750009h
0x18001beb1  jz      short loc_18001BF31
0x18001beb3  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001beba  jz      short loc_18001BECE
0x18001bebc  lea     r9, aGethardwarefil; "GetHardwareFilter"
0x18001bec3  mov     r8d, ebx
0x18001bec6  mov     rdx, r12
0x18001bec9  call    McTemplateU0dz_EventWriteTransfer
0x18001bece  mov     r8d, ebx; int
0x18001bed1  lea     rdx, aGethardwarefil; "GetHardwareFilter"
0x18001bed8  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001bedf  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001bee4  mov     edx, 2DAh
0x18001bee9  jmp     short loc_18001BF21
0x18001beeb  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001bef2  jz      short loc_18001BF06
0x18001bef4  lea     r9, aParsejson; "ParseJSON"
0x18001befb  mov     r8d, ebx
0x18001befe  mov     rdx, r12
0x18001bf01  call    McTemplateU0dz_EventWriteTransfer
0x18001bf06  mov     r8d, ebx; int
0x18001bf09  lea     rdx, aParsejson; "ParseJSON"
0x18001bf10  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001bf17  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001bf1c  mov     edx, 2E3h; void *
0x18001bf21  mov     r9d, ebx; char *
0x18001bf24  mov     r8, r13; unsigned int
0x18001bf27  mov     rcx, [rbp+5Fh]; this
0x18001bf2b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001bf30  nop
0x18001bf31  mov     rcx, [rbp+57h+Data]
0x18001bf35  test    rcx, rcx
0x18001bf38  jz      short loc_18001BF4B
0x18001bf3a  mov     [rbp+57h+Data], r14
0x18001bf3e  mov     rax, [rcx]
0x18001bf41  mov     rax, [rax+10h]
0x18001bf45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001bf4a  nop
0x18001bf4b  lea     rcx, [rbp+57h+var_48]
0x18001bf4f  call    ?StoreNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(std::wstring const &)
0x18001bf54  mov     ebx, eax
0x18001bf56  test    eax, eax
0x18001bf58  jns     short loc_18001BF9F
0x18001bf5a  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001bf61  jz      short loc_18001BF75
0x18001bf63  lea     r9, aStorecontactti; "StoreContactTime"
0x18001bf6a  mov     r8d, eax
0x18001bf6d  mov     rdx, r12
0x18001bf70  call    McTemplateU0dz_EventWriteTransfer
0x18001bf75  mov     r8d, ebx; int
0x18001bf78  lea     rdx, aStorecontactti; "StoreContactTime"
0x18001bf7f  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001bf86  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001bf8b  mov     rcx, [rbp+5Fh]; this
0x18001bf8f  mov     r9d, ebx; char *
0x18001bf92  mov     r8, r13; unsigned int
0x18001bf95  mov     edx, 2EEh; void *
0x18001bf9a  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001bf9f  mov     dword ptr [rbp+57h+Data], esi
0x18001bfa2  mov     [rsp+0B0h+cbData], 4; cbData
0x18001bfaa  lea     rax, [rbp+57h+Data]
0x18001bfae  mov     [rsp+0B0h+lpData], rax; int
0x18001bfb3  mov     r9d, 4; dwType
0x18001bfb9  lea     r8, aHardwareignore; "HardwareIgnoreFilter"
0x18001bfc0  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001bfc7  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001bfce  call    cs:__imp_RegSetKeyValueW
0x18001bfd4  test    eax, eax
0x18001bfd6  jz      short loc_18001C038
0x18001bfd8  mov     rcx, [rbp+5Fh]; this
0x18001bfdc  mov     r9d, eax; char *
0x18001bfdf  mov     r8, r13; unsigned int
0x18001bfe2  mov     edx, 328h; void *
0x18001bfe7  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001bfec  mov     ebx, eax
0x18001bfee  test    eax, eax
0x18001bff0  jns     short loc_18001C038
0x18001bff2  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001bff9  jz      short loc_18001C00D
0x18001bffb  lea     r9, aStorehardwaref; "StoreHardwareFilter"
0x18001c002  mov     r8d, eax
0x18001c005  mov     rdx, r12
0x18001c008  call    McTemplateU0dz_EventWriteTransfer
0x18001c00d  mov     r8d, ebx; int
0x18001c010  lea     rdx, aStorehardwaref; "StoreHardwareFilter"
0x18001c017  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c01e  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c023  mov     rcx, [rbp+5Fh]; this
0x18001c027  mov     r9d, ebx; char *
0x18001c02a  mov     r8, r13; unsigned int
0x18001c02d  mov     edx, 2F7h; void *
0x18001c032  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c037  nop
0x18001c038  lea     rcx, [rbp+57h+var_48]
0x18001c03c  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c041  xor     eax, eax
0x18001c043  mov     rcx, [rbp+57h+var_28]
0x18001c047  xor     rcx, rsp; StackCookie
0x18001c04a  call    __security_check_cookie
0x18001c04f  lea     r11, [rsp+0B0h+var_20]
0x18001c057  mov     rbx, [r11+38h]
0x18001c05b  mov     rsi, [r11+40h]
0x18001c05f  mov     rsp, r11
0x18001c062  pop     r14
0x18001c064  pop     r13
0x18001c066  pop     r12
0x18001c068  pop     rdi
0x18001c069  pop     rbp
0x18001c06a  retn
```
