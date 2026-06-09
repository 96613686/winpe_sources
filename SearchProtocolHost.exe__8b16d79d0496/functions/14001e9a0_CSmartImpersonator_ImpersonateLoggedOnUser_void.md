# CSmartImpersonator::ImpersonateLoggedOnUser(void *)

- ea: `0x14001e9a0`
- end: `0x14001e9cd`
- name: `?ImpersonateLoggedOnUser@CSmartImpersonator@@QEAAXPEAX@Z`
- size: `45`
- prototype: `void(CSmartImpersonator *__hidden this, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002a090`
- `0x14002d394`

## callees

- `0x14001e9a0`
- `0x14003178c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001e9a7`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x14001e9a7`

## string_xrefs

- `0x14001e9b6`: `onecoreuap\base\appmodel\Search\common\include\smartcls_common.hxx`

## pseudocode

```c
void __fastcall CSmartImpersonator::ImpersonateLoggedOnUser(CSmartImpersonator *this, void *a2)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !ImpersonateLoggedOnUser(a2) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1DC,
      (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx",
      v2);
}

```

## disassembly

```asm
0x14001e9a0  sub     rsp, 28h
0x14001e9a4  mov     rcx, rdx; hToken
0x14001e9a7  call    cs:__imp_ImpersonateLoggedOnUser
0x14001e9ad  test    eax, eax
0x14001e9af  jnz     short loc_14001E9C8
0x14001e9b1  mov     rcx, [rsp+28h]; this
0x14001e9b6  lea     r8, aOnecoreuapBase_44; "onecoreuap\\base\\appmodel\\Search\\com"...
0x14001e9bd  mov     edx, 1DCh; void *
0x14001e9c2  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x14001e9c8  add     rsp, 28h
0x14001e9cc  retn
```
