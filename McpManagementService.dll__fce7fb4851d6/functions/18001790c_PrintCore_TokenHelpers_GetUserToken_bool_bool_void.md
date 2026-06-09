# PrintCore::TokenHelpers::GetUserToken(bool,bool,void * *)

- ea: `0x18001790c`
- end: `0x1800179e1`
- name: `?GetUserToken@TokenHelpers@PrintCore@@SAJ_N0PEAPEAX@Z`
- size: `213`
- prototype: `__int64 __fastcall(__int64, __int64, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800176f4`

## callees

- `0x18000c4cc`
- `0x180012684`
- `0x18001790c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800179a9`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001796f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017986`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001796f`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180017986`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017990`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180017990`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001799f`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x18001799f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001794a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18001794a`

## string_xrefs

- `0x180017934`: `onecoreuap\internal\printscan\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall PrintCore::TokenHelpers::GetUserToken(__int64 a1, __int64 a2, void **a3)
{
  char *CurrentThread; // rbx
  unsigned int v6; // edi
  HANDLE CurrentProcess; // rax
  signed int LastError; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char *v11; // [rsp+40h] [rbp+18h] BYREF

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
      (unsigned int)"onecoreuap\\internal\\printscan\\inc\\TokenHelpers.h",
      (const char *)0x80004003LL,
      v9);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x18001790c  mov     [rsp+arg_0], rbx
0x180017911  mov     [rsp+arg_18], rsi
0x180017916  mov     byte ptr [rsp+arg_8], dl
0x18001791a  push    rdi; int
0x18001791b  sub     rsp, 20h
0x18001791f  mov     rsi, r8
0x180017922  test    r8, r8
0x180017925  jnz     short loc_18001794A
0x180017927  mov     rcx, [rsp+28h]; this
0x18001792c  mov     ebx, 80004003h
0x180017931  mov     r9d, ebx; char *
0x180017934  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\printscan\\inc\\T"...
0x18001793b  lea     edx, [rsi+13h]; void *
0x18001793e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180017943  mov     eax, ebx
0x180017945  jmp     loc_1800179D0
0x18001794a  call    cs:__imp_GetCurrentThread
0x180017950  mov     rbx, rax
0x180017953  mov     [rsp+28h+arg_10], rax
0x180017958  dec     rax
0x18001795b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001795f  ja      short loc_1800179A9
0x180017961  xor     edi, edi
0x180017963  mov     r9, rsi; TokenHandle
0x180017966  xor     r8d, r8d; OpenAsSelf
0x180017969  lea     edx, [rdi+8]; DesiredAccess
0x18001796c  mov     rcx, rbx; ThreadHandle
0x18001796f  call    cs:__imp_OpenThreadToken
0x180017975  test    eax, eax
0x180017977  jnz     short loc_1800179BE
0x180017979  mov     r9, rsi; TokenHandle
0x18001797c  lea     edx, [rdi+8]; DesiredAccess
0x18001797f  lea     r8d, [rdi+1]; OpenAsSelf
0x180017983  mov     rcx, rbx; ThreadHandle
0x180017986  call    cs:__imp_OpenThreadToken
0x18001798c  test    eax, eax
0x18001798e  jnz     short loc_1800179BE
0x180017990  call    cs:__imp_GetCurrentProcess
0x180017996  mov     rcx, rax; ProcessHandle
0x180017999  mov     r8, rsi; TokenHandle
0x18001799c  lea     edx, [rdi+8]; DesiredAccess
0x18001799f  call    cs:__imp_OpenProcessToken
0x1800179a5  test    eax, eax
0x1800179a7  jnz     short loc_1800179BE
0x1800179a9  call    cs:__imp_GetLastError
0x1800179af  test    eax, eax
0x1800179b1  mov     edi, eax
0x1800179b3  jle     short loc_1800179BE
0x1800179b5  movzx   edi, ax
0x1800179b8  or      edi, 80070000h
0x1800179be  lea     rcx, [rsp+28h+arg_10]
0x1800179c3  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800179c8  mov     eax, edi
0x1800179ca  jmp     short loc_1800179D0
0x1800179cc  mov     eax, [rsp+28h+arg_8]
0x1800179d0  mov     rbx, [rsp+28h+arg_0]
0x1800179d5  mov     rsi, [rsp+28h+arg_18]
0x1800179da  add     rsp, 20h
0x1800179de  pop     rdi
0x1800179df  retn
```
