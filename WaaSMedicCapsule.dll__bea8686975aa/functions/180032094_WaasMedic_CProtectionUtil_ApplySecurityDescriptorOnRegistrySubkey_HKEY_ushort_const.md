# WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(HKEY__ *,ushort const *)

- ea: `0x180032094`
- end: `0x1800321cc`
- name: `?ApplySecurityDescriptorOnRegistrySubkey@CProtectionUtil@WaasMedic@@CAJPEAUHKEY__@@PEBG@Z`
- size: `312`
- prototype: `__int64 __fastcall(HKEY handle, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180029500`

## callees

- `0x18002543c`
- `0x180032094`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032123`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800320e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032123`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180032119`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x180032119`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180032175`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180032175`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321b6`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800321b6`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800320de`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800320de`

## string_xrefs

- `0x1800320fd`: `ProtectionUtil - error converting string to security descriptor - 0x%08X`
- `0x180032138`: `ProtectionUtil - error creating sacl- 0x%08X`
- `0x18003218c`: `ProtectionUtil - error assigning SACL to subkey - 0x%08X`
- `0x18003219e`: `ProtectionUtil - error verifying that sacl is present - 0x%08X`

## pseudocode

```c
__int64 __fastcall WaasMedic::CProtectionUtil::ApplySecurityDescriptorOnRegistrySubkey(
        HKEY handle,
        const unsigned __int16 *a2)
{
  signed int v3; // eax
  unsigned int v4; // ebx
  signed int LastError; // eax
  signed int v6; // eax
  WINBOOL bSaclDefaulted; // [rsp+60h] [rbp+18h] BYREF
  WINBOOL bSaclPresent; // [rsp+68h] [rbp+20h] BYREF
  int v10; // [rsp+6Ch] [rbp+24h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+28h] BYREF
  PACL pSacl; // [rsp+78h] [rbp+30h] BYREF

  v10 = HIDWORD(a2);
  SecurityDescriptor = 0;
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  if ( !handle )
    return 2147942487LL;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"S:AI(TL;;KR;;;S-1-19-512-4096)",
         1u,
         &SecurityDescriptor,
         0) )
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
0x180032094  mov     qword ptr [rsp-10h+bSaclPresent], rdx
0x180032099  push    rbp
0x18003209a  push    rbx
0x18003209b  mov     rbp, rsp
0x18003209e  sub     rsp, 48h
0x1800320a2  mov     [rbp+SecurityDescriptor], 0
0x1800320aa  mov     rbx, rcx
0x1800320ad  mov     [rbp+pSacl], 0
0x1800320b5  mov     [rbp+bSaclPresent], 0
0x1800320bc  mov     [rbp+bSaclDefaulted], 0
0x1800320c3  test    rcx, rcx
0x1800320c6  jz      loc_1800321C0
0x1800320cc  xor     r9d, r9d; SecurityDescriptorSize
0x1800320cf  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x1800320d3  lea     rcx, StringSecurityDescriptor; "S:AI(TL;;KR;;;S-1-19-512-4096)"
0x1800320da  lea     edx, [r9+1]; StringSDRevision
0x1800320de  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x1800320e4  test    eax, eax
0x1800320e6  jnz     short loc_180032109
0x1800320e8  call    cs:__imp_GetLastError
0x1800320ee  mov     ebx, eax
0x1800320f0  test    eax, eax
0x1800320f2  jle     short loc_1800320FD
0x1800320f4  movzx   ebx, ax
0x1800320f7  or      ebx, 80070000h
0x1800320fd  lea     rdx, aProtectionutil; "ProtectionUtil - error converting strin"...
0x180032104  jmp     loc_1800321A5
0x180032109  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18003210d  lea     r9, [rbp+bSaclDefaulted]; lpbSaclDefaulted
0x180032111  lea     r8, [rbp+pSacl]; pSacl
0x180032115  lea     rdx, [rbp+bSaclPresent]; lpbSaclPresent
0x180032119  call    cs:__imp_GetSecurityDescriptorSacl
0x18003211f  test    eax, eax
0x180032121  jnz     short loc_180032141
0x180032123  call    cs:__imp_GetLastError
0x180032129  mov     ebx, eax
0x18003212b  test    eax, eax
0x18003212d  jle     short loc_180032138
0x18003212f  movzx   ebx, ax
0x180032132  or      ebx, 80070000h
0x180032138  lea     rdx, aProtectionutil_0; "ProtectionUtil - error creating sacl- 0"...
0x18003213f  jmp     short loc_1800321A5
0x180032141  cmp     [rbp+bSaclPresent], 0
0x180032145  jz      short loc_180032199
0x180032147  mov     rax, [rbp+pSacl]
0x18003214b  test    rax, rax
0x18003214e  jz      short loc_180032199
0x180032150  mov     [rsp+48h+var_18], rax; pSacl
0x180032155  xor     r9d, r9d; psidOwner
0x180032158  mov     [rsp+48h+pDacl], 0; pDacl
0x180032161  mov     rcx, rbx; handle
0x180032164  mov     [rsp+48h+psidGroup], 0; psidGroup
0x18003216d  lea     edx, [r9+4]; ObjectType
0x180032171  lea     r8d, [rdx+7Ch]; SecurityInfo
0x180032175  call    cs:__imp_SetSecurityInfo
0x18003217b  mov     ebx, eax
0x18003217d  test    eax, eax
0x18003217f  jz      short loc_180032195
0x180032181  jle     short loc_18003218C
0x180032183  movzx   ebx, ax
0x180032186  or      ebx, 80070000h
0x18003218c  lea     rdx, aProtectionutil_2; "ProtectionUtil - error assigning SACL t"...
0x180032193  jmp     short loc_1800321A5
0x180032195  xor     ebx, ebx
0x180032197  jmp     short loc_1800321B2
0x180032199  mov     ebx, 80070538h
0x18003219e  lea     rdx, aProtectionutil_1; "ProtectionUtil - error verifying that s"...
0x1800321a5  mov     r8d, ebx
0x1800321a8  mov     ecx, 2; unsigned __int8
0x1800321ad  call    ?LogLevelW@@YAXEPEBGZZ; LogLevelW(uchar,ushort const *,...)
0x1800321b2  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x1800321b6  call    cs:__imp_LocalFree
0x1800321bc  mov     eax, ebx
0x1800321be  jmp     short loc_1800321C5
0x1800321c0  mov     eax, 80070057h
0x1800321c5  add     rsp, 48h
0x1800321c9  pop     rbx
0x1800321ca  pop     rbp
0x1800321cb  retn
```
