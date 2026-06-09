# CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)

- ea: `0x1800439dc`
- end: `0x180043b19`
- name: `?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z`
- size: `317`
- prototype: `int(CallerIdentity *__hidden this, HWND, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x1800788a4`

## callees

- `0x18000b5c0`
- `0x18000cbc0`
- `0x1800439dc`
- `0x180043f5c`
- `0x180044408`
- `0x1800995dc`
- `0x180099af0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043a30`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180043a30`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180043a03`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x180043a03`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180043a71`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x180043a71`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CallerIdentity::GetImmersiveAppIdFromWindow(CallerIdentity *this, HWND a2, unsigned __int16 **a3)
{
  const char *v5; // r9
  char *v7; // rax
  void *v8; // rsi
  unsigned int LastErrorFailHr; // ebx
  unsigned __int16 **v10; // r8
  const char *v11; // r9
  int WeakWindowAppId; // eax
  unsigned int v13; // edi
  int savedregs; // [rsp+20h] [rbp+0h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  DWORD dwProcessId; // [rsp+48h] [rbp+28h] BYREF
  char *v17; // [rsp+50h] [rbp+30h] BYREF
  __int64 v18; // [rsp+58h] [rbp+38h] BYREF

  *(_QWORD *)a2 = 0;
  dwProcessId = 0;
  if ( !GetWindowThreadProcessId((HWND)this, &dwProcessId) )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x6C,
             (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
             v5);
  v7 = (char *)OpenProcess(0x1000u, 0, dwProcessId);
  v8 = v7;
  v17 = v7;
  if ( ((unsigned __int64)(v7 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastErrorFailHr = wil::details::GetLastErrorFailHr((wil::details *)(v7 + 1));
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return LastErrorFailHr;
  }
  v18 = 0;
  if ( !(unsigned int)GetProcessUIContextInformation(v7, &v18) )
  {
    LastErrorFailHr = wil::details::in1diag3::Return_GetLastError(
                        retaddr,
                        (void *)0x72,
                        (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
                        v11);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return LastErrorFailHr;
  }
  if ( (_DWORD)v18 == 2
    && (WeakWindowAppId = CallerIdentity::GetWeakWindowAppId(this, a2, v10), v13 = WeakWindowAppId, WeakWindowAppId < 0) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecore\\shell\\lib\\calleridentity\\calleridentity_window.cpp",
      (const char *)(unsigned int)WeakWindowAppId,
      savedregs);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return v13;
  }
  else
  {
    if ( !*(_QWORD *)a2 )
    {
      LastErrorFailHr = CallerIdentity::GetProcessAppId(v8, a2, v10);
      if ( (LastErrorFailHr & 0x80000000) != 0 )
      {
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
        return LastErrorFailHr;
      }
    }
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return 0;
  }
}

```

## disassembly

```asm
0x1800439dc  mov     [rsp-18h+arg_0], rbx
0x1800439e1  push    rbp
0x1800439e2  push    rsi
0x1800439e3  push    rdi; int
0x1800439e4  mov     rbp, rsp
0x1800439e7  sub     rsp, 20h
0x1800439eb  mov     rbx, rdx
0x1800439ee  mov     rdi, rcx
0x1800439f1  mov     qword ptr [rdx], 0
0x1800439f8  mov     [rbp+dwProcessId], 0
0x1800439ff  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x180043a03  call    cs:__imp_GetWindowThreadProcessId
0x180043a09  test    eax, eax
0x180043a0b  jnz     short loc_180043A25
0x180043a0d  mov     rcx, [rbp+18h]; this
0x180043a11  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180043a18  lea     edx, [rax+6Ch]; void *
0x180043a1b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043a20  jmp     loc_180043B0C
0x180043a25  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180043a29  xor     edx, edx; bInheritHandle
0x180043a2b  mov     ecx, 1000h; dwDesiredAccess
0x180043a30  call    cs:__imp_OpenProcess
0x180043a36  mov     rsi, rax
0x180043a39  mov     [rbp+arg_10], rax
0x180043a3d  lea     rcx, [rax+1]; this
0x180043a41  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180043a48  jnz     short loc_180043A62
0x180043a4a  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180043a4f  mov     ebx, eax
0x180043a51  lea     rcx, [rbp+arg_10]
0x180043a55  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043a5a  nop
0x180043a5b  mov     eax, ebx
0x180043a5d  jmp     loc_180043B0C
0x180043a62  mov     [rbp+arg_18], 0
0x180043a6a  lea     rdx, [rbp+arg_18]
0x180043a6e  mov     rcx, rsi
0x180043a71  call    cs:__imp_GetProcessUIContextInformation
0x180043a77  test    eax, eax
0x180043a79  jnz     short loc_180043A9C
0x180043a7b  mov     rcx, [rbp+18h]; this
0x180043a7f  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180043a86  lea     edx, [rax+72h]; void *
0x180043a89  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043a8e  mov     ebx, eax
0x180043a90  lea     rcx, [rbp+arg_10]
0x180043a94  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043a99  nop
0x180043a9a  jmp     short loc_180043A5B
0x180043a9c  cmp     dword ptr [rbp+arg_18], 2
0x180043aa0  jnz     short loc_180043ADA
0x180043aa2  mov     rdx, rbx; HWND
0x180043aa5  mov     rcx, rdi; this
0x180043aa8  call    ?GetWeakWindowAppId@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetWeakWindowAppId(HWND__ *,ushort * *)
0x180043aad  mov     edi, eax
0x180043aaf  test    eax, eax
0x180043ab1  jns     short loc_180043ADA
0x180043ab3  mov     rcx, [rbp+18h]; this
0x180043ab7  mov     r9d, eax; char *
0x180043aba  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180043ac1  mov     edx, 79h ; 'y'; void *
0x180043ac6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043acb  nop
0x180043acc  lea     rcx, [rbp+arg_10]
0x180043ad0  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043ad5  nop
0x180043ad6  mov     eax, edi
0x180043ad8  jmp     short loc_180043B0C
0x180043ada  cmp     qword ptr [rbx], 0
0x180043ade  jnz     short loc_180043B00
0x180043ae0  mov     rdx, rbx; void *
0x180043ae3  mov     rcx, rsi; ProcessHandle
0x180043ae6  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180043aeb  mov     ebx, eax
0x180043aed  test    eax, eax
0x180043aef  jns     short loc_180043B00
0x180043af1  lea     rcx, [rbp+arg_10]
0x180043af5  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043afa  nop
0x180043afb  jmp     loc_180043A5B
0x180043b00  lea     rcx, [rbp+arg_10]
0x180043b04  call    ??1?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180043b09  nop
0x180043b0a  xor     eax, eax
0x180043b0c  mov     rbx, [rsp+20h+arg_0]
0x180043b11  add     rsp, 20h
0x180043b15  pop     rdi
0x180043b16  pop     rsi
0x180043b17  pop     rbp
0x180043b18  retn
```
