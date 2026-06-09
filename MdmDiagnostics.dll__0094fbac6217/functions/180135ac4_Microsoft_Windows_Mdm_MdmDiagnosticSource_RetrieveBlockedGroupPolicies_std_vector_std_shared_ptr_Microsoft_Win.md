# Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>,std::allocator<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>> &)

- ea: `0x180135ac4`
- end: `0x180135eeb`
- name: `?RetrieveBlockedGroupPolicies@MdmDiagnosticSource@Mdm@Windows@Microsoft@@YAJAEAV?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@@Z`
- size: `1063`
- prototype: `__int64 __fastcall(int)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18012a624`

## callees

- `0x180019000`
- `0x1800e4348`
- `0x1800e66b8`
- `0x1800e7c08`
- `0x1800ece5c`
- `0x1800ef188`
- `0x1800ef5d8`
- `0x180104108`
- `0x180104270`
- `0x18013432c`
- `0x180135484`
- `0x180135ac4`

## import_xrefs

- `ntdll!RtlIsStateSeparationEnabled` at `0x180135afa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180135afa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135b2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135bd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135c47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135cc3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135b2d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135bd8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135c47`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180135cc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall Microsoft::Windows::Mdm::MdmDiagnosticSource::RetrieveBlockedGroupPolicies(__int64 a1)
{
  __int64 v1; // r14
  char IsStateSeparationEnabled; // al
  const WCHAR *v3; // rdx
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int SubKeyNames; // eax
  __int64 v7; // rdi
  __int64 v8; // r13
  const WCHAR *v9; // rax
  unsigned int v10; // eax
  int v11; // eax
  __int64 v12; // rsi
  __int64 v13; // r12
  const WCHAR *v14; // rax
  unsigned int v15; // eax
  int v16; // eax
  __int64 v17; // rbx
  __int64 v18; // r15
  const WCHAR *v19; // rax
  unsigned int v20; // eax
  int BlockedGroupPolicyData; // eax
  unsigned int v22; // r14d
  int v23; // eax
  unsigned int phkResult; // [rsp+20h] [rbp-99h]
  unsigned int phkResulta; // [rsp+20h] [rbp-99h]
  unsigned int phkResultb; // [rsp+20h] [rbp-99h]
  unsigned int phkResultc; // [rsp+20h] [rbp-99h]
  int phkResultd; // [rsp+20h] [rbp-99h]
  int phkResulte; // [rsp+20h] [rbp-99h]
  HKEY v31; // [rsp+30h] [rbp-89h] BYREF
  HKEY v32; // [rsp+38h] [rbp-81h] BYREF
  HKEY v33; // [rsp+40h] [rbp-79h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-71h] BYREF
  _QWORD v35[3]; // [rsp+50h] [rbp-69h] BYREF
  _QWORD v36[3]; // [rsp+68h] [rbp-51h] BYREF
  __int64 v37; // [rsp+80h] [rbp-39h] BYREF
  __int64 v38; // [rsp+88h] [rbp-31h]
  __int64 v39; // [rsp+98h] [rbp-21h]
  _BYTE v40[32]; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+5Fh]

  v1 = a1;
  v39 = a1;
  hKey = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v3 = L"OSData\\SOFTWARE\\Microsoft\\MdmWins";
  if ( !IsStateSeparationEnabled )
    v3 = L"SOFTWARE\\Microsoft\\MdmWins";
  v4 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, v3, 0, 0x20019u, &hKey);
  if ( v4 )
  {
    v5 = wil::details::in1diag3::Return_Win32(
           retaddr,
           (void *)0x28C,
           (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
           (const char *)v4,
           phkResult);
  }
  else
  {
    std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v35);
    SubKeyNames = anonymous_namespace_::GetSubKeyNames(&hKey, 0, v35);
    v5 = SubKeyNames;
    if ( SubKeyNames >= 0 )
    {
      v7 = v35[0];
      v8 = v35[1];
LABEL_9:
      if ( v7 == v8 )
      {
        std::vector<std::wstring>::_Tidy(v35);
        v5 = 0;
        goto LABEL_37;
      }
      v31 = 0;
      v9 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v7);
      v10 = RegOpenKeyExW(hKey, v9, 0, 0x20019u, &v31);
      if ( v10 )
      {
        v5 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x297,
               (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
               (const char *)v10,
               phkResulta);
      }
      else
      {
        std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(v36);
        v11 = anonymous_namespace_::GetSubKeyNames(&v31, 0, v36);
        v5 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x29A,
            (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
            (const char *)(unsigned int)v11,
            phkResulta);
        }
        else
        {
          v12 = v36[0];
          v13 = v36[1];
          while ( 1 )
          {
            if ( v12 == v13 )
            {
              std::vector<std::wstring>::_Tidy(v36);
              wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
              v7 += 32;
              goto LABEL_9;
            }
            v32 = 0;
            v14 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v12);
            v15 = RegOpenKeyExW(v31, v14, 0, 0x20019u, &v32);
            if ( v15 )
              break;
            std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(&v37);
            v16 = anonymous_namespace_::GetSubKeyNames(&v32, 0, &v37);
            v5 = v16;
            if ( v16 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x2A4,
                (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                (const char *)(unsigned int)v16,
                phkResultb);
              goto LABEL_29;
            }
            v17 = v37;
            v18 = v38;
            if ( (v38 - v37) >> 5 )
            {
              while ( v17 != v18 )
              {
                v33 = 0;
                v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
                v20 = RegOpenKeyExW(v32, v19, 0, 0x20019u, &v33);
                if ( v20 )
                {
                  v5 = wil::details::in1diag3::Return_Win32(
                         retaddr,
                         (void *)0x2AD,
                         (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                         (const char *)v20,
                         phkResultc);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                  goto LABEL_29;
                }
                BlockedGroupPolicyData = anonymous_namespace_::GetBlockedGroupPolicyData(
                                           (unsigned int)&v33,
                                           v7,
                                           v12,
                                           v17,
                                           v1);
                v22 = BlockedGroupPolicyData;
                if ( BlockedGroupPolicyData < 0 )
                {
                  wil::details::in1diag3::Return_Hr(
                    retaddr,
                    (void *)0x2AF,
                    (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                    (const char *)(unsigned int)BlockedGroupPolicyData,
                    phkResultd);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                  std::vector<std::wstring>::_Tidy(&v37);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
                  std::vector<std::wstring>::_Tidy(v36);
                  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
                  std::vector<std::wstring>::_Tidy(v35);
                  v5 = v22;
                  goto LABEL_37;
                }
                wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v33);
                v17 += 32;
                v1 = v39;
              }
            }
            else
            {
              std::wstring::wstring(v40);
              v23 = anonymous_namespace_::GetBlockedGroupPolicyData((unsigned int)&v32, v7, v12, (unsigned int)v40, v1);
              v5 = v23;
              if ( v23 < 0 )
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x2B5,
                  (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                  (const char *)(unsigned int)v23,
                  phkResulte);
                std::wstring::_Tidy_deallocate(v40);
LABEL_29:
                std::vector<std::wstring>::_Tidy(&v37);
                goto LABEL_31;
              }
              std::wstring::_Tidy_deallocate(v40);
            }
            std::vector<std::wstring>::_Tidy(&v37);
            wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
            v12 += 32;
          }
          v5 = wil::details::in1diag3::Return_Win32(
                 retaddr,
                 (void *)0x2A1,
                 (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
                 (const char *)v15,
                 phkResultb);
LABEL_31:
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
        }
        std::vector<std::wstring>::_Tidy(v36);
      }
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x290,
        (unsigned int)"onecoreuap\\admin\\enterprisemgmt\\mdmdiagnostics\\html\\policies.cpp",
        (const char *)(unsigned int)SubKeyNames,
        phkResult);
    }
    std::vector<std::wstring>::_Tidy(v35);
  }
LABEL_37:
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
  return v5;
}

```

## disassembly

```asm
0x180135ac4  push    rbp
0x180135ac6  push    rbx
0x180135ac7  push    rsi
0x180135ac8  push    rdi
0x180135ac9  push    r12
0x180135acb  push    r13
0x180135acd  push    r14
0x180135acf  push    r15
0x180135ad1  lea     rbp, [rsp-1Fh]
0x180135ad6  sub     rsp, 0D8h
0x180135add  mov     rax, cs:__security_cookie
0x180135ae4  xor     rax, rsp
0x180135ae7  mov     [rbp+57h+var_50], rax
0x180135aeb  mov     r14, rcx
0x180135aee  mov     [rbp+57h+var_78], rcx
0x180135af2  mov     [rbp+57h+hKey], 0
0x180135afa  call    cs:__imp_RtlIsStateSeparationEnabled
0x180135b00  lea     rcx, aSoftwareMicros_8; "SOFTWARE\\Microsoft\\MdmWins"
0x180135b07  lea     rdx, aOsdataSoftware_5; "OSData\\SOFTWARE\\Microsoft\\MdmWins"
0x180135b0e  test    al, al
0x180135b10  cmovz   rdx, rcx; lpSubKey
0x180135b14  lea     rax, [rbp+57h+hKey]
0x180135b18  mov     qword ptr [rsp+110h+phkResult], rax; int
0x180135b1d  mov     r9d, 20019h; samDesired
0x180135b23  xor     r8d, r8d; ulOptions
0x180135b26  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180135b2d  call    cs:__imp_RegOpenKeyExW
0x180135b33  test    eax, eax
0x180135b35  jz      short loc_180135B56
0x180135b37  mov     rcx, [rbp+5Fh]; this
0x180135b3b  mov     r9d, eax; char *
0x180135b3e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135b45  mov     edx, 28Ch; void *
0x180135b4a  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135b4f  mov     ebx, eax
0x180135b51  jmp     loc_180135EC0
0x180135b56  lea     rcx, [rbp+57h+var_C0]
0x180135b5a  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180135b5f  nop
0x180135b60  lea     r8, [rbp+57h+var_C0]
0x180135b64  xor     edx, edx
0x180135b66  lea     rcx, [rbp+57h+hKey]
0x180135b6a  call    _anonymous_namespace___GetSubKeyNames
0x180135b6f  mov     ebx, eax
0x180135b71  test    eax, eax
0x180135b73  jns     short loc_180135B9C
0x180135b75  mov     rcx, [rbp+5Fh]; this
0x180135b79  mov     r9d, eax; char *
0x180135b7c  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135b83  mov     edx, 290h; void *
0x180135b88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135b8d  nop
0x180135b8e  lea     rcx, [rbp+57h+var_C0]
0x180135b92  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135b97  jmp     loc_180135EC0
0x180135b9c  mov     rdi, [rbp+57h+var_C0]
0x180135ba0  mov     r13, [rbp+57h+var_B8]
0x180135ba4  cmp     rdi, r13
0x180135ba7  jz      loc_180135EB5
0x180135bad  mov     [rsp+110h+var_E0], 0
0x180135bb6  mov     rcx, rdi
0x180135bb9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180135bbe  lea     rcx, [rsp+110h+var_E0]
0x180135bc3  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180135bc8  mov     r9d, 20019h; samDesired
0x180135bce  xor     r8d, r8d; ulOptions
0x180135bd1  mov     rdx, rax; lpSubKey
0x180135bd4  mov     rcx, [rbp+57h+hKey]; hKey
0x180135bd8  call    cs:__imp_RegOpenKeyExW
0x180135bde  test    eax, eax
0x180135be0  jnz     loc_180135E8C
0x180135be6  lea     rcx, [rbp+57h+var_A8]
0x180135bea  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180135bef  nop
0x180135bf0  lea     r8, [rbp+57h+var_A8]
0x180135bf4  xor     edx, edx
0x180135bf6  lea     rcx, [rsp+110h+var_E0]
0x180135bfb  call    _anonymous_namespace___GetSubKeyNames
0x180135c00  mov     ebx, eax
0x180135c02  test    eax, eax
0x180135c04  js      loc_180135E68
0x180135c0a  mov     rsi, [rbp+57h+var_A8]
0x180135c0e  mov     r12, [rbp+57h+var_A0]
0x180135c12  cmp     rsi, r12
0x180135c15  jz      loc_180135D5A
0x180135c1b  mov     [rsp+110h+var_D8], 0
0x180135c24  mov     rcx, rsi
0x180135c27  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180135c2c  lea     rcx, [rsp+110h+var_D8]
0x180135c31  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180135c36  mov     r9d, 20019h; samDesired
0x180135c3c  xor     r8d, r8d; ulOptions
0x180135c3f  mov     rdx, rax; lpSubKey
0x180135c42  mov     rcx, [rsp+110h+var_E0]; hKey
0x180135c47  call    cs:__imp_RegOpenKeyExW
0x180135c4d  test    eax, eax
0x180135c4f  jnz     loc_180135E42
0x180135c55  lea     rcx, [rbp+57h+var_90]
0x180135c59  call    ??0?$vector@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@V?$allocator@V?$shared_ptr@VGroupPolicy@MdmDiagnosticSource@Mdm@Windows@Microsoft@@@std@@@2@@std@@QEAA@XZ; std::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>::vector<std::shared_ptr<Microsoft::Windows::Mdm::MdmDiagnosticSource::GroupPolicy>>(void)
0x180135c5e  nop
0x180135c5f  lea     r8, [rbp+57h+var_90]
0x180135c63  xor     edx, edx
0x180135c65  lea     rcx, [rsp+110h+var_D8]
0x180135c6a  call    _anonymous_namespace___GetSubKeyNames
0x180135c6f  mov     ebx, eax
0x180135c71  test    eax, eax
0x180135c73  js      loc_180135E1E
0x180135c79  mov     rbx, [rbp+57h+var_90]
0x180135c7d  mov     r15, [rbp+57h+var_88]
0x180135c81  mov     rax, r15
0x180135c84  sub     rax, rbx
0x180135c87  sar     rax, 5
0x180135c8b  test    rax, rax
0x180135c8e  jz      short loc_180135D06
0x180135c90  cmp     rbx, r15
0x180135c93  jz      loc_180135D3D
0x180135c99  mov     [rbp+57h+var_D0], 0
0x180135ca1  mov     rcx, rbx
0x180135ca4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180135ca9  lea     rcx, [rbp+57h+var_D0]
0x180135cad  mov     qword ptr [rsp+110h+phkResult], rcx; unsigned int
0x180135cb2  mov     r9d, 20019h; samDesired
0x180135cb8  xor     r8d, r8d; ulOptions
0x180135cbb  mov     rdx, rax; lpSubKey
0x180135cbe  mov     rcx, [rsp+110h+var_D8]; hKey
0x180135cc3  call    cs:__imp_RegOpenKeyExW
0x180135cc9  test    eax, eax
0x180135ccb  jnz     loc_180135DD5
0x180135cd1  mov     qword ptr [rsp+110h+phkResult], r14; int
0x180135cd6  mov     r9, rbx
0x180135cd9  mov     r8, rsi
0x180135cdc  mov     rdx, rdi
0x180135cdf  lea     rcx, [rbp+57h+var_D0]
0x180135ce3  call    _anonymous_namespace___GetBlockedGroupPolicyData
0x180135ce8  mov     r14d, eax
0x180135ceb  test    eax, eax
0x180135ced  js      loc_180135D77
0x180135cf3  lea     rcx, [rbp+57h+var_D0]
0x180135cf7  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135cfc  add     rbx, 20h ; ' '
0x180135d00  mov     r14, [rbp+57h+var_78]
0x180135d04  jmp     short loc_180135C90
0x180135d06  lea     rcx, [rbp+57h+var_70]
0x180135d0a  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180135d0f  nop
0x180135d10  mov     qword ptr [rsp+110h+phkResult], r14; int
0x180135d15  lea     r9, [rbp+57h+var_70]
0x180135d19  mov     r8, rsi
0x180135d1c  mov     rdx, rdi
0x180135d1f  lea     rcx, [rsp+110h+var_D8]
0x180135d24  call    _anonymous_namespace___GetBlockedGroupPolicyData
0x180135d29  mov     ebx, eax
0x180135d2b  test    eax, eax
0x180135d2d  js      loc_180135DFA
0x180135d33  lea     rcx, [rbp+57h+var_70]
0x180135d37  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180135d3c  nop
0x180135d3d  lea     rcx, [rbp+57h+var_90]
0x180135d41  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135d46  nop
0x180135d47  lea     rcx, [rsp+110h+var_D8]
0x180135d4c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135d51  add     rsi, 20h ; ' '
0x180135d55  jmp     loc_180135C12
0x180135d5a  lea     rcx, [rbp+57h+var_A8]
0x180135d5e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135d63  nop
0x180135d64  lea     rcx, [rsp+110h+var_E0]
0x180135d69  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135d6e  add     rdi, 20h ; ' '
0x180135d72  jmp     loc_180135BA4
0x180135d77  mov     rcx, [rbp+5Fh]; this
0x180135d7b  mov     r9d, r14d; char *
0x180135d7e  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135d85  mov     edx, 2AFh; void *
0x180135d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135d8f  nop
0x180135d90  lea     rcx, [rbp+57h+var_D0]
0x180135d94  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135d99  nop
0x180135d9a  lea     rcx, [rbp+57h+var_90]
0x180135d9e  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135da3  nop
0x180135da4  lea     rcx, [rsp+110h+var_D8]
0x180135da9  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135dae  nop
0x180135daf  lea     rcx, [rbp+57h+var_A8]
0x180135db3  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135db8  nop
0x180135db9  lea     rcx, [rsp+110h+var_E0]
0x180135dbe  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135dc3  nop
0x180135dc4  lea     rcx, [rbp+57h+var_C0]
0x180135dc8  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135dcd  mov     ebx, r14d
0x180135dd0  jmp     loc_180135EC0
0x180135dd5  mov     rcx, [rbp+5Fh]; this
0x180135dd9  mov     r9d, eax; char *
0x180135ddc  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135de3  mov     edx, 2ADh; void *
0x180135de8  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135ded  mov     ebx, eax
0x180135def  lea     rcx, [rbp+57h+var_D0]
0x180135df3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135df8  jmp     short loc_180135E37
0x180135dfa  mov     rcx, [rbp+5Fh]; this
0x180135dfe  mov     r9d, eax; char *
0x180135e01  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135e08  mov     edx, 2B5h; void *
0x180135e0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135e12  nop
0x180135e13  lea     rcx, [rbp+57h+var_70]
0x180135e17  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180135e1c  jmp     short loc_180135E37
0x180135e1e  mov     rcx, [rbp+5Fh]; this
0x180135e22  mov     r9d, eax; char *
0x180135e25  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135e2c  mov     edx, 2A4h; void *
0x180135e31  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135e36  nop
0x180135e37  lea     rcx, [rbp+57h+var_90]
0x180135e3b  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135e40  jmp     short loc_180135E5C
0x180135e42  mov     rcx, [rbp+5Fh]; this
0x180135e46  mov     r9d, eax; char *
0x180135e49  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135e50  mov     edx, 2A1h; void *
0x180135e55  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135e5a  mov     ebx, eax
0x180135e5c  lea     rcx, [rsp+110h+var_D8]
0x180135e61  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135e66  jmp     short loc_180135E81
0x180135e68  mov     rcx, [rbp+5Fh]; this
0x180135e6c  mov     r9d, eax; char *
0x180135e6f  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135e76  mov     edx, 29Ah; void *
0x180135e7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180135e80  nop
0x180135e81  lea     rcx, [rbp+57h+var_A8]
0x180135e85  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135e8a  jmp     short loc_180135EA6
0x180135e8c  mov     rcx, [rbp+5Fh]; this
0x180135e90  mov     r9d, eax; char *
0x180135e93  lea     r8, aOnecoreuapAdmi_32; "onecoreuap\\admin\\enterprisemgmt\\mdmd"...
0x180135e9a  mov     edx, 297h; void *
0x180135e9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180135ea4  mov     ebx, eax
0x180135ea6  lea     rcx, [rsp+110h+var_E0]
0x180135eab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135eb0  jmp     loc_180135B8E
0x180135eb5  lea     rcx, [rbp+57h+var_C0]
0x180135eb9  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180135ebe  xor     ebx, ebx
0x180135ec0  lea     rcx, [rbp+57h+hKey]
0x180135ec4  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180135ec9  mov     eax, ebx
0x180135ecb  mov     rcx, [rbp+57h+var_50]
0x180135ecf  xor     rcx, rsp; StackCookie
0x180135ed2  call    __security_check_cookie
0x180135ed7  add     rsp, 0D8h
0x180135ede  pop     r15
0x180135ee0  pop     r14
0x180135ee2  pop     r13
0x180135ee4  pop     r12
0x180135ee6  pop     rdi
0x180135ee7  pop     rsi
0x180135ee8  pop     rbx
0x180135ee9  pop     rbp
0x180135eea  retn
```
