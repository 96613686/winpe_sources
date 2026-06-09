# CKeyboardHandler::_Initialize(void)

- ea: `0x18000a3cc`
- end: `0x18000a7f4`
- name: `?_Initialize@CKeyboardHandler@@AEAAJXZ`
- size: `1064`
- prototype: `__int64 __fastcall(CKeyboardHandler *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180006e80`

## callees

- `0x180003520`
- `0x18000462c`
- `0x180008e9c`
- `0x1800092a4`
- `0x18000a374`
- `0x18000a3cc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a71f`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a71f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a41d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000a41d`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a43a`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000a43a`

## string_xrefs

- `0x18000a44d`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x18000a4c2`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x18000a598`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x18000a64a`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::_Initialize(CKeyboardHandler *this)
{
  HRESULT v2; // eax
  int v3; // edx
  unsigned int v4; // r8d
  int ActivationFactory; // eax
  unsigned int v6; // ebx
  __int64 v8; // rbx
  __int64 (__fastcall *v9)(__int64, char *); // rdi
  _QWORD *v10; // r14
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rax
  void *v14; // rax
  volatile signed __int32 *v15; // rbx
  volatile signed __int32 *v16; // rdi
  __int64 v17; // rdi
  int v18; // eax
  unsigned int v19; // r15d
  int v20; // eax
  unsigned int v21; // r14d
  __int64 v22; // rcx
  _QWORD *v23; // rax
  void *v24; // rcx
  __int64 v25; // r8
  const char *v26; // r9
  __int64 v27; // rcx
  __int64 v28; // [rsp+20h] [rbp-60h] BYREF
  void *v29; // [rsp+28h] [rbp-58h] BYREF
  volatile signed __int32 *v30; // [rsp+30h] [rbp-50h]
  HSTRING_HEADER hstringHeader; // [rsp+38h] [rbp-48h] BYREF
  HSTRING string; // [rsp+50h] [rbp-30h] BYREF
  __int64 v33; // [rsp+58h] [rbp-28h] BYREF
  __int64 v34; // [rsp+60h] [rbp-20h] BYREF
  int v35; // [rsp+68h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v33 = 0;
  string = 0;
  v2 = WindowsCreateStringReference(
         L"Windows.UI.Internal.Text.Core.CoreKeyboardInputProfileManager",
         0x3Du,
         &hstringHeader,
         &string);
  if ( v2 < 0 )
  {
    Microsoft::WRL::Details::RaiseException((Microsoft::WRL::Details *)(unsigned int)v2, v3, v4);
    JUMPOUT(0x18000A7F3LL);
  }
  ActivationFactory = RoGetActivationFactory(string, &GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae, &v33);
  v6 = ActivationFactory;
  if ( ActivationFactory < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)ActivationFactory,
      v28);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return v6;
  }
  v8 = v33;
  v9 = *(__int64 (__fastcall **)(__int64, char *))(*(_QWORD *)v33 + 48LL);
  v10 = (_QWORD *)((char *)this + 8);
  v11 = *((_QWORD *)this + 1);
  if ( v11 )
  {
    *v10 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
  }
  v12 = v9(v8, (char *)this + 8);
  v6 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x78,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v12,
      v28);
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return v6;
  }
  v13 = *((_QWORD *)this + 5);
  if ( v13 )
    _InterlockedIncrement((volatile signed __int32 *)(v13 + 8));
  v14 = (void *)*((_QWORD *)this + 4);
  hstringHeader.Reserved.Reserved1 = v14;
  v15 = (volatile signed __int32 *)*((_QWORD *)this + 5);
  *(_QWORD *)&hstringHeader.Reserved.Reserved2[8] = v15;
  if ( v15 )
    _InterlockedIncrement(v15 + 2);
  v29 = v14;
  v30 = v15;
  Microsoft::WRL::Callback_Windows::Foundation::ITypedEventHandler_Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManager___Windows::UI::Internal::Text::Core::CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____lambda_9457df648bd98a661435affe263029da___(
    &v28,
    &v29);
  v16 = v30;
  if ( v30 )
  {
    if ( _InterlockedExchangeAdd(v30 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v16)(v16);
      if ( _InterlockedExchangeAdd(v16 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v16 + 8LL))(v16);
    }
  }
  v17 = v28;
  v18 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *))(*(_QWORD *)*v10 + 64LL))(*v10, v28, (char *)this + 48);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v34 = 0;
    v20 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*v10 + 160LL))(*v10, &v34);
    v21 = v20;
    if ( v20 >= 0 )
    {
      v35 = 0;
      if ( (*(int (__fastcall **)(__int64, int *))(*(_QWORD *)v34 + 56LL))(v34, &v35) >= 0 && v35 )
      {
        v23 = (_QWORD *)*((_QWORD *)this + 4);
        v24 = v23 ? (void *)*v23 : 0LL;
        if ( !SetEvent(v24) )
          wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v25, v26);
      }
      v27 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      }
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      return 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x89,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v20,
        v28);
      v22 = v34;
      if ( v34 )
      {
        v34 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
      }
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      if ( v15 )
      {
        if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
          if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
        }
      }
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
      return v21;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x86,
      (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
      (const char *)(unsigned int)v18,
      v28);
    if ( v17 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    if ( v15 )
    {
      if ( _InterlockedExchangeAdd(v15 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v15)(v15);
        if ( _InterlockedExchangeAdd(v15 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v15 + 8LL))(v15);
      }
    }
    if ( v33 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    return v19;
  }
}

```

## disassembly

```asm
0x18000a3cc  mov     [rsp-28h+arg_8], rbx
0x18000a3d1  mov     [rsp-28h+arg_10], rsi
0x18000a3d6  push    rbp
0x18000a3d7  push    rdi
0x18000a3d8  push    r13
0x18000a3da  push    r14
0x18000a3dc  push    r15
0x18000a3de  mov     rbp, rsp
0x18000a3e1  sub     rsp, 80h
0x18000a3e8  mov     rax, cs:__security_cookie
0x18000a3ef  xor     rax, rsp
0x18000a3f2  mov     [rbp+var_10], rax
0x18000a3f6  mov     rsi, rcx
0x18000a3f9  mov     [rbp+var_28], 0
0x18000a401  mov     [rbp+string], 0
0x18000a409  lea     r9, [rbp+string]; string
0x18000a40d  lea     r8, [rbp+hstringHeader]; hstringHeader
0x18000a411  mov     edx, 3Dh ; '='; length
0x18000a416  lea     rcx, ?RuntimeClass_Windows_UI_Internal_Text_Core_CoreKeyboardInputProfileManager@@3QBGB; "Windows.UI.Internal.Text.Core.CoreKeybo"...
0x18000a41d  call    cs:__imp_WindowsCreateStringReference
0x18000a423  test    eax, eax
0x18000a425  js      loc_18000A7EC
0x18000a42b  lea     r8, [rbp+var_28]
0x18000a42f  lea     rdx, _GUID_d0380bbe_201e_4a70_8eff_bb52f7996cae
0x18000a436  mov     rcx, [rbp+string]
0x18000a43a  call    cs:__imp_RoGetActivationFactory
0x18000a440  mov     ebx, eax
0x18000a442  test    eax, eax
0x18000a444  jns     short loc_18000A47C
0x18000a446  mov     rcx, [rbp+28h]; this
0x18000a44a  mov     r9d, eax; char *
0x18000a44d  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000a454  mov     edx, 76h ; 'v'; void *
0x18000a459  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a45e  nop
0x18000a45f  mov     rcx, [rbp+var_28]
0x18000a463  test    rcx, rcx
0x18000a466  jz      short loc_18000A475
0x18000a468  mov     rax, [rcx]
0x18000a46b  mov     rax, [rax+10h]
0x18000a46f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a474  nop
0x18000a475  mov     eax, ebx
0x18000a477  jmp     loc_18000A7B9
0x18000a47c  mov     rbx, [rbp+var_28]
0x18000a480  mov     rax, [rbx]
0x18000a483  mov     rdi, [rax+30h]
0x18000a487  lea     r14, [rsi+8]
0x18000a48b  mov     rcx, [r14]
0x18000a48e  test    rcx, rcx
0x18000a491  jz      short loc_18000A4A7
0x18000a493  mov     qword ptr [r14], 0
0x18000a49a  mov     rdx, [rcx]
0x18000a49d  mov     rax, [rdx+10h]
0x18000a4a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4a6  nop
0x18000a4a7  mov     rdx, r14
0x18000a4aa  mov     rcx, rbx
0x18000a4ad  mov     rax, rdi
0x18000a4b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4b5  mov     ebx, eax
0x18000a4b7  test    eax, eax
0x18000a4b9  jns     short loc_18000A4EC
0x18000a4bb  mov     rcx, [rbp+28h]; this
0x18000a4bf  mov     r9d, eax; char *
0x18000a4c2  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000a4c9  mov     edx, 78h ; 'x'; void *
0x18000a4ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a4d3  nop
0x18000a4d4  mov     rcx, [rbp+var_28]
0x18000a4d8  test    rcx, rcx
0x18000a4db  jz      short loc_18000A4EA
0x18000a4dd  mov     rax, [rcx]
0x18000a4e0  mov     rax, [rax+10h]
0x18000a4e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e9  nop
0x18000a4ea  jmp     short loc_18000A475
0x18000a4ec  mov     rax, [rsi+28h]
0x18000a4f0  test    rax, rax
0x18000a4f3  jz      short loc_18000A4F9
0x18000a4f5  lock inc dword ptr [rax+8]
0x18000a4f9  mov     rax, [rsi+20h]
0x18000a4fd  mov     qword ptr [rbp+hstringHeader.Reserved], rax
0x18000a501  mov     rbx, [rsi+28h]
0x18000a505  mov     qword ptr [rbp+hstringHeader.Reserved+8], rbx
0x18000a509  test    rbx, rbx
0x18000a50c  jz      short loc_18000A512
0x18000a50e  lock inc dword ptr [rbx+8]
0x18000a512  mov     [rbp+var_58], rax
0x18000a516  mov     [rbp+var_50], rbx
0x18000a51a  lea     rdx, [rbp+var_58]
0x18000a51e  lea     rcx, [rbp+var_60]
0x18000a522  call    Microsoft__WRL__Callback_Windows__Foundation__ITypedEventHandler_Windows__UI__Internal__Text__Core__CoreKeyboardInputProfileManager___Windows__UI__Internal__Text__Core__CoreKeyboardInputProfileManagerEnabledProfilesChangedEventArgs_____lambda_9457df648bd98a661435affe263029da___
0x18000a527  nop
0x18000a528  mov     rdi, [rbp+var_50]
0x18000a52c  or      r13d, 0FFFFFFFFh
0x18000a530  test    rdi, rdi
0x18000a533  jz      short loc_18000A56C
0x18000a535  mov     eax, r13d
0x18000a538  lock xadd [rdi+8], eax
0x18000a53d  add     eax, r13d
0x18000a540  jnz     short loc_18000A56C
0x18000a542  mov     rax, [rdi]
0x18000a545  mov     rcx, rdi
0x18000a548  mov     rax, [rax]
0x18000a54b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a550  mov     eax, r13d
0x18000a553  lock xadd [rdi+0Ch], eax
0x18000a558  add     eax, r13d
0x18000a55b  jnz     short loc_18000A56C
0x18000a55d  mov     rax, [rdi]
0x18000a560  mov     rcx, rdi
0x18000a563  mov     rax, [rax+8]
0x18000a567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a56c  mov     rcx, [r14]
0x18000a56f  mov     rax, [rcx]
0x18000a572  lea     r8, [rsi+30h]
0x18000a576  mov     rdi, [rbp+var_60]
0x18000a57a  mov     rdx, rdi
0x18000a57d  mov     rax, [rax+40h]
0x18000a581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a586  mov     r15d, eax
0x18000a589  test    eax, eax
0x18000a58b  jns     loc_18000A61A
0x18000a591  mov     rcx, [rbp+28h]; this
0x18000a595  mov     r9d, eax; char *
0x18000a598  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000a59f  mov     edx, 86h; void *
0x18000a5a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a5a9  nop
0x18000a5aa  test    rdi, rdi
0x18000a5ad  jz      short loc_18000A5BF
0x18000a5af  mov     rax, [rdi]
0x18000a5b2  mov     rcx, rdi
0x18000a5b5  mov     rax, [rax+10h]
0x18000a5b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5be  nop
0x18000a5bf  test    rbx, rbx
0x18000a5c2  jz      short loc_18000A5FC
0x18000a5c4  mov     eax, r13d
0x18000a5c7  lock xadd [rbx+8], eax
0x18000a5cc  add     eax, r13d
0x18000a5cf  jnz     short loc_18000A5FC
0x18000a5d1  mov     rax, [rbx]
0x18000a5d4  mov     rcx, rbx
0x18000a5d7  mov     rax, [rax]
0x18000a5da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5df  mov     eax, r13d
0x18000a5e2  lock xadd [rbx+0Ch], eax
0x18000a5e7  add     eax, r13d
0x18000a5ea  jnz     short loc_18000A5FC
0x18000a5ec  mov     rax, [rbx]
0x18000a5ef  mov     rcx, rbx
0x18000a5f2  mov     rax, [rax+8]
0x18000a5f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5fb  nop
0x18000a5fc  mov     rcx, [rbp+var_28]
0x18000a600  test    rcx, rcx
0x18000a603  jz      short loc_18000A612
0x18000a605  mov     rax, [rcx]
0x18000a608  mov     rax, [rax+10h]
0x18000a60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a611  nop
0x18000a612  mov     eax, r15d
0x18000a615  jmp     loc_18000A7B9
0x18000a61a  mov     [rbp+var_20], 0
0x18000a622  mov     rcx, [r14]
0x18000a625  mov     rax, [rcx]
0x18000a628  lea     rdx, [rbp+var_20]
0x18000a62c  mov     rax, [rax+0A0h]
0x18000a633  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a638  mov     r14d, eax
0x18000a63b  test    eax, eax
0x18000a63d  jns     loc_18000A6EA
0x18000a643  mov     rcx, [rbp+28h]; this
0x18000a647  mov     r9d, eax; char *
0x18000a64a  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000a651  mov     edx, 89h; void *
0x18000a656  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000a65b  nop
0x18000a65c  mov     rcx, [rbp+var_20]
0x18000a660  test    rcx, rcx
0x18000a663  jz      short loc_18000A67A
0x18000a665  mov     [rbp+var_20], 0
0x18000a66d  mov     rax, [rcx]
0x18000a670  mov     rax, [rax+10h]
0x18000a674  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a679  nop
0x18000a67a  test    rdi, rdi
0x18000a67d  jz      short loc_18000A68F
0x18000a67f  mov     rax, [rdi]
0x18000a682  mov     rcx, rdi
0x18000a685  mov     rax, [rax+10h]
0x18000a689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a68e  nop
0x18000a68f  test    rbx, rbx
0x18000a692  jz      short loc_18000A6CC
0x18000a694  mov     eax, r13d
0x18000a697  lock xadd [rbx+8], eax
0x18000a69c  add     eax, r13d
0x18000a69f  jnz     short loc_18000A6CC
0x18000a6a1  mov     rax, [rbx]
0x18000a6a4  mov     rcx, rbx
0x18000a6a7  mov     rax, [rax]
0x18000a6aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6af  mov     eax, r13d
0x18000a6b2  lock xadd [rbx+0Ch], eax
0x18000a6b7  add     eax, r13d
0x18000a6ba  jnz     short loc_18000A6CC
0x18000a6bc  mov     rax, [rbx]
0x18000a6bf  mov     rcx, rbx
0x18000a6c2  mov     rax, [rax+8]
0x18000a6c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6cb  nop
0x18000a6cc  mov     rcx, [rbp+var_28]
0x18000a6d0  test    rcx, rcx
0x18000a6d3  jz      short loc_18000A6E2
0x18000a6d5  mov     rax, [rcx]
0x18000a6d8  mov     rax, [rax+10h]
0x18000a6dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e1  nop
0x18000a6e2  mov     eax, r14d
0x18000a6e5  jmp     loc_18000A7B9
0x18000a6ea  mov     [rbp+var_18], 0
0x18000a6f1  mov     rcx, [rbp+var_20]
0x18000a6f5  mov     rax, [rcx]
0x18000a6f8  lea     rdx, [rbp+var_18]
0x18000a6fc  mov     rax, [rax+38h]
0x18000a700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a705  test    eax, eax
0x18000a707  js      short loc_18000A731
0x18000a709  cmp     [rbp+var_18], 0
0x18000a70d  jbe     short loc_18000A731
0x18000a70f  mov     rax, [rsi+20h]
0x18000a713  test    rax, rax
0x18000a716  jz      short loc_18000A71D
0x18000a718  mov     rcx, [rax]
0x18000a71b  jmp     short loc_18000A71F
0x18000a71d  xor     ecx, ecx; hEvent
0x18000a71f  call    cs:__imp_SetEvent
0x18000a725  mov     rcx, [rbp+28h]; this
0x18000a729  test    eax, eax
0x18000a72b  jz      loc_18000A7E1
0x18000a731  mov     rcx, [rbp+var_20]
0x18000a735  test    rcx, rcx
0x18000a738  jz      short loc_18000A74F
0x18000a73a  mov     [rbp+var_20], 0
0x18000a742  mov     rax, [rcx]
0x18000a745  mov     rax, [rax+10h]
0x18000a749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74e  nop
0x18000a74f  test    rdi, rdi
0x18000a752  jz      short loc_18000A764
0x18000a754  mov     rax, [rdi]
0x18000a757  mov     rcx, rdi
0x18000a75a  mov     rax, [rax+10h]
0x18000a75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a763  nop
0x18000a764  test    rbx, rbx
0x18000a767  jz      short loc_18000A7A1
0x18000a769  mov     eax, r13d
0x18000a76c  lock xadd [rbx+8], eax
0x18000a771  add     eax, r13d
0x18000a774  jnz     short loc_18000A7A1
0x18000a776  mov     rax, [rbx]
0x18000a779  mov     rcx, rbx
0x18000a77c  mov     rax, [rax]
0x18000a77f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a784  mov     eax, r13d
0x18000a787  lock xadd [rbx+0Ch], eax
0x18000a78c  add     eax, r13d
0x18000a78f  jnz     short loc_18000A7A1
0x18000a791  mov     rax, [rbx]
0x18000a794  mov     rcx, rbx
0x18000a797  mov     rax, [rax+8]
0x18000a79b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7a0  nop
0x18000a7a1  mov     rcx, [rbp+var_28]
0x18000a7a5  test    rcx, rcx
0x18000a7a8  jz      short loc_18000A7B7
0x18000a7aa  mov     rax, [rcx]
0x18000a7ad  mov     rax, [rax+10h]
0x18000a7b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b6  nop
0x18000a7b7  xor     eax, eax
0x18000a7b9  mov     rcx, [rbp+var_10]
0x18000a7bd  xor     rcx, rsp; StackCookie
0x18000a7c0  call    __security_check_cookie
0x18000a7c5  lea     r11, [rsp+80h+var_s0]
0x18000a7cd  mov     rbx, [r11+38h]
0x18000a7d1  mov     rsi, [r11+40h]
0x18000a7d5  mov     rsp, r11
0x18000a7d8  pop     r15
0x18000a7da  pop     r14
0x18000a7dc  pop     r13
0x18000a7de  pop     rdi
0x18000a7df  pop     rbp
0x18000a7e0  retn
0x18000a7e1  mov     edx, 0A01h; void *
0x18000a7e6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
  ... truncated ...
```
