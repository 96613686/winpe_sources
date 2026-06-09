# SuspendImpersonationScope::SuspendImpersonationScope(void)

- ea: `0x18006cd80`
- end: `0x18006cdf7`
- name: `??0SuspendImpersonationScope@@QEAA@XZ`
- size: `119`
- prototype: `SuspendImpersonationScope *__fastcall(SuspendImpersonationScope *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005914`
- `0x180008e70`
- `0x180072980`
- `0x18008ea14`

## callees

- `0x18006cd80`
- `0x18008a400`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006cdc8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18006cdc8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cda4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18006cda4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cdba`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18006cdba`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
SuspendImpersonationScope *__fastcall SuspendImpersonationScope::SuspendImpersonationScope(
        SuspendImpersonationScope *this)
{
  HANDLE CurrentThread; // rax
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  *((_QWORD *)this + 1) = 0;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 4u, 1, (PHANDLE)this + 1) && !SetThreadToken(0, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0xB7,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\inc\\RAIIHelpers.h",
      v3);
  return this;
}

```

## disassembly

```asm
0x18006cd80  mov     [rsp+arg_8], rbx
0x18006cd85  mov     [rsp+arg_0], rcx
0x18006cd8a  push    rdi
0x18006cd8b  sub     rsp, 20h
0x18006cd8f  mov     rdi, rcx
0x18006cd92  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x18006cd99  mov     [rcx], rax
0x18006cd9c  mov     qword ptr [rcx+8], 0
0x18006cda4  call    cs:__imp_GetCurrentThread
0x18006cdaa  lea     r9, [rdi+8]; TokenHandle
0x18006cdae  mov     edx, 4; DesiredAccess
0x18006cdb3  lea     r8d, [rdx-3]; OpenAsSelf
0x18006cdb7  mov     rcx, rax; ThreadHandle
0x18006cdba  call    cs:__imp_OpenThreadToken
0x18006cdc0  test    eax, eax
0x18006cdc2  jz      short loc_18006CDE9
0x18006cdc4  xor     edx, edx; Token
0x18006cdc6  xor     ecx, ecx; Thread
0x18006cdc8  call    cs:__imp_SetThreadToken
0x18006cdce  mov     rcx, [rsp+28h]; this
0x18006cdd3  test    eax, eax
0x18006cdd5  jnz     short loc_18006CDE9
0x18006cdd7  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\WinStore\\inc\\RAI"...
0x18006cdde  mov     edx, 0B7h; void *
0x18006cde3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18006cde9  mov     rax, rdi
0x18006cdec  mov     rbx, [rsp+28h+arg_8]
0x18006cdf1  add     rsp, 20h
0x18006cdf5  pop     rdi
0x18006cdf6  retn
```
