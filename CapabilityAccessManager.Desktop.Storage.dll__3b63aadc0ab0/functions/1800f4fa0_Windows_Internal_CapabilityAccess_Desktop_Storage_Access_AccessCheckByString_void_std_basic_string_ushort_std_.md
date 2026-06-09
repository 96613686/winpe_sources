# Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800f4fa0`
- end: `0x1800f5124`
- name: `?AccessCheckByString@Access@Storage@Desktop@CapabilityAccess@Internal@Windows@@YA_NPEAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `388`
- prototype: `char __fastcall(HANDLE ClientToken, const WCHAR *StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800f512c`

## callees

- `0x180003060`
- `0x1800f4fa0`
- `0x1800f5bb4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f503b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f503b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f5028`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5033`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f50d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f50e3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f5033`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f50d0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f50e3`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800f50ad`
- `api-ms-win-security-base-l1-1-0!AccessCheckByType` at `0x1800f50ad`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f5000`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800f5000`

## pseudocode

```c
char __fastcall Windows::Internal::CapabilityAccess::Desktop::Storage::Access::AccessCheckByString(
        HANDLE ClientToken,
        const WCHAR *StringSecurityDescriptor)
{
  const WCHAR *v2; // rax
  __int64 v4; // r8
  const char *v5; // r9
  PSECURITY_DESCRIPTOR v6; // r14
  PSECURITY_DESCRIPTOR *v7; // rdi
  PSECURITY_DESCRIPTOR v8; // rsi
  DWORD LastError; // ebx
  __int64 v10; // r8
  const char *v11; // r9
  WINBOOL AccessStatus; // [rsp+60h] [rbp-19h] BYREF
  DWORD GrantedAccess; // [rsp+64h] [rbp-15h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+68h] [rbp-11h] BYREF
  DWORD PrivilegeSetLength; // [rsp+70h] [rbp-9h] BYREF
  PSECURITY_DESCRIPTOR *p_pSecurityDescriptor; // [rsp+78h] [rbp-1h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+80h] [rbp+7h] BYREF
  char v19; // [rsp+88h] [rbp+Fh]
  struct _PRIVILEGE_SET PrivilegeSet; // [rsp+90h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v2 = StringSecurityDescriptor;
  pSecurityDescriptor = 0;
  p_pSecurityDescriptor = &pSecurityDescriptor;
  SecurityDescriptor = 0;
  v19 = 1;
  if ( *((_QWORD *)StringSecurityDescriptor + 3) > 7u )
    v2 = *(const WCHAR **)StringSecurityDescriptor;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v2, 1u, &SecurityDescriptor, 0) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0xEE, v4, v5);
  if ( v19 )
  {
    v6 = SecurityDescriptor;
    v7 = p_pSecurityDescriptor;
    v8 = *p_pSecurityDescriptor;
    if ( *p_pSecurityDescriptor )
    {
      LastError = GetLastError();
      LocalFree(v8);
      SetLastError(LastError);
    }
    *v7 = v6;
  }
  memset(&PrivilegeSet, 0, sizeof(PrivilegeSet));
  GrantedAccess = 0;
  AccessStatus = 0;
  PrivilegeSetLength = 20;
  if ( !AccessCheckByType(
          pSecurityDescriptor,
          0,
          ClientToken,
          1u,
          0,
          0,
          (PGENERIC_MAPPING)&GenericMapping,
          &PrivilegeSet,
          &PrivilegeSetLength,
          &GrantedAccess,
          &AccessStatus) )
    wil::details::in1diag3::_Throw_GetLastError(retaddr, (void *)0x108, v10, v11);
  if ( AccessStatus && (GrantedAccess & 1) != 0 )
  {
    if ( pSecurityDescriptor )
      LocalFree(pSecurityDescriptor);
    return 1;
  }
  else
  {
    if ( pSecurityDescriptor )
      LocalFree(pSecurityDescriptor);
    return 0;
  }
}

```

## disassembly

```asm
0x1800f4fa0  mov     [rsp-8+arg_10], rbx
0x1800f4fa5  push    rbp
0x1800f4fa6  push    rsi
0x1800f4fa7  push    rdi
0x1800f4fa8  push    r14
0x1800f4faa  push    r15
0x1800f4fac  lea     rbp, [rsp-37h]
0x1800f4fb1  sub     rsp, 0B0h
0x1800f4fb8  mov     rax, cs:__security_cookie
0x1800f4fbf  xor     rax, rsp
0x1800f4fc2  mov     [rbp+57h+var_28], rax
0x1800f4fc6  mov     rax, rdx
0x1800f4fc9  mov     r15, rcx
0x1800f4fcc  mov     [rbp+57h+pSecurityDescriptor], 0
0x1800f4fd4  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1800f4fd8  mov     [rbp+57h+var_58], rcx
0x1800f4fdc  mov     [rbp+57h+SecurityDescriptor], 0
0x1800f4fe4  mov     [rbp+57h+var_48], 1
0x1800f4fe8  cmp     qword ptr [rdx+18h], 7
0x1800f4fed  jbe     short loc_1800F4FF2
0x1800f4fef  mov     rax, [rdx]
0x1800f4ff2  xor     r9d, r9d; SecurityDescriptorSize
0x1800f4ff5  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x1800f4ff9  lea     edx, [r9+1]; StringSDRevision
0x1800f4ffd  mov     rcx, rax; StringSecurityDescriptor
0x1800f5000  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800f5006  mov     rcx, [rbp+5Fh]; this
0x1800f500a  test    eax, eax
0x1800f500c  jz      loc_1800F5119
0x1800f5012  cmp     [rbp+57h+var_48], 0
0x1800f5016  jz      short loc_1800F5044
0x1800f5018  mov     r14, [rbp+57h+SecurityDescriptor]
0x1800f501c  mov     rdi, [rbp+57h+var_58]
0x1800f5020  mov     rsi, [rdi]
0x1800f5023  test    rsi, rsi
0x1800f5026  jz      short loc_1800F5041
0x1800f5028  call    cs:__imp_GetLastError
0x1800f502e  mov     ebx, eax
0x1800f5030  mov     rcx, rsi; hMem
0x1800f5033  call    cs:__imp_LocalFree
0x1800f5039  mov     ecx, ebx; dwErrCode
0x1800f503b  call    cs:__imp_SetLastError
0x1800f5041  mov     [rdi], r14
0x1800f5044  xorps   xmm0, xmm0
0x1800f5047  xor     eax, eax
0x1800f5049  movups  xmmword ptr [rbp+57h+var_40.PrivilegeCount], xmm0
0x1800f504d  mov     [rbp+57h+var_40.Privilege.Attributes], eax
0x1800f5050  mov     [rbp+57h+var_6C], eax
0x1800f5053  mov     [rbp+57h+var_70], eax
0x1800f5056  mov     [rbp+57h+var_60], 14h
0x1800f505d  lea     rax, [rbp+57h+var_70]
0x1800f5061  mov     [rsp+0D0h+AccessStatus], rax; AccessStatus
0x1800f5066  lea     rax, [rbp+57h+var_6C]
0x1800f506a  mov     [rsp+0D0h+GrantedAccess], rax; GrantedAccess
0x1800f506f  lea     rax, [rbp+57h+var_60]
0x1800f5073  mov     [rsp+0D0h+PrivilegeSetLength], rax; PrivilegeSetLength
0x1800f5078  lea     rax, [rbp+57h+var_40]
0x1800f507c  mov     [rsp+0D0h+PrivilegeSet], rax; PrivilegeSet
0x1800f5081  lea     rax, GenericMapping
0x1800f5088  mov     [rsp+0D0h+GenericMapping], rax; GenericMapping
0x1800f508d  mov     [rsp+0D0h+ObjectTypeListLength], 0; ObjectTypeListLength
0x1800f5095  mov     [rsp+0D0h+ObjectTypeList], 0; ObjectTypeList
0x1800f509e  mov     r9d, 1; DesiredAccess
0x1800f50a4  mov     r8, r15; ClientToken
0x1800f50a7  xor     edx, edx; PrincipalSelfSid
0x1800f50a9  mov     rcx, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x1800f50ad  call    cs:__imp_AccessCheckByType
0x1800f50b3  mov     rcx, [rbp+5Fh]; this
0x1800f50b7  test    eax, eax
0x1800f50b9  jz      short loc_1800F510E
0x1800f50bb  cmp     [rbp+57h+var_70], 0
0x1800f50bf  jz      short loc_1800F50DA
0x1800f50c1  test    byte ptr [rbp+57h+var_6C], 1
0x1800f50c5  jz      short loc_1800F50DA
0x1800f50c7  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x1800f50cb  test    rcx, rcx
0x1800f50ce  jz      short loc_1800F50D6
0x1800f50d0  call    cs:__imp_LocalFree
0x1800f50d6  mov     al, 1
0x1800f50d8  jmp     short loc_1800F50EB
0x1800f50da  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x1800f50de  test    rcx, rcx
0x1800f50e1  jz      short loc_1800F50E9
0x1800f50e3  call    cs:__imp_LocalFree
0x1800f50e9  xor     al, al
0x1800f50eb  mov     rcx, [rbp+57h+var_28]
0x1800f50ef  xor     rcx, rsp; StackCookie
0x1800f50f2  call    __security_check_cookie
0x1800f50f7  mov     rbx, [rsp+0D0h+arg_10]
0x1800f50ff  add     rsp, 0B0h
0x1800f5106  pop     r15
0x1800f5108  pop     r14
0x1800f510a  pop     rdi
0x1800f510b  pop     rsi
0x1800f510c  pop     rbp
0x1800f510d  retn
0x1800f510e  mov     edx, 108h; void *
0x1800f5113  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1800f5119  mov     edx, 0EEh; void *
0x1800f511e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
```
