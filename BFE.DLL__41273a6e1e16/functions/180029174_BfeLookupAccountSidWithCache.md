# BfeLookupAccountSidWithCache

- ea: `0x180029174`
- end: `0x180029223`
- name: `BfeLookupAccountSidWithCache`
- size: `175`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cce8`

## callees

- `0x180012e20`
- `0x1800197d0`
- `0x180029174`
- `0x18002922c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002918b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291da`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291fd`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18002918b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291da`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800291fd`

## string_xrefs

- `0x1800291b2`: `BfeLookupAccountSidWithCache`

## pseudocode

```c
__int64 __fastcall BfeLookupAccountSidWithCache(PSID pSid1)
{
  void *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx

  if ( EqualSid(pSid1, &qword_1800EE448) )
  {
    v2 = qword_1800EE458;
LABEL_3:
    v3 = WfpStringCopy(v2);
    goto LABEL_4;
  }
  if ( EqualSid(pSid1, &qword_1800EE460) )
  {
    v2 = (void *)qword_1800EE470;
    goto LABEL_3;
  }
  if ( EqualSid(pSid1, &qword_1800EE478) )
  {
    v2 = (void *)qword_1800EE488;
    goto LABEL_3;
  }
  v3 = BfeLookupAccountSid(pSid1);
LABEL_4:
  v4 = v3;
  if ( v3 )
    WfpReportError(v3, "BfeLookupAccountSidWithCache");
  return v4;
}

```

## disassembly

```asm
0x180029174  mov     [rsp+arg_0], rbx
0x180029179  push    rdi
0x18002917a  sub     rsp, 20h
0x18002917e  mov     rbx, rdx
0x180029181  mov     rdi, rcx
0x180029184  lea     rdx, qword_1800EE448; pSid2
0x18002918b  call    cs:__imp_EqualSid
0x180029192  nop     dword ptr [rax+rax+00h]
0x180029197  test    eax, eax
0x180029199  jz      short loc_1800291D0
0x18002919b  mov     rcx, cs:qword_1800EE458; Src
0x1800291a2  mov     r8, rbx
0x1800291a5  call    WfpStringCopy
0x1800291aa  mov     rbx, rax
0x1800291ad  test    rax, rax
0x1800291b0  jz      short loc_1800291C1
0x1800291b2  lea     rdx, aBfelookupaccou; "BfeLookupAccountSidWithCache"
0x1800291b9  mov     rcx, rax
0x1800291bc  call    WfpReportError
0x1800291c1  mov     rax, rbx
0x1800291c4  mov     rbx, [rsp+28h+arg_0]
0x1800291c9  add     rsp, 20h
0x1800291cd  pop     rdi
0x1800291ce  retn
0x1800291d0  lea     rdx, qword_1800EE460; pSid2
0x1800291d7  mov     rcx, rdi; pSid1
0x1800291da  call    cs:__imp_EqualSid
0x1800291e1  nop     dword ptr [rax+rax+00h]
0x1800291e6  test    eax, eax
0x1800291e8  jz      short loc_1800291F3
0x1800291ea  mov     rcx, cs:qword_1800EE470
0x1800291f1  jmp     short loc_1800291A2
0x1800291f3  lea     rdx, qword_1800EE478; pSid2
0x1800291fa  mov     rcx, rdi; pSid1
0x1800291fd  call    cs:__imp_EqualSid
0x180029204  nop     dword ptr [rax+rax+00h]
0x180029209  test    eax, eax
0x18002920b  jz      short loc_180029216
0x18002920d  mov     rcx, cs:qword_1800EE488
0x180029214  jmp     short loc_1800291A2
0x180029216  mov     rdx, rbx
0x180029219  mov     rcx, rdi; Sid
0x18002921c  call    BfeLookupAccountSid
0x180029221  jmp     short loc_1800291AA
```
