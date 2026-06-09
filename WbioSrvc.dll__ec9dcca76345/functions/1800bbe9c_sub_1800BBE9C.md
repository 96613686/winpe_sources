# sub_1800BBE9C

- ea: `0x1800bbe9c`
- end: `0x1800bc042`
- name: `sub_1800BBE9C`
- size: `422`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800bca60`
- `0x1800bcd80`

## callees

- `0x180068f60`
- `0x1800bb7b0`
- `0x1800bbe9c`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbf60`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbf93`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbfca`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbf60`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbf93`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800bbfca`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf0c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf3f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf72`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbfa5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbfeb`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf0c`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf3f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbf72`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbfa5`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1800bbfeb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbfdb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbffa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bc007`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bc01d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbfdb`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bbffa`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bc007`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x1800bc01d`

## pseudocode

```c
__int64 __fastcall sub_1800BBE9C(__int64 a1, void *a2)
{
  __int64 v3; // rcx
  unsigned int v4; // ebx
  DWORD cbSid; // [rsp+20h] [rbp-E0h] BYREF
  PSID v7; // [rsp+28h] [rbp-D8h] BYREF
  PSID pSid1[4]; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pSid[272]; // [rsp+50h] [rbp-B0h] BYREF

  cbSid = 260;
  pSid1[0] = 0;
  pSid1[1] = pSid1;
  v7 = 0;
  pSid1[2] = &v7;
  if ( (int)sub_1800BB7B0(a1, 500, pSid1) < 0 )
    goto LABEL_11;
  if ( EqualSid(pSid1[0], a2) )
  {
LABEL_3:
    v4 = 1;
LABEL_12:
    FreeSid(v7);
    goto LABEL_16;
  }
  if ( (int)sub_1800BB7B0(v3, 501, &v7) < 0 )
    goto LABEL_11;
  if ( EqualSid(v7, a2) )
    goto LABEL_3;
  cbSid = 260;
  if ( !CreateWellKnownSid(WinLocalSystemSid, 0, pSid, &cbSid) )
    goto LABEL_11;
  if ( EqualSid(pSid, a2) )
    goto LABEL_3;
  cbSid = 260;
  if ( !CreateWellKnownSid(WinLocalServiceSid, 0, pSid, &cbSid) )
    goto LABEL_11;
  if ( EqualSid(pSid, a2) )
    goto LABEL_3;
  cbSid = 260;
  if ( !CreateWellKnownSid(WinNetworkServiceSid, 0, pSid, &cbSid) )
  {
LABEL_11:
    v4 = 0;
    goto LABEL_12;
  }
  if ( EqualSid(pSid, a2) )
  {
    FreeSid(v7);
    v4 = 1;
  }
  else
  {
    FreeSid(v7);
    v4 = 0;
  }
LABEL_16:
  v7 = 0;
  FreeSid(pSid1[0]);
  return v4;
}

```

## disassembly

```asm
0x1800bbe9c  mov     [rsp-8+arg_0], rbx
0x1800bbea1  push    rbp
0x1800bbea2  lea     rbp, [rsp-70h]
0x1800bbea7  sub     rsp, 170h
0x1800bbeae  mov     rax, cs:__security_cookie
0x1800bbeb5  xor     rax, rsp
0x1800bbeb8  mov     [rbp+70h+var_10], rax
0x1800bbebc  mov     rbx, rdx
0x1800bbebf  mov     [rsp+170h+cbSid], 104h
0x1800bbec7  mov     [rsp+170h+pSid1], 0
0x1800bbed0  lea     rax, [rsp+170h+pSid1]
0x1800bbed5  mov     [rsp+170h+var_138], rax
0x1800bbeda  mov     [rsp+170h+var_148], 0
0x1800bbee3  lea     rax, [rsp+170h+var_148]
0x1800bbee8  mov     [rsp+170h+var_130], rax
0x1800bbeed  lea     r8, [rsp+170h+pSid1]
0x1800bbef2  mov     edx, 1F4h
0x1800bbef7  call    sub_1800BB7B0
0x1800bbefc  test    eax, eax
0x1800bbefe  js      loc_1800BBFD4
0x1800bbf04  mov     rdx, rbx; pSid2
0x1800bbf07  mov     rcx, [rsp+170h+pSid1]; pSid1
0x1800bbf0c  call    cs:EqualSid
0x1800bbf12  test    eax, eax
0x1800bbf14  jz      short loc_1800BBF20
0x1800bbf16  mov     ebx, 1
0x1800bbf1b  jmp     loc_1800BBFD6
0x1800bbf20  lea     r8, [rsp+170h+var_148]
0x1800bbf25  mov     edx, 1F5h
0x1800bbf2a  call    sub_1800BB7B0
0x1800bbf2f  test    eax, eax
0x1800bbf31  js      loc_1800BBFD4
0x1800bbf37  mov     rdx, rbx; pSid2
0x1800bbf3a  mov     rcx, [rsp+170h+var_148]; pSid1
0x1800bbf3f  call    cs:EqualSid
0x1800bbf45  test    eax, eax
0x1800bbf47  jnz     short loc_1800BBF16
0x1800bbf49  mov     [rsp+170h+cbSid], 104h
0x1800bbf51  lea     r9, [rsp+170h+cbSid]; cbSid
0x1800bbf56  lea     r8, [rsp+170h+pSid]; pSid
0x1800bbf5b  xor     edx, edx; DomainSid
0x1800bbf5d  lea     ecx, [rax+16h]; WellKnownSidType
0x1800bbf60  call    cs:CreateWellKnownSid
0x1800bbf66  test    eax, eax
0x1800bbf68  jz      short loc_1800BBFD4
0x1800bbf6a  mov     rdx, rbx; pSid2
0x1800bbf6d  lea     rcx, [rsp+170h+pSid]; pSid1
0x1800bbf72  call    cs:EqualSid
0x1800bbf78  test    eax, eax
0x1800bbf7a  jnz     short loc_1800BBF16
0x1800bbf7c  mov     [rsp+170h+cbSid], 104h
0x1800bbf84  lea     r9, [rsp+170h+cbSid]; cbSid
0x1800bbf89  lea     r8, [rsp+170h+pSid]; pSid
0x1800bbf8e  xor     edx, edx; DomainSid
0x1800bbf90  lea     ecx, [rax+17h]; WellKnownSidType
0x1800bbf93  call    cs:CreateWellKnownSid
0x1800bbf99  test    eax, eax
0x1800bbf9b  jz      short loc_1800BBFD4
0x1800bbf9d  mov     rdx, rbx; pSid2
0x1800bbfa0  lea     rcx, [rsp+170h+pSid]; pSid1
0x1800bbfa5  call    cs:EqualSid
0x1800bbfab  test    eax, eax
0x1800bbfad  jnz     loc_1800BBF16
0x1800bbfb3  mov     [rsp+170h+cbSid], 104h
0x1800bbfbb  lea     r9, [rsp+170h+cbSid]; cbSid
0x1800bbfc0  lea     r8, [rsp+170h+pSid]; pSid
0x1800bbfc5  xor     edx, edx; DomainSid
0x1800bbfc7  lea     ecx, [rax+18h]; WellKnownSidType
0x1800bbfca  call    cs:CreateWellKnownSid
0x1800bbfd0  test    eax, eax
0x1800bbfd2  jnz     short loc_1800BBFE3
0x1800bbfd4  xor     ebx, ebx
0x1800bbfd6  mov     rcx, [rsp+170h+var_148]; pSid
0x1800bbfdb  call    cs:FreeSid
0x1800bbfe1  jmp     short loc_1800BC00F
0x1800bbfe3  mov     rdx, rbx; pSid2
0x1800bbfe6  lea     rcx, [rsp+170h+pSid]; pSid1
0x1800bbfeb  call    cs:EqualSid
0x1800bbff1  mov     rcx, [rsp+170h+var_148]; pSid
0x1800bbff6  test    eax, eax
0x1800bbff8  jz      short loc_1800BC007
0x1800bbffa  call    cs:FreeSid
0x1800bc000  mov     ebx, 1
0x1800bc005  jmp     short loc_1800BC00F
0x1800bc007  call    cs:FreeSid
0x1800bc00d  xor     ebx, ebx
0x1800bc00f  mov     [rsp+170h+var_148], 0
0x1800bc018  mov     rcx, [rsp+170h+pSid1]; pSid
0x1800bc01d  call    cs:FreeSid
0x1800bc023  mov     eax, ebx
0x1800bc025  mov     rcx, [rbp+70h+var_10]
0x1800bc029  xor     rcx, rsp; StackCookie
0x1800bc02c  call    __security_check_cookie
0x1800bc031  mov     rbx, [rsp+170h+arg_0]
0x1800bc039  add     rsp, 170h
0x1800bc040  pop     rbp
0x1800bc041  retn
```
