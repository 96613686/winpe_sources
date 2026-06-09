# wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(wistd::unique_ptr<_TOKEN_PRIVILEGES,wil::details::token_info_deleter> &,void *)

- ea: `0x140023470`
- end: `0x1400235c6`
- name: `??$get_token_information_nothrow@U_TOKEN_PRIVILEGES@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_PRIVILEGES@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `342`
- prototype: `__int64 __fastcall(void **, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x1400225c8`

## callees

- `0x140004c60`
- `0x140004c6c`
- `0x14001179c`
- `0x1400117bc`
- `0x140023470`
- `0x1400248f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400234da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400234da`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400234c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002354b`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1400234c6`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x14002354b`

## string_xrefs

- `0x140023511`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x140023560`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x1400235a4`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`

## pseudocode

```c
__int64 __fastcall wil::get_token_information_nothrow<_TOKEN_PRIVILEGES,0>(void **a1, __int64 a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  void *Block; // [rsp+48h] [rbp+10h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( !a2 )
    a2 = -6;
  if ( GetTokenInformation((HANDLE)a2, TokenPrivileges, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x117,
             (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
             v5);
  Block = operator new(TokenInformationLength, (const struct std::nothrow_t *)std::nothrow);
  v6 = Block;
  if ( Block )
  {
    if ( GetTokenInformation((HANDLE)a2, TokenPrivileges, Block, TokenInformationLength, &TokenInformationLength) )
    {
      utl::unique_ptr<SmsCheckpointRecord,tlx::generic_delete<SmsCheckpointRecord,tlx::operator_delete_deallocate>>::operator=(
        a1,
        &Block);
      if ( Block )
        operator delete(Block);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x11A,
                    (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
                    v8);
      operator delete(v6);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x119,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x140023470  mov     [rsp+arg_10], rbx
0x140023475  mov     [rsp+arg_18], rsi
0x14002347a  push    rdi
0x14002347b  sub     rsp, 30h
0x14002347f  mov     rdi, rcx
0x140023482  mov     rsi, rdx
0x140023485  mov     rcx, [rcx]; Block
0x140023488  mov     qword ptr [rdi], 0
0x14002348f  test    rcx, rcx
0x140023492  jz      short loc_140023499
0x140023494  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140023499  mov     rax, 0FFFFFFFFFFFFFFFAh
0x1400234a0  mov     [rsp+38h+TokenInformationLength], 0
0x1400234a8  test    rsi, rsi
0x1400234ab  cmovz   rsi, rax
0x1400234af  xor     r9d, r9d; TokenInformationLength
0x1400234b2  lea     rax, [rsp+38h+TokenInformationLength]
0x1400234b7  xor     r8d, r8d; TokenInformation
0x1400234ba  mov     rcx, rsi; TokenHandle
0x1400234bd  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x1400234c2  lea     edx, [r9+3]; TokenInformationClass
0x1400234c6  call    cs:__imp_GetTokenInformation
0x1400234cd  nop     dword ptr [rax+rax+00h]
0x1400234d2  test    eax, eax
0x1400234d4  jnz     loc_14002359F
0x1400234da  call    cs:__imp_GetLastError
0x1400234e1  nop     dword ptr [rax+rax+00h]
0x1400234e6  cmp     eax, 7Ah ; 'z'
0x1400234e9  jnz     loc_14002359F
0x1400234ef  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x1400234f3  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400234fa  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1400234ff  mov     [rsp+38h+Block], rax
0x140023504  mov     rbx, rax
0x140023507  test    rax, rax
0x14002350a  jnz     short loc_140023531
0x14002350c  mov     rcx, [rsp+38h]; this
0x140023511  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023518  mov     ebx, 8007000Eh
0x14002351d  mov     edx, 119h; void *
0x140023522  mov     r9d, ebx; char *
0x140023525  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14002352a  mov     eax, ebx
0x14002352c  jmp     loc_1400235B5
0x140023531  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x140023536  lea     rax, [rsp+38h+TokenInformationLength]
0x14002353b  mov     r8, rbx; TokenInformation
0x14002353e  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x140023543  mov     edx, 3; TokenInformationClass
0x140023548  mov     rcx, rsi; TokenHandle
0x14002354b  call    cs:__imp_GetTokenInformation
0x140023552  nop     dword ptr [rax+rax+00h]
0x140023557  test    eax, eax
0x140023559  jnz     short loc_14002357F
0x14002355b  mov     rcx, [rsp+38h]; this
0x140023560  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140023567  mov     edx, 11Ah; void *
0x14002356c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140023571  mov     rcx, rbx; Block
0x140023574  mov     edi, eax
0x140023576  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002357b  mov     eax, edi
0x14002357d  jmp     short loc_1400235B5
0x14002357f  lea     rdx, [rsp+38h+Block]
0x140023584  mov     rcx, rdi
0x140023587  call    ??4?$unique_ptr@USmsCheckpointRecord@@U?$generic_delete@USmsCheckpointRecord@@Uoperator_delete_deallocate@tlx@@@tlx@@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::unique_ptr<SmsCheckpointRecord,tlx::generic_delete<SmsCheckpointRecord,tlx::operator_delete_deallocate>>::operator=(utl::unique_ptr<SmsCheckpointRecord,tlx::generic_delete<SmsCheckpointRecord,tlx::operator_delete_deallocate>> &&)
0x14002358c  mov     rcx, [rsp+38h+Block]; Block
0x140023591  test    rcx, rcx
0x140023594  jz      short loc_14002359B
0x140023596  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002359b  xor     eax, eax
0x14002359d  jmp     short loc_1400235B5
0x14002359f  mov     rcx, [rsp+38h]; this
0x1400235a4  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1400235ab  mov     edx, 117h; void *
0x1400235b0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1400235b5  mov     rbx, [rsp+38h+arg_10]
0x1400235ba  mov     rsi, [rsp+38h+arg_18]
0x1400235bf  add     rsp, 30h
0x1400235c3  pop     rdi
0x1400235c4  retn
```
