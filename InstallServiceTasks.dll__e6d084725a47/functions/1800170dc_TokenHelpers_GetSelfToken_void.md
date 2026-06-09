# TokenHelpers::GetSelfToken(void)

- ea: `0x1800170dc`
- end: `0x180017194`
- name: `?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ`
- size: `184`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017b80`
- `0x180018a10`
- `0x180027178`

## callees

- `0x1800170dc`
- `0x180019624`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001715d`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18001715d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017140`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180017140`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001717a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001717a`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180017104`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180017104`

## string_xrefs

- `0x18001710e`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x180017167`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall TokenHelpers::GetSelfToken(__int64 a1)
{
  const char *v2; // r9
  HANDLE CurrentThread; // rax
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( !ImpersonateSelf(SecurityImpersonation) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x46,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v2);
  *(_QWORD *)a1 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  CurrentThread = GetCurrentThread();
  if ( !OpenThreadToken(CurrentThread, 0x2000Eu, 1, (PHANDLE)(a1 + 8)) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x49,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v4);
  RevertToSelf();
  return a1;
}

```

## disassembly

```asm
0x1800170dc  mov     rax, rsp
0x1800170df  mov     [rax+18h], rbx
0x1800170e3  mov     [rax+20h], rsi
0x1800170e7  mov     [rax+8], rcx
0x1800170eb  push    rdi
0x1800170ec  sub     rsp, 30h
0x1800170f0  mov     rdi, rcx
0x1800170f3  mov     dword ptr [rax-18h], 0
0x1800170fa  mov     rbx, [rsp+38h]
0x1800170ff  mov     ecx, 2; ImpersonationLevel
0x180017104  call    cs:__imp_ImpersonateSelf
0x18001710a  test    eax, eax
0x18001710c  jnz     short loc_180017121
0x18001710e  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180017115  lea     edx, [rax+46h]; void *
0x180017118  mov     rcx, rbx; this
0x18001711b  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180017121  mov     [rsp+38h+arg_8], 1
0x180017126  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18001712d  mov     [rdi], rax
0x180017130  mov     qword ptr [rdi+8], 0
0x180017138  mov     [rsp+38h+var_18], 1
0x180017140  call    cs:__imp_GetCurrentThread
0x180017146  mov     rsi, [rsp+38h]
0x18001714b  lea     r9, [rdi+8]; TokenHandle
0x18001714f  mov     edx, 2000Eh; DesiredAccess
0x180017154  mov     r8d, 1; OpenAsSelf
0x18001715a  mov     rcx, rax; ThreadHandle
0x18001715d  call    cs:__imp_OpenThreadToken
0x180017163  test    eax, eax
0x180017165  jnz     short loc_18001717A
0x180017167  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x18001716e  lea     edx, [rax+49h]; void *
0x180017171  mov     rcx, rsi; this
0x180017174  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18001717a  call    cs:__imp_RevertToSelf
0x180017180  mov     rax, rdi
0x180017183  mov     rbx, [rsp+38h+arg_10]
0x180017188  mov     rsi, [rsp+38h+arg_18]
0x18001718d  add     rsp, 30h
0x180017191  pop     rdi
0x180017192  retn
```
