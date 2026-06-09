# CSmsRpcUtils::IsValidUserSid(ushort const *)

- ea: `0x1800275fc`
- end: `0x18002769e`
- name: `?IsValidUserSid@CSmsRpcUtils@@SAHPEBG@Z`
- size: `162`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000fd94`

## callees

- `0x1800275fc`
- `0x180051420`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002763a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180027629`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002763a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002768b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002768b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002767b`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x18002767b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002761f`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x18002761f`

## string_xrefs

- `0x180027651`: `ConvertStringSidToSid failed for user: %S`
- `0x180027660`: `CSmsRpcUtils::IsValidUserSid`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CSmsRpcUtils::IsValidUserSid(const unsigned __int16 *a1)
{
  signed int LastError; // eax
  PSID v4; // rbx
  unsigned int valid; // edi
  PSID pSid; // [rsp+48h] [rbp+10h] BYREF
  __int64 v7; // [rsp+50h] [rbp+18h]

  pSid = 0;
  v7 = 0;
  if ( ConvertStringSidToSidW(a1, &pSid) )
  {
    v4 = pSid;
    valid = IsValidSid(pSid);
    if ( v4 )
      LocalFree(v4);
    return valid;
  }
  else if ( GetLastError() == 1337 )
  {
    return 0;
  }
  else
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    LogSmsRouterError(
      "CSmsRpcUtils::IsValidUserSid",
      0x24Fu,
      LastError,
      "ConvertStringSidToSid failed for user: %S",
      a1);
    return 1;
  }
}

```

## disassembly

```asm
0x1800275fc  mov     rax, rsp
0x1800275ff  mov     [rax+8], rbx
0x180027603  push    rdi
0x180027604  sub     rsp, 30h
0x180027608  mov     rbx, rcx
0x18002760b  mov     qword ptr [rax+10h], 0
0x180027613  mov     qword ptr [rax+18h], 0
0x18002761b  lea     rdx, [rax+10h]; Sid
0x18002761f  call    cs:__imp_ConvertStringSidToSidW
0x180027625  test    eax, eax
0x180027627  jnz     short loc_180027673
0x180027629  call    cs:__imp_GetLastError
0x18002762f  cmp     eax, 539h
0x180027634  jnz     short loc_18002763A
0x180027636  xor     eax, eax
0x180027638  jmp     short loc_180027671
0x18002763a  call    cs:__imp_GetLastError
0x180027640  test    eax, eax
0x180027642  jle     short loc_18002764C
0x180027644  movzx   eax, ax
0x180027647  or      eax, 80070000h
0x18002764c  mov     [rsp+38h+var_18], rbx
0x180027651  lea     r9, aConvertstrings_1; "ConvertStringSidToSid failed for user: "...
0x180027658  mov     r8d, eax; int
0x18002765b  mov     edx, 24Fh; unsigned int
0x180027660  lea     rcx, aCsmsrpcutilsIs; "CSmsRpcUtils::IsValidUserSid"
0x180027667  call    ?LogSmsRouterError@@YAXPEADKJ0ZZ; LogSmsRouterError(char *,ulong,long,char *,...)
0x18002766c  mov     eax, 1
0x180027671  jmp     short loc_180027693
0x180027673  mov     rbx, [rsp+38h+pSid]
0x180027678  mov     rcx, rbx; pSid
0x18002767b  call    cs:__imp_IsValidSid
0x180027681  mov     edi, eax
0x180027683  test    rbx, rbx
0x180027686  jz      short loc_180027691
0x180027688  mov     rcx, rbx; hMem
0x18002768b  call    cs:__imp_LocalFree
0x180027691  mov     eax, edi
0x180027693  mov     rbx, [rsp+38h+arg_0]
0x180027698  add     rsp, 30h
0x18002769c  pop     rdi
0x18002769d  retn
```
