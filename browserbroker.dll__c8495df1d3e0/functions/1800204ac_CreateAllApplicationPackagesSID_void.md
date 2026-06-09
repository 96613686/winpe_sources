# CreateAllApplicationPackagesSID(void * *)

- ea: `0x1800204ac`
- end: `0x180020525`
- name: `?CreateAllApplicationPackagesSID@@YAKPEAPEAX@Z`
- size: `121`
- prototype: `DWORD __fastcall(PSID *pSid)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800208fc`

## callees

- `0x180002ce0`
- `0x1800204ac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002050c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800204fe`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800204fe`

## pseudocode

```c
DWORD __fastcall CreateAllApplicationPackagesSID(PSID *pSid)
{
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  *pSid = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, pSid) )
    return 0;
  else
    return GetLastError();
}

```

## disassembly

```asm
0x1800204ac  push    rbx
0x1800204ae  sub     rsp, 70h
0x1800204b2  mov     rax, cs:__security_cookie
0x1800204b9  xor     rax, rsp
0x1800204bc  mov     [rsp+78h+var_10], rax
0x1800204c1  xor     ebx, ebx
0x1800204c3  mov     [rsp+78h+pSid], rcx; pSid
0x1800204c8  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x1800204cc  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x1800204d0  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x1800204d4  lea     r8d, [rbx+2]; nSubAuthority0
0x1800204d8  mov     [rcx], rbx
0x1800204db  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x1800204df  lea     r9d, [rbx+1]; nSubAuthority1
0x1800204e3  mov     dl, r8b; nSubAuthorityCount
0x1800204e6  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x1800204ea  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x1800204ef  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], ebx
0x1800204f3  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x1800204fa  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x1800204fe  call    cs:__imp_AllocateAndInitializeSid
0x180020504  test    eax, eax
0x180020506  jz      short loc_18002050C
0x180020508  xor     eax, eax
0x18002050a  jmp     short loc_180020512
0x18002050c  call    cs:__imp_GetLastError
0x180020512  mov     rcx, [rsp+78h+var_10]
0x180020517  xor     rcx, rsp; StackCookie
0x18002051a  call    __security_check_cookie
0x18002051f  add     rsp, 70h
0x180020523  pop     rbx
0x180020524  retn
```
