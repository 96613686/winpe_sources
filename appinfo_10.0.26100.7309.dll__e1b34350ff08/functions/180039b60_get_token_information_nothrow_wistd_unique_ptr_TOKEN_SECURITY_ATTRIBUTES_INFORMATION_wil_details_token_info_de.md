# get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x180039b60`
- end: `0x180039c8e`
- name: `?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800342bc`

## callees

- `0x180007c78`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`
- `0x180039b60`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039ba2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039c1f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039ba2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039c1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bb6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039bb6`

## string_xrefs

- `0x180039be8`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039c34`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039c6c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

## pseudocode

```c
__int64 __fastcall get_token_information_nothrow(void **a1, void *a2)
{
  void *v4; // rcx
  const char *v5; // r9
  void *v6; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  void *v10; // rcx
  int ReturnLength; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF

  v4 = *a1;
  *a1 = 0;
  if ( v4 )
    operator delete(v4);
  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenSecurityAttributes, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x1E7,
             (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
             v5);
  v6 = operator new(TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( v6 )
  {
    if ( GetTokenInformation(a2, TokenSecurityAttributes, v6, TokenInformationLength, &TokenInformationLength) )
    {
      v10 = *a1;
      *a1 = v6;
      if ( v10 )
        operator delete(v10);
      return 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x1EB,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
                    v8);
      operator delete(v6);
      return LastError;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1EA,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180039b60  mov     [rsp+arg_8], rbx
0x180039b65  mov     [rsp+arg_10], rsi
0x180039b6a  push    rdi
0x180039b6b  sub     rsp, 30h
0x180039b6f  mov     rdi, rcx
0x180039b72  mov     rsi, rdx
0x180039b75  mov     rcx, [rcx]; Block
0x180039b78  and     qword ptr [rdi], 0
0x180039b7c  test    rcx, rcx
0x180039b7f  jz      short loc_180039B86
0x180039b81  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039b86  and     [rsp+38h+TokenInformationLength], 0
0x180039b8b  lea     rax, [rsp+38h+TokenInformationLength]
0x180039b90  xor     r9d, r9d; TokenInformationLength
0x180039b93  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180039b98  xor     r8d, r8d; TokenInformation
0x180039b9b  mov     rcx, rsi; TokenHandle
0x180039b9e  lea     edx, [r9+27h]; TokenInformationClass
0x180039ba2  call    cs:__imp_GetTokenInformation
0x180039ba9  nop     dword ptr [rax+rax+00h]
0x180039bae  test    eax, eax
0x180039bb0  jnz     loc_180039C67
0x180039bb6  call    cs:__imp_GetLastError
0x180039bbd  nop     dword ptr [rax+rax+00h]
0x180039bc2  cmp     eax, 7Ah ; 'z'
0x180039bc5  jnz     loc_180039C67
0x180039bcb  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180039bcf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039bd6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039bdb  mov     rbx, rax
0x180039bde  test    rax, rax
0x180039be1  jnz     short loc_180039C05
0x180039be3  mov     rcx, [rsp+38h]; this
0x180039be8  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039bef  mov     ebx, 8007000Eh
0x180039bf4  mov     edx, 1EAh; void *
0x180039bf9  mov     r9d, ebx; char *
0x180039bfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039c01  mov     eax, ebx
0x180039c03  jmp     short loc_180039C7D
0x180039c05  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180039c0a  lea     rax, [rsp+38h+TokenInformationLength]
0x180039c0f  mov     r8, rbx; TokenInformation
0x180039c12  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180039c17  mov     edx, 27h ; '''; TokenInformationClass
0x180039c1c  mov     rcx, rsi; TokenHandle
0x180039c1f  call    cs:__imp_GetTokenInformation
0x180039c26  nop     dword ptr [rax+rax+00h]
0x180039c2b  test    eax, eax
0x180039c2d  jnz     short loc_180039C53
0x180039c2f  mov     rcx, [rsp+38h]; this
0x180039c34  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039c3b  mov     edx, 1EBh; void *
0x180039c40  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039c45  mov     rcx, rbx; Block
0x180039c48  mov     edi, eax
0x180039c4a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039c4f  mov     eax, edi
0x180039c51  jmp     short loc_180039C7D
0x180039c53  mov     rcx, [rdi]; Block
0x180039c56  mov     [rdi], rbx
0x180039c59  test    rcx, rcx
0x180039c5c  jz      short loc_180039C63
0x180039c5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039c63  xor     eax, eax
0x180039c65  jmp     short loc_180039C7D
0x180039c67  mov     rcx, [rsp+38h]; this
0x180039c6c  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039c73  mov     edx, 1E7h; void *
0x180039c78  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039c7d  mov     rbx, [rsp+38h+arg_8]
0x180039c82  mov     rsi, [rsp+38h+arg_10]
0x180039c87  add     rsp, 30h
0x180039c8b  pop     rdi
0x180039c8c  retn
```
