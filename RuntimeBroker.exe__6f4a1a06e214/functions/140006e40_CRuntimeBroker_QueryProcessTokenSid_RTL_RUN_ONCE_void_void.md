# CRuntimeBroker::QueryProcessTokenSid(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140006e40`
- end: `0x140006edd`
- name: `?QueryProcessTokenSid@CRuntimeBroker@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `157`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140006e40`
- `0x140008c80`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140006eb9`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x140006eb9`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140006ecb`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x140006ecb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140006e84`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140006e84`

## pseudocode

```c
BOOL __fastcall CRuntimeBroker::QueryProcessTokenSid(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  BOOL result; // eax
  BOOL v4; // ebx
  PSID v5; // rdi
  DWORD LengthSid; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 0;
  result = GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenUser, TokenInformation, 0x54u, ReturnLength);
  v4 = result;
  if ( result )
  {
    v5 = TokenInformation[0];
    LengthSid = GetLengthSid(TokenInformation[0]);
    CopySid(LengthSid, &CRuntimeBroker::s_rtbSelfSid, v5);
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x140006e40  push    rbx
0x140006e42  sub     rsp, 0B0h
0x140006e49  mov     rax, cs:__security_cookie
0x140006e50  xor     rax, rsp
0x140006e53  mov     [rsp+0B8h+var_18], rax
0x140006e5b  lea     rax, [rsp+0B8h+var_88]
0x140006e60  mov     [rsp+0B8h+var_88], 0
0x140006e68  mov     r9d, 54h ; 'T'; TokenInformationLength
0x140006e6e  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x140006e73  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x140006e78  mov     edx, 1; TokenInformationClass
0x140006e7d  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x140006e84  call    cs:__imp_GetTokenInformation
0x140006e8a  mov     ebx, eax
0x140006e8c  test    eax, eax
0x140006e8e  jnz     short loc_140006EA9
0x140006e90  mov     rcx, [rsp+0B8h+var_18]
0x140006e98  xor     rcx, rsp; StackCookie
0x140006e9b  call    __security_check_cookie
0x140006ea0  add     rsp, 0B0h
0x140006ea7  pop     rbx
0x140006ea8  retn
0x140006ea9  mov     [rsp+0B8h+arg_0], rdi
0x140006eb1  mov     rdi, [rsp+0B8h+TokenInformation]
0x140006eb6  mov     rcx, rdi; pSid
0x140006eb9  call    cs:__imp_GetLengthSid
0x140006ebf  mov     r8, rdi; pSourceSid
0x140006ec2  lea     rdx, ?s_rtbSelfSid@CRuntimeBroker@@2PAEA; pDestinationSid
0x140006ec9  mov     ecx, eax; nDestinationSidLength
0x140006ecb  call    cs:__imp_CopySid
0x140006ed1  mov     rdi, [rsp+0B8h+arg_0]
0x140006ed9  mov     eax, ebx
0x140006edb  jmp     short loc_140006E90
```
