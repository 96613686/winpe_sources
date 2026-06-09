# _dynamic_initializer_for__g_isTheAllPackagesSidDefined__

- ea: `0x180001a10`
- end: `0x180001a57`
- name: `_dynamic_initializer_for__g_isTheAllPackagesSidDefined__`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001a10`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180001a33`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180001a29`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180001a29`

## pseudocode

```c
bool dynamic_initializer_for__g_isTheAllPackagesSidDefined__()
{
  DWORD LastError; // eax
  bool result; // al
  DWORD cbSid; // [rsp+30h] [rbp+8h] BYREF

  cbSid = 0;
  if ( CreateWellKnownSid(WinBuiltinAnyPackageSid, 0, 0, &cbSid) )
  {
    result = 1;
  }
  else
  {
    LastError = GetLastError();
    result = LastError != 87 && LastError == 122;
  }
  byte_18013C30C = result;
  return result;
}

```

## disassembly

```asm
0x180001a10  sub     rsp, 28h
0x180001a14  xor     edx, edx; DomainSid
0x180001a16  mov     [rsp+28h+cbSid], 0
0x180001a1e  lea     r9, [rsp+28h+cbSid]; cbSid
0x180001a23  xor     r8d, r8d; pSid
0x180001a26  lea     ecx, [rdx+54h]; WellKnownSidType
0x180001a29  call    cs:__imp_CreateWellKnownSid
0x180001a2f  test    eax, eax
0x180001a31  jnz     short loc_180001A4A
0x180001a33  call    cs:__imp_GetLastError
0x180001a39  cmp     eax, 57h ; 'W'
0x180001a3c  jz      short loc_180001A46
0x180001a3e  cmp     eax, 7Ah ; 'z'
0x180001a41  setz    al
0x180001a44  jmp     short loc_180001A4C
0x180001a46  xor     al, al
0x180001a48  jmp     short loc_180001A4C
0x180001a4a  mov     al, 1
0x180001a4c  mov     cs:byte_18013C30C, al
0x180001a52  add     rsp, 28h
0x180001a56  retn
```
