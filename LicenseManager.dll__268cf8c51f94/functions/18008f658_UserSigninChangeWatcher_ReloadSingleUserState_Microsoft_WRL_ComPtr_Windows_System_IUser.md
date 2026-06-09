# UserSigninChangeWatcher::ReloadSingleUserState(Microsoft::WRL::ComPtr<Windows::System::IUser> &)

- ea: `0x18008f658`
- end: `0x18008f7d0`
- name: `?ReloadSingleUserState@UserSigninChangeWatcher@@AEAAXAEAV?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@@Z`
- size: `376`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074cc0`
- `0x18008e4e0`

## callees

- `0x180013b50`
- `0x18008f658`
- `0x1800b8010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18008f6f7`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18008f6f7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f6e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18008f6e8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f67f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f67f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f6d6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f734`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008f7b6`

## string_xrefs

- `0x18008f6bf`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f706`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`
- `0x18008f792`: `onecoreuap\enduser\winstore\licensemanager\lib\service.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HRESULT __fastcall UserSigninChangeWatcher::ReloadSingleUserState(__int64 a1, __int64 a2)
{
  __int64 (*v3)(void); // rbx
  int v4; // eax
  HRESULT result; // eax
  const char *v6; // r9
  const wchar_t *StringRawBuffer; // rax
  unsigned int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v3 = *(__int64 (**)(void))(**(_QWORD **)a2 + 48LL);
  WindowsDeleteString(0);
  try
  {
    v4 = v3();
    if ( v4 >= 0 )
    {
      StringRawBuffer = WindowsGetStringRawBuffer(0, 0);
      v8 = wcstoul(StringRawBuffer, 0, 10);
      v9 = v8;
      if ( v8 == -1 )
      {
        LogMessage(
          1u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          0x3E4u,
          "UserSigninChangeWatcher::ReloadSingleUserState",
          (wchar_t *)L"Invalid user ID");
        result = WindowsDeleteString(0);
      }
      else
      {
        LogMessage(
          3u,
          "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
          0x3E8u,
          "UserSigninChangeWatcher::ReloadSingleUserState",
          (wchar_t *)L"Adding user, id=%d",
          v8);
        if ( (*(int (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)(a1 + 64) + 24LL))(*(_QWORD *)(a1 + 64), v9) < 0 )
        {
          LODWORD(v10) = v9;
          LogMessage(
            1u,
            "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
            0x3EFu,
            "UserSigninChangeWatcher::ReloadSingleUserState",
            (wchar_t *)L"Sign-in event failed for user, id=%d",
            v10);
        }
        result = WindowsDeleteString(0);
      }
    }
    else
    {
      LogMessage(
        1u,
        "onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
        0x3DDu,
        "UserSigninChangeWatcher::ReloadSingleUserState",
        (wchar_t *)L"user->get_NonRoamableId() failed, hr=0x%08x",
        v4);
      result = WindowsDeleteString(0);
    }
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x3F3,
             (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\lib\\service.cpp",
             v6);
  }
  return result;
}

```

## disassembly

```asm
0x18008f658  mov     [rsp+arg_0], rbx
0x18008f65d  mov     [rsp+arg_10], rsi
0x18008f662  push    rdi
0x18008f663  sub     rsp, 30h
0x18008f667  mov     rsi, rcx
0x18008f66a  mov     [rsp+38h+string], 0
0x18008f673  mov     rdi, [rdx]
0x18008f676  mov     rax, [rdi]
0x18008f679  mov     rbx, [rax+30h]
0x18008f67d  xor     ecx, ecx; string
0x18008f67f  call    cs:__imp_WindowsDeleteString
0x18008f685  mov     [rsp+38h+string], 0
0x18008f68e  lea     rdx, [rsp+38h+string]
0x18008f693  mov     rcx, rdi
0x18008f696  mov     rax, rbx
0x18008f699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f69e  test    eax, eax
0x18008f6a0  jns     short loc_18008F6E1
0x18008f6a2  mov     [rsp+38h+var_10], eax
0x18008f6a6  lea     rax, aUserGetNonroam; "user->get_NonRoamableId() failed, hr=0x"...
0x18008f6ad  mov     [rsp+38h+Format], rax; Format
0x18008f6b2  lea     r9, aUsersigninchan_0; "UserSigninChangeWatcher::ReloadSingleUs"...
0x18008f6b9  mov     r8d, 3DDh; unsigned int
0x18008f6bf  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008f6c6  mov     ecx, 1; unsigned int
0x18008f6cb  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008f6d0  nop
0x18008f6d1  mov     rcx, [rsp+38h+string]; string
0x18008f6d6  call    cs:__imp_WindowsDeleteString
0x18008f6dc  jmp     loc_18008F7BF
0x18008f6e1  xor     edx, edx; length
0x18008f6e3  mov     rcx, [rsp+38h+string]; string
0x18008f6e8  call    cs:__imp_WindowsGetStringRawBuffer
0x18008f6ee  xor     edx, edx; EndPtr
0x18008f6f0  lea     r8d, [rdx+0Ah]; Radix
0x18008f6f4  mov     rcx, rax; String
0x18008f6f7  call    cs:__imp_wcstoul
0x18008f6fd  mov     ebx, eax
0x18008f6ff  lea     r9, aUsersigninchan_0; "UserSigninChangeWatcher::ReloadSingleUs"...
0x18008f706  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008f70d  cmp     eax, 0FFFFFFFFh
0x18008f710  jnz     short loc_18008F73F
0x18008f712  lea     rax, aInvalidUserId; "Invalid user ID"
0x18008f719  mov     [rsp+38h+Format], rax; Format
0x18008f71e  mov     r8d, 3E4h; unsigned int
0x18008f724  mov     ecx, 1; unsigned int
0x18008f729  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008f72e  nop
0x18008f72f  mov     rcx, [rsp+38h+string]; string
0x18008f734  call    cs:__imp_WindowsDeleteString
0x18008f73a  jmp     loc_18008F7BF
0x18008f73f  mov     [rsp+38h+var_10], ebx
0x18008f743  lea     rax, aAddingUserIdD; "Adding user, id=%d"
0x18008f74a  mov     [rsp+38h+Format], rax; Format
0x18008f74f  mov     r8d, 3E8h; unsigned int
0x18008f755  mov     ecx, 3; unsigned int
0x18008f75a  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008f75f  mov     rcx, [rsi+40h]
0x18008f763  mov     rax, [rcx]
0x18008f766  mov     edx, ebx
0x18008f768  mov     rax, [rax+18h]
0x18008f76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f771  test    eax, eax
0x18008f773  jns     short loc_18008F7B1
0x18008f775  mov     [rsp+38h+var_10], ebx
0x18008f779  lea     rax, aSignInEventFai; "Sign-in event failed for user, id=%d"
0x18008f780  mov     [rsp+38h+Format], rax; Format
0x18008f785  lea     r9, aUsersigninchan_0; "UserSigninChangeWatcher::ReloadSingleUs"...
0x18008f78c  mov     r8d, 3EFh; unsigned int
0x18008f792  lea     rdx, aOnecoreuapEndu_25; "onecoreuap\\enduser\\winstore\\licensem"...
0x18008f799  mov     ecx, 1; unsigned int
0x18008f79e  call    ?LogMessage@@YAXIPEBDI0PEBGZZ; LogMessage(uint,char const *,uint,char const *,ushort const *,...)
0x18008f7a3  nop
0x18008f7a4  mov     rcx, [rsp+38h+string]; string
0x18008f7a9  call    cs:__imp_WindowsDeleteString
0x18008f7af  jmp     short loc_18008F7BF
0x18008f7b1  mov     rcx, [rsp+38h+string]; string
0x18008f7b6  call    cs:__imp_WindowsDeleteString
0x18008f7bc  nop
0x18008f7bd  jmp     short $+2
0x18008f7bf  mov     rbx, [rsp+38h+arg_0]
0x18008f7c4  mov     rsi, [rsp+38h+arg_10]
0x18008f7c9  add     rsp, 30h
0x18008f7cd  pop     rdi
0x18008f7ce  retn
```
