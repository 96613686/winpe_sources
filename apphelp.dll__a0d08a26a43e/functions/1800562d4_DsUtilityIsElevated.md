# DsUtilityIsElevated

- ea: `0x1800562d4`
- end: `0x1800563b0`
- name: `DsUtilityIsElevated`
- size: `220`
- prototype: `__int64()`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180054650`
- `0x180055ec0`

## callees

- `0x18000f114`
- `0x1800562d4`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x180056335`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180056335`
- `ntdll!RtlCheckTokenMembership` at `0x180056358`
- `ntdll!RtlCheckTokenMembership` at `0x180056358`
- `ntdll!RtlFreeSid` at `0x180056389`
- `ntdll!RtlFreeSid` at `0x180056389`

## string_xrefs

- `0x18005633f`: `Failed to get admin sid`
- `0x180056362`: `Failed to check token membership`

## pseudocode

```c
__int64 DsUtilityIsElevated()
{
  _BYTE v1[8]; // [rsp+60h] [rbp-20h] BYREF
  PSID Sid; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  Sid = 0;
  v1[0] = 0;
  if ( RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &Sid) >= 0 )
  {
    if ( (int)RtlCheckTokenMembership(0, Sid, v1) < 0 )
      AslLogCallPrintf(1, "DsUtilityIsElevated", 595, "Failed to check token membership");
  }
  else
  {
    AslLogCallPrintf(1, "DsUtilityIsElevated", 586, "Failed to get admin sid");
  }
  if ( Sid )
    RtlFreeSid(Sid);
  return v1[0];
}

```

## disassembly

```asm
0x1800562d4  mov     [rsp-8+arg_0], rbx
0x1800562d9  push    rbp
0x1800562da  mov     rbp, rsp
0x1800562dd  sub     rsp, 80h
0x1800562e4  mov     rax, cs:__security_cookie
0x1800562eb  xor     rax, rsp
0x1800562ee  mov     [rbp+var_8], rax
0x1800562f2  xor     ebx, ebx
0x1800562f4  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1800562fa  lea     rax, [rbp+var_18]
0x1800562fe  mov     dword ptr [rbp+IdentifierAuthority.Value], ebx
0x180056301  mov     [rsp+80h+Sid], rax; Sid
0x180056306  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x18005630a  mov     [rsp+80h+SubAuthority7], ebx; SubAuthority7
0x18005630e  mov     r9d, 220h; SubAuthority1
0x180056314  mov     [rsp+80h+SubAuthority6], ebx; SubAuthority6
0x180056318  lea     r8d, [rbx+20h]; SubAuthority0
0x18005631c  mov     [rsp+80h+SubAuthority5], ebx; SubAuthority5
0x180056320  mov     dl, 2; SubAuthorityCount
0x180056322  mov     [rsp+80h+SubAuthority4], ebx; SubAuthority4
0x180056326  mov     [rsp+80h+SubAuthority3], ebx; SubAuthority3
0x18005632a  mov     [rsp+80h+SubAuthority2], ebx; SubAuthority2
0x18005632e  mov     [rbp+var_18], rbx
0x180056332  mov     [rbp+var_20], bl
0x180056335  call    cs:__imp_RtlAllocateAndInitializeSid
0x18005633b  test    eax, eax
0x18005633d  jns     short loc_18005634E
0x18005633f  lea     r9, aFailedToGetAdm; "Failed to get admin sid"
0x180056346  mov     r8d, 24Ah
0x18005634c  jmp     short loc_18005636F
0x18005634e  mov     rdx, [rbp+var_18]
0x180056352  lea     r8, [rbp+var_20]
0x180056356  xor     ecx, ecx
0x180056358  call    cs:__imp_RtlCheckTokenMembership
0x18005635e  test    eax, eax
0x180056360  jns     short loc_180056380
0x180056362  lea     r9, aFailedToCheckT_0; "Failed to check token membership"
0x180056369  mov     r8d, 253h
0x18005636f  lea     rdx, aDsutilityisele; "DsUtilityIsElevated"
0x180056376  mov     ecx, 1
0x18005637b  call    AslLogCallPrintf
0x180056380  mov     rcx, [rbp+var_18]; Sid
0x180056384  test    rcx, rcx
0x180056387  jz      short loc_18005638F
0x180056389  call    cs:__imp_RtlFreeSid
0x18005638f  movzx   eax, [rbp+var_20]
0x180056393  mov     rcx, [rbp+var_8]
0x180056397  xor     rcx, rsp; StackCookie
0x18005639a  call    __security_check_cookie
0x18005639f  mov     rbx, [rsp+80h+arg_0]
0x1800563a7  add     rsp, 80h
0x1800563ae  pop     rbp
0x1800563af  retn
```
