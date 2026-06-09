# NotificationHelper::RemoveNotification(Microsoft::WRL::ComPtr<Windows::System::IUser> const &,HSTRING__ *)

- ea: `0x1801047b0`
- end: `0x180104bc6`
- name: `?RemoveNotification@NotificationHelper@@QEAAJAEBV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@PEAUHSTRING__@@@Z`
- size: `1046`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800668c4`
- `0x1801b370c`

## callees

- `0x1800101f4`
- `0x1800222d8`
- `0x18002ec2c`
- `0x18002f214`
- `0x1800538d0`
- `0x180104320`
- `0x1801044c4`
- `0x18010451c`
- `0x1801047b0`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801049ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104aa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104b30`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1801049ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104a02`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104a8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104aa3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104b1a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180104b30`

## string_xrefs

- `0x180104958`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x18010480b`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`
- `0x18010484b`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`
- `0x1801048c0`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`
- `0x1801049db`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`
- `0x180104a32`: `onecoreuap\enduser\winstore\installservice\lib\notificationhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall NotificationHelper::RemoveNotification(HSTRING a1, _QWORD *a2, HSTRING a3)
{
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  int v8; // eax
  __int64 v9; // rax
  __int64 v10; // rbx
  __int64 (__fastcall *v11)(__int64, __int64, HSTRING *); // rdi
  int v12; // eax
  __int64 v13; // rdx
  int i; // eax
  HSTRING v15; // rdi
  __int64 (__fastcall *v16)(HSTRING, _QWORD, __int64 *); // rbx
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rbx
  int v20; // eax
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, HSTRING *); // rbx
  int v23; // eax
  bool v24; // r8
  unsigned int v25; // ebx
  __int64 v26; // rdx
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rdx
  __int64 v30; // rdx
  __int64 v31; // rdx
  const char *v32; // r9
  __int64 result; // rax
  __int64 v34; // rdx
  __int64 v35; // rdx
  __int64 v36; // rdx
  __int64 v37; // rdx
  __int64 v38; // rdx
  __int64 v39; // rdx
  int v40; // [rsp+20h] [rbp-88h]
  HSTRING v41; // [rsp+30h] [rbp-78h] BYREF
  __int64 v42; // [rsp+38h] [rbp-70h] BYREF
  __int64 *v43; // [rsp+40h] [rbp-68h] BYREF
  __int64 v44; // [rsp+48h] [rbp-60h] BYREF
  HSTRING v45; // [rsp+50h] [rbp-58h]
  unsigned int v46; // [rsp+58h] [rbp-50h]
  __int64 v47; // [rsp+60h] [rbp-48h] BYREF
  __int64 v48; // [rsp+68h] [rbp-40h] BYREF
  __int64 *v49; // [rsp+70h] [rbp-38h] BYREF
  char v50[8]; // [rsp+78h] [rbp-30h] BYREF
  int v51; // [rsp+80h] [rbp-28h]
  _BYTE v52[32]; // [rsp+88h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  HSTRING v54; // [rsp+B0h] [rbp+8h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+20h] BYREF

  v54 = a1;
  try
  {
    wil::GetActivationFactory<Windows::UI::Notifications::IToastNotificationManagerStatics4>();
    v43 = 0;
    v5 = *v49;
    v43 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v5 + 48))(v49, *a2, &v43);
    if ( v6 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
        (const char *)(unsigned int)v6,
        v40);
    v42 = 0;
    v7 = *v43;
    v42 = 0;
    v8 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v7 + 64))(v43, &v42);
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
        (const char *)(unsigned int)v8,
        v40);
    v41 = 0;
    v9 = wil::com_ptr_t<Windows::UI::Notifications::IToastNotificationHistory,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotificationHistory2>(
           &v42,
           &v54);
    v10 = *(_QWORD *)v9;
    v11 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(**(_QWORD **)v9 + 56LL);
    v41 = 0;
    v12 = v11(v10, qword_1802CB168, &v41);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
        (const char *)(unsigned int)v12,
        v40);
    wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
      &v54,
      v13);
    v54 = v41;
    v45 = v41;
    v46 = 0;
    v47 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      &v54,
      v50);
    for ( i = v46; i != v51; i = ++v46 )
    {
      v15 = v45;
      v16 = *(__int64 (__fastcall **)(HSTRING, _QWORD, __int64 *))(*(_QWORD *)v45 + 48LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v47);
      v17 = v16(v15, v46, &v47);
      if ( v17 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v17,
          v40);
      v48 = v47;
      if ( v47 )
        (*(void (**)(void))(*(_QWORD *)v47 + 8LL))();
      wil::com_ptr_t<Windows::UI::Notifications::IToastNotification,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotification2>(
        &v48,
        &v44);
      v54 = 0;
      v18 = v44;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 56LL);
      WindowsDeleteString(0);
      v54 = 0;
      v20 = v19(v18, &v54);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAC,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
          (const char *)(unsigned int)v20,
          v40);
      string = 0;
      v21 = v44;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v44 + 72LL);
      WindowsDeleteString(0);
      string = 0;
      v23 = v22(v21, &string);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAF,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
          (const char *)(unsigned int)v23,
          v40);
      if ( StringHelpers::Equal(v54, a3, v24) )
      {
        v25 = (*(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, __int64))(*(_QWORD *)v42 + 64LL))(
                v42,
                v54,
                string,
                qword_1802CB168);
        WindowsDeleteString(string);
        string = 0;
        WindowsDeleteString(v54);
        v54 = 0;
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v44,
          v26);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v48,
          v27);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v52);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v47);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v41,
          v28);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v42,
          v29);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v43,
          v30);
        wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
          &v49,
          v31);
        return v25;
      }
      WindowsDeleteString(string);
      string = 0;
      WindowsDeleteString(v54);
      v54 = 0;
      wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
        &v44,
        v34);
      wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
        &v48,
        v35);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v52);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v47);
    wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
      &v41,
      v36);
    wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
      &v42,
      v37);
    wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
      &v43,
      v38);
    wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(
      &v49,
      v39);
    result = 0;
  }
  catch ( ... )
  {
    LODWORD(v54) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xB8,
                     (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\notificationhelper.cpp",
                     v32);
    return (unsigned int)v54;
  }
  return result;
}

```

## disassembly

```asm
0x1801047b0  mov     [rsp+arg_8], rbx
0x1801047b5  mov     [rsp+arg_0], rcx
0x1801047ba  push    rsi
0x1801047bb  push    rdi
0x1801047bc  push    r14
0x1801047be  sub     rsp, 90h
0x1801047c5  mov     rsi, r8
0x1801047c8  mov     rbx, rdx
0x1801047cb  xor     r14d, r14d
0x1801047ce  lea     rcx, [rsp+0A8h+var_38]
0x1801047d3  call    ??$GetActivationFactory@UIToastNotificationManagerStatics4@Notifications@UI@Windows@@@wil@@YA?AV?$com_ptr_t@UIToastNotificationManagerStatics4@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@0@PEBG@Z; wil::GetActivationFactory<Windows::UI::Notifications::IToastNotificationManagerStatics4>(ushort const *)
0x1801047d8  nop
0x1801047d9  mov     [rsp+0A8h+var_68], r14
0x1801047de  mov     rcx, [rsp+0A8h+var_38]
0x1801047e3  mov     rax, [rcx]
0x1801047e6  mov     [rsp+0A8h+var_68], r14
0x1801047eb  lea     r8, [rsp+0A8h+var_68]
0x1801047f0  mov     rdx, [rbx]
0x1801047f3  mov     rax, [rax+30h]
0x1801047f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801047fc  mov     rcx, [rsp+0A8h]; this
0x180104804  test    eax, eax
0x180104806  jns     short loc_18010481C
0x180104808  mov     r9d, eax; char *
0x18010480b  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180104812  mov     edx, 9Fh; void *
0x180104817  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010481c  mov     [rsp+0A8h+var_70], r14
0x180104821  mov     rcx, [rsp+0A8h+var_68]
0x180104826  mov     rax, [rcx]
0x180104829  mov     [rsp+0A8h+var_70], r14
0x18010482e  lea     rdx, [rsp+0A8h+var_70]
0x180104833  mov     rax, [rax+40h]
0x180104837  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010483c  mov     rcx, [rsp+0A8h]; this
0x180104844  test    eax, eax
0x180104846  jns     short loc_18010485C
0x180104848  mov     r9d, eax; char *
0x18010484b  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180104852  mov     edx, 0A2h; void *
0x180104857  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18010485c  mov     [rsp+0A8h+var_78], r14
0x180104861  lea     rdx, [rsp+0A8h+arg_0]
0x180104869  lea     rcx, [rsp+0A8h+var_70]
0x18010486e  call    ??$query@UIToastNotificationHistory2@Notifications@UI@Windows@@@?$com_ptr_t@UIToastNotificationHistory@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIToastNotificationHistory2@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::Notifications::IToastNotificationHistory,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotificationHistory2>(void)
0x180104873  nop
0x180104874  mov     rbx, [rax]
0x180104877  mov     rax, [rbx]
0x18010487a  mov     rdi, [rax+38h]
0x18010487e  mov     rcx, [rsp+0A8h+var_78]
0x180104883  mov     [rsp+0A8h+var_78], r14
0x180104888  test    rcx, rcx
0x18010488b  jz      short loc_18010489A
0x18010488d  mov     rdx, [rcx]
0x180104890  mov     rax, [rdx+10h]
0x180104894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104899  nop
0x18010489a  lea     r8, [rsp+0A8h+var_78]
0x18010489f  mov     rdx, cs:qword_1802CB168
0x1801048a6  mov     rcx, rbx
0x1801048a9  mov     rax, rdi
0x1801048ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801048b1  mov     rcx, [rsp+0A8h]; this
0x1801048b9  test    eax, eax
0x1801048bb  jns     short loc_1801048D2
0x1801048bd  mov     r9d, eax; char *
0x1801048c0  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x1801048c7  mov     edx, 0A5h; void *
0x1801048cc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801048d2  lea     rcx, [rsp+0A8h+arg_0]
0x1801048da  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x1801048df  mov     rax, [rsp+0A8h+var_78]
0x1801048e4  mov     [rsp+0A8h+arg_0], rax
0x1801048ec  mov     [rsp+0A8h+var_58], rax
0x1801048f1  mov     [rsp+0A8h+var_50], r14d
0x1801048f6  mov     [rsp+0A8h+var_48], r14
0x1801048fb  lea     rdx, [rsp+0A8h+var_30]
0x180104900  lea     rcx, [rsp+0A8h+arg_0]
0x180104908  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x18010490d  nop
0x18010490e  mov     eax, [rsp+0A8h+var_50]
0x180104912  cmp     eax, [rsp+0A8h+var_28]
0x180104919  jz      loc_180104B62
0x18010491f  mov     rdi, [rsp+0A8h+var_58]
0x180104924  mov     rax, [rdi]
0x180104927  mov     rbx, [rax+30h]
0x18010492b  lea     rcx, [rsp+0A8h+var_48]
0x180104930  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104935  lea     r8, [rsp+0A8h+var_48]
0x18010493a  mov     edx, [rsp+0A8h+var_50]
0x18010493e  mov     rcx, rdi
0x180104941  mov     rax, rbx
0x180104944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104949  mov     rcx, [rsp+0A8h]; this
0x180104951  test    eax, eax
0x180104953  jns     short loc_180104969
0x180104955  mov     r9d, eax; char *
0x180104958  lea     r8, aOnecoreInterna_11; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18010495f  mov     edx, 1CBEh; void *
0x180104964  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180104969  mov     rcx, [rsp+0A8h+var_48]
0x18010496e  mov     [rsp+0A8h+var_40], rcx
0x180104973  test    rcx, rcx
0x180104976  jz      short loc_180104985
0x180104978  mov     rax, [rcx]
0x18010497b  mov     rax, [rax+8]
0x18010497f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104984  nop
0x180104985  lea     rdx, [rsp+0A8h+var_60]
0x18010498a  lea     rcx, [rsp+0A8h+var_40]
0x18010498f  call    ??$query@UIToastNotification2@Notifications@UI@Windows@@@?$com_ptr_t@UIToastNotification@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@wil@@QEBA?AV?$com_ptr_t@UIToastNotification2@Notifications@UI@Windows@@Uerr_exception_policy@wil@@@1@XZ; wil::com_ptr_t<Windows::UI::Notifications::IToastNotification,wil::err_exception_policy>::query<Windows::UI::Notifications::IToastNotification2>(void)
0x180104994  nop
0x180104995  mov     [rsp+0A8h+arg_0], r14
0x18010499d  mov     rdi, [rsp+0A8h+var_60]
0x1801049a2  mov     rax, [rdi]
0x1801049a5  mov     rbx, [rax+38h]
0x1801049a9  xor     ecx, ecx; string
0x1801049ab  call    cs:__imp_WindowsDeleteString
0x1801049b1  mov     [rsp+0A8h+arg_0], r14
0x1801049b9  lea     rdx, [rsp+0A8h+arg_0]
0x1801049c1  mov     rcx, rdi
0x1801049c4  mov     rax, rbx
0x1801049c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801049cc  mov     rcx, [rsp+0A8h]; this
0x1801049d4  test    eax, eax
0x1801049d6  jns     short loc_1801049EC
0x1801049d8  mov     r9d, eax; char *
0x1801049db  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x1801049e2  mov     edx, 0ACh; void *
0x1801049e7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1801049ec  mov     [rsp+0A8h+string], r14
0x1801049f4  mov     rdi, [rsp+0A8h+var_60]
0x1801049f9  mov     rax, [rdi]
0x1801049fc  mov     rbx, [rax+48h]
0x180104a00  xor     ecx, ecx; string
0x180104a02  call    cs:__imp_WindowsDeleteString
0x180104a08  mov     [rsp+0A8h+string], r14
0x180104a10  lea     rdx, [rsp+0A8h+string]
0x180104a18  mov     rcx, rdi
0x180104a1b  mov     rax, rbx
0x180104a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104a23  mov     rcx, [rsp+0A8h]; this
0x180104a2b  test    eax, eax
0x180104a2d  jns     short loc_180104A43
0x180104a2f  mov     r9d, eax; char *
0x180104a32  lea     r8, aOnecoreuapEndu_7; "onecoreuap\\enduser\\winstore\\installs"...
0x180104a39  mov     edx, 0AFh; void *
0x180104a3e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180104a43  mov     rdx, rsi; HSTRING
0x180104a46  mov     rcx, [rsp+0A8h+arg_0]; HSTRING
0x180104a4e  call    ?Equal@StringHelpers@@SA_NPEAUHSTRING__@@0_N@Z; StringHelpers::Equal(HSTRING__ *,HSTRING__ *,bool)
0x180104a53  test    al, al
0x180104a55  jz      loc_180104B12
0x180104a5b  mov     rcx, [rsp+0A8h+var_70]
0x180104a60  mov     rax, [rcx]
0x180104a63  mov     r9, cs:qword_1802CB168
0x180104a6a  mov     r8, [rsp+0A8h+string]
0x180104a72  mov     rdx, [rsp+0A8h+arg_0]
0x180104a7a  mov     rax, [rax+40h]
0x180104a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180104a83  mov     ebx, eax
0x180104a85  mov     rcx, [rsp+0A8h+string]; string
0x180104a8d  call    cs:__imp_WindowsDeleteString
0x180104a93  mov     [rsp+0A8h+string], r14
0x180104a9b  mov     rcx, [rsp+0A8h+arg_0]; string
0x180104aa3  call    cs:__imp_WindowsDeleteString
0x180104aa9  mov     [rsp+0A8h+arg_0], r14
0x180104ab1  lea     rcx, [rsp+0A8h+var_60]
0x180104ab6  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104abb  nop
0x180104abc  lea     rcx, [rsp+0A8h+var_40]
0x180104ac1  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104ac6  nop
0x180104ac7  lea     rcx, [rsp+0A8h+var_20]
0x180104acf  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104ad4  nop
0x180104ad5  lea     rcx, [rsp+0A8h+var_48]
0x180104ada  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104adf  nop
0x180104ae0  lea     rcx, [rsp+0A8h+var_78]
0x180104ae5  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104aea  nop
0x180104aeb  lea     rcx, [rsp+0A8h+var_70]
0x180104af0  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104af5  nop
0x180104af6  lea     rcx, [rsp+0A8h+var_68]
0x180104afb  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b00  nop
0x180104b01  lea     rcx, [rsp+0A8h+var_38]
0x180104b06  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b0b  mov     eax, ebx
0x180104b0d  jmp     loc_180104BB1
0x180104b12  mov     rcx, [rsp+0A8h+string]; string
0x180104b1a  call    cs:__imp_WindowsDeleteString
0x180104b20  mov     [rsp+0A8h+string], r14
0x180104b28  mov     rcx, [rsp+0A8h+arg_0]; string
0x180104b30  call    cs:__imp_WindowsDeleteString
0x180104b36  mov     [rsp+0A8h+arg_0], r14
0x180104b3e  lea     rcx, [rsp+0A8h+var_60]
0x180104b43  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b48  nop
0x180104b49  lea     rcx, [rsp+0A8h+var_40]
0x180104b4e  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b53  mov     eax, [rsp+0A8h+var_50]
0x180104b57  inc     eax
0x180104b59  mov     [rsp+0A8h+var_50], eax
0x180104b5d  jmp     loc_180104912
0x180104b62  lea     rcx, [rsp+0A8h+var_20]
0x180104b6a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104b6f  nop
0x180104b70  lea     rcx, [rsp+0A8h+var_48]
0x180104b75  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x180104b7a  nop
0x180104b7b  lea     rcx, [rsp+0A8h+var_78]
0x180104b80  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b85  nop
0x180104b86  lea     rcx, [rsp+0A8h+var_70]
0x180104b8b  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b90  nop
0x180104b91  lea     rcx, [rsp+0A8h+var_68]
0x180104b96  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104b9b  nop
0x180104b9c  lea     rcx, [rsp+0A8h+var_38]
0x180104ba1  call    ??1?$com_ptr_t@VInstallQueue@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<InstallQueue,wil::err_exception_policy>::~com_ptr_t<InstallQueue,wil::err_exception_policy>(void)
0x180104ba6  xor     eax, eax
0x180104ba8  jmp     short loc_180104BB1
0x180104baa  mov     eax, dword ptr [rsp+0A8h+arg_0]
0x180104bb1  mov     rbx, [rsp+0A8h+arg_8]
0x180104bb9  add     rsp, 90h
0x180104bc0  pop     r14
0x180104bc2  pop     rdi
0x180104bc3  pop     rsi
0x180104bc4  retn
```
