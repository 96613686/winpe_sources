# Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager____Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____::_)(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs__)_::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____lambda_9457df648bd98a661435affe263029da___1_Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___::Invoke

- ea: `0x180008790`
- end: `0x180008878`
- name: `Microsoft::WRL::Details::DelegateArgTraits_long_(__cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager____Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____::_)(Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs__)_::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____lambda_9457df648bd98a661435affe263029da___1_Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___::Invoke`
- size: `232`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180007454`
- `0x180008790`
- `0x1800092a4`
- `0x18000a374`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008822`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180008822`

## string_xrefs

- `0x1800087d7`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::DelegateArgTraits_long____cdecl_Windows::Foundation::ITypedEventHandler_impl_Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager____Windows::Foundation::Internal::AggregateType_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____::___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs____::DelegateInvokeHelper_Windows::Foundation::ITypedEventHandler_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____lambda_9457df648bd98a661435affe263029da___1_Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::ICoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs___::Invoke(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rcx
  void **v7; // rax
  void *v8; // rcx
  __int64 v9; // r8
  const char *v10; // r9
  __int64 v11; // rcx
  int v13[2]; // [rsp+20h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)v13 = 0;
  v4 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)a3 + 48LL))(a3, v13);
  v5 = v4;
  if ( v4 >= 0 )
  {
    v7 = *(void ***)(a1 + 16);
    if ( v7 )
      v8 = *v7;
    else
      v8 = 0;
    if ( !SetEvent(v8) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
    v11 = *(_QWORD *)v13;
    if ( *(_QWORD *)v13 )
    {
      *(_QWORD *)v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7F,
      (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v4);
    v6 = *(_QWORD *)v13;
    if ( *(_QWORD *)v13 )
    {
      *(_QWORD *)v13 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
    }
    Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(v5);
  }
  return v5;
}

```

## disassembly

```asm
0x180008790  mov     [rsp+arg_8], rbx
0x180008795  push    rdi
0x180008796  sub     rsp, 30h
0x18000879a  mov     rax, cs:__security_cookie
0x1800087a1  xor     rax, rsp
0x1800087a4  mov     [rsp+38h+var_10], rax
0x1800087a9  mov     rdi, rcx
0x1800087ac  mov     qword ptr [rsp+38h+var_18], 0; int
0x1800087b5  mov     rax, [r8]
0x1800087b8  lea     rdx, [rsp+38h+var_18]
0x1800087bd  mov     rcx, r8
0x1800087c0  mov     rax, [rax+30h]
0x1800087c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087c9  mov     ebx, eax
0x1800087cb  test    eax, eax
0x1800087cd  jns     short loc_180008812
0x1800087cf  mov     rcx, [rsp+38h]; this
0x1800087d4  mov     r9d, eax; char *
0x1800087d7  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x1800087de  mov     edx, 7Fh; void *
0x1800087e3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800087e8  nop
0x1800087e9  mov     rcx, qword ptr [rsp+38h+var_18]
0x1800087ee  test    rcx, rcx
0x1800087f1  jz      short loc_180008809
0x1800087f3  mov     qword ptr [rsp+38h+var_18], 0
0x1800087fc  mov     rax, [rcx]
0x1800087ff  mov     rax, [rax+10h]
0x180008803  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008808  nop
0x180008809  mov     ecx, ebx
0x18000880b  call    ?EnsureStackSnapshot@?$DelegateTraits@$0?0@WRL@Microsoft@@SAXJ@Z; Microsoft::WRL::DelegateTraits<-1>::EnsureStackSnapshot(long)
0x180008810  jmp     short loc_180008853
0x180008812  mov     rax, [rdi+10h]
0x180008816  test    rax, rax
0x180008819  jz      short loc_180008820
0x18000881b  mov     rcx, [rax]
0x18000881e  jmp     short loc_180008822
0x180008820  xor     ecx, ecx; hEvent
0x180008822  call    cs:__imp_SetEvent
0x180008828  mov     rcx, [rsp+38h]; this
0x18000882d  test    eax, eax
0x18000882f  jz      short loc_18000886D
0x180008831  mov     rcx, qword ptr [rsp+38h+var_18]
0x180008836  test    rcx, rcx
0x180008839  jz      short loc_180008851
0x18000883b  mov     qword ptr [rsp+38h+var_18], 0
0x180008844  mov     rax, [rcx]
0x180008847  mov     rax, [rax+10h]
0x18000884b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008850  nop
0x180008851  xor     ebx, ebx
0x180008853  mov     eax, ebx
0x180008855  mov     rcx, [rsp+38h+var_10]
0x18000885a  xor     rcx, rsp; StackCookie
0x18000885d  call    __security_check_cookie
0x180008862  mov     rbx, [rsp+38h+arg_8]
0x180008867  add     rsp, 30h
0x18000886b  pop     rdi
0x18000886c  retn
0x18000886d  mov     edx, 0A01h; void *
0x180008872  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
