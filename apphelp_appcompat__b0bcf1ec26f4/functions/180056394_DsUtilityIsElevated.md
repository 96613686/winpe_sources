# DsUtilityIsElevated

- ea: `0x180056394`
- end: `0x180056470`
- name: `DsUtilityIsElevated`
- size: `220`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180054650`
- `0x180055f54`

## callees

- `0x18000f114`
- `0x180056394`
- `0x180059270`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x1800563f5`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800563f5`
- `ntdll!RtlCheckTokenMembership` at `0x180056418`
- `ntdll!RtlCheckTokenMembership` at `0x180056418`
- `ntdll!RtlFreeSid` at `0x180056449`
- `ntdll!RtlFreeSid` at `0x180056449`

## string_xrefs

- `0x1800563ff`: `Failed to get admin sid`
- `0x180056422`: `Failed to check token membership`

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
0x180056394  mov     [rsp-8+arg_0], rbx
0x180056399  push    rbp
0x18005639a  mov     rbp, rsp
0x18005639d  sub     rsp, 80h
0x1800563a4  mov     rax, cs:__security_cookie
0x1800563ab  xor     rax, rsp
0x1800563ae  mov     [rbp+var_8], rax
0x1800563b2  xor     ebx, ebx
0x1800563b4  mov     word ptr [rbp+IdentifierAuthority.Value+4], 500h
0x1800563ba  lea     rax, [rbp+var_18]
0x1800563be  mov     dword ptr [rbp+IdentifierAuthority.Value], ebx
0x1800563c1  mov     [rsp+80h+Sid], rax; Sid
0x1800563c6  lea     rcx, [rbp+IdentifierAuthority]; IdentifierAuthority
0x1800563ca  mov     [rsp+80h+SubAuthority7], ebx; SubAuthority7
0x1800563ce  mov     r9d, 220h; SubAuthority1
0x1800563d4  mov     [rsp+80h+SubAuthority6], ebx; SubAuthority6
0x1800563d8  lea     r8d, [rbx+20h]; SubAuthority0
0x1800563dc  mov     [rsp+80h+SubAuthority5], ebx; SubAuthority5
0x1800563e0  mov     dl, 2; SubAuthorityCount
0x1800563e2  mov     [rsp+80h+SubAuthority4], ebx; SubAuthority4
0x1800563e6  mov     [rsp+80h+SubAuthority3], ebx; SubAuthority3
0x1800563ea  mov     [rsp+80h+SubAuthority2], ebx; SubAuthority2
0x1800563ee  mov     [rbp+var_18], rbx
0x1800563f2  mov     [rbp+var_20], bl
0x1800563f5  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800563fb  test    eax, eax
0x1800563fd  jns     short loc_18005640E
0x1800563ff  lea     r9, aFailedToGetAdm; "Failed to get admin sid"
0x180056406  mov     r8d, 24Ah
0x18005640c  jmp     short loc_18005642F
0x18005640e  mov     rdx, [rbp+var_18]
0x180056412  lea     r8, [rbp+var_20]
0x180056416  xor     ecx, ecx
0x180056418  call    cs:__imp_RtlCheckTokenMembership
0x18005641e  test    eax, eax
0x180056420  jns     short loc_180056440
0x180056422  lea     r9, aFailedToCheckT_0; "Failed to check token membership"
0x180056429  mov     r8d, 253h
0x18005642f  lea     rdx, aDsutilityisele; "DsUtilityIsElevated"
0x180056436  mov     ecx, 1
0x18005643b  call    AslLogCallPrintf
0x180056440  mov     rcx, [rbp+var_18]; Sid
0x180056444  test    rcx, rcx
0x180056447  jz      short loc_18005644F
0x180056449  call    cs:__imp_RtlFreeSid
0x18005644f  movzx   eax, [rbp+var_20]
0x180056453  mov     rcx, [rbp+var_8]
0x180056457  xor     rcx, rsp; StackCookie
0x18005645a  call    __security_check_cookie
0x18005645f  mov     rbx, [rsp+80h+arg_0]
0x180056467  add     rsp, 80h
0x18005646e  pop     rbp
0x18005646f  retn
```
