# CallerIdentity::GetImmersiveAppIdFromWindow(HWND__ *,ushort * *)

- ea: `0x180056044`
- end: `0x180056181`
- name: `?GetImmersiveAppIdFromWindow@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z`
- size: `317`
- prototype: `int(CallerIdentity *__hidden this, HWND, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002a7a0`

## callees

- `0x18000d158`
- `0x180010aec`
- `0x180010b0c`
- `0x1800166a8`
- `0x180055b7c`
- `0x180056044`
- `0x180056188`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180056098`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180056098`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18005606b`
- `ext-ms-win-ntuser-window-l1-1-0!GetWindowThreadProcessId` at `0x18005606b`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1800560d9`
- `ext-ms-win-ntuser-uicontext-ext-l1-1-0!__imp_GetProcessUIContextInformation` at `0x1800560d9`

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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
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
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return v13;
  }
  else
  {
    if ( !*(_QWORD *)a2 )
    {
      LastErrorFailHr = CallerIdentity::GetProcessAppId(v8, a2, v10);
      if ( (LastErrorFailHr & 0x80000000) != 0 )
      {
        wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
        return LastErrorFailHr;
      }
    }
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&v17);
    return 0;
  }
}

```

## disassembly

```asm
0x180056044  mov     [rsp-18h+arg_0], rbx
0x180056049  push    rbp
0x18005604a  push    rsi
0x18005604b  push    rdi; int
0x18005604c  mov     rbp, rsp
0x18005604f  sub     rsp, 20h
0x180056053  mov     rbx, rdx
0x180056056  mov     rdi, rcx
0x180056059  mov     qword ptr [rdx], 0
0x180056060  mov     [rbp+dwProcessId], 0
0x180056067  lea     rdx, [rbp+dwProcessId]; lpdwProcessId
0x18005606b  call    cs:__imp_GetWindowThreadProcessId
0x180056071  test    eax, eax
0x180056073  jnz     short loc_18005608D
0x180056075  mov     rcx, [rbp+18h]; this
0x180056079  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180056080  lea     edx, [rax+6Ch]; void *
0x180056083  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180056088  jmp     loc_180056174
0x18005608d  mov     r8d, [rbp+dwProcessId]; dwProcessId
0x180056091  xor     edx, edx; bInheritHandle
0x180056093  mov     ecx, 1000h; dwDesiredAccess
0x180056098  call    cs:__imp_OpenProcess
0x18005609e  mov     rsi, rax
0x1800560a1  mov     [rbp+arg_10], rax
0x1800560a5  lea     rcx, [rax+1]; this
0x1800560a9  test    rcx, 0FFFFFFFFFFFFFFFEh
0x1800560b0  jnz     short loc_1800560CA
0x1800560b2  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x1800560b7  mov     ebx, eax
0x1800560b9  lea     rcx, [rbp+arg_10]
0x1800560bd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800560c2  nop
0x1800560c3  mov     eax, ebx
0x1800560c5  jmp     loc_180056174
0x1800560ca  mov     [rbp+arg_18], 0
0x1800560d2  lea     rdx, [rbp+arg_18]
0x1800560d6  mov     rcx, rsi
0x1800560d9  call    cs:__imp_GetProcessUIContextInformation
0x1800560df  test    eax, eax
0x1800560e1  jnz     short loc_180056104
0x1800560e3  mov     rcx, [rbp+18h]; this
0x1800560e7  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x1800560ee  lea     edx, [rax+72h]; void *
0x1800560f1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800560f6  mov     ebx, eax
0x1800560f8  lea     rcx, [rbp+arg_10]
0x1800560fc  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056101  nop
0x180056102  jmp     short loc_1800560C3
0x180056104  cmp     dword ptr [rbp+arg_18], 2
0x180056108  jnz     short loc_180056142
0x18005610a  mov     rdx, rbx; HWND
0x18005610d  mov     rcx, rdi; this
0x180056110  call    ?GetWeakWindowAppId@CallerIdentity@@YAJPEAUHWND__@@PEAPEAG@Z; CallerIdentity::GetWeakWindowAppId(HWND__ *,ushort * *)
0x180056115  mov     edi, eax
0x180056117  test    eax, eax
0x180056119  jns     short loc_180056142
0x18005611b  mov     rcx, [rbp+18h]; this
0x18005611f  mov     r9d, eax; char *
0x180056122  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\calleridentity\\ca"...
0x180056129  mov     edx, 79h ; 'y'; void *
0x18005612e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180056133  nop
0x180056134  lea     rcx, [rbp+arg_10]
0x180056138  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18005613d  nop
0x18005613e  mov     eax, edi
0x180056140  jmp     short loc_180056174
0x180056142  cmp     qword ptr [rbx], 0
0x180056146  jnz     short loc_180056168
0x180056148  mov     rdx, rbx; void *
0x18005614b  mov     rcx, rsi; ProcessHandle
0x18005614e  call    ?GetProcessAppId@CallerIdentity@@YAJPEAXPEAPEAG@Z; CallerIdentity::GetProcessAppId(void *,ushort * *)
0x180056153  mov     ebx, eax
0x180056155  test    eax, eax
0x180056157  jns     short loc_180056168
0x180056159  lea     rcx, [rbp+arg_10]
0x18005615d  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056162  nop
0x180056163  jmp     loc_1800560C3
0x180056168  lea     rcx, [rbp+arg_10]
0x18005616c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180056171  nop
0x180056172  xor     eax, eax
0x180056174  mov     rbx, [rsp+20h+arg_0]
0x180056179  add     rsp, 20h
0x18005617d  pop     rdi
0x18005617e  pop     rsi
0x18005617f  pop     rbp
0x180056180  retn
```
