# AddUserToProcessObject(void *)

- ea: `0x180087e44`
- end: `0x180087f73`
- name: `?AddUserToProcessObject@@YAJPEAX@Z`
- size: `303`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180086f20`

## callees

- `0x18001330c`
- `0x18001332c`
- `0x180087a70`
- `0x180087c40`
- `0x180087e44`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087ee9`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180087ee9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087e56`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180087e56`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180087e66`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180087e66`

## string_xrefs

- `0x180087e84`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087eb8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087ef8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180087f35`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
__int64 __fastcall AddUserToProcessObject(void *a1)
{
  DWORD CurrentProcessId; // eax
  HANDLE v3; // rbx
  const char *v4; // r9
  unsigned int LastError; // ebx
  int v6; // eax
  int v7; // edi
  const char *v8; // r9
  int v9; // eax
  int v11; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *TokenHandle; // [rsp+38h] [rbp+10h] BYREF
  HANDLE v14; // [rsp+40h] [rbp+18h] BYREF

  CurrentProcessId = GetCurrentProcessId();
  v3 = OpenProcess(0x60400u, 0, CurrentProcessId);
  v14 = v3;
  if ( (((unsigned __int64)v3 + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
  {
    v6 = AddUserToHandle(v3, a1, 0x101400u);
    v7 = v6;
    if ( v6 >= 0 )
    {
      TokenHandle = 0;
      if ( OpenProcessToken(v3, 0x60008u, &TokenHandle) )
      {
        v9 = AddUserToHandle(TokenHandle, a1, 0xEu);
        LastError = v9;
        if ( v9 >= 0 )
        {
          wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          LastError = 0;
          goto LABEL_11;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x87,
          (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
          (const char *)(unsigned int)v9,
          v11);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x85,
                      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                      v8);
      }
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x82,
        (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
        (const char *)(unsigned int)v6,
        v11);
      LastError = v7;
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x80,
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                  v4);
  }
LABEL_11:
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v14);
  return LastError;
}

```

## disassembly

```asm
0x180087e44  mov     [rsp+arg_0], rbx
0x180087e49  mov     [rsp+arg_18], rsi
0x180087e4e  push    rdi; int
0x180087e4f  sub     rsp, 20h
0x180087e53  mov     rsi, rcx
0x180087e56  call    cs:__imp_GetCurrentProcessId
0x180087e5c  xor     edx, edx; bInheritHandle
0x180087e5e  mov     ecx, 60400h; dwDesiredAccess
0x180087e63  mov     r8d, eax; dwProcessId
0x180087e66  call    cs:__imp_OpenProcess
0x180087e6c  mov     rbx, rax
0x180087e6f  mov     [rsp+28h+arg_10], rax
0x180087e74  inc     rax
0x180087e77  test    rax, 0FFFFFFFFFFFFFFFEh
0x180087e7d  jnz     short loc_180087E9C
0x180087e7f  mov     rcx, [rsp+28h]; this
0x180087e84  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087e8b  mov     edx, 80h; void *
0x180087e90  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180087e95  mov     ebx, eax
0x180087e97  jmp     loc_180087F57
0x180087e9c  mov     r8d, 101400h; unsigned int
0x180087ea2  mov     rdx, rsi; void *
0x180087ea5  mov     rcx, rbx; Handle
0x180087ea8  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x180087ead  mov     edi, eax
0x180087eaf  test    eax, eax
0x180087eb1  jns     short loc_180087ED3
0x180087eb3  mov     rcx, [rsp+28h]; this
0x180087eb8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087ebf  mov     r9d, eax; char *
0x180087ec2  mov     edx, 82h; void *
0x180087ec7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087ecc  mov     ebx, edi
0x180087ece  jmp     loc_180087F57
0x180087ed3  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180087ed8  mov     [rsp+28h+TokenHandle], 0
0x180087ee1  mov     edx, 60008h; DesiredAccess
0x180087ee6  mov     rcx, rbx; ProcessHandle
0x180087ee9  call    cs:__imp_OpenProcessToken
0x180087eef  test    eax, eax
0x180087ef1  jnz     short loc_180087F17
0x180087ef3  mov     rcx, [rsp+28h]; this
0x180087ef8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087eff  mov     edx, 85h; void *
0x180087f04  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180087f09  mov     ebx, eax
0x180087f0b  lea     rcx, [rsp+28h+TokenHandle]
0x180087f10  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180087f15  jmp     short loc_180087F57
0x180087f17  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x180087f1c  mov     r8d, 0Eh; unsigned int
0x180087f22  mov     rdx, rsi; void *
0x180087f25  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x180087f2a  mov     ebx, eax
0x180087f2c  test    eax, eax
0x180087f2e  jns     short loc_180087F4B
0x180087f30  mov     rcx, [rsp+28h]; this
0x180087f35  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087f3c  mov     r9d, eax; char *
0x180087f3f  mov     edx, 87h; void *
0x180087f44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180087f49  jmp     short loc_180087F0B
0x180087f4b  lea     rcx, [rsp+28h+TokenHandle]
0x180087f50  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180087f55  xor     ebx, ebx
0x180087f57  lea     rcx, [rsp+28h+arg_10]
0x180087f5c  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180087f61  mov     rsi, [rsp+28h+arg_18]
0x180087f66  mov     eax, ebx
0x180087f68  mov     rbx, [rsp+28h+arg_0]
0x180087f6d  add     rsp, 20h
0x180087f71  pop     rdi
0x180087f72  retn
```
