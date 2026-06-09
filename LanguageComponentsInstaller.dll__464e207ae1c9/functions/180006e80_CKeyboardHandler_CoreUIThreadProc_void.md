# CKeyboardHandler::CoreUIThreadProc(void *)

- ea: `0x180006e80`
- end: `0x180007084`
- name: `?CoreUIThreadProc@CKeyboardHandler@@CAKPEAX@Z`
- size: `516`
- prototype: `__int64 __fastcall(HANDLE *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180003520`
- `0x180006e80`
- `0x18000a374`
- `0x18000a3cc`
- `0x18000a7fc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006fe4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180006fe4`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180006fa6`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180006fa6`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180006ea9`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180006ea9`
- `CoreMessaging!CoreUICreate` at `0x180006eca`
- `CoreMessaging!CoreUICreate` at `0x180006eca`

## string_xrefs

- `0x180007014`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007029`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x18000703e`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007052`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`
- `0x180007066`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\keyboardhandler.cpp`

## pseudocode

```c
__int64 __fastcall CKeyboardHandler::CoreUIThreadProc(HANDLE *a1)
{
  int v1; // eax
  int v2; // eax
  __int64 v3; // rcx
  int v4; // eax
  int v5; // eax
  int v6; // eax
  HANDLE v7; // rcx
  __int64 v8; // r8
  const char *v9; // r9
  __int64 result; // rax
  int v11; // [rsp+20h] [rbp-48h]
  __int64 v13; // [rsp+48h] [rbp-20h] BYREF
  __int64 v14; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v1 = RoInitialize(0);
  try
  {
    if ( v1 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x45,
        (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v1,
        v11);
    v13 = 0;
    CoreUICreate(&v13);
    v2 = CKeyboardHandler::_Initialize((CKeyboardHandler *)a1);
    if ( v2 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x58,
        (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v2,
        v11);
    v3 = v13;
    v14 = v13;
    if ( v13 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 8LL))(v13);
      v3 = v13;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, HANDLE, __int64 (__fastcall *)(), __int64 *))(*(_QWORD *)v3 + 272LL))(
           v3,
           a1[2],
           CKeyboardHandler::CoreUIThreadProc_::_3_::MessageLoopStopper::WaitCallback,
           &v14);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5B,
        (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v4,
        v11);
    v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v13 + 232LL))(v13);
    if ( v5 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5D,
        (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v5,
        v11);
    v6 = (*(__int64 (__fastcall **)(__int64, HANDLE))(*(_QWORD *)v13 + 280LL))(v13, a1[2]);
    if ( v6 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5E,
        (int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\keyboardhandler.cpp",
        (const char *)(unsigned int)v6,
        v11);
    v7 = a1[1];
    if ( v7 )
    {
      a1[1] = 0;
      (*(void (__fastcall **)(HANDLE))(*(_QWORD *)v7 + 16LL))(v7);
    }
    RoUninitialize(v7);
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    if ( !SetEvent(a1[3]) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v8, v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x67,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "keyboardhandler.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x180006e80  sub     rsp, 68h
0x180006e84  mov     rax, cs:__security_cookie
0x180006e8b  xor     rax, rsp
0x180006e8e  mov     [rsp+68h+var_10], rax
0x180006e93  mov     [rsp+68h+var_28], rcx
0x180006e98  lea     rax, [rsp+68h+var_28]
0x180006e9d  mov     [rsp+68h+var_38], rax
0x180006ea2  mov     [rsp+68h+var_30], 1
0x180006ea7  xor     ecx, ecx
0x180006ea9  call    cs:__imp_RoInitialize
0x180006eaf  mov     rcx, [rsp+68h]; this
0x180006eb4  test    eax, eax
0x180006eb6  js      loc_180007011
0x180006ebc  mov     [rsp+68h+var_20], 0
0x180006ec5  lea     rcx, [rsp+68h+var_20]
0x180006eca  call    cs:__imp_CoreUICreate
0x180006ed0  mov     rcx, [rsp+68h+var_28]; this
0x180006ed5  call    ?_Initialize@CKeyboardHandler@@AEAAJXZ; CKeyboardHandler::_Initialize(void)
0x180006eda  mov     rcx, [rsp+68h]; this
0x180006edf  test    eax, eax
0x180006ee1  js      loc_180007026
0x180006ee7  mov     rcx, [rsp+68h+var_20]
0x180006eec  mov     [rsp+68h+var_18], rcx
0x180006ef1  test    rcx, rcx
0x180006ef4  jz      short loc_180006F07
0x180006ef6  mov     rax, [rcx]
0x180006ef9  mov     rax, [rax+8]
0x180006efd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f02  mov     rcx, [rsp+68h+var_20]
0x180006f07  mov     rax, [rcx]
0x180006f0a  lea     r9, [rsp+68h+var_18]
0x180006f0f  lea     r8, _CKeyboardHandler__CoreUIThreadProc____3___MessageLoopStopper__WaitCallback
0x180006f16  mov     rdx, [rsp+68h+var_28]
0x180006f1b  mov     rdx, [rdx+10h]
0x180006f1f  mov     rax, [rax+110h]
0x180006f26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2b  mov     rcx, [rsp+68h]; this
0x180006f30  test    eax, eax
0x180006f32  js      loc_18000703B
0x180006f38  mov     rcx, [rsp+68h+var_20]
0x180006f3d  mov     rax, [rcx]
0x180006f40  mov     rax, [rax+0E8h]
0x180006f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4c  mov     rcx, [rsp+68h]; this
0x180006f51  test    eax, eax
0x180006f53  js      loc_18000704F
0x180006f59  mov     rcx, [rsp+68h+var_20]
0x180006f5e  mov     rax, [rcx]
0x180006f61  mov     rdx, [rsp+68h+var_28]
0x180006f66  mov     rdx, [rdx+10h]
0x180006f6a  mov     rax, [rax+118h]
0x180006f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f76  mov     rcx, [rsp+68h]; this
0x180006f7b  test    eax, eax
0x180006f7d  js      loc_180007063
0x180006f83  mov     rax, [rsp+68h+var_28]
0x180006f88  mov     rcx, [rax+8]
0x180006f8c  test    rcx, rcx
0x180006f8f  jz      short loc_180006FA6
0x180006f91  mov     qword ptr [rax+8], 0
0x180006f99  mov     rax, [rcx]
0x180006f9c  mov     rax, [rax+10h]
0x180006fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fa5  nop
0x180006fa6  call    cs:__imp_RoUninitialize
0x180006fac  nop
0x180006fad  mov     rcx, [rsp+68h+var_18]
0x180006fb2  test    rcx, rcx
0x180006fb5  jz      short loc_180006FC4
0x180006fb7  mov     rax, [rcx]
0x180006fba  mov     rax, [rax+10h]
0x180006fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc3  nop
0x180006fc4  mov     rcx, [rsp+68h+var_20]
0x180006fc9  test    rcx, rcx
0x180006fcc  jz      short loc_180006FDB
0x180006fce  mov     rax, [rcx]
0x180006fd1  mov     rax, [rax+10h]
0x180006fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fda  nop
0x180006fdb  mov     rcx, [rsp+68h+var_28]
0x180006fe0  mov     rcx, [rcx+18h]; hEvent
0x180006fe4  call    cs:__imp_SetEvent
0x180006fea  mov     rcx, [rsp+68h]; this
0x180006fef  test    eax, eax
0x180006ff1  jz      loc_180007078
0x180006ff7  xor     eax, eax
0x180006ff9  jmp     short loc_180006FFF
0x180006ffb  mov     eax, dword ptr [rsp+68h+var_20]
0x180006fff  mov     rcx, [rsp+68h+var_10]
0x180007004  xor     rcx, rsp; StackCookie
0x180007007  call    __security_check_cookie
0x18000700c  add     rsp, 68h
0x180007010  retn
0x180007011  mov     r9d, eax; char *
0x180007014  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000701b  mov     edx, 45h ; 'E'; void *
0x180007020  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007026  mov     r9d, eax; char *
0x180007029  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180007030  mov     edx, 58h ; 'X'; void *
0x180007035  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000703b  mov     r9d, eax; char *
0x18000703e  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180007045  mov     edx, 5Bh ; '['; void *
0x18000704a  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000704f  mov     r9d, eax; char *
0x180007052  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x180007059  mov     edx, 5Dh ; ']'; void *
0x18000705e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007063  mov     r9d, eax; char *
0x180007066  lea     r8, aOnecoreShellCp_5; "onecore\\shell\\cpls\\internationalsett"...
0x18000706d  mov     edx, 5Eh ; '^'; void *
0x180007072  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180007078  mov     edx, 0A01h; void *
0x18000707d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
