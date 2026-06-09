# AppReadinessAwaiter::AppReadinessAwaiter(void *)

- ea: `0x1800150ac`
- end: `0x18001526a`
- name: `??0AppReadinessAwaiter@@QEAA@PEAX@Z`
- size: `446`
- prototype: `AppReadinessAwaiter *__fastcall(AppReadinessAwaiter *__hidden this, void *)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x18000b50c`
- `0x18000c520`
- `0x18000fd08`
- `0x180010150`
- `0x180012f10`
- `0x1800146cc`
- `0x180014d48`
- `0x1800150ac`
- `0x1800156e8`
- `0x18001719c`
- `0x180017394`
- `0x180034240`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800151ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800151ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015168`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015128`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180015168`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800151de`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x1800151de`

## string_xrefs

- `0x18001514d`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x1800151a6`: `onecoreuap\enduser\winstore\installservice\lib\scanforupdatesworker.cpp`
- `0x180015185`: `AppReadiness cancel event set for UserSid: %s.`
- `0x180015199`: `AppReadinessAwaiter::AppReadinessAwaiter`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
AppReadinessAwaiter *__fastcall AppReadinessAwaiter::AppReadinessAwaiter(AppReadinessAwaiter *this, void *a2)
{
  void *v2; // rdi
  wil::details **v3; // rbx
  AppReadinessInfoAPI *StringRawBuffer; // rax
  enum USER_STATE *v5; // r8
  int UserState; // eax
  void *v7; // rdx
  const char *v8; // r9
  char *v9; // rax
  char *v10; // rcx
  int v12; // [rsp+20h] [rbp-88h]
  char *v13; // [rsp+50h] [rbp-58h]
  char *v15; // [rsp+58h] [rbp-50h]
  HKEY phkResult; // [rsp+60h] [rbp-48h] BYREF
  HANDLE Handles[2]; // [rsp+68h] [rbp-40h] BYREF
  char *v19; // [rsp+78h] [rbp-30h] BYREF
  char *v20; // [rsp+80h] [rbp-28h]
  __int64 v21; // [rsp+88h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]
  int v28; // [rsp+C0h] [rbp+18h] BYREF
  HSTRING string; // [rsp+C8h] [rbp+20h] BYREF

  v2 = a2;
  v3 = (wil::details **)this;
  v28 = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    this,
    &v28);
  try
  {
    Registry::OpenKeyForRead<Registry::NotFoundPolicy::Throw>(&phkResult);
    TokenHelpers::GetAllLoggedInUserTokens(&v19);
    v9 = v19;
    v10 = v20;
    v15 = v20;
    while ( 2 )
    {
      v13 = v9;
      if ( v9 != v10 )
      {
        try
        {
          TokenHelpers::GetTokenSid(&string, v9);
          StringRawBuffer = (AppReadinessInfoAPI *)WindowsGetStringRawBuffer(string, 0);
          UserState = AppReadinessInfoAPI::GetUserState(StringRawBuffer, (const unsigned __int16 *)&v28, v5);
          if ( UserState < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x1FA,
              (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
              (const char *)(unsigned int)UserState,
              v12);
          WindowsGetStringRawBuffer(string, 0);
          LogMessage(
            3u,
            "onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
            0x1FCu,
            "AppReadinessAwaiter::AppReadinessAwaiter",
            -1,
            L"AppReadiness cancel event set for UserSid: %s.",
            0,
            0);
          wil::details::SetEvent(*v3, v7);
          Handles[0] = v2;
          Handles[1] = *v3;
          WaitForMultipleObjects(2u, Handles, 0, 0x493E0u);
          WindowsDeleteString(string);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x205,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
            v8);
          v9 = v13 + 16;
          v3 = (wil::details **)this;
          v2 = a2;
          v10 = v15;
          continue;
        }
      }
      break;
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x206,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      v8);
    return this;
  }
  if ( v19 )
  {
    std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(
      v19,
      v20);
    std::_Deallocate<16>(v19, (struct std::nothrow_t *)((v21 - (_QWORD)v19) & 0xFFFFFFFFFFFFFFF0uLL));
  }
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
  return (AppReadinessAwaiter *)v3;
}

```

## disassembly

```asm
0x1800150ac  mov     rax, rsp
0x1800150af  mov     [rax+10h], rdx
0x1800150b3  mov     [rax+8], rcx
0x1800150b7  push    rbx
0x1800150b8  push    rdi
0x1800150b9  sub     rsp, 98h
0x1800150c0  mov     rdi, rdx
0x1800150c3  mov     rbx, rcx
0x1800150c6  mov     dword ptr [rax+18h], 1
0x1800150cd  lea     rdx, [rax+18h]
0x1800150d1  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x1800150d6  nop
0x1800150d7  lea     rcx, [rsp+0A8h+phkResult]; phkResult
0x1800150dc  call    ??$OpenKeyForRead@UThrow@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForRead<Registry::NotFoundPolicy::Throw>(HKEY__ *,ushort const *)
0x1800150e1  nop
0x1800150e2  lea     rcx, [rsp+0A8h+var_30]
0x1800150e7  call    ?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; TokenHelpers::GetAllLoggedInUserTokens(void)
0x1800150ec  nop
0x1800150ed  mov     rax, [rsp+0A8h+var_30]
0x1800150f2  mov     rcx, [rsp+0A8h+var_28]
0x1800150fa  mov     [rsp+0A8h+var_50], rcx
0x1800150ff  mov     [rsp+0A8h+var_58], rax
0x180015104  cmp     rax, rcx
0x180015107  jz      loc_1800151F4
0x18001510d  mov     rdx, rax
0x180015110  lea     rcx, [rsp+0A8h+string]
0x180015118  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x18001511d  nop
0x18001511e  xor     edx, edx; length
0x180015120  mov     rcx, [rsp+0A8h+string]; string
0x180015128  call    cs:__imp_WindowsGetStringRawBuffer
0x18001512e  lea     rdx, [rsp+0A8h+arg_10]; unsigned __int16 *
0x180015136  mov     rcx, rax; this
0x180015139  call    ?GetUserState@AppReadinessInfoAPI@@YAJPEBGPEAW4USER_STATE@@@Z; AppReadinessInfoAPI::GetUserState(ushort const *,USER_STATE *)
0x18001513e  mov     rcx, [rsp+0A8h]; this
0x180015146  test    eax, eax
0x180015148  jns     short loc_18001515E
0x18001514a  mov     r9d, eax; char *
0x18001514d  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x180015154  mov     edx, 1FAh; void *
0x180015159  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001515e  xor     edx, edx; length
0x180015160  mov     rcx, [rsp+0A8h+string]; string
0x180015168  call    cs:__imp_WindowsGetStringRawBuffer
0x18001516e  mov     [rsp+0A8h+var_68], rax
0x180015173  mov     [rsp+0A8h+var_70], 0; unsigned __int16 *
0x18001517c  mov     [rsp+0A8h+var_78], 0; char *
0x180015185  lea     rax, aAppreadinessCa; "AppReadiness cancel event set for UserS"...
0x18001518c  mov     [rsp+0A8h+var_80], rax; unsigned __int16 *
0x180015191  mov     [rsp+0A8h+var_88], 0FFFFFFFFh; int
0x180015199  lea     r9, aAppreadinessaw; "AppReadinessAwaiter::AppReadinessAwaite"...
0x1800151a0  mov     r8d, 1FCh; unsigned int
0x1800151a6  lea     rdx, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\installs"...
0x1800151ad  mov     ecx, 3; unsigned int
0x1800151b2  call    ?LogMessage@@YAXIPEBDI0JPEBG01ZZ; LogMessage(uint,char const *,uint,char const *,long,ushort const *,char const *,ushort const *,...)
0x1800151b7  mov     rcx, [rbx]; this
0x1800151ba  call    ?SetEvent@details@wil@@YAXPEAX@Z; wil::details::SetEvent(void *)
0x1800151bf  mov     [rsp+0A8h+Handles], rdi
0x1800151c4  mov     rax, [rbx]
0x1800151c7  mov     [rsp+0A8h+var_38], rax
0x1800151cc  mov     r9d, 493E0h; dwMilliseconds
0x1800151d2  xor     r8d, r8d; bWaitAll
0x1800151d5  lea     rdx, [rsp+0A8h+Handles]; lpHandles
0x1800151da  lea     ecx, [r8+2]; nCount
0x1800151de  call    cs:__imp_WaitForMultipleObjects
0x1800151e4  nop
0x1800151e5  mov     rcx, [rsp+0A8h+string]; string
0x1800151ed  call    cs:__imp_WindowsDeleteString
0x1800151f3  nop
0x1800151f4  mov     rcx, [rsp+0A8h+var_30]
0x1800151f9  test    rcx, rcx
0x1800151fc  jz      short loc_180015225
0x1800151fe  mov     rdx, [rsp+0A8h+var_28]
0x180015206  call    ??$_Destroy_range@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>> &)
0x18001520b  mov     rcx, [rsp+0A8h+var_30]
0x180015210  mov     rdx, [rsp+0A8h+var_20]
0x180015218  sub     rdx, rcx
0x18001521b  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18001521f  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180015224  nop
0x180015225  lea     rcx, [rsp+0A8h+phkResult]
0x18001522a  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18001522f  nop
0x180015230  jmp     short loc_18001525D
0x180015232  mov     rax, [rsp+0A8h+var_58]
0x180015237  add     rax, 10h
0x18001523b  mov     rbx, [rsp+0A8h+arg_0]
0x180015243  mov     rdi, [rsp+0A8h+arg_8]
0x18001524b  mov     rcx, [rsp+0A8h+var_50]
0x180015250  jmp     loc_1800150FF
0x180015255  mov     rbx, [rsp+0A8h+arg_0]
0x18001525d  mov     rax, rbx
0x180015260  add     rsp, 98h
0x180015267  pop     rdi
0x180015268  pop     rbx
0x180015269  retn
```
