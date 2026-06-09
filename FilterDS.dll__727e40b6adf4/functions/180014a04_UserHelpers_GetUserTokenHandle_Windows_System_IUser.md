# UserHelpers::GetUserTokenHandle(Windows::System::IUser *)

- ea: `0x180014a04`
- end: `0x180014c17`
- name: `?GetUserTokenHandle@UserHelpers@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAUIUser@System@Windows@@@Z`
- size: `531`
- prototype: `PHANDLE __fastcall(PHANDLE TokenHandle, UserHelpers *this)`
- caller_count: `2`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800136c0`
- `0x18001486c`

## callees

- `0x1800028c4`
- `0x18000cd18`
- `0x180014794`
- `0x180014a04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014a9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014ae0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b22`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014b86`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b5a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014a64`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014ab2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180014b5a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014b03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180014b9a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180014b67`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014b14`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014bab`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014b14`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180014bab`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014ad2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014b7c`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014ad2`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180014b7c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b52`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014a5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014aaa`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180014b52`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180014a7f`
- `ext-ms-win-session-usermgr-l1-1-0!UMgrQueryUserToken` at `0x180014a7f`

## pseudocode

```c
PHANDLE __fastcall UserHelpers::GetUserTokenHandle(PHANDLE TokenHandle, UserHelpers *this)
{
  struct Windows::System::IUser *v4; // rdx
  void *v5; // rsi
  DWORD LastError; // ebx
  __int64 UserContextToken; // rax
  int UserToken; // eax
  void *v9; // rsi
  DWORD v10; // ebx
  HANDLE CurrentThread; // rax
  signed int v12; // eax
  HANDLE CurrentProcess; // rax
  void *v14; // rsi
  DWORD v15; // ebx
  HANDLE v16; // rax
  HANDLE v17; // rax
  bool v18; // sf
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *TokenHandle = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent(TokenHandle, this) && this )
  {
    v5 = *TokenHandle;
    if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(v5);
      SetLastError(LastError);
    }
    *TokenHandle = 0;
    UserContextToken = UserHelpers::GetUserContextToken(this, v4);
    UserToken = UMgrQueryUserToken(UserContextToken, TokenHandle);
    if ( UserToken < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x60,
        (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
        (const char *)(unsigned int)UserToken,
        1);
    return TokenHandle;
  }
  v9 = *TokenHandle;
  if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v10 = GetLastError();
    CloseHandle(v9);
    SetLastError(v10);
  }
  *TokenHandle = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, TokenHandle) )
    goto LABEL_24;
  v12 = GetLastError();
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 != -2147023888 )
    goto LABEL_27;
  CurrentProcess = GetCurrentProcess();
  if ( OpenProcessToken(CurrentProcess, 8u, TokenHandle) )
    goto LABEL_24;
  v12 = GetLastError();
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 != -2147023888 )
    goto LABEL_27;
  v14 = *TokenHandle;
  if ( (char *)*TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    v15 = GetLastError();
    CloseHandle(v14);
    SetLastError(v15);
  }
  *TokenHandle = 0;
  v16 = GetCurrentThread();
  if ( OpenThreadToken(v16, 8u, 1, TokenHandle) )
    goto LABEL_24;
  v12 = GetLastError();
  if ( v12 > 0 )
    v12 = (unsigned __int16)v12 | 0x80070000;
  if ( v12 != -2147023888 )
    goto LABEL_27;
  v17 = GetCurrentProcess();
  if ( OpenProcessToken(v17, 8u, TokenHandle) )
  {
LABEL_24:
    v12 = 0;
  }
  else
  {
    v12 = GetLastError();
    v18 = v12 < 0;
    if ( v12 <= 0 )
      goto LABEL_28;
    v12 = (unsigned __int16)v12 | 0x80070000;
  }
LABEL_27:
  v18 = v12 < 0;
LABEL_28:
  if ( v18 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x5B,
      (int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\textinput\\UserHelpers.h",
      (const char *)(unsigned int)v12,
      1);
  return TokenHandle;
}

```

## disassembly

```asm
0x180014a04  mov     rax, rsp
0x180014a07  mov     [rax+10h], rbx
0x180014a0b  mov     [rax+18h], rbp
0x180014a0f  mov     [rax+8], rcx
0x180014a13  push    rsi
0x180014a14  push    rdi
0x180014a15  push    r15
0x180014a17  sub     rsp, 30h
0x180014a1b  mov     rbp, rdx
0x180014a1e  mov     rdi, rcx
0x180014a21  mov     dword ptr [rax-28h], 0
0x180014a28  mov     qword ptr [rcx], 0
0x180014a2f  mov     dword ptr [rax-28h], 1
0x180014a36  call    IsUMgrQueryUserContextPresent
0x180014a3b  test    al, al
0x180014a3d  jz      short loc_180014A92
0x180014a3f  test    rbp, rbp
0x180014a42  jz      short loc_180014A92
0x180014a44  mov     rsi, [rdi]
0x180014a47  lea     rax, [rsi-1]
0x180014a4b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014a4f  ja      short loc_180014A6A
0x180014a51  call    cs:__imp_GetLastError
0x180014a57  mov     ebx, eax
0x180014a59  mov     rcx, rsi; hObject
0x180014a5c  call    cs:__imp_CloseHandle
0x180014a62  mov     ecx, ebx; dwErrCode
0x180014a64  call    cs:__imp_SetLastError
0x180014a6a  mov     qword ptr [rdi], 0
0x180014a71  mov     rcx, rbp; this
0x180014a74  call    ?GetUserContextToken@UserHelpers@@YA_KPEAUIUser@System@Windows@@@Z; UserHelpers::GetUserContextToken(Windows::System::IUser *)
0x180014a79  mov     rdx, rdi
0x180014a7c  mov     rcx, rax
0x180014a7f  call    cs:__imp_UMgrQueryUserToken
0x180014a85  test    eax, eax
0x180014a87  js      loc_180014BFD
0x180014a8d  jmp     loc_180014BCD
0x180014a92  mov     rsi, [rdi]
0x180014a95  lea     rax, [rsi-1]
0x180014a99  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014a9d  ja      short loc_180014AB8
0x180014a9f  call    cs:__imp_GetLastError
0x180014aa5  mov     ebx, eax
0x180014aa7  mov     rcx, rsi; hObject
0x180014aaa  call    cs:__imp_CloseHandle
0x180014ab0  mov     ecx, ebx; dwErrCode
0x180014ab2  call    cs:__imp_SetLastError
0x180014ab8  mov     qword ptr [rdi], 0
0x180014abf  call    cs:__imp_GetCurrentThread
0x180014ac5  mov     rcx, rax; ThreadHandle
0x180014ac8  mov     r9, rdi; TokenHandle
0x180014acb  xor     r8d, r8d; OpenAsSelf
0x180014ace  lea     edx, [r8+8]; DesiredAccess
0x180014ad2  call    cs:__imp_OpenThreadToken
0x180014ad8  test    eax, eax
0x180014ada  jnz     loc_180014BB5
0x180014ae0  call    cs:__imp_GetLastError
0x180014ae6  mov     r15d, 80070000h
0x180014aec  test    eax, eax
0x180014aee  jle     short loc_180014AF6
0x180014af0  movzx   eax, ax
0x180014af3  or      eax, r15d
0x180014af6  mov     ebp, 800703F0h
0x180014afb  cmp     eax, ebp
0x180014afd  jnz     loc_180014BC9
0x180014b03  call    cs:__imp_GetCurrentProcess
0x180014b09  mov     rcx, rax; ProcessHandle
0x180014b0c  mov     r8, rdi; TokenHandle
0x180014b0f  mov     edx, 8; DesiredAccess
0x180014b14  call    cs:__imp_OpenProcessToken
0x180014b1a  test    eax, eax
0x180014b1c  jnz     loc_180014BB5
0x180014b22  call    cs:__imp_GetLastError
0x180014b28  test    eax, eax
0x180014b2a  jle     short loc_180014B32
0x180014b2c  movzx   eax, ax
0x180014b2f  or      eax, r15d
0x180014b32  cmp     eax, ebp
0x180014b34  jnz     loc_180014BC9
0x180014b3a  mov     rsi, [rdi]
0x180014b3d  lea     rax, [rsi-1]
0x180014b41  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180014b45  ja      short loc_180014B60
0x180014b47  call    cs:__imp_GetLastError
0x180014b4d  mov     ebx, eax
0x180014b4f  mov     rcx, rsi; hObject
0x180014b52  call    cs:__imp_CloseHandle
0x180014b58  mov     ecx, ebx; dwErrCode
0x180014b5a  call    cs:__imp_SetLastError
0x180014b60  mov     qword ptr [rdi], 0
0x180014b67  call    cs:__imp_GetCurrentThread
0x180014b6d  mov     rcx, rax; ThreadHandle
0x180014b70  mov     r9, rdi; TokenHandle
0x180014b73  mov     edx, 8; DesiredAccess
0x180014b78  lea     r8d, [rdx-7]; OpenAsSelf
0x180014b7c  call    cs:__imp_OpenThreadToken
0x180014b82  test    eax, eax
0x180014b84  jnz     short loc_180014BB5
0x180014b86  call    cs:__imp_GetLastError
0x180014b8c  test    eax, eax
0x180014b8e  jle     short loc_180014B96
0x180014b90  movzx   eax, ax
0x180014b93  or      eax, r15d
0x180014b96  cmp     eax, ebp
0x180014b98  jnz     short loc_180014BC9
0x180014b9a  call    cs:__imp_GetCurrentProcess
0x180014ba0  mov     rcx, rax; ProcessHandle
0x180014ba3  mov     r8, rdi; TokenHandle
0x180014ba6  mov     edx, 8; DesiredAccess
0x180014bab  call    cs:__imp_OpenProcessToken
0x180014bb1  test    eax, eax
0x180014bb3  jz      short loc_180014BB9
0x180014bb5  xor     eax, eax
0x180014bb7  jmp     short loc_180014BC9
0x180014bb9  call    cs:__imp_GetLastError
0x180014bbf  test    eax, eax
0x180014bc1  jle     short loc_180014BCB
0x180014bc3  movzx   eax, ax
0x180014bc6  or      eax, r15d
0x180014bc9  test    eax, eax
0x180014bcb  js      short loc_180014BE3
0x180014bcd  mov     rax, rdi
0x180014bd0  mov     rbx, [rsp+48h+arg_8]
0x180014bd5  mov     rbp, [rsp+48h+arg_10]
0x180014bda  add     rsp, 30h
0x180014bde  pop     r15
0x180014be0  pop     rdi
0x180014be1  pop     rsi
0x180014be2  retn
0x180014be3  mov     rcx, [rsp+48h]; this
0x180014be8  mov     r9d, eax; char *
0x180014beb  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014bf2  mov     edx, 5Bh ; '['; void *
0x180014bf7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180014bfd  mov     rcx, [rsp+48h]; this
0x180014c02  mov     r9d, eax; char *
0x180014c05  lea     r8, aOnecoreInterna_6; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180014c0c  mov     edx, 60h ; '`'; void *
0x180014c11  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
