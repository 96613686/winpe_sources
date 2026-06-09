# SpeechPlatform::Settings::AddAllApplicationPackagesACL(ushort const * const)

- ea: `0x140014388`
- end: `0x140014439`
- name: `?AddAllApplicationPackagesACL@Settings@SpeechPlatform@@YAJQEBG@Z`
- size: `177`
- prototype: `__int64 __fastcall(LPWSTR pObjectName, const unsigned __int16 *const)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140013588`

## callees

- `0x140002d30`
- `0x140014388`
- `0x140017604`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400143bf`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1400143bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400143c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400143c9`

## pseudocode

```c
signed int __fastcall SpeechPlatform::Settings::AddAllApplicationPackagesACL(
        LPWSTR pObjectName,
        const unsigned __int16 *const a2)
{
  struct _EXPLICIT_ACCESS_W *v3; // r8
  signed int result; // eax
  bool v5; // sf
  DWORD cbSid; // [rsp+20h] [rbp-49h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+28h] [rbp-41h] BYREF
  _BYTE pSid[80]; // [rsp+60h] [rbp-9h] BYREF

  cbSid = 68;
  if ( CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, pSid, &cbSid) )
    goto LABEL_5;
  result = GetLastError();
  v5 = result < 0;
  if ( result > 0 )
  {
    result = (unsigned __int16)result | 0x80070000;
    v5 = result < 0;
  }
  if ( !v5 )
  {
LABEL_5:
    *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 5;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 2;
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
    memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
    return SpeechPlatform::Settings::Details::RegKeyAddToDacl(pObjectName, &pListOfExplicitEntries, v3);
  }
  return result;
}

```

## disassembly

```asm
0x140014388  mov     [rsp-8+arg_8], rbx
0x14001438d  push    rbp
0x14001438e  lea     rbp, [rsp-57h]
0x140014393  sub     rsp, 0C0h
0x14001439a  mov     rax, cs:__security_cookie
0x1400143a1  xor     rax, rsp
0x1400143a4  mov     [rbp+57h+var_10], rax
0x1400143a8  xor     edx, edx; DomainSid
0x1400143aa  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1400143b1  mov     rbx, rcx
0x1400143b4  lea     r9, [rbp+57h+cbSid]; cbSid
0x1400143b8  lea     r8, [rbp+57h+pSid]; pSid
0x1400143bc  lea     ecx, [rdx+54h]; WellKnownSidType
0x1400143bf  call    cs:__imp_CreateWellKnownSid
0x1400143c5  test    eax, eax
0x1400143c7  jnz     short loc_1400143DF
0x1400143c9  call    cs:__imp_GetLastError
0x1400143cf  test    eax, eax
0x1400143d1  jle     short loc_1400143DD
0x1400143d3  movzx   eax, ax
0x1400143d6  or      eax, 80070000h
0x1400143db  test    eax, eax
0x1400143dd  js      short loc_14001441C
0x1400143df  mov     eax, 2
0x1400143e4  mov     qword ptr [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1400143ec  mov     [rbp+57h+pListOfExplicitEntries.grfAccessMode], eax
0x1400143ef  lea     rdx, [rbp+57h+pListOfExplicitEntries]; pListOfExplicitEntries
0x1400143f3  mov     [rbp+57h+pListOfExplicitEntries.grfInheritance], eax
0x1400143f6  xorps   xmm0, xmm0
0x1400143f9  lea     rax, [rbp+57h+pSid]
0x1400143fd  mov     [rbp+57h+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x140014404  mov     rcx, rbx; pObjectName
0x140014407  mov     [rbp+57h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x14001440b  movdqu  xmmword ptr [rbp+57h+pListOfExplicitEntries+0Ch], xmm0
0x140014410  mov     [rbp+57h+pListOfExplicitEntries.Trustee.TrusteeForm], 0
0x140014417  call    ?RegKeyAddToDacl@Details@Settings@SpeechPlatform@@YAJPEBGAEAU_EXPLICIT_ACCESS_W@@@Z; SpeechPlatform::Settings::Details::RegKeyAddToDacl(ushort const *,_EXPLICIT_ACCESS_W &)
0x14001441c  mov     rcx, [rbp+57h+var_10]
0x140014420  xor     rcx, rsp; StackCookie
0x140014423  call    __security_check_cookie
0x140014428  mov     rbx, [rsp+0C0h+arg_8]
0x140014430  add     rsp, 0C0h
0x140014437  pop     rbp
0x140014438  retn
```
