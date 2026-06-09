# _lambda_00ef9e7755dbedf78ac1bb14d30c4fbe_::operator()

- ea: `0x180022660`
- end: `0x18002291b`
- name: `_lambda_00ef9e7755dbedf78ac1bb14d30c4fbe_::operator()`
- size: `699`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025300`

## callees

- `0x180002a3c`
- `0x180008344`
- `0x18000e6f4`
- `0x180012408`
- `0x18001dc6c`
- `0x1800225c4`
- `0x180022660`
- `0x180026f34`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800227c4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180022747`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180022774`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800227d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800227d9`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180022884`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x180022884`
- `credui!CredPackAuthenticationBufferW` at `0x18002279e`
- `credui!CredPackAuthenticationBufferW` at `0x180022832`
- `credui!CredPackAuthenticationBufferW` at `0x18002279e`
- `credui!CredPackAuthenticationBufferW` at `0x180022832`

## string_xrefs

- `0x1800226d9`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022723`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800227ad`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800227f8`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022840`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180022897`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall lambda_00ef9e7755dbedf78ac1bb14d30c4fbe_::operator()(__int64 a1, __int64 a2)
{
  int ElevatedObject; // eax
  unsigned int LastError; // ebx
  __int64 v5; // rdx
  int v6; // eax
  __int64 v7; // rdx
  WCHAR *StringRawBuffer; // rsi
  const char *v9; // r9
  __int64 v10; // rdx
  BYTE *v11; // rbx
  __int64 v12; // r9
  __int64 v13; // rdx
  const char *v14; // r9
  HRESULT v15; // eax
  HRESULT v16; // esi
  int v17; // eax
  int pcbPackedCredentials; // [rsp+20h] [rbp-30h]
  int pcbPackedCredentialsa; // [rsp+20h] [rbp-30h]
  _QWORD v21[2]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  __int64 v23; // [rsp+78h] [rbp+28h] BYREF
  HSTRING string; // [rsp+80h] [rbp+30h] BYREF
  IUnknown *pProxy; // [rsp+88h] [rbp+38h] BYREF

  v23 = a2;
  pProxy = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  ElevatedObject = CloudExperienceHostCreateElevatedObject(
                     &GUID_54337179_c8b2_4ed4_95e4_95601c850d8c,
                     &GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c,
                     (void **)&pProxy);
  LastError = ElevatedObject;
  if ( ElevatedObject >= 0 )
  {
    if ( !*(_DWORD *)(a1 + 8) )
    {
      ElevatedObject = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD))pProxy->lpVtbl[1].AddRef)(pProxy, 0, 0);
      LastError = ElevatedObject;
      if ( ElevatedObject < 0 )
      {
        v5 = 198;
        goto LABEL_6;
      }
LABEL_31:
      LastError = 0;
      goto LABEL_32;
    }
    string = 0;
    if ( !*(_QWORD *)a1 )
    {
      v6 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, _QWORD))pProxy->lpVtbl[1].AddRef)(pProxy, 0, 0);
      LastError = v6;
      if ( v6 < 0 )
      {
        v7 = 205;
LABEL_10:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v7,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
          (const char *)(unsigned int)v6,
          pcbPackedCredentials);
LABEL_11:
        SecureZeroHString::~SecureZeroHString((SecureZeroHString *)&string);
        goto LABEL_32;
      }
LABEL_30:
      SecureZeroHString::~SecureZeroHString((SecureZeroHString *)&string);
      goto LABEL_31;
    }
    WindowsDeleteString(0);
    string = 0;
    v6 = CloudExperienceHostBroker::Account::LocalAccountManager::s_DecryptPassword(
           *(struct Windows::Storage::Streams::IBuffer **)a1,
           &string);
    LastError = v6;
    if ( v6 < 0 )
    {
      v7 = 209;
      goto LABEL_10;
    }
    StringRawBuffer = (WCHAR *)WindowsGetStringRawBuffer(string, 0);
    LODWORD(v23) = 0;
    if ( CredPackAuthenticationBufferW(1u, (LPWSTR)L"RetailUserName", StringRawBuffer, 0, (DWORD *)&v23) )
    {
      v10 = 215;
LABEL_16:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v10,
                    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                    v9);
      goto LABEL_11;
    }
    if ( GetLastError() != 122 )
    {
      v10 = 216;
      goto LABEL_16;
    }
    v11 = (BYTE *)CoTaskMemAlloc((unsigned int)v23);
    v21[0] = v11;
    if ( v11 )
    {
      if ( !CredPackAuthenticationBufferW(1u, (LPWSTR)L"RetailUserName", StringRawBuffer, v11, (DWORD *)&v23) )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xDC,
                      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
                      v14);
        goto LABEL_22;
      }
      v15 = CoSetProxyBlanket(pProxy, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x40u);
      v16 = v15;
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xE0,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
          (const char *)(unsigned int)v15,
          pcbPackedCredentialsa);
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v21);
        SecureZeroHString::~SecureZeroHString((SecureZeroHString *)&string);
        LastError = v16;
        goto LABEL_32;
      }
      v17 = ((__int64 (__fastcall *)(IUnknown *, BYTE *, _QWORD, _QWORD))pProxy->lpVtbl[1].AddRef)(
              pProxy,
              v11,
              (unsigned int)v23,
              *(unsigned int *)(a1 + 8));
      LastError = v17;
      if ( v17 >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v21);
        goto LABEL_30;
      }
      v12 = (unsigned int)v17;
      v13 = 225;
    }
    else
    {
      LastError = -2147024882;
      v12 = 2147942414LL;
      v13 = 218;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
      (const char *)v12,
      pcbPackedCredentialsa);
LABEL_22:
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(v21);
    goto LABEL_11;
  }
  v5 = 194;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v5,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
    (const char *)(unsigned int)ElevatedObject,
    pcbPackedCredentials);
LABEL_32:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&pProxy);
  return LastError;
}

```

## disassembly

```asm
0x180022660  mov     [rsp-18h+arg_0], rbx
0x180022665  mov     [rsp-18h+arg_8], rdx
0x18002266a  push    rbp
0x18002266b  push    rsi
0x18002266c  push    rdi
0x18002266d  mov     rbp, rsp
0x180022670  sub     rsp, 50h
0x180022674  mov     rdi, rcx
0x180022677  mov     [rbp+pProxy], 0
0x18002267f  lea     rcx, [rbp+pProxy]
0x180022683  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180022688  lea     r8, [rbp+pProxy]; void **
0x18002268c  lea     rdx, _GUID_30e038f9_64c9_4a5c_ba4c_f9f7df30849c; struct _GUID *
0x180022693  lea     rcx, _GUID_54337179_c8b2_4ed4_95e4_95601c850d8c; struct _GUID *
0x18002269a  call    ?CloudExperienceHostCreateElevatedObject@@YAJAEBU_GUID@@0PEAPEAX@Z; CloudExperienceHostCreateElevatedObject(_GUID const &,_GUID const &,void * *)
0x18002269f  mov     ebx, eax
0x1800226a1  test    eax, eax
0x1800226a3  jns     short loc_1800226AC
0x1800226a5  mov     edx, 0C2h
0x1800226aa  jmp     short loc_1800226D9
0x1800226ac  mov     r9d, [rdi+8]
0x1800226b0  test    r9d, r9d
0x1800226b3  jnz     short loc_1800226F1
0x1800226b5  mov     rcx, [rbp+pProxy]
0x1800226b9  mov     rax, [rcx]
0x1800226bc  xor     r8d, r8d
0x1800226bf  xor     edx, edx
0x1800226c1  mov     rax, [rax+20h]
0x1800226c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800226ca  mov     ebx, eax
0x1800226cc  test    eax, eax
0x1800226ce  jns     loc_180022901
0x1800226d4  mov     edx, 0C6h; void *
0x1800226d9  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800226e0  mov     r9d, eax; char *
0x1800226e3  mov     rcx, [rbp+18h]; this
0x1800226e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800226ec  jmp     loc_180022903
0x1800226f1  mov     [rbp+string], 0
0x1800226f9  cmp     qword ptr [rdi], 0
0x1800226fd  jnz     short loc_180022745
0x1800226ff  mov     rcx, [rbp+pProxy]
0x180022703  mov     rax, [rcx]
0x180022706  xor     r8d, r8d
0x180022709  xor     edx, edx
0x18002270b  mov     rax, [rax+20h]
0x18002270f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022714  mov     ebx, eax
0x180022716  test    eax, eax
0x180022718  jns     loc_1800228F8
0x18002271e  mov     edx, 0CDh; void *
0x180022723  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002272a  mov     r9d, eax; char *
0x18002272d  mov     rcx, [rbp+18h]; this
0x180022731  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022736  nop
0x180022737  lea     rcx, [rbp+string]; this
0x18002273b  call    ??1SecureZeroHString@@QEAA@XZ; SecureZeroHString::~SecureZeroHString(void)
0x180022740  jmp     loc_180022903
0x180022745  xor     ecx, ecx; string
0x180022747  call    cs:__imp_WindowsDeleteString
0x18002274d  mov     [rbp+string], 0
0x180022755  lea     rdx, [rbp+string]; HSTRING *
0x180022759  mov     rcx, [rdi]; struct Windows::Storage::Streams::IBuffer *
0x18002275c  call    ?s_DecryptPassword@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUIBuffer@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_DecryptPassword(Windows::Storage::Streams::IBuffer *,HSTRING__ * *)
0x180022761  mov     ebx, eax
0x180022763  test    eax, eax
0x180022765  jns     short loc_18002276E
0x180022767  mov     edx, 0D1h
0x18002276c  jmp     short loc_180022723
0x18002276e  xor     edx, edx; length
0x180022770  mov     rcx, [rbp+string]; string
0x180022774  call    cs:__imp_WindowsGetStringRawBuffer
0x18002277a  mov     rsi, rax
0x18002277d  mov     dword ptr [rbp+arg_8], 0
0x180022784  lea     rax, [rbp+arg_8]
0x180022788  mov     [rsp+50h+pcbPackedCredentials], rax; int
0x18002278d  xor     r9d, r9d; pPackedCredentials
0x180022790  mov     r8, rsi; pszPassword
0x180022793  lea     rdx, pszUserName; "RetailUserName"
0x18002279a  lea     ecx, [r9+1]; dwFlags
0x18002279e  call    cs:__imp_CredPackAuthenticationBufferW
0x1800227a4  test    eax, eax
0x1800227a6  jz      short loc_1800227C4
0x1800227a8  mov     edx, 0D7h; void *
0x1800227ad  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800227b4  mov     rcx, [rbp+18h]; this
0x1800227b8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800227bd  mov     ebx, eax
0x1800227bf  jmp     loc_180022737
0x1800227c4  call    cs:__imp_GetLastError
0x1800227ca  cmp     eax, 7Ah ; 'z'
0x1800227cd  jz      short loc_1800227D6
0x1800227cf  mov     edx, 0D8h
0x1800227d4  jmp     short loc_1800227AD
0x1800227d6  mov     ecx, dword ptr [rbp+arg_8]; cb
0x1800227d9  call    cs:__imp_CoTaskMemAlloc
0x1800227df  mov     rbx, rax
0x1800227e2  mov     [rbp+var_10], rax
0x1800227e6  test    rax, rax
0x1800227e9  jnz     short loc_180022817
0x1800227eb  mov     ebx, 8007000Eh
0x1800227f0  mov     r9d, ebx; char *
0x1800227f3  mov     edx, 0DAh; void *
0x1800227f8  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800227ff  mov     rcx, [rbp+18h]; this
0x180022803  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022808  nop
0x180022809  lea     rcx, [rbp+var_10]
0x18002280d  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180022812  jmp     loc_180022737
0x180022817  lea     rax, [rbp+arg_8]
0x18002281b  mov     [rsp+50h+pcbPackedCredentials], rax; pcbPackedCredentials
0x180022820  mov     r9, rbx; pPackedCredentials
0x180022823  mov     r8, rsi; pszPassword
0x180022826  lea     rdx, pszUserName; "RetailUserName"
0x18002282d  mov     ecx, 1; dwFlags
0x180022832  call    cs:__imp_CredPackAuthenticationBufferW
0x180022838  test    eax, eax
0x18002283a  jnz     short loc_180022855
0x18002283c  mov     rcx, [rbp+18h]; this
0x180022840  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180022847  mov     edx, 0DCh; void *
0x18002284c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180022851  mov     ebx, eax
0x180022853  jmp     short loc_180022809
0x180022855  mov     [rsp+50h+dwCapabilities], 40h ; '@'; dwCapabilities
0x18002285d  mov     [rsp+50h+pAuthInfo], 0; pAuthInfo
0x180022866  mov     [rsp+50h+dwImpLevel], 3; dwImpLevel
0x18002286e  mov     dword ptr [rsp+50h+pcbPackedCredentials], 0; int
0x180022876  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18002287a  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18002287d  mov     r8d, edx; dwAuthzSvc
0x180022880  mov     rcx, [rbp+pProxy]; pProxy
0x180022884  call    cs:__imp_CoSetProxyBlanket
0x18002288a  mov     esi, eax
0x18002288c  test    eax, eax
0x18002288e  jns     short loc_1800228C0
0x180022890  mov     rcx, [rbp+18h]; this
0x180022894  mov     r9d, eax; char *
0x180022897  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x18002289e  mov     edx, 0E0h; void *
0x1800228a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800228a8  nop
0x1800228a9  lea     rcx, [rbp+var_10]
0x1800228ad  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800228b2  nop
0x1800228b3  lea     rcx, [rbp+string]; this
0x1800228b7  call    ??1SecureZeroHString@@QEAA@XZ; SecureZeroHString::~SecureZeroHString(void)
0x1800228bc  mov     ebx, esi
0x1800228be  jmp     short loc_180022903
0x1800228c0  mov     rcx, [rbp+pProxy]
0x1800228c4  mov     rax, [rcx]
0x1800228c7  mov     r9d, [rdi+8]
0x1800228cb  mov     r8d, dword ptr [rbp+arg_8]
0x1800228cf  mov     rdx, rbx
0x1800228d2  mov     rax, [rax+20h]
0x1800228d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800228db  mov     ebx, eax
0x1800228dd  test    eax, eax
0x1800228df  jns     short loc_1800228EE
0x1800228e1  mov     r9d, eax
0x1800228e4  mov     edx, 0E1h
0x1800228e9  jmp     loc_1800227F8
0x1800228ee  lea     rcx, [rbp+var_10]
0x1800228f2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800228f7  nop
0x1800228f8  lea     rcx, [rbp+string]; this
0x1800228fc  call    ??1SecureZeroHString@@QEAA@XZ; SecureZeroHString::~SecureZeroHString(void)
0x180022901  xor     ebx, ebx
0x180022903  lea     rcx, [rbp+pProxy]
0x180022907  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002290c  mov     eax, ebx
0x18002290e  mov     rbx, [rsp+50h+arg_0]
0x180022913  add     rsp, 50h
0x180022917  pop     rdi
0x180022918  pop     rsi
0x180022919  pop     rbp
0x18002291a  retn
```
