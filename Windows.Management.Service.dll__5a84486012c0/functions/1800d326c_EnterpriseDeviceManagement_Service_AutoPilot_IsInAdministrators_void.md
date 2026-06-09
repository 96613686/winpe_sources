# EnterpriseDeviceManagement::Service::AutoPilot::IsInAdministrators(void)

- ea: `0x1800d326c`
- end: `0x1800d3315`
- name: `?IsInAdministrators@AutoPilot@Service@EnterpriseDeviceManagement@@YA_NXZ`
- size: `169`
- prototype: `bool __fastcall(EnterpriseDeviceManagement::Service::AutoPilot *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800d2d34`

## callees

- `0x18000b820`
- `0x1800d326c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800d32eb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800d32eb`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800d32cd`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800d32cd`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d32e1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x1800d32e1`

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
0x1800d326c  mov     [rsp-8+arg_0], rbx
0x1800d3271  push    rbp
0x1800d3272  mov     rbp, rsp
0x1800d3275  sub     rsp, 80h
0x1800d327c  mov     rax, cs:__security_cookie
0x1800d3283  xor     rax, rsp
0x1800d3286  mov     [rbp+var_8], rax
0x1800d328a  xor     ebx, ebx
0x1800d328c  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x1800d3292  lea     rax, [rbp+SidToCheck]
0x1800d3296  mov     [rbp+IsMember], ebx
0x1800d3299  mov     [rsp+80h+pSid], rax; pSid
0x1800d329e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x1800d32a2  mov     [rsp+80h+nSubAuthority7], ebx; nSubAuthority7
0x1800d32a6  mov     r9d, 220h; nSubAuthority1
0x1800d32ac  mov     [rsp+80h+nSubAuthority6], ebx; nSubAuthority6
0x1800d32b0  lea     r8d, [rbx+20h]; nSubAuthority0
0x1800d32b4  mov     [rsp+80h+nSubAuthority5], ebx; nSubAuthority5
0x1800d32b8  mov     dl, 2; nSubAuthorityCount
0x1800d32ba  mov     [rsp+80h+nSubAuthority4], ebx; nSubAuthority4
0x1800d32be  mov     [rsp+80h+nSubAuthority3], ebx; nSubAuthority3
0x1800d32c2  mov     [rsp+80h+nSubAuthority2], ebx; nSubAuthority2
0x1800d32c6  mov     dword ptr [rbp+pIdentifierAuthority.Value], ebx
0x1800d32c9  mov     [rbp+SidToCheck], rbx
0x1800d32cd  call    cs:__imp_AllocateAndInitializeSid
0x1800d32d3  test    eax, eax
0x1800d32d5  jz      short loc_1800D32F1
0x1800d32d7  mov     rdx, [rbp+SidToCheck]; SidToCheck
0x1800d32db  lea     r8, [rbp+IsMember]; IsMember
0x1800d32df  xor     ecx, ecx; TokenHandle
0x1800d32e1  call    cs:__imp_CheckTokenMembership
0x1800d32e7  mov     rcx, [rbp+SidToCheck]; pSid
0x1800d32eb  call    cs:__imp_FreeSid
0x1800d32f1  cmp     [rbp+IsMember], 1
0x1800d32f5  setz    al
0x1800d32f8  mov     rcx, [rbp+var_8]
0x1800d32fc  xor     rcx, rsp; StackCookie
0x1800d32ff  call    __security_check_cookie
0x1800d3304  mov     rbx, [rsp+80h+arg_0]
0x1800d330c  add     rsp, 80h
0x1800d3313  pop     rbp
0x1800d3314  retn
```
