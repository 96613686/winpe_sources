# CloudExperienceHostBroker::Account::LocalAccountManager::s_DecryptPassword(Windows::Storage::Streams::IBuffer *,HSTRING__ * *)

- ea: `0x180026f34`
- end: `0x180027223`
- name: `?s_DecryptPassword@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUIBuffer@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z`
- size: `751`
- prototype: `__int64 __fastcall(struct Windows::Storage::Streams::IBuffer *, HSTRING *)`
- caller_count: `2`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180022660`
- `0x180022924`

## callees

- `0x180002a3c`
- `0x180006120`
- `0x180008344`
- `0x180009f30`
- `0x18001fed0`
- `0x180020dd8`
- `0x180026870`
- `0x180026f34`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f9e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800270aa`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180026f9e`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800270aa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027121`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027091`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180026f85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x180027091`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800270cb`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x1800270cb`

## string_xrefs

- `0x180026f7e`: `Windows.Security.Cryptography.DataProtection.DataProtectionProvider`
- `0x18002708a`: `Windows.Security.Cryptography.CryptographicBuffer`
- `0x180026fbe`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x18002700f`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800270de`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x180027151`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`
- `0x1800271ce`: `shell\cloudexperiencehost\broker\lib\localaccountmanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CloudExperienceHostBroker::Account::LocalAccountManager::s_DecryptPassword(
        struct Windows::Storage::Streams::IBuffer *a1,
        HSTRING *a2)
{
  int v4; // eax
  int v5; // ebx
  __int64 v6; // rdi
  __int64 (__fastcall *v7)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *); // rbx
  int v8; // eax
  __int64 v9; // rdi
  HSTRING v10; // rbx
  int ActivationFactory; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, _QWORD, struct Windows::Storage::Streams::IBuffer *, HSTRING *); // rbx
  int v14; // eax
  int v16; // [rsp+20h] [rbp-39h]
  struct Windows::Storage::Streams::IBuffer *v17; // [rsp+30h] [rbp-29h] BYREF
  __int64 v18; // [rsp+38h] [rbp-21h] BYREF
  HSTRING v19; // [rsp+40h] [rbp-19h] BYREF
  __int64 v20; // [rsp+48h] [rbp-11h] BYREF
  __int64 v21; // [rsp+50h] [rbp-9h] BYREF
  HSTRING string; // [rsp+58h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp+7h] BYREF
  HSTRING v24; // [rsp+78h] [rbp+1Fh] BYREF
  HSTRING_HEADER v25; // [rsp+80h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+5Fh]

  *a2 = 0;
  v21 = 0;
  if ( WindowsCreateStringReference(
         L"Windows.Security.Cryptography.DataProtection.DataProtectionProvider",
         0x43u,
         &hstringHeader,
         &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v4 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::DataProtection::IDataProtectionProvider>>(
         string,
         &v21);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v18 = 0;
    v6 = v21;
    v7 = *(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer *, __int64 *))(*(_QWORD *)v21 + 56LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    v8 = v7(v6, a1, &v18);
    v5 = v8;
    if ( v8 >= 0 )
    {
      v17 = 0;
      v9 = v18;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
      v5 = WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(v9);
      if ( v5 < 0
        || (v5 = (*(__int64 (__fastcall **)(__int64, struct Windows::Storage::Streams::IBuffer **))(*(_QWORD *)v9 + 64LL))(
                   v9,
                   &v17),
            v5 < 0) )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1C2,
          (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
          (const char *)(unsigned int)v5,
          v16);
      }
      else
      {
        string = (HSTRING)&v17;
        hstringHeader.Reserved.Reserved2[0] = 1;
        v20 = 0;
        if ( WindowsCreateStringReference(L"Windows.Security.Cryptography.CryptographicBuffer", 0x31u, &v25, &v24) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        v10 = v24;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
        ActivationFactory = RoGetActivationFactory(v10, &GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb, &v20);
        v5 = ActivationFactory;
        if ( ActivationFactory >= 0 )
        {
          v19 = 0;
          v12 = v20;
          v13 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Storage::Streams::IBuffer *, HSTRING *))(*(_QWORD *)v20 + 128LL);
          WindowsDeleteString(0);
          v19 = 0;
          v14 = v13(v12, 0, v17, &v19);
          v5 = v14;
          if ( v14 >= 0 )
          {
            *a2 = v19;
            v19 = 0;
            Windows::Internal::String::~String((Windows::Internal::String *)&v19);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
            CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(v17);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
            Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
            v5 = 0;
            goto LABEL_19;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CE,
            (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
            (const char *)(unsigned int)v14,
            v16);
          Windows::Internal::String::~String((Windows::Internal::String *)&v19);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
          CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(v17);
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1CC,
            (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
            (const char *)(unsigned int)ActivationFactory,
            v16);
          Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v20);
          CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(v17);
        }
      }
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v17);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BE,
        (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
        (const char *)(unsigned int)v8,
        v16);
    }
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v18);
    goto LABEL_19;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1BC,
    (unsigned int)"shell\\cloudexperiencehost\\broker\\lib\\localaccountmanager.cpp",
    (const char *)(unsigned int)v4,
    v16);
LABEL_19:
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v21);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180026f34  mov     [rsp-8+arg_10], rbx
0x180026f39  mov     [rsp-8+arg_18], rsi
0x180026f3e  push    rbp
0x180026f3f  push    rdi
0x180026f40  push    r14
0x180026f42  lea     rbp, [rsp-47h]
0x180026f47  sub     rsp, 0A0h
0x180026f4e  mov     rax, cs:__security_cookie
0x180026f55  xor     rax, rsp
0x180026f58  mov     [rbp+57h+var_18], rax
0x180026f5c  mov     rsi, rdx
0x180026f5f  mov     r14, rcx
0x180026f62  mov     qword ptr [rdx], 0
0x180026f69  mov     [rbp+57h+var_60], 0
0x180026f71  lea     r9, [rbp+57h+string]; string
0x180026f75  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x180026f79  mov     edx, 43h ; 'C'; length
0x180026f7e  lea     rcx, ?RuntimeClass_Windows_Security_Cryptography_DataProtection_DataProtectionProvider@@3QBGB; "Windows.Security.Cryptography.DataProte"...
0x180026f85  call    cs:__imp_WindowsCreateStringReference
0x180026f8b  test    eax, eax
0x180026f8d  jns     short loc_180026FA4
0x180026f8f  xor     r9d, r9d; lpArguments
0x180026f92  xor     r8d, r8d; nNumberOfArguments
0x180026f95  lea     edx, [r9+1]; dwExceptionFlags
0x180026f99  mov     ecx, 0C000000Dh; dwExceptionCode
0x180026f9e  call    cs:__imp_RaiseException
0x180026fa4  lea     rdx, [rbp+57h+var_60]
0x180026fa8  mov     rcx, [rbp+57h+string]
0x180026fac  call    ??$ActivateInstance@V?$ComPtr@UIDataProtectionProvider@DataProtection@Cryptography@Security@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDataProtectionProvider@DataProtection@Cryptography@Security@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::DataProtection::IDataProtectionProvider>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Security::Cryptography::DataProtection::IDataProtectionProvider>>)
0x180026fb1  mov     ebx, eax
0x180026fb3  test    eax, eax
0x180026fb5  jns     short loc_180026FD4
0x180026fb7  mov     rcx, [rbp+5Fh]; this
0x180026fbb  mov     r9d, eax; char *
0x180026fbe  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180026fc5  mov     edx, 1BCh; void *
0x180026fca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180026fcf  jmp     loc_1800271F4
0x180026fd4  mov     [rbp+57h+var_78], 0
0x180026fdc  mov     rdi, [rbp+57h+var_60]
0x180026fe0  mov     rax, [rdi]
0x180026fe3  mov     rbx, [rax+38h]
0x180026fe7  lea     rcx, [rbp+57h+var_78]
0x180026feb  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180026ff0  lea     r8, [rbp+57h+var_78]
0x180026ff4  mov     rdx, r14
0x180026ff7  mov     rcx, rdi
0x180026ffa  mov     rax, rbx
0x180026ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027002  mov     ebx, eax
0x180027004  test    eax, eax
0x180027006  jns     short loc_180027025
0x180027008  mov     rcx, [rbp+5Fh]; this
0x18002700c  mov     r9d, eax; char *
0x18002700f  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180027016  mov     edx, 1BEh; void *
0x18002701b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027020  jmp     loc_1800271EA
0x180027025  mov     [rbp+57h+var_80], 0
0x18002702d  mov     rdi, [rbp+57h+var_78]
0x180027031  lea     rcx, [rbp+57h+var_80]
0x180027035  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002703a  mov     rcx, rdi
0x18002703d  call    ??$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAUIBuffer@Streams@Storage@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z; WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::Streams::IBuffer *>,Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *>>(Windows::Foundation::IAsyncOperation<Windows::Storage::Streams::IBuffer *> *,tagCOWAIT_FLAGS,void *)
0x180027042  mov     ebx, eax
0x180027044  test    eax, eax
0x180027046  js      loc_1800271C7
0x18002704c  mov     rax, [rdi]
0x18002704f  lea     rdx, [rbp+57h+var_80]
0x180027053  mov     rcx, rdi
0x180027056  mov     rax, [rax+40h]
0x18002705a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002705f  mov     ebx, eax
0x180027061  test    eax, eax
0x180027063  js      loc_1800271C7
0x180027069  lea     rax, [rbp+57h+var_80]
0x18002706d  mov     [rbp+57h+string], rax
0x180027071  mov     byte ptr [rbp+57h+hstringHeader.Reserved], 1
0x180027075  mov     [rbp+57h+var_68], 0
0x18002707d  lea     r9, [rbp+57h+var_38]; string
0x180027081  lea     r8, [rbp+57h+var_30]; hstringHeader
0x180027085  mov     edx, 31h ; '1'; length
0x18002708a  lea     rcx, ?RuntimeClass_Windows_Security_Cryptography_CryptographicBuffer@@3QBGB; "Windows.Security.Cryptography.Cryptogra"...
0x180027091  call    cs:__imp_WindowsCreateStringReference
0x180027097  test    eax, eax
0x180027099  jns     short loc_1800270B0
0x18002709b  xor     r9d, r9d; lpArguments
0x18002709e  xor     r8d, r8d; nNumberOfArguments
0x1800270a1  lea     edx, [r9+1]; dwExceptionFlags
0x1800270a5  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800270aa  call    cs:__imp_RaiseException
0x1800270b0  mov     rbx, [rbp+57h+var_38]
0x1800270b4  lea     rcx, [rbp+57h+var_68]
0x1800270b8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270bd  lea     r8, [rbp+57h+var_68]
0x1800270c1  lea     rdx, _GUID_320b7e22_3cb0_4cdf_8663_1d28910065eb
0x1800270c8  mov     rcx, rbx
0x1800270cb  call    cs:__imp_RoGetActivationFactory
0x1800270d1  mov     ebx, eax
0x1800270d3  test    eax, eax
0x1800270d5  jns     short loc_180027109
0x1800270d7  mov     rcx, [rbp+5Fh]; this
0x1800270db  mov     r9d, eax; char *
0x1800270de  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800270e5  mov     edx, 1CCh; void *
0x1800270ea  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800270ef  nop
0x1800270f0  lea     rcx, [rbp+57h+var_68]
0x1800270f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800270f9  nop
0x1800270fa  mov     rcx, [rbp+57h+var_80]; struct Windows::Storage::Streams::IBuffer *
0x1800270fe  call    ?s_ClearPasswordBuffer@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUIBuffer@Streams@Storage@Windows@@@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(Windows::Storage::Streams::IBuffer *)
0x180027103  nop
0x180027104  jmp     loc_1800271E0
0x180027109  mov     [rbp+57h+var_70], 0
0x180027111  mov     rdi, [rbp+57h+var_68]
0x180027115  mov     rax, [rdi]
0x180027118  mov     rbx, [rax+80h]
0x18002711f  xor     ecx, ecx; string
0x180027121  call    cs:__imp_WindowsDeleteString
0x180027127  mov     [rbp+57h+var_70], 0
0x18002712f  lea     r9, [rbp+57h+var_70]
0x180027133  mov     r8, [rbp+57h+var_80]
0x180027137  xor     edx, edx
0x180027139  mov     rcx, rdi
0x18002713c  mov     rax, rbx
0x18002713f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027144  mov     ebx, eax
0x180027146  test    eax, eax
0x180027148  jns     short loc_180027183
0x18002714a  mov     rcx, [rbp+5Fh]; this
0x18002714e  mov     r9d, eax; char *
0x180027151  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x180027158  mov     edx, 1CEh; void *
0x18002715d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180027162  nop
0x180027163  lea     rcx, [rbp+57h+var_70]; this
0x180027167  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002716c  nop
0x18002716d  lea     rcx, [rbp+57h+var_68]
0x180027171  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180027176  nop
0x180027177  mov     rcx, [rbp+57h+var_80]; struct Windows::Storage::Streams::IBuffer *
0x18002717b  call    ?s_ClearPasswordBuffer@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUIBuffer@Streams@Storage@Windows@@@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(Windows::Storage::Streams::IBuffer *)
0x180027180  nop
0x180027181  jmp     short loc_1800271E0
0x180027183  mov     rax, [rbp+57h+var_70]
0x180027187  mov     [rsi], rax
0x18002718a  mov     [rbp+57h+var_70], 0
0x180027192  lea     rcx, [rbp+57h+var_70]; this
0x180027196  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18002719b  nop
0x18002719c  lea     rcx, [rbp+57h+var_68]
0x1800271a0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271a5  nop
0x1800271a6  mov     rcx, [rbp+57h+var_80]; struct Windows::Storage::Streams::IBuffer *
0x1800271aa  call    ?s_ClearPasswordBuffer@LocalAccountManager@Account@CloudExperienceHostBroker@@CAJPEAUIBuffer@Streams@Storage@Windows@@@Z; CloudExperienceHostBroker::Account::LocalAccountManager::s_ClearPasswordBuffer(Windows::Storage::Streams::IBuffer *)
0x1800271af  nop
0x1800271b0  lea     rcx, [rbp+57h+var_80]
0x1800271b4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271b9  nop
0x1800271ba  lea     rcx, [rbp+57h+var_78]
0x1800271be  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271c3  xor     ebx, ebx
0x1800271c5  jmp     short loc_1800271F4
0x1800271c7  mov     rcx, [rbp+5Fh]; this
0x1800271cb  mov     r9d, ebx; char *
0x1800271ce  lea     r8, aShellCloudexpe_4; "shell\\cloudexperiencehost\\broker\\lib"...
0x1800271d5  mov     edx, 1C2h; void *
0x1800271da  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800271df  nop
0x1800271e0  lea     rcx, [rbp+57h+var_80]
0x1800271e4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271e9  nop
0x1800271ea  lea     rcx, [rbp+57h+var_78]
0x1800271ee  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271f3  nop
0x1800271f4  lea     rcx, [rbp+57h+var_60]
0x1800271f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800271fd  mov     eax, ebx
0x1800271ff  mov     rcx, [rbp+57h+var_18]
0x180027203  xor     rcx, rsp; StackCookie
0x180027206  call    __security_check_cookie
0x18002720b  lea     r11, [rsp+0B0h+var_10]
0x180027213  mov     rbx, [r11+30h]
0x180027217  mov     rsi, [r11+38h]
0x18002721b  mov     rsp, r11
0x18002721e  pop     r14
0x180027220  pop     rdi
0x180027221  pop     rbp
0x180027222  retn
```
