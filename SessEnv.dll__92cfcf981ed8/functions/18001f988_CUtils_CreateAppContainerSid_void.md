# CUtils::CreateAppContainerSid(void * *)

- ea: `0x18001f988`
- end: `0x18001fa35`
- name: `?CreateAppContainerSid@CUtils@@SAJPEAPEAX@Z`
- size: `173`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020acc`

## callees

- `0x180003f30`
- `0x18001a280`
- `0x18001f988`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f9ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f9ec`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001f9e2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001f9e2`

## string_xrefs

- `0x18001fa05`: `CUtils::CreateAppContainerSid`
- `0x18001fa0f`: `AllocateAndInitializeSid failed: 0x%x in %s`

## pseudocode

```c
__int64 __fastcall CUtils::CreateAppContainerSid(void **a1)
{
  signed int v1; // ebx
  signed int LastError; // eax
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+60h] [rbp-18h] BYREF

  v1 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 3840;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 2u, 1u, 0, 0, 0, 0, 0, 0, &CUtils::pAppContainerSid) )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( v1 < 0 )
      _DbgPrintMessage(8, "AllocateAndInitializeSid failed: 0x%x in %s", v1, "CUtils::CreateAppContainerSid");
  }
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001f988  push    rbx
0x18001f98a  sub     rsp, 70h
0x18001f98e  mov     rax, cs:__security_cookie
0x18001f995  xor     rax, rsp
0x18001f998  mov     [rsp+78h+var_10], rax
0x18001f99d  xor     ebx, ebx
0x18001f99f  mov     dword ptr [rsp+78h+pIdentifierAuthority.Value], 0
0x18001f9a7  lea     rax, ?pAppContainerSid@CUtils@@0PEAXEA; void * CUtils::pAppContainerSid
0x18001f9ae  mov     word ptr [rsp+78h+pIdentifierAuthority.Value+4], 0F00h
0x18001f9b5  mov     [rsp+78h+pSid], rax; pSid
0x18001f9ba  lea     rcx, [rsp+78h+pIdentifierAuthority]; pIdentifierAuthority
0x18001f9bf  mov     [rsp+78h+nSubAuthority7], ebx; nSubAuthority7
0x18001f9c3  mov     [rsp+78h+nSubAuthority6], ebx; nSubAuthority6
0x18001f9c7  lea     r8d, [rbx+2]; nSubAuthority0
0x18001f9cb  mov     [rsp+78h+nSubAuthority5], ebx; nSubAuthority5
0x18001f9cf  lea     r9d, [rbx+1]; nSubAuthority1
0x18001f9d3  mov     [rsp+78h+nSubAuthority4], ebx; nSubAuthority4
0x18001f9d7  mov     dl, r8b; nSubAuthorityCount
0x18001f9da  mov     [rsp+78h+nSubAuthority3], ebx; nSubAuthority3
0x18001f9de  mov     [rsp+78h+nSubAuthority2], ebx; nSubAuthority2
0x18001f9e2  call    cs:__imp_AllocateAndInitializeSid
0x18001f9e8  test    eax, eax
0x18001f9ea  jnz     short loc_18001FA20
0x18001f9ec  call    cs:__imp_GetLastError
0x18001f9f2  mov     ebx, eax
0x18001f9f4  test    eax, eax
0x18001f9f6  jle     short loc_18001FA01
0x18001f9f8  movzx   ebx, ax
0x18001f9fb  or      ebx, 80070000h
0x18001fa01  test    ebx, ebx
0x18001fa03  jns     short loc_18001FA20
0x18001fa05  lea     r9, aCutilsCreateap_0; "CUtils::CreateAppContainerSid"
0x18001fa0c  mov     r8d, ebx
0x18001fa0f  lea     rdx, aAllocateandini; "AllocateAndInitializeSid failed: 0x%x i"...
0x18001fa16  mov     ecx, 8; int
0x18001fa1b  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x18001fa20  mov     eax, ebx
0x18001fa22  mov     rcx, [rsp+78h+var_10]
0x18001fa27  xor     rcx, rsp; StackCookie
0x18001fa2a  call    __security_check_cookie
0x18001fa2f  add     rsp, 70h
0x18001fa33  pop     rbx
0x18001fa34  retn
```
