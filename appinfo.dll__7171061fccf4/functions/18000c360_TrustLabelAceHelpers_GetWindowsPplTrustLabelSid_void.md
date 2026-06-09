# TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(void * *)

- ea: `0x18000c360`
- end: `0x18000c3fd`
- name: `?GetWindowsPplTrustLabelSid@TrustLabelAceHelpers@@SAJPEAPEAX@Z`
- size: `157`
- prototype: `__int64 __fastcall(PSID *Sid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000c130`

## callees

- `0x18000c360`
- `0x180018190`
- `0x180046e50`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c3b4`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000c3b4`

## pseudocode

```c
__int64 __fastcall TrustLabelAceHelpers::GetWindowsPplTrustLabelSid(PSID *Sid)
{
  NTSTATUS v1; // eax
  ULONG SubAuthority2; // [rsp+20h] [rbp-58h]
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 4864;
  v1 = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x200u, 0x1000u, 0, 0, 0, 0, 0, 0, Sid);
  if ( v1 >= 0 )
    return 0;
  else
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)0x4B,
             (unsigned int)"onecore\\base\\appmodel\\trust\\trustlabelhelpersbase.cpp",
             (const char *)(unsigned int)v1,
             SubAuthority2);
}

```

## disassembly

```asm
0x18000c360  sub     rsp, 78h
0x18000c364  mov     rax, cs:__security_cookie
0x18000c36b  xor     rax, rsp
0x18000c36e  mov     [rsp+78h+var_10], rax
0x18000c373  mov     [rsp+78h+Sid], rcx; Sid
0x18000c378  xor     eax, eax
0x18000c37a  mov     [rsp+78h+SubAuthority7], eax; SubAuthority7
0x18000c37e  lea     rcx, [rsp+78h+IdentifierAuthority]; IdentifierAuthority
0x18000c383  mov     [rsp+78h+SubAuthority6], eax; SubAuthority6
0x18000c387  mov     r9d, 1000h; SubAuthority1
0x18000c38d  mov     [rsp+78h+SubAuthority5], eax; SubAuthority5
0x18000c391  mov     r8d, 200h; SubAuthority0
0x18000c397  mov     [rsp+78h+SubAuthority4], eax; SubAuthority4
0x18000c39b  mov     dl, 2; SubAuthorityCount
0x18000c39d  mov     [rsp+78h+SubAuthority3], eax; SubAuthority3
0x18000c3a1  mov     [rsp+78h+SubAuthority2], eax; int
0x18000c3a5  mov     dword ptr [rsp+78h+IdentifierAuthority.Value], 0
0x18000c3ad  mov     word ptr [rsp+78h+IdentifierAuthority.Value+4], 1300h
0x18000c3b4  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000c3ba  test    eax, eax
0x18000c3bc  jns     short loc_18000C3E9
0x18000c3be  mov     rcx, [rsp+78h]; this
0x18000c3c3  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\trust\\trustla"...
0x18000c3ca  mov     r9d, eax; char *
0x18000c3cd  mov     edx, 4Bh ; 'K'; void *
0x18000c3d2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18000c3d7  mov     rcx, [rsp+78h+var_10]
0x18000c3dc  xor     rcx, rsp; StackCookie
0x18000c3df  call    __security_check_cookie
0x18000c3e4  add     rsp, 78h
0x18000c3e8  retn
0x18000c3e9  xor     eax, eax
0x18000c3eb  mov     rcx, [rsp+78h+var_10]
0x18000c3f0  xor     rcx, rsp; StackCookie
0x18000c3f3  call    __security_check_cookie
0x18000c3f8  add     rsp, 78h
0x18000c3fc  retn
```
