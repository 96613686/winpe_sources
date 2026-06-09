# PackageSid::PackageSidToPackageCapabilitySid(void * const,void * *)

- ea: `0x1801749bc`
- end: `0x180174b34`
- name: `?PackageSidToPackageCapabilitySid@PackageSid@@SAJQEAXPEAPEAX@Z`
- size: `376`
- prototype: `__int64 __fastcall(PSID pSid, PSID *Sid)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1800a0c14`
- `0x1800ed294`

## callees

- `0x1800aed10`
- `0x1801749bc`

## import_xrefs

- `ntdll!RtlValidSid` at `0x1801749f2`
- `ntdll!RtlValidSid` at `0x1801749f2`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180174af3`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180174af3`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180174a0f`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180174a0f`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a32`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a49`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a60`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a76`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a8c`
- `ADVAPI32!GetSidSubAuthority` at `0x180174aa2`
- `ADVAPI32!GetSidSubAuthority` at `0x180174ab8`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a32`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a49`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a60`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a76`
- `ADVAPI32!GetSidSubAuthority` at `0x180174a8c`
- `ADVAPI32!GetSidSubAuthority` at `0x180174aa2`
- `ADVAPI32!GetSidSubAuthority` at `0x180174ab8`

## pseudocode

```c
__int64 __fastcall PackageSid::PackageSidToPackageCapabilitySid(PSID pSid, PSID *Sid)
{
  __int64 result; // rax
  ULONG SubAuthority7; // r15d
  ULONG SubAuthority6; // r14d
  ULONG SubAuthority5; // ebp
  ULONG SubAuthority4; // esi
  ULONG SubAuthority3; // edi
  ULONG SubAuthority2; // ebx
  ULONG *SidSubAuthority; // rax
  NTSTATUS v12; // edx
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-48h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  if ( !RtlValidSid(pSid) )
    return 2147942487LL;
  if ( *GetSidSubAuthorityCount(pSid) != 8 )
    return 2147549183LL;
  SubAuthority7 = *GetSidSubAuthority(pSid, 7u);
  SubAuthority6 = *GetSidSubAuthority(pSid, 6u);
  SubAuthority5 = *GetSidSubAuthority(pSid, 5u);
  SubAuthority4 = *GetSidSubAuthority(pSid, 4u);
  SubAuthority3 = *GetSidSubAuthority(pSid, 3u);
  SubAuthority2 = *GetSidSubAuthority(pSid, 2u);
  SidSubAuthority = GetSidSubAuthority(pSid, 1u);
  v12 = RtlAllocateAndInitializeSid(
          &IdentifierAuthority,
          8u,
          3u,
          *SidSubAuthority,
          SubAuthority2,
          SubAuthority3,
          SubAuthority4,
          SubAuthority5,
          SubAuthority6,
          SubAuthority7,
          Sid);
  result = 0;
  if ( v12 < 0 )
    return v12 | 0x10000000u;
  return result;
}

```

## disassembly

```asm
0x1801749bc  mov     [rsp+arg_10], rbx
0x1801749c1  push    rbp
0x1801749c2  push    rsi
0x1801749c3  push    rdi
0x1801749c4  push    r12
0x1801749c6  push    r13
0x1801749c8  push    r14
0x1801749ca  push    r15
0x1801749cc  sub     rsp, 70h
0x1801749d0  mov     rax, cs:__security_cookie
0x1801749d7  xor     rax, rsp
0x1801749da  mov     [rsp+0A8h+var_40], rax
0x1801749df  xor     ebx, ebx
0x1801749e1  mov     word ptr [rsp+0A8h+IdentifierAuthority.Value+4], 0F00h
0x1801749e8  mov     dword ptr [rsp+0A8h+IdentifierAuthority.Value], ebx
0x1801749ec  mov     r13, rdx
0x1801749ef  mov     r12, rcx
0x1801749f2  call    cs:__imp_RtlValidSid
0x1801749f9  nop     dword ptr [rax+rax+00h]
0x1801749fe  test    al, al
0x180174a00  jnz     short loc_180174A0C
0x180174a02  mov     eax, 80070057h
0x180174a07  jmp     loc_180174B0E
0x180174a0c  mov     rcx, r12; pSid
0x180174a0f  call    cs:__imp_GetSidSubAuthorityCount
0x180174a16  nop     dword ptr [rax+rax+00h]
0x180174a1b  cmp     byte ptr [rax], 8
0x180174a1e  jz      short loc_180174A2A
0x180174a20  mov     eax, 8000FFFFh
0x180174a25  jmp     loc_180174B0E
0x180174a2a  mov     edx, 7; nSubAuthority
0x180174a2f  mov     rcx, r12; pSid
0x180174a32  call    cs:__imp_GetSidSubAuthority
0x180174a39  nop     dword ptr [rax+rax+00h]
0x180174a3e  mov     edx, 6; nSubAuthority
0x180174a43  mov     rcx, r12; pSid
0x180174a46  mov     r15d, [rax]
0x180174a49  call    cs:__imp_GetSidSubAuthority
0x180174a50  nop     dword ptr [rax+rax+00h]
0x180174a55  mov     edx, 5; nSubAuthority
0x180174a5a  mov     rcx, r12; pSid
0x180174a5d  mov     r14d, [rax]
0x180174a60  call    cs:__imp_GetSidSubAuthority
0x180174a67  nop     dword ptr [rax+rax+00h]
0x180174a6c  mov     edx, 4; nSubAuthority
0x180174a71  mov     rcx, r12; pSid
0x180174a74  mov     ebp, [rax]
0x180174a76  call    cs:__imp_GetSidSubAuthority
0x180174a7d  nop     dword ptr [rax+rax+00h]
0x180174a82  mov     edx, 3; nSubAuthority
0x180174a87  mov     rcx, r12; pSid
0x180174a8a  mov     esi, [rax]
0x180174a8c  call    cs:__imp_GetSidSubAuthority
0x180174a93  nop     dword ptr [rax+rax+00h]
0x180174a98  mov     edx, 2; nSubAuthority
0x180174a9d  mov     rcx, r12; pSid
0x180174aa0  mov     edi, [rax]
0x180174aa2  call    cs:__imp_GetSidSubAuthority
0x180174aa9  nop     dword ptr [rax+rax+00h]
0x180174aae  mov     edx, 1; nSubAuthority
0x180174ab3  mov     rcx, r12; pSid
0x180174ab6  mov     ebx, [rax]
0x180174ab8  call    cs:__imp_GetSidSubAuthority
0x180174abf  nop     dword ptr [rax+rax+00h]
0x180174ac4  mov     [rsp+0A8h+Sid], r13; Sid
0x180174ac9  lea     rcx, [rsp+0A8h+IdentifierAuthority]; IdentifierAuthority
0x180174ace  mov     [rsp+0A8h+SubAuthority7], r15d; SubAuthority7
0x180174ad3  mov     r8d, 3; SubAuthority0
0x180174ad9  mov     [rsp+0A8h+SubAuthority6], r14d; SubAuthority6
0x180174ade  mov     dl, 8; SubAuthorityCount
0x180174ae0  mov     r9d, [rax]; SubAuthority1
0x180174ae3  mov     [rsp+0A8h+SubAuthority5], ebp; SubAuthority5
0x180174ae7  mov     [rsp+0A8h+SubAuthority4], esi; SubAuthority4
0x180174aeb  mov     [rsp+0A8h+SubAuthority3], edi; SubAuthority3
0x180174aef  mov     [rsp+0A8h+SubAuthority2], ebx; SubAuthority2
0x180174af3  call    cs:__imp_RtlAllocateAndInitializeSid
0x180174afa  nop     dword ptr [rax+rax+00h]
0x180174aff  mov     ecx, eax
0x180174b01  mov     edx, eax
0x180174b03  bts     ecx, 1Ch
0x180174b07  xor     eax, eax
0x180174b09  test    edx, edx
0x180174b0b  cmovs   eax, ecx
0x180174b0e  mov     rcx, [rsp+0A8h+var_40]
0x180174b13  xor     rcx, rsp; StackCookie
0x180174b16  call    __security_check_cookie
0x180174b1b  mov     rbx, [rsp+0A8h+arg_10]
0x180174b23  add     rsp, 70h
0x180174b27  pop     r15
0x180174b29  pop     r14
0x180174b2b  pop     r13
0x180174b2d  pop     r12
0x180174b2f  pop     rdi
0x180174b30  pop     rsi
0x180174b31  pop     rbp
0x180174b32  retn
```
