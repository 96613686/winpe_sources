# KERNEL_USER_CONTEXT::GetPrimaryToken(void)

- ea: `0x180003e90`
- end: `0x180003ecb`
- name: `?GetPrimaryToken@KERNEL_USER_CONTEXT@@UEAAPEAXXZ`
- size: `59`
- prototype: `void *__fastcall(KERNEL_USER_CONTEXT *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180003e90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003ebc`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x180003ebc`

## pseudocode

```c
void *__fastcall KERNEL_USER_CONTEXT::GetPrimaryToken(HANDLE *this)
{
  void **phNewToken; // rbx

  phNewToken = this + 4;
  if ( !this[4] )
    DuplicateTokenEx(this[3], 0, 0, SecurityImpersonation, TokenPrimary, phNewToken);
  return *phNewToken;
}

```

## disassembly

```asm
0x180003e90  push    rbx
0x180003e92  sub     rsp, 30h
0x180003e96  lea     rbx, [rcx+20h]
0x180003e9a  cmp     qword ptr [rbx], 0
0x180003e9e  jnz     short loc_180003EC2
0x180003ea0  mov     rcx, [rcx+18h]; hExistingToken
0x180003ea4  mov     r9d, 2; ImpersonationLevel
0x180003eaa  mov     [rsp+38h+phNewToken], rbx; phNewToken
0x180003eaf  xor     r8d, r8d; lpTokenAttributes
0x180003eb2  xor     edx, edx; dwDesiredAccess
0x180003eb4  mov     [rsp+38h+TokenType], 1; TokenType
0x180003ebc  call    cs:__imp_DuplicateTokenEx
0x180003ec2  mov     rax, [rbx]
0x180003ec5  add     rsp, 30h
0x180003ec9  pop     rbx
0x180003eca  retn
```
