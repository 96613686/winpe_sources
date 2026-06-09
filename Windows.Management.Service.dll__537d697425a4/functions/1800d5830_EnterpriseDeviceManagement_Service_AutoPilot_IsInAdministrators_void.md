# EnterpriseDeviceManagement::Service::AutoPilot::IsInAdministrators(void)

- ea: `0x1800d5830`
- end: `0x1800d58ec`
- name: `?IsInAdministrators@AutoPilot@Service@EnterpriseDeviceManagement@@YA_NXZ`
- size: `188`
- prototype: `bool __fastcall(EnterpriseDeviceManagement::Service::AutoPilot *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d52f4`

## callees

- `0x18000b8f0`
- `0x1800d5830`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800d58bb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800d58bb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800d5891`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800d5891`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d58ab`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d58ab`

## pseudocode

```c
bool __fastcall EnterpriseDeviceManagement::Service::AutoPilot::IsInAdministrators(
        EnterpriseDeviceManagement::Service::AutoPilot *this)
{
  WINBOOL IsMember; // [rsp+60h] [rbp-20h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp-18h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  IsMember = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
  }
  return IsMember == 1;
}

```

## disassembly

```asm
0x1800d5830  mov     [rsp-8+arg_0], rbx
0x1800d5835  push    rbp
0x1800d5836  mov     rbp, rsp
0x1800d5839  sub     rsp, 80h
0x1800d5840  mov     rax, cs:__security_cookie
0x1800d5847  xor     rax, rsp
0x1800d584a  mov     [rbp+var_8], rax
0x1800d584e  xor     ebx, ebx
0x1800d5850  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800d5856  lea     rax, [rbp+SidToCheck]
0x1800d585a  mov     [rbp+IsMember], ebx
0x1800d585d  mov     [rsp+80h+pSid], rax; pSid
0x1800d5862  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800d5866  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x1800d586a  mov     r9d, 220h; nSubAuthority1
0x1800d5870  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x1800d5874  lea     r8d, [rbx+20h]; nSubAuthority0
0x1800d5878  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x1800d587c  mov     dl, 2; nSubAuthorityCount
0x1800d587e  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x1800d5882  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x1800d5886  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x1800d588a  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x1800d588d  mov     [rbp+SidToCheck], rbx
0x1800d5891  call    cs:__imp_AllocateAndInitializeSid
0x1800d5898  nop     dword ptr [rax+rax+00h]
0x1800d589d  test    eax, eax
0x1800d589f  jz      short loc_1800D58C7
0x1800d58a1  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800d58a5  lea     r8, [rbp+IsMember]; IsMember
0x1800d58a9  xor     ecx, ecx; TokenHandle
0x1800d58ab  call    cs:__imp_CheckTokenMembership
0x1800d58b2  nop     dword ptr [rax+rax+00h]
0x1800d58b7  mov     rcx, [rbp+SidToCheck]; pSid
0x1800d58bb  call    cs:__imp_FreeSid
0x1800d58c2  nop     dword ptr [rax+rax+00h]
0x1800d58c7  cmp     [rbp+IsMember], 1
0x1800d58cb  setz    al
0x1800d58ce  mov     rcx, [rbp+var_8]
0x1800d58d2  xor     rcx, rsp; StackCookie
0x1800d58d5  call    __security_check_cookie
0x1800d58da  mov     rbx, [rsp+80h+arg_0]
0x1800d58e2  add     rsp, 80h
0x1800d58e9  pop     rbp
0x1800d58ea  retn
```
