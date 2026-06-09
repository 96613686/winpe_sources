# AhcGetTrustedInstallerSid

- ea: `0x140027790`
- end: `0x1400278d5`
- name: `AhcGetTrustedInstallerSid`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140029020`

## callees

- `0x1400079f0`
- `0x140027790`
- `0x14003e364`
- `0x14005498c`

## import_xrefs

- `ntoskrnl!RtlLengthRequiredSid` at `0x1400277c0`
- `ntoskrnl!RtlLengthRequiredSid` at `0x1400277c0`
- `ntoskrnl!RtlInitializeSid` at `0x140027812`
- `ntoskrnl!RtlInitializeSid` at `0x140027812`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027823`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002783d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027857`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027871`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002788b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400278a5`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027823`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002783d`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027857`
- `ntoskrnl!RtlSubAuthoritySid` at `0x140027871`
- `ntoskrnl!RtlSubAuthoritySid` at `0x14002788b`
- `ntoskrnl!RtlSubAuthoritySid` at `0x1400278a5`

## string_xrefs

- `0x1400277e1`: `Failed to allocate memory for sid`
- `0x1400277ee`: `AhcGetTrustedInstallerSid`

## pseudocode

```c
__int64 __fastcall AhcGetTrustedInstallerSid(_QWORD *a1)
{
  ULONG v2; // eax
  __int64 v3; // rcx
  void *v4; // rax
  void *v5; // rbx
  __int64 result; // rax
  __int64 IdentifierAuthority; // [rsp+20h] [rbp-18h] BYREF

  LODWORD(IdentifierAuthority) = 0;
  WORD2(IdentifierAuthority) = 1280;
  v2 = RtlLengthRequiredSid(6u);
  v4 = (void *)AslAlloc(v3, v2, 1);
  v5 = v4;
  if ( v4 )
  {
    RtlInitializeSid(v4, (PSID_IDENTIFIER_AUTHORITY)&IdentifierAuthority, 6u);
    *RtlSubAuthoritySid(v5, 0) = 80;
    *RtlSubAuthoritySid(v5, 1u) = 956008885;
    *RtlSubAuthoritySid(v5, 2u) = -876444647;
    *RtlSubAuthoritySid(v5, 3u) = 1831038044;
    *RtlSubAuthoritySid(v5, 4u) = 1853292631;
    *RtlSubAuthoritySid(v5, 5u) = -2023488832;
    result = 0;
    *a1 = v5;
  }
  else
  {
    AslLogCallPrintf(1, "AhcGetTrustedInstallerSid", 427, "Failed to allocate memory for sid", IdentifierAuthority);
    return 3221225495LL;
  }
  return result;
}

```

## disassembly

```asm
0x140027790  mov     [rsp+arg_8], rbx
0x140027795  push    rdi
0x140027796  sub     rsp, 30h
0x14002779a  mov     rax, cs:__security_cookie
0x1400277a1  xor     rax, rsp
0x1400277a4  mov     [rsp+38h+var_10], rax
0x1400277a9  mov     rdi, rcx
0x1400277ac  mov     dword ptr [rsp+38h+IdentifierAuthority], 0
0x1400277b4  mov     ecx, 6; SubAuthorityCount
0x1400277b9  mov     word ptr [rsp+38h+IdentifierAuthority+4], 500h
0x1400277c0  call    cs:__imp_RtlLengthRequiredSid
0x1400277c7  nop     dword ptr [rax+rax+00h]
0x1400277cc  mov     edx, eax
0x1400277ce  mov     r8d, 1
0x1400277d4  call    AslAlloc
0x1400277d9  mov     rbx, rax
0x1400277dc  test    rax, rax
0x1400277df  jnz     short loc_140027807
0x1400277e1  lea     r9, aFailedToAlloca_22; "Failed to allocate memory for sid"
0x1400277e8  mov     r8d, 1ABh
0x1400277ee  lea     rdx, aAhcgettrustedi; "AhcGetTrustedInstallerSid"
0x1400277f5  lea     ecx, [rax+1]
0x1400277f8  call    AslLogCallPrintf
0x1400277fd  mov     eax, 0C0000017h
0x140027802  jmp     loc_1400278BC
0x140027807  mov     r8b, 6; SubAuthorityCount
0x14002780a  lea     rdx, [rsp+38h+IdentifierAuthority]; IdentifierAuthority
0x14002780f  mov     rcx, rbx; Sid
0x140027812  call    cs:__imp_RtlInitializeSid
0x140027819  nop     dword ptr [rax+rax+00h]
0x14002781e  xor     edx, edx; SubAuthority
0x140027820  mov     rcx, rbx; Sid
0x140027823  call    cs:__imp_RtlSubAuthoritySid
0x14002782a  nop     dword ptr [rax+rax+00h]
0x14002782f  mov     edx, 1; SubAuthority
0x140027834  mov     rcx, rbx; Sid
0x140027837  mov     dword ptr [rax], 50h ; 'P'
0x14002783d  call    cs:__imp_RtlSubAuthoritySid
0x140027844  nop     dword ptr [rax+rax+00h]
0x140027849  mov     edx, 2; SubAuthority
0x14002784e  mov     rcx, rbx; Sid
0x140027851  mov     dword ptr [rax], 38FB89B5h
0x140027857  call    cs:__imp_RtlSubAuthoritySid
0x14002785e  nop     dword ptr [rax+rax+00h]
0x140027863  mov     edx, 3; SubAuthority
0x140027868  mov     rcx, rbx; Sid
0x14002786b  mov     dword ptr [rax], 0CBC28419h
0x140027871  call    cs:__imp_RtlSubAuthoritySid
0x140027878  nop     dword ptr [rax+rax+00h]
0x14002787d  mov     edx, 4; SubAuthority
0x140027882  mov     rcx, rbx; Sid
0x140027885  mov     dword ptr [rax], 6D236C5Ch
0x14002788b  call    cs:__imp_RtlSubAuthoritySid
0x140027892  nop     dword ptr [rax+rax+00h]
0x140027897  mov     edx, 5; SubAuthority
0x14002789c  mov     rcx, rbx; Sid
0x14002789f  mov     dword ptr [rax], 6E770057h
0x1400278a5  call    cs:__imp_RtlSubAuthoritySid
0x1400278ac  nop     dword ptr [rax+rax+00h]
0x1400278b1  mov     dword ptr [rax], 876402C0h
0x1400278b7  xor     eax, eax
0x1400278b9  mov     [rdi], rbx
0x1400278bc  mov     rcx, [rsp+38h+var_10]
0x1400278c1  xor     rcx, rsp; StackCookie
0x1400278c4  call    __security_check_cookie
0x1400278c9  mov     rbx, [rsp+38h+arg_8]
0x1400278ce  add     rsp, 30h
0x1400278d2  pop     rdi
0x1400278d3  retn
```
