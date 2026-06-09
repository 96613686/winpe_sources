# AddUserToProcessObject(void *)

- ea: `0x180025ba8`
- end: `0x180025ce3`
- name: `?AddUserToProcessObject@@YAJPEAX@Z`
- size: `315`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `4`
- callee_count: `6`
- tags: `authz_impersonation, registry_config`

## callers

- `0x180022520`
- `0x180022744`
- `0x180022968`
- `0x180022b8c`

## callees

- `0x180006e8c`
- `0x180006eac`
- `0x18000c0ec`
- `0x180019e0c`
- `0x180025924`
- `0x180025ba8`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025c59`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180025c59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025bba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180025bba`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025bca`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180025bca`

## string_xrefs

- `0x180025be8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025c1f`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025c68`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025ca8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &TokenHandle,
        0);
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
0x180025ba8  mov     [rsp+arg_0], rbx
0x180025bad  mov     [rsp+arg_18], rsi
0x180025bb2  push    rdi; int
0x180025bb3  sub     rsp, 20h
0x180025bb7  mov     rsi, rcx
0x180025bba  call    cs:__imp_GetCurrentProcessId
0x180025bc0  mov     r8d, eax; dwProcessId
0x180025bc3  xor     edx, edx; bInheritHandle
0x180025bc5  mov     ecx, 60400h; dwDesiredAccess
0x180025bca  call    cs:__imp_OpenProcess
0x180025bd0  mov     rbx, rax
0x180025bd3  mov     [rsp+28h+arg_10], rax
0x180025bd8  inc     rax
0x180025bdb  test    rax, 0FFFFFFFFFFFFFFFEh
0x180025be1  jnz     short loc_180025C00
0x180025be3  mov     rcx, [rsp+28h]; this
0x180025be8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025bef  mov     edx, 80h; void *
0x180025bf4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025bf9  mov     ebx, eax
0x180025bfb  jmp     loc_180025CC7
0x180025c00  mov     r8d, 101400h; unsigned int
0x180025c06  mov     rdx, rsi; void *
0x180025c09  mov     rcx, rbx; Handle
0x180025c0c  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x180025c11  mov     edi, eax
0x180025c13  test    eax, eax
0x180025c15  jns     short loc_180025C37
0x180025c17  mov     rcx, [rsp+28h]; this
0x180025c1c  mov     r9d, eax; char *
0x180025c1f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025c26  mov     edx, 82h; void *
0x180025c2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025c30  mov     ebx, edi
0x180025c32  jmp     loc_180025CC7
0x180025c37  mov     [rsp+28h+TokenHandle], 0
0x180025c40  xor     edx, edx
0x180025c42  lea     rcx, [rsp+28h+TokenHandle]
0x180025c47  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180025c4c  lea     r8, [rsp+28h+TokenHandle]; TokenHandle
0x180025c51  mov     edx, 60008h; DesiredAccess
0x180025c56  mov     rcx, rbx; ProcessHandle
0x180025c59  call    cs:__imp_OpenProcessToken
0x180025c5f  test    eax, eax
0x180025c61  jnz     short loc_180025C87
0x180025c63  mov     rcx, [rsp+28h]; this
0x180025c68  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025c6f  mov     edx, 85h; void *
0x180025c74  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180025c79  mov     ebx, eax
0x180025c7b  lea     rcx, [rsp+28h+TokenHandle]
0x180025c80  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025c85  jmp     short loc_180025CC7
0x180025c87  mov     r8d, 0Eh; unsigned int
0x180025c8d  mov     rdx, rsi; void *
0x180025c90  mov     rcx, [rsp+28h+TokenHandle]; Handle
0x180025c95  call    ?AddUserToHandle@@YAJPEAX0K@Z; AddUserToHandle(void *,void *,ulong)
0x180025c9a  mov     ebx, eax
0x180025c9c  test    eax, eax
0x180025c9e  jns     short loc_180025CBB
0x180025ca0  mov     rcx, [rsp+28h]; this
0x180025ca5  mov     r9d, eax; char *
0x180025ca8  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025caf  mov     edx, 87h; void *
0x180025cb4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025cb9  jmp     short loc_180025C7B
0x180025cbb  lea     rcx, [rsp+28h+TokenHandle]
0x180025cc0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025cc5  xor     ebx, ebx
0x180025cc7  lea     rcx, [rsp+28h+arg_10]
0x180025ccc  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180025cd1  mov     eax, ebx
0x180025cd3  mov     rbx, [rsp+28h+arg_0]
0x180025cd8  mov     rsi, [rsp+28h+arg_18]
0x180025cdd  add     rsp, 20h
0x180025ce1  pop     rdi
0x180025ce2  retn
```
