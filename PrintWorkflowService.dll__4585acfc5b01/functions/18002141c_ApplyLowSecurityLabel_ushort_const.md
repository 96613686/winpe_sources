# ApplyLowSecurityLabel(ushort const *)

- ea: `0x18002141c`
- end: `0x180021567`
- name: `?ApplyLowSecurityLabel@@YAJPEBG@Z`
- size: `331`
- prototype: `__int64 __fastcall(LPWSTR pObjectName)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800239c8`
- `0x180042dc8`

## callees

- `0x180003ca0`
- `0x1800127c4`
- `0x1800213cc`
- `0x18002141c`
- `0x180023664`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180021484`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180021484`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800214b6`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorSacl` at `0x1800214b6`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800214ea`
- `api-ms-win-security-provider-l1-1-0!SetNamedSecurityInfoW` at `0x1800214ea`

## string_xrefs

- `0x18002152c`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x18002153d`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`
- `0x180021554`: `onecoreuap\printscan\print\workflow\broker\common_lib\workflowbrokerutilities.cpp`

## pseudocode

```c
__int64 __fastcall ApplyLowSecurityLabel(LPWSTR pObjectName)
{
  const char *v2; // r9
  const char *v3; // r9
  DWORD v4; // eax
  unsigned int psidGroup; // [rsp+20h] [rbp-68h]
  WINBOOL bSaclPresent; // [rsp+40h] [rbp-48h] BYREF
  WINBOOL bSaclDefaulted; // [rsp+44h] [rbp-44h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+48h] [rbp-40h] BYREF
  PACL pSacl; // [rsp+50h] [rbp-38h] BYREF
  _OWORD v11[2]; // [rsp+58h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v11[0] = *(_OWORD *)L"S:(ML;;NW;;;LW)";
  v11[1] = *(_OWORD *)L"W;;;LW)";
  pSacl = 0;
  bSaclPresent = 0;
  bSaclDefaulted = 0;
  pSecurityDescriptor = 0;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW((LPCWSTR)v11, 1u, &pSecurityDescriptor, 0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x21D,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v2);
  if ( !GetSecurityDescriptorSacl(pSecurityDescriptor, &bSaclPresent, &pSacl, &bSaclDefaulted) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x220,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      v3);
  v4 = SetNamedSecurityInfoW(pObjectName, SE_FILE_OBJECT, 0x10u, 0, 0, 0, pSacl);
  if ( v4 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x225,
      (unsigned int)"onecoreuap\\printscan\\print\\workflow\\broker\\common_lib\\workflowbrokerutilities.cpp",
      (const char *)v4,
      psidGroup);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pSecurityDescriptor);
  return 0;
}

```

## disassembly

```asm
0x18002141c  mov     r11, rsp
0x18002141f  mov     [r11+10h], rbx
0x180021423  push    rdi
0x180021424  sub     rsp, 80h
0x18002142b  mov     rax, cs:__security_cookie
0x180021432  xor     rax, rsp
0x180021435  mov     [rsp+88h+var_10], rax
0x18002143a  mov     rdi, rcx
0x18002143d  movups  xmm0, xmmword ptr cs:aSMlNwLw; "S:(ML;;NW;;;LW)"
0x180021444  movups  [rsp+88h+var_30], xmm0
0x180021449  movups  xmm1, xmmword ptr cs:aSMlNwLw+10h; "W;;;LW)"
0x180021450  movups  [rsp+88h+var_20], xmm1
0x180021455  mov     qword ptr [r11-38h], 0
0x18002145d  mov     [rsp+88h+bSaclPresent], 0
0x180021465  mov     [rsp+88h+bSaclDefaulted], 0
0x18002146d  mov     qword ptr [r11-40h], 0
0x180021475  xor     r9d, r9d; SecurityDescriptorSize
0x180021478  lea     r8, [r11-40h]; SecurityDescriptor
0x18002147c  lea     edx, [r9+1]; StringSDRevision
0x180021480  lea     rcx, [r11-30h]; StringSecurityDescriptor
0x180021484  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18002148a  mov     rcx, [rsp+88h]; this
0x180021492  test    eax, eax
0x180021494  jz      loc_18002152C
0x18002149a  mov     rbx, [rsp+88h]
0x1800214a2  lea     r9, [rsp+88h+bSaclDefaulted]; lpbSaclDefaulted
0x1800214a7  lea     r8, [rsp+88h+pSacl]; pSacl
0x1800214ac  lea     rdx, [rsp+88h+bSaclPresent]; lpbSaclPresent
0x1800214b1  mov     rcx, [rsp+88h+pSecurityDescriptor]; pSecurityDescriptor
0x1800214b6  call    cs:__imp_GetSecurityDescriptorSacl
0x1800214bc  test    eax, eax
0x1800214be  jz      short loc_18002153D
0x1800214c0  mov     rax, [rsp+88h+pSacl]
0x1800214c5  mov     [rsp+88h+var_58], rax; pSacl
0x1800214ca  mov     [rsp+88h+pDacl], 0; pDacl
0x1800214d3  mov     [rsp+88h+psidGroup], 0; unsigned int
0x1800214dc  xor     r9d, r9d; psidOwner
0x1800214df  lea     edx, [r9+1]; ObjectType
0x1800214e3  lea     r8d, [r9+10h]; SecurityInfo
0x1800214e7  mov     rcx, rdi; pObjectName
0x1800214ea  call    cs:__imp_SetNamedSecurityInfoW
0x1800214f0  mov     rcx, [rsp+88h]; this
0x1800214f8  test    eax, eax
0x1800214fa  jnz     short loc_180021551
0x1800214fc  lea     rcx, [rsp+88h+pSecurityDescriptor]
0x180021501  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180021506  xor     eax, eax
0x180021508  jmp     short loc_18002150E
0x18002150a  mov     eax, [rsp+88h+bSaclPresent]
0x18002150e  mov     rcx, [rsp+88h+var_10]
0x180021513  xor     rcx, rsp; StackCookie
0x180021516  call    __security_check_cookie
0x18002151b  mov     rbx, [rsp+88h+arg_8]
0x180021523  add     rsp, 80h
0x18002152a  pop     rdi
0x18002152b  retn
0x18002152c  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021533  mov     edx, 21Dh; void *
0x180021538  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002153d  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x180021544  mov     edx, 220h; void *
0x180021549  mov     rcx, rbx; this
0x18002154c  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180021551  mov     r9d, eax; char *
0x180021554  lea     r8, aOnecoreuapPrin_29; "onecoreuap\\printscan\\print\\workflow"...
0x18002155b  mov     edx, 225h; void *
0x180021560  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
