# AssessmentCore::PerformAssessment(tagOSUpdateAssessment *,ushort * * const)

- ea: `0x180009d40`
- end: `0x180009f59`
- name: `?PerformAssessment@AssessmentCore@@MEAAJPEAUtagOSUpdateAssessment@@QEAPEAG@Z`
- size: `537`
- prototype: `__int64 __fastcall(AssessmentCore *__hidden this, struct tagOSUpdateAssessment *, unsigned __int16 **const)`
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009d40`
- `0x18001752c`
- `0x180018888`
- `0x180018c74`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009ec5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180009ec5`

## string_xrefs

- `0x180009e73`: `Determining security status`

## pseudocode

```c
__int64 __fastcall AssessmentCore::PerformAssessment(
        AssessmentCore *this,
        struct tagOSUpdateAssessment *a2,
        unsigned __int16 **const a3)
{
  int FirstItemInList; // edi
  int v7; // eax
  int v9; // [rsp+68h] [rbp+10h] BYREF
  unsigned __int16 *v10; // [rsp+78h] [rbp+20h] BYREF

  v9 = 0;
  if ( !a2 )
  {
    FirstItemInList = -2147467261;
LABEL_18:
    LogLevel(2u, L"PerformAssessment Failure: 0x%x", (unsigned int)FirstItemInList);
    return (unsigned int)FirstItemInList;
  }
  if ( (*((_BYTE *)this + 96) & 1) == 0 )
    goto LABEL_7;
  LogLevel(4u, L"Determining End of Support");
  FirstItemInList = (*(__int64 (__fastcall **)(AssessmentCore *, int *))(*(_QWORD *)this + 168LL))(this, &v9);
  if ( FirstItemInList < 0 )
    goto LABEL_18;
  if ( !v9 )
    goto LABEL_7;
  LogLevel(4u, L"OS is in End of Support state");
  a2->isEndOfSupport = 1;
  a2->assessmentForCurrent.status = UpdateAssessmentStatus_NotLatestEndOfSupport;
  a2->assessmentForUpToDate.status = UpdateAssessmentStatus_NotLatestEndOfSupport;
  a2->securityStatus = UpdateAssessmentStatus_NotLatestEndOfSupport;
  a2->assessmentForCurrent.impact = UpdateImpactLevel_High;
  a2->assessmentForUpToDate.impact = UpdateImpactLevel_High;
  a2->assessmentForCurrent.daysOutOfDate = -1;
  a2->assessmentForUpToDate.daysOutOfDate = -1;
  if ( !v9 )
  {
LABEL_7:
    LogLevel(4u, L"Determining up to date assessment");
    v7 = (*(__int64 (__fastcall **)(AssessmentCore *, UpdateAssessment *, unsigned __int16 *, _QWORD))(*(_QWORD *)this + 184LL))(
           this,
           &a2->assessmentForUpToDate,
           a3[2],
           *a3);
    FirstItemInList = v7;
    if ( (*((_BYTE *)this + 96) & 2) == 0 && a2->assessmentForUpToDate.status )
    {
      FirstItemInList = -2147024894;
      goto LABEL_18;
    }
    if ( v7 < 0 )
      goto LABEL_18;
    LogLevel(4u, L"Determining current assessment");
    FirstItemInList = (*(__int64 (__fastcall **)(AssessmentCore *, UpdateAssessment *, _QWORD))(*(_QWORD *)this + 176LL))(
                        this,
                        &a2->assessmentForCurrent,
                        *a3);
    if ( FirstItemInList < 0 )
      goto LABEL_18;
    LogLevel(4u, L"Determining security status");
    FirstItemInList = (*(__int64 (__fastcall **)(AssessmentCore *, UpdateAssessmentStatus *, unsigned __int16 *, UpdateAssessment *))(*(_QWORD *)this + 192LL))(
                        this,
                        &a2->securityStatus,
                        a3[3],
                        &a2->assessmentForUpToDate);
    if ( FirstItemInList < 0 )
      goto LABEL_18;
  }
  v10 = 0;
  LogLevel(4u, L"Populating rest of Assessment result");
  GetSystemTimeAsFileTime(&a2->assessmentTime);
  a2->releaseInfoTime = StringToFileTime(a3[5]);
  if ( (int)GetFirstItemInList(*a3, &v10) >= 0 )
  {
    a2->currentOSBuild = v10;
    v10 = 0;
  }
  a2->currentOSReleaseTime = *(FILETIME *)((char *)this + 156);
  FirstItemInList = GetFirstItemInList(a3[2], &v10);
  if ( FirstItemInList >= 0 )
    a2->upToDateOSBuild = v10;
  a2->upToDateOSReleaseTime = *(FILETIME *)((char *)this + 172);
  if ( FirstItemInList < 0 )
    goto LABEL_18;
  return (unsigned int)FirstItemInList;
}

```

## disassembly

```asm
0x180009d40  mov     [rsp+arg_0], rbx
0x180009d45  push    rbp
0x180009d46  push    rsi
0x180009d47  push    rdi
0x180009d48  push    r12
0x180009d4a  push    r14
0x180009d4c  sub     rsp, 30h
0x180009d50  mov     [rsp+58h+arg_8], 0
0x180009d58  mov     r14, r8
0x180009d5b  mov     rbx, rdx
0x180009d5e  mov     rsi, rcx
0x180009d61  test    rdx, rdx
0x180009d64  jnz     short loc_180009D70
0x180009d66  mov     edi, 80004003h
0x180009d6b  jmp     loc_180009F32
0x180009d70  test    byte ptr [rcx+60h], 1
0x180009d74  mov     r12d, 4
0x180009d7a  jbe     short loc_180009DF2
0x180009d7c  lea     rdx, aDeterminingEnd; "Determining End of Support"
0x180009d83  mov     ecx, r12d; unsigned __int8
0x180009d86  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009d8b  mov     rax, [rsi]
0x180009d8e  lea     rdx, [rsp+58h+arg_8]
0x180009d93  mov     rcx, rsi
0x180009d96  mov     rax, [rax+0A8h]
0x180009d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da2  mov     edi, eax
0x180009da4  test    eax, eax
0x180009da6  js      loc_180009F32
0x180009dac  mov     eax, [rsp+58h+arg_8]
0x180009db0  test    eax, eax
0x180009db2  jz      short loc_180009DF2
0x180009db4  lea     rdx, aOsIsInEndOfSup; "OS is in End of Support state"
0x180009dbb  mov     ecx, r12d; unsigned __int8
0x180009dbe  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009dc3  lea     eax, [r12-1]
0x180009dc8  mov     dword ptr [rbx], 1
0x180009dce  mov     [rbx+4], eax
0x180009dd1  mov     [rbx+10h], eax
0x180009dd4  mov     [rbx+1Ch], eax
0x180009dd7  mov     [rbx+8], eax
0x180009dda  mov     [rbx+14h], eax
0x180009ddd  or      eax, 0FFFFFFFFh
0x180009de0  mov     [rbx+0Ch], eax
0x180009de3  mov     [rbx+18h], eax
0x180009de6  mov     eax, [rsp+58h+arg_8]
0x180009dea  test    eax, eax
0x180009dec  jnz     loc_180009EA9
0x180009df2  lea     rdx, aDeterminingUpT; "Determining up to date assessment"
0x180009df9  mov     ecx, r12d; unsigned __int8
0x180009dfc  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009e01  mov     rax, [rsi]
0x180009e04  lea     rbp, [rbx+10h]
0x180009e08  mov     r9, [r14]
0x180009e0b  mov     rdx, rbp
0x180009e0e  mov     r8, [r14+10h]
0x180009e12  mov     rcx, rsi
0x180009e15  mov     rax, [rax+0B8h]
0x180009e1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e21  test    byte ptr [rsi+60h], 2
0x180009e25  mov     edi, eax
0x180009e27  ja      short loc_180009E39
0x180009e29  cmp     dword ptr [rbp+0], 0
0x180009e2d  jz      short loc_180009E39
0x180009e2f  mov     edi, 80070002h
0x180009e34  jmp     loc_180009F32
0x180009e39  test    eax, eax
0x180009e3b  js      loc_180009F32
0x180009e41  lea     rdx, aDeterminingCur; "Determining current assessment"
0x180009e48  mov     ecx, r12d; unsigned __int8
0x180009e4b  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009e50  mov     rax, [rsi]
0x180009e53  lea     rdx, [rbx+4]
0x180009e57  mov     r8, [r14]
0x180009e5a  mov     rcx, rsi
0x180009e5d  mov     rax, [rax+0B0h]
0x180009e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e69  mov     edi, eax
0x180009e6b  test    eax, eax
0x180009e6d  js      loc_180009F32
0x180009e73  lea     rdx, aDeterminingSec; "Determining security status"
0x180009e7a  mov     ecx, r12d; unsigned __int8
0x180009e7d  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009e82  mov     rax, [rsi]
0x180009e85  lea     rdx, [rbx+1Ch]
0x180009e89  mov     r8, [r14+18h]
0x180009e8d  mov     r9, rbp
0x180009e90  mov     rcx, rsi
0x180009e93  mov     rax, [rax+0C0h]
0x180009e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e9f  mov     edi, eax
0x180009ea1  test    eax, eax
0x180009ea3  js      loc_180009F32
0x180009ea9  lea     rdx, aPopulatingRest; "Populating rest of Assessment result"
0x180009eb0  mov     [rsp+58h+arg_18], 0
0x180009eb9  mov     ecx, r12d; unsigned __int8
0x180009ebc  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009ec1  lea     rcx, [rbx+20h]; lpSystemTimeAsFileTime
0x180009ec5  call    cs:__imp_GetSystemTimeAsFileTime
0x180009ecb  mov     rcx, [r14+28h]; unsigned __int16 *
0x180009ecf  call    ?StringToFileTime@@YA?AU_FILETIME@@PEBG@Z; StringToFileTime(ushort const *)
0x180009ed4  mov     [rbx+28h], rax
0x180009ed8  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180009edd  mov     rcx, [r14]; unsigned __int16 *
0x180009ee0  call    ?GetFirstItemInList@@YAJPEBGPEAPEAG@Z; GetFirstItemInList(ushort const *,ushort * *)
0x180009ee5  test    eax, eax
0x180009ee7  js      short loc_180009EFB
0x180009ee9  mov     rax, [rsp+58h+arg_18]
0x180009eee  mov     [rbx+30h], rax
0x180009ef2  mov     [rsp+58h+arg_18], 0
0x180009efb  mov     rax, [rsi+9Ch]
0x180009f02  lea     rdx, [rsp+58h+arg_18]; unsigned __int16 **
0x180009f07  mov     [rbx+38h], rax
0x180009f0b  mov     rcx, [r14+10h]; unsigned __int16 *
0x180009f0f  call    ?GetFirstItemInList@@YAJPEBGPEAPEAG@Z; GetFirstItemInList(ushort const *,ushort * *)
0x180009f14  mov     edi, eax
0x180009f16  test    eax, eax
0x180009f18  js      short loc_180009F23
0x180009f1a  mov     rax, [rsp+58h+arg_18]
0x180009f1f  mov     [rbx+40h], rax
0x180009f23  mov     rax, [rsi+0ACh]
0x180009f2a  mov     [rbx+48h], rax
0x180009f2e  test    edi, edi
0x180009f30  jns     short loc_180009F46
0x180009f32  mov     r8d, edi
0x180009f35  lea     rdx, aPerformassessm; "PerformAssessment Failure: 0x%x"
0x180009f3c  mov     ecx, 2; unsigned __int8
0x180009f41  call    ?LogLevel@@YAXEPEBGZZ; LogLevel(uchar,ushort const *,...)
0x180009f46  mov     rbx, [rsp+58h+arg_0]
0x180009f4b  mov     eax, edi
0x180009f4d  add     rsp, 30h
0x180009f51  pop     r14
0x180009f53  pop     r12
0x180009f55  pop     rdi
0x180009f56  pop     rsi
0x180009f57  pop     rbp
0x180009f58  retn
```
