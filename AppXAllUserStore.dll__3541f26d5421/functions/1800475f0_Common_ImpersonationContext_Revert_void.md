# Common::ImpersonationContext::Revert(void)

- ea: `0x1800475f0`
- end: `0x180047655`
- name: `?Revert@ImpersonationContext@Common@@QEAAXXZ`
- size: `101`
- prototype: `void __fastcall(Common::ImpersonationContext *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180045edc`
- `0x180049114`
- `0x18004a9a4`

## callees

- `0x1800466e4`
- `0x1800475f0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180047619`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004762f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18004762f`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180047602`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180047602`

## pseudocode

```c
void __fastcall Common::ImpersonationContext::Revert(Common::ImpersonationContext *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
  {
    if ( !ImpersonateLoggedOnUser(v2) )
    {
      Common::HandleInternalFailure(2);
      __debugbreak();
    }
    CloseHandle(*((HANDLE *)this + 1));
    *((_QWORD *)this + 1) = 0;
  }
  else if ( *((_DWORD *)this + 1) )
  {
    if ( !RevertToSelf() )
    {
      Common::HandleInternalFailure(2);
      __debugbreak();
    }
    *((_DWORD *)this + 1) = 0;
  }
  *(_DWORD *)this = 0;
}

```

## disassembly

```asm
0x1800475f0  push    rbx
0x1800475f2  sub     rsp, 20h
0x1800475f6  mov     rbx, rcx
0x1800475f9  mov     rcx, [rcx+8]; hToken
0x1800475fd  test    rcx, rcx
0x180047600  jz      short loc_180047629
0x180047602  call    cs:__imp_ImpersonateLoggedOnUser
0x180047608  test    eax, eax
0x18004760a  jnz     short loc_180047615
0x18004760c  lea     ecx, [rax+2]
0x18004760f  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180047614  int     3; Trap to Debugger
0x180047615  mov     rcx, [rbx+8]; hObject
0x180047619  call    cs:__imp_CloseHandle
0x18004761f  mov     qword ptr [rbx+8], 0
0x180047627  jmp     short loc_180047649
0x180047629  cmp     dword ptr [rbx+4], 0
0x18004762d  jz      short loc_180047649
0x18004762f  call    cs:__imp_RevertToSelf
0x180047635  test    eax, eax
0x180047637  jnz     short loc_180047642
0x180047639  lea     ecx, [rax+2]
0x18004763c  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180047641  int     3; Trap to Debugger
0x180047642  mov     dword ptr [rbx+4], 0
0x180047649  mov     dword ptr [rbx], 0
0x18004764f  add     rsp, 20h
0x180047653  pop     rbx
0x180047654  retn
```
