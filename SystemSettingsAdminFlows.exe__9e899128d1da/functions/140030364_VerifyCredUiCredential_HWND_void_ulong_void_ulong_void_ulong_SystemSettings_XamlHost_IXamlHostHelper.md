# VerifyCredUiCredential(HWND__ *,void *,ulong,void *,ulong,void * &,ulong &,SystemSettings::XamlHost::IXamlHostHelper *)

- ea: `0x140030364`
- end: `0x1400306fc`
- name: `?VerifyCredUiCredential@@YAJPEAUHWND__@@PEAXK1KAEAPEAXAEAKPEAUIXamlHostHelper@XamlHost@SystemSettings@@@Z`
- size: `920`
- prototype: `__int64 __fastcall(HWND, void *, ULONG, void *, ULONG ulInAuthBufferSize, void **ppvOutAuthBuffer, unsigned int *pulOutAuthBufferSize, struct SystemSettings::XamlHost::IXamlHostHelper *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14003007c`

## callees

- `0x140005f30`
- `0x14000ec98`
- `0x140011b68`
- `0x14002ff20`
- `0x140030364`
- `0x140030704`
- `0x14003075c`
- `0x14007d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003042e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140030492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14003042e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140030492`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400303e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030616`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003069b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400306bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400306d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400303e0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030444`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030602`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030616`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140030687`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003069b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400306bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1400306d1`
- `SspiCli!LsaLogonUser` at `0x1400305c5`
- `SspiCli!LsaLogonUser` at `0x1400305c5`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x140030539`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x14003065a`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x140030539`
- `credui!CredUIPromptForWindowsCredentialsW` at `0x14003065a`

## pseudocode

```c
__int64 __fastcall VerifyCredUiCredential(
        HWND a1,
        void *a2,
        ULONG a3,
        void *a4,
        ULONG ulInAuthBufferSize,
        void **ppvOutAuthBuffer,
        unsigned int *pulOutAuthBufferSize,
        struct SystemSettings::XamlHost::IXamlHostHelper *a8)
{
  void (__fastcall *v11)(struct SystemSettings::XamlHost::IXamlHostHelper *, __int64, HSTRING *); // rbx
  void (__fastcall *v12)(struct SystemSettings::XamlHost::IXamlHostHelper *, __int64, HSTRING *); // rbx
  NTSTATUS v13; // edi
  DWORD v14; // edx
  DWORD v15; // eax
  signed int v16; // ebx
  HSTRING v18; // [rsp+70h] [rbp-90h] BYREF
  HSTRING string; // [rsp+78h] [rbp-88h] BYREF
  BOOL pfSave; // [rsp+80h] [rbp-80h] BYREF
  ULONG pulAuthPackage; // [rsp+84h] [rbp-7Ch] BYREF
  void *Token; // [rsp+88h] [rbp-78h] BYREF
  PVOID ProfileBuffer; // [rsp+90h] [rbp-70h] BYREF
  int SubStatus; // [rsp+98h] [rbp-68h] BYREF
  ULONG ProfileBufferLength; // [rsp+9Ch] [rbp-64h] BYREF
  _LSA_STRING OriginName; // [rsp+A0h] [rbp-60h] BYREF
  struct _LUID LogonId; // [rsp+B0h] [rbp-50h] BYREF
  HANDLE LsaHandle; // [rsp+B8h] [rbp-48h]
  _CREDUI_INFOW pUiInfo; // [rsp+C0h] [rbp-40h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v31; // [rsp+100h] [rbp+0h]
  _TOKEN_SOURCE SourceContext; // [rsp+108h] [rbp+8h] BYREF
  struct _QUOTA_LIMITS Quotas; // [rsp+118h] [rbp+18h] BYREF

  LsaHandle = a2;
  string = 0;
  v18 = 0;
  memset(&pUiInfo, 0, sizeof(pUiInfo));
  pUiInfo.cbSize = 40;
  v11 = *(void (__fastcall **)(struct SystemSettings::XamlHost::IXamlHostHelper *, __int64, HSTRING *))(*(_QWORD *)a8 + 80LL);
  WindowsDeleteString(0);
  string = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"PasswordlessRestart_CredUI_Caption",
    0x23u,
    0x22u);
  v11(a8, v31, &string);
  pUiInfo.pszCaptionText = WindowsGetStringRawBuffer(string, 0);
  v12 = *(void (__fastcall **)(struct SystemSettings::XamlHost::IXamlHostHelper *, __int64, HSTRING *))(*(_QWORD *)a8 + 80LL);
  WindowsDeleteString(0);
  v18 = 0;
  v31 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"PasswordlessRestart_CredUI_Message",
    0x23u,
    0x22u);
  v12(a8, v31, &v18);
  pUiInfo.pszMessageText = WindowsGetStringRawBuffer(v18, 0);
  pUiInfo.hwndParent = a1;
  pulAuthPackage = a3;
  pfSave = 0;
  *(_QWORD *)&OriginName.Length = 1638424;
  OriginName.Buffer = "Sign in without password";
  SourceContext = 0;
  ProfileBuffer = 0;
  ProfileBufferLength = 0;
  LogonId = 0;
  Token = 0;
  memset(&Quotas, 0, sizeof(Quotas));
  SubStatus = 0;
  v13 = 0;
  do
  {
    v14 = -2146893044;
    if ( v13 != -1073741715 )
      v14 = 0;
    v15 = CredUIPromptForWindowsCredentialsW(
            &pUiInfo,
            v14,
            &pulAuthPackage,
            a4,
            ulInAuthBufferSize,
            ppvOutAuthBuffer,
            pulOutAuthBufferSize,
            &pfSave,
            0x10u);
    v16 = v15;
    if ( v15 )
    {
      if ( v15 == 1223 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
        wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProfileBuffer);
        WindowsDeleteString(v18);
        v18 = 0;
        WindowsDeleteString(string);
        return 2147943623LL;
      }
    }
    else
    {
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &Token,
        0);
      wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        &ProfileBuffer,
        0);
      v13 = LsaLogonUser(
              LsaHandle,
              &OriginName,
              Interactive,
              a3,
              *ppvOutAuthBuffer,
              *pulOutAuthBufferSize,
              0,
              &SourceContext,
              &ProfileBuffer,
              &ProfileBufferLength,
              &LogonId,
              &Token,
              &Quotas,
              &SubStatus);
    }
  }
  while ( v13 == -1073741715 );
  if ( v13 < 0 )
  {
    if ( v13 == -1073741260 )
      v16 = CredUIPromptForWindowsCredentialsW(
              &pUiInfo,
              5u,
              &pulAuthPackage,
              a4,
              ulInAuthBufferSize,
              ppvOutAuthBuffer,
              pulOutAuthBufferSize,
              &pfSave,
              0x10u);
    if ( v16 > 0 )
      v16 = (unsigned __int16)v16 | 0x80070000;
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProfileBuffer);
    WindowsDeleteString(v18);
    v18 = 0;
    WindowsDeleteString(string);
    return (unsigned int)v16;
  }
  else
  {
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&Token);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ProfileBuffer);
    WindowsDeleteString(v18);
    v18 = 0;
    WindowsDeleteString(string);
    return 0;
  }
}

```

## disassembly

```asm
0x140030364  push    rbp
0x140030366  push    rbx
0x140030367  push    rsi
0x140030368  push    rdi
0x140030369  push    r12
0x14003036b  push    r13
0x14003036d  push    r14
0x14003036f  push    r15
0x140030371  lea     rbp, [rsp-58h]
0x140030376  sub     rsp, 158h
0x14003037d  mov     rax, cs:__security_cookie
0x140030384  xor     rax, rsp
0x140030387  mov     [rbp+90h+var_48], rax
0x14003038b  mov     r12, r9
0x14003038e  mov     r13d, r8d
0x140030391  mov     [rbp+90h+LsaHandle], rdx
0x140030395  mov     rsi, rcx
0x140030398  mov     r14, [rbp+90h+arg_28]
0x14003039f  mov     r15, [rbp+90h+arg_30]
0x1400303a6  mov     rdi, [rbp+90h+arg_38]
0x1400303ad  mov     [rsp+190h+string], 0
0x1400303b6  mov     [rsp+190h+var_120], 0
0x1400303bf  xorps   xmm0, xmm0
0x1400303c2  xor     eax, eax
0x1400303c4  movups  xmmword ptr [rbp+90h+pUiInfo.cbSize], xmm0
0x1400303c8  movups  xmmword ptr [rbp+90h+pUiInfo.pszMessageText], xmm0
0x1400303cc  mov     [rbp+90h+pUiInfo.hbmBanner], rax
0x1400303d0  mov     [rbp+90h+pUiInfo.cbSize], 28h ; '('
0x1400303d7  mov     rax, [rdi]
0x1400303da  mov     rbx, [rax+50h]
0x1400303de  xor     ecx, ecx; string
0x1400303e0  call    cs:__imp_WindowsDeleteString
0x1400303e6  mov     [rsp+190h+string], 0
0x1400303ef  mov     [rbp+90h+var_90], 0
0x1400303f7  mov     r9d, 22h ; '"'; unsigned int
0x1400303fd  lea     r8d, [r9+1]; unsigned int
0x140030401  lea     rdx, sourceString; "PasswordlessRestart_CredUI_Caption"
0x140030408  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x14003040c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140030411  nop
0x140030412  lea     r8, [rsp+190h+string]
0x140030417  mov     rdx, [rbp+90h+var_90]
0x14003041b  mov     rcx, rdi
0x14003041e  mov     rax, rbx
0x140030421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140030426  nop
0x140030427  xor     edx, edx; length
0x140030429  mov     rcx, [rsp+190h+string]; string
0x14003042e  call    cs:__imp_WindowsGetStringRawBuffer
0x140030434  mov     [rbp+90h+pUiInfo.pszCaptionText], rax
0x140030438  mov     rax, [rdi]
0x14003043b  mov     rbx, [rax+50h]
0x14003043f  mov     rcx, [rsp+190h+var_120]; string
0x140030444  call    cs:__imp_WindowsDeleteString
0x14003044a  mov     [rsp+190h+var_120], 0
0x140030453  mov     [rbp+90h+var_90], 0
0x14003045b  mov     r9d, 22h ; '"'; unsigned int
0x140030461  lea     r8d, [r9+1]; unsigned int
0x140030465  lea     rdx, aPasswordlessre_0; "PasswordlessRestart_CredUI_Message"
0x14003046c  lea     rcx, [rbp+90h+hstringHeader]; hstringHeader
0x140030470  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x140030475  nop
0x140030476  lea     r8, [rsp+190h+var_120]
0x14003047b  mov     rdx, [rbp+90h+var_90]
0x14003047f  mov     rcx, rdi
0x140030482  mov     rax, rbx
0x140030485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003048a  nop
0x14003048b  xor     edx, edx; length
0x14003048d  mov     rcx, [rsp+190h+var_120]; string
0x140030492  call    cs:__imp_WindowsGetStringRawBuffer
0x140030498  mov     [rbp+90h+pUiInfo.pszMessageText], rax
0x14003049c  mov     [rbp+90h+pUiInfo.hwndParent], rsi
0x1400304a0  mov     [rbp+90h+pulAuthPackage], r13d
0x1400304a4  mov     [rbp+90h+var_110], 0
0x1400304ab  mov     qword ptr [rbp+90h+OriginName.Length], 190018h
0x1400304b3  lea     rax, aSignInWithoutP; "Sign in without password"
0x1400304ba  mov     [rbp+90h+OriginName.Buffer], rax
0x1400304be  xorps   xmm0, xmm0
0x1400304c1  movups  xmmword ptr [rbp+90h+SourceContext.SourceName], xmm0
0x1400304c5  mov     [rbp+90h+ProfileBuffer], 0
0x1400304cd  mov     [rbp+90h+var_F4], 0
0x1400304d4  mov     qword ptr [rbp+90h+var_E0.LowPart], 0
0x1400304dc  mov     [rbp+90h+var_108], 0
0x1400304e4  movups  xmmword ptr [rbp+90h+var_78.PagedPoolLimit], xmm0
0x1400304e8  movups  xmmword ptr [rbp+90h+var_78.MinimumWorkingSetSize], xmm0
0x1400304ec  movups  xmmword ptr [rbp+90h+var_78.PagefileLimit], xmm0
0x1400304f0  mov     [rbp+90h+var_F8], 0
0x1400304f7  xor     edi, edi
0x1400304f9  mov     esi, [rbp+90h+arg_20]
0x1400304ff  mov     edx, 8009030Ch
0x140030504  xor     eax, eax
0x140030506  cmp     edi, 0C000006Dh
0x14003050c  cmovnz  edx, eax; dwAuthError
0x14003050f  mov     [rsp+190h+dwFlags], 10h; dwFlags
0x140030517  lea     rax, [rbp+90h+var_110]
0x14003051b  mov     [rsp+190h+pfSave], rax; pfSave
0x140030520  mov     [rsp+190h+pulOutAuthBufferSize], r15; pulOutAuthBufferSize
0x140030525  mov     [rsp+190h+ppvOutAuthBuffer], r14; ppvOutAuthBuffer
0x14003052a  mov     [rsp+190h+ulInAuthBufferSize], esi; ulInAuthBufferSize
0x14003052e  mov     r9, r12; pvInAuthBuffer
0x140030531  lea     r8, [rbp+90h+pulAuthPackage]; pulAuthPackage
0x140030535  lea     rcx, [rbp+90h+pUiInfo]; pUiInfo
0x140030539  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x14003053f  mov     ebx, eax
0x140030541  test    eax, eax
0x140030543  jnz     loc_1400305CF
0x140030549  xor     edx, edx
0x14003054b  lea     rcx, [rbp+90h+var_108]
0x14003054f  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x140030554  xor     edx, edx
0x140030556  lea     rcx, [rbp+90h+ProfileBuffer]
0x14003055a  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x14003055f  lea     rax, [rbp+90h+var_F8]
0x140030563  mov     [rsp+190h+SubStatus], rax; SubStatus
0x140030568  lea     rax, [rbp+90h+var_78]
0x14003056c  mov     [rsp+190h+Quotas], rax; Quotas
0x140030571  lea     rax, [rbp+90h+var_108]
0x140030575  mov     [rsp+190h+Token], rax; Token
0x14003057a  lea     rax, [rbp+90h+var_E0]
0x14003057e  mov     [rsp+190h+LogonId], rax; LogonId
0x140030583  lea     rax, [rbp+90h+var_F4]
0x140030587  mov     [rsp+190h+ProfileBufferLength], rax; ProfileBufferLength
0x14003058c  lea     rax, [rbp+90h+ProfileBuffer]
0x140030590  mov     qword ptr [rsp+190h+dwFlags], rax; ProfileBuffer
0x140030595  lea     rax, [rbp+90h+SourceContext]
0x140030599  mov     [rsp+190h+pfSave], rax; SourceContext
0x14003059e  mov     [rsp+190h+pulOutAuthBufferSize], 0; LocalGroups
0x1400305a7  mov     eax, [r15]
0x1400305aa  mov     dword ptr [rsp+190h+ppvOutAuthBuffer], eax; AuthenticationInformationLength
0x1400305ae  mov     rax, [r14]
0x1400305b1  mov     qword ptr [rsp+190h+ulInAuthBufferSize], rax; AuthenticationInformation
0x1400305b6  mov     r9d, r13d; AuthenticationPackage
0x1400305b9  lea     r8d, [rbx+2]; LogonType
0x1400305bd  lea     rdx, [rbp+90h+OriginName]; OriginName
0x1400305c1  mov     rcx, [rbp+90h+LsaHandle]; LsaHandle
0x1400305c5  call    cs:__imp_LsaLogonUser
0x1400305cb  mov     edi, eax
0x1400305cd  jmp     short loc_1400305DA
0x1400305cf  cmp     eax, 4C7h
0x1400305d4  jz      loc_1400306A5
0x1400305da  cmp     edi, 0C000006Dh
0x1400305e0  jz      loc_1400304FF
0x1400305e6  test    edi, edi
0x1400305e8  js      short loc_140030623
0x1400305ea  lea     rcx, [rbp+90h+var_108]
0x1400305ee  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400305f3  lea     rcx, [rbp+90h+ProfileBuffer]
0x1400305f7  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400305fc  nop
0x1400305fd  mov     rcx, [rsp+190h+var_120]; string
0x140030602  call    cs:__imp_WindowsDeleteString
0x140030608  mov     [rsp+190h+var_120], 0
0x140030611  mov     rcx, [rsp+190h+string]; string
0x140030616  call    cs:__imp_WindowsDeleteString
0x14003061c  xor     eax, eax
0x14003061e  jmp     loc_1400306DC
0x140030623  cmp     edi, 0C0000234h
0x140030629  jnz     short loc_140030662
0x14003062b  mov     [rsp+190h+dwFlags], 10h; dwFlags
0x140030633  lea     rax, [rbp+90h+var_110]
0x140030637  mov     [rsp+190h+pfSave], rax; pfSave
0x14003063c  mov     [rsp+190h+pulOutAuthBufferSize], r15; pulOutAuthBufferSize
0x140030641  mov     [rsp+190h+ppvOutAuthBuffer], r14; ppvOutAuthBuffer
0x140030646  mov     [rsp+190h+ulInAuthBufferSize], esi; ulInAuthBufferSize
0x14003064a  mov     r9, r12; pvInAuthBuffer
0x14003064d  lea     r8, [rbp+90h+pulAuthPackage]; pulAuthPackage
0x140030651  mov     edx, 5; dwAuthError
0x140030656  lea     rcx, [rbp+90h+pUiInfo]; pUiInfo
0x14003065a  call    cs:__imp_CredUIPromptForWindowsCredentialsW
0x140030660  mov     ebx, eax
0x140030662  test    ebx, ebx
0x140030664  jle     short loc_14003066F
0x140030666  movzx   ebx, bx
0x140030669  or      ebx, 80070000h
0x14003066f  lea     rcx, [rbp+90h+var_108]
0x140030673  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x140030678  lea     rcx, [rbp+90h+ProfileBuffer]
0x14003067c  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x140030681  nop
0x140030682  mov     rcx, [rsp+190h+var_120]; string
0x140030687  call    cs:__imp_WindowsDeleteString
0x14003068d  mov     [rsp+190h+var_120], 0
0x140030696  mov     rcx, [rsp+190h+string]; string
0x14003069b  call    cs:__imp_WindowsDeleteString
0x1400306a1  mov     eax, ebx
0x1400306a3  jmp     short loc_1400306DC
0x1400306a5  lea     rcx, [rbp+90h+var_108]
0x1400306a9  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1400306ae  lea     rcx, [rbp+90h+ProfileBuffer]
0x1400306b2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaFreeReturnBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaFreeReturnBuffer(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1400306b7  nop
0x1400306b8  mov     rcx, [rsp+190h+var_120]; string
0x1400306bd  call    cs:__imp_WindowsDeleteString
0x1400306c3  mov     [rsp+190h+var_120], 0
0x1400306cc  mov     rcx, [rsp+190h+string]; string
0x1400306d1  call    cs:__imp_WindowsDeleteString
0x1400306d7  mov     eax, 800704C7h
0x1400306dc  mov     rcx, [rbp+90h+var_48]
0x1400306e0  xor     rcx, rsp; StackCookie
0x1400306e3  call    __security_check_cookie
0x1400306e8  add     rsp, 158h
0x1400306ef  pop     r15
0x1400306f1  pop     r14
0x1400306f3  pop     r13
0x1400306f5  pop     r12
0x1400306f7  pop     rdi
0x1400306f8  pop     rsi
0x1400306f9  pop     rbx
0x1400306fa  pop     rbp
0x1400306fb  retn
```
