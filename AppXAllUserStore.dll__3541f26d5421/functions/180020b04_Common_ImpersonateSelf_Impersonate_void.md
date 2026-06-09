# Common::ImpersonateSelf::Impersonate(void)

- ea: `0x180020b04`
- end: `0x180020bab`
- name: `?Impersonate@ImpersonateSelf@Common@@QEAAJXZ`
- size: `167`
- prototype: `int(Common::ImpersonateSelf *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020290`

## callees

- `0x180017f50`
- `0x180020b04`
- `0x180020c2c`
- `0x1800466e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b82`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020b82`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b75`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180020b75`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180020b63`
- `api-ms-win-security-base-l1-1-0!ImpersonateSelf` at `0x180020b63`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020b4b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020b4b`

## string_xrefs

- `0x180020b30`: `onecore\admin\appmodel\common\impersonateself.cpp`

## pseudocode

```c
int __fastcall Common::ImpersonateSelf::Impersonate(void **this)
{
  HANDLE *v1; // rbx
  signed int ThreadImpersonationToken; // eax
  signed int v4; // edi
  int result; // eax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = this + 1;
  ThreadImpersonationToken = Common::ImpersonationContext::GetThreadImpersonationToken(this + 1);
  v4 = ThreadImpersonationToken;
  if ( ThreadImpersonationToken >= 0 )
  {
    if ( *v1 && !RevertToSelf() )
    {
      Common::HandleInternalFailure(2);
      __debugbreak();
    }
    if ( ImpersonateSelf(SecurityImpersonation) )
    {
      *(_BYTE *)this = 1;
      return 0;
    }
    else
    {
      if ( *v1 )
      {
        CloseHandle(*v1);
        *v1 = 0;
      }
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2B,
      (int)"onecore\\admin\\appmodel\\common\\impersonateself.cpp",
      (const char *)(unsigned int)ThreadImpersonationToken);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180020b04  mov     [rsp+arg_0], rbx
0x180020b09  mov     [rsp+arg_8], rsi
0x180020b0e  push    rdi; int
0x180020b0f  sub     rsp, 20h
0x180020b13  lea     rbx, [rcx+8]
0x180020b17  mov     rsi, rcx
0x180020b1a  mov     rcx, rbx; TokenHandle
0x180020b1d  call    ?GetThreadImpersonationToken@ImpersonationContext@Common@@SAJPEAPEAX@Z; Common::ImpersonationContext::GetThreadImpersonationToken(void * *)
0x180020b22  mov     rcx, [rsp+28h]; this
0x180020b27  mov     edi, eax
0x180020b29  test    eax, eax
0x180020b2b  jns     short loc_180020B45
0x180020b2d  mov     r9d, eax; char *
0x180020b30  lea     r8, aOnecoreAdminAp_22; "onecore\\admin\\appmodel\\common\\imper"...
0x180020b37  mov     edx, 2Bh ; '+'; void *
0x180020b3c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180020b41  mov     eax, edi
0x180020b43  jmp     short loc_180020B9B
0x180020b45  cmp     qword ptr [rbx], 0
0x180020b49  jz      short loc_180020B5E
0x180020b4b  call    cs:__imp_RevertToSelf
0x180020b51  test    eax, eax
0x180020b53  jnz     short loc_180020B5E
0x180020b55  lea     ecx, [rax+2]
0x180020b58  call    ?HandleInternalFailure@Common@@YAXW4FATAL_FAILURE_REASON_TYPE@1@_KK@Z; Common::HandleInternalFailure(Common::FATAL_FAILURE_REASON_TYPE,unsigned __int64,ulong)
0x180020b5d  int     3; Trap to Debugger
0x180020b5e  mov     ecx, 2; ImpersonationLevel
0x180020b63  call    cs:__imp_ImpersonateSelf
0x180020b69  test    eax, eax
0x180020b6b  jnz     short loc_180020B96
0x180020b6d  mov     rcx, [rbx]; hObject
0x180020b70  test    rcx, rcx
0x180020b73  jz      short loc_180020B82
0x180020b75  call    cs:__imp_CloseHandle
0x180020b7b  mov     qword ptr [rbx], 0
0x180020b82  call    cs:__imp_GetLastError
0x180020b88  test    eax, eax
0x180020b8a  jle     short loc_180020B9B
0x180020b8c  movzx   eax, ax
0x180020b8f  or      eax, 80070000h
0x180020b94  jmp     short loc_180020B9B
0x180020b96  mov     byte ptr [rsi], 1
0x180020b99  xor     eax, eax
0x180020b9b  mov     rbx, [rsp+28h+arg_0]
0x180020ba0  mov     rsi, [rsp+28h+arg_8]
0x180020ba5  add     rsp, 20h
0x180020ba9  pop     rdi
0x180020baa  retn
```
