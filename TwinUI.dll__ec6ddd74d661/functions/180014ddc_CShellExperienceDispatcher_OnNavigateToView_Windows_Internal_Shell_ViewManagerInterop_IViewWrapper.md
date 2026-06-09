# CShellExperienceDispatcher::_OnNavigateToView(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)

- ea: `0x180014ddc`
- end: `0x1800150f6`
- name: `?_OnNavigateToView@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(CShellExperienceDispatcher *__hidden this, struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x180013960`

## callees

- `0x180009dfc`
- `0x180014ddc`
- `0x18001597c`
- `0x180016064`
- `0x180016078`
- `0x18001bbdc`
- `0x1800378dc`
- `0x1800884d8`
- `0x1800b2368`
- `0x1800c134c`
- `0x1800f5534`
- `0x180151f64`
- `0x180151fbc`
- `0x180152010`
- `0x1803bb010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014ee6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014f3d`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014ee6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x180014f3d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014e10`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x180014e10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ece`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014fdb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180014ff8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180015041`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015012`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180015012`

## string_xrefs

- `0x180014eb8`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x18001502b`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`
- `0x1800150c6`: `onecoreuap\shell\onecore\coreexperiencebrokercomponents\shellexperiencedispatcher\lib\shellexperiencedispatcher.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CShellExperienceDispatcher::_OnNavigateToView(
        RTL_SRWLOCK *this,
        struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *a2)
{
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v2; // rdi
  CShellExperienceDispatcher *v3; // rsi
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v4; // r14
  RTL_SRWLOCK *v5; // r15
  _QWORD *v6; // rax
  __int64 v7; // rcx
  _QWORD *v8; // rax
  __int64 v9; // r8
  HSTRING **v10; // rax
  HSTRING *v11; // rbx
  char v12; // r13
  HSTRING *v13; // r12
  HSTRING v14; // rsi
  __int64 (__fastcall *v15)(HSTRING, HSTRING *); // rdi
  int v16; // eax
  unsigned int v17; // edi
  RTL_SRWLOCK *v19; // rdi
  _QWORD *v20; // rax
  __int64 v21; // rcx
  _QWORD *v22; // rax
  __int64 v23; // r8
  HSTRING **v24; // rax
  _QWORD *v25; // rax
  __int64 v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // r8
  RTL_SRWLOCK **v29; // rax
  HSTRING *v30; // rdi
  HRESULT v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  int v34; // [rsp+20h] [rbp-48h]
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v35; // [rsp+30h] [rbp-38h] BYREF
  HSTRING *v36; // [rsp+38h] [rbp-30h] BYREF
  RTL_SRWLOCK *v37; // [rsp+40h] [rbp-28h] BYREF
  char v38[8]; // [rsp+48h] [rbp-20h] BYREF
  _BYTE v39[24]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+40h]
  RTL_SRWLOCK *v41; // [rsp+B0h] [rbp+48h] BYREF
  struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *v42; // [rsp+B8h] [rbp+50h]
  HSTRING string; // [rsp+C0h] [rbp+58h] BYREF
  HSTRING *v44; // [rsp+C8h] [rbp+60h] BYREF

  v42 = a2;
  v41 = this;
  v2 = a2;
  v3 = (CShellExperienceDispatcher *)this;
  v4 = 0;
  v35 = 0;
  v5 = this + 38;
  AcquireSRWLockShared(this + 38);
  v37 = v5;
  v6 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                   (char *)v3 + 240,
                   &string);
  v8 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                   v7,
                   &v44,
                   *v6);
  std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(
    &v36,
    *v8,
    v9,
    v2);
  v10 = (HSTRING **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                      (char *)v3 + 240,
                      &string);
  v11 = v36;
  if ( v36 == *v10 )
  {
    v12 = 0;
  }
  else
  {
    v12 = 1;
    v13 = v36 + 1;
    if ( !v36[1] )
    {
      string = 0;
      v14 = *v36;
      v15 = *(__int64 (__fastcall **)(HSTRING, HSTRING *))(*(_QWORD *)*v36 + 56LL);
      WindowsDeleteString(0);
      string = 0;
      v16 = v15(v14, &string);
      v17 = v16;
      if ( v16 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x300,
          (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shel"
                        "lexperiencedispatcher.cpp",
          (const char *)(unsigned int)v16,
          v34);
        WindowsDeleteString(string);
        string = 0;
        if ( v5 )
          ReleaseSRWLockShared(v5);
        return v17;
      }
      v3 = (CShellExperienceDispatcher *)v41;
      v19 = v41 + 27;
      v20 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                        &v41[27],
                        &v41);
      v22 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                        v21,
                        v38,
                        *v20);
      std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceListener_______lambda_d98ce7ba9d50f524bf721f54c5296cbc___(
        &v44,
        *v22,
        v23,
        &string);
      v24 = (HSTRING **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                          v19,
                          &v41);
      if ( v44 != *v24 )
      {
        v25 = (_QWORD *)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                          (char *)v3 + 240,
                          v38);
        v27 = (_QWORD *)std::_Tree<std::_Tmap_traits<unsigned long,std::unique_ptr<SmartCookie>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::unique_ptr<SmartCookie>>>,0>>::end(
                          v26,
                          v39,
                          *v25);
        std::find_if_std::_Vector_iterator_std::_Vector_val_std::_Simple_types_ShellExperienceView_______lambda_0012612325cc5d9ae02f7451c73fbada___(
          &v41,
          *v27,
          v28,
          &v44);
        v29 = (RTL_SRWLOCK **)std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(
                                (char *)v3 + 240,
                                v39);
        if ( v41 == *v29 )
        {
          v30 = v44;
          WindowsDeleteString(*v13);
          *v13 = 0;
          v31 = WindowsDuplicateString(*v30, v11 + 1);
          v17 = v31;
          if ( v31 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x315,
              (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\"
                            "shellexperiencedispatcher.cpp",
              (const char *)(unsigned int)v31,
              v34);
            WindowsDeleteString(string);
            string = 0;
            wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(&v37);
LABEL_26:
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
            return v17;
          }
          Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(&v35, v11);
          *(_BYTE *)(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ViewSizePair>>>::operator->(&v36) + 16) = 1;
          v4 = v35;
        }
      }
      WindowsDeleteString(string);
      v2 = v42;
    }
  }
  if ( v5 )
    ReleaseSRWLockShared(v5);
  if ( !v12 )
  {
    v32 = CShellExperienceDispatcher::_OnViewCreated(v3, v2);
    v17 = v32;
    if ( v32 < 0 )
    {
      v33 = 803;
LABEL_25:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v33,
        (unsigned int)"onecoreuap\\shell\\onecore\\coreexperiencebrokercomponents\\shellexperiencedispatcher\\lib\\shelle"
                      "xperiencedispatcher.cpp",
        (const char *)(unsigned int)v32,
        v34);
      goto LABEL_26;
    }
  }
  if ( v4 )
  {
    v32 = CShellExperienceDispatcher::_NotifyListener((__int64)v3, (__int64)v4, 0, 0, 0);
    v17 = v32;
    if ( v32 < 0 )
    {
      v33 = 808;
      goto LABEL_25;
    }
    CShellExperienceDispatcher::_FlushQueuedEvents(v3, v4);
  }
  if ( v4 )
    (*(void (__fastcall **)(struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *))(*(_QWORD *)v4 + 16LL))(v4);
  return 0;
}

```

## disassembly

```asm
0x180014ddc  mov     [rsp-40h+arg_8], rdx
0x180014de1  mov     [rsp-40h+arg_0], rcx
0x180014de6  push    rbp
0x180014de7  push    rbx
0x180014de8  push    rsi
0x180014de9  push    rdi
0x180014dea  push    r12
0x180014dec  push    r13
0x180014dee  push    r14
0x180014df0  push    r15
0x180014df2  mov     rbp, rsp
0x180014df5  sub     rsp, 68h
0x180014df9  mov     rdi, rdx
0x180014dfc  mov     rsi, rcx
0x180014dff  xor     r14d, r14d
0x180014e02  mov     [rbp+var_38], r14
0x180014e06  lea     r15, [rcx+130h]
0x180014e0d  mov     rcx, r15; SRWLock
0x180014e10  call    cs:__imp_AcquireSRWLockShared
0x180014e17  nop     dword ptr [rax+rax+00h]
0x180014e1c  mov     [rbp+var_28], r15
0x180014e20  lea     rbx, [rsi+0F0h]
0x180014e27  lea     rdx, [rbp+string]
0x180014e2b  mov     rcx, rbx
0x180014e2e  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014e33  mov     r8, [rax]
0x180014e36  lea     rdx, [rbp+arg_18]
0x180014e3a  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180014e3f  mov     r9, rdi
0x180014e42  mov     rdx, [rax]
0x180014e45  lea     rcx, [rbp+var_30]
0x180014e49  call    ??$find_if@V?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@std@@VShellExperienceViewFindByView@@@std@@YA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UShellExperienceView@@@std@@@std@@@0@V10@V10@VShellExperienceViewFindByView@@@Z; std::find_if<std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView>(std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ShellExperienceView>>>,ShellExperienceViewFindByView)
0x180014e4e  lea     rdx, [rbp+string]
0x180014e52  mov     rcx, rbx
0x180014e55  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014e5a  mov     rbx, [rbp+var_30]
0x180014e5e  cmp     rbx, [rax]
0x180014e61  jz      loc_180014EF7
0x180014e67  mov     r13b, 1
0x180014e6a  lea     r12, [rbx+8]
0x180014e6e  cmp     [r12], r14
0x180014e72  jnz     loc_180014EFA
0x180014e78  mov     [rbp+string], r14
0x180014e7c  mov     rsi, [rbx]
0x180014e7f  mov     rax, [rsi]
0x180014e82  mov     rdi, [rax+38h]
0x180014e86  xor     ecx, ecx; string
0x180014e88  call    cs:__imp_WindowsDeleteString
0x180014e8f  nop     dword ptr [rax+rax+00h]
0x180014e94  mov     [rbp+string], r14
0x180014e98  lea     rdx, [rbp+string]
0x180014e9c  mov     rcx, rsi
0x180014e9f  mov     rax, rdi
0x180014ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ea7  mov     edi, eax
0x180014ea9  test    eax, eax
0x180014eab  jns     loc_180014F4B
0x180014eb1  mov     rcx, [rbp+40h]; this
0x180014eb5  mov     r9d, eax; char *
0x180014eb8  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x180014ebf  mov     edx, 300h; void *
0x180014ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014ec9  nop
0x180014eca  mov     rcx, [rbp+string]; string
0x180014ece  call    cs:__imp_WindowsDeleteString
0x180014ed5  nop     dword ptr [rax+rax+00h]
0x180014eda  mov     [rbp+string], r14
0x180014ede  test    r15, r15
0x180014ee1  jz      short loc_180014EF3
0x180014ee3  mov     rcx, r15; SRWLock
0x180014ee6  call    cs:__imp_ReleaseSRWLockShared
0x180014eed  nop     dword ptr [rax+rax+00h]
0x180014ef2  nop
0x180014ef3  mov     eax, edi
0x180014ef5  jmp     short loc_180014F28
0x180014ef7  xor     r13b, r13b
0x180014efa  test    r15, r15
0x180014efd  jnz     short loc_180014F3A
0x180014eff  test    r13b, r13b
0x180014f02  jz      loc_180015082
0x180014f08  test    r14, r14
0x180014f0b  jnz     loc_18001509E
0x180014f11  test    r14, r14
0x180014f14  jz      short loc_180014F26
0x180014f16  mov     rax, [r14]
0x180014f19  mov     rcx, r14
0x180014f1c  mov     rax, [rax+10h]
0x180014f20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f25  nop
0x180014f26  xor     eax, eax
0x180014f28  add     rsp, 68h
0x180014f2c  pop     r15
0x180014f2e  pop     r14
0x180014f30  pop     r13
0x180014f32  pop     r12
0x180014f34  pop     rdi
0x180014f35  pop     rsi
0x180014f36  pop     rbx
0x180014f37  pop     rbp
0x180014f38  retn
0x180014f3a  mov     rcx, r15; SRWLock
0x180014f3d  call    cs:__imp_ReleaseSRWLockShared
0x180014f44  nop     dword ptr [rax+rax+00h]
0x180014f49  jmp     short loc_180014EFF
0x180014f4b  mov     rsi, [rbp+arg_0]
0x180014f4f  lea     rdi, [rsi+0D8h]
0x180014f56  lea     rdx, [rbp+arg_0]
0x180014f5a  mov     rcx, rdi
0x180014f5d  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014f62  mov     r8, [rax]
0x180014f65  lea     rdx, [rbp+var_20]
0x180014f69  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180014f6e  lea     r9, [rbp+string]
0x180014f72  mov     rdx, [rax]
0x180014f75  lea     rcx, [rbp+arg_18]
0x180014f79  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceListener_______lambda_d98ce7ba9d50f524bf721f54c5296cbc___
0x180014f7e  lea     rdx, [rbp+arg_0]
0x180014f82  mov     rcx, rdi
0x180014f85  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014f8a  mov     rcx, [rax]
0x180014f8d  cmp     [rbp+arg_18], rcx
0x180014f91  jz      short loc_180014FD7
0x180014f93  lea     rdx, [rbp+var_20]
0x180014f97  lea     rdi, [rsi+0F0h]
0x180014f9e  mov     rcx, rdi
0x180014fa1  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014fa6  mov     r8, [rax]
0x180014fa9  lea     rdx, [rbp+var_18]
0x180014fad  call    ?end@?$_Tree@V?$_Tmap_traits@KV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKV?$unique_ptr@VSmartCookie@@U?$default_delete@VSmartCookie@@@std@@@std@@@std@@@std@@@std@@@2@XZ; std::_Tree<std::_Tmap_traits<ulong,std::unique_ptr<SmartCookie>,std::less<ulong>,std::allocator<std::pair<ulong const,std::unique_ptr<SmartCookie>>>,0>>::end(void)
0x180014fb2  lea     r9, [rbp+arg_18]
0x180014fb6  mov     rdx, [rax]
0x180014fb9  lea     rcx, [rbp+arg_0]
0x180014fbd  call    std__find_if_std___Vector_iterator_std___Vector_val_std___Simple_types_ShellExperienceView_______lambda_0012612325cc5d9ae02f7451c73fbada___
0x180014fc2  lea     rdx, [rbp+var_18]
0x180014fc6  mov     rcx, rdi
0x180014fc9  call    ?end@?$vector@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@V?$allocator@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@2@@std@@QEAA?AV?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@V?$shared_ptr@UHostedApplicationActivationContext@HostedApplicationExperienceManager@@@std@@@std@@@std@@@2@XZ; std::vector<std::shared_ptr<HostedApplicationExperienceManager::HostedApplicationActivationContext>>::end(void)
0x180014fce  mov     rcx, [rax]
0x180014fd1  cmp     [rbp+arg_0], rcx
0x180014fd5  jz      short loc_180014FF0
0x180014fd7  mov     rcx, [rbp+string]; string
0x180014fdb  call    cs:__imp_WindowsDeleteString
0x180014fe2  nop     dword ptr [rax+rax+00h]
0x180014fe7  mov     rdi, [rbp+arg_8]
0x180014feb  jmp     loc_180014EFA
0x180014ff0  mov     rdi, [rbp+arg_18]
0x180014ff4  mov     rcx, [r12]; string
0x180014ff8  call    cs:__imp_WindowsDeleteString
0x180014fff  nop     dword ptr [rax+rax+00h]
0x180015004  mov     qword ptr [r12], 0
0x18001500c  mov     rdx, r12; newString
0x18001500f  mov     rcx, [rdi]; string
0x180015012  call    cs:__imp_WindowsDuplicateString
0x180015019  nop     dword ptr [rax+rax+00h]
0x18001501e  mov     edi, eax
0x180015020  test    eax, eax
0x180015022  jns     short loc_180015060
0x180015024  mov     rcx, [rbp+40h]; this
0x180015028  mov     r9d, eax; char *
0x18001502b  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x180015032  mov     edx, 315h; void *
0x180015037  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001503c  nop
0x18001503d  mov     rcx, [rbp+string]; string
0x180015041  call    cs:__imp_WindowsDeleteString
0x180015048  nop     dword ptr [rax+rax+00h]
0x18001504d  mov     [rbp+string], 0
0x180015055  lea     rcx, [rbp+var_28]
0x180015059  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockShared@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockShared(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>>(void)
0x18001505e  jmp     short loc_1800150D7
0x180015060  mov     rdx, rbx
0x180015063  lea     rcx, [rbp+var_38]
0x180015067  call    ??4?$ComPtr@VCMarshalStream@CMarshaledInterface@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream>::operator=(Microsoft::WRL::ComPtr<CMarshaledInterface::CMarshalStream> const &)
0x18001506c  lea     rcx, [rbp+var_30]
0x180015070  call    ??C?$_Vector_iterator@V?$_Vector_val@U?$_Simple_types@UViewSizePair@@@std@@@std@@@std@@QEBAPEAUViewSizePair@@XZ; std::_Vector_iterator<std::_Vector_val<std::_Simple_types<ViewSizePair>>>::operator->(void)
0x180015075  mov     [rax+10h], r13b
0x180015079  mov     r14, [rbp+var_38]
0x18001507d  jmp     loc_180014FD7
0x180015082  mov     rdx, rdi; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x180015085  mov     rcx, rsi; this
0x180015088  call    ?_OnViewCreated@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; CShellExperienceDispatcher::_OnViewCreated(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x18001508d  mov     edi, eax
0x18001508f  test    eax, eax
0x180015091  jns     loc_180014F08
0x180015097  mov     edx, 323h
0x18001509c  jmp     short loc_1800150C3
0x18001509e  mov     qword ptr [rsp+68h+var_48], 0; int
0x1800150a7  xor     r9d, r9d
0x1800150aa  xor     r8d, r8d
0x1800150ad  mov     rdx, r14
0x1800150b0  mov     rcx, rsi
0x1800150b3  call    ?_NotifyListener@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@W4ShellExperienceViewState@Experience@456@PEAUHSTRING__@@PEAUIPropertySet@Collections@Foundation@6@@Z; CShellExperienceDispatcher::_NotifyListener(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *,Windows::Internal::Shell::Experience::ShellExperienceViewState,HSTRING__ *,Windows::Foundation::Collections::IPropertySet *)
0x1800150b8  mov     edi, eax
0x1800150ba  test    eax, eax
0x1800150bc  jns     short loc_1800150E5
0x1800150be  mov     edx, 328h; void *
0x1800150c3  mov     r9d, eax; char *
0x1800150c6  lea     r8, aOnecoreuapShel_1; "onecoreuap\\shell\\onecore\\coreexperie"...
0x1800150cd  mov     rcx, [rbp+40h]; this
0x1800150d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800150d6  nop
0x1800150d7  lea     rcx, [rbp+var_38]
0x1800150db  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800150e0  jmp     loc_180014EF3
0x1800150e5  mov     rdx, r14; struct Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *
0x1800150e8  mov     rcx, rsi; this
0x1800150eb  call    ?_FlushQueuedEvents@CShellExperienceDispatcher@@AEAAJPEAUIViewWrapper@ViewManagerInterop@Shell@Internal@Windows@@@Z; CShellExperienceDispatcher::_FlushQueuedEvents(Windows::Internal::Shell::ViewManagerInterop::IViewWrapper *)
0x1800150f0  jmp     loc_180014F11
```
