# WerPluginAdjustAppContainerAccessToKey(HKEY__ *,_ACCESS_MODE,ulong)

- ea: `0x140054aa0`
- end: `0x140054c6d`
- name: `?WerPluginAdjustAppContainerAccessToKey@@YAJPEAUHKEY__@@W4_ACCESS_MODE@@K@Z`
- size: `461`
- prototype: `__int64 __fastcall(HKEY hKey, enum _ACCESS_MODE, unsigned int)`
- caller_count: `4`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x140049364`
- `0x14004aca8`
- `0x14004cbac`
- `0x14005463c`

## callees

- `0x140002470`
- `0x140002728`
- `0x140004198`
- `0x140054aa0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140054c20`
- `api-ms-win-core-registry-l1-1-0!RegSetKeySecurity` at `0x140054c20`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140054b64`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140054ba1`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140054b64`
- `api-ms-win-core-registry-l1-1-0!RegGetKeySecurity` at `0x140054ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054afb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140054afb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140054af1`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x140054af1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054c39`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054bcc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140054c39`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x140054c06`
- `api-ms-win-security-trustee-l1-1-0!BuildSecurityDescriptorW` at `0x140054c06`

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
  HLOCAL v11; // rcx
  DWORD cbSid; // [rsp+50h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-51h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfAccessEntries; // [rsp+60h] [rbp-49h] BYREF
  _BYTE pSid[80]; // [rsp+90h] [rbp-19h] BYREF

  cbSid = 68;
  pOldSD = 0;
  hMem = 0;
  memset(&pListOfAccessEntries, 0, sizeof(pListOfAccessEntries));
  if ( !CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, pSid, &cbSid) )
  {
    LastError = GetLastError();
    KeySecurity = LastError;
    v9 = LastError <= 0;
    goto LABEL_3;
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
      goto LABEL_20;
    }
    KeySecurity = RegGetKeySecurity(hKey, 4u, v10, &cbSid);
  }
  if ( KeySecurity )
  {
    if ( KeySecurity <= 0 )
    {
LABEL_6:
      if ( KeySecurity >= 0 )
        KeySecurity = -2147467259;
      goto LABEL_20;
    }
    KeySecurity = (unsigned __int16)KeySecurity;
LABEL_5:
    KeySecurity |= 0x80070000;
    goto LABEL_6;
  }
  v11 = hMem;
  hMem = 0;
  if ( v11 )
    LocalFree(v11);
  LastError = BuildSecurityDescriptorW(0, 0, 1u, &pListOfAccessEntries, 0, 0, pOldSD, &cbSid, &hMem);
  KeySecurity = LastError;
  v9 = LastError <= 0;
  if ( LastError
    || (LastError = RegSetKeySecurity(hKey, 4u, hMem), KeySecurity = LastError, v9 = LastError <= 0, LastError) )
  {
LABEL_3:
    if ( v9 )
      goto LABEL_6;
    KeySecurity = (unsigned __int16)LastError;
    goto LABEL_5;
  }
LABEL_20:
  if ( hMem )
    LocalFree(hMem);
  if ( pOldSD )
    operator delete(pOldSD, v7);
  return (unsigned int)KeySecurity;
}

```

## disassembly

```asm
0x140054aa0  mov     [rsp-8+arg_8], rbx
0x140054aa5  push    rbp
0x140054aa6  push    rsi
0x140054aa7  push    rdi
0x140054aa8  lea     rbp, [rsp-47h]
0x140054aad  sub     rsp, 0F0h
0x140054ab4  mov     rax, cs:__security_cookie
0x140054abb  xor     rax, rsp
0x140054abe  mov     [rbp+57h+var_20], rax
0x140054ac2  xorps   xmm0, xmm0
0x140054ac5  mov     [rbp+57h+cbSid], 44h ; 'D'
0x140054acc  xor     ebx, ebx
0x140054ace  lea     r9, [rbp+57h+cbSid]; cbSid
0x140054ad2  mov     edi, r8d
0x140054ad5  mov     [rbp+57h+hMem], rbx
0x140054ad9  mov     rsi, rcx
0x140054adc  lea     r8, [rbp+57h+pSid]; pSid
0x140054ae0  xor     edx, edx; DomainSid
0x140054ae2  lea     ecx, [rbx+54h]; WellKnownSidType
0x140054ae5  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x140054ae9  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x140054aed  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x140054af1  call    cs:__imp_CreateWellKnownSid
0x140054af7  test    eax, eax
0x140054af9  jnz     short loc_140054B1F
0x140054afb  call    cs:__imp_GetLastError
0x140054b01  mov     edi, eax
0x140054b03  test    eax, eax
0x140054b05  jle     short loc_140054B10
0x140054b07  movzx   edi, ax
0x140054b0a  or      edi, 80070000h
0x140054b10  test    edi, edi
0x140054b12  mov     eax, 80004005h
0x140054b17  cmovns  edi, eax
0x140054b1a  jmp     loc_140054C30
0x140054b1f  xorps   xmm0, xmm0
0x140054b22  lea     rax, [rbp+57h+pSid]
0x140054b26  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.grfAccessPermissions], xmm0
0x140054b2a  xor     r8d, r8d; pSecurityDescriptor
0x140054b2d  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x140054b31  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], xmm0
0x140054b35  mov     rcx, rsi; hKey
0x140054b38  mov     [rbp+57h+pListOfAccessEntries.grfAccessPermissions], edi
0x140054b3b  movups  xmmword ptr [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], xmm0
0x140054b3f  lea     edx, [r8+4]; SecurityInformation
0x140054b43  mov     [rbp+57h+pListOfAccessEntries.grfAccessMode], 1
0x140054b4a  mov     [rbp+57h+pListOfAccessEntries.grfInheritance], 3
0x140054b51  mov     [rbp+57h+pListOfAccessEntries.Trustee.pMultipleTrustee], rbx
0x140054b55  mov     qword ptr [rbp+57h+pListOfAccessEntries.Trustee.MultipleTrusteeOperation], rbx
0x140054b59  mov     [rbp+57h+pListOfAccessEntries.Trustee.TrusteeType], 5
0x140054b60  mov     [rbp+57h+pListOfAccessEntries.Trustee.ptstrName], rax
0x140054b64  call    cs:__imp_RegGetKeySecurity
0x140054b6a  mov     edi, eax
0x140054b6c  cmp     eax, 7Ah ; 'z'
0x140054b6f  jnz     short loc_140054BA9
0x140054b71  mov     ecx, [rbp+57h+cbSid]; unsigned __int64
0x140054b74  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140054b7b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140054b80  mov     rbx, rax
0x140054b83  test    rax, rax
0x140054b86  jnz     short loc_140054B92
0x140054b88  mov     edi, 8007000Eh
0x140054b8d  jmp     loc_140054C30
0x140054b92  lea     r9, [rbp+57h+cbSid]; lpcbSecurityDescriptor
0x140054b96  mov     r8, rax; pSecurityDescriptor
0x140054b99  mov     edx, 4; SecurityInformation
0x140054b9e  mov     rcx, rsi; hKey
0x140054ba1  call    cs:__imp_RegGetKeySecurity
0x140054ba7  mov     edi, eax
0x140054ba9  test    edi, edi
0x140054bab  jz      short loc_140054BBB
0x140054bad  jle     loc_140054B10
0x140054bb3  movzx   edi, di
0x140054bb6  jmp     loc_140054B0A
0x140054bbb  mov     rcx, [rbp+57h+hMem]; hMem
0x140054bbf  mov     [rbp+57h+hMem], 0
0x140054bc7  test    rcx, rcx
0x140054bca  jz      short loc_140054BD2
0x140054bcc  call    cs:__imp_LocalFree
0x140054bd2  lea     rax, [rbp+57h+hMem]
0x140054bd6  xor     edx, edx; pGroup
0x140054bd8  mov     [rsp+100h+pNewSD], rax; pNewSD
0x140054bdd  lea     r9, [rbp+57h+pListOfAccessEntries]; pListOfAccessEntries
0x140054be1  lea     rax, [rbp+57h+cbSid]
0x140054be5  xor     ecx, ecx; pOwner
0x140054be7  mov     [rsp+100h+pSizeNewSD], rax; pSizeNewSD
0x140054bec  mov     [rsp+100h+pOldSD], rbx; pOldSD
0x140054bf1  lea     r8d, [rdx+1]; cCountOfAccessEntries
0x140054bf5  mov     [rsp+100h+pListOfAuditEntries], 0; pListOfAuditEntries
0x140054bfe  mov     [rsp+100h+cCountOfAuditEntries], 0; cCountOfAuditEntries
0x140054c06  call    cs:__imp_BuildSecurityDescriptorW
0x140054c0c  mov     edi, eax
0x140054c0e  test    eax, eax
0x140054c10  jnz     loc_140054B05
0x140054c16  mov     r8, [rbp+57h+hMem]; pSecurityDescriptor
0x140054c1a  lea     edx, [rax+4]; SecurityInformation
0x140054c1d  mov     rcx, rsi; hKey
0x140054c20  call    cs:__imp_RegSetKeySecurity
0x140054c26  mov     edi, eax
0x140054c28  test    eax, eax
0x140054c2a  jnz     loc_140054B05
0x140054c30  mov     rcx, [rbp+57h+hMem]; hMem
0x140054c34  test    rcx, rcx
0x140054c37  jz      short loc_140054C3F
0x140054c39  call    cs:__imp_LocalFree
0x140054c3f  test    rbx, rbx
0x140054c42  jz      short loc_140054C4C
0x140054c44  mov     rcx, rbx; void *
0x140054c47  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140054c4c  mov     eax, edi
0x140054c4e  mov     rcx, [rbp+57h+var_20]
0x140054c52  xor     rcx, rsp; StackCookie
0x140054c55  call    __security_check_cookie
0x140054c5a  mov     rbx, [rsp+100h+arg_8]
0x140054c62  add     rsp, 0F0h
0x140054c69  pop     rdi
0x140054c6a  pop     rsi
0x140054c6b  pop     rbp
0x140054c6c  retn
```
