# CLogonController::_TransformCredentialRequestResult(Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *,_CRED_PROV_CREDENTIAL *,uint *,uint *,ushort * *,ushort * *)

- ea: `0x18003d3e8`
- end: `0x18003d75c`
- name: `?_TransformCredentialRequestResult@CLogonController@@AEAAJPEAUIRequestCredentialsData@Controller@Logon@UI@Internal@Windows@@PEAU_CRED_PROV_CREDENTIAL@@PEAI2PEAPEAG3@Z`
- size: `884`
- prototype: `__int64 __fastcall(CLogonController *this, struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, struct _CRED_PROV_CREDENTIAL *, unsigned int *, HSTRING string, _QWORD *length, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180021730`

## callees

- `0x18000df10`
- `0x18003d3e8`
- `0x18003d7d0`
- `0x18003da84`
- `0x180047680`
- `0x180048e80`
- `0x18004ae90`
- `0x18005d488`
- `0x18009b79c`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d633`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d66f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d6fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003d725`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6b7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003d6b7`

## pseudocode

```c
__int64 __fastcall CLogonController::_TransformCredentialRequestResult(
        CLogonController *this,
        struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *a2,
        struct _CRED_PROV_CREDENTIAL *a3,
        unsigned int *a4,
        HSTRING string,
        _QWORD *length,
        unsigned __int16 **a7)
{
  _QWORD *v10; // r13
  unsigned __int16 **v11; // r12
  HSTRING v12; // rdi
  int v13; // eax
  __int64 v14; // rcx
  unsigned int v15; // ebx
  __int64 (__fastcall *v16)(struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, unsigned __int16 ***); // rbx
  int v17; // eax
  unsigned __int16 **v18; // rcx
  unsigned __int16 *v19; // rdi
  int v20; // eax
  unsigned __int16 **v21; // rbx
  __int64 (__fastcall *v22)(unsigned __int16 **, GUID *, struct ICredProviderCredentialSerialization **); // rdi
  int v23; // eax
  int v24; // eax
  struct ICredProviderCredentialSerialization *v25; // rcx
  unsigned __int16 **v26; // rcx
  struct ICredProviderCredentialSerialization *v27; // rcx
  __int64 (__fastcall *v28)(struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, HSTRING *); // rbx
  int v29; // eax
  unsigned __int16 **v30; // rcx
  HSTRING v31; // rcx
  PCWSTR StringRawBuffer; // r14
  size_t v33; // rbx
  void *v34; // rax
  void *v35; // rsi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+38h]
  struct ICredProviderCredentialSerialization *v40; // [rsp+70h] [rbp+50h] BYREF
  unsigned __int16 *v41; // [rsp+78h] [rbp+58h] BYREF

  *(_QWORD *)a3 = 0;
  *((_QWORD *)a3 + 2) = 0;
  *((_DWORD *)a3 + 2) = 0;
  *a4 = 0;
  v10 = length;
  *length = 0;
  v11 = a7;
  *a7 = 0;
  v12 = string;
  if ( string )
  {
    *(_DWORD *)string = 0;
    LODWORD(length) = 0;
    v13 = (*(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, _QWORD **))(*(_QWORD *)a2 + 56LL))(
            a2,
            &length);
    v15 = v13;
    if ( v13 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD22,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v13,
        savedregs);
      return v15;
    }
    *(_DWORD *)v12 = CLogonController::_ResultMaskFromShutdownChoice(v14, (unsigned int)length);
  }
  a7 = 0;
  v16 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, unsigned __int16 ***))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&a7);
  v17 = v16(a2, &a7);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xD28,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
      (const char *)(unsigned int)v17,
      savedregs);
    v18 = a7;
    if ( a7 )
    {
      a7 = 0;
      (*((void (__fastcall **)(unsigned __int16 **))*v18 + 2))(v18);
    }
    return v15;
  }
  v19 = 0;
  v41 = 0;
  if ( a7 )
  {
    v20 = (*((__int64 (__fastcall **)(unsigned __int16 **, unsigned int *))*a7 + 6))(a7, a4);
    v15 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD2E,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v20,
        savedregs);
LABEL_39:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WluiFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void WluiFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v41);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&a7);
      return v15;
    }
    v40 = 0;
    v21 = a7;
    v22 = *(__int64 (__fastcall **)(unsigned __int16 **, GUID *, struct ICredProviderCredentialSerialization **))*a7;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v40);
    v23 = v22(v21, &GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c, &v40);
    v15 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD31,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v23,
        savedregs);
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v40);
      goto LABEL_39;
    }
    v41 = 0;
    v24 = CLogonController::_TransformCredentialSerialization(this, v40, a3, &v41);
    v15 = v24;
    if ( v24 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xD32,
        (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
        (const char *)(unsigned int)v24,
        savedregs);
      v25 = v40;
      if ( v40 )
      {
        v40 = 0;
        (*(void (__fastcall **)(struct ICredProviderCredentialSerialization *))(*(_QWORD *)v25 + 16LL))(v25);
      }
      if ( v41 )
        MIDL_user_free(v41);
      v26 = a7;
      if ( a7 )
      {
        a7 = 0;
        (*((void (__fastcall **)(unsigned __int16 **))*v26 + 2))(v26);
      }
      return v15;
    }
    v27 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(struct ICredProviderCredentialSerialization *))(*(_QWORD *)v27 + 16LL))(v27);
    }
    v19 = v41;
  }
  string = 0;
  v28 = *(__int64 (__fastcall **)(struct Windows::Internal::UI::Logon::Controller::IRequestCredentialsData *, HSTRING *))(*(_QWORD *)a2 + 64LL);
  WindowsDeleteString(0);
  string = 0;
  v29 = v28(a2, &string);
  v15 = v29;
  if ( v29 >= 0 )
  {
    v31 = string;
    if ( string )
    {
      LODWORD(length) = 0;
      StringRawBuffer = WindowsGetStringRawBuffer(string, (UINT32 *)&length);
      v33 = 2LL * (unsigned int)((_DWORD)length + 1);
      v34 = MIDL_user_allocate(v33);
      v35 = v34;
      if ( !v34 )
      {
        v15 = -2147024882;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xD44,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)0x8007000ELL,
          savedregs);
        WindowsDeleteString(string);
LABEL_38:
        string = 0;
        goto LABEL_39;
      }
      memcpy_0(v34, StringRawBuffer, v33);
      *v10 = v35;
      v31 = string;
    }
    if ( v19 )
    {
      v41 = 0;
      *v11 = v19;
    }
    WindowsDeleteString(v31);
    v15 = 0;
    goto LABEL_38;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xD36,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)v29,
    savedregs);
  WindowsDeleteString(string);
  string = 0;
  if ( v19 )
    MIDL_user_free(v19);
  v30 = a7;
  if ( a7 )
  {
    a7 = 0;
    (*((void (__fastcall **)(unsigned __int16 **))*v30 + 2))(v30);
  }
  return v15;
}

```

## disassembly

```asm
0x18003d3e8  mov     [rsp-38h+arg_8], rbx
0x18003d3ed  mov     [rsp-38h+arg_0], rcx
0x18003d3f2  push    rbp
0x18003d3f3  push    rsi
0x18003d3f4  push    rdi
0x18003d3f5  push    r12
0x18003d3f7  push    r13
0x18003d3f9  push    r14
0x18003d3fb  push    r15; int
0x18003d3fd  mov     rbp, rsp
0x18003d400  sub     rsp, 20h
0x18003d404  mov     r15, r9
0x18003d407  mov     rsi, r8
0x18003d40a  mov     r14, rdx
0x18003d40d  xor     eax, eax
0x18003d40f  mov     [r8], rax
0x18003d412  mov     [r8+10h], rax
0x18003d416  mov     [r8+8], eax
0x18003d41a  mov     [r9], eax
0x18003d41d  mov     r13, [rbp+length]
0x18003d421  mov     [r13+0], rax
0x18003d425  mov     r12, [rbp+arg_30]
0x18003d429  mov     [r12], rax
0x18003d42d  mov     rdi, [rbp+string]
0x18003d431  test    rdi, rdi
0x18003d434  jz      short loc_18003D47D
0x18003d436  mov     [rdi], eax
0x18003d438  mov     dword ptr [rbp+length], eax
0x18003d43b  mov     rax, [rdx]
0x18003d43e  lea     rdx, [rbp+length]
0x18003d442  mov     rcx, r14
0x18003d445  mov     rax, [rax+38h]
0x18003d449  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d44e  mov     ebx, eax
0x18003d450  test    eax, eax
0x18003d452  jns     short loc_18003D471
0x18003d454  mov     rcx, [rbp+38h]; this
0x18003d458  mov     r9d, eax; char *
0x18003d45b  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d462  mov     edx, 0D22h; void *
0x18003d467  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d46c  jmp     loc_18003D745
0x18003d471  mov     edx, dword ptr [rbp+length]
0x18003d474  call    ?_ResultMaskFromShutdownChoice@CLogonController@@AEAAIW4LogonUIShutdownChoice@Controller@Logon@UI@Internal@Windows@@@Z; CLogonController::_ResultMaskFromShutdownChoice(Windows::Internal::UI::Logon::Controller::LogonUIShutdownChoice)
0x18003d479  mov     [rdi], eax
0x18003d47b  xor     eax, eax
0x18003d47d  mov     [rbp+arg_30], rax
0x18003d481  mov     rax, [r14]
0x18003d484  mov     rbx, [rax+30h]
0x18003d488  lea     rcx, [rbp+arg_30]
0x18003d48c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003d491  lea     rdx, [rbp+arg_30]
0x18003d495  mov     rcx, r14
0x18003d498  mov     rax, rbx
0x18003d49b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4a0  mov     ebx, eax
0x18003d4a2  test    eax, eax
0x18003d4a4  jns     short loc_18003D4E2
0x18003d4a6  mov     rcx, [rbp+38h]; this
0x18003d4aa  mov     r9d, eax; char *
0x18003d4ad  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d4b4  mov     edx, 0D28h; void *
0x18003d4b9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d4be  nop
0x18003d4bf  mov     rcx, [rbp+arg_30]
0x18003d4c3  test    rcx, rcx
0x18003d4c6  jz      short loc_18003D4DD
0x18003d4c8  mov     [rbp+arg_30], 0
0x18003d4d0  mov     rax, [rcx]
0x18003d4d3  mov     rax, [rax+10h]
0x18003d4d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d4dc  nop
0x18003d4dd  jmp     loc_18003D745
0x18003d4e2  xor     edi, edi
0x18003d4e4  mov     [rbp+arg_18], rdi
0x18003d4e8  mov     rcx, [rbp+arg_30]
0x18003d4ec  test    rcx, rcx
0x18003d4ef  jz      loc_18003D623
0x18003d4f5  mov     rax, [rcx]
0x18003d4f8  mov     rdx, r15
0x18003d4fb  mov     rax, [rax+30h]
0x18003d4ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d504  mov     ebx, eax
0x18003d506  xor     r15d, r15d
0x18003d509  test    eax, eax
0x18003d50b  jns     short loc_18003D52A
0x18003d50d  mov     rcx, [rbp+38h]; this
0x18003d511  mov     r9d, eax; char *
0x18003d514  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d51b  mov     edx, 0D2Eh; void *
0x18003d520  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d525  jmp     loc_18003D732
0x18003d52a  mov     [rbp+arg_10], r15
0x18003d52e  mov     rbx, [rbp+arg_30]
0x18003d532  mov     rax, [rbx]
0x18003d535  mov     rdi, [rax]
0x18003d538  lea     rcx, [rbp+arg_10]
0x18003d53c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003d541  lea     r8, [rbp+arg_10]
0x18003d545  lea     rdx, _GUID_e86e9b83_bc3e_4f34_8e22_8cda6723295c
0x18003d54c  mov     rcx, rbx
0x18003d54f  mov     rax, rdi
0x18003d552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d557  mov     ebx, eax
0x18003d559  test    eax, eax
0x18003d55b  jns     short loc_18003D584
0x18003d55d  mov     rcx, [rbp+38h]; this
0x18003d561  mov     r9d, eax; char *
0x18003d564  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d56b  mov     edx, 0D31h; void *
0x18003d570  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d575  nop
0x18003d576  lea     rcx, [rbp+arg_10]
0x18003d57a  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003d57f  jmp     loc_18003D732
0x18003d584  mov     [rbp+arg_18], r15
0x18003d588  lea     r9, [rbp+arg_18]; unsigned __int16 **
0x18003d58c  mov     r8, rsi; struct _CRED_PROV_CREDENTIAL *
0x18003d58f  mov     rdx, [rbp+arg_10]; struct ICredProviderCredentialSerialization *
0x18003d593  mov     rcx, [rbp+arg_0]; this
0x18003d597  call    ?_TransformCredentialSerialization@CLogonController@@AEAAJPEAUICredProviderCredentialSerialization@@PEAU_CRED_PROV_CREDENTIAL@@PEAPEAG@Z; CLogonController::_TransformCredentialSerialization(ICredProviderCredentialSerialization *,_CRED_PROV_CREDENTIAL *,ushort * *)
0x18003d59c  mov     ebx, eax
0x18003d59e  test    eax, eax
0x18003d5a0  jns     short loc_18003D603
0x18003d5a2  mov     rcx, [rbp+38h]; this
0x18003d5a6  mov     r9d, eax; char *
0x18003d5a9  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d5b0  mov     edx, 0D32h; void *
0x18003d5b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d5ba  nop
0x18003d5bb  mov     rcx, [rbp+arg_10]
0x18003d5bf  test    rcx, rcx
0x18003d5c2  jz      short loc_18003D5D5
0x18003d5c4  mov     [rbp+arg_10], r15
0x18003d5c8  mov     rax, [rcx]
0x18003d5cb  mov     rax, [rax+10h]
0x18003d5cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5d4  nop
0x18003d5d5  mov     rcx, [rbp+arg_18]; void *
0x18003d5d9  test    rcx, rcx
0x18003d5dc  jz      short loc_18003D5E4
0x18003d5de  call    MIDL_user_free
0x18003d5e3  nop
0x18003d5e4  mov     rcx, [rbp+arg_30]
0x18003d5e8  test    rcx, rcx
0x18003d5eb  jz      short loc_18003D5FE
0x18003d5ed  mov     [rbp+arg_30], r15
0x18003d5f1  mov     rax, [rcx]
0x18003d5f4  mov     rax, [rax+10h]
0x18003d5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d5fd  nop
0x18003d5fe  jmp     loc_18003D745
0x18003d603  mov     rcx, [rbp+arg_10]
0x18003d607  test    rcx, rcx
0x18003d60a  jz      short loc_18003D61D
0x18003d60c  mov     [rbp+arg_10], r15
0x18003d610  mov     rax, [rcx]
0x18003d613  mov     rax, [rax+10h]
0x18003d617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d61c  nop
0x18003d61d  mov     rdi, [rbp+arg_18]
0x18003d621  jmp     short loc_18003D626
0x18003d623  xor     r15d, r15d
0x18003d626  mov     [rbp+string], r15
0x18003d62a  mov     rax, [r14]
0x18003d62d  mov     rbx, [rax+40h]
0x18003d631  xor     ecx, ecx; string
0x18003d633  call    cs:__imp_WindowsDeleteString
0x18003d639  mov     [rbp+string], r15
0x18003d63d  lea     rdx, [rbp+string]
0x18003d641  mov     rcx, r14
0x18003d644  mov     rax, rbx
0x18003d647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d64c  mov     ebx, eax
0x18003d64e  test    eax, eax
0x18003d650  jns     short loc_18003D6A6
0x18003d652  mov     rcx, [rbp+38h]; this
0x18003d656  mov     r9d, eax; char *
0x18003d659  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d660  mov     edx, 0D36h; void *
0x18003d665  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d66a  nop
0x18003d66b  mov     rcx, [rbp+string]; string
0x18003d66f  call    cs:__imp_WindowsDeleteString
0x18003d675  mov     [rbp+string], r15
0x18003d679  test    rdi, rdi
0x18003d67c  jz      short loc_18003D687
0x18003d67e  mov     rcx, rdi; void *
0x18003d681  call    MIDL_user_free
0x18003d686  nop
0x18003d687  mov     rcx, [rbp+arg_30]
0x18003d68b  test    rcx, rcx
0x18003d68e  jz      short loc_18003D6A1
0x18003d690  mov     [rbp+arg_30], r15
0x18003d694  mov     rax, [rcx]
0x18003d697  mov     rax, [rax+10h]
0x18003d69b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d6a0  nop
0x18003d6a1  jmp     loc_18003D745
0x18003d6a6  mov     rcx, [rbp+string]; string
0x18003d6aa  test    rcx, rcx
0x18003d6ad  jz      short loc_18003D718
0x18003d6af  mov     dword ptr [rbp+length], r15d
0x18003d6b3  lea     rdx, [rbp+length]; length
0x18003d6b7  call    cs:__imp_WindowsGetStringRawBuffer
0x18003d6bd  mov     r14, rax
0x18003d6c0  mov     ebx, dword ptr [rbp+length]
0x18003d6c3  inc     ebx
0x18003d6c5  add     rbx, rbx
0x18003d6c8  mov     rcx, rbx; size
0x18003d6cb  call    MIDL_user_allocate
0x18003d6d0  mov     rsi, rax
0x18003d6d3  test    rax, rax
0x18003d6d6  jnz     short loc_18003D702
0x18003d6d8  mov     rcx, [rbp+38h]; this
0x18003d6dc  mov     ebx, 8007000Eh
0x18003d6e1  mov     r9d, ebx; char *
0x18003d6e4  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18003d6eb  mov     edx, 0D44h; void *
0x18003d6f0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003d6f5  nop
0x18003d6f6  mov     rcx, [rbp+string]; string
0x18003d6fa  call    cs:__imp_WindowsDeleteString
0x18003d700  jmp     short loc_18003D72E
0x18003d702  mov     r8, rbx; Size
0x18003d705  mov     rdx, r14; Src
0x18003d708  mov     rcx, rsi; void *
0x18003d70b  call    memcpy_0
0x18003d710  mov     [r13+0], rsi
0x18003d714  mov     rcx, [rbp+string]; string
0x18003d718  test    rdi, rdi
0x18003d71b  jz      short loc_18003D725
0x18003d71d  mov     [rbp+arg_18], r15
0x18003d721  mov     [r12], rdi
0x18003d725  call    cs:__imp_WindowsDeleteString
0x18003d72b  mov     ebx, r15d
0x18003d72e  mov     [rbp+string], r15
0x18003d732  lea     rcx, [rbp+arg_18]
0x18003d736  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?WluiFreeMemory@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WluiFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&WluiFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003d73b  nop
0x18003d73c  lea     rcx, [rbp+arg_30]
0x18003d740  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18003d745  mov     eax, ebx
0x18003d747  mov     rbx, [rsp+20h+arg_8]
0x18003d74c  add     rsp, 20h
0x18003d750  pop     r15
0x18003d752  pop     r14
0x18003d754  pop     r13
0x18003d756  pop     r12
0x18003d758  pop     rdi
0x18003d759  pop     rsi
0x18003d75a  pop     rbp
0x18003d75b  retn
```
