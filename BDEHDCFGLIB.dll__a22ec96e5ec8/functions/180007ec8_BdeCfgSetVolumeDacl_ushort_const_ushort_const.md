# BdeCfgSetVolumeDacl(ushort const *,ushort const *)

- ea: `0x180007ec8`
- end: `0x180008018`
- name: `?BdeCfgSetVolumeDacl@@YAJPEBG0@Z`
- size: `336`
- prototype: `__int64 __fastcall(const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x1800101a0`

## callees

- `0x180006c30`
- `0x180007ec8`
- `0x1800135c0`

## import_xrefs

- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180007f84`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x180007f84`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007f4f`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180007f4f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180007fca`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180007fca`
- `KERNEL32!GetLastError` at `0x180007f59`
- `KERNEL32!GetLastError` at `0x180007f59`
- `KERNEL32!LocalFree` at `0x180007fe9`
- `KERNEL32!LocalFree` at `0x180007fe9`

## pseudocode

```c
__int64 __fastcall BdeCfgSetVolumeDacl(const unsigned __int16 *a1, const unsigned __int16 *a2)
{
  signed int v2; // ebx
  signed int LastError; // eax
  WINBOOL bDaclPresent; // [rsp+40h] [rbp-C0h] BYREF
  WINBOOL bDaclDefaulted; // [rsp+44h] [rbp-BCh] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+48h] [rbp-B8h] BYREF
  PACL pDacl; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pObjectName[264]; // [rsp+60h] [rbp-A0h] BYREF

  bDaclPresent = 0;
  bDaclDefaulted = 0;
  SecurityDescriptor = 0;
  pDacl = 0;
  if ( !a1 )
    return 2147500035LL;
  v2 = StringCchPrintfW(pObjectName, 0x104u, L"%s\\", a1);
  if ( v2 >= 0 )
  {
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464G:S-1-5-80-956008885-3418522649-1831038044-18"
            "53292631-2271478464D:P(A;CI;GA;;;S-1-5-80-956008885-3418522649-1831038044-1853292631-2271478464)(A;;0x1301bf"
            ";;;SY)(A;IOCIOI;GA;;;SY)(A;;0x1301bf;;;BA)(A;IOCIOI;GA;;;BA)(A;CIOI;GRGX;;;BU)(A;OICIIO;GA;;;CO)",
           1u,
           &SecurityDescriptor,
           0)
      && GetSecurityDescriptorDacl(SecurityDescriptor, &bDaclPresent, &pDacl, &bDaclDefaulted) )
    {
      if ( !bDaclPresent || bDaclDefaulted )
      {
        v2 = -1063256039;
        goto LABEL_13;
      }
      LastError = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x80000004, 0, 0, pDacl, 0);
      if ( LastError )
      {
        if ( LastError <= 0 )
        {
          v2 = LastError;
          goto LABEL_13;
        }
        goto LABEL_5;
      }
    }
    else
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
LABEL_5:
        v2 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_13:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180007ec8  mov     [rsp-8+arg_8], rbx
0x180007ecd  push    rbp
0x180007ece  lea     rbp, [rsp-180h]
0x180007ed6  sub     rsp, 280h
0x180007edd  mov     rax, cs:__security_cookie
0x180007ee4  xor     rax, rsp
0x180007ee7  mov     [rbp+180h+var_10], rax
0x180007eee  mov     [rsp+280h+bDaclPresent], 0
0x180007ef6  mov     [rsp+280h+bDaclDefaulted], 0
0x180007efe  mov     [rsp+280h+SecurityDescriptor], 0
0x180007f07  mov     [rsp+280h+pDacl], 0
0x180007f10  test    rcx, rcx
0x180007f13  jz      loc_180007FF3
0x180007f19  mov     r9, rcx
0x180007f1c  lea     r8, aS; "%s\\"
0x180007f23  lea     rcx, [rsp+280h+pObjectName]; unsigned __int16 *
0x180007f28  mov     edx, 104h; unsigned __int64
0x180007f2d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180007f32  mov     ebx, eax
0x180007f34  test    eax, eax
0x180007f36  js      loc_180007FDF
0x180007f3c  xor     r9d, r9d; SecurityDescriptorSize
0x180007f3f  lea     r8, [rsp+280h+SecurityDescriptor]; SecurityDescriptor
0x180007f44  lea     rcx, StringSecurityDescriptor; "O:S-1-5-80-956008885-3418522649-1831038"...
0x180007f4b  lea     edx, [r9+1]; StringSDRevision
0x180007f4f  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180007f55  test    eax, eax
0x180007f57  jnz     short loc_180007F70
0x180007f59  call    cs:__imp_GetLastError
0x180007f5f  mov     ebx, eax
0x180007f61  test    eax, eax
0x180007f63  jle     short loc_180007FDF
0x180007f65  movzx   ebx, ax
0x180007f68  or      ebx, 80070000h
0x180007f6e  jmp     short loc_180007FDF
0x180007f70  mov     rcx, [rsp+280h+SecurityDescriptor]; pSecurityDescriptor
0x180007f75  lea     r9, [rsp+280h+bDaclDefaulted]; lpbDaclDefaulted
0x180007f7a  lea     r8, [rsp+280h+pDacl]; pDacl
0x180007f7f  lea     rdx, [rsp+280h+bDaclPresent]; lpbDaclPresent
0x180007f84  call    cs:__imp_GetSecurityDescriptorDacl
0x180007f8a  test    eax, eax
0x180007f8c  jz      short loc_180007F59
0x180007f8e  cmp     [rsp+280h+bDaclPresent], 0
0x180007f93  jz      short loc_180007FDA
0x180007f95  cmp     [rsp+280h+bDaclDefaulted], 0
0x180007f9a  jnz     short loc_180007FDA
0x180007f9c  mov     rax, [rsp+280h+pDacl]
0x180007fa1  lea     rcx, [rsp+280h+pObjectName]; pObjectName
0x180007fa6  xor     r9d, r9d; psidOwner
0x180007fa9  mov     [rsp+280h+pSacl], 0; pSacl
0x180007fb2  mov     [rsp+280h+var_258], rax; pDacl
0x180007fb7  mov     r8d, 80000004h; SecurityInfo
0x180007fbd  mov     [rsp+280h+psidGroup], 0; psidGroup
0x180007fc6  lea     edx, [r9+1]; ObjectType
0x180007fca  call    cs:__imp_SetNamedSecurityInfoW
0x180007fd0  test    eax, eax
0x180007fd2  jz      short loc_180007FDF
0x180007fd4  jg      short loc_180007F65
0x180007fd6  mov     ebx, eax
0x180007fd8  jmp     short loc_180007FDF
0x180007fda  mov     ebx, 0C0A00019h
0x180007fdf  mov     rcx, [rsp+280h+SecurityDescriptor]; hMem
0x180007fe4  test    rcx, rcx
0x180007fe7  jz      short loc_180007FEF
0x180007fe9  call    cs:__imp_LocalFree
0x180007fef  mov     eax, ebx
0x180007ff1  jmp     short loc_180007FF8
0x180007ff3  mov     eax, 80004003h
0x180007ff8  mov     rcx, [rbp+180h+var_10]
0x180007fff  xor     rcx, rsp; StackCookie
0x180008002  call    __security_check_cookie
0x180008007  mov     rbx, [rsp+280h+arg_8]
0x18000800f  add     rsp, 280h
0x180008016  pop     rbp
0x180008017  retn
```
