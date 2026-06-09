# WaasMedic::CProtectionUtil::ApplyPermissionsOnRegistryKey(HKEY__ *,ushort const *)

- ea: `0x180035734`
- end: `0x1800358d0`
- name: `?ApplyPermissionsOnRegistryKey@CProtectionUtil@WaasMedic@@SAJPEAUHKEY__@@PEBG@Z`
- size: `412`
- prototype: `__int64 __fastcall(HKEY handle, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a660`

## callees

- `0x18002e81c`
- `0x180035734`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003587b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800357d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003587b`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800357c8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorDacl` at `0x1800357c8`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180035814`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180035814`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800358b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800358b6`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180035857`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180035857`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003578d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18003578d`

## string_xrefs

- `0x1800357e7`: `ProtectionUtil - error creating dacl - 0x%08X`
- `0x18003589e`: `ProtectionUtil - error verifying that dacl is present - 0x%08X`
- `0x1800357ac`: `ProtectionUtil - error converting string to security descriptor - 0x%08X`
- `0x180035890`: `ProtectionUtil - error getting security descriptor control - 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CProtectionUtil::ApplyPermissionsOnRegistryKey(
        HKEY handle,
        LPCWSTR StringSecurityDescriptor)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int v5; // eax
  signed int v6; // eax
  signed int LastError; // eax
  DWORD dwRevision; // [rsp+40h] [rbp-20h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-18h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-10h] BYREF
  WORD pControl; // [rsp+70h] [rbp+10h] BYREF
  WINBOOL bDaclPresent; // [rsp+80h] [rbp+20h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+88h] [rbp+28h] BYREF

  SecurityDescriptor = 0;
  pDacl = 0;
  bDaclPresent = 0;
  bDaclDefaulted = 0;
  pControl = 0;
  dwRevision = 0;
  if ( !handle || !StringSecurityDescriptor )
    return 2147942487LL;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0) )
  {
    if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( bDaclPresent && pDacl )
      {
        if ( GetSecurityDescriptorControl(SecurityDescriptor, &pControl, &dwRevision) )
        {
          v6 = SetSecurityInfo(handle, SE_REGISTRY_KEY, ((pControl & 0x100) << 21) | 4, 0, 0, pDacl, 0);
          v4 = v6;
          if ( v6 )
          {
            if ( v6 > 0 )
              v4 = (unsigned __int16)v6 | 0x80070000;
            LogLevelW(2u, L"ProtectionUtil - error assigning SD to key - 0x%08X", v4);
          }
          else
          {
            v4 = 0;
          }
        }
        else
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
          LogLevelW(2u, L"ProtectionUtil - error getting security descriptor control - 0x%08X", v4);
        }
      }
      else
      {
        v4 = -2147023560;
        LogLevelW(2u, L"ProtectionUtil - error verifying that dacl is present - 0x%08X", 2147943736LL);
      }
    }
    else
    {
      v5 = GetLastError();
      v4 = v5;
      if ( v5 > 0 )
        v4 = (unsigned __int16)v5 | 0x80070000;
      LogLevelW(2u, L"ProtectionUtil - error creating dacl - 0x%08X", v4);
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
0x180035734  mov     [rsp-8+arg_8], rbx
0x180035739  push    rbp
0x18003573a  mov     rbp, rsp
0x18003573d  sub     rsp, 60h
0x180035741  xor     eax, eax
0x180035743  mov     [rbp+SecurityDescriptor], 0
0x18003574b  mov     [rbp+pDacl], 0
0x180035753  mov     r10, rdx
0x180035756  mov     [rbp+bDaclPresent], 0
0x18003575d  mov     rbx, rcx
0x180035760  mov     [rbp+bDaclDefaulted], 0
0x180035767  mov     [rbp+pControl], ax
0x18003576b  mov     [rbp+dwRevision], eax
0x18003576e  test    rcx, rcx
0x180035771  jz      loc_1800358C0
0x180035777  test    rdx, rdx
0x18003577a  jz      loc_1800358C0
0x180035780  xor     r9d, r9d; SecurityDescriptorSize
0x180035783  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180035787  lea     edx, [rax+1]; StringSDRevision
0x18003578a  mov     rcx, r10; StringSecurityDescriptor
0x18003578d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180035793  test    eax, eax
0x180035795  jnz     short loc_1800357B8
0x180035797  call    cs:__imp_GetLastError
0x18003579d  mov     ebx, eax
0x18003579f  test    eax, eax
0x1800357a1  jle     short loc_1800357AC
0x1800357a3  movzx   ebx, ax
0x1800357a6  or      ebx, 80070000h
0x1800357ac  lea     rdx, aProtectionutil_2; "ProtectionUtil - error converting strin"...
0x1800357b3  jmp     loc_1800358A5
0x1800357b8  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x1800357bc  lea     r9, [rbp+bDaclDefaulted]; lpbDaclDefaulted
0x1800357c0  lea     r8, [rbp+pDacl]; pDacl
0x1800357c4  lea     rdx, [rbp+bDaclPresent]; lpbDaclPresent
0x1800357c8  call    cs:__imp_GetSecurityDescriptorDacl
0x1800357ce  test    eax, eax
0x1800357d0  jnz     short loc_1800357F3
0x1800357d2  call    cs:__imp_GetLastError
0x1800357d8  mov     ebx, eax
0x1800357da  test    eax, eax
0x1800357dc  jle     short loc_1800357E7
0x1800357de  movzx   ebx, ax
0x1800357e1  or      ebx, 80070000h
0x1800357e7  lea     rdx, aProtectionutil_0; "ProtectionUtil - error creating dacl - "...
0x1800357ee  jmp     loc_1800358A5
0x1800357f3  cmp     [rbp+bDaclPresent], 0
0x1800357f7  jz      loc_180035899
0x1800357fd  cmp     [rbp+pDacl], 0
0x180035802  jz      loc_180035899
0x180035808  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18003580c  lea     r8, [rbp+dwRevision]; lpdwRevision
0x180035810  lea     rdx, [rbp+pControl]; pControl
0x180035814  call    cs:__imp_GetSecurityDescriptorControl
0x18003581a  test    eax, eax
0x18003581c  jz      short loc_18003587B
0x18003581e  movzx   r8d, [rbp+pControl]
0x180035823  mov     edx, 4; ObjectType
0x180035828  mov     rax, [rbp+pDacl]
0x18003582c  and     r8d, 100h
0x180035833  shl     r8d, 15h
0x180035837  xor     r9d, r9d; psidOwner
0x18003583a  mov     [rsp+60h+pSacl], 0; pSacl
0x180035843  or      r8d, edx; SecurityInfo
0x180035846  mov     [rsp+60h+var_38], rax; pDacl
0x18003584b  mov     rcx, rbx; handle
0x18003584e  mov     [rsp+60h+psidGroup], 0; psidGroup
0x180035857  call    cs:__imp_SetSecurityInfo
0x18003585d  mov     ebx, eax
0x18003585f  test    eax, eax
0x180035861  jz      short loc_180035877
0x180035863  jle     short loc_18003586E
0x180035865  movzx   ebx, ax
0x180035868  or      ebx, 80070000h
0x18003586e  lea     rdx, aProtectionutil_6; "ProtectionUtil - error assigning SD to "...
0x180035875  jmp     short loc_1800358A5
0x180035877  xor     ebx, ebx
0x180035879  jmp     short loc_1800358B2
0x18003587b  call    cs:__imp_GetLastError
0x180035881  mov     ebx, eax
0x180035883  test    eax, eax
0x180035885  jle     short loc_180035890
0x180035887  movzx   ebx, ax
0x18003588a  or      ebx, 80070000h
0x180035890  lea     rdx, aProtectionutil_1; "ProtectionUtil - error getting security"...
0x180035897  jmp     short loc_1800358A5
0x180035899  mov     ebx, 80070538h
0x18003589e  lea     rdx, aProtectionutil; "ProtectionUtil - error verifying that d"...
0x1800358a5  mov     r8d, ebx
0x1800358a8  mov     ecx, 2; unsigned __int8
0x1800358ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800358b2  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800358b6  call    cs:__imp_LocalFree
0x1800358bc  mov     eax, ebx
0x1800358be  jmp     short loc_1800358C5
0x1800358c0  mov     eax, 80070057h
0x1800358c5  mov     rbx, [rsp+60h+arg_8]
0x1800358ca  add     rsp, 60h
0x1800358ce  pop     rbp
0x1800358cf  retn
```
