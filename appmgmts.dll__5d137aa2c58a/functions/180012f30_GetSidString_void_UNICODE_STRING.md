# GetSidString(void *,_UNICODE_STRING *)

- ea: `0x180012f30`
- end: `0x180012fb6`
- name: `?GetSidString@@YAKPEAXPEAU_UNICODE_STRING@@@Z`
- size: `134`
- prototype: `signed int __fastcall(void *, struct _UNICODE_STRING *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180011268`
- `0x180012690`

## callees

- `0x1800016d0`
- `0x180012f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012f76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012f6c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180012f6c`
- `ntdll!RtlNtStatusToDosError` at `0x180012f97`
- `ntdll!RtlNtStatusToDosError` at `0x180012f97`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180012f8b`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180012f8b`

## pseudocode

```c
signed int __fastcall GetSidString(void *a1, struct _UNICODE_STRING *a2)
{
  signed int result; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-88h] BYREF
  PSID TokenInformation[12]; // [rsp+40h] [rbp-78h] BYREF

  ReturnLength[0] = 84;
  if ( GetTokenInformation(a1, TokenUser, TokenInformation, 0x54u, ReturnLength) || (result = GetLastError()) == 0 )
  {
    result = RtlConvertSidToUnicodeString(a2, TokenInformation[0], 1u);
    if ( result < 0 )
      return RtlNtStatusToDosError(result);
  }
  return result;
}

```

## disassembly

```asm
0x180012f30  push    rbx
0x180012f32  sub     rsp, 0B0h
0x180012f39  mov     rax, cs:__security_cookie
0x180012f40  xor     rax, rsp
0x180012f43  mov     [rsp+0B8h+var_18], rax
0x180012f4b  mov     r9d, 54h ; 'T'; TokenInformationLength
0x180012f51  lea     rax, [rsp+0B8h+var_88]
0x180012f56  mov     rbx, rdx
0x180012f59  mov     [rsp+0B8h+var_88], r9d
0x180012f5e  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180012f63  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180012f68  lea     edx, [r9-53h]; TokenInformationClass
0x180012f6c  call    cs:__imp_GetTokenInformation
0x180012f72  test    eax, eax
0x180012f74  jnz     short loc_180012F80
0x180012f76  call    cs:__imp_GetLastError
0x180012f7c  test    eax, eax
0x180012f7e  jnz     short loc_180012F9D
0x180012f80  mov     rdx, [rsp+0B8h+TokenInformation]; Sid
0x180012f85  mov     r8b, 1; AllocateDestinationString
0x180012f88  mov     rcx, rbx; UnicodeString
0x180012f8b  call    cs:__imp_RtlConvertSidToUnicodeString
0x180012f91  test    eax, eax
0x180012f93  jns     short loc_180012F9D
0x180012f95  mov     ecx, eax; Status
0x180012f97  call    cs:__imp_RtlNtStatusToDosError
0x180012f9d  mov     rcx, [rsp+0B8h+var_18]
0x180012fa5  xor     rcx, rsp; StackCookie
0x180012fa8  call    __security_check_cookie
0x180012fad  add     rsp, 0B0h
0x180012fb4  pop     rbx
0x180012fb5  retn
```
