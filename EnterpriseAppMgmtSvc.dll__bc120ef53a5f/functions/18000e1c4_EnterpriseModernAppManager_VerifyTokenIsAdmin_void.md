# EnterpriseModernAppManager::VerifyTokenIsAdmin(void *)

- ea: `0x18000e1c4`
- end: `0x18000e31c`
- name: `?VerifyTokenIsAdmin@EnterpriseModernAppManager@@QEAAJPEAX@Z`
- size: `344`
- prototype: `int(EnterpriseModernAppManager *__hidden this, void *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000b7b0`
- `0x18000bd80`
- `0x18000d240`
- `0x18000ddd0`
- `0x18000df50`

## callees

- `0x18000d3dc`
- `0x18000e1c4`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000e227`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e217`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18000e217`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2b0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000e2b0`
- `ntdll!NtAccessCheck` at `0x18000e29e`
- `ntdll!NtAccessCheck` at `0x18000e29e`

## string_xrefs

- `0x18000e2ed`: `onecoreuap\admin\appmodel\enterprisemodernappmanagement\service\dll\enterprisemodernappmanager.cpp`

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
0x18000e1c4  mov     [rsp-8+arg_0], rbx
0x18000e1c9  push    rbp
0x18000e1ca  lea     rbp, [rsp-57h]
0x18000e1cf  sub     rsp, 0A0h
0x18000e1d6  mov     rax, cs:__security_cookie
0x18000e1dd  xor     rax, rsp
0x18000e1e0  mov     [rbp+57h+var_8], rax
0x18000e1e4  xor     r9d, r9d; SecurityDescriptorSize
0x18000e1e7  mov     qword ptr [rbp+57h+GenericMapping.GenericRead], 0
0x18000e1ef  mov     rbx, rdx
0x18000e1f2  mov     [rbp+57h+GenericMapping.GenericExecute], 0
0x18000e1f9  lea     r8, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000e1fd  mov     [rbp+57h+GenericMapping.GenericAll], 1
0x18000e204  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;;0x1;;;SY)(A;;0x1;;;BA)"
0x18000e20b  mov     [rbp+57h+SecurityDescriptor], 0
0x18000e213  lea     edx, [r9+1]; StringSDRevision
0x18000e217  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18000e21e  nop     dword ptr [rax+rax+00h]
0x18000e223  test    eax, eax
0x18000e225  jnz     short loc_18000E254
0x18000e227  call    cs:__imp_GetLastError
0x18000e22e  nop     dword ptr [rax+rax+00h]
0x18000e233  mov     ebx, eax
0x18000e235  test    eax, eax
0x18000e237  jle     short loc_18000E242
0x18000e239  movzx   ebx, ax
0x18000e23c  or      ebx, 80070000h
0x18000e242  test    ebx, ebx
0x18000e244  jns     loc_18000E2FC
0x18000e24a  mov     edx, 8Fh
0x18000e24f  jmp     loc_18000E2E9
0x18000e254  mov     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000e258  lea     rax, [rbp+57h+var_60]
0x18000e25c  mov     [rsp+0A0h+AccessStatus], rax; AccessStatus
0x18000e261  lea     r9, [rbp+57h+GenericMapping]; GenericMapping
0x18000e265  lea     rax, [rbp+57h+var_5C]
0x18000e269  mov     [rbp+57h+var_5C], 0
0x18000e270  mov     [rsp+0A0h+GrantedAccess], rax; GrantedAccess
0x18000e275  mov     r8d, 1; DesiredAccess
0x18000e27b  lea     rax, [rbp+57h+var_58]
0x18000e27f  mov     [rbp+57h+var_60], 0C0000022h
0x18000e286  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x18000e28b  mov     rdx, rbx; ClientToken
0x18000e28e  lea     rax, [rbp+57h+var_38]
0x18000e292  mov     [rbp+57h+var_58], 2Ch ; ','
0x18000e299  mov     [rsp+0A0h+PrivilegeSet], rax; int
0x18000e29e  call    cs:__imp_NtAccessCheck
0x18000e2a5  nop     dword ptr [rax+rax+00h]
0x18000e2aa  mov     rcx, [rbp+57h+SecurityDescriptor]; hMem
0x18000e2ae  mov     ebx, eax
0x18000e2b0  call    cs:__imp_LocalFree
0x18000e2b7  nop     dword ptr [rax+rax+00h]
0x18000e2bc  test    ebx, ebx
0x18000e2be  jns     short loc_18000E2CF
0x18000e2c0  or      ebx, 10000000h
0x18000e2c6  jge     short loc_18000E2FC
0x18000e2c8  mov     edx, 0A7h
0x18000e2cd  jmp     short loc_18000E2E9
0x18000e2cf  cmp     [rbp+57h+var_60], 0
0x18000e2d3  jnz     short loc_18000E2DF
0x18000e2d5  cmp     [rbp+57h+var_5C], 1
0x18000e2d9  jnz     short loc_18000E2DF
0x18000e2db  xor     ebx, ebx
0x18000e2dd  jmp     short loc_18000E2FC
0x18000e2df  mov     ebx, 80070005h
0x18000e2e4  mov     edx, 0AAh; void *
0x18000e2e9  mov     rcx, [rbp+5Fh]; this
0x18000e2ed  lea     r8, aOnecoreuapAdmi_2; "onecoreuap\\admin\\appmodel\\enterprise"...
0x18000e2f4  mov     r9d, ebx; char *
0x18000e2f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000e2fc  mov     eax, ebx
0x18000e2fe  mov     rcx, [rbp+57h+var_8]
0x18000e302  xor     rcx, rsp; StackCookie
0x18000e305  call    __security_check_cookie
0x18000e30a  mov     rbx, [rsp+0A0h+arg_0]
0x18000e312  add     rsp, 0A0h
0x18000e319  pop     rbp
0x18000e31a  retn
```
