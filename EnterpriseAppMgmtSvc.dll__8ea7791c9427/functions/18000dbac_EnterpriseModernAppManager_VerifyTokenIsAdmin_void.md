# EnterpriseModernAppManager::VerifyTokenIsAdmin(void *)

- ea: `0x18000dbac`
- end: `0x18000dceb`
- name: `?VerifyTokenIsAdmin@EnterpriseModernAppManager@@QEAAJPEAX@Z`
- size: `319`
- prototype: `int(EnterpriseModernAppManager *__hidden this, void *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b4d0`
- `0x18000b9a0`
- `0x18000ce70`
- `0x18000d850`
- `0x18000d9d0`

## callees

- `0x18000cfe8`
- `0x18000dbac`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc09`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dbff`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000dbff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc86`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000dc86`
- `ntdll!NtAccessCheck` at `0x18000dc7a`
- `ntdll!NtAccessCheck` at `0x18000dc7a`

## string_xrefs

- `0x18000dcbd`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`

## pseudocode

```c
__int64 __fastcall EnterpriseModernAppManager::VerifyTokenIsAdmin(EnterpriseModernAppManager *this, void *a2)
{
  signed int LastError; // eax
  int v4; // ebx
  __int64 v5; // rdx
  NTSTATUS v6; // ebx
  int PrivilegeSet; // [rsp+20h] [rbp-29h]
  int AccessStatus; // [rsp+40h] [rbp-9h] BYREF
  DWORD GrantedAccess; // [rsp+44h] [rbp-5h] BYREF
  ULONG ReturnLength; // [rsp+48h] [rbp-1h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp+7h] BYREF
  _GENERIC_MAPPING GenericMapping; // [rsp+58h] [rbp+Fh] BYREF
  struct _PRIVILEGE_SET v14; // [rsp+68h] [rbp+1Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  *(_QWORD *)&GenericMapping.GenericRead = 0;
  GenericMapping.GenericExecute = 0;
  GenericMapping.GenericAll = 1;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAG:BAD:(A;;0x1;;;SY)(A;;0x1;;;BA)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    GrantedAccess = 0;
    AccessStatus = -1073741790;
    ReturnLength = 44;
    v6 = NtAccessCheck(SecurityDescriptor, a2, 1u, &GenericMapping, &v14, &ReturnLength, &GrantedAccess, &AccessStatus);
    LocalFree(SecurityDescriptor);
    if ( v6 >= 0 )
    {
      if ( AccessStatus || GrantedAccess != 1 )
      {
        v4 = -2147024891;
        v5 = 170;
        goto LABEL_13;
      }
      return 0;
    }
    else
    {
      v4 = v6 | 0x10000000;
      if ( v4 < 0 )
      {
        v5 = 167;
        goto LABEL_13;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v4 < 0 )
    {
      v5 = 143;
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v5,
        (unsigned int)"onecoreuap\\admin\\appmodel\\enterprisemodernappmanagement\\service\\dll\\enterprisemodernappmanager.cpp",
        (const char *)(unsigned int)v4,
        PrivilegeSet);
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000dbac  mov     [rsp-8+arg_0], rbx
0x18000dbb1  push    rbp
0x18000dbb2  lea     rbp, [rsp-57h]
0x18000dbb7  sub     rsp, 0A0h
0x18000dbbe  mov     rax, cs:__security_cookie
0x18000dbc5  xor     rax, rsp
0x18000dbc8  mov     [rbp+57h+var_8], rax
0x18000dbcc  xor     r9d, r9d; SecurityDescriptorSize
0x18000dbcf  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], 0
0x18000dbd7  mov     rbx, rdx
0x18000dbda  mov     [rbp+57h+GenericMapping.GenericExecute], 0
0x18000dbe1  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000dbe5  mov     [rbp+57h+GenericMapping.GenericAll], 1
0x18000dbec  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1;;;SY)(A;;0x1;;;BA)"
0x18000dbf3  mov     [rbp+57h+SecurityDescriptor], 0
0x18000dbfb  lea     edx, [r9+1]; StringSDRevision
0x18000dbff  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000dc05  test    eax, eax
0x18000dc07  jnz     short loc_18000DC30
0x18000dc09  call    cs:__imp_GetLastError
0x18000dc0f  mov     ebx, eax
0x18000dc11  test    eax, eax
0x18000dc13  jle     short loc_18000DC1E
0x18000dc15  movzx   ebx, ax
0x18000dc18  or      ebx, 80070000h
0x18000dc1e  test    ebx, ebx
0x18000dc20  jns     loc_18000DCCC
0x18000dc26  mov     edx, 8Fh
0x18000dc2b  jmp     loc_18000DCB9
0x18000dc30  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000dc34  lea     rax, [rbp+57h+var_60]
0x18000dc38  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18000dc3d  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18000dc41  lea     rax, [rbp+57h+var_5C]
0x18000dc45  mov     [rbp+57h+var_5C], 0
0x18000dc4c  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18000dc51  mov     r8d, 1; DesiredAccess
0x18000dc57  lea     rax, [rbp+57h+var_58]
0x18000dc5b  mov     [rbp+57h+var_60], 0C0000022h
0x18000dc62  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18000dc67  mov     rdx, rbx; ClientToken
0x18000dc6a  lea     rax, [rbp+57h+var_38]
0x18000dc6e  mov     [rbp+57h+var_58], 2Ch ; ','
0x18000dc75  mov     [rsp+0A0h+PrivilegeSet], rax; int
0x18000dc7a  call    cs:__imp_NtAccessCheck
0x18000dc80  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000dc84  mov     ebx, eax
0x18000dc86  call    cs:__imp_LocalFree
0x18000dc8c  test    ebx, ebx
0x18000dc8e  jns     short loc_18000DC9F
0x18000dc90  or      ebx, 10000000h
0x18000dc96  jge     short loc_18000DCCC
0x18000dc98  mov     edx, 0A7h
0x18000dc9d  jmp     short loc_18000DCB9
0x18000dc9f  cmp     [rbp+57h+var_60], 0
0x18000dca3  jnz     short loc_18000DCAF
0x18000dca5  cmp     [rbp+57h+var_5C], 1
0x18000dca9  jnz     short loc_18000DCAF
0x18000dcab  xor     ebx, ebx
0x18000dcad  jmp     short loc_18000DCCC
0x18000dcaf  mov     ebx, 80070005h
0x18000dcb4  mov     edx, 0AAh; void *
0x18000dcb9  mov     rcx, [rbp+5Fh]; this
0x18000dcbd  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000dcc4  mov     r9d, ebx; char *
0x18000dcc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dccc  mov     eax, ebx
0x18000dcce  mov     rcx, [rbp+57h+var_8]
0x18000dcd2  xor     rcx, rsp; StackCookie
0x18000dcd5  call    __security_check_cookie
0x18000dcda  mov     rbx, [rsp+0A0h+arg_0]
0x18000dce2  add     rsp, 0A0h
0x18000dce9  pop     rbp
0x18000dcea  retn
```
