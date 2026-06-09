# Microsoft::Windows::Autopilot::GetJsonFromRegistry(Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)

- ea: `0x1800185c0`
- end: `0x180018915`
- name: `?GetJsonFromRegistry@Autopilot@Windows@Microsoft@@YAJAEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@3@@Z`
- size: `853`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180018430`
- `0x18001891c`

## callees

- `0x1800045b0`
- `0x18000ec40`
- `0x1800105f4`
- `0x1800166dc`
- `0x1800174f0`
- `0x1800175f4`
- `0x180018120`
- `0x1800185c0`
- `0x18001f0ec`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001864f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018710`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001864f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018710`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180018783`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180018892`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018828`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800187b5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018806`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018828`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800185f8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800186c0`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800185f8`
- `ntdll!RtlIsStateSeparationEnabled` at `0x1800186c0`

## string_xrefs

- `0x18001888b`: `Windows.Data.Json.JsonObject`
- `0x180018641`: `PolicyJsonCache`
- `0x1800186ff`: `PolicyJsonCache`
- `0x180018617`: `OSData\Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180018610`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x1800186da`: `Software\Microsoft\Provisioning\AutopilotPolicyCache`
- `0x180018725`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x18001879a`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1800187eb`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x180018862`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`
- `0x1800188d5`: `onecoreuap\admin\moderndeployment\autopilot\commonutils\autopilotpolicycache.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
      std::wstring::_Tidy_deallocate(&Src);
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
      std::wstring::_Tidy_deallocate(&Src);
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
    std::wstring::_Tidy_deallocate(&Src);
    return 0;
  }
  if ( (unsigned int)(ValueW - 2) <= 1 )
  {
    v34 = 0;
    v22 = WindowsCreateStringReference(L"Windows.Data.Json.JsonObject", 0x1Cu, &Src, &v34);
    if ( v22 < 0 )
    {
      Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v22, v23, v24);
      JUMPOUT(0x180018913LL);
    }
    v25 = v34;
    v26 = *a1;
    if ( *a1 )
    {
      *a1 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
    }
    v27 = Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(v25, a1);
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
0x1800185c0  push    rbx
0x1800185c2  push    rsi
0x1800185c3  push    rdi
0x1800185c4  push    r14
0x1800185c6  sub     rsp, 88h
0x1800185cd  mov     rax, cs:__security_cookie
0x1800185d4  xor     rax, rsp
0x1800185d7  mov     [rsp+0A8h+var_38], rax
0x1800185dc  mov     rdi, rcx
0x1800185df  xor     r14d, r14d
0x1800185e2  mov     [rsp+0A8h+var_68], r14d
0x1800185e7  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r14b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800185ee  jz      short loc_1800185F8
0x1800185f0  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800185f6  jmp     short loc_180018610
0x1800185f8  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800185fe  test    al, al
0x180018600  setnz   al
0x180018603  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x180018609  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x180018610  lea     rcx, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x180018617  lea     rsi, aOsdataSoftware; "OSData\\Software\\Microsoft\\Provisioni"...
0x18001861e  mov     rdx, rsi
0x180018621  test    al, al
0x180018623  cmovz   rdx, rcx; lpSubKey
0x180018627  lea     rax, [rsp+0A8h+var_68]
0x18001862c  mov     [rsp+0A8h+pcbData], rax; pcbData
0x180018631  mov     [rsp+0A8h+pvData], r14; pvData
0x180018636  mov     [rsp+0A8h+pdwType], r14; int
0x18001863b  mov     r9d, 2; dwFlags
0x180018641  lea     r8, aPolicyjsoncach; "PolicyJsonCache"
0x180018648  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001864f  call    cs:__imp_RegGetValueW
0x180018655  mov     ebx, eax
0x180018657  test    eax, eax
0x180018659  jnz     loc_18001883E
0x18001865f  xorps   xmm0, xmm0
0x180018662  movups  xmmword ptr [rsp+0A8h+Src], xmm0
0x180018667  mov     [rsp+0A8h+var_48], r14
0x18001866c  mov     [rsp+0A8h+var_40], 7
0x180018675  mov     word ptr [rsp+0A8h+Src], r14w
0x18001867b  mov     edx, [rsp+0A8h+var_68]
0x18001867f  shr     rdx, 1
0x180018682  jnz     short loc_180018691
0x180018684  mov     [rsp+0A8h+var_48], rdx
0x180018689  mov     word ptr [rsp+rdx*2+0A8h+Src], r14w
0x18001868f  jmp     short loc_18001869E
0x180018691  xor     r8d, r8d
0x180018694  lea     rcx, [rsp+0A8h+Src]; Src
0x180018699  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@_KG@Z; std::wstring::append(unsigned __int64,ushort)
0x18001869e  lea     rbx, [rsp+0A8h+Src]
0x1800186a3  cmp     [rsp+0A8h+var_40], 7
0x1800186a9  cmova   rbx, [rsp+0A8h+Src]
0x1800186af  cmp     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, r14b; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800186b6  jz      short loc_1800186C0
0x1800186b8  mov     al, cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800186be  jmp     short loc_1800186D8
0x1800186c0  call    cs:__imp_RtlIsStateSeparationEnabled
0x1800186c6  test    al, al
0x1800186c8  setnz   al
0x1800186cb  mov     cs:?s_Redirection@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, al; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_Redirection
0x1800186d1  mov     cs:?s_HasRun@?1??ZTPIsStateSeparationEnabled@@YA_NXZ@4_NA, 1; bool `ZTPIsStateSeparationEnabled(void)'::`2'::s_HasRun
0x1800186d8  test    al, al
0x1800186da  lea     rax, SubKey; "Software\\Microsoft\\Provisioning\\Auto"...
0x1800186e1  cmovz   rsi, rax
0x1800186e5  lea     rax, [rsp+0A8h+var_68]
0x1800186ea  mov     [rsp+0A8h+pcbData], rax; pcbData
0x1800186ef  mov     [rsp+0A8h+pvData], rbx; pvData
0x1800186f4  mov     [rsp+0A8h+pdwType], r14; int
0x1800186f9  mov     r9d, 2; dwFlags
0x1800186ff  lea     r8, aPolicyjsoncach; "PolicyJsonCache"
0x180018706  mov     rdx, rsi; lpSubKey
0x180018709  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180018710  call    cs:__imp_RegGetValueW
0x180018716  test    eax, eax
0x180018718  jz      short loc_180018749
0x18001871a  mov     rcx, [rsp+0A8h]; this
0x180018722  mov     r9d, eax; char *
0x180018725  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x18001872c  mov     edx, 2Bh ; '+'; void *
0x180018731  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180018736  mov     ebx, eax
0x180018738  lea     rcx, [rsp+0A8h+Src]
0x18001873d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018742  mov     eax, ebx
0x180018744  jmp     loc_1800188F2
0x180018749  mov     [rsp+0A8h+string], r14
0x18001874e  lea     rax, [rsp+0A8h+Src]
0x180018753  cmp     [rsp+0A8h+var_40], 7
0x180018759  cmova   rax, [rsp+0A8h+Src]
0x18001875f  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180018763  inc     rdx; length
0x180018766  cmp     [rax+rdx*2], r14w
0x18001876b  jnz     short loc_180018763
0x18001876d  lea     rcx, [rsp+0A8h+Src]
0x180018772  cmp     [rsp+0A8h+var_40], 7
0x180018778  cmova   rcx, [rsp+0A8h+Src]; sourceString
0x18001877e  lea     r8, [rsp+0A8h+string]; string
0x180018783  call    cs:__imp_WindowsCreateString
0x180018789  mov     ebx, eax
0x18001878b  test    eax, eax
0x18001878d  jns     short loc_1800187CD
0x18001878f  mov     rcx, [rsp+0A8h]; this
0x180018797  mov     r9d, eax; char *
0x18001879a  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800187a1  mov     edx, 2Eh ; '.'; void *
0x1800187a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187ab  mov     rcx, [rsp+0A8h+string]; string
0x1800187b0  test    rcx, rcx
0x1800187b3  jz      short loc_1800187BC
0x1800187b5  call    cs:__imp_WindowsDeleteString
0x1800187bb  nop
0x1800187bc  lea     rcx, [rsp+0A8h+Src]
0x1800187c1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800187c6  mov     eax, ebx
0x1800187c8  jmp     loc_1800188F2
0x1800187cd  mov     rdx, rdi
0x1800187d0  lea     rcx, [rsp+0A8h+string]
0x1800187d5  call    ?FromString@JsonHelpers@Autopilot@Windows@Microsoft@@SAJAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@AEAV?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@4@@Z; Microsoft::Windows::Autopilot::JsonHelpers::FromString(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>> const &,Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject> &)
0x1800187da  mov     ebx, eax
0x1800187dc  test    eax, eax
0x1800187de  jns     short loc_18001881E
0x1800187e0  mov     rcx, [rsp+0A8h]; this
0x1800187e8  mov     r9d, eax; char *
0x1800187eb  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800187f2  mov     edx, 2Fh ; '/'; void *
0x1800187f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800187fc  mov     rcx, [rsp+0A8h+string]; string
0x180018801  test    rcx, rcx
0x180018804  jz      short loc_18001880D
0x180018806  call    cs:__imp_WindowsDeleteString
0x18001880c  nop
0x18001880d  lea     rcx, [rsp+0A8h+Src]
0x180018812  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018817  mov     eax, ebx
0x180018819  jmp     loc_1800188F2
0x18001881e  mov     rcx, [rsp+0A8h+string]; string
0x180018823  test    rcx, rcx
0x180018826  jz      short loc_18001882F
0x180018828  call    cs:__imp_WindowsDeleteString
0x18001882e  nop
0x18001882f  lea     rcx, [rsp+0A8h+Src]
0x180018834  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180018839  jmp     loc_1800188EA
0x18001883e  add     eax, 0FFFFFFFEh
0x180018841  cmp     eax, 1
0x180018844  jbe     short loc_180018877
0x180018846  test    ebx, ebx
0x180018848  jle     short loc_180018855
0x18001884a  movzx   ebx, bx
0x18001884d  or      ebx, 80070000h
0x180018853  test    ebx, ebx
0x180018855  jns     short loc_180018873
0x180018857  mov     rcx, [rsp+0A8h]; this
0x18001885f  mov     r9d, ebx; char *
0x180018862  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x180018869  mov     edx, 38h ; '8'; void *
0x18001886e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018873  mov     eax, ebx
0x180018875  jmp     short loc_1800188F2
0x180018877  mov     [rsp+0A8h+var_40], r14
0x18001887c  lea     r9, [rsp+0A8h+var_40]; string
0x180018881  lea     r8, [rsp+0A8h+Src]; hstringHeader
0x180018886  mov     edx, 1Ch; length
0x18001888b  lea     rcx, ?RuntimeClass_Windows_Data_Json_JsonObject@@3QBGB; "Windows.Data.Json.JsonObject"
0x180018892  call    cs:__imp_WindowsCreateStringReference
0x180018898  test    eax, eax
0x18001889a  js      short loc_18001890C
0x18001889c  mov     rbx, [rsp+0A8h+var_40]
0x1800188a1  mov     rcx, [rdi]
0x1800188a4  test    rcx, rcx
0x1800188a7  jz      short loc_1800188B9
0x1800188a9  mov     [rdi], r14
0x1800188ac  mov     rax, [rcx]
0x1800188af  mov     rax, [rax+10h]
0x1800188b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800188b8  nop
0x1800188b9  mov     rdx, rdi
0x1800188bc  mov     rcx, rbx
0x1800188bf  call    ??$ActivateInstance@UIJsonObject@Json@Data@Windows@@@Foundation@Windows@@YAJPEAUHSTRING__@@PEAPEAUIJsonObject@Json@Data@1@@Z; Windows::Foundation::ActivateInstance<Windows::Data::Json::IJsonObject>(HSTRING__ *,Windows::Data::Json::IJsonObject * *)
0x1800188c4  mov     ebx, eax
0x1800188c6  test    eax, eax
0x1800188c8  jns     short loc_1800188EA
0x1800188ca  mov     rcx, [rsp+0A8h]; this
0x1800188d2  mov     r9d, eax; char *
0x1800188d5  lea     r8, aOnecoreuapAdmi_4; "onecoreuap\\admin\\moderndeployment\\au"...
0x1800188dc  mov     edx, 34h ; '4'; void *
0x1800188e1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800188e6  mov     eax, ebx
0x1800188e8  jmp     short loc_1800188F2
0x1800188ea  xor     eax, eax
0x1800188ec  jmp     short loc_1800188F2
0x1800188ee  mov     eax, [rsp+0A8h+var_68]
0x1800188f2  mov     rcx, [rsp+0A8h+var_38]
0x1800188f7  xor     rcx, rsp; StackCookie
0x1800188fa  call    __security_check_cookie
0x1800188ff  add     rsp, 88h
0x180018906  pop     r14
0x180018908  pop     rdi
0x180018909  pop     rsi
0x18001890a  pop     rbx
0x18001890b  retn
0x18001890c  mov     ecx, eax; this
0x18001890e  call    ?RaiseException@Details@WRL@Microsoft@@YAXJK@Z; Microsoft::WRL::Details::RaiseException(long,ulong)
```
