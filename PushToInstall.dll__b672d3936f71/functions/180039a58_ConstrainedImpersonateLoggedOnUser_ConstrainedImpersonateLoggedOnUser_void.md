# ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(void)

- ea: `0x180039a58`
- end: `0x180039ac3`
- name: `??1ConstrainedImpersonateLoggedOnUser@@QEAA@XZ`
- size: `107`
- prototype: `void __fastcall(ConstrainedImpersonateLoggedOnUser *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003ceb8`
- `0x180043ddc`
- `0x18004df50`
- `0x18004e100`

## callees

- `0x180011afc`
- `0x180039a58`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039aa4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180039aa4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180039a66`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180039a66`

## string_xrefs

- `0x180039ab1`: `OneCore\Internal\OneCore\Priv_Sdk\Inc\ConstrainedImpersonationUtil.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConstrainedImpersonateLoggedOnUser::~ConstrainedImpersonateLoggedOnUser(
        ConstrainedImpersonateLoggedOnUser *this)
{
  const char *v2; // r9
  __int64 v3; // rcx
  char *v4; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *(_BYTE *)this )
  {
    if ( !RevertToSelf() )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0x49,
        (unsigned int)"OneCore\\Internal\\OneCore\\Priv_Sdk\\Inc\\ConstrainedImpersonationUtil.h",
        v2);
    *(_BYTE *)this = 0;
  }
  v3 = *((_QWORD *)this + 2);
  if ( v3 )
  {
    *((_QWORD *)this + 2) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  }
  v4 = (char *)*((_QWORD *)this + 1);
  if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v4);
}

```

## disassembly

```asm
0x180039a58  push    rbx
0x180039a5a  sub     rsp, 20h
0x180039a5e  mov     rbx, rcx
0x180039a61  cmp     byte ptr [rcx], 0
0x180039a64  jz      short loc_180039A78
0x180039a66  call    cs:__imp_RevertToSelf
0x180039a6c  mov     rcx, [rsp+28h]; this
0x180039a71  test    eax, eax
0x180039a73  jz      short loc_180039AB1
0x180039a75  mov     byte ptr [rbx], 0
0x180039a78  mov     rcx, [rbx+10h]
0x180039a7c  test    rcx, rcx
0x180039a7f  jz      short loc_180039A96
0x180039a81  mov     qword ptr [rbx+10h], 0
0x180039a89  mov     rax, [rcx]
0x180039a8c  mov     rax, [rax+10h]
0x180039a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039a95  nop
0x180039a96  mov     rcx, [rbx+8]; hObject
0x180039a9a  lea     rax, [rcx-1]
0x180039a9e  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180039aa2  ja      short loc_180039AAB
0x180039aa4  call    cs:__imp_CloseHandle
0x180039aaa  nop
0x180039aab  add     rsp, 20h
0x180039aaf  pop     rbx
0x180039ab0  retn
0x180039ab1  lea     r8, aOnecoreInterna_0; "OneCore\\Internal\\OneCore\\Priv_Sdk\\I"...
0x180039ab8  mov     edx, 49h ; 'I'; void *
0x180039abd  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
