# _anonymous_namespace_::get_single_token_sid_4_

- ea: `0x1400ec130`
- end: `0x1400ec23c`
- name: `_anonymous_namespace_::get_single_token_sid_4_`
- size: `268`
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
- `0x1400ec130`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400ec180`
- `KERNEL32!GetLastError` at `0x1400ec180`
- `KERNEL32!SetLastError` at `0x1400ec20f`
- `KERNEL32!SetLastError` at `0x1400ec20f`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1400ec1e3`
- `ADVAPI32!ConvertSidToStringSidA` at `0x1400ec1e3`
- `ADVAPI32!GetTokenInformation` at `0x1400ec172`
- `ADVAPI32!GetTokenInformation` at `0x1400ec1c1`
- `ADVAPI32!GetTokenInformation` at `0x1400ec172`
- `ADVAPI32!GetTokenInformation` at `0x1400ec1c1`

## pseudocode

```c
unsigned __int64 *__fastcall anonymous_namespace_::get_single_token_sid_4_(unsigned __int64 *a1, void *a2)
{
  void **v4; // rbx
  const struct std::nothrow_t *v5; // rdx
  void *v6; // rcx
  BOOL v7; // eax
  const struct std::nothrow_t *v8; // rdx
  DWORD TokenInformationLength; // [rsp+30h] [rbp-28h] BYREF
  LPSTR StringSid; // [rsp+38h] [rbp-20h] BYREF

  TokenInformationLength = 0;
  if ( GetTokenInformation(a2, TokenOwner, 0, 0, &TokenInformationLength) || GetLastError() != 122 )
    goto LABEL_9;
  v4 = (void **)operator new[](TokenInformationLength, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v4 )
  {
    SetLastError(0xEu);
    goto LABEL_9;
  }
  if ( !GetTokenInformation(a2, TokenOwner, v4, TokenInformationLength, &TokenInformationLength)
    || TokenInformationLength < 8 )
  {
    operator delete(v4, v5);
LABEL_9:
    *a1 = 0;
    return a1;
  }
  v6 = *v4;
  StringSid = 0;
  v7 = ConvertSidToStringSidA(v6, &StringSid);
  *a1 = (unsigned __int64)StringSid & -(__int64)v7;
  operator delete(v4, v8);
  return a1;
}

```

## disassembly

```asm
0x1400ec130  mov     r11, rsp
0x1400ec133  mov     [r11+18h], rbx
0x1400ec137  mov     [r11+20h], rsi
0x1400ec13b  push    rdi
0x1400ec13c  sub     rsp, 50h
0x1400ec140  mov     rax, cs:__security_cookie
0x1400ec147  xor     rax, rsp
0x1400ec14a  mov     [rsp+58h+var_18], rax
0x1400ec14f  mov     rsi, rdx
0x1400ec152  mov     [rsp+58h+TokenInformationLength], 0
0x1400ec15a  xor     r9d, r9d; TokenInformationLength
0x1400ec15d  lea     rax, [r11-28h]
0x1400ec161  mov     rdi, rcx
0x1400ec164  mov     [r11-38h], rax
0x1400ec168  xor     r8d, r8d; TokenInformation
0x1400ec16b  mov     rcx, rsi; TokenHandle
0x1400ec16e  lea     edx, [r9+4]; TokenInformationClass
0x1400ec172  call    cs:__imp_GetTokenInformation
0x1400ec178  test    eax, eax
0x1400ec17a  jnz     loc_1400EC215
0x1400ec180  call    cs:__imp_GetLastError
0x1400ec186  cmp     eax, 7Ah ; 'z'
0x1400ec189  jnz     loc_1400EC215
0x1400ec18f  mov     ecx, [rsp+58h+TokenInformationLength]; unsigned __int64
0x1400ec193  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400ec19a  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400ec19f  mov     rbx, rax
0x1400ec1a2  test    rax, rax
0x1400ec1a5  jz      short loc_1400EC20A
0x1400ec1a7  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1400ec1ac  lea     rax, [rsp+58h+TokenInformationLength]
0x1400ec1b1  mov     r8, rbx; TokenInformation
0x1400ec1b4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1400ec1b9  mov     edx, 4; TokenInformationClass
0x1400ec1be  mov     rcx, rsi; TokenHandle
0x1400ec1c1  call    cs:__imp_GetTokenInformation
0x1400ec1c7  test    eax, eax
0x1400ec1c9  jz      short loc_1400EC200
0x1400ec1cb  cmp     [rsp+58h+TokenInformationLength], 8
0x1400ec1d0  jb      short loc_1400EC200
0x1400ec1d2  mov     rcx, [rbx]; Sid
0x1400ec1d5  lea     rdx, [rsp+58h+StringSid]; StringSid
0x1400ec1da  mov     [rsp+58h+StringSid], 0
0x1400ec1e3  call    cs:__imp_ConvertSidToStringSidA
0x1400ec1e9  neg     eax
0x1400ec1eb  sbb     rcx, rcx
0x1400ec1ee  and     rcx, [rsp+58h+StringSid]
0x1400ec1f3  mov     [rdi], rcx
0x1400ec1f6  mov     rcx, rbx; void *
0x1400ec1f9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400ec1fe  jmp     short loc_1400EC21C
0x1400ec200  mov     rcx, rbx; void *
0x1400ec203  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1400ec208  jmp     short loc_1400EC215
0x1400ec20a  mov     ecx, 0Eh; dwErrCode
0x1400ec20f  call    cs:__imp_SetLastError
0x1400ec215  mov     qword ptr [rdi], 0
0x1400ec21c  mov     rax, rdi
0x1400ec21f  mov     rcx, [rsp+58h+var_18]
0x1400ec224  xor     rcx, rsp; StackCookie
0x1400ec227  call    __security_check_cookie
0x1400ec22c  mov     rbx, [rsp+58h+arg_10]
0x1400ec231  mov     rsi, [rsp+58h+arg_18]
0x1400ec236  add     rsp, 50h
0x1400ec23a  pop     rdi
0x1400ec23b  retn
```
