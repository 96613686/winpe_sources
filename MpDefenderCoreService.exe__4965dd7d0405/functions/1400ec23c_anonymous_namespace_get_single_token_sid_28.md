# _anonymous_namespace_::get_single_token_sid_28_

- ea: `0x1400ec23c`
- end: `0x1400ec34e`
- name: `_anonymous_namespace_::get_single_token_sid_28_`
- size: `274`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x1400ed580`

## callees

- `0x14003a130`
- `0x14003a5c0`
- `0x14003aa6c`
- `0x1400ec23c`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400ec28c`
- `KERNEL32!GetLastError` at `0x1400ec28c`
- `KERNEL32!SetLastError` at `0x1400ec321`
- `KERNEL32!SetLastError` at `0x1400ec321`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1400ec2f5`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1400ec2f5`
- `ADVAPI32!GetTokenInformation` at `0x1400ec27e`
- `ADVAPI32!GetTokenInformation` at `0x1400ec2cd`
- `ADVAPI32!GetTokenInformation` at `0x1400ec27e`
- `ADVAPI32!GetTokenInformation` at `0x1400ec2cd`

## pseudocode

```c
unsigned __int64 *__fastcall anonymous_namespace_::get_single_token_sid_28_(unsigned __int64 *a1, void *a2)
{
  _QWORD *v4; // rbx
  const struct std::nothrow_t *v5; // rdx
  void *v6; // rcx
  BOOL v7; // eax
  const struct std::nothrow_t *v8; // rdx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  LPSTR StringSid; // [rsp+38h] [rbp-20h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenLogonSid, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    goto LABEL_10;
  v4 = operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    SetLastError(0xEu);
    goto LABEL_10;
  }
  if ( !GetTokenInformation(a2, TokenLogonSid, v4, TokenInformationLength, &TokenInformationLength)
    || TokenInformationLength < 0x18
    || *(_DWORD *)v4 != 1 )
  {
    operator delete(v4, v5);
LABEL_10:
    *a1 = 0;
    return a1;
  }
  v6 = (void *)v4[1];
  StringSid = 0;
  v7 = ConvertSidToStringSidA(v6, &StringSid);
  *a1 = (unsigned __int64)StringSid & -(__int64)v7;
  operator delete(v4, v8);
  return a1;
}

```

## disassembly

```asm
0x1400ec23c  mov     r11, rsp
0x1400ec23f  mov     [r11+18h], rbx
0x1400ec243  mov     [r11+20h], rsi
0x1400ec247  push    rdi
0x1400ec248  sub     rsp, 50h
0x1400ec24c  mov     rax, cs:__security_cookie
0x1400ec253  xor     rax, rsp
0x1400ec256  mov     [rsp+58h+var_18], rax
0x1400ec25b  mov     rsi, rdx
0x1400ec25e  mov     [rsp+58h+TokenInformationLength], 0
0x1400ec266  xor     r9d, r9d; TokenInformationLength
0x1400ec269  lea     rax, [r11-28h]
0x1400ec26d  mov     rdi, rcx
0x1400ec270  mov     [r11-38h], rax
0x1400ec274  xor     r8d, r8d; TokenInformation
0x1400ec277  mov     rcx, rsi; TokenHandle
0x1400ec27a  lea     edx, [r9+1Ch]; TokenInformationClass
0x1400ec27e  call    cs:__imp_GetTokenInformation
0x1400ec284  test    eax, eax
0x1400ec286  jnz     loc_1400EC327
0x1400ec28c  call    cs:__imp_GetLastError
0x1400ec292  cmp     eax, 7Ah ; 'z'
0x1400ec295  jnz     loc_1400EC327
0x1400ec29b  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1400ec29f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400ec2a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400ec2ab  mov     rbx, rax
0x1400ec2ae  test    rax, rax
0x1400ec2b1  jz      short loc_1400EC31C
0x1400ec2b3  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1400ec2b8  lea     rax, [rsp+58h+TokenInformationLength]
0x1400ec2bd  mov     r8, rbx; TokenInformation
0x1400ec2c0  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400ec2c5  mov     edx, 1Ch; TokenInformationClass
0x1400ec2ca  mov     rcx, rsi; TokenHandle
0x1400ec2cd  call    cs:__imp_GetTokenInformation
0x1400ec2d3  test    eax, eax
0x1400ec2d5  jz      short loc_1400EC312
0x1400ec2d7  cmp     [rsp+58h+TokenInformationLength], 18h
0x1400ec2dc  jb      short loc_1400EC312
0x1400ec2de  cmp     dword ptr [rbx], 1
0x1400ec2e1  jnz     short loc_1400EC312
0x1400ec2e3  mov     rcx, [rbx+8]; Sid
0x1400ec2e7  lea     rdx, [rsp+58h+StringSid]; StringSid
0x1400ec2ec  mov     [rsp+58h+StringSid], 0
0x1400ec2f5  call    cs:__imp_ConvertSidToStringSidA
0x1400ec2fb  neg     eax
0x1400ec2fd  sbb     rcx, rcx
0x1400ec300  and     rcx, [rsp+58h+StringSid]
0x1400ec305  mov     [rdi], rcx
0x1400ec308  mov     rcx, rbx; void *
0x1400ec30b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400ec310  jmp     short loc_1400EC32E
0x1400ec312  mov     rcx, rbx; void *
0x1400ec315  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400ec31a  jmp     short loc_1400EC327
0x1400ec31c  mov     ecx, 0Eh; dwErrCode
0x1400ec321  call    cs:__imp_SetLastError
0x1400ec327  mov     qword ptr [rdi], 0
0x1400ec32e  mov     rax, rdi
0x1400ec331  mov     rcx, [rsp+58h+var_18]
0x1400ec336  xor     rcx, rsp; StackCookie
0x1400ec339  call    __security_check_cookie
0x1400ec33e  mov     rbx, [rsp+58h+arg_10]
0x1400ec343  mov     rsi, [rsp+58h+arg_18]
0x1400ec348  add     rsp, 50h
0x1400ec34c  pop     rdi
0x1400ec34d  retn
```
