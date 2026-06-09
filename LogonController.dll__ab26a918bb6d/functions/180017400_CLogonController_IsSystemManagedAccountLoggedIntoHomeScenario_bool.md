# CLogonController::_IsSystemManagedAccountLoggedIntoHomeScenario(bool *)

- ea: `0x180017400`
- end: `0x18001761e`
- name: `?_IsSystemManagedAccountLoggedIntoHomeScenario@CLogonController@@AEAAJPEA_N@Z`
- size: `542`
- prototype: `__int64 __fastcall(CLogonController *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800182c0`

## callees

- `0x18000df10`
- `0x180017400`
- `0x180044558`
- `0x18005d488`
- `0x180073500`
- `0x18009d010`

## import_xrefs

- `KERNEL32!CompareStringOrdinal` at `0x1800175d5`
- `KERNEL32!CompareStringOrdinal` at `0x1800175d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800174fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017547`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017583`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017591`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800175f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800175bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLogonController::_IsSystemManagedAccountLoggedIntoHomeScenario(CLogonController *this, bool *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential *v6; // rcx
  int v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  __int64 v12; // rdi
  __int64 (__fastcall *v13)(__int64, HSTRING *); // rbx
  int v14; // eax
  const WCHAR *StringRawBuffer; // rbx
  const WCHAR *v16; // rax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential *v19; // [rsp+30h] [rbp-10h] BYREF
  __int64 v20; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  int v22; // [rsp+78h] [rbp+38h] BYREF
  HSTRING v23; // [rsp+80h] [rbp+40h] BYREF
  HSTRING string; // [rsp+88h] [rbp+48h] BYREF

  *a2 = 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v19);
  v4 = CLogonController::_EnsureSystemCredentialManager(this, &v19);
  v5 = v4;
  if ( v4 >= 0 )
  {
    if ( v19 )
    {
      v20 = 0;
      v7 = Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>::As<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>(
             &v19,
             &v20);
      v5 = v7;
      if ( v7 < 0 )
      {
        v8 = 3748;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v8,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
          (const char *)(unsigned int)v7,
          bIgnoreCase);
LABEL_18:
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
LABEL_22:
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v19);
        return v5;
      }
      if ( v20 )
      {
        v22 = 0;
        v7 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v20 + 48LL))(v20, &v22);
        v5 = v7;
        if ( v7 < 0 )
        {
          v8 = 3753;
          goto LABEL_11;
        }
        if ( v22 == 1 )
        {
          v23 = 0;
          v9 = *((_QWORD *)this + 18);
          v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)(v9 + 16) + 80LL);
          WindowsDeleteString(0);
          v23 = 0;
          v11 = v10(v9 + 16, &v23);
          v5 = v11;
          if ( v11 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xEAE,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
              (const char *)(unsigned int)v11,
              bIgnoreCase);
LABEL_17:
            WindowsDeleteString(v23);
            v23 = 0;
            goto LABEL_18;
          }
          string = 0;
          v12 = v20;
          v13 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v20 + 56LL);
          WindowsDeleteString(0);
          string = 0;
          v14 = v13(v12, &string);
          v5 = v14;
          if ( v14 < 0 )
          {
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0xEB1,
              (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
              (const char *)(unsigned int)v14,
              bIgnoreCase);
            WindowsDeleteString(string);
            string = 0;
            goto LABEL_17;
          }
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          v16 = WindowsGetStringRawBuffer(v23, 0);
          *a2 = CompareStringOrdinal(v16, -1, StringRawBuffer, -1, 1) == 2;
          WindowsDeleteString(string);
          string = 0;
          WindowsDeleteString(v23);
        }
      }
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v20);
    }
    v5 = 0;
    goto LABEL_22;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xE9F,
    (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\controller.cpp",
    (const char *)(unsigned int)v4,
    bIgnoreCase);
  v6 = v19;
  if ( v19 )
  {
    v19 = 0;
    (*(void (__fastcall **)(struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential *))(*(_QWORD *)v6 + 16LL))(v6);
  }
  return v5;
}

```

## disassembly

```asm
0x180017400  push    rbp
0x180017402  push    rbx
0x180017403  push    rsi
0x180017404  push    rdi
0x180017405  push    r14
0x180017407  mov     rbp, rsp
0x18001740a  sub     rsp, 40h
0x18001740e  mov     rsi, rdx
0x180017411  mov     rdi, rcx
0x180017414  xor     r14d, r14d
0x180017417  mov     [rdx], r14b
0x18001741a  mov     [rbp+var_10], r14
0x18001741e  lea     rcx, [rbp+var_10]
0x180017422  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180017427  lea     rdx, [rbp+var_10]; struct Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential **
0x18001742b  mov     rcx, rdi; this
0x18001742e  call    ?_EnsureSystemCredentialManager@CLogonController@@AEAAJPEAPEAUISystemManagedAccountCredential@Logon@SystemManagedAccount@Internal@Windows@@@Z; CLogonController::_EnsureSystemCredentialManager(Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential * *)
0x180017433  mov     ebx, eax
0x180017435  test    eax, eax
0x180017437  jns     short loc_180017471
0x180017439  mov     rcx, [rbp+28h]; this
0x18001743d  mov     r9d, eax; char *
0x180017440  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180017447  mov     edx, 0E9Fh; void *
0x18001744c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017451  nop
0x180017452  mov     rcx, [rbp+var_10]
0x180017456  test    rcx, rcx
0x180017459  jz      short loc_18001746C
0x18001745b  mov     [rbp+var_10], r14
0x18001745f  mov     rax, [rcx]
0x180017462  mov     rax, [rax+10h]
0x180017466  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001746b  nop
0x18001746c  jmp     loc_180017611
0x180017471  cmp     [rbp+var_10], r14
0x180017475  jz      loc_180017605
0x18001747b  mov     [rbp+var_8], r14
0x18001747f  lea     rdx, [rbp+var_8]
0x180017483  lea     rcx, [rbp+var_10]
0x180017487  call    ??$As@UISystemManagedAccountInfo@SystemManagedAccount@Internal@Windows@@@?$ComPtr@UISystemManagedAccountCredential@Logon@SystemManagedAccount@Internal@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISystemManagedAccountInfo@SystemManagedAccount@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::Logon::ISystemManagedAccountCredential>::As<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::SystemManagedAccount::ISystemManagedAccountInfo>>)
0x18001748c  mov     ebx, eax
0x18001748e  test    eax, eax
0x180017490  jns     short loc_180017499
0x180017492  mov     edx, 0EA4h
0x180017497  jmp     short loc_1800174C5
0x180017499  mov     rcx, [rbp+var_8]
0x18001749d  test    rcx, rcx
0x1800174a0  jz      loc_1800175FC
0x1800174a6  mov     [rbp+arg_8], r14d
0x1800174aa  mov     rax, [rcx]
0x1800174ad  lea     rdx, [rbp+arg_8]
0x1800174b1  mov     rax, [rax+30h]
0x1800174b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800174ba  mov     ebx, eax
0x1800174bc  test    eax, eax
0x1800174be  jns     short loc_1800174DD
0x1800174c0  mov     edx, 0EA9h; void *
0x1800174c5  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x1800174cc  mov     r9d, eax; char *
0x1800174cf  mov     rcx, [rbp+28h]; this
0x1800174d3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800174d8  jmp     loc_18001759B
0x1800174dd  cmp     [rbp+arg_8], 1
0x1800174e1  jnz     loc_1800175FC
0x1800174e7  mov     [rbp+arg_10], r14
0x1800174eb  mov     rdi, [rdi+90h]
0x1800174f2  mov     rax, [rdi+10h]
0x1800174f6  mov     rbx, [rax+50h]
0x1800174fa  xor     ecx, ecx; string
0x1800174fc  call    cs:__imp_WindowsDeleteString
0x180017502  mov     [rbp+arg_10], r14
0x180017506  lea     rdx, [rbp+arg_10]
0x18001750a  lea     rcx, [rdi+10h]
0x18001750e  mov     rax, rbx
0x180017511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017516  mov     ebx, eax
0x180017518  test    eax, eax
0x18001751a  jns     short loc_180017536
0x18001751c  mov     rcx, [rbp+28h]; this
0x180017520  mov     r9d, eax; char *
0x180017523  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x18001752a  mov     edx, 0EAEh; void *
0x18001752f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017534  jmp     short loc_18001758D
0x180017536  mov     [rbp+string], r14
0x18001753a  mov     rdi, [rbp+var_8]
0x18001753e  mov     rax, [rdi]
0x180017541  mov     rbx, [rax+38h]
0x180017545  xor     ecx, ecx; string
0x180017547  call    cs:__imp_WindowsDeleteString
0x18001754d  mov     [rbp+string], r14
0x180017551  lea     rdx, [rbp+string]
0x180017555  mov     rcx, rdi
0x180017558  mov     rax, rbx
0x18001755b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017560  mov     ebx, eax
0x180017562  test    eax, eax
0x180017564  jns     short loc_1800175A6
0x180017566  mov     rcx, [rbp+28h]; this
0x18001756a  mov     r9d, eax; char *
0x18001756d  lea     r8, aPcshellShellAu_14; "pcshell\\shell\\auth\\authux\\controlle"...
0x180017574  mov     edx, 0EB1h; void *
0x180017579  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001757e  nop
0x18001757f  mov     rcx, [rbp+string]; string
0x180017583  call    cs:__imp_WindowsDeleteString
0x180017589  mov     [rbp+string], r14
0x18001758d  mov     rcx, [rbp+arg_10]; string
0x180017591  call    cs:__imp_WindowsDeleteString
0x180017597  mov     [rbp+arg_10], r14
0x18001759b  lea     rcx, [rbp+var_8]
0x18001759f  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x1800175a4  jmp     short loc_180017608
0x1800175a6  xor     edx, edx; length
0x1800175a8  mov     rcx, [rbp+string]; string
0x1800175ac  call    cs:__imp_WindowsGetStringRawBuffer
0x1800175b2  mov     rbx, rax
0x1800175b5  xor     edx, edx; length
0x1800175b7  mov     rcx, [rbp+arg_10]; string
0x1800175bb  call    cs:__imp_WindowsGetStringRawBuffer
0x1800175c1  mov     [rsp+40h+bIgnoreCase], 1; bIgnoreCase
0x1800175c9  or      edx, 0FFFFFFFFh; cchCount1
0x1800175cc  mov     r9d, edx; cchCount2
0x1800175cf  mov     r8, rbx; lpString2
0x1800175d2  mov     rcx, rax; lpString1
0x1800175d5  call    cs:__imp_CompareStringOrdinal
0x1800175db  cmp     eax, 2
0x1800175de  setz    al
0x1800175e1  mov     [rsi], al
0x1800175e3  mov     rcx, [rbp+string]; string
0x1800175e7  call    cs:__imp_WindowsDeleteString
0x1800175ed  mov     [rbp+string], r14
0x1800175f1  mov     rcx, [rbp+arg_10]; string
0x1800175f5  call    cs:__imp_WindowsDeleteString
0x1800175fb  nop
0x1800175fc  lea     rcx, [rbp+var_8]
0x180017600  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180017605  mov     ebx, r14d
0x180017608  lea     rcx, [rbp+var_10]
0x18001760c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180017611  mov     eax, ebx
0x180017613  add     rsp, 40h
0x180017617  pop     r14
0x180017619  pop     rdi
0x18001761a  pop     rsi
0x18001761b  pop     rbx
0x18001761c  pop     rbp
0x18001761d  retn
```
