# WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)

- ea: `0x1400584c0`
- end: `0x1400586a6`
- name: `?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z`
- size: `486`
- prototype: `__int64 __fastcall(HKEY hKey, enum _ACCESS_MODE, unsigned int)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x14004c6e0`
- `0x14004e104`
- `0x14005014c`
- `0x140058034`

## callees

- `0x140002490`
- `0x140002748`
- `0x1400041e8`
- `0x1400167a4`
- `0x1400584c0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14005864c`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x14005864c`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140058590`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1400585d3`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140058590`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x1400585d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058521`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140058521`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140058511`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140058511`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005866b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14005866b`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x14005862c`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x14005862c`

## pseudocode

```c
__int64 __fastcall WerPluginAdjustAppContainerAccessToKey(HKEY hKey, enum _ACCESS_MODE a2, DWORD a3)
{
  void *pOldSD; // rbx
  signed int LastError; // eax
  const struct std::nothrow_t *v7; // rdx
  LSTATUS KeySecurity; // edi
  bool v9; // cc
  void *v10; // rax
  PSECURITY_DESCRIPTOR *pNewSD; // rax
  DWORD cbSid; // [rsp+50h] [rbp-59h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-51h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfAccessEntries; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-19h] BYREF

  cbSid = 68;
  pOldSD = 0;
  pSecurityDescriptor = 0;
  memset(&pListOfAccessEntries, 0, sizeof(pListOfAccessEntries));
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    KeySecurity = LastError;
    v9 = LastError <= 0;
LABEL_3:
    if ( v9 )
      goto LABEL_6;
    KeySecurity = (unsigned __int16)LastError;
    goto LABEL_5;
  }
  memset(&pListOfAccessEntries.grfInheritance + 1, 0, 20);
  pListOfAccessEntries.grfAccessPermissions = a3;
  *((_DWORD *)&pListOfAccessEntries.Trustee.TrusteeType + 1) = 0;
  pListOfAccessEntries.grfAccessMode = GRANT_ACCESS;
  pListOfAccessEntries.grfInheritance = 3;
  pListOfAccessEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  pListOfAccessEntries.Trustee.ptstrName = (LPWCH)pSid;
  KeySecurity = RegGetKeySecurity(hKey, 4u, 0, &cbSid);
  if ( KeySecurity == 122 )
  {
    v10 = operator new[](cbSid, (const struct std::nothrow_t *)&std::nothrow);
    pOldSD = v10;
    if ( !v10 )
    {
      KeySecurity = -2147024882;
      goto LABEL_18;
    }
    KeySecurity = RegGetKeySecurity(hKey, 4u, v10, &cbSid);
  }
  if ( !KeySecurity )
  {
    pNewSD = (PSECURITY_DESCRIPTOR *)___replace_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___utl__YAPEAPEAXAEAV__unique_ptr_XU__generic_delete_XU__generic_deallocate__MP6APEAXPEAX_Z1_LocalFree__YAPEAX0_ZPEAX_tlx___tlx___0__Z(&pSecurityDescriptor);
    LastError = BuildSecurityDescriptorW(0, 0, 1u, &pListOfAccessEntries, 0, 0, pOldSD, &cbSid, pNewSD);
    KeySecurity = LastError;
    v9 = LastError <= 0;
    if ( !LastError )
    {
      LastError = RegSetKeySecurity(hKey, 4u, pSecurityDescriptor);
      KeySecurity = LastError;
      v9 = LastError <= 0;
      if ( !LastError )
        goto LABEL_18;
    }
    goto LABEL_3;
  }
  if ( KeySecurity > 0 )
  {
    KeySecurity = (unsigned __int16)KeySecurity;
LABEL_5:
    KeySecurity |= 0x80070000;
  }
LABEL_6:
  if ( KeySecurity >= 0 )
    KeySecurity = -2147467259;
LABEL_18:
  if ( pSecurityDescriptor )
    LocalFree(pSecurityDescriptor);
  if ( pOldSD )
    operator delete(pOldSD, v7);
  return (unsigned int)KeySecurity;
}

```

## disassembly

```asm
0x1400584c0  mov     [rsp-8+arg_8], rbx
0x1400584c5  push    rbp
0x1400584c6  push    rsi
0x1400584c7  push    rdi
0x1400584c8  lea     rbp, [rsp-47h]
0x1400584cd  sub     rsp, 0F0h
0x1400584d4  mov     rax, cs:__security_cookie
0x1400584db  xor     rax, rsp
0x1400584de  mov     [rbp+57h+var_20], rax
0x1400584e2  xorps   xmm0, xmm0
0x1400584e5  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1400584ec  xor     ebx, ebx
0x1400584ee  lea     r9, [rbp+57h+cbSid]; cbSid
0x1400584f2  mov     edi, r8d
0x1400584f5  mov     [rbp+57h+pSecurityDescriptor], rbx
0x1400584f9  mov     rsi, rcx
0x1400584fc  lea     r8, [rbp+57h+pSid]; pSid
0x140058500  xor     edx, edx; DomainSid
0x140058502  lea     ecx, [rbx+54h]; WellKnownSidType
0x140058505  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x140058509  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x14005850d  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x140058511  call    cs:__imp_CreateWellKnownSid
0x140058518  nop     dword ptr [rax+rax+00h]
0x14005851d  test    eax, eax
0x14005851f  jnz     short loc_14005854B
0x140058521  call    cs:__imp_GetLastError
0x140058528  nop     dword ptr [rax+rax+00h]
0x14005852d  mov     edi, eax
0x14005852f  test    eax, eax
0x140058531  jle     short loc_14005853C
0x140058533  movzx   edi, ax
0x140058536  or      edi, 80070000h
0x14005853c  test    edi, edi
0x14005853e  mov     eax, 80004005h
0x140058543  cmovns  edi, eax
0x140058546  jmp     loc_140058662
0x14005854b  xorps   xmm0, xmm0
0x14005854e  lea     rax, [rbp+57h+pSid]
0x140058552  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x140058556  xor     r8d, r8d; pSecurityDescriptor
0x140058559  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x14005855d  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x140058561  mov     rcx, rsi; hKey
0x140058564  mov     [rbp+57h+pListOfAccessEntries.grfAccessPermissions], edi
0x140058567  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x14005856b  lea     edx, [r8+4]; SecurityInformation
0x14005856f  mov     [rbp+57h+pListOfAccessEntries.grfAccessMode], 1
0x140058576  mov     [rbp+57h+pListOfAccessEntries.grfInheritance], 3
0x14005857d  mov     [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], rbx
0x140058581  mov     qword ptr [rbp+57h+pListOfAccessEntries.Trustee.MultipleTrusteeOperation], rbx
0x140058585  mov     [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], 5
0x14005858c  mov     [rbp+57h+pListOfAccessEntries.Trustee.ptstrName], rax
0x140058590  call    cs:__imp_RegGetKeySecurity
0x140058597  nop     dword ptr [rax+rax+00h]
0x14005859c  mov     edi, eax
0x14005859e  cmp     eax, 7Ah ; 'z'
0x1400585a1  jnz     short loc_1400585E1
0x1400585a3  mov     ecx, [rbp+57h+cbSid]; unsigned __int64
0x1400585a6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1400585ad  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1400585b2  mov     rbx, rax
0x1400585b5  test    rax, rax
0x1400585b8  jnz     short loc_1400585C4
0x1400585ba  mov     edi, 8007000Eh
0x1400585bf  jmp     loc_140058662
0x1400585c4  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x1400585c8  mov     r8, rax; pSecurityDescriptor
0x1400585cb  mov     edx, 4; SecurityInformation
0x1400585d0  mov     rcx, rsi; hKey
0x1400585d3  call    cs:__imp_RegGetKeySecurity
0x1400585da  nop     dword ptr [rax+rax+00h]
0x1400585df  mov     edi, eax
0x1400585e1  test    edi, edi
0x1400585e3  jz      short loc_1400585F3
0x1400585e5  jle     loc_14005853C
0x1400585eb  movzx   edi, di
0x1400585ee  jmp     loc_140058536
0x1400585f3  lea     rcx, [rbp+57h+pSecurityDescriptor]
0x1400585f7  call    ??$replace@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@utl@@YAPEAPEAXAEAV?$unique_ptr@XU?$generic_delete@XU?$generic_deallocate@$MP6APEAXPEAX@Z1?LocalFree@@YAPEAX0@ZPEAX@tlx@@@tlx@@@0@@Z
0x1400585fc  mov     [rsp+100h+pNewSD], rax; pNewSD
0x140058601  lea     r9, [rbp+57h+pListOfAccessEntries]; pListOfAccessEntries
0x140058605  xor     edx, edx; pGroup
0x140058607  lea     rax, [rbp+57h+cbSid]
0x14005860b  mov     [rsp+100h+pSizeNewSD], rax; pSizeNewSD
0x140058610  xor     ecx, ecx; pOwner
0x140058612  mov     [rsp+100h+pOldSD], rbx; pOldSD
0x140058617  mov     [rsp+100h+pListOfAuditEntries], 0; pListOfAuditEntries
0x140058620  lea     r8d, [rdx+1]; cCountOfAccessEntries
0x140058624  mov     [rsp+100h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x14005862c  call    cs:__imp_BuildSecurityDescriptorW
0x140058633  nop     dword ptr [rax+rax+00h]
0x140058638  mov     edi, eax
0x14005863a  test    eax, eax
0x14005863c  jnz     loc_140058531
0x140058642  mov     r8, [rbp+57h+pSecurityDescriptor]; pSecurityDescriptor
0x140058646  lea     edx, [rax+4]; SecurityInformation
0x140058649  mov     rcx, rsi; hKey
0x14005864c  call    cs:__imp_RegSetKeySecurity
0x140058653  nop     dword ptr [rax+rax+00h]
0x140058658  mov     edi, eax
0x14005865a  test    eax, eax
0x14005865c  jnz     loc_140058531
0x140058662  mov     rcx, [rbp+57h+pSecurityDescriptor]; hMem
0x140058666  test    rcx, rcx
0x140058669  jz      short loc_140058677
0x14005866b  call    cs:__imp_LocalFree
0x140058672  nop     dword ptr [rax+rax+00h]
0x140058677  test    rbx, rbx
0x14005867a  jz      short loc_140058684
0x14005867c  mov     rcx, rbx; void *
0x14005867f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140058684  mov     eax, edi
0x140058686  mov     rcx, [rbp+57h+var_20]
0x14005868a  xor     rcx, rsp; StackCookie
0x14005868d  call    __security_check_cookie
0x140058692  mov     rbx, [rsp+100h+arg_8]
0x14005869a  add     rsp, 0F0h
0x1400586a1  pop     rdi
0x1400586a2  pop     rsi
0x1400586a3  pop     rbp
0x1400586a4  retn
```
