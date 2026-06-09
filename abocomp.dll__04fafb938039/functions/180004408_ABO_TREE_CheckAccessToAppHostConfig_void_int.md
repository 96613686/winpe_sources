# ABO_TREE::CheckAccessToAppHostConfig(void *,int)

- ea: `0x180004408`
- end: `0x1800044d8`
- name: `?CheckAccessToAppHostConfig@ABO_TREE@@QEAAJPEAXH@Z`
- size: `208`
- prototype: `signed int __fastcall(ABO_TREE *this, void *, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18000b68c`

## callees

- `0x180003460`
- `0x180004408`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000449e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000449e`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180004494`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x180004494`

## pseudocode

```c
signed int __fastcall ABO_TREE::CheckAccessToAppHostConfig(ABO_TREE *this, void *a2, int a3)
{
  DWORD v3; // r8d
  signed int result; // eax
  void *v5; // rcx
  WINBOOL AccessStatus; // [rsp+40h] [rbp-128h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-124h] BYREF
  DWORD PrivilegeSetLength; // [rsp+48h] [rbp-120h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+50h] [rbp-118h] BYREF

  PrivilegeSetLength = 256;
  GrantedAccess = 0;
  AccessStatus = 0;
  v3 = a3 != 0 ? 1180063 : 1179785;
  if ( !a2 )
    return -2147024809;
  v5 = (void *)*((_QWORD *)this + 6);
  PrivilegeSet.PrivilegeCount = 0;
  if ( AccessCheck(v5, a2, v3, &g_gmFile, &PrivilegeSet, &PrivilegeSetLength, &GrantedAccess, &AccessStatus) )
  {
    result = 0;
    if ( !AccessStatus )
      return -2147024891;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180004408  sub     rsp, 168h
0x18000440f  mov     rax, cs:__security_cookie
0x180004416  xor     rax, rsp
0x180004419  mov     [rsp+168h+var_18], rax
0x180004421  neg     r8d
0x180004424  mov     [rsp+168h+var_120], 100h
0x18000442c  mov     [rsp+168h+var_124], 0
0x180004434  sbb     r8d, r8d
0x180004437  mov     [rsp+168h+var_128], 0
0x18000443f  and     r8d, 116h
0x180004446  add     r8d, 120089h; DesiredAccess
0x18000444d  test    rdx, rdx
0x180004450  jnz     short loc_180004459
0x180004452  mov     eax, 80070057h
0x180004457  jmp     short loc_1800044C0
0x180004459  mov     rcx, [rcx+30h]; pSecurityDescriptor
0x18000445d  lea     rax, [rsp+168h+var_128]
0x180004462  mov     [rsp+168h+AccessStatus], rax; AccessStatus
0x180004467  lea     r9, ?g_gmFile@@3U_GENERIC_MAPPING@@A; GenericMapping
0x18000446e  lea     rax, [rsp+168h+var_124]
0x180004473  mov     [rsp+168h+var_118.PrivilegeCount], 0
0x18000447b  mov     [rsp+168h+GrantedAccess], rax; GrantedAccess
0x180004480  lea     rax, [rsp+168h+var_120]
0x180004485  mov     [rsp+168h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000448a  lea     rax, [rsp+168h+var_118]
0x18000448f  mov     [rsp+168h+PrivilegeSet], rax; PrivilegeSet
0x180004494  call    cs:__imp_AccessCheck
0x18000449a  test    eax, eax
0x18000449c  jnz     short loc_1800044B2
0x18000449e  call    cs:__imp_GetLastError
0x1800044a4  test    eax, eax
0x1800044a6  jle     short loc_1800044C0
0x1800044a8  movzx   eax, ax
0x1800044ab  or      eax, 80070000h
0x1800044b0  jmp     short loc_1800044C0
0x1800044b2  xor     eax, eax
0x1800044b4  mov     ecx, 80070005h
0x1800044b9  cmp     [rsp+168h+var_128], eax
0x1800044bd  cmovz   eax, ecx
0x1800044c0  mov     rcx, [rsp+168h+var_18]
0x1800044c8  xor     rcx, rsp; StackCookie
0x1800044cb  call    __security_check_cookie
0x1800044d0  add     rsp, 168h
0x1800044d7  retn
```
