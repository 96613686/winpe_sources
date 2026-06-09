# GetTokenPackageSID(void *,ulong,void *)

- ea: `0x180021060`
- end: `0x1800210f8`
- name: `?GetTokenPackageSID@@YAJPEAXK0@Z`
- size: `152`
- prototype: `int(void *, unsigned int, void *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000a4fc`

## callees

- `0x180002ce0`
- `0x180021060`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800210cd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002109d`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002109d`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800210bf`
- `api-ms-win-security-base-l1-1-0!CopySid` at `0x1800210bf`

## pseudocode

```c
int __fastcall GetTokenPackageSID(void *a1, __int64 a2, void *a3)
{
  int result; // eax
  DWORD ReturnLength[4]; // [rsp+30h] [rbp-138h] BYREF
  PSID TokenInformation[34]; // [rsp+40h] [rbp-128h] BYREF

  ReturnLength[0] = 264;
  if ( !GetTokenInformation(a1, TokenAppContainerSid, TokenInformation, 0x108u, ReturnLength) )
    goto LABEL_6;
  if ( !TokenInformation[0] )
    return 1;
  if ( CopySid(0x100u, a3, TokenInformation[0]) )
    return 0;
LABEL_6:
  result = GetLastError();
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180021060  push    rbx
0x180021062  sub     rsp, 160h
0x180021069  mov     rax, cs:__security_cookie
0x180021070  xor     rax, rsp
0x180021073  mov     [rsp+168h+var_18], rax
0x18002107b  mov     rbx, r8
0x18002107e  lea     rax, [rsp+168h+var_138]
0x180021083  mov     r9d, 108h; TokenInformationLength
0x180021089  mov     [rsp+168h+ReturnLength], rax; ReturnLength
0x18002108e  lea     r8, [rsp+168h+TokenInformation]; TokenInformation
0x180021093  mov     [rsp+168h+var_138], r9d
0x180021098  mov     edx, 1Fh; TokenInformationClass
0x18002109d  call    cs:__imp_GetTokenInformation
0x1800210a3  test    eax, eax
0x1800210a5  jz      short loc_1800210CD
0x1800210a7  mov     r8, [rsp+168h+TokenInformation]; pSourceSid
0x1800210ac  test    r8, r8
0x1800210af  jnz     short loc_1800210B7
0x1800210b1  lea     eax, [r8+1]
0x1800210b5  jmp     short loc_1800210DF
0x1800210b7  mov     rdx, rbx; pDestinationSid
0x1800210ba  mov     ecx, 100h; nDestinationSidLength
0x1800210bf  call    cs:__imp_CopySid
0x1800210c5  test    eax, eax
0x1800210c7  jz      short loc_1800210CD
0x1800210c9  xor     eax, eax
0x1800210cb  jmp     short loc_1800210DF
0x1800210cd  call    cs:__imp_GetLastError
0x1800210d3  test    eax, eax
0x1800210d5  jle     short loc_1800210DF
0x1800210d7  movzx   eax, ax
0x1800210da  or      eax, 80070000h
0x1800210df  mov     rcx, [rsp+168h+var_18]
0x1800210e7  xor     rcx, rsp; StackCookie
0x1800210ea  call    __security_check_cookie
0x1800210ef  add     rsp, 160h
0x1800210f6  pop     rbx
0x1800210f7  retn
```
