# TakeOwnership(ushort const *)

- ea: `0x18001ab78`
- end: `0x18001acb1`
- name: `?TakeOwnership@@YAJPEBG@Z`
- size: `313`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001a6a8`

## callees

- `0x1800016d0`
- `0x18001ab78`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac24`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ac24`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ac88`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18001ac88`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ac1a`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18001ac1a`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001ac59`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x18001ac59`
- `ntdll!RtlAdjustPrivilege` at `0x18001abbd`
- `ntdll!RtlAdjustPrivilege` at `0x18001ac79`
- `ntdll!RtlAdjustPrivilege` at `0x18001abbd`
- `ntdll!RtlAdjustPrivilege` at `0x18001ac79`
- `ntdll!RtlNtStatusToDosError` at `0x18001abc9`
- `ntdll!RtlNtStatusToDosError` at `0x18001abc9`

## pseudocode

```c
__int64 __fastcall TakeOwnership(LPWSTR pObjectName)
{
  int v2; // eax
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  bool v6; // cc
  unsigned __int8 OldValue[8]; // [rsp+60h] [rbp-20h] BYREF
  PSID psidOwner; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  psidOwner = 0;
  OldValue[0] = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  v2 = RtlAdjustPrivilege(9u, 1u, 0, OldValue);
  if ( v2 < 0 )
  {
    v3 = RtlNtStatusToDosError(v2);
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    goto LABEL_12;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    LastError = GetLastError();
    v4 = LastError;
    v6 = LastError <= 0;
    goto LABEL_6;
  }
  LastError = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 1u, psidOwner, 0, 0, 0);
  v4 = LastError;
  v6 = LastError <= 0;
  if ( LastError )
  {
LABEL_6:
    if ( !v6 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_10;
  }
  v4 = 0;
LABEL_10:
  if ( !OldValue[0] )
    RtlAdjustPrivilege(9u, 0, 0, OldValue);
LABEL_12:
  if ( psidOwner )
    FreeSid(psidOwner);
  return v4;
}

```

## disassembly

```asm
0x18001ab78  mov     [rsp-8+arg_8], rbx
0x18001ab7d  mov     [rsp-8+arg_10], rdi
0x18001ab82  push    rbp
0x18001ab83  mov     rbp, rsp
0x18001ab86  sub     rsp, 80h
0x18001ab8d  mov     rax, cs:__security_cookie
0x18001ab94  xor     rax, rsp
0x18001ab97  mov     [rbp+var_8], rax
0x18001ab9b  xor     edi, edi
0x18001ab9d  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18001aba3  mov     rbx, rcx
0x18001aba6  mov     [rbp+psidOwner], rdi
0x18001abaa  lea     r9, [rbp+OldValue]; OldValue
0x18001abae  mov     [rbp+OldValue], dil
0x18001abb2  xor     r8d, r8d; ForThread
0x18001abb5  mov     dword ptr [rbp+pIdentifierAuthority.Value], edi
0x18001abb8  lea     ecx, [rdi+9]; Privilege
0x18001abbb  mov     dl, 1; NewValue
0x18001abbd  call    cs:__imp_RtlAdjustPrivilege
0x18001abc3  test    eax, eax
0x18001abc5  jns     short loc_18001ABE7
0x18001abc7  mov     ecx, eax; Status
0x18001abc9  call    cs:__imp_RtlNtStatusToDosError
0x18001abcf  mov     ebx, eax
0x18001abd1  test    eax, eax
0x18001abd3  jle     loc_18001AC7F
0x18001abd9  movzx   ebx, ax
0x18001abdc  or      ebx, 80070000h
0x18001abe2  jmp     loc_18001AC7F
0x18001abe7  lea     rax, [rbp+psidOwner]
0x18001abeb  mov     r9d, 220h; nSubAuthority1
0x18001abf1  mov     [rsp+80h+pSid], rax; pSid
0x18001abf6  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18001abfa  mov     [rsp+80h+nSubAuthority7], edi; nSubAuthority7
0x18001abfe  mov     r8d, 20h ; ' '; nSubAuthority0
0x18001ac04  mov     [rsp+80h+nSubAuthority6], edi; nSubAuthority6
0x18001ac08  mov     dl, 2; nSubAuthorityCount
0x18001ac0a  mov     [rsp+80h+nSubAuthority5], edi; nSubAuthority5
0x18001ac0e  mov     [rsp+80h+nSubAuthority4], edi; nSubAuthority4
0x18001ac12  mov     [rsp+80h+nSubAuthority3], edi; nSubAuthority3
0x18001ac16  mov     [rsp+80h+nSubAuthority2], edi; nSubAuthority2
0x18001ac1a  call    cs:__imp_AllocateAndInitializeSid
0x18001ac20  test    eax, eax
0x18001ac22  jnz     short loc_18001AC3B
0x18001ac24  call    cs:__imp_GetLastError
0x18001ac2a  mov     ebx, eax
0x18001ac2c  test    eax, eax
0x18001ac2e  jle     short loc_18001AC67
0x18001ac30  movzx   ebx, ax
0x18001ac33  or      ebx, 80070000h
0x18001ac39  jmp     short loc_18001AC67
0x18001ac3b  mov     r9, [rbp+psidOwner]; psidOwner
0x18001ac3f  mov     edx, 1; ObjectType
0x18001ac44  mov     qword ptr [rsp+80h+nSubAuthority4], rdi; pSacl
0x18001ac49  mov     r8d, edx; SecurityInfo
0x18001ac4c  mov     qword ptr [rsp+80h+nSubAuthority3], rdi; pDacl
0x18001ac51  mov     rcx, rbx; pObjectName
0x18001ac54  mov     qword ptr [rsp+80h+nSubAuthority2], rdi; psidGroup
0x18001ac59  call    cs:__imp_SetNamedSecurityInfoW
0x18001ac5f  mov     ebx, eax
0x18001ac61  test    eax, eax
0x18001ac63  jnz     short loc_18001AC2E
0x18001ac65  mov     ebx, edi
0x18001ac67  cmp     [rbp+OldValue], dil
0x18001ac6b  jnz     short loc_18001AC7F
0x18001ac6d  xor     edx, edx; NewValue
0x18001ac6f  lea     r9, [rbp+OldValue]; OldValue
0x18001ac73  xor     r8d, r8d; ForThread
0x18001ac76  lea     ecx, [rdx+9]; Privilege
0x18001ac79  call    cs:__imp_RtlAdjustPrivilege
0x18001ac7f  mov     rcx, [rbp+psidOwner]; pSid
0x18001ac83  test    rcx, rcx
0x18001ac86  jz      short loc_18001AC8E
0x18001ac88  call    cs:__imp_FreeSid
0x18001ac8e  mov     eax, ebx
0x18001ac90  mov     rcx, [rbp+var_8]
0x18001ac94  xor     rcx, rsp; StackCookie
0x18001ac97  call    __security_check_cookie
0x18001ac9c  lea     r11, [rsp+80h+var_s0]
0x18001aca4  mov     rbx, [r11+18h]
0x18001aca8  mov     rdi, [r11+20h]
0x18001acac  mov     rsp, r11
0x18001acaf  pop     rbp
0x18001acb0  retn
```
