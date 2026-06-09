# CShellExperienceDispatcher::QueueEvent(int,ushort const *,IUnknown *)

- ea: `0x1800152f0`
- end: `0x180015973`
- name: `?QueueEvent@CShellExperienceDispatcher@@UEAAJHPEBGPEAUIUnknown@@@Z`
- size: `1667`
- prototype: `int(CShellExperienceDispatcher *__hidden this, int, const unsigned __int16 *, struct IUnknown *)`
- caller_count: `0`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009dfc`
- `0x180014b34`
- `0x1800152f0`
- `0x18001597c`
- `0x180016064`
- `0x180016078`
- `0x1800378dc`
- `0x180037b9c`
- `0x1800bd554`
- `0x1800eb924`
- `0x180142e10`
- `0x180145275`
- `0x18015206c`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800153db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800156d1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800153db`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x1800156d1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015359`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180015359`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18001555b`
- `api-ms-win-ro-typeresolution-l1-1-1!RoCreatePropertySetSerializer` at `0x18001555b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001544c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001544c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015619`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015730`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015761`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800157e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015880`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015955`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180015465`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800154d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800154d7`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015507`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x180015507`

## string_xrefs

- `0x18001564e`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015670`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18001571a`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18001579c`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18001581c`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x1800158b2`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x1800158d7`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x1800158f1`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x180015935`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CShellExperienceDispatcher::QueueEvent(
        CShellExperienceDispatcher *this,
        int a2,
        const unsigned __int16 *a3,
        struct IUnknown *a4)
{
  RTL_SRWLOCK *v7; // r13
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v8; // rsi
  _QWORD *v9; // rax
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // r8
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper ***v13; // rax
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v14; // rdi
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v15; // rbx
  unsigned __int64 v16; // rbx
  UINT32 v17; // edx
  const WCHAR *v18; // rcx
  unsigned int v19; // ebx
  struct Windows::Foundation::Collections::IPropertySet *v20; // r9
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v22; // eax
  HRESULT v23; // eax
  int v24; // edx
  unsigned int v25; // r8d
  HSTRING v26; // rbx
  int v27; // eax
  int v28; // eax
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v29; // rcx
  RTL_SRWLOCK *v30; // rcx
  int v31; // eax
  struct Windows::Foundation::Collections::IPropertySet *v32; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v33; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v35; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v36; // rcx
  int v37; // eax
  RTL_SRWLOCK *v38; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v39; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v40; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v41; // rcx
  RTL_SRWLOCK *v42; // rcx
  struct Windows::Foundation::Collections::IPropertySet *v43; // rcx
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v44; // rcx
  int v45; // eax
  int v46; // [rsp+20h] [rbp-69h]
  int v47; // [rsp+20h] [rbp-69h]
  int v48; // [rsp+20h] [rbp-69h]
  HSTRING string; // [rsp+30h] [rbp-59h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v50; // [rsp+38h] [rbp-51h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v51; // [rsp+40h] [rbp-49h] BYREF
  RTL_SRWLOCK *v52; // [rsp+48h] [rbp-41h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **v53; // [rsp+50h] [rbp-39h] BYREF
  struct Windows::Foundation::Collections::IPropertySet *v54; // [rsp+58h] [rbp-31h] BYREF
  int v55; // [rsp+60h] [rbp-29h]
  char v56[8]; // [rsp+68h] [rbp-21h] BYREF
  char v57[8]; // [rsp+70h] [rbp-19h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+78h] [rbp-11h] BYREF
  HSTRING v59; // [rsp+90h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v55 = a2;
  v50 = 0;
  v7 = (RTL_SRWLOCK *)((char *)this - 176);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
  v50 = 0;
  v8 = 0;
  v54 = 0;
  AcquireSRWLockShared(v7 + 38);
  v52 = v7 + 38;
  v9 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                   &v7[30],
                   v57);
  v11 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                    v10,
                    v56,
                    *v9);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow>(
    &v53,
    *v11,
    v12,
    ~a2);
  v13 = (struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper ***)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                                                                                 &v7[30],
                                                                                 v56);
  if ( v53 == *v13 )
  {
    if ( v7 != (RTL_SRWLOCK *)-304LL )
      ReleaseSRWLockShared(v7 + 38);
  }
  else
  {
    v14 = v53[1];
    v15 = *v53;
    if ( *v53 )
    {
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v15 + 8LL))(*v53);
      v8 = v15;
      v54 = v15;
    }
    if ( v7 != (RTL_SRWLOCK *)-304LL )
      ReleaseSRWLockShared(v7 + 38);
    if ( !v14 )
    {
      v37 = CShellExperienceDispatcher::_InitializeExperienceId((CShellExperienceDispatcher *)v7, v8);
      v19 = v37;
      if ( v37 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x4C4,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v37,
          v46);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v54);
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x354,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)v19,
          v48);
        v35 = v50;
        if ( v50 )
        {
          v50 = 0;
          (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v35 + 16LL))(v35);
        }
        return v19;
      }
    }
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v8 + 8LL))(v8);
    v50 = v8;
    if ( v8 )
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v8 + 16LL))(v8);
  }
  string = 0;
  if ( !a3 )
  {
    WindowsDeleteString(0);
    v17 = 0;
    v18 = &pszDefault;
    goto LABEL_16;
  }
  v16 = -1;
  do
    ++v16;
  while ( a3[v16] );
  if ( v16 <= 0xFFFFFFFF )
  {
    WindowsDeleteString(0);
    v17 = v16;
    v18 = a3;
LABEL_16:
    string = 0;
    v19 = WindowsCreateString(v18, v17, &string);
    goto LABEL_17;
  }
  v19 = -2147024362;
LABEL_17:
  if ( (v19 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x357,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v19,
      v46);
    WindowsDeleteString(string);
    string = 0;
    v36 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v36 + 16LL))(v36);
    }
    return v19;
  }
  v20 = 0;
  v51 = 0;
  if ( !a4 )
    goto LABEL_32;
  v52 = 0;
  QueryInterface = a4->lpVtbl->QueryInterface;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
  v22 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, RTL_SRWLOCK **))QueryInterface)(
          a4,
          &GUID_905a0fe0_bc53_11df_8c49_001e4fc686da,
          &v52);
  v19 = v22;
  if ( v22 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35E,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v22,
      v46);
    v38 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v38->Ptr + 2))(v38);
    }
    v39 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v39 + 16LL))(v39);
    }
    WindowsDeleteString(string);
    string = 0;
    v40 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v40 + 16LL))(v40);
    }
    return v19;
  }
  v59 = 0;
  v23 = WindowsCreateStringReference(L"Windows.Foundation.Collections.ValueSet", 0x27u, &hstringHeader, &v59);
  if ( v23 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v23, v24, v25);
    __debugbreak();
  }
  v26 = v59;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
  v51 = 0;
  v54 = 0;
  v19 = RoActivateInstance(v26, &v54);
  if ( (v19 & 0x80000000) == 0 )
  {
    if ( !memcmp_0(&GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90, 0x10u) )
    {
      v51 = v54;
    }
    else
    {
      v19 = (**(__int64 (__fastcall ***)(struct Windows::Foundation::Collections::IPropertySet *, GUID *, struct Windows::Foundation::Collections::IPropertySet **))v54)(
              v54,
              &GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c,
              &v51);
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v54 + 16LL))(v54);
    }
  }
  if ( (v19 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)v19,
      v46);
LABEL_73:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v52);
LABEL_76:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v51);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v50);
    return v19;
  }
  v53 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
  v27 = RoCreatePropertySetSerializer(&v53);
  v19 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x363,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v27,
      v46);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v53);
    goto LABEL_73;
  }
  v28 = (*((__int64 (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **, struct Windows::Foundation::Collections::IPropertySet *, RTL_SRWLOCK *))*v53
         + 7))(
          v53,
          v51,
          v52);
  v19 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x364,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v28,
      v46);
    v41 = v53;
    if ( v53 )
    {
      v53 = 0;
      (*((void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))*v41 + 2))(v41);
    }
    v42 = v52;
    if ( v52 )
    {
      v52 = 0;
      (*((void (__fastcall **)(RTL_SRWLOCK *))v42->Ptr + 2))(v42);
    }
    v43 = v51;
    if ( v51 )
    {
      v51 = 0;
      (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v43 + 16LL))(v43);
    }
    WindowsDeleteString(string);
    string = 0;
    v44 = v50;
    if ( v50 )
    {
      v50 = 0;
      (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v44 + 16LL))(v44);
    }
    return v19;
  }
  v29 = v53;
  if ( v53 )
  {
    v53 = 0;
    (*((void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper **))*v29 + 2))(v29);
  }
  v30 = v52;
  if ( v52 )
  {
    v52 = 0;
    (*((void (__fastcall **)(RTL_SRWLOCK *))v30->Ptr + 2))(v30);
  }
  v20 = v51;
LABEL_32:
  if ( v50 )
  {
    v47 = (int)v20;
    v31 = CShellExperienceDispatcher::_NotifyListener(v7, v50, 2, string);
    if ( v31 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v31,
        v47);
    goto LABEL_35;
  }
  v45 = CShellExperienceDispatcher::_BufferQueuedEvent((CShellExperienceDispatcher *)v7, v55, string, v20);
  v19 = v45;
  if ( v45 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x375,
      (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shellexp"
                    "eriencedispatcher.cpp",
      (const char *)(unsigned int)v45,
      v46);
    goto LABEL_76;
  }
LABEL_35:
  v32 = v51;
  if ( v51 )
  {
    v51 = 0;
    (*(void (__fastcall **)(struct Windows::Foundation::Collections::IPropertySet *))(*(_QWORD *)v32 + 16LL))(v32);
  }
  WindowsDeleteString(string);
  string = 0;
  v33 = v50;
  if ( v50 )
  {
    v50 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v33 + 16LL))(v33);
  }
  return 0;
}

```

## disassembly

```asm
0x1800152f0  push    rbp
0x1800152f2  push    rbx
0x1800152f3  push    rsi
0x1800152f4  push    rdi
0x1800152f5  push    r12
0x1800152f7  push    r13
0x1800152f9  push    r14
0x1800152fb  push    r15
0x1800152fd  lea     rbp, [rsp-1Fh]
0x180015302  sub     rsp, 0A8h
0x180015309  mov     rax, cs:__security_cookie
0x180015310  xor     rax, rsp
0x180015313  mov     [rbp+57h+var_48], rax
0x180015317  mov     r12, r9
0x18001531a  mov     r15, r8
0x18001531d  mov     ebx, edx
0x18001531f  mov     [rbp+57h+var_80], edx
0x180015322  mov     [rbp+57h+var_A8], 0
0x18001532a  lea     r13, [rcx-0B0h]
0x180015331  lea     rcx, [rbp+57h+var_A8]
0x180015335  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001533a  mov     [rbp+57h+var_A8], 0
0x180015342  mov     eax, ebx
0x180015344  not     eax
0x180015346  movsxd  rdi, eax
0x180015349  xor     esi, esi
0x18001534b  mov     [rbp+57h+var_88], rsi
0x18001534f  lea     r14, [r13+130h]
0x180015356  mov     rcx, r14; SRWLock
0x180015359  call    cs:__imp_AcquireSRWLockShared
0x180015360  nop     dword ptr [rax+rax+00h]
0x180015365  mov     [rbp+57h+var_98], r14
0x180015369  lea     rbx, [r13+0F0h]
0x180015370  lea     rdx, [rbp+57h+var_70]
0x180015374  mov     rcx, rbx
0x180015377  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x18001537c  mov     r8, [rax]
0x18001537f  lea     rdx, [rbp+57h+var_78]
0x180015383  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180015388  mov     r9, rdi
0x18001538b  mov     rdx, [rax]
0x18001538e  lea     rcx, [rbp+57h+var_90]
0x180015392  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByWindow@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByWindow@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByWindow)
0x180015397  lea     rdx, [rbp+57h+var_78]
0x18001539b  mov     rcx, rbx
0x18001539e  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x1800153a3  mov     rdx, [rbp+57h+var_90]
0x1800153a7  cmp     rdx, [rax]
0x1800153aa  jz      loc_1800156C9
0x1800153b0  mov     rdi, [rdx+8]
0x1800153b4  mov     rbx, [rdx]
0x1800153b7  test    rbx, rbx
0x1800153ba  jz      short loc_1800153D3
0x1800153bc  mov     rax, [rbx]
0x1800153bf  mov     rcx, rbx
0x1800153c2  mov     rax, [rax+8]
0x1800153c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153cb  nop
0x1800153cc  mov     rsi, rbx
0x1800153cf  mov     [rbp+57h+var_88], rbx
0x1800153d3  test    r14, r14
0x1800153d6  jz      short loc_1800153E7
0x1800153d8  mov     rcx, r14; SRWLock
0x1800153db  call    cs:__imp_ReleaseSRWLockShared
0x1800153e2  nop     dword ptr [rax+rax+00h]
0x1800153e7  xor     r14d, r14d
0x1800153ea  test    rdi, rdi
0x1800153ed  jz      loc_18001577B
0x1800153f3  test    rsi, rsi
0x1800153f6  jz      short loc_180015408
0x1800153f8  mov     rax, [rsi]
0x1800153fb  mov     rcx, rsi
0x1800153fe  mov     rax, [rax+8]
0x180015402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015407  nop
0x180015408  mov     [rbp+57h+var_A8], rsi
0x18001540c  test    rsi, rsi
0x18001540f  jz      short loc_180015421
0x180015411  mov     rax, [rsi]
0x180015414  mov     rcx, rsi
0x180015417  mov     rax, [rax+10h]
0x18001541b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015420  nop
0x180015421  mov     [rbp+57h+string], r14
0x180015425  test    r15, r15
0x180015428  jz      loc_18001575F
0x18001542e  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180015432  inc     rbx
0x180015435  cmp     [r15+rbx*2], r14w
0x18001543a  jnz     short loc_180015432
0x18001543c  mov     eax, 0FFFFFFFFh
0x180015441  cmp     rbx, rax
0x180015444  ja      loc_1800156BF
0x18001544a  xor     ecx, ecx; string
0x18001544c  call    cs:__imp_WindowsDeleteString
0x180015453  nop     dword ptr [rax+rax+00h]
0x180015458  mov     edx, ebx; length
0x18001545a  mov     rcx, r15; sourceString
0x18001545d  mov     [rbp+57h+string], r14
0x180015461  lea     r8, [rbp+57h+string]; string
0x180015465  call    cs:__imp_WindowsCreateString
0x18001546c  nop     dword ptr [rax+rax+00h]
0x180015471  mov     ebx, eax
0x180015473  test    ebx, ebx
0x180015475  js      loc_180015713
0x18001547b  mov     r9, r14
0x18001547e  mov     [rbp+57h+var_A0], r14
0x180015482  test    r12, r12
0x180015485  jz      loc_1800155CB
0x18001548b  mov     [rbp+57h+var_98], r14
0x18001548f  mov     rax, [r12]
0x180015493  mov     rbx, [rax]
0x180015496  lea     rcx, [rbp+57h+var_98]
0x18001549a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001549f  lea     r8, [rbp+57h+var_98]
0x1800154a3  lea     rdx, _GUID_905a0fe0_bc53_11df_8c49_001e4fc686da
0x1800154aa  mov     rcx, r12
0x1800154ad  mov     rax, rbx
0x1800154b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b5  mov     ebx, eax
0x1800154b7  test    eax, eax
0x1800154b9  js      loc_180015795
0x1800154bf  mov     [rbp+57h+var_50], r14
0x1800154c3  lea     r9, [rbp+57h+var_50]; string
0x1800154c7  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800154cb  mov     edx, 27h ; '''; length
0x1800154d0  lea     rcx, ?RuntimeClass_Windows_Foundation_Collections_ValueSet@@3QBGB; "Windows.Foundation.Collections.ValueSet"
0x1800154d7  call    cs:__imp_WindowsCreateStringReference
0x1800154de  nop     dword ptr [rax+rax+00h]
0x1800154e3  test    eax, eax
0x1800154e5  js      loc_1800158C8
0x1800154eb  mov     rbx, [rbp+57h+var_50]
0x1800154ef  lea     rcx, [rbp+57h+var_A0]
0x1800154f3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800154f8  mov     [rbp+57h+var_A0], r14
0x1800154fc  mov     [rbp+57h+var_88], r14
0x180015500  lea     rdx, [rbp+57h+var_88]
0x180015504  mov     rcx, rbx
0x180015507  call    cs:__imp_RoActivateInstance
0x18001550e  nop     dword ptr [rax+rax+00h]
0x180015513  mov     ebx, eax
0x180015515  test    eax, eax
0x180015517  js      short loc_180015542
0x180015519  mov     r8d, 10h; Size
0x18001551f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90; Buf2
0x180015526  lea     rcx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c; Buf1
0x18001552d  call    memcmp_0
0x180015532  mov     rcx, [rbp+57h+var_88]
0x180015536  test    eax, eax
0x180015538  jnz     loc_1800156E6
0x18001553e  mov     [rbp+57h+var_A0], rcx
0x180015542  test    ebx, ebx
0x180015544  js      loc_1800158D0
0x18001554a  mov     [rbp+57h+var_90], r14
0x18001554e  lea     rcx, [rbp+57h+var_90]
0x180015552  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015557  lea     rcx, [rbp+57h+var_90]
0x18001555b  call    cs:__imp_RoCreatePropertySetSerializer
0x180015562  nop     dword ptr [rax+rax+00h]
0x180015567  mov     ebx, eax
0x180015569  test    eax, eax
0x18001556b  js      loc_1800158EA
0x180015571  mov     rcx, [rbp+57h+var_90]
0x180015575  mov     rax, [rcx]
0x180015578  mov     r8, [rbp+57h+var_98]
0x18001557c  mov     rdx, [rbp+57h+var_A0]
0x180015580  mov     rax, [rax+38h]
0x180015584  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015589  mov     ebx, eax
0x18001558b  test    eax, eax
0x18001558d  js      loc_180015815
0x180015593  mov     rcx, [rbp+57h+var_90]
0x180015597  test    rcx, rcx
0x18001559a  jz      short loc_1800155AD
0x18001559c  mov     [rbp+57h+var_90], r14
0x1800155a0  mov     rax, [rcx]
0x1800155a3  mov     rax, [rax+10h]
0x1800155a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155ac  nop
0x1800155ad  mov     rcx, [rbp+57h+var_98]
0x1800155b1  test    rcx, rcx
0x1800155b4  jz      short loc_1800155C7
0x1800155b6  mov     [rbp+57h+var_98], r14
0x1800155ba  mov     rax, [rcx]
0x1800155bd  mov     rax, [rax+10h]
0x1800155c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800155c6  nop
0x1800155c7  mov     r9, [rbp+57h+var_A0]; struct Windows::Foundation::Collections::IPropertySet *
0x1800155cb  mov     rdx, [rbp+57h+var_A8]
0x1800155cf  mov     rcx, r13; this
0x1800155d2  test    rdx, rdx
0x1800155d5  jz      loc_180015918
0x1800155db  mov     qword ptr [rsp+0E0h+var_C0], r9; int
0x1800155e0  mov     r9, [rbp+57h+string]
0x1800155e4  mov     r8d, 2
0x1800155ea  call    ?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z; CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)
0x1800155ef  mov     rcx, [rbp+5Fh]; this
0x1800155f3  test    eax, eax
0x1800155f5  js      loc_1800158AF
0x1800155fb  mov     rcx, [rbp+57h+var_A0]
0x1800155ff  test    rcx, rcx
0x180015602  jz      short loc_180015615
0x180015604  mov     [rbp+57h+var_A0], r14
0x180015608  mov     rax, [rcx]
0x18001560b  mov     rax, [rax+10h]
0x18001560f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015614  nop
0x180015615  mov     rcx, [rbp+57h+string]; string
0x180015619  call    cs:__imp_WindowsDeleteString
0x180015620  nop     dword ptr [rax+rax+00h]
0x180015625  mov     [rbp+57h+string], r14
0x180015629  mov     rcx, [rbp+57h+var_A8]
0x18001562d  test    rcx, rcx
0x180015630  jz      short loc_180015643
0x180015632  mov     [rbp+57h+var_A8], r14
0x180015636  mov     rax, [rcx]
0x180015639  mov     rax, [rax+10h]
0x18001563d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015642  nop
0x180015643  xor     eax, eax
0x180015645  jmp     short loc_18001569E
0x180015647  mov     rcx, [rbp+5Fh]; this
0x18001564b  mov     r9d, ebx; char *
0x18001564e  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x180015655  mov     edx, 4C4h; void *
0x18001565a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001565f  nop
0x180015660  lea     rcx, [rbp+57h+var_88]
0x180015664  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180015669  mov     rcx, [rbp+5Fh]; this
0x18001566d  mov     r9d, ebx; char *
0x180015670  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x180015677  mov     edx, 354h; void *
0x18001567c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015681  nop
0x180015682  mov     rcx, [rbp+57h+var_A8]
0x180015686  test    rcx, rcx
0x180015689  jz      short loc_18001569C
0x18001568b  mov     [rbp+57h+var_A8], r14
0x18001568f  mov     rax, [rcx]
0x180015692  mov     rax, [rax+10h]
0x180015696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001569b  nop
0x18001569c  mov     eax, ebx
0x18001569e  mov     rcx, [rbp+57h+var_48]
0x1800156a2  xor     rcx, rsp; StackCookie
0x1800156a5  call    __security_check_cookie
0x1800156aa  add     rsp, 0A8h
0x1800156b1  pop     r15
0x1800156b3  pop     r14
0x1800156b5  pop     r13
0x1800156b7  pop     r12
0x1800156b9  pop     rdi
0x1800156ba  pop     rsi
0x1800156bb  pop     rbx
0x1800156bc  pop     rbp
0x1800156bd  retn
0x1800156bf  mov     ebx, 80070216h
0x1800156c4  jmp     loc_180015473
0x1800156c9  test    r14, r14
0x1800156cc  jz      short loc_1800156DE
0x1800156ce  mov     rcx, r14; SRWLock
0x1800156d1  call    cs:__imp_ReleaseSRWLockShared
0x1800156d8  nop     dword ptr [rax+rax+00h]
0x1800156dd  nop
0x1800156de  xor     r14d, r14d
0x1800156e1  jmp     loc_180015421
0x1800156e6  mov     rax, [rcx]
0x1800156e9  lea     r8, [rbp+57h+var_A0]
0x1800156ed  lea     rdx, _GUID_8a43ed9f_f4e6_4421_acf9_1dab2986820c
0x1800156f4  mov     rax, [rax]
0x1800156f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156fc  mov     ebx, eax
0x1800156fe  mov     rcx, [rbp+57h+var_88]
0x180015702  mov     rax, [rcx]
0x180015705  mov     rax, [rax+10h]
0x180015709  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001570e  jmp     loc_180015542
0x180015713  mov     rcx, [rbp+5Fh]; this
0x180015717  mov     r9d, ebx; char *
0x18001571a  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x180015721  mov     edx, 357h; void *
0x180015726  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001572b  nop
0x18001572c  mov     rcx, [rbp+57h+string]; string
0x180015730  call    cs:__imp_WindowsDeleteString
0x180015737  nop     dword ptr [rax+rax+00h]
0x18001573c  mov     [rbp+57h+string], r14
0x180015740  mov     rcx, [rbp+57h+var_A8]
0x180015744  test    rcx, rcx
0x180015747  jz      short loc_18001575A
0x180015749  mov     [rbp+57h+var_A8], r14
0x18001574d  mov     rax, [rcx]
0x180015750  mov     rax, [rax+10h]
0x180015754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015759  nop
0x18001575a  jmp     loc_18001569C
0x18001575f  xor     ecx, ecx; string
0x180015761  call    cs:__imp_WindowsDeleteString
0x180015768  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
