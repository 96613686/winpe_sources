# TokenHelpers::ImpersonateContext::~ImpersonateContext(void)

- ea: `0x18001584c`
- end: `0x1800158b5`
- name: `??1ImpersonateContext@TokenHelpers@@QEAA@XZ`
- size: `105`
- prototype: `void __fastcall(TokenHelpers::ImpersonateContext *__hidden this)`
- caller_count: `6`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180017b80`
- `0x18001913c`
- `0x180027178`
- `0x180034194`
- `0x180040de7`
- `0x180040ef3`

## callees

- `0x18000a5b4`
- `0x18001584c`
- `0x180015e78`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180015860`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x180015860`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001587f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001587f`

## string_xrefs

- `0x18001586f`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`
- `0x18001588e`: `onecoreuap\enduser\WinStore\ServicesCommon\inc\TokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall TokenHelpers::ImpersonateContext::~ImpersonateContext(TokenHelpers::ImpersonateContext *this)
{
  void *v1; // rdx
  const char *v3; // r9
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = (void *)*((_QWORD *)this + 1);
  if ( v1 )
  {
    if ( !SetThreadToken(0, v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x25,
        (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
        v3);
  }
  else if ( !RevertToSelf() )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x29,
      (unsigned int)"onecoreuap\\enduser\\WinStore\\ServicesCommon\\inc\\TokenHelpers.h",
      v4);
  }
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(this);
}

```

## disassembly

```asm
0x18001584c  push    rbx
0x18001584e  sub     rsp, 20h
0x180015852  mov     rdx, [rcx+8]; Token
0x180015856  mov     rbx, rcx
0x180015859  test    rdx, rdx
0x18001585c  jz      short loc_18001587F
0x18001585e  xor     ecx, ecx; Thread
0x180015860  call    cs:__imp_SetThreadToken
0x180015866  test    eax, eax
0x180015868  jnz     short loc_18001589E
0x18001586a  mov     rcx, [rsp+28h]; this
0x18001586f  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180015876  lea     edx, [rax+25h]; void *
0x180015879  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001587f  call    cs:__imp_RevertToSelf
0x180015885  test    eax, eax
0x180015887  jnz     short loc_18001589E
0x180015889  mov     rcx, [rsp+28h]; this
0x18001588e  lea     r8, aOnecoreuapEndu_15; "onecoreuap\\enduser\\WinStore\\Services"...
0x180015895  lea     edx, [rax+29h]; void *
0x180015898  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001589e  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800158a5  mov     rcx, rbx
0x1800158a8  mov     [rbx], rax
0x1800158ab  add     rsp, 20h
0x1800158af  pop     rbx
0x1800158b0  jmp     ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
```
