# CopyCallbackDataAnsiToNeutral(_FAX_JOB_PARAMA *,_FAX_COVERPAGE_INFOA *,_FAX_JOB_PARAM_EXW *,_FAX_COVERPAGE_INFO_EXW *,_FAX_PERSONAL_PROFILEW *,_FAX_PERSONAL_PROFILEW *)

- ea: `0x180016424`
- end: `0x1800166be`
- name: `?CopyCallbackDataAnsiToNeutral@@YAHPEAU_FAX_JOB_PARAMA@@PEAU_FAX_COVERPAGE_INFOA@@PEAU_FAX_JOB_PARAM_EXW@@PEAU_FAX_COVERPAGE_INFO_EXW@@PEAU_FAX_PERSONAL_PROFILEW@@4@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct _FAX_JOB_PARAMA *, struct _FAX_COVERPAGE_INFOA *, struct _FAX_JOB_PARAM_EXW *, struct _FAX_COVERPAGE_INFO_EXW *, struct _FAX_PERSONAL_PROFILEW *, struct _FAX_PERSONAL_PROFILEW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a10`

## callees

- `0x180016424`
- `0x18002bc50`
- `0x18003d4ca`

## pseudocode

```c
__int64 __fastcall CopyCallbackDataAnsiToNeutral(
        struct _FAX_JOB_PARAMA *a1,
        struct _FAX_COVERPAGE_INFOA *a2,
        struct _FAX_JOB_PARAM_EXW *a3,
        struct _FAX_COVERPAGE_INFO_EXW *a4,
        struct _FAX_PERSONAL_PROFILEW *a5,
        struct _FAX_PERSONAL_PROFILEW *a6)
{
  memset_0((char *)a3 + 4, 0, 0x5Cu);
  *(_DWORD *)a3 = 96;
  *((_DWORD *)a3 + 1) = a1->ScheduleAction;
  *(SYSTEMTIME *)((char *)a3 + 8) = a1->ScheduleTime;
  *((_DWORD *)a3 + 6) = a1->DeliveryReportType;
  *((_DWORD *)a3 + 10) = 1;
  *((_DWORD *)a3 + 11) = a1->CallHandle;
  *((_OWORD *)a3 + 3) = *(_OWORD *)a1->Reserved;
  *((_QWORD *)a3 + 8) = a1->Reserved[2];
  if ( a2 )
    *((_DWORD *)a3 + 22) = a2->PageCount;
  *((_QWORD *)a4 + 1) = 0;
  *((_QWORD *)a4 + 2) = 0;
  *((_QWORD *)a4 + 3) = 0;
  *((_QWORD *)a4 + 4) = 0;
  *(_DWORD *)a4 = 40;
  *((_DWORD *)a4 + 1) = 1;
  if ( a2 )
    *((_DWORD *)a4 + 4) = a2->UseServerCoverPage;
  memset_0((char *)a5 + 4, 0, 0x84u);
  *(_DWORD *)a5 = 136;
  memset_0((char *)a6 + 4, 0, 0x84u);
  *(_DWORD *)a6 = 136;
  *((_QWORD *)a3 + 4) = AnsiStringToUnicodeString(a1->DeliveryReportAddress);
  *((_QWORD *)a3 + 10) = AnsiStringToUnicodeString(a1->DocumentName);
  *((_QWORD *)a5 + 1) = AnsiStringToUnicodeString(a1->SenderName);
  *((_QWORD *)a5 + 3) = AnsiStringToUnicodeString(a1->SenderCompany);
  *((_QWORD *)a5 + 10) = AnsiStringToUnicodeString(a1->SenderDept);
  *((_QWORD *)a5 + 15) = AnsiStringToUnicodeString(a1->BillingCode);
  *((_QWORD *)a6 + 1) = AnsiStringToUnicodeString(a1->RecipientName);
  *((_QWORD *)a6 + 2) = AnsiStringToUnicodeString(a1->RecipientNumber);
  *((_QWORD *)a6 + 16) = AnsiStringToUnicodeString(a1->Tsid);
  if ( a2 )
  {
    *((_QWORD *)a4 + 1) = AnsiStringToUnicodeString(a2->CoverPageName);
    *((_QWORD *)a4 + 3) = AnsiStringToUnicodeString(a2->Note);
    *((_QWORD *)a4 + 4) = AnsiStringToUnicodeString(a2->Subject);
    *((_QWORD *)a5 + 5) = AnsiStringToUnicodeString(a2->SdrAddress);
    *((_QWORD *)a5 + 2) = AnsiStringToUnicodeString(a2->SdrFaxNumber);
    *((_QWORD *)a5 + 4) = AnsiStringToUnicodeString(a2->SdrAddress);
    *((_QWORD *)a5 + 9) = AnsiStringToUnicodeString(a2->SdrTitle);
    *((_QWORD *)a5 + 11) = AnsiStringToUnicodeString(a2->SdrOfficeLocation);
    *((_QWORD *)a5 + 12) = AnsiStringToUnicodeString(a2->SdrHomePhone);
    *((_QWORD *)a5 + 13) = AnsiStringToUnicodeString(a2->SdrOfficePhone);
    *((_QWORD *)a6 + 3) = AnsiStringToUnicodeString(a2->RecCompany);
    *((_QWORD *)a6 + 4) = AnsiStringToUnicodeString(a2->RecStreetAddress);
    *((_QWORD *)a6 + 5) = AnsiStringToUnicodeString(a2->RecCity);
    *((_QWORD *)a6 + 6) = AnsiStringToUnicodeString(a2->RecState);
    *((_QWORD *)a6 + 7) = AnsiStringToUnicodeString(a2->RecZip);
    *((_QWORD *)a6 + 8) = AnsiStringToUnicodeString(a2->RecCountry);
    *((_QWORD *)a6 + 9) = AnsiStringToUnicodeString(a2->RecTitle);
    *((_QWORD *)a6 + 10) = AnsiStringToUnicodeString(a2->RecDepartment);
    *((_QWORD *)a6 + 11) = AnsiStringToUnicodeString(a2->RecOfficeLocation);
    *((_QWORD *)a6 + 12) = AnsiStringToUnicodeString(a2->RecHomePhone);
    *((_QWORD *)a6 + 13) = AnsiStringToUnicodeString(a2->RecOfficePhone);
  }
  return 1;
}

```

## disassembly

```asm
0x180016424  push    rbx
0x180016426  push    rbp
0x180016427  push    rsi
0x180016428  push    rdi
0x180016429  push    r14
0x18001642b  push    r15
0x18001642d  sub     rsp, 28h
0x180016431  mov     rbp, rdx
0x180016434  mov     rdi, rcx
0x180016437  xor     edx, edx; Val
0x180016439  lea     rcx, [r8+4]; void *
0x18001643d  mov     rbx, r8
0x180016440  mov     rsi, r9
0x180016443  lea     r8d, [rdx+5Ch]; Size
0x180016447  call    memset_0
0x18001644c  mov     dword ptr [rbx], 60h ; '`'
0x180016452  mov     edx, 1
0x180016457  mov     eax, [rdi+40h]
0x18001645a  xor     ecx, ecx
0x18001645c  mov     [rbx+4], eax
0x18001645f  movups  xmm0, xmmword ptr [rdi+44h]
0x180016463  movdqu  xmmword ptr [rbx+8], xmm0
0x180016468  mov     eax, [rdi+54h]
0x18001646b  mov     [rbx+18h], eax
0x18001646e  mov     [rbx+28h], edx
0x180016471  mov     eax, [rdi+68h]
0x180016474  mov     [rbx+2Ch], eax
0x180016477  movups  xmm0, xmmword ptr [rdi+70h]
0x18001647b  movups  xmmword ptr [rbx+30h], xmm0
0x18001647f  movsd   xmm1, qword ptr [rdi+80h]
0x180016487  movsd   qword ptr [rbx+40h], xmm1
0x18001648c  test    rbp, rbp
0x18001648f  jz      short loc_18001649A
0x180016491  mov     eax, [rbp+0E8h]
0x180016497  mov     [rbx+58h], eax
0x18001649a  mov     [rsi+8], rcx
0x18001649e  mov     [rsi+10h], rcx
0x1800164a2  mov     [rsi+18h], rcx
0x1800164a6  mov     [rsi+20h], rcx
0x1800164aa  mov     dword ptr [rsi], 28h ; '('
0x1800164b0  mov     [rsi+4], edx
0x1800164b3  test    rbp, rbp
0x1800164b6  jz      short loc_1800164BE
0x1800164b8  mov     eax, [rbp+10h]
0x1800164bb  mov     [rsi+10h], eax
0x1800164be  mov     r14, [rsp+58h+arg_20]
0x1800164c6  xor     edx, edx; Val
0x1800164c8  mov     r8d, 84h; Size
0x1800164ce  lea     rcx, [r14+4]; void *
0x1800164d2  call    memset_0
0x1800164d7  mov     r15, [rsp+58h+arg_28]
0x1800164df  xor     edx, edx; Val
0x1800164e1  mov     r8d, 84h; Size
0x1800164e7  mov     dword ptr [r14], 88h
0x1800164ee  lea     rcx, [r15+4]; void *
0x1800164f2  call    memset_0
0x1800164f7  mov     dword ptr [r15], 88h
0x1800164fe  mov     rcx, [rdi+58h]; lpMultiByteStr
0x180016502  call    AnsiStringToUnicodeString
0x180016507  mov     [rbx+20h], rax
0x18001650b  mov     rcx, [rdi+60h]; lpMultiByteStr
0x18001650f  call    AnsiStringToUnicodeString
0x180016514  mov     [rbx+50h], rax
0x180016518  mov     rcx, [rdi+20h]; lpMultiByteStr
0x18001651c  call    AnsiStringToUnicodeString
0x180016521  mov     [r14+8], rax
0x180016525  mov     rcx, [rdi+28h]; lpMultiByteStr
0x180016529  call    AnsiStringToUnicodeString
0x18001652e  mov     [r14+18h], rax
0x180016532  mov     rcx, [rdi+30h]; lpMultiByteStr
0x180016536  call    AnsiStringToUnicodeString
0x18001653b  mov     [r14+50h], rax
0x18001653f  mov     rcx, [rdi+38h]; lpMultiByteStr
0x180016543  call    AnsiStringToUnicodeString
0x180016548  mov     [r14+78h], rax
0x18001654c  mov     rcx, [rdi+10h]; lpMultiByteStr
0x180016550  call    AnsiStringToUnicodeString
0x180016555  mov     [r15+8], rax
0x180016559  mov     rcx, [rdi+8]; lpMultiByteStr
0x18001655d  call    AnsiStringToUnicodeString
0x180016562  mov     [r15+10h], rax
0x180016566  mov     rcx, [rdi+18h]; lpMultiByteStr
0x18001656a  call    AnsiStringToUnicodeString
0x18001656f  mov     [r15+80h], rax
0x180016576  test    rbp, rbp
0x180016579  jz      loc_1800166AB
0x18001657f  mov     rcx, [rbp+8]; lpMultiByteStr
0x180016583  call    AnsiStringToUnicodeString
0x180016588  mov     [rsi+8], rax
0x18001658c  mov     rcx, [rbp+0C8h]; lpMultiByteStr
0x180016593  call    AnsiStringToUnicodeString
0x180016598  mov     [rsi+18h], rax
0x18001659c  mov     rcx, [rbp+0D0h]; lpMultiByteStr
0x1800165a3  call    AnsiStringToUnicodeString
0x1800165a8  mov     [rsi+20h], rax
0x1800165ac  mov     rcx, [rbp+98h]; lpMultiByteStr
0x1800165b3  call    AnsiStringToUnicodeString
0x1800165b8  mov     [r14+28h], rax
0x1800165bc  mov     rcx, [rbp+88h]; lpMultiByteStr
0x1800165c3  call    AnsiStringToUnicodeString
0x1800165c8  mov     [r14+10h], rax
0x1800165cc  mov     rcx, [rbp+98h]; lpMultiByteStr
0x1800165d3  call    AnsiStringToUnicodeString
0x1800165d8  mov     [r14+20h], rax
0x1800165dc  mov     rcx, [rbp+0A0h]; lpMultiByteStr
0x1800165e3  call    AnsiStringToUnicodeString
0x1800165e8  mov     [r14+48h], rax
0x1800165ec  mov     rcx, [rbp+0B0h]; lpMultiByteStr
0x1800165f3  call    AnsiStringToUnicodeString
0x1800165f8  mov     [r14+58h], rax
0x1800165fc  mov     rcx, [rbp+0B8h]; lpMultiByteStr
0x180016603  call    AnsiStringToUnicodeString
0x180016608  mov     [r14+60h], rax
0x18001660c  mov     rcx, [rbp+0C0h]; lpMultiByteStr
0x180016613  call    AnsiStringToUnicodeString
0x180016618  mov     [r14+68h], rax
0x18001661c  mov     rcx, [rbp+28h]; lpMultiByteStr
0x180016620  call    AnsiStringToUnicodeString
0x180016625  mov     [r15+18h], rax
0x180016629  mov     rcx, [rbp+30h]; lpMultiByteStr
0x18001662d  call    AnsiStringToUnicodeString
0x180016632  mov     [r15+20h], rax
0x180016636  mov     rcx, [rbp+38h]; lpMultiByteStr
0x18001663a  call    AnsiStringToUnicodeString
0x18001663f  mov     [r15+28h], rax
0x180016643  mov     rcx, [rbp+40h]; lpMultiByteStr
0x180016647  call    AnsiStringToUnicodeString
0x18001664c  mov     [r15+30h], rax
0x180016650  mov     rcx, [rbp+48h]; lpMultiByteStr
0x180016654  call    AnsiStringToUnicodeString
0x180016659  mov     [r15+38h], rax
0x18001665d  mov     rcx, [rbp+50h]; lpMultiByteStr
0x180016661  call    AnsiStringToUnicodeString
0x180016666  mov     [r15+40h], rax
0x18001666a  mov     rcx, [rbp+58h]; lpMultiByteStr
0x18001666e  call    AnsiStringToUnicodeString
0x180016673  mov     [r15+48h], rax
0x180016677  mov     rcx, [rbp+60h]; lpMultiByteStr
0x18001667b  call    AnsiStringToUnicodeString
0x180016680  mov     [r15+50h], rax
0x180016684  mov     rcx, [rbp+68h]; lpMultiByteStr
0x180016688  call    AnsiStringToUnicodeString
0x18001668d  mov     [r15+58h], rax
0x180016691  mov     rcx, [rbp+70h]; lpMultiByteStr
0x180016695  call    AnsiStringToUnicodeString
0x18001669a  mov     [r15+60h], rax
0x18001669e  mov     rcx, [rbp+78h]; lpMultiByteStr
0x1800166a2  call    AnsiStringToUnicodeString
0x1800166a7  mov     [r15+68h], rax
0x1800166ab  mov     eax, 1
0x1800166b0  add     rsp, 28h
0x1800166b4  pop     r15
0x1800166b6  pop     r14
0x1800166b8  pop     rdi
0x1800166b9  pop     rsi
0x1800166ba  pop     rbp
0x1800166bb  pop     rbx
0x1800166bc  retn
```
