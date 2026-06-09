# BfeLookupAccountSidWithCache

- ea: `0x18003a434`
- end: `0x18003a4d0`
- name: `BfeLookupAccountSidWithCache`
- size: `156`
- prototype: `__int64 __fastcall(PSID pSid1)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004aeb8`

## callees

- `0x180012400`
- `0x180018b74`
- `0x18003a434`
- `0x18003a4d8`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a44b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a493`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a4b0`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a44b`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a493`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18003a4b0`

## string_xrefs

- `0x18003a46c`: `BfeLookupAccountSidWithCache`

## pseudocode

```c
__int64 __fastcall BfeLookupAccountSidWithCache(PSID pSid1)
{
  void *v2; // rcx
  __int64 v3; // rax
  __int64 v4; // rbx

  if ( EqualSid(pSid1, &qword_1800EB348) )
  {
    v2 = qword_1800EB358;
LABEL_3:
    v3 = WfpStringCopy(v2);
    goto LABEL_4;
  }
  if ( EqualSid(pSid1, &qword_1800EB360) )
  {
    v2 = (void *)qword_1800EB370;
    goto LABEL_3;
  }
  if ( EqualSid(pSid1, &qword_1800EB378) )
  {
    v2 = (void *)qword_1800EB388;
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
0x18003a434  mov     [rsp+arg_0], rbx
0x18003a439  push    rdi
0x18003a43a  sub     rsp, 20h
0x18003a43e  mov     rbx, rdx
0x18003a441  mov     rdi, rcx
0x18003a444  lea     rdx, qword_1800EB348; pSid2
0x18003a44b  call    cs:__imp_EqualSid
0x18003a451  test    eax, eax
0x18003a453  jz      short loc_18003A489
0x18003a455  mov     rcx, cs:qword_1800EB358; Src
0x18003a45c  mov     r8, rbx
0x18003a45f  call    WfpStringCopy
0x18003a464  mov     rbx, rax
0x18003a467  test    rax, rax
0x18003a46a  jz      short loc_18003A47B
0x18003a46c  lea     rdx, aBfelookupaccou; "BfeLookupAccountSidWithCache"
0x18003a473  mov     rcx, rax
0x18003a476  call    WfpReportError
0x18003a47b  mov     rax, rbx
0x18003a47e  mov     rbx, [rsp+28h+arg_0]
0x18003a483  add     rsp, 20h
0x18003a487  pop     rdi
0x18003a488  retn
0x18003a489  lea     rdx, qword_1800EB360; pSid2
0x18003a490  mov     rcx, rdi; pSid1
0x18003a493  call    cs:__imp_EqualSid
0x18003a499  test    eax, eax
0x18003a49b  jz      short loc_18003A4A6
0x18003a49d  mov     rcx, cs:qword_1800EB370
0x18003a4a4  jmp     short loc_18003A45C
0x18003a4a6  lea     rdx, qword_1800EB378; pSid2
0x18003a4ad  mov     rcx, rdi; pSid1
0x18003a4b0  call    cs:__imp_EqualSid
0x18003a4b6  test    eax, eax
0x18003a4b8  jz      short loc_18003A4C3
0x18003a4ba  mov     rcx, cs:qword_1800EB388
0x18003a4c1  jmp     short loc_18003A45C
0x18003a4c3  mov     rdx, rbx
0x18003a4c6  mov     rcx, rdi; Sid
0x18003a4c9  call    BfeLookupAccountSid
0x18003a4ce  jmp     short loc_18003A464
```
