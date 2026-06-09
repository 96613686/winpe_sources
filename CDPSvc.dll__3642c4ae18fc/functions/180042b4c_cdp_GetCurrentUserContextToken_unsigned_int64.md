# cdp::GetCurrentUserContextToken(unsigned __int64 &)

- ea: `0x180042b4c`
- end: `0x180042ccc`
- name: `?GetCurrentUserContextToken@cdp@@YAJAEA_K@Z`
- size: `384`
- prototype: `__int64 __fastcall(cdp *__hidden this, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting`

## callers

- `0x1800125fc`
- `0x1800429e0`

## callees

- `0x180019938`
- `0x18001999c`
- `0x1800257e0`
- `0x18004263c`
- `0x1800427e4`
- `0x180042b4c`
- `0x180042d08`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180042c1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042b91`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180042b91`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042ba7`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180042ba7`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042c2c`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180042c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042bb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180042c36`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c03`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180042c03`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall cdp::GetCurrentUserContextToken(cdp *this, unsigned __int64 *a2)
{
  unsigned __int64 *v3; // r8
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  int v6; // ecx
  int v7; // r9d
  signed int v8; // ebx
  void *v9; // rbx
  HANDLE CurrentProcess; // rax
  signed int v11; // eax
  int v12; // ecx
  int v13; // r9d
  int UserManagerForUserContextToken; // eax
  signed int v16; // [rsp+50h] [rbp+20h] BYREF
  int v17; // [rsp+58h] [rbp+28h] BYREF
  void *TokenHandle; // [rsp+60h] [rbp+30h] BYREF

  *(_QWORD *)this = 0;
  if ( (unsigned __int8)IsUMgrQueryUserContextPresent(this, a2) )
  {
    TokenHandle = 0;
    if ( (NtCurrentPeb()->BitField & 0x20) == 0 )
    {
      TokenHandle = 0;
      CurrentThread = GetCurrentThread();
      if ( !OpenThreadToken(CurrentThread, 8u, 1, &TokenHandle) )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        if ( v8 != -2147023888 )
        {
          v16 = v8;
          if ( v8 >= 0 )
          {
LABEL_20:
            wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
            return (unsigned int)v8;
          }
          v17 = 140;
LABEL_19:
          Log<long &,char const (&)[20],int>(
            v6,
            (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
            (unsigned int)&v16,
            v7,
            (__int64)&v17);
          v8 = v16;
          goto LABEL_20;
        }
        v9 = TokenHandle;
        if ( (char *)TokenHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
        {
          wil::last_error_context::last_error_context((wil::last_error_context *)&v16);
          CloseHandle(v9);
          wil::last_error_context::~last_error_context((wil::last_error_context *)&v16);
        }
        TokenHandle = 0;
        CurrentProcess = GetCurrentProcess();
        if ( !OpenProcessToken(CurrentProcess, 8u, &TokenHandle) )
        {
          v11 = GetLastError();
          if ( v11 > 0 )
            v11 = (unsigned __int16)v11 | 0x80070000;
          v16 = v11;
          if ( v11 < 0 )
          {
            v17 = 144;
            Log<long &,char const (&)[20],int>(
              v12,
              (unsigned int)"{\"hr\":\"0x%08x\",\"file\":\"%s\",\"line\":%d,\"text\":\"Error:\"}",
              (unsigned int)&v16,
              v13,
              (__int64)&v17);
            v11 = v16;
          }
          v8 = v11;
          goto LABEL_20;
        }
      }
    }
    UserManagerForUserContextToken = cdp::QueryUserManagerForUserContextToken((cdp *)TokenHandle, this, v3);
    if ( UserManagerForUserContextToken < 0 )
    {
      v16 = UserManagerForUserContextToken;
      v17 = 149;
      goto LABEL_19;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
  }
  return 0;
}

```

## disassembly

```asm
0x180042b4c  push    rbp
0x180042b4e  push    rbx
0x180042b4f  push    rdi
0x180042b50  mov     rbp, rsp
0x180042b53  sub     rsp, 30h
0x180042b57  mov     rdi, rcx
0x180042b5a  mov     qword ptr [rcx], 0
0x180042b61  call    IsUMgrQueryUserContextPresent
0x180042b66  test    al, al
0x180042b68  jz      loc_180042CC2
0x180042b6e  mov     [rbp+TokenHandle], 0
0x180042b76  mov     rax, gs:60h
0x180042b7f  test    byte ptr [rax+3], 20h
0x180042b83  jnz     loc_180042C76
0x180042b89  mov     [rbp+TokenHandle], 0
0x180042b91  call    cs:__imp_GetCurrentThread
0x180042b97  lea     r9, [rbp+TokenHandle]; TokenHandle
0x180042b9b  mov     edx, 8; DesiredAccess
0x180042ba0  lea     r8d, [rdx-7]; OpenAsSelf
0x180042ba4  mov     rcx, rax; ThreadHandle
0x180042ba7  call    cs:__imp_OpenThreadToken
0x180042bad  test    eax, eax
0x180042baf  jnz     loc_180042C76
0x180042bb5  call    cs:__imp_GetLastError
0x180042bbb  mov     ebx, eax
0x180042bbd  test    eax, eax
0x180042bbf  jle     short loc_180042BCA
0x180042bc1  movzx   ebx, ax
0x180042bc4  or      ebx, 80070000h
0x180042bca  cmp     ebx, 800703F0h
0x180042bd0  jz      short loc_180042BE9
0x180042bd2  mov     [rbp+arg_0], ebx
0x180042bd5  test    ebx, ebx
0x180042bd7  jns     loc_180042CAC
0x180042bdd  mov     [rbp+arg_8], 8Ch
0x180042be4  jmp     loc_180042C90
0x180042be9  mov     rbx, [rbp+TokenHandle]
0x180042bed  lea     rax, [rbx-1]
0x180042bf1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180042bf5  ja      short loc_180042C12
0x180042bf7  lea     rcx, [rbp+arg_0]; this
0x180042bfb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180042c00  mov     rcx, rbx; hObject
0x180042c03  call    cs:__imp_CloseHandle
0x180042c09  lea     rcx, [rbp+arg_0]; this
0x180042c0d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180042c12  mov     [rbp+TokenHandle], 0
0x180042c1a  call    cs:__imp_GetCurrentProcess
0x180042c20  lea     r8, [rbp+TokenHandle]; TokenHandle
0x180042c24  mov     edx, 8; DesiredAccess
0x180042c29  mov     rcx, rax; ProcessHandle
0x180042c2c  call    cs:__imp_OpenProcessToken
0x180042c32  test    eax, eax
0x180042c34  jnz     short loc_180042C76
0x180042c36  call    cs:__imp_GetLastError
0x180042c3c  test    eax, eax
0x180042c3e  jle     short loc_180042C48
0x180042c40  movzx   eax, ax
0x180042c43  or      eax, 80070000h
0x180042c48  mov     [rbp+arg_0], eax
0x180042c4b  test    eax, eax
0x180042c4d  jns     short loc_180042C72
0x180042c4f  mov     [rbp+arg_8], 90h
0x180042c56  lea     rax, [rbp+arg_8]
0x180042c5a  mov     [rsp+30h+var_10], rax
0x180042c5f  lea     r8, [rbp+arg_0]
0x180042c63  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042c6a  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180042c6f  mov     eax, [rbp+arg_0]
0x180042c72  mov     ebx, eax
0x180042c74  jmp     short loc_180042CAC
0x180042c76  mov     rdx, rdi; void *
0x180042c79  mov     rcx, [rbp+TokenHandle]; this
0x180042c7d  call    ?QueryUserManagerForUserContextToken@cdp@@YAJPEAXAEA_K@Z; cdp::QueryUserManagerForUserContextToken(void *,unsigned __int64 &)
0x180042c82  test    eax, eax
0x180042c84  jns     short loc_180042CB9
0x180042c86  mov     [rbp+arg_0], eax
0x180042c89  mov     [rbp+arg_8], 95h
0x180042c90  lea     rax, [rbp+arg_8]
0x180042c94  mov     [rsp+30h+var_10], rax
0x180042c99  lea     r8, [rbp+arg_0]
0x180042c9d  lea     rdx, aHr0x08xFileSLi_1; "{\"hr\":\"0x%08x\",\"file\":\"%s\",\"li"...
0x180042ca4  call    ??$Log@AEAJAEAY0BE@$$CBDH@@YAXW4CDPLogLevel@@PEBDAEAJAEAY0BE@$$CBD$$QEAH@Z; Log<long &,char const (&)[20],int>(CDPLogLevel,char const *,long &,char const (&)[20],int &&)
0x180042ca9  mov     ebx, [rbp+arg_0]
0x180042cac  lea     rcx, [rbp+TokenHandle]
0x180042cb0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042cb5  mov     eax, ebx
0x180042cb7  jmp     short loc_180042CC4
0x180042cb9  lea     rcx, [rbp+TokenHandle]
0x180042cbd  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180042cc2  xor     eax, eax
0x180042cc4  add     rsp, 30h
0x180042cc8  pop     rdi
0x180042cc9  pop     rbx
0x180042cca  pop     rbp
0x180042ccb  retn
```
