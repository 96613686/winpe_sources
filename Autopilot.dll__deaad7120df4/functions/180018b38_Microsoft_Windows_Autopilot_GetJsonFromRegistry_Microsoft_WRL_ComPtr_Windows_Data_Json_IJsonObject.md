# Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x180018b38`
- end: `0x180018ec7`
- name: `?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z`
- size: `911`
- prototype: `__int64 __fastcall(__int64 *, __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800189a4`
- `0x180018ed0`

## callees

- `0x1800045d0`
- `0x18000ed44`
- `0x180010764`
- `0x180016b80`
- `0x180017a20`
- `0x180017b2c`
- `0x180018678`
- `0x180018b38`
- `0x18001f98c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018bcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018c9a`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018bcd`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018c9a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018d13`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018e3d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018d4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018da2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018dca`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018d4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018da2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018dca`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180018b70`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180018c44`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180018b70`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180018c44`

## string_xrefs

- `0x180018e36`: `Windows.Data.Json.JsonObject`
- `0x180018bbf`: `PolicyJsonCache`
- `0x180018c89`: `PolicyJsonCache`
- `0x180018b95`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180018b8e`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180018c64`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180018cb5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018d30`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018d87`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018e0a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018e86`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
__int64 __fastcall Microsoft::Windows::Autopilot::GetJsonFromRegistry(__int64 *a1, __int64 a2)
{
  char v3; // al
  const WCHAR *v4; // rsi
  const WCHAR *v5; // rdx
  LSTATUS ValueW; // eax
  __int64 v7; // rcx
  unsigned int v8; // ebx
  unsigned __int64 v9; // rdx
  HSTRING_HEADER *pvData; // rbx
  char v11; // al
  unsigned int v12; // eax
  unsigned int v13; // ebx
  HSTRING_HEADER *p_Src; // rax
  __int64 v16; // rdx
  const WCHAR *Reserved1; // rcx
  HRESULT v18; // eax
  unsigned int v19; // ebx
  int v20; // eax
  bool v21; // sf
  HRESULT v22; // eax
  int v23; // edx
  unsigned int v24; // r8d
  HSTRING v25; // rbx
  __int64 v26; // rcx
  int v27; // eax
  unsigned int v28; // ebx
  int pdwType; // [rsp+20h] [rbp-88h]
  unsigned int pdwTypea; // [rsp+20h] [rbp-88h]
  DWORD pcbData; // [rsp+40h] [rbp-68h] BYREF
  HSTRING string; // [rsp+48h] [rbp-60h] BYREF
  HSTRING_HEADER Src; // [rsp+50h] [rbp-58h] BYREF
  HSTRING v34; // [rsp+68h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  pcbData = 0;
  if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
  {
    v3 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
  }
  else
  {
    v3 = (unsigned __int8)RtlIsStateSeparationEnabled(a1, a2) != 0;
    `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v3;
    `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
  }
  v4 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  v5 = L"OSData\\Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  if ( !v3 )
    v5 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
  ValueW = RegGetValueW(HKEY_LOCAL_MACHINE, v5, L"PolicyJsonCache", 2u, 0, 0, &pcbData);
  v8 = ValueW;
  if ( !ValueW )
  {
    memset(&Src, 0, sizeof(Src));
    v34 = (HSTRING)7;
    LOWORD(Src.Reserved.Reserved1) = 0;
    v9 = (unsigned __int64)pcbData >> 1;
    if ( v9 )
    {
      std::wstring::append(&Src);
    }
    else
    {
      *(_QWORD *)&Src.Reserved.Reserved2[16] = 0;
      LOWORD(Src.Reserved.Reserved1) = 0;
    }
    pvData = &Src;
    if ( (unsigned __int64)v34 > 7 )
      pvData = (HSTRING_HEADER *)Src.Reserved.Reserved1;
    if ( `ZTPIsStateSeparationEnabled'::`2'::s_HasRun )
    {
      v11 = `ZTPIsStateSeparationEnabled'::`2'::s_Redirection;
    }
    else
    {
      v11 = (unsigned __int8)RtlIsStateSeparationEnabled(v7, v9) != 0;
      `ZTPIsStateSeparationEnabled'::`2'::s_Redirection = v11;
      `ZTPIsStateSeparationEnabled'::`2'::s_HasRun = 1;
    }
    if ( !v11 )
      v4 = L"Software\\Microsoft\\Provisioning\\AutopilotPolicyCache";
    v12 = RegGetValueW(HKEY_LOCAL_MACHINE, v4, L"PolicyJsonCache", 2u, 0, pvData, &pcbData);
    if ( v12 )
    {
      v13 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)0x2B,
              (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
              (const char *)v12,
              pdwTypea);
      std::wstring::_Tidy_deallocate((char **)&Src);
      return v13;
    }
    string = 0;
    p_Src = &Src;
    if ( (unsigned __int64)v34 > 7 )
      p_Src = (HSTRING_HEADER *)Src.Reserved.Reserved1;
    v16 = -1;
    do
      ++v16;
    while ( *(_WORD *)&p_Src->Reserved.Reserved2[2 * v16] );
    Reserved1 = (const WCHAR *)&Src;
    if ( (unsigned __int64)v34 > 7 )
      Reserved1 = (const WCHAR *)Src.Reserved.Reserved1;
    v18 = WindowsCreateString(Reserved1, v16, &string);
    v19 = v18;
    if ( v18 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2E,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)(unsigned int)v18,
        pdwTypea);
      if ( string )
        WindowsDeleteString(string);
LABEL_28:
      std::wstring::_Tidy_deallocate((char **)&Src);
      return v19;
    }
    v20 = Microsoft::Windows::Autopilot::JsonHelpers::FromString(&string, a1);
    v19 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)(unsigned int)v20,
        pdwTypea);
      if ( string )
        WindowsDeleteString(string);
      goto LABEL_28;
    }
    if ( string )
      WindowsDeleteString(string);
    std::wstring::_Tidy_deallocate((char **)&Src);
    return 0;
  }
  if ( (unsigned int)(ValueW - 2) <= 1 )
  {
    v34 = 0;
    v22 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &Src, &v34);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      JUMPOUT(0x180018EC5LL);
    }
    v25 = v34;
    v26 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>((__int64)v25, a1);
    v28 = v27;
    if ( v27 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x34,
        (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
        (const char *)(unsigned int)v27,
        pdwType);
      return v28;
    }
    return 0;
  }
  v21 = ValueW < 0;
  if ( ValueW > 0 )
  {
    v8 = (unsigned __int16)ValueW | 0x80070000;
    v21 = 1;
  }
  if ( v21 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\admin\\moderndeployment\\autopilot\\commonutils\\autopilotpolicycache.cpp",
      (const char *)v8,
      pdwType);
  return v8;
}

```

## disassembly

```asm
0x180018b38  push    rbx
0x180018b3a  push    rsi
0x180018b3b  push    rdi
0x180018b3c  push    r14
0x180018b3e  sub     rsp, 88h
0x180018b45  mov     rax, cs:__security_cookie
0x180018b4c  xor     rax, rsp
0x180018b4f  mov     [rsp+0A8h+var_38], rax
0x180018b54  mov     rdi, rcx
0x180018b57  xor     r14d, r14d
0x180018b5a  mov     [rsp+0A8h+var_68], r14d
0x180018b5f  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r14b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180018b66  jz      short loc_180018B70
0x180018b68  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180018b6e  jmp     short loc_180018B8E
0x180018b70  call    cs:__imp_RtlIsStateSeparationEnabled
0x180018b77  nop     dword ptr [rax+rax+00h]
0x180018b7c  test    al, al
0x180018b7e  setnz   al
0x180018b81  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180018b87  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180018b8e  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x180018b95  lea     rsi, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x180018b9c  mov     rdx, rsi
0x180018b9f  test    al, al
0x180018ba1  cmovz   rdx, rcx; lpSubKey
0x180018ba5  lea     rax, [rsp+0A8h+var_68]
0x180018baa  mov     [rsp+0A8h+pcbData], rax; pcbData
0x180018baf  mov     [rsp+0A8h+pvData], r14; pvData
0x180018bb4  mov     [rsp+0A8h+pdwType], r14; int
0x180018bb9  mov     r9d, 2; dwFlags
0x180018bbf  lea     r8, aPolicyjsoncach; "PolicyJsonCache"
0x180018bc6  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180018bcd  call    cs:__imp_RegGetValueW
0x180018bd4  nop     dword ptr [rax+rax+00h]
0x180018bd9  mov     ebx, eax
0x180018bdb  test    eax, eax
0x180018bdd  jnz     loc_180018DE6
0x180018be3  xorps   xmm0, xmm0
0x180018be6  movups  xmmword ptr [rsp+0A8h+Src], xmm0
0x180018beb  mov     [rsp+0A8h+var_48], r14
0x180018bf0  mov     [rsp+0A8h+var_40], 7
0x180018bf9  mov     word ptr [rsp+0A8h+Src], r14w
0x180018bff  mov     edx, [rsp+0A8h+var_68]
0x180018c03  shr     rdx, 1
0x180018c06  jnz     short loc_180018C15
0x180018c08  mov     [rsp+0A8h+var_48], rdx
0x180018c0d  mov     word ptr [rsp+rdx*2+0A8h+Src], r14w
0x180018c13  jmp     short loc_180018C22
0x180018c15  xor     r8d, r8d
0x180018c18  lea     rcx, [rsp+0A8h+Src]; Src
0x180018c1d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x180018c22  lea     rbx, [rsp+0A8h+Src]
0x180018c27  cmp     [rsp+0A8h+var_40], 7
0x180018c2d  cmova   rbx, [rsp+0A8h+Src]
0x180018c33  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r14b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180018c3a  jz      short loc_180018C44
0x180018c3c  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180018c42  jmp     short loc_180018C62
0x180018c44  call    cs:__imp_RtlIsStateSeparationEnabled
0x180018c4b  nop     dword ptr [rax+rax+00h]
0x180018c50  test    al, al
0x180018c52  setnz   al
0x180018c55  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180018c5b  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180018c62  test    al, al
0x180018c64  lea     rax, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x180018c6b  cmovz   rsi, rax
0x180018c6f  lea     rax, [rsp+0A8h+var_68]
0x180018c74  mov     [rsp+0A8h+pcbData], rax; pcbData
0x180018c79  mov     [rsp+0A8h+pvData], rbx; pvData
0x180018c7e  mov     [rsp+0A8h+pdwType], r14; int
0x180018c83  mov     r9d, 2; dwFlags
0x180018c89  lea     r8, aPolicyjsoncach; "PolicyJsonCache"
0x180018c90  mov     rdx, rsi; lpSubKey
0x180018c93  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180018c9a  call    cs:__imp_RegGetValueW
0x180018ca1  nop     dword ptr [rax+rax+00h]
0x180018ca6  test    eax, eax
0x180018ca8  jz      short loc_180018CD9
0x180018caa  mov     rcx, [rsp+0A8h]; this
0x180018cb2  mov     r9d, eax; char *
0x180018cb5  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018cbc  mov     edx, 2Bh ; '+'; void *
0x180018cc1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018cc6  mov     ebx, eax
0x180018cc8  lea     rcx, [rsp+0A8h+Src]
0x180018ccd  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018cd2  mov     eax, ebx
0x180018cd4  jmp     loc_180018EA3
0x180018cd9  mov     [rsp+0A8h+string], r14
0x180018cde  lea     rax, [rsp+0A8h+Src]
0x180018ce3  cmp     [rsp+0A8h+var_40], 7
0x180018ce9  cmova   rax, [rsp+0A8h+Src]
0x180018cef  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018cf3  inc     rdx; length
0x180018cf6  cmp     [rax+rdx*2], r14w
0x180018cfb  jnz     short loc_180018CF3
0x180018cfd  lea     rcx, [rsp+0A8h+Src]
0x180018d02  cmp     [rsp+0A8h+var_40], 7
0x180018d08  cmova   rcx, [rsp+0A8h+Src]; sourceString
0x180018d0e  lea     r8, [rsp+0A8h+string]; string
0x180018d13  call    cs:__imp_WindowsCreateString
0x180018d1a  nop     dword ptr [rax+rax+00h]
0x180018d1f  mov     ebx, eax
0x180018d21  test    eax, eax
0x180018d23  jns     short loc_180018D69
0x180018d25  mov     rcx, [rsp+0A8h]; this
0x180018d2d  mov     r9d, eax; char *
0x180018d30  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018d37  mov     edx, 2Eh ; '.'; void *
0x180018d3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d41  mov     rcx, [rsp+0A8h+string]; string
0x180018d46  test    rcx, rcx
0x180018d49  jz      short loc_180018D58
0x180018d4b  call    cs:__imp_WindowsDeleteString
0x180018d52  nop     dword ptr [rax+rax+00h]
0x180018d57  nop
0x180018d58  lea     rcx, [rsp+0A8h+Src]
0x180018d5d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018d62  mov     eax, ebx
0x180018d64  jmp     loc_180018EA3
0x180018d69  mov     rdx, rdi
0x180018d6c  lea     rcx, [rsp+0A8h+string]
0x180018d71  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x180018d76  mov     ebx, eax
0x180018d78  test    eax, eax
0x180018d7a  jns     short loc_180018DC0
0x180018d7c  mov     rcx, [rsp+0A8h]; this
0x180018d84  mov     r9d, eax; char *
0x180018d87  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018d8e  mov     edx, 2Fh ; '/'; void *
0x180018d93  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d98  mov     rcx, [rsp+0A8h+string]; string
0x180018d9d  test    rcx, rcx
0x180018da0  jz      short loc_180018DAF
0x180018da2  call    cs:__imp_WindowsDeleteString
0x180018da9  nop     dword ptr [rax+rax+00h]
0x180018dae  nop
0x180018daf  lea     rcx, [rsp+0A8h+Src]
0x180018db4  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018db9  mov     eax, ebx
0x180018dbb  jmp     loc_180018EA3
0x180018dc0  mov     rcx, [rsp+0A8h+string]; string
0x180018dc5  test    rcx, rcx
0x180018dc8  jz      short loc_180018DD7
0x180018dca  call    cs:__imp_WindowsDeleteString
0x180018dd1  nop     dword ptr [rax+rax+00h]
0x180018dd6  nop
0x180018dd7  lea     rcx, [rsp+0A8h+Src]
0x180018ddc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018de1  jmp     loc_180018E9B
0x180018de6  add     eax, 0FFFFFFFEh
0x180018de9  cmp     eax, 1
0x180018dec  jbe     short loc_180018E22
0x180018dee  test    ebx, ebx
0x180018df0  jle     short loc_180018DFD
0x180018df2  movzx   ebx, bx
0x180018df5  or      ebx, 80070000h
0x180018dfb  test    ebx, ebx
0x180018dfd  jns     short loc_180018E1B
0x180018dff  mov     rcx, [rsp+0A8h]; this
0x180018e07  mov     r9d, ebx; char *
0x180018e0a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018e11  mov     edx, 38h ; '8'; void *
0x180018e16  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e1b  mov     eax, ebx
0x180018e1d  jmp     loc_180018EA3
0x180018e22  mov     [rsp+0A8h+var_40], r14
0x180018e27  lea     r9, [rsp+0A8h+var_40]; string
0x180018e2c  lea     r8, [rsp+0A8h+Src]; hstringHeader
0x180018e31  mov     edx, 1Ch; length
0x180018e36  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180018e3d  call    cs:__imp_WindowsCreateStringReference
0x180018e44  nop     dword ptr [rax+rax+00h]
0x180018e49  test    eax, eax
0x180018e4b  js      short loc_180018EBE
0x180018e4d  mov     rbx, [rsp+0A8h+var_40]
0x180018e52  mov     rcx, [rdi]
0x180018e55  test    rcx, rcx
0x180018e58  jz      short loc_180018E6A
0x180018e5a  mov     [rdi], r14
0x180018e5d  mov     rax, [rcx]
0x180018e60  mov     rax, [rax+10h]
0x180018e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018e69  nop
0x180018e6a  mov     rdx, rdi
0x180018e6d  mov     rcx, rbx
0x180018e70  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x180018e75  mov     ebx, eax
0x180018e77  test    eax, eax
0x180018e79  jns     short loc_180018E9B
0x180018e7b  mov     rcx, [rsp+0A8h]; this
0x180018e83  mov     r9d, eax; char *
0x180018e86  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018e8d  mov     edx, 34h ; '4'; void *
0x180018e92  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e97  mov     eax, ebx
0x180018e99  jmp     short loc_180018EA3
0x180018e9b  xor     eax, eax
0x180018e9d  jmp     short loc_180018EA3
0x180018e9f  mov     eax, [rsp+0A8h+var_68]
0x180018ea3  mov     rcx, [rsp+0A8h+var_38]
0x180018ea8  xor     rcx, rsp; StackCookie
0x180018eab  call    __security_check_cookie
0x180018eb0  add     rsp, 88h
0x180018eb7  pop     r14
0x180018eb9  pop     rdi
0x180018eba  pop     rsi
0x180018ebb  pop     rbx
0x180018ebc  retn
0x180018ebe  mov     ecx, eax; this
0x180018ec0  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
