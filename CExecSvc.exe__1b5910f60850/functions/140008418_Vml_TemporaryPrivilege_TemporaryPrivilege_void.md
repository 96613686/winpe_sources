# Vml::TemporaryPrivilege::~TemporaryPrivilege(void)

- ea: `0x140008418`
- end: `0x140008478`
- name: `??1TemporaryPrivilege@Vml@@QEAA@XZ`
- size: `96`
- prototype: `void __fastcall(const struct _LUID *this, __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000c340`
- `0x140022986`

## callees

- `0x140008418`
- `0x1400093d4`
- `0x140009490`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140008441`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x140008441`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008451`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140008451`

## string_xrefs

- `0x140008466`: `onecore\vm\common\vml\VmSecurity.h`

## pseudocode

```c
void __fastcall Vml::TemporaryPrivilege::~TemporaryPrivilege(
        const struct _LUID *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  void *v5; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  try
  {
    if ( !this[2].LowPart )
      Vml::VmAccessToken::EnablePrivilege((Vml::VmAccessToken *)&this[1], this, 0);
    if ( LOBYTE(this[2].HighPart) )
      RevertToSelf();
    v5 = (void *)this[1];
    if ( v5 && !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1004,
        (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
        a4);
  }
  catch ( ... )
  {
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1E04,
      (unsigned int)"onecore\\vm\\common\\vml\\VmSecurity.h",
      a4);
  }
}

```

## disassembly

```asm
0x140008418  mov     [rsp+arg_0], rcx
0x14000841d  push    rbx
0x14000841e  sub     rsp, 20h
0x140008422  mov     rbx, rcx
0x140008425  cmp     dword ptr [rcx+10h], 0
0x140008429  jnz     short loc_14000843B
0x14000842b  add     rcx, 8; this
0x14000842f  xor     r8d, r8d; int
0x140008432  mov     rdx, rbx; struct _LUID *
0x140008435  call    ?EnablePrivilege@VmAccessToken@Vml@@QEAAHAEBU_LUID@@H@Z; Vml::VmAccessToken::EnablePrivilege(_LUID const &,int)
0x14000843a  nop
0x14000843b  cmp     byte ptr [rbx+14h], 0
0x14000843f  jz      short loc_140008448
0x140008441  call    cs:__imp_RevertToSelf
0x140008447  nop
0x140008448  mov     rcx, [rbx+8]; hObject
0x14000844c  test    rcx, rcx
0x14000844f  jz      short loc_14000845B
0x140008451  call    cs:__imp_CloseHandle
0x140008457  test    eax, eax
0x140008459  jz      short loc_140008461
0x14000845b  add     rsp, 20h
0x14000845f  pop     rbx
0x140008460  retn
0x140008461  mov     rcx, [rsp+28h]; this
0x140008466  lea     r8, aOnecoreVmCommo_2; "onecore\\vm\\common\\vml\\VmSecurity.h"
0x14000846d  mov     edx, 1004h; void *
0x140008472  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
