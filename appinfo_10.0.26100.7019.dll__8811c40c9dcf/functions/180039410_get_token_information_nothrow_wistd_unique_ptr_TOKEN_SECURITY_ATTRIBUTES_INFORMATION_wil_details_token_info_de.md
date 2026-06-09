# get_token_information_nothrow(wistd::unique_ptr<_TOKEN_SECURITY_ATTRIBUTES_INFORMATION,wil::details::token_info_deleter> &,void *)

- ea: `0x180039410`
- end: `0x18003953e`
- name: `?get_token_information_nothrow@@YAJAEAV?$unique_ptr@U_TOKEN_SECURITY_ATTRIBUTES_INFORMATION@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18003420c`

## callees

- `0x180007c78`
- `0x180018150`
- `0x18001b0c4`
- `0x18001b8a4`
- `0x180039410`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800394cf`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180039452`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800394cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039466`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039466`

## string_xrefs

- `0x180039498`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x1800394e4`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`
- `0x18003951c`: `onecoreuap\ds\security\services\lua\appinfo\launch.cxx`

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
             (void *)0x1E9,
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
                    (void *)0x1ED,
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
      (void *)0x1EC,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\launch.cxx",
      (const char *)0x8007000ELL,
      ReturnLength);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180039410  mov     [rsp+arg_8], rbx
0x180039415  mov     [rsp+arg_10], rsi
0x18003941a  push    rdi
0x18003941b  sub     rsp, 30h
0x18003941f  mov     rdi, rcx
0x180039422  mov     rsi, rdx
0x180039425  mov     rcx, [rcx]; Block
0x180039428  and     qword ptr [rdi], 0
0x18003942c  test    rcx, rcx
0x18003942f  jz      short loc_180039436
0x180039431  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039436  and     [rsp+38h+TokenInformationLength], 0
0x18003943b  lea     rax, [rsp+38h+TokenInformationLength]
0x180039440  xor     r9d, r9d; TokenInformationLength
0x180039443  mov     qword ptr [rsp+38h+ReturnLength], rax; int
0x180039448  xor     r8d, r8d; TokenInformation
0x18003944b  mov     rcx, rsi; TokenHandle
0x18003944e  lea     edx, [r9+27h]; TokenInformationClass
0x180039452  call    cs:__imp_GetTokenInformation
0x180039459  nop     dword ptr [rax+rax+00h]
0x18003945e  test    eax, eax
0x180039460  jnz     loc_180039517
0x180039466  call    cs:__imp_GetLastError
0x18003946d  nop     dword ptr [rax+rax+00h]
0x180039472  cmp     eax, 7Ah ; 'z'
0x180039475  jnz     loc_180039517
0x18003947b  mov     ecx, [rsp+38h+TokenInformationLength]; unsigned __int64
0x18003947f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180039486  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18003948b  mov     rbx, rax
0x18003948e  test    rax, rax
0x180039491  jnz     short loc_1800394B5
0x180039493  mov     rcx, [rsp+38h]; this
0x180039498  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x18003949f  mov     ebx, 8007000Eh
0x1800394a4  mov     edx, 1ECh; void *
0x1800394a9  mov     r9d, ebx; char *
0x1800394ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800394b1  mov     eax, ebx
0x1800394b3  jmp     short loc_18003952D
0x1800394b5  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1800394ba  lea     rax, [rsp+38h+TokenInformationLength]
0x1800394bf  mov     r8, rbx; TokenInformation
0x1800394c2  mov     qword ptr [rsp+38h+ReturnLength], rax; ReturnLength
0x1800394c7  mov     edx, 27h ; '''; TokenInformationClass
0x1800394cc  mov     rcx, rsi; TokenHandle
0x1800394cf  call    cs:__imp_GetTokenInformation
0x1800394d6  nop     dword ptr [rax+rax+00h]
0x1800394db  test    eax, eax
0x1800394dd  jnz     short loc_180039503
0x1800394df  mov     rcx, [rsp+38h]; this
0x1800394e4  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x1800394eb  mov     edx, 1EDh; void *
0x1800394f0  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800394f5  mov     rcx, rbx; Block
0x1800394f8  mov     edi, eax
0x1800394fa  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800394ff  mov     eax, edi
0x180039501  jmp     short loc_18003952D
0x180039503  mov     rcx, [rdi]; Block
0x180039506  mov     [rdi], rbx
0x180039509  test    rcx, rcx
0x18003950c  jz      short loc_180039513
0x18003950e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180039513  xor     eax, eax
0x180039515  jmp     short loc_18003952D
0x180039517  mov     rcx, [rsp+38h]; this
0x18003951c  lea     r8, aOnecoreuapDsSe_0; "onecoreuap\\ds\\security\\services\\lua"...
0x180039523  mov     edx, 1E9h; void *
0x180039528  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003952d  mov     rbx, [rsp+38h+arg_8]
0x180039532  mov     rsi, [rsp+38h+arg_10]
0x180039537  add     rsp, 30h
0x18003953b  pop     rdi
0x18003953c  retn
```
