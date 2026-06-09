# Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18001c448`
- end: `0x18001c7c8`
- name: `?ProcessRemediationResult@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `896`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800199e4`

## callees

- `0x1800045d0`
- `0x180013580`
- `0x180013de4`
- `0x180016350`
- `0x180016b80`
- `0x180017a20`
- `0x1800185f8`
- `0x18001c070`
- `0x18001c448`
- `0x18001cff4`
- `0x18001f774`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c501`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001c501`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c724`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18001c724`

## string_xrefs

- `0x18001c49a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\hardwareinfo.cpp`
- `0x18001c64a`: `ParseJSON`
- `0x18001c65f`: `ParseJSON`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult(__int64 a1)
{
  int v1; // esi
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // r8d
  unsigned int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, PVOID, HSTRING *); // rbx
  HSTRING_HEADER *v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  unsigned int v11; // r8d
  unsigned int v12; // ebx
  PCWSTR StringRawBuffer; // rax
  unsigned __int64 v14; // r8
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, PVOID, double *); // rbx
  HSTRING_HEADER *v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  __int64 v20; // rdx
  __int64 v21; // rcx
  int v22; // eax
  __int64 v23; // rcx
  unsigned int v24; // ebx
  unsigned int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  unsigned int v28; // ebx
  unsigned int lpData; // [rsp+20h] [rbp-39h]
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
  if ( !*(_QWORD *)(a1 + 16) )
    goto LABEL_23;
  Data = 0;
  v2 = Microsoft::Windows::Autopilot::JsonHelpers::FromString((const WCHAR *)a1, &Data);
  v5 = v2;
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
      v5);
    v20 = 739;
    goto LABEL_20;
  }
  string = 0;
  v6 = Data;
  v7 = *(__int64 (__fastcall **)(__int64, PVOID, HSTRING *))(*(_QWORD *)Data + 80LL);
  v8 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
         (HSTRING_HEADER *)&v34,
         (const WCHAR **)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonNextContactTime,
         v4);
  v9 = v7(v6, v8[1].Reserved.Reserved1, &string);
  v12 = v9;
  if ( v9 < 0 )
  {
    if ( v9 != -2089484279 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(
          v10,
          AutopilotRestorationHardwareProcessRemediationFailure,
          (unsigned int)v9,
          L"GetNextContactTime");
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
        L"GetNextContactTime",
        v12);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2C9,
        (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v12);
    }
  }
  else
  {
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    v34 = 0;
    v35 = 0;
    v14 = -1;
    do
      ++v14;
    while ( StringRawBuffer[v14] );
    std::wstring::_Construct<1,unsigned short const *>(&v34, StringRawBuffer, v14);
    std::wstring::_Tidy_deallocate((char **)&v36);
    v36 = v34;
    si128 = v35;
    v35 = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v34) = 0;
    std::wstring::_Tidy_deallocate((char **)&v34);
  }
  v33 = 0.0;
  v15 = Data;
  v16 = *(__int64 (__fastcall **)(__int64, PVOID, double *))(*(_QWORD *)Data + 88LL);
  v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(
          (HSTRING_HEADER *)&v34,
          (const WCHAR **)&Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter,
          v11);
  v18 = v16(v15, v17[1].Reserved.Reserved1, &v33);
  v5 = v18;
  if ( v18 >= 0 )
  {
    v1 = (int)v33;
    goto LABEL_21;
  }
  if ( v18 != -2089484279 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        v19,
        AutopilotRestorationHardwareProcessRemediationFailure,
        (unsigned int)v18,
        L"GetHardwareFilter");
    Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
      L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
      L"GetHardwareFilter",
      v5);
    v20 = 730;
LABEL_20:
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)v20,
      (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v5);
  }
LABEL_21:
  v21 = Data;
  if ( Data )
  {
    Data = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
LABEL_23:
  v22 = Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(&v36);
  v24 = v22;
  if ( v22 < 0 )
  {
    if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
      McTemplateU0dz_EventWriteTransfer(
        v23,
        AutopilotRestorationHardwareProcessRemediationFailure,
        (unsigned int)v22,
        L"StoreContactTime");
    Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
      L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
      L"StoreContactTime",
      v24);
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x2EE,
      (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
      (const char *)v24);
  }
  LODWORD(Data) = v1;
  v25 = RegSetKeyValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Provisioning\\HardwareInfo",
          L"HardwareIgnoreFilter",
          4u,
          &Data,
          4u);
  if ( v25 )
  {
    v26 = wil::details::in1diag3::Return_Win32(
            retaddr,
            (void *)0x328,
            (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
            (const char *)v25,
            lpData);
    v28 = v26;
    if ( v26 < 0 )
    {
      if ( (Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits & 4) != 0 )
        McTemplateU0dz_EventWriteTransfer(
          v27,
          AutopilotRestorationHardwareProcessRemediationFailure,
          (unsigned int)v26,
          L"StoreHardwareFilter");
      Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(
        L"Microsoft::Windows::Autopilot::HardwareInfo::ProcessRemediationResult",
        L"StoreHardwareFilter",
        v28);
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2F7,
        (__int64)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\hardwareinfo.cpp",
        (const char *)v28);
    }
  }
  std::wstring::_Tidy_deallocate((char **)&v36);
  return 0;
}

```

## disassembly

```asm
0x18001c448  mov     [rsp-8+arg_8], rbx
0x18001c44d  mov     [rsp-8+arg_10], rsi
0x18001c452  push    rbp
0x18001c453  push    rdi
0x18001c454  push    r12
0x18001c456  push    r13
0x18001c458  push    r14
0x18001c45a  lea     rbp, [rsp-37h]
0x18001c45f  sub     rsp, 90h
0x18001c466  mov     rax, cs:__security_cookie
0x18001c46d  xor     rax, rsp
0x18001c470  mov     [rbp+57h+var_28], rax
0x18001c474  xorps   xmm0, xmm0
0x18001c477  movups  [rbp+57h+var_48], xmm0
0x18001c47b  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001c483  movdqu  [rbp+57h+var_38], xmm1
0x18001c488  xor     r14d, r14d
0x18001c48b  mov     word ptr [rbp+57h+var_48], r14w
0x18001c490  mov     esi, r14d
0x18001c493  lea     r12, AutopilotRestorationHardwareProcessRemediationFailure
0x18001c49a  lea     r13, aOnecoreuapAdmi_12; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001c4a1  cmp     [rcx+10h], r14
0x18001c4a5  jz      loc_18001C6A1
0x18001c4ab  mov     [rbp+57h+Data], r14
0x18001c4af  lea     rdx, [rbp+57h+Data]
0x18001c4b3  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(std::wstring const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x18001c4b8  mov     ebx, eax
0x18001c4ba  test    eax, eax
0x18001c4bc  js      loc_18001C641
0x18001c4c2  mov     [rbp+57h+string], r14
0x18001c4c6  mov     rdi, [rbp+57h+Data]
0x18001c4ca  mov     rax, [rdi]
0x18001c4cd  mov     rbx, [rax+50h]
0x18001c4d1  lea     rdx, ?c_remediationResponseJsonNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonNextContactTime
0x18001c4d8  lea     rcx, [rbp+57h+var_68]
0x18001c4dc  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c4e1  nop
0x18001c4e2  lea     r8, [rbp+57h+string]
0x18001c4e6  mov     rdx, [rax+18h]
0x18001c4ea  mov     rcx, rdi
0x18001c4ed  mov     rax, rbx
0x18001c4f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c4f5  mov     ebx, eax
0x18001c4f7  test    eax, eax
0x18001c4f9  js      short loc_18001C56C
0x18001c4fb  xor     edx, edx; length
0x18001c4fd  mov     rcx, [rbp+57h+string]; string
0x18001c501  call    cs:__imp_WindowsGetStringRawBuffer
0x18001c508  nop     dword ptr [rax+rax+00h]
0x18001c50d  xorps   xmm0, xmm0
0x18001c510  movups  [rbp+57h+var_68], xmm0
0x18001c514  xorps   xmm1, xmm1
0x18001c517  movdqu  [rbp+57h+var_58], xmm1
0x18001c51c  or      r8, 0FFFFFFFFFFFFFFFFh
0x18001c520  inc     r8
0x18001c523  cmp     [rax+r8*2], r14w
0x18001c528  jnz     short loc_18001C520
0x18001c52a  mov     rdx, rax
0x18001c52d  lea     rcx, [rbp+57h+var_68]
0x18001c531  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18001c536  lea     rcx, [rbp+57h+var_48]
0x18001c53a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c53f  movups  xmm0, [rbp+57h+var_68]
0x18001c543  movups  [rbp+57h+var_48], xmm0
0x18001c547  movups  xmm1, [rbp+57h+var_58]
0x18001c54b  movups  [rbp+57h+var_38], xmm1
0x18001c54f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x18001c557  movdqu  [rbp+57h+var_58], xmm0
0x18001c55c  mov     word ptr [rbp+57h+var_68], r14w
0x18001c561  lea     rcx, [rbp+57h+var_68]
0x18001c565  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c56a  jmp     short loc_18001C5B9
0x18001c56c  cmp     ebx, 83750009h
0x18001c572  jz      short loc_18001C5B9
0x18001c574  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c57b  jz      short loc_18001C58F
0x18001c57d  lea     r9, aGetnextcontact; "GetNextContactTime"
0x18001c584  mov     r8d, ebx
0x18001c587  mov     rdx, r12
0x18001c58a  call    McTemplateU0dz_EventWriteTransfer
0x18001c58f  mov     r8d, ebx; int
0x18001c592  lea     rdx, aGetnextcontact; "GetNextContactTime"
0x18001c599  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c5a0  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c5a5  mov     rcx, [rbp+5Fh]; this
0x18001c5a9  mov     r9d, ebx; char *
0x18001c5ac  mov     r8, r13; unsigned int
0x18001c5af  mov     edx, 2C9h; void *
0x18001c5b4  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c5b9  xorps   xmm0, xmm0
0x18001c5bc  movsd   [rbp+57h+var_70], xmm0
0x18001c5c1  mov     rdi, [rbp+57h+Data]
0x18001c5c5  mov     rax, [rdi]
0x18001c5c8  mov     rbx, [rax+58h]
0x18001c5cc  lea     rdx, ?c_remediationResponseJsonHardwareFilter@HardwareInfo@Autopilot@Windows@Microsoft@@2QEBGEB; ushort const * const Microsoft::Windows::Autopilot::HardwareInfo::c_remediationResponseJsonHardwareFilter
0x18001c5d3  lea     rcx, [rbp+57h+var_68]
0x18001c5d7  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18001c5dc  nop
0x18001c5dd  lea     r8, [rbp+57h+var_70]
0x18001c5e1  mov     rdx, [rax+18h]
0x18001c5e5  mov     rcx, rdi
0x18001c5e8  mov     rax, rbx
0x18001c5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5f0  mov     ebx, eax
0x18001c5f2  test    eax, eax
0x18001c5f4  js      short loc_18001C601
0x18001c5f6  cvttsd2si rsi, [rbp+57h+var_70]
0x18001c5fc  jmp     loc_18001C687
0x18001c601  cmp     ebx, 83750009h
0x18001c607  jz      short loc_18001C687
0x18001c609  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c610  jz      short loc_18001C624
0x18001c612  lea     r9, aGethardwarefil; "GetHardwareFilter"
0x18001c619  mov     r8d, ebx
0x18001c61c  mov     rdx, r12
0x18001c61f  call    McTemplateU0dz_EventWriteTransfer
0x18001c624  mov     r8d, ebx; int
0x18001c627  lea     rdx, aGethardwarefil; "GetHardwareFilter"
0x18001c62e  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c635  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c63a  mov     edx, 2DAh
0x18001c63f  jmp     short loc_18001C677
0x18001c641  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c648  jz      short loc_18001C65C
0x18001c64a  lea     r9, aParsejson; "ParseJSON"
0x18001c651  mov     r8d, ebx
0x18001c654  mov     rdx, r12
0x18001c657  call    McTemplateU0dz_EventWriteTransfer
0x18001c65c  mov     r8d, ebx; int
0x18001c65f  lea     rdx, aParsejson; "ParseJSON"
0x18001c666  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c66d  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c672  mov     edx, 2E3h; void *
0x18001c677  mov     r9d, ebx; char *
0x18001c67a  mov     r8, r13; unsigned int
0x18001c67d  mov     rcx, [rbp+5Fh]; this
0x18001c681  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c686  nop
0x18001c687  mov     rcx, [rbp+57h+Data]
0x18001c68b  test    rcx, rcx
0x18001c68e  jz      short loc_18001C6A1
0x18001c690  mov     [rbp+57h+Data], r14
0x18001c694  mov     rax, [rcx]
0x18001c697  mov     rax, [rax+10h]
0x18001c69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c6a0  nop
0x18001c6a1  lea     rcx, [rbp+57h+var_48]
0x18001c6a5  call    ?StoreNextContactTime@HardwareInfo@Autopilot@Windows@Microsoft@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; Microsoft::Windows::Autopilot::HardwareInfo::StoreNextContactTime(std::wstring const &)
0x18001c6aa  mov     ebx, eax
0x18001c6ac  test    eax, eax
0x18001c6ae  jns     short loc_18001C6F5
0x18001c6b0  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c6b7  jz      short loc_18001C6CB
0x18001c6b9  lea     r9, aStorecontactti; "StoreContactTime"
0x18001c6c0  mov     r8d, eax
0x18001c6c3  mov     rdx, r12
0x18001c6c6  call    McTemplateU0dz_EventWriteTransfer
0x18001c6cb  mov     r8d, ebx; int
0x18001c6ce  lea     rdx, aStorecontactti; "StoreContactTime"
0x18001c6d5  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c6dc  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c6e1  mov     rcx, [rbp+5Fh]; this
0x18001c6e5  mov     r9d, ebx; char *
0x18001c6e8  mov     r8, r13; unsigned int
0x18001c6eb  mov     edx, 2EEh; void *
0x18001c6f0  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c6f5  mov     dword ptr [rbp+57h+Data], esi
0x18001c6f8  mov     [rsp+0B0h+cbData], 4; cbData
0x18001c700  lea     rax, [rbp+57h+Data]
0x18001c704  mov     [rsp+0B0h+lpData], rax; int
0x18001c709  mov     r9d, 4; dwType
0x18001c70f  lea     r8, aHardwareignore; "HardwareIgnoreFilter"
0x18001c716  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Provisioning\\Hard"...
0x18001c71d  mov     rcx, 0FFFFFFFF80000002h; hKey
0x18001c724  call    cs:__imp_RegSetKeyValueW
0x18001c72b  nop     dword ptr [rax+rax+00h]
0x18001c730  test    eax, eax
0x18001c732  jz      short loc_18001C794
0x18001c734  mov     rcx, [rbp+5Fh]; this
0x18001c738  mov     r9d, eax; char *
0x18001c73b  mov     r8, r13; unsigned int
0x18001c73e  mov     edx, 328h; void *
0x18001c743  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18001c748  mov     ebx, eax
0x18001c74a  test    eax, eax
0x18001c74c  jns     short loc_18001C794
0x18001c74e  test    byte ptr cs:Microsoft_Windows_ModernDeployment_Diagnostics_ProviderEnableBits, 4
0x18001c755  jz      short loc_18001C769
0x18001c757  lea     r9, aStorehardwaref; "StoreHardwareFilter"
0x18001c75e  mov     r8d, eax
0x18001c761  mov     rdx, r12
0x18001c764  call    McTemplateU0dz_EventWriteTransfer
0x18001c769  mov     r8d, ebx; int
0x18001c76c  lea     rdx, aStorehardwaref; "StoreHardwareFilter"
0x18001c773  lea     rcx, aMicrosoftWindo_2; "Microsoft::Windows::Autopilot::Hardware"...
0x18001c77a  call    ?LogAutopilotTelemetryEvent@HardwareInfo@Autopilot@Windows@Microsoft@@CAXPEBG0J@Z; Microsoft::Windows::Autopilot::HardwareInfo::LogAutopilotTelemetryEvent(ushort const *,ushort const *,long)
0x18001c77f  mov     rcx, [rbp+5Fh]; this
0x18001c783  mov     r9d, ebx; char *
0x18001c786  mov     r8, r13; unsigned int
0x18001c789  mov     edx, 2F7h; void *
0x18001c78e  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18001c793  nop
0x18001c794  lea     rcx, [rbp+57h+var_48]
0x18001c798  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001c79d  xor     eax, eax
0x18001c79f  mov     rcx, [rbp+57h+var_28]
0x18001c7a3  xor     rcx, rsp; StackCookie
0x18001c7a6  call    __security_check_cookie
0x18001c7ab  lea     r11, [rsp+0B0h+var_20]
0x18001c7b3  mov     rbx, [r11+38h]
0x18001c7b7  mov     rsi, [r11+40h]
0x18001c7bb  mov     rsp, r11
0x18001c7be  pop     r14
0x18001c7c0  pop     r13
0x18001c7c2  pop     r12
0x18001c7c4  pop     rdi
0x18001c7c5  pop     rbp
0x18001c7c6  retn
```
