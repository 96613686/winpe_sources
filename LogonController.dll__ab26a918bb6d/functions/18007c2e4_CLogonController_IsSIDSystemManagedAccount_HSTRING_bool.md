# CLogonController::_IsSIDSystemManagedAccount(HSTRING__ *,bool *)

- ea: `0x18007c2e4`
- end: `0x18007c471`
- name: `?_IsSIDSystemManagedAccount@CLogonController@@AEAAJPEAUHSTRING__@@PEA_N@Z`
- size: `397`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, HSTRING string, bool *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800182c0`
- `0x18001ac90`
- `0x18005e2b8`
- `0x1800752b0`

## callees

- `0x18000df10`
- `0x180044558`
- `0x18005d488`
- `0x180073500`
- `0x18007c2e4`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x18007c42f`
- `KERNEL32!CompareStringOrdinal` at `0x18007c42f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c3b1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c3f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18007c441`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c415`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18007c415`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CLogonController::_IsSIDSystemManagedAccount(CLogonController *this, HSTRING string, bool *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  int v8; // eax
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rdi
  int v11; // eax
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v13; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential *v16[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+18h]
  HSTRING stringa; // [rsp+70h] [rbp+30h] BYREF
  __int64 v19; // [rsp+78h] [rbp+38h] BYREF

  *a3 = 0;
  v16[0] = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v16);
  v6 = CLogonController::_EnsureSystemCredentialManager(this, v16);
  v7 = v6;
  if ( v6 >= 0 )
  {
    if ( v16[0] )
    {
      v19 = 0;
      v8 = Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>::As<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>(
             v16,
             &v19);
      v7 = v8;
      if ( v8 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xEC5,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v8,
          bIgnoreCase);
LABEL_6:
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v19);
        goto LABEL_13;
      }
      v9 = v19;
      if ( v19 )
      {
        stringa = 0;
        v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v19 + 56LL);
        WindowsDeleteString(0);
        stringa = 0;
        v11 = v10(v9, &stringa);
        v7 = v11;
        if ( v11 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xECA,
            (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
            (const char *)(unsigned int)v11,
            bIgnoreCase);
          WindowsDeleteString(stringa);
          stringa = 0;
          goto LABEL_6;
        }
        StringRawBuffer = WindowsGetStringRawBuffer(stringa, 0);
        v13 = WindowsGetStringRawBuffer(string, 0);
        *a3 = CompareStringOrdinal(v13, -1, StringRawBuffer, -1, 1) == 2;
        WindowsDeleteString(stringa);
      }
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v19);
    }
    v7 = 0;
    goto LABEL_13;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xEC0,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)v6,
    bIgnoreCase);
LABEL_13:
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v16);
  return v7;
}

```

## disassembly

```asm
0x18007c2e4  mov     [rsp-18h+arg_0], rbx
0x18007c2e9  mov     [rsp-18h+arg_8], rsi
0x18007c2ee  push    rbp
0x18007c2ef  push    rdi
0x18007c2f0  push    r14
0x18007c2f2  mov     rbp, rsp
0x18007c2f5  sub     rsp, 40h
0x18007c2f9  mov     rsi, r8
0x18007c2fc  mov     r14, rdx
0x18007c2ff  mov     rbx, rcx
0x18007c302  mov     byte ptr [r8], 0
0x18007c306  mov     [rbp+var_10], 0
0x18007c30e  lea     rcx, [rbp+var_10]
0x18007c312  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18007c317  lea     rdx, [rbp+var_10]; struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential **
0x18007c31b  mov     rcx, rbx; this
0x18007c31e  call    ?_EnsureSystemCredentialManager@CLogonController@@AEAAJPEAPEAUISystemManagedAccountCredential@Logon@SystemManagedAccount@Internal@Windows@@@Z; CLogonController::_EnsureSystemCredentialManager(Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential * *)
0x18007c323  mov     ebx, eax
0x18007c325  test    eax, eax
0x18007c327  jns     short loc_18007C346
0x18007c329  mov     rcx, [rbp+18h]; this
0x18007c32d  mov     r9d, eax; char *
0x18007c330  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18007c337  mov     edx, 0EC0h; void *
0x18007c33c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c341  jmp     loc_18007C453
0x18007c346  cmp     [rbp+var_10], 0
0x18007c34b  jz      loc_18007C451
0x18007c351  mov     [rbp+arg_18], 0
0x18007c359  lea     rdx, [rbp+arg_18]
0x18007c35d  lea     rcx, [rbp+var_10]
0x18007c361  call    ??$As@UISystemManagedAccountInfo@SystemManagedAccount@Internal@Windows@@@?$ComPtr@UISystemManagedAccountCredential@Logon@SystemManagedAccount@Internal@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISystemManagedAccountInfo@SystemManagedAccount@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>::As<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>>)
0x18007c366  mov     ebx, eax
0x18007c368  test    eax, eax
0x18007c36a  jns     short loc_18007C393
0x18007c36c  mov     rcx, [rbp+18h]; this
0x18007c370  mov     r9d, eax; char *
0x18007c373  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18007c37a  mov     edx, 0EC5h; void *
0x18007c37f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c384  nop
0x18007c385  lea     rcx, [rbp+arg_18]
0x18007c389  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18007c38e  jmp     loc_18007C453
0x18007c393  mov     rbx, [rbp+arg_18]
0x18007c397  test    rbx, rbx
0x18007c39a  jz      loc_18007C448
0x18007c3a0  mov     [rbp+string], 0
0x18007c3a8  mov     rax, [rbx]
0x18007c3ab  mov     rdi, [rax+38h]
0x18007c3af  xor     ecx, ecx; string
0x18007c3b1  call    cs:__imp_WindowsDeleteString
0x18007c3b7  mov     [rbp+string], 0
0x18007c3bf  lea     rdx, [rbp+string]
0x18007c3c3  mov     rcx, rbx
0x18007c3c6  mov     rax, rdi
0x18007c3c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c3ce  mov     ebx, eax
0x18007c3d0  test    eax, eax
0x18007c3d2  jns     short loc_18007C401
0x18007c3d4  mov     rcx, [rbp+18h]; this
0x18007c3d8  mov     r9d, eax; char *
0x18007c3db  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18007c3e2  mov     edx, 0ECAh; void *
0x18007c3e7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18007c3ec  nop
0x18007c3ed  mov     rcx, [rbp+string]; string
0x18007c3f1  call    cs:__imp_WindowsDeleteString
0x18007c3f7  mov     [rbp+string], 0
0x18007c3ff  jmp     short loc_18007C385
0x18007c401  xor     edx, edx; length
0x18007c403  mov     rcx, [rbp+string]; string
0x18007c407  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c40d  mov     rbx, rax
0x18007c410  xor     edx, edx; length
0x18007c412  mov     rcx, r14; string
0x18007c415  call    cs:__imp_WindowsGetStringRawBuffer
0x18007c41b  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x18007c423  or      edx, 0FFFFFFFFh; cchCount1
0x18007c426  mov     r9d, edx; cchCount2
0x18007c429  mov     r8, rbx; lpString2
0x18007c42c  mov     rcx, rax; lpString1
0x18007c42f  call    cs:__imp_CompareStringOrdinal
0x18007c435  cmp     eax, 2
0x18007c438  setz    al
0x18007c43b  mov     [rsi], al
0x18007c43d  mov     rcx, [rbp+string]; string
0x18007c441  call    cs:__imp_WindowsDeleteString
0x18007c447  nop
0x18007c448  lea     rcx, [rbp+arg_18]
0x18007c44c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18007c451  xor     ebx, ebx
0x18007c453  lea     rcx, [rbp+var_10]
0x18007c457  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x18007c45c  mov     eax, ebx
0x18007c45e  mov     rbx, [rsp+40h+arg_0]
0x18007c463  mov     rsi, [rsp+40h+arg_8]
0x18007c468  add     rsp, 40h
0x18007c46c  pop     r14
0x18007c46e  pop     rdi
0x18007c46f  pop     rbp
0x18007c470  retn
```
