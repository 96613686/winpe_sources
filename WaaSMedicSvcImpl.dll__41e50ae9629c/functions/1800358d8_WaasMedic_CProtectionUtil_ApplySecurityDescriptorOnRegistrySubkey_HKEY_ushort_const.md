# WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)

- ea: `0x1800358d8`
- end: `0x180035a1b`
- name: `?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z`
- size: `323`
- prototype: `__int64 __fastcall(HKEY handle, LPCWSTR StringSecurityDescriptor)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180025728`
- `0x18002744c`
- `0x18003a660`
- `0x18003ba20`
- `0x180068100`

## callees

- `0x18002e81c`
- `0x1800358d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003596e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035933`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003596e`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180035964`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180035964`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a01`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180035a01`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800359c0`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1800359c0`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035929`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180035929`

## string_xrefs

- `0x180035948`: `ProtectionUtil - error converting string to security descriptor - 0x%08X`
- `0x180035983`: `ProtectionUtil - error creating sacl- 0x%08X`
- `0x1800359e9`: `ProtectionUtil - error verifying that sacl is present - 0x%08X`
- `0x1800359d7`: `ProtectionUtil - error assigning SACL to subkey - 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(
        HKEY handle,
        LPCWSTR StringSecurityDescriptor)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  PACL pSacl; // [rsp+40h] [rbp-10h] BYREF
  WINBOOL bSaclPresent; // [rsp+60h] [rbp+10h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+70h] [rbp+20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+78h] [rbp+28h] BYREF

  SecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !handle || !StringSecurityDescriptor )
    return 2147942487LL;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    {
      if ( bSaclPresent && pSacl )
      {
        v6 = SetSecurityInfo(handle, SE_REGISTRY_KEY, 0x80u, 0, 0, 0, pSacl);
        v4 = v6;
        if ( v6 )
        {
          if ( v6 > 0 )
            v4 = (unsigned __int16)v6 | 0x80070000;
          LogLevelW(2u, L"ProtectionUtil - error assigning SACL to subkey - 0x%08X", v4);
        }
        else
        {
          v4 = 0;
        }
      }
      else
      {
        v4 = -2147023560;
        LogLevelW(2u, L"ProtectionUtil - error verifying that sacl is present - 0x%08X", 2147943736LL);
      }
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError > 0 )
        v4 = (unsigned __int16)LastError | 0x80070000;
      LogLevelW(2u, L"ProtectionUtil - error creating sacl- 0x%08X", v4);
    }
  }
  else
  {
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      v4 = (unsigned __int16)v3 | 0x80070000;
    LogLevelW(2u, L"ProtectionUtil - error converting string to security descriptor - 0x%08X", v4);
  }
  LocalFree(SecurityDescriptor);
  return v4;
}

```

## disassembly

```asm
0x1800358d8  mov     [rsp-8+arg_8], rbx
0x1800358dd  push    rbp
0x1800358de  mov     rbp, rsp
0x1800358e1  sub     rsp, 50h
0x1800358e5  mov     [rbp+SecurityDescriptor], 0
0x1800358ed  mov     rax, rdx
0x1800358f0  mov     [rbp+pSacl], 0
0x1800358f8  mov     rbx, rcx
0x1800358fb  mov     [rbp+bSaclPresent], 0
0x180035902  mov     [rbp+bSaclDefaulted], 0
0x180035909  test    rcx, rcx
0x18003590c  jz      loc_180035A0B
0x180035912  test    rax, rax
0x180035915  jz      loc_180035A0B
0x18003591b  xor     r9d, r9d; SecurityDescriptorSize
0x18003591e  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180035922  mov     rcx, rax; StringSecurityDescriptor
0x180035925  lea     edx, [r9+1]; StringSDRevision
0x180035929  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18003592f  test    eax, eax
0x180035931  jnz     short loc_180035954
0x180035933  call    cs:__imp_GetLastError
0x180035939  mov     ebx, eax
0x18003593b  test    eax, eax
0x18003593d  jle     short loc_180035948
0x18003593f  movzx   ebx, ax
0x180035942  or      ebx, 80070000h
0x180035948  lea     rdx, aProtectionutil_2; "ProtectionUtil - error converting strin"...
0x18003594f  jmp     loc_1800359F0
0x180035954  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x180035958  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x18003595c  lea     r8, [rbp+pSacl]; pSacl
0x180035960  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180035964  call    cs:__imp_GetSecurityDescriptorSacl
0x18003596a  test    eax, eax
0x18003596c  jnz     short loc_18003598C
0x18003596e  call    cs:__imp_GetLastError
0x180035974  mov     ebx, eax
0x180035976  test    eax, eax
0x180035978  jle     short loc_180035983
0x18003597a  movzx   ebx, ax
0x18003597d  or      ebx, 80070000h
0x180035983  lea     rdx, aProtectionutil_3; "ProtectionUtil - error creating sacl- 0"...
0x18003598a  jmp     short loc_1800359F0
0x18003598c  cmp     [rbp+bSaclPresent], 0
0x180035990  jz      short loc_1800359E4
0x180035992  mov     rax, [rbp+pSacl]
0x180035996  test    rax, rax
0x180035999  jz      short loc_1800359E4
0x18003599b  mov     [rsp+50h+var_20], rax; pSacl
0x1800359a0  xor     r9d, r9d; psidOwner
0x1800359a3  mov     [rsp+50h+pDacl], 0; pDacl
0x1800359ac  mov     rcx, rbx; handle
0x1800359af  mov     [rsp+50h+psidGroup], 0; psidGroup
0x1800359b8  lea     edx, [r9+4]; ObjectType
0x1800359bc  lea     r8d, [rdx+7Ch]; SecurityInfo
0x1800359c0  call    cs:__imp_SetSecurityInfo
0x1800359c6  mov     ebx, eax
0x1800359c8  test    eax, eax
0x1800359ca  jz      short loc_1800359E0
0x1800359cc  jle     short loc_1800359D7
0x1800359ce  movzx   ebx, ax
0x1800359d1  or      ebx, 80070000h
0x1800359d7  lea     rdx, aProtectionutil_5; "ProtectionUtil - error assigning SACL t"...
0x1800359de  jmp     short loc_1800359F0
0x1800359e0  xor     ebx, ebx
0x1800359e2  jmp     short loc_1800359FD
0x1800359e4  mov     ebx, 80070538h
0x1800359e9  lea     rdx, aProtectionutil_4; "ProtectionUtil - error verifying that s"...
0x1800359f0  mov     r8d, ebx
0x1800359f3  mov     ecx, 2; unsigned __int8
0x1800359f8  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800359fd  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180035a01  call    cs:__imp_LocalFree
0x180035a07  mov     eax, ebx
0x180035a09  jmp     short loc_180035A10
0x180035a0b  mov     eax, 80070057h
0x180035a10  mov     rbx, [rsp+50h+arg_8]
0x180035a15  add     rsp, 50h
0x180035a19  pop     rbp
0x180035a1a  retn
```
