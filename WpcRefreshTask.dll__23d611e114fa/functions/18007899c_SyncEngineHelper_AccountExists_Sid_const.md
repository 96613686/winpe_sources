# SyncEngineHelper::AccountExists(Sid const &)

- ea: `0x18007899c`
- end: `0x180078a2f`
- name: `?AccountExists@SyncEngineHelper@@YA_NAEBVSid@@@Z`
- size: `147`
- prototype: `bool __fastcall(PSID Sid, const struct Sid *)`
- caller_count: `3`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18007908c`
- `0x18007985c`
- `0x18007aa74`

## callees

- `0x1800060a0`
- `0x18007899c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180078a0f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800789fa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800789fa`

## pseudocode

```c
char __fastcall SyncEngineHelper::AccountExists(PSID Sid, const struct Sid *a2)
{
  enum _SID_NAME_USE peUse; // [rsp+40h] [rbp-258h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-254h] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-250h] BYREF
  WCHAR ReferencedDomainName[16]; // [rsp+50h] [rbp-248h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-228h] BYREF

  cchName = 257;
  cchReferencedDomainName = 16;
  peUse = 0;
  if ( LookupAccountSidW(0, Sid, Name, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    return 1;
  if ( peUse == SidTypeUser )
    GetLastError();
  return 0;
}

```

## disassembly

```asm
0x18007899c  sub     rsp, 298h
0x1800789a3  mov     rax, cs:__security_cookie
0x1800789aa  xor     rax, rsp
0x1800789ad  mov     [rsp+298h+var_18], rax
0x1800789b5  lea     rax, [rsp+298h+var_258]
0x1800789ba  mov     [rsp+298h+cchName], 101h
0x1800789c2  mov     [rsp+298h+peUse], rax; peUse
0x1800789c7  lea     r9, [rsp+298h+cchName]; cchName
0x1800789cc  lea     rax, [rsp+298h+var_250]
0x1800789d1  mov     [rsp+298h+var_250], 10h
0x1800789d9  mov     [rsp+298h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800789de  lea     r8, [rsp+298h+Name]; Name
0x1800789e3  lea     rax, [rsp+298h+var_248]
0x1800789e8  mov     [rsp+298h+var_258], 0
0x1800789f0  mov     rdx, rcx; Sid
0x1800789f3  mov     [rsp+298h+ReferencedDomainName], rax; ReferencedDomainName
0x1800789f8  xor     ecx, ecx; lpSystemName
0x1800789fa  call    cs:__imp_LookupAccountSidW
0x180078a00  test    eax, eax
0x180078a02  jz      short loc_180078A08
0x180078a04  mov     al, 1
0x180078a06  jmp     short loc_180078A17
0x180078a08  cmp     [rsp+298h+var_258], 1
0x180078a0d  jnz     short loc_180078A15
0x180078a0f  call    cs:__imp_GetLastError
0x180078a15  xor     al, al
0x180078a17  mov     rcx, [rsp+298h+var_18]
0x180078a1f  xor     rcx, rsp; StackCookie
0x180078a22  call    __security_check_cookie
0x180078a27  add     rsp, 298h
0x180078a2e  retn
```
