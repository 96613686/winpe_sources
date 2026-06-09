# SSPI_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180007cf0`
- end: `0x180007d2b`
- name: `?GetPrimaryToken@SSPI_USER_CONTEXT@@UEAAPEAXXZ`
- size: `59`
- prototype: `void *__fastcall(SSPI_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007cf0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180007d1c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180007d1c`

## pseudocode

```c
void *__fastcall SSPI_USER_CONTEXT::GetPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx

  phNewToken = this + 3;
  if ( !this[3] )
    DuplicateTokenEx(this[2], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x180007cf0  push    rbx
0x180007cf2  sub     rsp, 30h
0x180007cf6  lea     rbx, [rcx+18h]
0x180007cfa  cmp     qword ptr [rbx], 0
0x180007cfe  jnz     short loc_180007D22
0x180007d00  mov     rcx, [rcx+10h]; hExistingToken
0x180007d04  mov     r9d, 2; ImpersonationLevel
0x180007d0a  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180007d0f  xor     r8d, r8d; lpTokenAttributes
0x180007d12  xor     edx, edx; dwDesiredAccess
0x180007d14  mov     [rsp+38h+TokenType], 1; TokenType
0x180007d1c  call    cs:__imp_DuplicateTokenEx
0x180007d22  mov     rax, [rbx]
0x180007d25  add     rsp, 30h
0x180007d29  pop     rbx
0x180007d2a  retn
```
