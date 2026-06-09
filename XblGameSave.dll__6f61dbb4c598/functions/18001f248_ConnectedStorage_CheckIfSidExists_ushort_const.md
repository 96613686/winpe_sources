# ConnectedStorage::CheckIfSidExists(ushort const *)

- ea: `0x18001f248`
- end: `0x18001f2d8`
- name: `?CheckIfSidExists@ConnectedStorage@@YA_NPEBG@Z`
- size: `144`
- prototype: `bool __fastcall(ConnectedStorage *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001f4a0`

## callees

- `0x18001f248`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f2c1`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f25c`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18001f25c`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001f2aa`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18001f2aa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2b7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001f2b7`

## pseudocode

```c
bool __fastcall ConnectedStorage::CheckIfSidExists(const WCHAR *this, const unsigned __int16 *a2)
{
  BOOL v2; // ebx
  bool result; // al
  PSID Sid; // [rsp+40h] [rbp-18h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+68h] [rbp+10h] BYREF
  DWORD cchReferencedDomainName; // [rsp+70h] [rbp+18h] BYREF
  DWORD cchName; // [rsp+78h] [rbp+20h] BYREF

  Sid = 0;
  result = 0;
  if ( ConvertStringSidToSidW(this, &Sid) )
  {
    cchName = 0;
    cchReferencedDomainName = 0;
    peUse = 0;
    v2 = LookupAccountSidW(0, Sid, 0, &cchName, 0, &cchReferencedDomainName, &peUse);
    LocalFree(Sid);
    if ( v2 || GetLastError() == 122 )
      return 1;
  }
  return result;
}

```

## disassembly

```asm
0x18001f248  push    rbx
0x18001f24a  sub     rsp, 50h
0x18001f24e  lea     rdx, [rsp+58h+Sid]; Sid
0x18001f253  mov     [rsp+58h+Sid], 0
0x18001f25c  call    cs:__imp_ConvertStringSidToSidW
0x18001f262  test    eax, eax
0x18001f264  jz      short loc_18001F2D0
0x18001f266  mov     rdx, [rsp+58h+Sid]; Sid
0x18001f26b  lea     rax, [rsp+58h+arg_8]
0x18001f270  mov     [rsp+58h+peUse], rax; peUse
0x18001f275  lea     r9, [rsp+58h+cchName]; cchName
0x18001f27a  lea     rax, [rsp+58h+arg_10]
0x18001f27f  mov     [rsp+58h+cchName], 0
0x18001f287  mov     [rsp+58h+cchReferencedDomainName], rax; cchReferencedDomainName
0x18001f28c  xor     r8d, r8d; Name
0x18001f28f  xor     ecx, ecx; lpSystemName
0x18001f291  mov     [rsp+58h+ReferencedDomainName], 0; ReferencedDomainName
0x18001f29a  mov     [rsp+58h+arg_10], 0
0x18001f2a2  mov     [rsp+58h+arg_8], 0
0x18001f2aa  call    cs:__imp_LookupAccountSidW
0x18001f2b0  mov     rcx, [rsp+58h+Sid]; hMem
0x18001f2b5  mov     ebx, eax
0x18001f2b7  call    cs:__imp_LocalFree
0x18001f2bd  test    ebx, ebx
0x18001f2bf  jnz     short loc_18001F2CC
0x18001f2c1  call    cs:__imp_GetLastError
0x18001f2c7  cmp     eax, 7Ah ; 'z'
0x18001f2ca  jnz     short loc_18001F2D0
0x18001f2cc  mov     al, 1
0x18001f2ce  jmp     short loc_18001F2D2
0x18001f2d0  xor     al, al
0x18001f2d2  add     rsp, 50h
0x18001f2d6  pop     rbx
0x18001f2d7  retn
```
