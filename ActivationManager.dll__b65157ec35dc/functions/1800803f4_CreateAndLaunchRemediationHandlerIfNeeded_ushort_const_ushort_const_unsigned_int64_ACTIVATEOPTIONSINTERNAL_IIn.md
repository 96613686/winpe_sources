# CreateAndLaunchRemediationHandlerIfNeeded(ushort const *,ushort const *,unsigned __int64,ACTIVATEOPTIONSINTERNAL,IInspectable *,long,ACTIVATION_PHASE)

- ea: `0x1800803f4`
- end: `0x180080809`
- name: `?CreateAndLaunchRemediationHandlerIfNeeded@@YAJPEBG0_KW4ACTIVATEOPTIONSINTERNAL@@PEAUIInspectable@@JW4ACTIVATION_PHASE@@@Z`
- size: `1045`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029270`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x180011328`
- `0x180027c60`
- `0x180027ce8`
- `0x18002a380`
- `0x180038c70`
- `0x18004c7d0`
- `0x18005ae90`
- `0x18005ba40`
- `0x18005d2ad`
- `0x18006871c`
- `0x18007faa4`
- `0x18007fe68`
- `0x1800803f4`
- `0x180080a6c`
- `0x180080c34`
- `0x18008e8d8`
- `0x1800a0010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800804d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008050a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800804d7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18008050a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180080636`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800807cb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008066a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080707`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008066a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180080707`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800806c3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800806c3`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800805b8`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800805b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800805da`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800805da`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008057d`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x18008057d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 CreateAndLaunchRemediationHandlerIfNeeded(
        const WCHAR *a1,
        __int64 a2,
        __int64 a3,
        int a4,
        __int64 a5,
        unsigned int a6,
        ...)
{
  char v6; // r12
  char v9; // r14
  int AppActivationFailedHandler; // eax
  unsigned int v11; // ebx
  char v13; // di
  HRESULT v14; // eax
  void *v15; // rbx
  HSTRING v16; // rbx
  HSTRING_HEADER *v17; // rax
  HSTRING *v18; // r9
  PCWSTR StringRawBuffer; // rax
  LSTATUS ValueW; // eax
  int v21; // eax
  int ppv; // [rsp+20h] [rbp-E0h]
  int ppva; // [rsp+20h] [rbp-E0h]
  int ppvb; // [rsp+20h] [rbp-E0h]
  char v25[8]; // [rsp+50h] [rbp-B0h] BYREF
  HSTRING string; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR StringSid; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID v28; // [rsp+68h] [rbp-98h] BYREF
  HANDLE TokenHandle; // [rsp+70h] [rbp-90h] BYREF
  int pvData; // [rsp+78h] [rbp-88h] BYREF
  int v31; // [rsp+7Ch] [rbp-84h] BYREF
  int v32; // [rsp+80h] [rbp-80h] BYREF
  DWORD pcbData; // [rsp+84h] [rbp-7Ch] BYREF
  __int64 v34; // [rsp+88h] [rbp-78h] BYREF
  DWORD ReturnLength; // [rsp+90h] [rbp-70h] BYREF
  int v36; // [rsp+98h] [rbp-68h] BYREF
  PCWSTR v37; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v39; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v40; // [rsp+B8h] [rbp-48h] BYREF
  IID Buf1; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v42[24]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v43; // [rsp+E8h] [rbp-18h]
  HSTRING_HEADER v44; // [rsp+F0h] [rbp-10h] BYREF
  _QWORD TokenInformation[12]; // [rsp+110h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+B8h]
  va_list va; // [rsp+1F0h] [rbp+F0h] BYREF

  va_start(va, a6);
  v6 = a4;
  v37 = a1;
  v40 = a2;
  v39 = a3;
  v36 = a4;
  v38 = a5;
  v9 = 0;
  pcbData = 0;
  if ( (a4 & 0x90001) == 0 )
  {
    Buf1 = 0;
    AppActivationFailedHandler = FindAppActivationFailedHandler(a6, &Buf1);
    v11 = AppActivationFailedHandler;
    if ( AppActivationFailedHandler < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2A4,
        (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
        (const char *)(unsigned int)AppActivationFailedHandler,
        ppv);
      return v11;
    }
    if ( memcmp_0(&Buf1, &GUID_NULL, 0x10u) )
    {
      v28 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      v13 = 1;
      if ( CoCreateInstance(&Buf1, 0, 4u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v28) >= 0
        || (Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28),
            v14 = CoCreateInstance(&Buf1, 0, 1u, &GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e, &v28),
            v11 = v14,
            v14 >= 0) )
      {
        string = 0;
        v31 = 0;
        v32 = 0;
        StringSid = 0;
        if ( !a3 )
          goto LABEL_16;
        TokenHandle = 0;
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &TokenHandle,
          0);
        if ( (int)UMgrQueryUserToken(a3, &TokenHandle) >= 0 )
        {
          memset_0(TokenInformation, 0, 0x54u);
          ReturnLength = 0;
          if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x54u, &ReturnLength) )
          {
            v15 = (void *)TokenInformation[0];
            wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
              &StringSid,
              0);
            if ( !ConvertSidToStringSidW(v15, &StringSid) )
              wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(&StringSid);
          }
        }
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
        if ( StringSid )
        {
          TokenHandle = StringSid;
          v9 = 1;
          v16 = *(HSTRING *)(Microsoft::WRL::Wrappers::HStringReference::HStringReference(v42, &TokenHandle) + 24);
        }
        else
        {
LABEL_16:
          v16 = 0;
        }
        if ( (v9 & 1) != 0 )
          v43 = 0;
        WindowsDeleteString(string);
        string = 0;
        v17 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(&v44, &v37);
        if ( (int)DevPlat::Shared::StateRepository::GetPackageFullNameFromAppIdForUser(
                    v16,
                    (HSTRING)v17[1].Reserved.Reserved1,
                    (HSTRING)&string,
                    v18) >= 0 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          FindPackageStatusAndPackageOrigin(a3, StringRawBuffer, &v31, &v32);
        }
        pvData = 0;
        pcbData = 4;
        ValueW = RegGetValueW(
                   HKEY_LOCAL_MACHINE,
                   L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\RegisterPackageTimeoutMs",
                   L"SuppressRemediationUI",
                   0x10u,
                   0,
                   &pvData,
                   &pcbData);
        v11 = ValueW;
        if ( ValueW == 2 || !ValueW )
        {
          if ( pvData == 1 || (v6 & 2) != 0 )
            v13 = 0;
          v25[0] = v13;
          v34 = 0;
          v37 = WindowsGetStringRawBuffer(string, 0);
          v21 = Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,enum ACTIVATEOPTIONSINTERNAL &,enum _PackageOrigin &,unsigned short const *,unsigned int &,unsigned short const * &,unsigned __int64 &,IInspectable * &,enum ACTIVATION_PHASE &,bool const &>(
                  (int)&v34,
                  (int)&v36,
                  (int)&v32,
                  (int)&v37,
                  (__int64)&v31,
                  (__int64)&v40,
                  (__int64)&v39,
                  (__int64)&v38,
                  (__int64)va,
                  (__int64)v25);
          v11 = v21;
          if ( v21 >= 0 )
            v11 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, const WCHAR *, __int64))(*(_QWORD *)v28 + 32LL))(
                    v28,
                    a6,
                    a1,
                    (v34 + 8) & -(__int64)(v34 != 0));
          else
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x2EF,
              (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
              (const char *)(unsigned int)v21,
              ppvb);
          Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(&v34);
        }
        else if ( ValueW > 0 )
        {
          v11 = (unsigned __int16)ValueW | 0x80070000;
        }
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&StringSid);
        WindowsDeleteString(string);
        string = 0;
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B1,
          (unsigned int)"onecoreuap\\base\\appmodel\\execmodel\\modern\\activationmanager\\activationdeployment.cpp",
          (const char *)(unsigned int)v14,
          ppva);
      }
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v28);
      return v11;
    }
  }
  return a6;
}

```

## disassembly

```asm
0x1800803f4  push    rbp
0x1800803f6  push    rbx
0x1800803f7  push    rsi
0x1800803f8  push    rdi
0x1800803f9  push    r12
0x1800803fb  push    r13
0x1800803fd  push    r14
0x1800803ff  lea     rbp, [rsp-80h]
0x180080404  sub     rsp, 180h
0x18008040b  mov     rax, cs:__security_cookie
0x180080412  xor     rax, rsp
0x180080415  mov     [rbp+0B0h+var_40], rax
0x180080419  mov     r12d, r9d
0x18008041c  mov     rsi, r8
0x18008041f  mov     r13, rcx
0x180080422  mov     [rbp+0B0h+var_110], rcx
0x180080426  mov     [rbp+0B0h+var_F8], rdx
0x18008042a  mov     [rbp+0B0h+var_100], r8
0x18008042e  mov     [rbp+0B0h+var_118], r9d
0x180080432  mov     rax, [rbp+0B0h+arg_20]
0x180080439  mov     [rbp+0B0h+var_108], rax
0x18008043d  xor     r14d, r14d
0x180080440  mov     [rbp+0B0h+var_12C], r14d
0x180080444  test    r9d, 90001h
0x18008044b  jnz     loc_1800807E5
0x180080451  xorps   xmm0, xmm0
0x180080454  movups  [rbp+0B0h+Buf1], xmm0
0x180080458  lea     rdx, [rbp+0B0h+Buf1]
0x18008045c  mov     ecx, [rbp+0B0h+arg_28]
0x180080462  call    FindAppActivationFailedHandler
0x180080467  mov     ebx, eax
0x180080469  test    eax, eax
0x18008046b  jns     short loc_18008048F
0x18008046d  mov     rcx, [rbp+0B8h]; this
0x180080474  mov     r9d, eax; char *
0x180080477  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x18008047e  mov     edx, 2A4h; void *
0x180080483  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080488  mov     eax, ebx
0x18008048a  jmp     loc_1800807EB
0x18008048f  mov     r8d, 10h; Size
0x180080495  lea     rdx, GUID_NULL; Buf2
0x18008049c  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x1800804a0  call    memcmp_0
0x1800804a5  test    eax, eax
0x1800804a7  jz      loc_1800807E5
0x1800804ad  mov     [rsp+1B0h+var_148], r14
0x1800804b2  lea     rcx, [rsp+1B0h+var_148]
0x1800804b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800804bc  lea     rax, [rsp+1B0h+var_148]
0x1800804c1  mov     [rsp+1B0h+ppv], rax; ppv
0x1800804c6  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x1800804cd  xor     edx, edx; pUnkOuter
0x1800804cf  lea     r8d, [rdx+4]; dwClsContext
0x1800804d3  lea     rcx, [rbp+0B0h+Buf1]; rclsid
0x1800804d7  call    cs:__imp_CoCreateInstance
0x1800804dd  mov     edi, 1
0x1800804e2  test    eax, eax
0x1800804e4  jns     short loc_180080536
0x1800804e6  lea     rcx, [rsp+1B0h+var_148]
0x1800804eb  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800804f0  lea     rax, [rsp+1B0h+var_148]
0x1800804f5  mov     [rsp+1B0h+ppv], rax; int
0x1800804fa  lea     r9, _GUID_ba8e2d49_2e77_4442_bf1c_34c22bedf42e; riid
0x180080501  mov     r8d, edi; dwClsContext
0x180080504  xor     edx, edx; pUnkOuter
0x180080506  lea     rcx, [rbp+0B0h+Buf1]; rclsid
0x18008050a  call    cs:__imp_CoCreateInstance
0x180080510  mov     ebx, eax
0x180080512  test    eax, eax
0x180080514  jns     short loc_180080536
0x180080516  mov     rcx, [rbp+0B8h]; this
0x18008051d  mov     r9d, eax; char *
0x180080520  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180080527  mov     edx, 2B1h; void *
0x18008052c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080531  jmp     loc_1800807D6
0x180080536  mov     [rsp+1B0h+string], 0
0x18008053f  mov     [rsp+1B0h+var_134], 0
0x180080547  mov     [rbp+0B0h+var_130], 0
0x18008054e  mov     [rsp+1B0h+StringSid], 0
0x180080557  test    rsi, rsi
0x18008055a  jz      loc_18008061E
0x180080560  mov     [rsp+1B0h+TokenHandle], 0
0x180080569  xor     edx, edx
0x18008056b  lea     rcx, [rsp+1B0h+TokenHandle]
0x180080570  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180080575  lea     rdx, [rsp+1B0h+TokenHandle]
0x18008057a  mov     rcx, rsi
0x18008057d  call    cs:__imp_UMgrQueryUserToken
0x180080583  test    eax, eax
0x180080585  js      short loc_1800805EE
0x180080587  mov     ebx, 54h ; 'T'
0x18008058c  mov     r8d, ebx; Size
0x18008058f  xor     edx, edx; Val
0x180080591  lea     rcx, [rbp+0B0h+TokenInformation]; void *
0x180080595  call    memset_0
0x18008059a  mov     [rbp+0B0h+ReturnLength], 0
0x1800805a1  lea     rax, [rbp+0B0h+ReturnLength]
0x1800805a5  mov     [rsp+1B0h+ppv], rax; ReturnLength
0x1800805aa  mov     r9d, ebx; TokenInformationLength
0x1800805ad  lea     r8, [rbp+0B0h+TokenInformation]; TokenInformation
0x1800805b1  mov     edx, edi; TokenInformationClass
0x1800805b3  mov     rcx, [rsp+1B0h+TokenHandle]; TokenHandle
0x1800805b8  call    cs:__imp_GetTokenInformation
0x1800805be  test    eax, eax
0x1800805c0  jz      short loc_1800805EE
0x1800805c2  mov     rbx, [rbp+0B0h+TokenInformation]
0x1800805c6  xor     edx, edx
0x1800805c8  lea     rcx, [rsp+1B0h+StringSid]
0x1800805cd  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800805d2  lea     rdx, [rsp+1B0h+StringSid]; StringSid
0x1800805d7  mov     rcx, rbx; Sid
0x1800805da  call    cs:__imp_ConvertSidToStringSidW
0x1800805e0  test    eax, eax
0x1800805e2  jnz     short loc_1800805EE
0x1800805e4  lea     rcx, [rsp+1B0h+StringSid]
0x1800805e9  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$T@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(std::nullptr_t)
0x1800805ee  lea     rcx, [rsp+1B0h+TokenHandle]
0x1800805f3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800805f8  mov     rax, [rsp+1B0h+StringSid]
0x1800805fd  test    rax, rax
0x180080600  jz      short loc_18008061E
0x180080602  mov     [rsp+1B0h+TokenHandle], rax
0x180080607  lea     rdx, [rsp+1B0h+TokenHandle]
0x18008060c  lea     rcx, [rbp+0B0h+var_E0]
0x180080610  call    ??$?0PEAG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEAGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort * const &,Microsoft::WRL::Details::Dummy)
0x180080615  mov     r14d, edi
0x180080618  mov     rbx, [rax+18h]
0x18008061c  jmp     short loc_180080620
0x18008061e  xor     ebx, ebx
0x180080620  test    dil, r14b
0x180080623  jz      short loc_18008062E
0x180080625  xor     r14d, r14d
0x180080628  mov     [rbp+0B0h+var_C8], r14
0x18008062c  jmp     short loc_180080631
0x18008062e  xor     r14d, r14d
0x180080631  mov     rcx, [rsp+1B0h+string]; string
0x180080636  call    cs:__imp_WindowsDeleteString
0x18008063c  mov     [rsp+1B0h+string], r14
0x180080641  lea     rdx, [rbp+0B0h+var_110]
0x180080645  lea     rcx, [rbp+0B0h+var_C0]
0x180080649  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18008064e  lea     r8, [rsp+1B0h+string]; HSTRING
0x180080653  mov     rdx, [rax+18h]; HSTRING
0x180080657  mov     rcx, rbx; string
0x18008065a  call    ?GetPackageFullNameFromAppIdForUser@StateRepository@Shared@DevPlat@@YAJPEAUHSTRING__@@0PEAPEAU4@@Z; DevPlat::Shared::StateRepository::GetPackageFullNameFromAppIdForUser(HSTRING__ *,HSTRING__ *,HSTRING__ * *)
0x18008065f  test    eax, eax
0x180080661  js      short loc_180080684
0x180080663  xor     edx, edx; length
0x180080665  mov     rcx, [rsp+1B0h+string]; string
0x18008066a  call    cs:__imp_WindowsGetStringRawBuffer
0x180080670  lea     r9, [rbp+0B0h+var_130]
0x180080674  lea     r8, [rsp+1B0h+var_134]
0x180080679  mov     rdx, rax
0x18008067c  mov     rcx, rsi
0x18008067f  call    FindPackageStatusAndPackageOrigin
0x180080684  mov     [rsp+1B0h+var_138], r14d
0x180080689  mov     [rbp+0B0h+var_12C], 4
0x180080690  lea     rax, [rbp+0B0h+var_12C]
0x180080694  mov     [rsp+1B0h+pcbData], rax; pcbData
0x180080699  lea     rax, [rsp+1B0h+var_138]
0x18008069e  mov     [rsp+1B0h+pvData], rax; pvData
0x1800806a3  mov     [rsp+1B0h+ppv], r14; pdwType
0x1800806a8  mov     r9d, 10h; dwFlags
0x1800806ae  lea     r8, aSuppressremedi; "SuppressRemediationUI"
0x1800806b5  lea     rdx, aSoftwareMicros_5; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800806bc  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1800806c3  call    cs:__imp_RegGetValueW
0x1800806c9  mov     ebx, eax
0x1800806cb  cmp     eax, 2
0x1800806ce  jz      short loc_1800806E8
0x1800806d0  test    eax, eax
0x1800806d2  jz      short loc_1800806E8
0x1800806d4  jle     loc_1800807BB
0x1800806da  movzx   ebx, ax
0x1800806dd  or      ebx, 80070000h
0x1800806e3  jmp     loc_1800807BB
0x1800806e8  cmp     [rsp+1B0h+var_138], edi
0x1800806ec  jz      short loc_1800806F4
0x1800806ee  test    r12b, 2
0x1800806f2  jz      short loc_1800806F7
0x1800806f4  mov     dil, r14b
0x1800806f7  mov     [rsp+1B0h+var_160], dil
0x1800806fc  mov     [rbp+0B0h+var_128], r14
0x180080700  xor     edx, edx; length
0x180080702  mov     rcx, [rsp+1B0h+string]; string
0x180080707  call    cs:__imp_WindowsGetStringRawBuffer
0x18008070d  mov     [rbp+0B0h+var_110], rax
0x180080711  lea     rax, [rsp+1B0h+var_160]
0x180080716  mov     [rsp+1B0h+var_168], rax
0x18008071b  lea     rax, [rbp+0B0h+arg_30]
0x180080722  mov     [rsp+1B0h+var_170], rax
0x180080727  lea     rax, [rbp+0B0h+var_108]
0x18008072b  mov     [rsp+1B0h+var_178], rax
0x180080730  lea     rax, [rbp+0B0h+var_100]
0x180080734  mov     [rsp+1B0h+pcbData], rax
0x180080739  lea     rax, [rbp+0B0h+var_F8]
0x18008073d  mov     [rsp+1B0h+pvData], rax
0x180080742  lea     rax, [rsp+1B0h+var_134]
0x180080747  mov     [rsp+1B0h+ppv], rax; int
0x18008074c  lea     r9, [rbp+0B0h+var_110]
0x180080750  lea     r8, [rbp+0B0h+var_130]
0x180080754  lea     rdx, [rbp+0B0h+var_118]
0x180080758  lea     rcx, [rbp+0B0h+var_128]
0x18008075c  call    ??$MakeAndInitialize@VAppActivationRemediationInfo@@V1@AEAW4ACTIVATEOPTIONSINTERNAL@@AEAW4_PackageOrigin@@PEBGAEAIAEAPEBGAEA_KAEAPEAUIInspectable@@AEAW4ACTIVATION_PHASE@@AEB_N@Details@WRL@Microsoft@@YAJV?$ComPtrRef@V?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@@012@AEAW4ACTIVATEOPTIONSINTERNAL@@AEAW4_PackageOrigin@@$$QEAPEBGAEAIAEAPEBGAEA_KAEAPEAUIInspectable@@AEAW4ACTIVATION_PHASE@@AEB_N@Z; Microsoft::WRL::Details::MakeAndInitialize<AppActivationRemediationInfo,AppActivationRemediationInfo,ACTIVATEOPTIONSINTERNAL &,_PackageOrigin &,ushort const *,uint &,ushort const * &,unsigned __int64 &,IInspectable * &,ACTIVATION_PHASE &,bool const &>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<AppActivationRemediationInfo>>,ACTIVATEOPTIONSINTERNAL &,_PackageOrigin &,ushort const * &&,uint &,ushort const * &,unsigned __int64 &,IInspectable * &,ACTIVATION_PHASE &,bool const &)
0x180080761  mov     ebx, eax
0x180080763  test    eax, eax
0x180080765  jns     short loc_180080784
0x180080767  mov     rcx, [rbp+0B8h]; this
0x18008076e  mov     r9d, eax; char *
0x180080771  lea     r8, aOnecoreuapBase_31; "onecoreuap\\base\\appmodel\\execmodel\\"...
0x180080778  mov     edx, 2EFh; void *
0x18008077d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180080782  jmp     short loc_1800807B1
0x180080784  mov     rcx, [rsp+1B0h+var_148]
0x180080789  mov     r9, [rbp+0B0h+var_128]
0x18008078d  mov     r10, [rcx]
0x180080790  lea     rax, [r9+8]
0x180080794  neg     r9
0x180080797  sbb     r9, r9
0x18008079a  and     r9, rax
0x18008079d  mov     r8, r13
0x1800807a0  mov     edx, [rbp+0B0h+arg_28]
0x1800807a6  mov     rax, [r10+20h]
0x1800807aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800807af  mov     ebx, eax
0x1800807b1  lea     rcx, [rbp+0B0h+var_128]
0x1800807b5  call    ?InternalRelease@?$ComPtr@VAppActivationRemediationInfo@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<AppActivationRemediationInfo>::InternalRelease(void)
0x1800807ba  nop
0x1800807bb  lea     rcx, [rsp+1B0h+StringSid]
0x1800807c0  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800807c5  nop
0x1800807c6  mov     rcx, [rsp+1B0h+string]; string
0x1800807cb  call    cs:__imp_WindowsDeleteString
0x1800807d1  mov     [rsp+1B0h+string], r14
0x1800807d6  lea     rcx, [rsp+1B0h+var_148]
0x1800807db  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800807e0  jmp     loc_180080488
0x1800807e5  mov     eax, [rbp+0B0h+arg_28]
0x1800807eb  mov     rcx, [rbp+0B0h+var_40]
0x1800807ef  xor     rcx, rsp; StackCookie
0x1800807f2  call    __security_check_cookie
0x1800807f7  add     rsp, 180h
0x1800807fe  pop     r14
0x180080800  pop     r13
0x180080802  pop     r12
0x180080804  pop     rdi
0x180080805  pop     rsi
0x180080806  pop     rbx
0x180080807  pop     rbp
0x180080808  retn
```
