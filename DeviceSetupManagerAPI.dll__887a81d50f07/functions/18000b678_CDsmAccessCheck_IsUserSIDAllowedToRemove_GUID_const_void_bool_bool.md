# CDsmAccessCheck::_IsUserSIDAllowedToRemove(_GUID const &,void *,bool *,bool *)

- ea: `0x18000b678`
- end: `0x18000b8a4`
- name: `?_IsUserSIDAllowedToRemove@CDsmAccessCheck@@CAXAEBU_GUID@@PEAXPEA_N2@Z`
- size: `556`
- prototype: `void __fastcall(const struct _GUID *, void *, bool *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a934`

## callees

- `0x1800017c0`
- `0x18000b678`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b841`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000b7de`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18000b7de`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000b7a3`
- `api-ms-win-security-base-l1-1-0!DuplicateToken` at `0x18000b7a3`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000b82f`
- `api-ms-win-security-base-l1-1-0!AccessCheck` at `0x18000b82f`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18000b870`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18000b870`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18000b74c`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18000b74c`

## pseudocode

```c
void __fastcall CDsmAccessCheck::_IsUserSIDAllowedToRemove(const struct _GUID *a1, void *a2, bool *a3, bool *a4)
{
  bool v7; // di
  bool v8; // r14
  unsigned int v9; // r8d
  unsigned int v10; // ebx
  __int64 v11; // rdx
  void *v12; // rdi
  unsigned int v13; // [rsp+40h] [rbp-89h] BYREF
  WINBOOL AccessStatus; // [rsp+44h] [rbp-85h] BYREF
  DWORD AccessMask; // [rsp+48h] [rbp-81h] BYREF
  DWORD GrantedAccess; // [rsp+4Ch] [rbp-7Dh] BYREF
  DWORD PrivilegeSetLength; // [rsp+50h] [rbp-79h] BYREF
  void *DuplicateTokenHandle; // [rsp+58h] [rbp-71h] BYREF
  __int64 v19; // [rsp+60h] [rbp-69h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+68h] [rbp-61h] BYREF
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+78h] [rbp-51h] BYREF
  int v22; // [rsp+90h] [rbp-39h] BYREF
  DEVPROPKEY v23; // [rsp+98h] [rbp-31h]
  int v24; // [rsp+ACh] [rbp-1Dh]
  __int64 v25; // [rsp+B0h] [rbp-19h]
  int v26; // [rsp+B8h] [rbp-11h]
  int v27; // [rsp+BCh] [rbp-Dh]
  const struct _GUID *v28; // [rsp+C0h] [rbp-9h]
  __int128 v29; // [rsp+C8h] [rbp-1h] BYREF
  int v30; // [rsp+D8h] [rbp+Fh]
  int v31; // [rsp+DCh] [rbp+13h]
  __int64 v32; // [rsp+E0h] [rbp+17h]

  v30 = 102;
  v23 = DEVPKEY_Device_ContainerId;
  v28 = a1;
  v31 = 0;
  v7 = 0;
  v32 = 0;
  v8 = 0;
  v22 = 2;
  v29 = DEVPKEY_Device_EffectiveRestrictedSD;
  v24 = 0;
  v25 = 0;
  v26 = 13;
  v27 = 16;
  v13 = 0;
  v19 = 0;
  if ( (int)DevGetObjects(3, 0, 1, &v29, 1, &v22, &v13, &v19) < 0 )
    goto LABEL_14;
  v9 = v13;
  v10 = 0;
  if ( !v13 )
    goto LABEL_13;
  while ( 1 )
  {
    v11 = *(_QWORD *)(32LL * v10 + v19 + 24);
    if ( *(_DWORD *)(v11 + 32) == 19 )
      break;
LABEL_10:
    if ( ++v10 >= v9 )
      goto LABEL_13;
  }
  v12 = *(void **)(v11 + 40);
  AccessStatus = 0;
  DuplicateTokenHandle = 0;
  if ( DuplicateToken(a2, SecurityImpersonation, &DuplicateTokenHandle) )
  {
    GenericMapping.GenericRead = 1179785;
    GenericMapping.GenericWrite = 1179926;
    GenericMapping.GenericExecute = 1179808;
    GenericMapping.GenericAll = 2032127;
    AccessMask = 0x10000;
    MapGenericMask(&AccessMask, &GenericMapping);
    GrantedAccess = 0;
    PrivilegeSetLength = 20;
    memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
    if ( !AccessCheck(
            v12,
            DuplicateTokenHandle,
            AccessMask,
            &GenericMapping,
            &PrivilegeSet,
            &PrivilegeSetLength,
            &GrantedAccess,
            &AccessStatus) )
      AccessStatus = 0;
    CloseHandle(DuplicateTokenHandle);
  }
  v9 = v13;
  if ( AccessStatus )
  {
    v7 = 1;
    goto LABEL_10;
  }
  v7 = 0;
  v8 = 1;
LABEL_13:
  DevFreeObjects(v9, v19);
LABEL_14:
  if ( a3 )
    *a3 = v7;
  if ( a4 )
    *a4 = v8;
}

```

## disassembly

```asm
0x18000b678  push    rbp
0x18000b67a  push    rbx
0x18000b67b  push    rsi
0x18000b67c  push    rdi
0x18000b67d  push    r12
0x18000b67f  push    r14
0x18000b681  push    r15
0x18000b683  lea     rbp, [rsp-27h]
0x18000b688  sub     rsp, 0F0h
0x18000b68f  mov     rax, cs:__security_cookie
0x18000b696  xor     rax, rsp
0x18000b699  mov     [rbp+57h+var_38], rax
0x18000b69d  mov     eax, cs:dword_180012BE0
0x18000b6a3  mov     rsi, r9
0x18000b6a6  movups  xmm0, cs:DEVPKEY_Device_EffectiveRestrictedSD
0x18000b6ad  mov     [rbp+57h+var_48], eax
0x18000b6b0  lea     r9, [rbp+57h+var_58]
0x18000b6b4  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x18000b6ba  mov     r15, r8
0x18000b6bd  mov     [rbp+57h+var_78], eax
0x18000b6c0  mov     r12, rdx
0x18000b6c3  lea     rax, [rbp+57h+var_C0]
0x18000b6c7  mov     [rbp+57h+var_60], rcx
0x18000b6cb  mov     [rsp+120h+AccessStatus], rax
0x18000b6d0  xor     edx, edx
0x18000b6d2  lea     rax, [rsp+120h+var_E0]
0x18000b6d7  mov     [rbp+57h+var_44], 0
0x18000b6de  mov     [rsp+120h+GrantedAccess], rax
0x18000b6e3  xor     dil, dil
0x18000b6e6  lea     rax, [rbp+57h+var_90]
0x18000b6ea  mov     [rbp+57h+var_40], 0
0x18000b6f2  mov     [rsp+120h+PrivilegeSetLength], rax
0x18000b6f7  xor     r14b, r14b
0x18000b6fa  mov     eax, 1
0x18000b6ff  mov     [rbp+57h+var_90], 2
0x18000b706  movups  [rbp+57h+var_58], xmm0
0x18000b70a  mov     r8d, eax
0x18000b70d  mov     [rbp+57h+var_74], 0
0x18000b714  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18000b71b  lea     ecx, [rax+2]
0x18000b71e  mov     [rbp+57h+var_70], 0
0x18000b726  mov     [rbp+57h+var_68], 0Dh
0x18000b72d  movups  [rbp+57h+var_88], xmm0
0x18000b731  mov     [rbp+57h+var_64], 10h
0x18000b738  mov     [rsp+120h+var_E0], 0
0x18000b740  mov     [rbp+57h+var_C0], 0
0x18000b748  mov     dword ptr [rsp+120h+PrivilegeSet], eax
0x18000b74c  call    cs:__imp_DevGetObjects
0x18000b752  test    eax, eax
0x18000b754  js      loc_18000B876
0x18000b75a  mov     r8d, [rsp+120h+var_E0]
0x18000b75f  xor     ebx, ebx
0x18000b761  test    r8d, r8d
0x18000b764  jz      loc_18000B869
0x18000b76a  mov     rax, [rbp+57h+var_C0]
0x18000b76e  mov     ecx, ebx
0x18000b770  shl     rcx, 5
0x18000b774  mov     rdx, [rcx+rax+18h]
0x18000b779  cmp     dword ptr [rdx+20h], 13h
0x18000b77d  jnz     loc_18000B856
0x18000b783  mov     rdi, [rdx+28h]
0x18000b787  lea     r8, [rbp+57h+DuplicateTokenHandle]; DuplicateTokenHandle
0x18000b78b  mov     edx, 2; ImpersonationLevel
0x18000b790  mov     [rsp+120h+var_DC], 0
0x18000b798  mov     rcx, r12; ExistingTokenHandle
0x18000b79b  mov     [rbp+57h+DuplicateTokenHandle], 0
0x18000b7a3  call    cs:__imp_DuplicateToken
0x18000b7a9  test    eax, eax
0x18000b7ab  jz      loc_18000B847
0x18000b7b1  lea     rdx, [rbp+57h+GenericMapping]; GenericMapping
0x18000b7b5  mov     [rbp+57h+GenericMapping.GenericRead], 120089h
0x18000b7bc  lea     rcx, [rsp+120h+AccessMask]; AccessMask
0x18000b7c1  mov     [rbp+57h+GenericMapping.GenericWrite], 120116h
0x18000b7c8  mov     [rbp+57h+GenericMapping.GenericExecute], 1200A0h
0x18000b7cf  mov     [rbp+57h+GenericMapping.GenericAll], 1F01FFh
0x18000b7d6  mov     [rsp+120h+AccessMask], 10000h
0x18000b7de  call    cs:__imp_MapGenericMask
0x18000b7e4  mov     r8d, [rsp+120h+AccessMask]; DesiredAccess
0x18000b7e9  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18000b7ed  mov     rdx, [rbp+57h+DuplicateTokenHandle]; ClientToken
0x18000b7f1  xor     eax, eax
0x18000b7f3  mov     [rbp+57h+var_A8.Privilege.Attributes], eax
0x18000b7f6  xorps   xmm0, xmm0
0x18000b7f9  mov     [rbp+57h+var_D4], eax
0x18000b7fc  mov     rcx, rdi; pSecurityDescriptor
0x18000b7ff  lea     rax, [rsp+120h+var_DC]
0x18000b804  mov     [rbp+57h+var_D0], 14h
0x18000b80b  mov     [rsp+120h+AccessStatus], rax; AccessStatus
0x18000b810  lea     rax, [rbp+57h+var_D4]
0x18000b814  mov     [rsp+120h+GrantedAccess], rax; GrantedAccess
0x18000b819  lea     rax, [rbp+57h+var_D0]
0x18000b81d  mov     [rsp+120h+PrivilegeSetLength], rax; PrivilegeSetLength
0x18000b822  lea     rax, [rbp+57h+var_A8]
0x18000b826  mov     [rsp+120h+PrivilegeSet], rax; PrivilegeSet
0x18000b82b  movups  xmmword ptr [rbp+57h+var_A8.PrivilegeCount], xmm0
0x18000b82f  call    cs:__imp_AccessCheck
0x18000b835  test    eax, eax
0x18000b837  jnz     short loc_18000B83D
0x18000b839  mov     [rsp+120h+var_DC], eax
0x18000b83d  mov     rcx, [rbp+57h+DuplicateTokenHandle]; hObject
0x18000b841  call    cs:__imp_CloseHandle
0x18000b847  cmp     [rsp+120h+var_DC], 0
0x18000b84c  mov     r8d, [rsp+120h+var_E0]
0x18000b851  jz      short loc_18000B863
0x18000b853  mov     dil, 1
0x18000b856  inc     ebx
0x18000b858  cmp     ebx, r8d
0x18000b85b  jb      loc_18000B76A
0x18000b861  jmp     short loc_18000B869
0x18000b863  xor     dil, dil
0x18000b866  mov     r14b, 1
0x18000b869  mov     rdx, [rbp+57h+var_C0]
0x18000b86d  mov     ecx, r8d
0x18000b870  call    cs:__imp_DevFreeObjects
0x18000b876  test    r15, r15
0x18000b879  jz      short loc_18000B87E
0x18000b87b  mov     [r15], dil
0x18000b87e  test    rsi, rsi
0x18000b881  jz      short loc_18000B886
0x18000b883  mov     [rsi], r14b
0x18000b886  mov     rcx, [rbp+57h+var_38]
0x18000b88a  xor     rcx, rsp; StackCookie
0x18000b88d  call    __security_check_cookie
0x18000b892  add     rsp, 0F0h
0x18000b899  pop     r15
0x18000b89b  pop     r14
0x18000b89d  pop     r12
0x18000b89f  pop     rdi
0x18000b8a0  pop     rsi
0x18000b8a1  pop     rbx
0x18000b8a2  pop     rbp
0x18000b8a3  retn
```
