# ATL::CAccessToken::GetPrimaryGroup(ATL::CSid *)

- ea: `0x14000cd94`
- end: `0x14000cef5`
- name: `?GetPrimaryGroup@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z`
- size: `353`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this, struct ATL::CSid *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000a5a0`

## callees

- `0x140004280`
- `0x14000958c`
- `0x14000cd94`
- `0x140013afc`
- `0x140065be0`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000cde2`
- `ADVAPI32!GetTokenInformation` at `0x14000ce9b`
- `ADVAPI32!GetTokenInformation` at `0x14000cde2`
- `ADVAPI32!GetTokenInformation` at `0x14000ce9b`
- `KERNEL32!GetLastError` at `0x14000cde8`
- `KERNEL32!GetLastError` at `0x14000cde8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ce76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cead`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ced1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ce76`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000cead`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000ced1`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000ce44`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000ce44`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CAccessToken::GetPrimaryGroup(HANDLE *this, struct ATL::CSid *a2)
{
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rbx
  DWORD v7; // eax
  DWORD v8; // r9d
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  DWORD *p_TokenInformation; // rdi
  _QWORD *v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  DWORD TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  _QWORD *v18; // [rsp+38h] [rbp+8h]

  if ( !a2 )
    return 0;
  TokenInformation = 0;
  GetTokenInformation(this[1], TokenPrimaryGroup, 0, 0, &TokenInformation);
  if ( GetLastError() != 122 )
    return 0;
  v6 = 0;
  v18 = 0;
  v7 = TokenInformation;
  if ( TokenInformation > 0x400 )
    goto LABEL_10;
  if ( !ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)TokenInformation, v5) )
  {
    v7 = TokenInformation;
LABEL_10:
    v13 = malloc(v7 + 16LL);
    if ( v13 )
    {
      *v13 = 0;
      v6 = v13;
      v18 = v13;
      p_TokenInformation = (DWORD *)(v13 + 2);
    }
    else
    {
      p_TokenInformation = 0;
    }
    v8 = TokenInformation;
    goto LABEL_14;
  }
  v8 = TokenInformation;
  v9 = TokenInformation + 15LL;
  if ( v9 <= TokenInformation )
    v9 = 0xFFFFFFFFFFFFFF0LL;
  v10 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  v11 = alloca(v9 & 0xFFFFFFFFFFFFFFF0uLL);
  p_TokenInformation = &TokenInformation;
LABEL_14:
  if ( !p_TokenInformation )
  {
    while ( v6 )
    {
      v14 = v6;
      v6 = (_QWORD *)*v6;
      free(v14);
    }
    return 0;
  }
  if ( !GetTokenInformation(this[1], TokenPrimaryGroup, p_TokenInformation, v8, &TokenInformation) )
  {
    while ( v6 )
    {
      v15 = v6;
      v6 = (_QWORD *)*v6;
      free(v15);
    }
    return 0;
  }
  ATL::CSid::operator=((__int64)a2, *(void **)p_TokenInformation);
  while ( v6 )
  {
    v16 = v6;
    v6 = (_QWORD *)*v6;
    free(v16);
  }
  return 1;
}

```

## disassembly

```asm
0x14000cd94  push    rbp
0x14000cd96  push    rbx
0x14000cd97  push    rsi
0x14000cd98  push    rdi
0x14000cd99  push    r14
0x14000cd9b  sub     rsp, 50h
0x14000cd9f  lea     rbp, [rsp+30h]
0x14000cda4  mov     rax, cs:__security_cookie
0x14000cdab  xor     rax, rbp
0x14000cdae  mov     [rbp+40h+var_30], rax
0x14000cdb2  mov     rsi, rdx
0x14000cdb5  mov     r14, rcx
0x14000cdb8  test    rdx, rdx
0x14000cdbb  jnz     short loc_14000CDC4
0x14000cdbd  xor     al, al
0x14000cdbf  jmp     loc_14000CEDE
0x14000cdc4  mov     [rbp+40h+TokenInformation], 0
0x14000cdcb  lea     rax, [rbp+40h+TokenInformation]
0x14000cdcf  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14000cdd4  xor     r9d, r9d; TokenInformationLength
0x14000cdd7  xor     r8d, r8d; TokenInformation
0x14000cdda  lea     edx, [r9+5]; TokenInformationClass
0x14000cdde  mov     rcx, [rcx+8]; TokenHandle
0x14000cde2  call    cs:__imp_GetTokenInformation
0x14000cde8  call    cs:__imp_GetLastError
0x14000cdee  cmp     eax, 7Ah ; 'z'
0x14000cdf1  jnz     short loc_14000CDBD
0x14000cdf3  xor     ebx, ebx
0x14000cdf5  mov     [rbp+40h+var_38], rbx
0x14000cdf9  mov     eax, [rbp+40h+TokenInformation]
0x14000cdfc  cmp     eax, 400h
0x14000ce01  ja      short loc_14000CE3E
0x14000ce03  mov     ecx, eax; this
0x14000ce05  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x14000ce0a  test    al, al
0x14000ce0c  jz      short loc_14000CE3B
0x14000ce0e  mov     r9d, [rbp+40h+TokenInformation]
0x14000ce12  lea     rcx, [r9+0Fh]
0x14000ce16  cmp     rcx, r9
0x14000ce19  ja      short loc_14000CE25
0x14000ce1b  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000ce25  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000ce29  mov     rax, rcx
0x14000ce2c  call    _alloca_probe
0x14000ce31  sub     rsp, rcx
0x14000ce34  lea     rdi, [rsp+70h+TokenInformation]
0x14000ce39  jmp     short loc_14000CE69
0x14000ce3b  mov     eax, [rbp+40h+TokenInformation]
0x14000ce3e  mov     ecx, eax
0x14000ce40  add     rcx, 10h; Size
0x14000ce44  call    cs:__imp_malloc
0x14000ce4a  test    rax, rax
0x14000ce4d  jnz     short loc_14000CE53
0x14000ce4f  xor     edi, edi
0x14000ce51  jmp     short loc_14000CE65
0x14000ce53  mov     qword ptr [rax], 0
0x14000ce5a  mov     rbx, rax
0x14000ce5d  mov     [rbp+40h+var_38], rax
0x14000ce61  lea     rdi, [rax+10h]
0x14000ce65  mov     r9d, [rbp+40h+TokenInformation]; TokenInformationLength
0x14000ce69  test    rdi, rdi
0x14000ce6c  jnz     short loc_14000CE86
0x14000ce6e  jmp     short loc_14000CE7C
0x14000ce70  mov     rcx, rbx; Block
0x14000ce73  mov     rbx, [rbx]
0x14000ce76  call    cs:__imp_free
0x14000ce7c  test    rbx, rbx
0x14000ce7f  jnz     short loc_14000CE70
0x14000ce81  jmp     loc_14000CDBD
0x14000ce86  lea     rax, [rbp+40h+TokenInformation]
0x14000ce8a  mov     [rsp+70h+ReturnLength], rax; ReturnLength
0x14000ce8f  mov     r8, rdi; TokenInformation
0x14000ce92  mov     edx, 5; TokenInformationClass
0x14000ce97  mov     rcx, [r14+8]; TokenHandle
0x14000ce9b  call    cs:__imp_GetTokenInformation
0x14000cea1  test    eax, eax
0x14000cea3  jnz     short loc_14000CEBD
0x14000cea5  jmp     short loc_14000CEB3
0x14000cea7  mov     rcx, rbx; Block
0x14000ceaa  mov     rbx, [rbx]
0x14000cead  call    cs:__imp_free
0x14000ceb3  test    rbx, rbx
0x14000ceb6  jnz     short loc_14000CEA7
0x14000ceb8  jmp     loc_14000CDBD
0x14000cebd  mov     rdx, [rdi]
0x14000cec0  mov     rcx, rsi
0x14000cec3  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x14000cec8  nop
0x14000cec9  jmp     short loc_14000CED7
0x14000cecb  mov     rcx, rbx; Block
0x14000cece  mov     rbx, [rbx]
0x14000ced1  call    cs:__imp_free
0x14000ced7  test    rbx, rbx
0x14000ceda  jnz     short loc_14000CECB
0x14000cedc  mov     al, 1
0x14000cede  mov     rcx, [rbp+40h+var_30]
0x14000cee2  xor     rcx, rbp; StackCookie
0x14000cee5  call    __security_check_cookie
0x14000ceea  lea     rsp, [rbp+20h]
0x14000ceee  pop     r14
0x14000cef0  pop     rdi
0x14000cef1  pop     rsi
0x14000cef2  pop     rbx
0x14000cef3  pop     rbp
0x14000cef4  retn
```
