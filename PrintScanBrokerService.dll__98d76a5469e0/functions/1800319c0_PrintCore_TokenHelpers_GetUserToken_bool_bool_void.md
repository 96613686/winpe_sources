# PrintCore::TokenHelpers::GetUserToken(bool,bool,void * *)

- ea: `0x1800319c0`
- end: `0x180031a95`
- name: `?GetUserToken@TokenHelpers@PrintCore@@SAJ_N0PEAPEAX@Z`
- size: `213`
- prototype: `static int(bool, bool, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800317bc`

## callees

- `0x18000ddac`
- `0x18001255c`
- `0x1800319c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a5d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031a5d`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031a53`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180031a53`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031a23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031a3a`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031a23`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180031a3a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800319fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800319fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a44`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031a44`

## string_xrefs

- `0x1800319e8`: `OneCoreUap\Internal\Printscan\inc\TokenHelpers.h`

## pseudocode

```c
__int64 __fastcall PrintCore::TokenHelpers::GetUserToken(__int64 a1, __int64 a2, void **a3)
{
  char *CurrentThread; // rbx
  unsigned int v6; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  void *v11; // [rsp+40h] [rbp+18h] BYREF

  if ( a3 )
  {
    CurrentThread = (char *)GetCurrentThread();
    v11 = CurrentThread;
    if ( (unsigned __int64)(CurrentThread - 1) > 0xFFFFFFFFFFFFFFFDuLL
      || (v6 = 0, !OpenThreadToken(CurrentThread, 8u, 0, a3))
      && !OpenThreadToken(CurrentThread, 8u, 1, a3)
      && (CurrentProcess = GetCurrentProcess(), !OpenProcessToken(CurrentProcess, 8u, a3)) )
    {
      LastError = GetLastError();
      v6 = LastError;
      if ( LastError > 0 )
        v6 = (unsigned __int16)LastError | 0x80070000;
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v11);
    return v6;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13,
      (unsigned int)"OneCoreUap\\Internal\\Printscan\\inc\\TokenHelpers.h",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x1800319c0  mov     [rsp+arg_0], rbx
0x1800319c5  mov     [rsp+arg_18], rsi
0x1800319ca  mov     byte ptr [rsp+arg_8], dl
0x1800319ce  push    rdi; int
0x1800319cf  sub     rsp, 20h
0x1800319d3  mov     rsi, r8
0x1800319d6  test    r8, r8
0x1800319d9  jnz     short loc_1800319FE
0x1800319db  mov     rcx, [rsp+28h]; this
0x1800319e0  mov     ebx, 80004003h
0x1800319e5  mov     r9d, ebx; char *
0x1800319e8  lea     r8, aOnecoreuapInte_2; "OneCoreUap\\Internal\\Printscan\\inc\\T"...
0x1800319ef  lea     edx, [rsi+13h]; void *
0x1800319f2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800319f7  mov     eax, ebx
0x1800319f9  jmp     loc_180031A84
0x1800319fe  call    cs:__imp_GetCurrentThread
0x180031a04  mov     rbx, rax
0x180031a07  mov     [rsp+28h+arg_10], rax
0x180031a0c  dec     rax
0x180031a0f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180031a13  ja      short loc_180031A5D
0x180031a15  xor     edi, edi
0x180031a17  mov     r9, rsi; TokenHandle
0x180031a1a  xor     r8d, r8d; OpenAsSelf
0x180031a1d  lea     edx, [rdi+8]; DesiredAccess
0x180031a20  mov     rcx, rbx; ThreadHandle
0x180031a23  call    cs:__imp_OpenThreadToken
0x180031a29  test    eax, eax
0x180031a2b  jnz     short loc_180031A72
0x180031a2d  mov     r9, rsi; TokenHandle
0x180031a30  lea     edx, [rdi+8]; DesiredAccess
0x180031a33  lea     r8d, [rdi+1]; OpenAsSelf
0x180031a37  mov     rcx, rbx; ThreadHandle
0x180031a3a  call    cs:__imp_OpenThreadToken
0x180031a40  test    eax, eax
0x180031a42  jnz     short loc_180031A72
0x180031a44  call    cs:__imp_GetCurrentProcess
0x180031a4a  mov     rcx, rax; ProcessHandle
0x180031a4d  mov     r8, rsi; TokenHandle
0x180031a50  lea     edx, [rdi+8]; DesiredAccess
0x180031a53  call    cs:__imp_OpenProcessToken
0x180031a59  test    eax, eax
0x180031a5b  jnz     short loc_180031A72
0x180031a5d  call    cs:__imp_GetLastError
0x180031a63  test    eax, eax
0x180031a65  mov     edi, eax
0x180031a67  jle     short loc_180031A72
0x180031a69  movzx   edi, ax
0x180031a6c  or      edi, 80070000h
0x180031a72  lea     rcx, [rsp+28h+arg_10]
0x180031a77  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180031a7c  mov     eax, edi
0x180031a7e  jmp     short loc_180031A84
0x180031a80  mov     eax, [rsp+28h+arg_8]
0x180031a84  mov     rbx, [rsp+28h+arg_0]
0x180031a89  mov     rsi, [rsp+28h+arg_18]
0x180031a8e  add     rsp, 20h
0x180031a92  pop     rdi
0x180031a93  retn
```
