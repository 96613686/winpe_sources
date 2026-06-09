# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(ushort const * const)

- ea: `0x1800a397c`
- end: `0x1800a3c4a`
- name: `?BackUpAndDeleteDMClientCspTrackingFiles@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG@Z`
- size: `718`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a5490`

## callees

- `0x18000b820`
- `0x18000b850`
- `0x18000c414`
- `0x180067a54`
- `0x18006c628`
- `0x18007755c`
- `0x18008019c`
- `0x18008122c`
- `0x1800839bc`
- `0x18008a0a8`
- `0x18008dc94`
- `0x18008f7d4`
- `0x1800a13a4`
- `0x1800a140c`
- `0x1800a397c`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a3b43`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a3b43`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a3bd0`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a3bd0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a39d0`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a39d0`

## string_xrefs

- `0x1800a39e6`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a3a9f`: `ExpectedMSIAppPackages`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(
        const unsigned __int16 *a1)
{
  int BasicProfileFolderPath; // eax
  unsigned int v3; // ebx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 i; // rdi
  __int64 v11; // rax
  const WCHAR *v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  const WCHAR *v16; // rbx
  const WCHAR *v17; // rax
  int v18[8]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[32]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[32]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v21[32]; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v22[32]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v23[32]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v24[32]; // [rsp+E0h] [rbp-20h] BYREF
  _OWORD v25[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v26[32]; // [rsp+120h] [rbp+20h] BYREF
  _BYTE v27[32]; // [rsp+140h] [rbp+40h] BYREF
  _BYTE v28[32]; // [rsp+160h] [rbp+60h] BYREF
  _BYTE v29[32]; // [rsp+180h] [rbp+80h] BYREF
  _BYTE v30[32]; // [rsp+1A0h] [rbp+A0h] BYREF
  _BYTE v31[528]; // [rsp+1C0h] [rbp+C0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3E8h] [rbp+2E8h]

  memset_0(v31, 0, 0x208u);
  BasicProfileFolderPath = GetBasicProfileFolderPath(4, 0, v31, 260);
  v3 = BasicProfileFolderPath;
  if ( BasicProfileFolderPath >= 0 )
  {
    std::wstring::wstring(v21, v31);
    v5 = std::wstring::append(v21, L"\\");
    v6 = std::wstring::append(v5, L"Microsoft\\DMClient");
    v7 = std::wstring::append(v6, L"\\");
    v8 = std::wstring::append(v7, a1);
    std::wstring::append(v8, L"\\");
    std::wstring::wstring(v19, v21);
    v9 = std::wstring::append(v19, L"FirstSync");
    std::wstring::append(v9, L"\\");
    std::wstring::wstring(v25, L"ExpectedPolicies");
    std::wstring::wstring(v26, L"ExpectedNetworkProfiles");
    std::wstring::wstring(v27, L"ExpectedMSIAppPackages");
    std::wstring::wstring(v28, L"ExpectedModernAppPackages");
    std::wstring::wstring(v29, L"ExpectedPFXCerts");
    std::wstring::wstring(v30, L"ExpectedSCEPCerts");
    std::wstring::wstring(v18);
    std::wstring::wstring(v20);
    for ( i = 0; i != 6; ++i )
    {
      v11 = std::operator+<unsigned short>(v22, v19, &v25[2 * i]);
      std::wstring::operator=(v18, v11);
      std::wstring::_Tidy_deallocate(v22);
      v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
      if ( PathFileExistsW(v12) )
      {
        v13 = std::wstring::wstring(v24, L"WhiteGlove_PreReseal_Backup_");
        v14 = std::operator+<unsigned short>(v23, v19, v13);
        v15 = std::operator+<unsigned short>(v22, v14, &v25[2 * i]);
        std::wstring::operator=(v20, v15);
        std::wstring::_Tidy_deallocate(v22);
        std::wstring::_Tidy_deallocate(v23);
        std::wstring::_Tidy_deallocate(v24);
        v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v20);
        v17 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v18);
        MoveFileExW(v17, v16, 1u);
      }
    }
    std::wstring::_Tidy_deallocate(v20);
    std::wstring::_Tidy_deallocate(v18);
    `eh vector destructor iterator'(
      v25,
      0x20u,
      6u,
      Microsoft::Windows::Autopilot::Diagnostics::GenericMappingUtilities<std::wstring,enum Microsoft::Windows::Autopilot::Diagnostics::JsonOutputBuilder::ApiScenario>::GenericMapping::~GenericMapping);
    std::wstring::_Tidy_deallocate(v19);
    std::wstring::_Tidy_deallocate(v21);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x3BA,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\service\\lib\\devicemanagementutilities.cpp",
      (const char *)(unsigned int)BasicProfileFolderPath,
      v18[0]);
    return v3;
  }
}

```

## disassembly

```asm
0x1800a397c  mov     [rsp-8+arg_8], rbx
0x1800a3981  mov     [rsp-8+arg_10], rdi
0x1800a3986  push    rbp
0x1800a3987  lea     rbp, [rsp-2E0h]
0x1800a398f  sub     rsp, 3E0h
0x1800a3996  mov     rax, cs:__security_cookie
0x1800a399d  xor     rax, rsp
0x1800a39a0  mov     [rbp+2E0h+var_10], rax
0x1800a39a7  mov     rdi, rcx
0x1800a39aa  xor     edx, edx; Val
0x1800a39ac  mov     r8d, 208h; Size
0x1800a39b2  lea     rcx, [rbp+2E0h+var_220]; void *
0x1800a39b9  call    memset_0
0x1800a39be  mov     r9d, 104h
0x1800a39c4  lea     r8, [rbp+2E0h+var_220]
0x1800a39cb  xor     edx, edx
0x1800a39cd  lea     ecx, [rdx+4]
0x1800a39d0  call    cs:__imp_GetBasicProfileFolderPath
0x1800a39d6  mov     ebx, eax
0x1800a39d8  test    eax, eax
0x1800a39da  jns     short loc_1800A39FE
0x1800a39dc  mov     rcx, [rbp+2E8h]; this
0x1800a39e3  mov     r9d, eax; char *
0x1800a39e6  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a39ed  mov     edx, 3BAh; void *
0x1800a39f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a39f7  mov     eax, ebx
0x1800a39f9  jmp     loc_1800A3C26
0x1800a39fe  lea     rdx, [rbp+2E0h+var_220]
0x1800a3a05  lea     rcx, [rbp+2E0h+var_360]
0x1800a3a09  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3a0e  nop
0x1800a3a0f  lea     rbx, SubBlock; "\\"
0x1800a3a16  mov     rdx, rbx
0x1800a3a19  lea     rcx, [rbp+2E0h+var_360]
0x1800a3a1d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a22  lea     rdx, aMicrosoftDmcli; "Microsoft\\DMClient"
0x1800a3a29  mov     rcx, rax
0x1800a3a2c  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a31  mov     rdx, rbx
0x1800a3a34  mov     rcx, rax
0x1800a3a37  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a3c  mov     rdx, rdi
0x1800a3a3f  mov     rcx, rax
0x1800a3a42  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a47  mov     rdx, rbx
0x1800a3a4a  mov     rcx, rax
0x1800a3a4d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a52  lea     rdx, [rbp+2E0h+var_360]
0x1800a3a56  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a3a5b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a3a60  nop
0x1800a3a61  lea     rdx, aFirstsync; "FirstSync"
0x1800a3a68  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a3a6d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a72  mov     rdx, rbx
0x1800a3a75  mov     rcx, rax
0x1800a3a78  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a3a7d  lea     rdx, aExpectedpolici; "ExpectedPolicies"
0x1800a3a84  lea     rcx, [rbp+2E0h+var_2E0]
0x1800a3a88  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3a8d  nop
0x1800a3a8e  lea     rdx, aExpectednetwor; "ExpectedNetworkProfiles"
0x1800a3a95  lea     rcx, [rbp+2E0h+var_2C0]
0x1800a3a99  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3a9e  nop
0x1800a3a9f  lea     rdx, aExpectedmsiapp; "ExpectedMSIAppPackages"
0x1800a3aa6  lea     rcx, [rbp+2E0h+var_2A0]
0x1800a3aaa  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3aaf  nop
0x1800a3ab0  lea     rdx, aExpectedmodern; "ExpectedModernAppPackages"
0x1800a3ab7  lea     rcx, [rbp+2E0h+var_280]
0x1800a3abb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3ac0  nop
0x1800a3ac1  lea     rdx, aExpectedpfxcer; "ExpectedPFXCerts"
0x1800a3ac8  lea     rcx, [rbp+2E0h+var_260]
0x1800a3acf  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3ad4  nop
0x1800a3ad5  lea     rdx, aExpectedscepce; "ExpectedSCEPCerts"
0x1800a3adc  lea     rcx, [rbp+2E0h+var_240]
0x1800a3ae3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3ae8  nop
0x1800a3ae9  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a3aee  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a3af3  nop
0x1800a3af4  lea     rcx, [rsp+3E0h+var_380]
0x1800a3af9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a3afe  nop
0x1800a3aff  xor     edi, edi
0x1800a3b01  mov     rax, rdi
0x1800a3b04  shl     rax, 5
0x1800a3b08  lea     rbx, [rbp+2E0h+var_2E0]
0x1800a3b0c  add     rbx, rax
0x1800a3b0f  mov     r8, rbx
0x1800a3b12  lea     rdx, [rsp+3E0h+var_3A0]
0x1800a3b17  lea     rcx, [rbp+2E0h+var_340]
0x1800a3b1b  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x1800a3b20  mov     rdx, rax
0x1800a3b23  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a3b28  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a3b2d  lea     rcx, [rbp+2E0h+var_340]
0x1800a3b31  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b36  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a3b3b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3b40  mov     rcx, rax; pszPath
0x1800a3b43  call    cs:__imp_PathFileExistsW
0x1800a3b49  test    eax, eax
0x1800a3b4b  jz      loc_1800A3BD6
0x1800a3b51  lea     rdx, aWhiteglovePrer_1; "WhiteGlove_PreReseal_Backup_"
0x1800a3b58  lea     rcx, [rbp+2E0h+var_300]
0x1800a3b5c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a3b61  nop
0x1800a3b62  mov     r8, rax
0x1800a3b65  lea     rdx, [rsp+3E0h+var_3A0]
0x1800a3b6a  lea     rcx, [rbp+2E0h+var_320]
0x1800a3b6e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800a3b73  nop
0x1800a3b74  mov     r8, rbx
0x1800a3b77  mov     rdx, rax
0x1800a3b7a  lea     rcx, [rbp+2E0h+var_340]
0x1800a3b7e  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800a3b83  mov     rdx, rax
0x1800a3b86  lea     rcx, [rsp+3E0h+var_380]
0x1800a3b8b  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a3b90  lea     rcx, [rbp+2E0h+var_340]
0x1800a3b94  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3b99  nop
0x1800a3b9a  lea     rcx, [rbp+2E0h+var_320]
0x1800a3b9e  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3ba3  nop
0x1800a3ba4  lea     rcx, [rbp+2E0h+var_300]
0x1800a3ba8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bad  lea     rcx, [rsp+3E0h+var_380]
0x1800a3bb2  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3bb7  mov     rbx, rax
0x1800a3bba  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a3bbf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a3bc4  mov     rcx, rax; lpExistingFileName
0x1800a3bc7  mov     r8d, 1; dwFlags
0x1800a3bcd  mov     rdx, rbx; lpNewFileName
0x1800a3bd0  call    cs:__imp_MoveFileExW
0x1800a3bd6  inc     rdi
0x1800a3bd9  cmp     rdi, 6
0x1800a3bdd  jnz     loc_1800A3B01
0x1800a3be3  lea     rcx, [rsp+3E0h+var_380]
0x1800a3be8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bed  nop
0x1800a3bee  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a3bf3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3bf8  nop
0x1800a3bf9  lea     r9, ??1GenericMapping@?$GenericMappingUtilities@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ApiScenario@JsonOutputBuilder@Diagnostics@Autopilot@Windows@Microsoft@@@Diagnostics@Autopilot@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x1800a3c00  lea     edx, [rdi+1Ah]; unsigned __int64
0x1800a3c03  mov     r8, rdi; unsigned __int64
0x1800a3c06  lea     rcx, [rbp+2E0h+var_2E0]; void *
0x1800a3c0a  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800a3c0f  nop
0x1800a3c10  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a3c15  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3c1a  nop
0x1800a3c1b  lea     rcx, [rbp+2E0h+var_360]
0x1800a3c1f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a3c24  xor     eax, eax
0x1800a3c26  mov     rcx, [rbp+2E0h+var_10]
0x1800a3c2d  xor     rcx, rsp; StackCookie
0x1800a3c30  call    __security_check_cookie
0x1800a3c35  lea     r11, [rsp+3E0h+var_s0]
0x1800a3c3d  mov     rbx, [r11+18h]
0x1800a3c41  mov     rdi, [r11+20h]
0x1800a3c45  mov     rsp, r11
0x1800a3c48  pop     rbp
0x1800a3c49  retn
```
