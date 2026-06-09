# ImpersonateContext::~ImpersonateContext(void)

- ea: `0x1800853a0`
- end: `0x18008540d`
- name: `??1ImpersonateContext@@QEAA@XZ`
- size: `109`
- prototype: `void __fastcall(ImpersonateContext *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180059460`
- `0x1800b19ae`

## callees

- `0x18000b7a4`
- `0x1800853a0`
- `0x18008a110`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800853b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800853b4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800853d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800853d5`

## pseudocode

```c
void __fastcall ImpersonateContext::~ImpersonateContext(ImpersonateContext *this)
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
        (void *)0x20F,
        (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
        v3);
  }
  else if ( !RevertToSelf() )
  {
    wil::details::in1diag3::_FailFast_GetLastError(
      retaddr,
      (void *)0x213,
      (unsigned int)"onecoreuap\\enduser\\winstore\\licensemanager\\inc\\util.h",
      v4);
  }
  *(_QWORD *)this = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(this);
}

```

## disassembly

```asm
0x1800853a0  push    rbx
0x1800853a2  sub     rsp, 20h
0x1800853a6  mov     rdx, [rcx+8]; Token
0x1800853aa  mov     rbx, rcx
0x1800853ad  test    rdx, rdx
0x1800853b0  jz      short loc_1800853D5
0x1800853b2  xor     ecx, ecx; Thread
0x1800853b4  call    cs:__imp_SetThreadToken
0x1800853ba  test    eax, eax
0x1800853bc  jnz     short loc_1800853F6
0x1800853be  mov     rcx, [rsp+28h]; this
0x1800853c3  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800853ca  mov     edx, 20Fh; void *
0x1800853cf  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800853d5  call    cs:__imp_RevertToSelf
0x1800853db  test    eax, eax
0x1800853dd  jnz     short loc_1800853F6
0x1800853df  mov     rcx, [rsp+28h]; this
0x1800853e4  lea     r8, aOnecoreuapEndu_11; "onecoreuap\\enduser\\winstore\\licensem"...
0x1800853eb  mov     edx, 213h; void *
0x1800853f0  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800853f6  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x1800853fd  mov     rcx, rbx
0x180085400  mov     [rbx], rax
0x180085403  add     rsp, 20h
0x180085407  pop     rbx
0x180085408  jmp     ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
```
