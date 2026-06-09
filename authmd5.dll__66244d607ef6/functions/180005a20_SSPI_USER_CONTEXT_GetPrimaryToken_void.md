# SSPI_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180005a20`
- end: `0x180005a5b`
- name: `?GetPrimaryToken@SSPI_USER_CONTEXT@@UEAAPEAXXZ`
- size: `59`
- prototype: `void *__fastcall(SSPI_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180005a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a4c`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180005a4c`

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
0x180005a20  push    rbx
0x180005a22  sub     rsp, 30h
0x180005a26  lea     rbx, [rcx+18h]
0x180005a2a  cmp     qword ptr [rbx], 0
0x180005a2e  jnz     short loc_180005A52
0x180005a30  mov     rcx, [rcx+10h]; hExistingToken
0x180005a34  mov     r9d, 2; ImpersonationLevel
0x180005a3a  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180005a3f  xor     r8d, r8d; lpTokenAttributes
0x180005a42  xor     edx, edx; dwDesiredAccess
0x180005a44  mov     [rsp+38h+TokenType], 1; TokenType
0x180005a4c  call    cs:__imp_DuplicateTokenEx
0x180005a52  mov     rax, [rbx]
0x180005a55  add     rsp, 30h
0x180005a59  pop     rbx
0x180005a5a  retn
```
