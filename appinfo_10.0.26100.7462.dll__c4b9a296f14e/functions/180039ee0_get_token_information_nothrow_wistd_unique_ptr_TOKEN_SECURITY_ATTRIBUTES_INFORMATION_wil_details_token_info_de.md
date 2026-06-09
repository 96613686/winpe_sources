# get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x180039ee0`
- end: `0x18003a00e`
- name: `?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003457c`

## callees

- `0x180007c78`
- `0x180018400`
- `0x18001b494`
- `0x18001bc74`
- `0x180039ee0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039f22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039f9f`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039f22`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039f9f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f36`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039f36`

## string_xrefs

- `0x180039f68`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039fb4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x180039fec`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1E8,
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
                    (void *)0x1EC,
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
      (void *)0x1EB,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180039ee0  mov     [rsp+arg_8], rbx
0x180039ee5  mov     [rsp+arg_10], rsi
0x180039eea  push    rdi
0x180039eeb  sub     rsp, 30h
0x180039eef  mov     rdi, rcx
0x180039ef2  mov     rsi, rdx
0x180039ef5  mov     rcx, [rcx]; Block
0x180039ef8  and     qword ptr [rdi], 0
0x180039efc  test    rcx, rcx
0x180039eff  jz      short loc_180039F06
0x180039f01  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039f06  and     [rsp+38h+TokenInformationLength], 0
0x180039f0b  lea     rax, [rsp+38h+TokenInformationLength]
0x180039f10  xor     r9d, r9d; TokenInformationLength
0x180039f13  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180039f18  xor     r8d, r8d; TokenInformation
0x180039f1b  mov     rcx, rsi; TokenHandle
0x180039f1e  lea     edx, [r9+27h]; TokenInformationClass
0x180039f22  call    cs:__imp_GetTokenInformation
0x180039f29  nop     dword ptr [rax+rax+00h]
0x180039f2e  test    eax, eax
0x180039f30  jnz     loc_180039FE7
0x180039f36  call    cs:__imp_GetLastError
0x180039f3d  nop     dword ptr [rax+rax+00h]
0x180039f42  cmp     eax, 7Ah ; 'z'
0x180039f45  jnz     loc_180039FE7
0x180039f4b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x180039f4f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039f56  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180039f5b  mov     rbx, rax
0x180039f5e  test    rax, rax
0x180039f61  jnz     short loc_180039F85
0x180039f63  mov     rcx, [rsp+38h]; this
0x180039f68  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039f6f  mov     ebx, 8007000Eh
0x180039f74  mov     edx, 1EBh; void *
0x180039f79  mov     r9d, ebx; char *
0x180039f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039f81  mov     eax, ebx
0x180039f83  jmp     short loc_180039FFD
0x180039f85  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x180039f8a  lea     rax, [rsp+38h+TokenInformationLength]
0x180039f8f  mov     r8, rbx; TokenInformation
0x180039f92  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x180039f97  mov     edx, 27h ; '''; TokenInformationClass
0x180039f9c  mov     rcx, rsi; TokenHandle
0x180039f9f  call    cs:__imp_GetTokenInformation
0x180039fa6  nop     dword ptr [rax+rax+00h]
0x180039fab  test    eax, eax
0x180039fad  jnz     short loc_180039FD3
0x180039faf  mov     rcx, [rsp+38h]; this
0x180039fb4  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039fbb  mov     edx, 1ECh; void *
0x180039fc0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039fc5  mov     rcx, rbx; Block
0x180039fc8  mov     edi, eax
0x180039fca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039fcf  mov     eax, edi
0x180039fd1  jmp     short loc_180039FFD
0x180039fd3  mov     rcx, [rdi]; Block
0x180039fd6  mov     [rdi], rbx
0x180039fd9  test    rcx, rcx
0x180039fdc  jz      short loc_180039FE3
0x180039fde  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039fe3  xor     eax, eax
0x180039fe5  jmp     short loc_180039FFD
0x180039fe7  mov     rcx, [rsp+38h]; this
0x180039fec  lea     r8, aOnecoreuapDsSe_1; "onecoreuap\\ds\\security\\services\\lua"...
0x180039ff3  mov     edx, 1E8h; void *
0x180039ff8  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180039ffd  mov     rbx, [rsp+38h+arg_8]
0x18003a002  mov     rsi, [rsp+38h+arg_10]
0x18003a007  add     rsp, 30h
0x18003a00b  pop     rdi
0x18003a00c  retn
```
