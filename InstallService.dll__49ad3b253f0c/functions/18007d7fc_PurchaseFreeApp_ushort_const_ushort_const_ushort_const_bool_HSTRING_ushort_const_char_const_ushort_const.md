# PurchaseFreeApp(ushort const *,ushort const *,ushort const *,bool,HSTRING__ *,ushort const *,char const *,ushort const *)

- ea: `0x18007d7fc`
- end: `0x18007dcf7`
- name: `?PurchaseFreeApp@@YAJPEBG00_NPEAUHSTRING__@@0PEBD0@Z`
- size: `1275`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, bool@<r9b>, HSTRING, const unsigned __int16 *, const char *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `17`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800267f0`
- `0x1800fbd44`
- `0x1800fbe84`
- `0x1801d66e4`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x1800127c8`
- `0x18001c844`
- `0x180022374`
- `0x1800252e8`
- `0x18002548c`
- `0x18003f884`
- `0x18007c818`
- `0x18007ca8c`
- `0x18007d288`
- `0x18007d57c`
- `0x18007d7fc`
- `0x18011b84c`
- `0x1801ed1a8`
- `0x1801f7954`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d893`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d89f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d8ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007d992`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da33`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da3e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007da55`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dbd8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dc84`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007dcc5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dc46`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007dc46`

## string_xrefs

- `0x18007d91d`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007d966`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007d9c8`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007da12`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007db9f`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007dc2d`: `onecoreuap\enduser\winstore\installservice\lib\purchase.cpp`
- `0x18007d90a`: `WinStoreAuth::GetTicketsForAccount(accountId.Get(), providerId.Get(), authority.Get(), &tickets, spWebTokenRequestResult.GetAddressOf())`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
__int64 __fastcall PurchaseFreeApp(
        const unsigned __int16 *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        bool a4,
        HSTRING a5,
        unsigned __int16 *a6,
        char *a7,
        unsigned __int16 *a8)
{
  unsigned __int16 *v10; // rdi
  TraceLoggingCorrelationVector *v11; // rax
  struct TraceLoggingCorrelationVector *v12; // rsi
  char v13; // r14
  int AuthTicket; // ebx
  __int64 v15; // rcx
  int TicketsForAccountForUser; // eax
  int v17; // eax
  HSTRING v18; // rdi
  __int64 (__fastcall *v19)(HSTRING, _QWORD, HSTRING *); // rbx
  int v20; // eax
  int v21; // eax
  struct Windows::Data::Json::IJsonObject *v22; // rdi
  __int64 (__fastcall *v23)(struct Windows::Data::Json::IJsonObject *, __int64, _BYTE *); // rbx
  int v24; // eax
  struct Windows::Data::Json::IJsonObject *v25; // rdi
  __int64 (__fastcall *v26)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *); // rbx
  int v27; // eax
  const wchar_t *StringRawBuffer; // rax
  int v30; // [rsp+28h] [rbp-A1h]
  int v31; // [rsp+28h] [rbp-A1h]
  int v32; // [rsp+28h] [rbp-A1h]
  int v33; // [rsp+28h] [rbp-A1h]
  _BYTE v34[8]; // [rsp+40h] [rbp-89h] BYREF
  HSTRING v35; // [rsp+48h] [rbp-81h] BYREF
  struct Windows::Data::Json::IJsonObject *v36; // [rsp+50h] [rbp-79h] BYREF
  HSTRING string; // [rsp+58h] [rbp-71h] BYREF
  struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *v38; // [rsp+60h] [rbp-69h] BYREF
  HSTRING v39; // [rsp+68h] [rbp-61h] BYREF
  HSTRING v40; // [rsp+70h] [rbp-59h] BYREF
  HSTRING v41; // [rsp+78h] [rbp-51h] BYREF
  unsigned __int16 *v42; // [rsp+80h] [rbp-49h]
  TraceLoggingCorrelationVector *v43; // [rsp+88h] [rbp-41h] BYREF
  unsigned __int16 *v44; // [rsp+90h] [rbp-39h]
  unsigned __int16 *v45; // [rsp+98h] [rbp-31h]
  unsigned __int16 *v46; // [rsp+A0h] [rbp-29h]
  HSTRING_HEADER hstringHeader; // [rsp+A8h] [rbp-21h] BYREF
  __int64 v48; // [rsp+C0h] [rbp-9h]

  v45 = a3;
  v46 = a2;
  v10 = a6;
  v42 = a6;
  v44 = a8;
  string = 0;
  v11 = TraceLoggingCorrelationVector::Extend(a7, 1);
  v12 = v11;
  v43 = v11;
  if ( v11 )
  {
    TraceLoggingCorrelationVector::Increment(v11, 0);
    v13 = 0;
    while ( 1 )
    {
      v38 = 0;
      if ( a4 || !a5 )
      {
        WindowsDeleteString(string);
        string = 0;
        AuthTicket = GetAuthTicket(a4, &string, &v38);
      }
      else
      {
        v35 = 0;
        WindowsDeleteString(0);
        v39 = 0;
        WindowsDeleteString(0);
        v40 = 0;
        WindowsDeleteString(0);
        v41 = 0;
        AuthTicket = ParseIdentityData(a5, &v41, &v40, &v39, 0);
        if ( AuthTicket >= 0 )
        {
          Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
          TicketsForAccountForUser = GetTicketsForAccountForUser(v15, v41, v40, v39, &v35);
          AuthTicket = TraceHR(
                         "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                         0x16Fu,
                         "PurchaseFreeApp",
                         "WinStoreAuth::GetTicketsForAccount(accountId.Get(), providerId.Get(), authority.Get(), &tickets"
                         ", spWebTokenRequestResult.GetAddressOf())",
                         TicketsForAccountForUser,
                         (int)&v38);
          if ( AuthTicket >= 0 )
          {
            LODWORD(v36) = 0;
            v17 = (*(__int64 (__fastcall **)(HSTRING, struct Windows::Data::Json::IJsonObject **))(*(_QWORD *)v35 + 56LL))(
                    v35,
                    &v36);
            AuthTicket = TraceHR(
                           "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                           0x173u,
                           "PurchaseFreeApp",
                           "tickets->get_Size(&ticketCount)",
                           v17,
                           v30);
            if ( AuthTicket >= 0 )
            {
              if ( (_DWORD)v36 )
              {
                v18 = v35;
                v19 = *(__int64 (__fastcall **)(HSTRING, _QWORD, HSTRING *))(*(_QWORD *)v35 + 48LL);
                WindowsDeleteString(string);
                string = 0;
                v20 = v19(v18, 0, &string);
                AuthTicket = TraceHR(
                               "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                               0x178u,
                               "PurchaseFreeApp",
                               "tickets->GetAt(0, authTicket.GetAddressOf())",
                               v20,
                               v31);
                v10 = v42;
              }
              else
              {
                AuthTicket = -2147467259;
                LogSimpleMessage(
                  1u,
                  "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                  0x17Du,
                  "PurchaseFreeApp",
                  -2147467259,
                  L"Failed to obtain user tickets.",
                  0,
                  0);
              }
            }
          }
        }
        WindowsDeleteString(v39);
        WindowsDeleteString(v40);
        WindowsDeleteString(v41);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
      }
      if ( AuthTicket < 0 )
        break;
      v36 = 0;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
      v21 = CreatePurchaseOrder(string, a1, v46, v45, v10, v12, v44, &v36);
      AuthTicket = v21;
      if ( v21 != -2147023728 )
      {
        if ( v21 >= 0 )
        {
          v34[0] = 0;
          v22 = v36;
          v23 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, _BYTE *))(*(_QWORD *)v36 + 96LL);
          v48 = 0;
          Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"isPIRequired", 0xDu, 0xCu);
          v24 = v23(v22, v48, v34);
          AuthTicket = TraceHR(
                         "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                         0x19Du,
                         "PurchaseFreeApp",
                         "spOrder->GetNamedBoolean(HStringReference(L\"isPIRequired\").Get(), &piRequired)",
                         v24,
                         v32);
          if ( AuthTicket >= 0 )
          {
            if ( v34[0] )
            {
              AuthTicket = -2147024891;
            }
            else
            {
              v35 = 0;
              v25 = v36;
              v26 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonObject *, __int64, HSTRING *))(*(_QWORD *)v36 + 80LL);
              WindowsDeleteString(0);
              v35 = 0;
              v48 = 0;
              Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"orderState", 0xBu, 0xAu);
              v27 = v26(v25, v48, &v35);
              AuthTicket = TraceHR(
                             "onecoreuap\\enduser\\winstore\\installservice\\lib\\purchase.cpp",
                             0x1A9u,
                             "PurchaseFreeApp",
                             "spOrder->GetNamedString(HStringReference(L\"orderState\").Get(), strOrderState.GetAddressOf())",
                             v27,
                             v33);
              if ( AuthTicket < 0
                || (StringRawBuffer = WindowsGetStringRawBuffer(v35, 0)) == 0
                || wcscmp_0(StringRawBuffer, L"Purchased") )
              {
                AuthTicket = CompletePurchaseOrder(a1, string, v36, v42, v12);
              }
              WindowsDeleteString(v35);
            }
          }
        }
        goto LABEL_30;
      }
      if ( v13 || !v38 )
        goto LABEL_30;
      v35 = 0;
      if ( (*(int (__fastcall **)(struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult *, HSTRING *))(*(_QWORD *)v38 + 72LL))(
             v38,
             &v35) < 0
        || (int)WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(v35) < 0 )
      {
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
LABEL_30:
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
        break;
      }
      v13 = 1;
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v38);
    std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(&v43);
    WindowsDeleteString(string);
    return (unsigned int)AuthTicket;
  }
  else
  {
    std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(&v43);
    WindowsDeleteString(string);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18007d7fc  mov     [rsp-8+arg_18], rbx
0x18007d801  push    rbp
0x18007d802  push    rsi
0x18007d803  push    rdi
0x18007d804  push    r12
0x18007d806  push    r13
0x18007d808  push    r14
0x18007d80a  push    r15
0x18007d80c  lea     rbp, [rsp-7]
0x18007d811  sub     rsp, 0D0h
0x18007d818  mov     rax, cs:__security_cookie
0x18007d81f  xor     rax, rsp
0x18007d822  mov     [rbp+37h+var_38], rax
0x18007d826  mov     r15b, r9b
0x18007d829  mov     [rbp+37h+var_68], r8
0x18007d82d  mov     [rbp+37h+var_60], rdx
0x18007d831  mov     r13, rcx
0x18007d834  mov     r12, [rbp+37h+arg_20]
0x18007d838  mov     rdi, [rbp+37h+arg_28]
0x18007d83c  mov     [rbp+37h+var_80], rdi
0x18007d840  mov     rcx, [rbp+37h+arg_30]; char *
0x18007d844  mov     rax, [rbp+37h+arg_38]
0x18007d848  mov     [rbp+37h+var_70], rax
0x18007d84c  xor     ebx, ebx
0x18007d84e  mov     [rbp+37h+string], rbx
0x18007d852  mov     dl, 1; bool
0x18007d854  call    ?Extend@TraceLoggingCorrelationVector@@SAPEAV1@PEBD_N@Z; TraceLoggingCorrelationVector::Extend(char const *,bool)
0x18007d859  mov     rsi, rax
0x18007d85c  mov     [rbp+37h+var_78], rax
0x18007d860  test    rax, rax
0x18007d863  jz      loc_18007DCB7
0x18007d869  xor     edx, edx; char *
0x18007d86b  mov     rcx, rax; this
0x18007d86e  call    ?Increment@TraceLoggingCorrelationVector@@QEAA_NPEAD@Z; TraceLoggingCorrelationVector::Increment(char *)
0x18007d873  mov     r14b, bl
0x18007d876  mov     [rbp+37h+var_A0], rbx
0x18007d87a  test    r15b, r15b
0x18007d87d  jnz     loc_18007DA51
0x18007d883  test    r12, r12
0x18007d886  jz      loc_18007DA51
0x18007d88c  mov     [rsp+100h+var_B8], rbx
0x18007d891  xor     ecx, ecx; string
0x18007d893  call    cs:__imp_WindowsDeleteString
0x18007d899  mov     [rbp+37h+var_98], rbx
0x18007d89d  xor     ecx, ecx; string
0x18007d89f  call    cs:__imp_WindowsDeleteString
0x18007d8a5  mov     [rbp+37h+var_90], rbx
0x18007d8a9  xor     ecx, ecx; string
0x18007d8ab  call    cs:__imp_WindowsDeleteString
0x18007d8b1  mov     [rbp+37h+var_88], rbx
0x18007d8b5  mov     [rsp+100h+var_E0], rbx; struct _GUID *
0x18007d8ba  lea     r9, [rbp+37h+var_98]; HSTRING *
0x18007d8be  lea     r8, [rbp+37h+var_90]; HSTRING *
0x18007d8c2  lea     rdx, [rbp+37h+var_88]; HSTRING *
0x18007d8c6  mov     rcx, r12; HSTRING
0x18007d8c9  call    ?ParseIdentityData@@YAJPEAUHSTRING__@@PEAPEAU1@11PEAU_GUID@@@Z; ParseIdentityData(HSTRING__ *,HSTRING__ * *,HSTRING__ * *,HSTRING__ * *,_GUID *)
0x18007d8ce  mov     ebx, eax
0x18007d8d0  test    eax, eax
0x18007d8d2  js      loc_18007DA24
0x18007d8d8  lea     rcx, [rsp+100h+var_B8]
0x18007d8dd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007d8e2  lea     rax, [rbp+37h+var_A0]
0x18007d8e6  mov     [rsp+100h+var_D8], rax; int
0x18007d8eb  lea     rax, [rsp+100h+var_B8]
0x18007d8f0  mov     [rsp+100h+var_E0], rax
0x18007d8f5  mov     r9, [rbp+37h+var_98]
0x18007d8f9  mov     r8, [rbp+37h+var_90]
0x18007d8fd  mov     rdx, [rbp+37h+var_88]
0x18007d901  call    GetTicketsForAccountForUser
0x18007d906  mov     dword ptr [rsp+100h+var_E0], eax; int
0x18007d90a  lea     r9, aWinstoreauthGe_2; "WinStoreAuth::GetTicketsForAccount(acco"...
0x18007d911  lea     r8, aPurchasefreeap; "PurchaseFreeApp"
0x18007d918  mov     edx, 16Fh; unsigned int
0x18007d91d  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007d924  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007d929  mov     ebx, eax
0x18007d92b  test    eax, eax
0x18007d92d  js      loc_18007DA24
0x18007d933  mov     dword ptr [rbp+37h+var_B0], 0
0x18007d93a  mov     rcx, [rsp+100h+var_B8]
0x18007d93f  mov     rax, [rcx]
0x18007d942  lea     rdx, [rbp+37h+var_B0]
0x18007d946  mov     rax, [rax+38h]
0x18007d94a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d94f  mov     dword ptr [rsp+100h+var_E0], eax; int
0x18007d953  lea     r9, aTicketsGetSize; "tickets->get_Size(&ticketCount)"
0x18007d95a  lea     r8, aPurchasefreeap; "PurchaseFreeApp"
0x18007d961  mov     edx, 173h; unsigned int
0x18007d966  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007d96d  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007d972  mov     ebx, eax
0x18007d974  test    eax, eax
0x18007d976  js      loc_18007DA24
0x18007d97c  cmp     dword ptr [rbp+37h+var_B0], 1
0x18007d980  jb      short loc_18007D9DC
0x18007d982  mov     rdi, [rsp+100h+var_B8]
0x18007d987  mov     rax, [rdi]
0x18007d98a  mov     rbx, [rax+30h]
0x18007d98e  mov     rcx, [rbp+37h+string]; string
0x18007d992  call    cs:__imp_WindowsDeleteString
0x18007d998  mov     [rbp+37h+string], 0
0x18007d9a0  lea     r8, [rbp+37h+string]
0x18007d9a4  xor     edx, edx
0x18007d9a6  mov     rcx, rdi
0x18007d9a9  mov     rax, rbx
0x18007d9ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d9b1  mov     dword ptr [rsp+100h+var_E0], eax; int
0x18007d9b5  lea     r9, aTicketsGetat0A; "tickets->GetAt(0, authTicket.GetAddress"...
0x18007d9bc  lea     r8, aPurchasefreeap; "PurchaseFreeApp"
0x18007d9c3  mov     edx, 178h; unsigned int
0x18007d9c8  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007d9cf  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007d9d4  mov     ebx, eax
0x18007d9d6  mov     rdi, [rbp+37h+var_80]
0x18007d9da  jmp     short loc_18007DA24
0x18007d9dc  mov     ecx, 80004005h
0x18007d9e1  mov     ebx, ecx
0x18007d9e3  mov     [rsp+100h+var_C8], 0; unsigned __int16 *
0x18007d9ec  mov     [rsp+100h+var_D0], 0; char *
0x18007d9f5  lea     rax, aFailedToObtain; "Failed to obtain user tickets."
0x18007d9fc  mov     [rsp+100h+var_D8], rax; unsigned __int16 *
0x18007da01  mov     dword ptr [rsp+100h+var_E0], ecx; int
0x18007da05  lea     r9, aPurchasefreeap; "PurchaseFreeApp"
0x18007da0c  mov     r8d, 17Dh; unsigned int
0x18007da12  lea     rdx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007da19  mov     ecx, 1; unsigned int
0x18007da1e  call    ?LogSimpleMessage@@YAXIPEBDI0JPEBG01@Z; LogSimpleMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *)
0x18007da23  nop
0x18007da24  mov     rcx, [rbp+37h+var_98]; string
0x18007da28  call    cs:__imp_WindowsDeleteString
0x18007da2e  nop
0x18007da2f  mov     rcx, [rbp+37h+var_90]; string
0x18007da33  call    cs:__imp_WindowsDeleteString
0x18007da39  nop
0x18007da3a  mov     rcx, [rbp+37h+var_88]; string
0x18007da3e  call    cs:__imp_WindowsDeleteString
0x18007da44  nop
0x18007da45  lea     rcx, [rsp+100h+var_B8]
0x18007da4a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007da4f  jmp     short loc_18007DA71
0x18007da51  mov     rcx, [rbp+37h+string]; string
0x18007da55  call    cs:__imp_WindowsDeleteString
0x18007da5b  mov     [rbp+37h+string], rbx
0x18007da5f  lea     r8, [rbp+37h+var_A0]; struct Windows::Security::Authentication::Web::Core::IWebTokenRequestResult **
0x18007da63  lea     rdx, [rbp+37h+string]; HSTRING *
0x18007da67  mov     cl, r15b; bool
0x18007da6a  call    ?GetAuthTicket@@YAJ_NPEAPEAUHSTRING__@@PEAPEAUIWebTokenRequestResult@Core@Web@Authentication@Security@Windows@@@Z; GetAuthTicket(bool,HSTRING__ * *,Windows::Security::Authentication::Web::Core::IWebTokenRequestResult * *)
0x18007da6f  mov     ebx, eax
0x18007da71  test    ebx, ebx
0x18007da73  js      loc_18007DC95
0x18007da79  mov     [rbp+37h+var_B0], 0
0x18007da81  lea     rcx, [rbp+37h+var_B0]
0x18007da85  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007da8a  lea     rax, [rbp+37h+var_B0]
0x18007da8e  mov     [rsp+100h+var_C8], rax; struct Windows::Data::Json::IJsonObject **
0x18007da93  mov     rax, [rbp+37h+var_70]
0x18007da97  mov     [rsp+100h+var_D0], rax; unsigned __int16 *
0x18007da9c  mov     [rsp+100h+var_D8], rsi; int
0x18007daa1  mov     [rsp+100h+var_E0], rdi; unsigned __int16 *
0x18007daa6  mov     r9, [rbp+37h+var_68]; unsigned __int16 *
0x18007daaa  mov     r8, [rbp+37h+var_60]; unsigned __int16 *
0x18007daae  mov     rdx, r13; unsigned __int16 *
0x18007dab1  mov     rcx, [rbp+37h+string]; HSTRING
0x18007dab5  call    ?CreatePurchaseOrder@@YAJPEAUHSTRING__@@PEBG111PEAVTraceLoggingCorrelationVector@@1PEAPEAUIJsonObject@Json@Data@Windows@@@Z; CreatePurchaseOrder(HSTRING__ *,ushort const *,ushort const *,ushort const *,ushort const *,TraceLoggingCorrelationVector *,ushort const *,Windows::Data::Json::IJsonObject * *)
0x18007daba  mov     ebx, eax
0x18007dabc  cmp     eax, 80070490h
0x18007dac1  jnz     short loc_18007DB3C
0x18007dac3  test    r14b, r14b
0x18007dac6  jnz     loc_18007DC8B
0x18007dacc  mov     rcx, [rbp+37h+var_A0]
0x18007dad0  test    rcx, rcx
0x18007dad3  jz      loc_18007DC8B
0x18007dad9  mov     [rsp+100h+var_B8], 0
0x18007dae2  mov     rax, [rcx]
0x18007dae5  lea     rdx, [rsp+100h+var_B8]
0x18007daea  mov     rax, [rax+48h]
0x18007daee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007daf3  test    eax, eax
0x18007daf5  js      short loc_18007DB2D
0x18007daf7  mov     rcx, [rsp+100h+var_B8]
0x18007dafc  call    ??$WaitForCompletion@UIAsyncActionCompletedHandler@Foundation@Windows@@UIAsyncAction@23@@@YAJPEAUIAsyncAction@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncActionCompletedHandler,Windows::Foundation::IAsyncAction>(Windows::Foundation::IAsyncAction *,tagCOWAIT_FLAGS,void *)
0x18007db01  test    eax, eax
0x18007db03  js      short loc_18007DB2D
0x18007db05  mov     r14b, 1
0x18007db08  lea     rcx, [rsp+100h+var_B8]
0x18007db0d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007db12  nop
0x18007db13  lea     rcx, [rbp+37h+var_B0]
0x18007db17  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007db1c  nop
0x18007db1d  lea     rcx, [rbp+37h+var_A0]
0x18007db21  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007db26  xor     ebx, ebx
0x18007db28  jmp     loc_18007D876
0x18007db2d  lea     rcx, [rsp+100h+var_B8]
0x18007db32  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007db37  jmp     loc_18007DC8B
0x18007db3c  xor     r14d, r14d
0x18007db3f  test    eax, eax
0x18007db41  js      loc_18007DC8B
0x18007db47  mov     [rsp+100h+var_C0], r14b
0x18007db4c  mov     rdi, [rbp+37h+var_B0]
0x18007db50  mov     rax, [rdi]
0x18007db53  mov     rbx, [rax+60h]
0x18007db57  mov     [rbp+37h+var_40], r14
0x18007db5b  lea     r9d, [r14+0Ch]; unsigned int
0x18007db5f  lea     r8d, [r14+0Dh]; unsigned int
0x18007db63  lea     rdx, aIspirequired; "isPIRequired"
0x18007db6a  lea     rcx, [rbp+37h+hstringHeader]; hstringHeader
0x18007db6e  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007db73  nop
0x18007db74  lea     r8, [rsp+100h+var_C0]
0x18007db79  mov     rdx, [rbp+37h+var_40]
0x18007db7d  mov     rcx, rdi
0x18007db80  mov     rax, rbx
0x18007db83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007db88  mov     dword ptr [rsp+100h+var_E0], eax; int
0x18007db8c  lea     r9, aSporderGetname_0; "spOrder->GetNamedBoolean(HStringReferen"...
0x18007db93  lea     r8, aPurchasefreeap; "PurchaseFreeApp"
0x18007db9a  mov     edx, 19Dh; unsigned int
0x18007db9f  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007dba6  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007dbab  mov     ebx, eax
0x18007dbad  test    eax, eax
0x18007dbaf  js      loc_18007DC8B
0x18007dbb5  cmp     [rsp+100h+var_C0], r14b
0x18007dbba  jz      short loc_18007DBC6
0x18007dbbc  mov     ebx, 80070005h
0x18007dbc1  jmp     loc_18007DC8B
0x18007dbc6  mov     [rsp+100h+var_B8], r14
0x18007dbcb  mov     rdi, [rbp+37h+var_B0]
0x18007dbcf  mov     rax, [rdi]
0x18007dbd2  mov     rbx, [rax+50h]
0x18007dbd6  xor     ecx, ecx; string
0x18007dbd8  call    cs:__imp_WindowsDeleteString
0x18007dbde  mov     [rsp+100h+var_B8], r14
0x18007dbe3  mov     [rbp+37h+var_40], r14
0x18007dbe7  mov     r9d, 0Ah; unsigned int
0x18007dbed  lea     r8d, [r9+1]; unsigned int
0x18007dbf1  lea     rdx, aOrderstate; "orderState"
0x18007dbf8  lea     rcx, [rbp+37h+hstringHeader]; hstringHeader
0x18007dbfc  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18007dc01  nop
0x18007dc02  lea     r8, [rsp+100h+var_B8]
0x18007dc07  mov     rdx, [rbp+37h+var_40]
0x18007dc0b  mov     rcx, rdi
0x18007dc0e  mov     rax, rbx
0x18007dc11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007dc16  mov     dword ptr [rsp+100h+var_E0], eax; int
0x18007dc1a  lea     r9, aSporderGetname; "spOrder->GetNamedString(HStringReferenc"...
0x18007dc21  lea     r8, aPurchasefreeap; "PurchaseFreeApp"
0x18007dc28  mov     edx, 1A9h; unsigned int
0x18007dc2d  lea     rcx, aOnecoreuapEndu_44; "onecoreuap\\enduser\\winstore\\installs"...
0x18007dc34  call    ?TraceHR@@YAJPEBDI00JH@Z; TraceHR(char const *,uint,char const *,char const *,long,int)
0x18007dc39  mov     ebx, eax
0x18007dc3b  test    eax, eax
0x18007dc3d  js      short loc_18007DC64
0x18007dc3f  xor     edx, edx; length
0x18007dc41  mov     rcx, [rsp+100h+var_B8]; string
0x18007dc46  call    cs:__imp_WindowsGetStringRawBuffer
0x18007dc4c  test    rax, rax
0x18007dc4f  jz      short loc_18007DC64
0x18007dc51  lea     rdx, aPurchased; "Purchased"
0x18007dc58  mov     rcx, rax; String1
0x18007dc5b  call    wcscmp_0
0x18007dc60  test    eax, eax
0x18007dc62  jz      short loc_18007DC7F
0x18007dc64  mov     [rsp+100h+var_E0], rsi; struct TraceLoggingCorrelationVector *
0x18007dc69  mov     r9, [rbp+37h+var_80]; unsigned __int16 *
0x18007dc6d  mov     r8, [rbp+37h+var_B0]; struct Windows::Data::Json::IJsonObject *
0x18007dc71  mov     rdx, [rbp+37h+string]; HSTRING
0x18007dc75  mov     rcx, r13; unsigned __int16 *
0x18007dc78  call    ?CompletePurchaseOrder@@YAJPEBGPEAUHSTRING__@@PEAUIJsonObject@Json@Data@Windows@@0PEAVTraceLoggingCorrelationVector@@@Z; CompletePurchaseOrder(ushort const *,HSTRING__ *,Windows::Data::Json::IJsonObject *,ushort const *,TraceLoggingCorrelationVector *)
0x18007dc7d  mov     ebx, eax
0x18007dc7f  mov     rcx, [rsp+100h+var_B8]; string
0x18007dc84  call    cs:__imp_WindowsDeleteString
0x18007dc8a  nop
0x18007dc8b  lea     rcx, [rbp+37h+var_B0]
0x18007dc8f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007dc94  nop
0x18007dc95  lea     rcx, [rbp+37h+var_A0]
0x18007dc99  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18007dc9e  nop
0x18007dc9f  lea     rcx, [rbp+37h+var_78]
0x18007dca3  call    ??1?$_Temporary_owner@VTraceLoggingCorrelationVector@@@std@@QEAA@XZ; std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(void)
0x18007dca8  nop
0x18007dca9  mov     rcx, [rbp+37h+string]; string
0x18007dcad  call    cs:__imp_WindowsDeleteString
0x18007dcb3  mov     eax, ebx
0x18007dcb5  jmp     short loc_18007DCD0
0x18007dcb7  lea     rcx, [rbp+37h+var_78]
0x18007dcbb  call    ??1?$_Temporary_owner@VTraceLoggingCorrelationVector@@@std@@QEAA@XZ; std::_Temporary_owner<TraceLoggingCorrelationVector>::~_Temporary_owner<TraceLoggingCorrelationVector>(void)
0x18007dcc0  nop
0x18007dcc1  mov     rcx, [rbp+37h+string]; string
0x18007dcc5  call    cs:__imp_WindowsDeleteString
0x18007dccb  mov     eax, 8007000Eh
0x18007dcd0  mov     rcx, [rbp+37h+var_38]
0x18007dcd4  xor     rcx, rsp; StackCookie
0x18007dcd7  call    __security_check_cookie
0x18007dcdc  mov     rbx, [rsp+100h+arg_18]
  ... truncated ...
```
