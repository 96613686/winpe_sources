# CSmartImpersonator::RevertToPrevious(void)

- ea: `0x140028074`
- end: `0x1400280c7`
- name: `?RevertToPrevious@CSmartImpersonator@@QEAAXXZ`
- size: `83`
- prototype: `void __fastcall(CSmartImpersonator *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000f98c`
- `0x14002a090`
- `0x14002d394`

## callees

- `0x140028074`
- `0x14003178c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400280a1`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400280a1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140028080`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x140028080`

## string_xrefs

- `0x14002808f`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`
- `0x1400280b0`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`

## pseudocode

```c
void __fastcall CSmartImpersonator::RevertToPrevious(void **this)
{
  void *v1; // rcx
  const char *v2; // r9
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *this;
  if ( v1 )
  {
    if ( !ImpersonateLoggedOnUser(v1) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1EE,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
        v2);
  }
  else if ( !RevertToSelf() )
  {
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1F5,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
      v3);
  }
}

```

## disassembly

```asm
0x140028074  sub     rsp, 28h
0x140028078  mov     rcx, [rcx]; hToken
0x14002807b  test    rcx, rcx
0x14002807e  jz      short loc_1400280A1
0x140028080  call    cs:__imp_ImpersonateLoggedOnUser
0x140028086  test    eax, eax
0x140028088  jnz     short loc_1400280C2
0x14002808a  mov     rcx, [rsp+28h]; this
0x14002808f  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\appmodel\\Search\\com"...
0x140028096  mov     edx, 1EEh; void *
0x14002809b  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400280a1  call    cs:__imp_RevertToSelf
0x1400280a7  test    eax, eax
0x1400280a9  jnz     short loc_1400280C2
0x1400280ab  mov     rcx, [rsp+28h]; this
0x1400280b0  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1400280b7  mov     edx, 1F5h; void *
0x1400280bc  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400280c2  add     rsp, 28h
0x1400280c6  retn
```
