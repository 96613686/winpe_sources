# ATL::CAccessToken::GetUser(ATL::CSid *)

- ea: `0x14000d3bc`
- end: `0x14000d522`
- name: `?GetUser@CAccessToken@ATL@@QEBA_NPEAVCSid@2@@Z`
- size: `358`
- prototype: `bool __fastcall(ATL::CAccessToken *__hidden this, struct ATL::CSid *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14000a5a0`
- `0x14003a028`

## callees

- `0x140004280`
- `0x14000958c`
- `0x14000d3bc`
- `0x140013afc`
- `0x140065be0`

## import_xrefs

- `ADVAPI32!GetTokenInformation` at `0x14000d40f`
- `ADVAPI32!GetTokenInformation` at `0x14000d4c5`
- `ADVAPI32!GetTokenInformation` at `0x14000d40f`
- `ADVAPI32!GetTokenInformation` at `0x14000d4c5`
- `KERNEL32!GetLastError` at `0x14000d415`
- `KERNEL32!GetLastError` at `0x14000d415`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4fb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4a3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000d4fb`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000d471`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000d471`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
char __fastcall ATL::CAccessToken::GetUser(HANDLE *this, struct ATL::CSid *a2)
{
  char v4; // di
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rbx
  DWORD v7; // eax
  DWORD v8; // r9d
  unsigned __int64 v9; // rcx
  void *v10; // rsp
  void *v11; // rsp
  DWORD *p_TokenInformation; // rsi
  _QWORD *v13; // rax
  void *v14; // rcx
  void *v15; // rcx
  void *v16; // rcx
  DWORD TokenInformation; // [rsp+30h] [rbp+0h] BYREF
  _QWORD *v19; // [rsp+38h] [rbp+8h]

  if ( !a2 )
    return 0;
  TokenInformation = 0;
  v4 = 1;
  GetTokenInformation(this[1], TokenUser, 0, 0, &TokenInformation);
  if ( GetLastError() != 122 )
    return 0;
  v6 = 0;
  v19 = 0;
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
      v19 = v13;
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
  if ( !GetTokenInformation(this[1], TokenUser, p_TokenInformation, v8, &TokenInformation) )
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
  return v4;
}

```

## disassembly

```asm
0x14000d3bc  push    rbp
0x14000d3be  push    rbx
0x14000d3bf  push    rsi
0x14000d3c0  push    rdi
0x14000d3c1  push    r14
0x14000d3c3  push    r15
0x14000d3c5  sub     rsp, 58h
0x14000d3c9  lea     rbp, [rsp+30h]
0x14000d3ce  mov     rax, cs:__security_cookie
0x14000d3d5  xor     rax, rbp
0x14000d3d8  mov     [rbp+50h+var_40], rax
0x14000d3dc  mov     r14, rdx
0x14000d3df  mov     r15, rcx
0x14000d3e2  test    rdx, rdx
0x14000d3e5  jnz     short loc_14000D3EF
0x14000d3e7  xor     dil, dil
0x14000d3ea  jmp     loc_14000D506
0x14000d3ef  mov     [rbp+50h+TokenInformation], 0
0x14000d3f6  lea     rax, [rbp+50h+TokenInformation]
0x14000d3fa  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x14000d3ff  xor     r9d, r9d; TokenInformationLength
0x14000d402  xor     r8d, r8d; TokenInformation
0x14000d405  lea     edi, [r9+1]
0x14000d409  mov     edx, edi; TokenInformationClass
0x14000d40b  mov     rcx, [rcx+8]; TokenHandle
0x14000d40f  call    cs:__imp_GetTokenInformation
0x14000d415  call    cs:__imp_GetLastError
0x14000d41b  cmp     eax, 7Ah ; 'z'
0x14000d41e  jnz     short loc_14000D3E7
0x14000d420  xor     ebx, ebx
0x14000d422  mov     [rbp+50h+var_48], rbx
0x14000d426  mov     eax, [rbp+50h+TokenInformation]
0x14000d429  cmp     eax, 400h
0x14000d42e  ja      short loc_14000D46B
0x14000d430  mov     ecx, eax; this
0x14000d432  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x14000d437  test    al, al
0x14000d439  jz      short loc_14000D468
0x14000d43b  mov     r9d, [rbp+50h+TokenInformation]
0x14000d43f  lea     rcx, [r9+0Fh]
0x14000d443  cmp     rcx, r9
0x14000d446  ja      short loc_14000D452
0x14000d448  mov     rcx, 0FFFFFFFFFFFFFF0h
0x14000d452  and     rcx, 0FFFFFFFFFFFFFFF0h
0x14000d456  mov     rax, rcx
0x14000d459  call    _alloca_probe
0x14000d45e  sub     rsp, rcx
0x14000d461  lea     rsi, [rsp+80h+TokenInformation]
0x14000d466  jmp     short loc_14000D496
0x14000d468  mov     eax, [rbp+50h+TokenInformation]
0x14000d46b  mov     ecx, eax
0x14000d46d  add     rcx, 10h; Size
0x14000d471  call    cs:__imp_malloc
0x14000d477  test    rax, rax
0x14000d47a  jnz     short loc_14000D480
0x14000d47c  xor     esi, esi
0x14000d47e  jmp     short loc_14000D492
0x14000d480  mov     qword ptr [rax], 0
0x14000d487  mov     rbx, rax
0x14000d48a  mov     [rbp+50h+var_48], rax
0x14000d48e  lea     rsi, [rax+10h]
0x14000d492  mov     r9d, [rbp+50h+TokenInformation]; TokenInformationLength
0x14000d496  test    rsi, rsi
0x14000d499  jnz     short loc_14000D4B3
0x14000d49b  jmp     short loc_14000D4A9
0x14000d49d  mov     rcx, rbx; Block
0x14000d4a0  mov     rbx, [rbx]
0x14000d4a3  call    cs:__imp_free
0x14000d4a9  test    rbx, rbx
0x14000d4ac  jnz     short loc_14000D49D
0x14000d4ae  jmp     loc_14000D3E7
0x14000d4b3  lea     rax, [rbp+50h+TokenInformation]
0x14000d4b7  mov     [rsp+80h+ReturnLength], rax; ReturnLength
0x14000d4bc  mov     r8, rsi; TokenInformation
0x14000d4bf  mov     edx, edi; TokenInformationClass
0x14000d4c1  mov     rcx, [r15+8]; TokenHandle
0x14000d4c5  call    cs:__imp_GetTokenInformation
0x14000d4cb  test    eax, eax
0x14000d4cd  jnz     short loc_14000D4E7
0x14000d4cf  jmp     short loc_14000D4DD
0x14000d4d1  mov     rcx, rbx; Block
0x14000d4d4  mov     rbx, [rbx]
0x14000d4d7  call    cs:__imp_free
0x14000d4dd  test    rbx, rbx
0x14000d4e0  jnz     short loc_14000D4D1
0x14000d4e2  jmp     loc_14000D3E7
0x14000d4e7  mov     rdx, [rsi]
0x14000d4ea  mov     rcx, r14
0x14000d4ed  call    ??4CSid@ATL@@QEAAAEAV01@AEBU_SID@@@Z; ATL::CSid::operator=(_SID const &)
0x14000d4f2  nop
0x14000d4f3  jmp     short loc_14000D501
0x14000d4f5  mov     rcx, rbx; Block
0x14000d4f8  mov     rbx, [rbx]
0x14000d4fb  call    cs:__imp_free
0x14000d501  test    rbx, rbx
0x14000d504  jnz     short loc_14000D4F5
0x14000d506  mov     al, dil
0x14000d509  mov     rcx, [rbp+50h+var_40]
0x14000d50d  xor     rcx, rbp; StackCookie
0x14000d510  call    __security_check_cookie
0x14000d515  lea     rsp, [rbp+28h]
0x14000d519  pop     r15
0x14000d51b  pop     r14
0x14000d51d  pop     rdi
0x14000d51e  pop     rsi
0x14000d51f  pop     rbx
0x14000d520  pop     rbp
0x14000d521  retn
```
