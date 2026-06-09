# CopyCallbackDataWideToNeutral(_FAX_JOB_PARAMW *,_FAX_COVERPAGE_INFOW *,_FAX_JOB_PARAM_EXW *,_FAX_COVERPAGE_INFO_EXW *,_FAX_PERSONAL_PROFILEW *,_FAX_PERSONAL_PROFILEW *)

- ea: `0x1800166c4`
- end: `0x18001695e`
- name: `?CopyCallbackDataWideToNeutral@@YAHPEAU_FAX_JOB_PARAMW@@PEAU_FAX_COVERPAGE_INFOW@@PEAU_FAX_JOB_PARAM_EXW@@PEAU_FAX_COVERPAGE_INFO_EXW@@PEAU_FAX_PERSONAL_PROFILEW@@4@Z`
- size: `666`
- prototype: `__int64 __fastcall(struct _FAX_JOB_PARAMW *, struct _FAX_COVERPAGE_INFOW *, struct _FAX_JOB_PARAM_EXW *, struct _FAX_COVERPAGE_INFO_EXW *, struct _FAX_PERSONAL_PROFILEW *, struct _FAX_PERSONAL_PROFILEW *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180018a10`

## callees

- `0x1800166c4`
- `0x18002c7bc`
- `0x18003d4ca`

## pseudocode

```c
__int64 __fastcall CopyCallbackDataWideToNeutral(
        struct _FAX_JOB_PARAMW *a1,
        struct _FAX_COVERPAGE_INFOW *a2,
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
  *((_QWORD *)a3 + 4) = StringDup((unsigned __int16 *)a1->DeliveryReportAddress);
  *((_QWORD *)a3 + 10) = StringDup((unsigned __int16 *)a1->DocumentName);
  *((_QWORD *)a5 + 1) = StringDup((unsigned __int16 *)a1->SenderName);
  *((_QWORD *)a5 + 3) = StringDup((unsigned __int16 *)a1->SenderCompany);
  *((_QWORD *)a5 + 10) = StringDup((unsigned __int16 *)a1->SenderDept);
  *((_QWORD *)a5 + 15) = StringDup((unsigned __int16 *)a1->BillingCode);
  *((_QWORD *)a6 + 1) = StringDup((unsigned __int16 *)a1->RecipientName);
  *((_QWORD *)a6 + 2) = StringDup((unsigned __int16 *)a1->RecipientNumber);
  *((_QWORD *)a6 + 16) = StringDup((unsigned __int16 *)a1->Tsid);
  if ( a2 )
  {
    *((_QWORD *)a4 + 1) = StringDup((unsigned __int16 *)a2->CoverPageName);
    *((_QWORD *)a4 + 3) = StringDup((unsigned __int16 *)a2->Note);
    *((_QWORD *)a4 + 4) = StringDup((unsigned __int16 *)a2->Subject);
    *((_QWORD *)a5 + 5) = StringDup((unsigned __int16 *)a2->SdrAddress);
    *((_QWORD *)a5 + 2) = StringDup((unsigned __int16 *)a2->SdrFaxNumber);
    *((_QWORD *)a5 + 4) = StringDup((unsigned __int16 *)a2->SdrAddress);
    *((_QWORD *)a5 + 9) = StringDup((unsigned __int16 *)a2->SdrTitle);
    *((_QWORD *)a5 + 11) = StringDup((unsigned __int16 *)a2->SdrOfficeLocation);
    *((_QWORD *)a5 + 12) = StringDup((unsigned __int16 *)a2->SdrHomePhone);
    *((_QWORD *)a5 + 13) = StringDup((unsigned __int16 *)a2->SdrOfficePhone);
    *((_QWORD *)a6 + 3) = StringDup((unsigned __int16 *)a2->RecCompany);
    *((_QWORD *)a6 + 4) = StringDup((unsigned __int16 *)a2->RecStreetAddress);
    *((_QWORD *)a6 + 5) = StringDup((unsigned __int16 *)a2->RecCity);
    *((_QWORD *)a6 + 6) = StringDup((unsigned __int16 *)a2->RecState);
    *((_QWORD *)a6 + 7) = StringDup((unsigned __int16 *)a2->RecZip);
    *((_QWORD *)a6 + 8) = StringDup((unsigned __int16 *)a2->RecCountry);
    *((_QWORD *)a6 + 9) = StringDup((unsigned __int16 *)a2->RecTitle);
    *((_QWORD *)a6 + 10) = StringDup((unsigned __int16 *)a2->RecDepartment);
    *((_QWORD *)a6 + 11) = StringDup((unsigned __int16 *)a2->RecOfficeLocation);
    *((_QWORD *)a6 + 12) = StringDup((unsigned __int16 *)a2->RecHomePhone);
    *((_QWORD *)a6 + 13) = StringDup((unsigned __int16 *)a2->RecOfficePhone);
  }
  return 1;
}

```

## disassembly

```asm
0x1800166c4  push    rbx
0x1800166c6  push    rbp
0x1800166c7  push    rsi
0x1800166c8  push    rdi
0x1800166c9  push    r14
0x1800166cb  push    r15
0x1800166cd  sub     rsp, 28h
0x1800166d1  mov     rbp, rdx
0x1800166d4  mov     rdi, rcx
0x1800166d7  xor     edx, edx; Val
0x1800166d9  lea     rcx, [r8+4]; void *
0x1800166dd  mov     rbx, r8
0x1800166e0  mov     rsi, r9
0x1800166e3  lea     r8d, [rdx+5Ch]; Size
0x1800166e7  call    memset_0
0x1800166ec  mov     dword ptr [rbx], 60h ; '`'
0x1800166f2  mov     edx, 1
0x1800166f7  mov     eax, [rdi+40h]
0x1800166fa  xor     ecx, ecx
0x1800166fc  mov     [rbx+4], eax
0x1800166ff  movups  xmm0, xmmword ptr [rdi+44h]
0x180016703  movdqu  xmmword ptr [rbx+8], xmm0
0x180016708  mov     eax, [rdi+54h]
0x18001670b  mov     [rbx+18h], eax
0x18001670e  mov     [rbx+28h], edx
0x180016711  mov     eax, [rdi+68h]
0x180016714  mov     [rbx+2Ch], eax
0x180016717  movups  xmm0, xmmword ptr [rdi+70h]
0x18001671b  movups  xmmword ptr [rbx+30h], xmm0
0x18001671f  movsd   xmm1, qword ptr [rdi+80h]
0x180016727  movsd   qword ptr [rbx+40h], xmm1
0x18001672c  test    rbp, rbp
0x18001672f  jz      short loc_18001673A
0x180016731  mov     eax, [rbp+0E8h]
0x180016737  mov     [rbx+58h], eax
0x18001673a  mov     [rsi+8], rcx
0x18001673e  mov     [rsi+10h], rcx
0x180016742  mov     [rsi+18h], rcx
0x180016746  mov     [rsi+20h], rcx
0x18001674a  mov     dword ptr [rsi], 28h ; '('
0x180016750  mov     [rsi+4], edx
0x180016753  test    rbp, rbp
0x180016756  jz      short loc_18001675E
0x180016758  mov     eax, [rbp+10h]
0x18001675b  mov     [rsi+10h], eax
0x18001675e  mov     r14, [rsp+58h+arg_20]
0x180016766  xor     edx, edx; Val
0x180016768  mov     r8d, 84h; Size
0x18001676e  lea     rcx, [r14+4]; void *
0x180016772  call    memset_0
0x180016777  mov     r15, [rsp+58h+arg_28]
0x18001677f  xor     edx, edx; Val
0x180016781  mov     r8d, 84h; Size
0x180016787  mov     dword ptr [r14], 88h
0x18001678e  lea     rcx, [r15+4]; void *
0x180016792  call    memset_0
0x180016797  mov     dword ptr [r15], 88h
0x18001679e  mov     rcx, [rdi+58h]; unsigned __int16 *
0x1800167a2  call    StringDup
0x1800167a7  mov     [rbx+20h], rax
0x1800167ab  mov     rcx, [rdi+60h]; unsigned __int16 *
0x1800167af  call    StringDup
0x1800167b4  mov     [rbx+50h], rax
0x1800167b8  mov     rcx, [rdi+20h]; unsigned __int16 *
0x1800167bc  call    StringDup
0x1800167c1  mov     [r14+8], rax
0x1800167c5  mov     rcx, [rdi+28h]; unsigned __int16 *
0x1800167c9  call    StringDup
0x1800167ce  mov     [r14+18h], rax
0x1800167d2  mov     rcx, [rdi+30h]; unsigned __int16 *
0x1800167d6  call    StringDup
0x1800167db  mov     [r14+50h], rax
0x1800167df  mov     rcx, [rdi+38h]; unsigned __int16 *
0x1800167e3  call    StringDup
0x1800167e8  mov     [r14+78h], rax
0x1800167ec  mov     rcx, [rdi+10h]; unsigned __int16 *
0x1800167f0  call    StringDup
0x1800167f5  mov     [r15+8], rax
0x1800167f9  mov     rcx, [rdi+8]; unsigned __int16 *
0x1800167fd  call    StringDup
0x180016802  mov     [r15+10h], rax
0x180016806  mov     rcx, [rdi+18h]; unsigned __int16 *
0x18001680a  call    StringDup
0x18001680f  mov     [r15+80h], rax
0x180016816  test    rbp, rbp
0x180016819  jz      loc_18001694B
0x18001681f  mov     rcx, [rbp+8]; unsigned __int16 *
0x180016823  call    StringDup
0x180016828  mov     [rsi+8], rax
0x18001682c  mov     rcx, [rbp+0C8h]; unsigned __int16 *
0x180016833  call    StringDup
0x180016838  mov     [rsi+18h], rax
0x18001683c  mov     rcx, [rbp+0D0h]; unsigned __int16 *
0x180016843  call    StringDup
0x180016848  mov     [rsi+20h], rax
0x18001684c  mov     rcx, [rbp+98h]; unsigned __int16 *
0x180016853  call    StringDup
0x180016858  mov     [r14+28h], rax
0x18001685c  mov     rcx, [rbp+88h]; unsigned __int16 *
0x180016863  call    StringDup
0x180016868  mov     [r14+10h], rax
0x18001686c  mov     rcx, [rbp+98h]; unsigned __int16 *
0x180016873  call    StringDup
0x180016878  mov     [r14+20h], rax
0x18001687c  mov     rcx, [rbp+0A0h]; unsigned __int16 *
0x180016883  call    StringDup
0x180016888  mov     [r14+48h], rax
0x18001688c  mov     rcx, [rbp+0B0h]; unsigned __int16 *
0x180016893  call    StringDup
0x180016898  mov     [r14+58h], rax
0x18001689c  mov     rcx, [rbp+0B8h]; unsigned __int16 *
0x1800168a3  call    StringDup
0x1800168a8  mov     [r14+60h], rax
0x1800168ac  mov     rcx, [rbp+0C0h]; unsigned __int16 *
0x1800168b3  call    StringDup
0x1800168b8  mov     [r14+68h], rax
0x1800168bc  mov     rcx, [rbp+28h]; unsigned __int16 *
0x1800168c0  call    StringDup
0x1800168c5  mov     [r15+18h], rax
0x1800168c9  mov     rcx, [rbp+30h]; unsigned __int16 *
0x1800168cd  call    StringDup
0x1800168d2  mov     [r15+20h], rax
0x1800168d6  mov     rcx, [rbp+38h]; unsigned __int16 *
0x1800168da  call    StringDup
0x1800168df  mov     [r15+28h], rax
0x1800168e3  mov     rcx, [rbp+40h]; unsigned __int16 *
0x1800168e7  call    StringDup
0x1800168ec  mov     [r15+30h], rax
0x1800168f0  mov     rcx, [rbp+48h]; unsigned __int16 *
0x1800168f4  call    StringDup
0x1800168f9  mov     [r15+38h], rax
0x1800168fd  mov     rcx, [rbp+50h]; unsigned __int16 *
0x180016901  call    StringDup
0x180016906  mov     [r15+40h], rax
0x18001690a  mov     rcx, [rbp+58h]; unsigned __int16 *
0x18001690e  call    StringDup
0x180016913  mov     [r15+48h], rax
0x180016917  mov     rcx, [rbp+60h]; unsigned __int16 *
0x18001691b  call    StringDup
0x180016920  mov     [r15+50h], rax
0x180016924  mov     rcx, [rbp+68h]; unsigned __int16 *
0x180016928  call    StringDup
0x18001692d  mov     [r15+58h], rax
0x180016931  mov     rcx, [rbp+70h]; unsigned __int16 *
0x180016935  call    StringDup
0x18001693a  mov     [r15+60h], rax
0x18001693e  mov     rcx, [rbp+78h]; unsigned __int16 *
0x180016942  call    StringDup
0x180016947  mov     [r15+68h], rax
0x18001694b  mov     eax, 1
0x180016950  add     rsp, 28h
0x180016954  pop     r15
0x180016956  pop     r14
0x180016958  pop     rdi
0x180016959  pop     rsi
0x18001695a  pop     rbp
0x18001695b  pop     rbx
0x18001695c  retn
```
