# ModernDeployment::Autopilot::Core::DeviceManagementUtilities::BackUpAndDeleteDMClientCspTrackingFiles(ushort const * const)

- ea: `0x1800a4fcc`
- end: `0x1800a52ad`
- name: `?BackUpAndDeleteDMClientCspTrackingFiles@DeviceManagementUtilities@Core@Autopilot@ModernDeployment@@CAJQEBG@Z`
- size: `737`
- prototype: `__int64 __fastcall(const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800a6b70`

## callees

- `0x18000b8f0`
- `0x18000b920`
- `0x18000c504`
- `0x180067e54`
- `0x18006cb28`
- `0x180077de0`
- `0x180080bac`
- `0x180081cac`
- `0x180084574`
- `0x18008af70`
- `0x18008ed78`
- `0x180090944`
- `0x1800a29ac`
- `0x1800a2a14`
- `0x1800a4fcc`

## import_xrefs

- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5199`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x1800a5199`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a522c`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x1800a522c`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a5020`
- `profapi!__imp_GetBasicProfileFolderPath` at `0x1800a5020`

## string_xrefs

- `0x1800a503c`: `onecoreuap\admin\moderndeployment\autopilot\service\lib\devicemanagementutilities.cpp`
- `0x1800a50f5`: `ExpectedMSIAppPackages`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
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
0x1800a4fcc  mov     [rsp-8+arg_8], rbx
0x1800a4fd1  mov     [rsp-8+arg_10], rdi
0x1800a4fd6  push    rbp
0x1800a4fd7  lea     rbp, [rsp-2E0h]
0x1800a4fdf  sub     rsp, 3E0h
0x1800a4fe6  mov     rax, cs:__security_cookie
0x1800a4fed  xor     rax, rsp
0x1800a4ff0  mov     [rbp+2E0h+var_10], rax
0x1800a4ff7  mov     rdi, rcx
0x1800a4ffa  xor     edx, edx; Val
0x1800a4ffc  mov     r8d, 208h; Size
0x1800a5002  lea     rcx, [rbp+2E0h+var_220]; void *
0x1800a5009  call    memset_0
0x1800a500e  mov     r9d, 104h
0x1800a5014  lea     r8, [rbp+2E0h+var_220]
0x1800a501b  xor     edx, edx
0x1800a501d  lea     ecx, [rdx+4]
0x1800a5020  call    cs:__imp_GetBasicProfileFolderPath
0x1800a5027  nop     dword ptr [rax+rax+00h]
0x1800a502c  mov     ebx, eax
0x1800a502e  test    eax, eax
0x1800a5030  jns     short loc_1800A5054
0x1800a5032  mov     rcx, [rbp+2E8h]; this
0x1800a5039  mov     r9d, eax; char *
0x1800a503c  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800a5043  mov     edx, 3BAh; void *
0x1800a5048  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a504d  mov     eax, ebx
0x1800a504f  jmp     loc_1800A5288
0x1800a5054  lea     rdx, [rbp+2E0h+var_220]
0x1800a505b  lea     rcx, [rbp+2E0h+var_360]
0x1800a505f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a5064  nop
0x1800a5065  lea     rbx, SubBlock; "\\"
0x1800a506c  mov     rdx, rbx
0x1800a506f  lea     rcx, [rbp+2E0h+var_360]
0x1800a5073  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a5078  lea     rdx, aMicrosoftDmcli; "Microsoft\\DMClient"
0x1800a507f  mov     rcx, rax
0x1800a5082  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a5087  mov     rdx, rbx
0x1800a508a  mov     rcx, rax
0x1800a508d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a5092  mov     rdx, rdi
0x1800a5095  mov     rcx, rax
0x1800a5098  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a509d  mov     rdx, rbx
0x1800a50a0  mov     rcx, rax
0x1800a50a3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a50a8  lea     rdx, [rbp+2E0h+var_360]
0x1800a50ac  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a50b1  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800a50b6  nop
0x1800a50b7  lea     rdx, aFirstsync; "FirstSync"
0x1800a50be  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a50c3  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a50c8  mov     rdx, rbx
0x1800a50cb  mov     rcx, rax
0x1800a50ce  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x1800a50d3  lea     rdx, aExpectedpolici; "ExpectedPolicies"
0x1800a50da  lea     rcx, [rbp+2E0h+var_2E0]
0x1800a50de  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a50e3  nop
0x1800a50e4  lea     rdx, aExpectednetwor; "ExpectedNetworkProfiles"
0x1800a50eb  lea     rcx, [rbp+2E0h+var_2C0]
0x1800a50ef  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a50f4  nop
0x1800a50f5  lea     rdx, aExpectedmsiapp; "ExpectedMSIAppPackages"
0x1800a50fc  lea     rcx, [rbp+2E0h+var_2A0]
0x1800a5100  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a5105  nop
0x1800a5106  lea     rdx, aExpectedmodern; "ExpectedModernAppPackages"
0x1800a510d  lea     rcx, [rbp+2E0h+var_280]
0x1800a5111  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a5116  nop
0x1800a5117  lea     rdx, aExpectedpfxcer; "ExpectedPFXCerts"
0x1800a511e  lea     rcx, [rbp+2E0h+var_260]
0x1800a5125  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a512a  nop
0x1800a512b  lea     rdx, aExpectedscepce; "ExpectedSCEPCerts"
0x1800a5132  lea     rcx, [rbp+2E0h+var_240]
0x1800a5139  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a513e  nop
0x1800a513f  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a5144  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5149  nop
0x1800a514a  lea     rcx, [rsp+3E0h+var_380]
0x1800a514f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x1800a5154  nop
0x1800a5155  xor     edi, edi
0x1800a5157  mov     rax, rdi
0x1800a515a  shl     rax, 5
0x1800a515e  lea     rbx, [rbp+2E0h+var_2E0]
0x1800a5162  add     rbx, rax
0x1800a5165  mov     r8, rbx
0x1800a5168  lea     rdx, [rsp+3E0h+var_3A0]
0x1800a516d  lea     rcx, [rbp+2E0h+var_340]
0x1800a5171  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@0@Z; std::operator+<ushort>(std::wstring const &,std::wstring const &)
0x1800a5176  mov     rdx, rax
0x1800a5179  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a517e  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a5183  lea     rcx, [rbp+2E0h+var_340]
0x1800a5187  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a518c  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a5191  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5196  mov     rcx, rax; pszPath
0x1800a5199  call    cs:__imp_PathFileExistsW
0x1800a51a0  nop     dword ptr [rax+rax+00h]
0x1800a51a5  test    eax, eax
0x1800a51a7  jz      loc_1800A5238
0x1800a51ad  lea     rdx, aWhiteglovePrer_1; "WhiteGlove_PreReseal_Backup_"
0x1800a51b4  lea     rcx, [rbp+2E0h+var_300]
0x1800a51b8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800a51bd  nop
0x1800a51be  mov     r8, rax
0x1800a51c1  lea     rdx, [rsp+3E0h+var_3A0]
0x1800a51c6  lea     rcx, [rbp+2E0h+var_320]
0x1800a51ca  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x1800a51cf  nop
0x1800a51d0  mov     r8, rbx
0x1800a51d3  mov     rdx, rax
0x1800a51d6  lea     rcx, [rbp+2E0h+var_340]
0x1800a51da  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x1800a51df  mov     rdx, rax
0x1800a51e2  lea     rcx, [rsp+3E0h+var_380]
0x1800a51e7  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800a51ec  lea     rcx, [rbp+2E0h+var_340]
0x1800a51f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a51f5  nop
0x1800a51f6  lea     rcx, [rbp+2E0h+var_320]
0x1800a51fa  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a51ff  nop
0x1800a5200  lea     rcx, [rbp+2E0h+var_300]
0x1800a5204  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5209  lea     rcx, [rsp+3E0h+var_380]
0x1800a520e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5213  mov     rbx, rax
0x1800a5216  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a521b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800a5220  mov     rcx, rax; lpExistingFileName
0x1800a5223  mov     r8d, 1; dwFlags
0x1800a5229  mov     rdx, rbx; lpNewFileName
0x1800a522c  call    cs:__imp_MoveFileExW
0x1800a5233  nop     dword ptr [rax+rax+00h]
0x1800a5238  inc     rdi
0x1800a523b  cmp     rdi, 6
0x1800a523f  jnz     loc_1800A5157
0x1800a5245  lea     rcx, [rsp+3E0h+var_380]
0x1800a524a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a524f  nop
0x1800a5250  lea     rcx, [rsp+3E0h+var_3C0]
0x1800a5255  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a525a  nop
0x1800a525b  lea     r9, ??1GenericMapping@?$GenericMappingUtilities@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@W4ApiScenario@JsonOutputBuilder@Diagnostics@Autopilot@Windows@Microsoft@@@Diagnostics@Autopilot@Windows@Microsoft@@QEAA@XZ; void (*)(void *)
0x1800a5262  lea     edx, [rdi+1Ah]; unsigned __int64
0x1800a5265  mov     r8, rdi; unsigned __int64
0x1800a5268  lea     rcx, [rbp+2E0h+var_2E0]; void *
0x1800a526c  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x1800a5271  nop
0x1800a5272  lea     rcx, [rsp+3E0h+var_3A0]
0x1800a5277  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a527c  nop
0x1800a527d  lea     rcx, [rbp+2E0h+var_360]
0x1800a5281  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800a5286  xor     eax, eax
0x1800a5288  mov     rcx, [rbp+2E0h+var_10]
0x1800a528f  xor     rcx, rsp; StackCookie
0x1800a5292  call    __security_check_cookie
0x1800a5297  lea     r11, [rsp+3E0h+var_s0]
0x1800a529f  mov     rbx, [r11+18h]
0x1800a52a3  mov     rdi, [r11+20h]
0x1800a52a7  mov     rsp, r11
0x1800a52aa  pop     rbp
0x1800a52ab  retn
```
