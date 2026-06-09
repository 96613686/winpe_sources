# JobExecution::ProcessInstallJob(_Job &)

- ea: `0x14000eae8`
- end: `0x14000ec4e`
- name: `?ProcessInstallJob@JobExecution@@CAJAEAU_Job@@@Z`
- size: `358`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x1400098b0`

## callees

- `0x14000740c`
- `0x1400074d4`
- `0x14000a230`
- `0x14000cd78`
- `0x14000d134`
- `0x14000d470`
- `0x14000d898`
- `0x14000dab4`
- `0x14000eae8`
- `0x14001104c`

## string_xrefs

- `0x14000eb38`: `+ Processing %1 install job %2.  Status=%3!d!. RetryStatus=%4!d!. StatusReport=%5!d!.`

## pseudocode

```c
__int64 __fastcall JobExecution::ProcessInstallJob(struct _Job *a1)
{
  int v1; // eax
  int v3; // ecx
  struct _Job *v4; // r8
  const wchar_t *v5; // rdx
  __int64 v6; // rdx
  struct _Job *v7; // r8
  int v9; // edi

  v1 = *((_DWORD *)a1 + 38);
  v3 = *((_DWORD *)a1 + 39);
  if ( *((_QWORD *)a1 + 3) < 8u )
    v4 = a1;
  else
    v4 = *(struct _Job **)a1;
  v5 = L"Per User";
  if ( *((_DWORD *)a1 + 90) )
    v5 = L"Per Machine";
  LogInfo(
    L"+ Processing %1 install job %2.  Status=%3!d!. RetryStatus=%4!d!. StatusReport=%5!d!.",
    v5,
    v4,
    *((unsigned int *)a1 + 37),
    v3,
    v1);
  v6 = *((unsigned int *)a1 + 37);
  if ( (int)v6 <= 48 )
  {
    if ( (_DWORD)v6 == 48 )
      goto LABEL_28;
    if ( (_DWORD)v6 != 10 )
    {
      if ( (_DWORD)v6 == 20 )
      {
LABEL_26:
        v9 = JobExecution::HandleJobCheckDownload(a1);
        if ( v9 < 0 || !JobExecution::ContinueProcessingJob(a1) )
          return (unsigned int)v9;
        goto LABEL_28;
      }
      if ( (_DWORD)v6 != 25 )
      {
        if ( (_DWORD)v6 == 30 )
          return (unsigned int)JobExecution::HandleEnforcementStatusReport(a1);
        if ( (_DWORD)v6 != 40 && (_DWORD)v6 != 45 )
        {
LABEL_20:
          if ( *((_QWORD *)a1 + 3) < 8u )
            v7 = a1;
          else
            v7 = *(struct _Job **)a1;
          LogError(L"Unknown job status %1!d! for job %2", v6, v7);
          return (unsigned int)JobExecution::SuspendJob(a1);
        }
LABEL_28:
        v9 = JobExecution::HandleJobRetryEnforcement(a1);
        if ( v9 < 0 || !JobExecution::ContinueProcessingJob(a1) )
          return (unsigned int)v9;
        goto LABEL_30;
      }
    }
LABEL_24:
    v9 = JobExecution::HandleJobRetryDownload(a1);
    if ( v9 < 0 || !JobExecution::ContinueProcessingJob(a1) )
      return (unsigned int)v9;
    goto LABEL_26;
  }
  if ( (_DWORD)v6 != 50 )
  {
    if ( (_DWORD)v6 == 55 )
      goto LABEL_28;
    if ( (_DWORD)v6 == 60 || (_DWORD)v6 == 70 )
      return (unsigned int)JobExecution::HandleEnforcementStatusReport(a1);
    if ( (_DWORD)v6 != 110 )
      goto LABEL_20;
    goto LABEL_24;
  }
LABEL_30:
  v9 = JobExecution::HandleJobCheckEnforcement(a1);
  if ( v9 >= 0 && JobExecution::ContinueProcessingJob(a1) )
    return (unsigned int)JobExecution::HandleEnforcementStatusReport(a1);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x14000eae8  mov     [rsp+arg_0], rbx
0x14000eaed  push    rdi
0x14000eaee  sub     rsp, 30h
0x14000eaf2  mov     eax, [rcx+98h]
0x14000eaf8  mov     rbx, rcx
0x14000eafb  mov     ecx, [rcx+9Ch]
0x14000eb01  cmp     qword ptr [rbx+18h], 8
0x14000eb06  jb      short loc_14000EB0D
0x14000eb08  mov     r8, [rbx]
0x14000eb0b  jmp     short loc_14000EB10
0x14000eb0d  mov     r8, rbx
0x14000eb10  cmp     dword ptr [rbx+168h], 0
0x14000eb17  lea     r9, aPerMachine; "Per Machine"
0x14000eb1e  mov     [rsp+38h+var_10], eax
0x14000eb22  lea     rdx, aPerUser; "Per User"
0x14000eb29  cmovnz  rdx, r9
0x14000eb2d  mov     [rsp+38h+var_18], ecx
0x14000eb31  mov     r9d, [rbx+94h]
0x14000eb38  lea     rcx, aProcessing1Ins; "+ Processing %1 install job %2.  Status"...
0x14000eb3f  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000eb44  mov     edx, [rbx+94h]
0x14000eb4a  cmp     edx, 30h ; '0'
0x14000eb4d  jg      short loc_14000EB85
0x14000eb4f  jz      loc_14000EC03
0x14000eb55  cmp     edx, 0Ah
0x14000eb58  jz      short loc_14000EBCF
0x14000eb5a  cmp     edx, 14h
0x14000eb5d  jz      loc_14000EBE9
0x14000eb63  cmp     edx, 19h
0x14000eb66  jz      short loc_14000EBCF
0x14000eb68  cmp     edx, 1Eh
0x14000eb6b  jz      loc_14000EC37
0x14000eb71  cmp     edx, 28h ; '('
0x14000eb74  jz      loc_14000EC03
0x14000eb7a  cmp     edx, 2Dh ; '-'
0x14000eb7d  jz      loc_14000EC03
0x14000eb83  jmp     short loc_14000EBAA
0x14000eb85  cmp     edx, 32h ; '2'
0x14000eb88  jz      loc_14000EC1D
0x14000eb8e  cmp     edx, 37h ; '7'
0x14000eb91  jz      short loc_14000EC03
0x14000eb93  cmp     edx, 3Ch ; '<'
0x14000eb96  jz      loc_14000EC37
0x14000eb9c  cmp     edx, 46h ; 'F'
0x14000eb9f  jz      loc_14000EC37
0x14000eba5  cmp     edx, 6Eh ; 'n'
0x14000eba8  jz      short loc_14000EBCF
0x14000ebaa  cmp     qword ptr [rbx+18h], 8
0x14000ebaf  jb      short loc_14000EBB6
0x14000ebb1  mov     r8, [rbx]
0x14000ebb4  jmp     short loc_14000EBB9
0x14000ebb6  mov     r8, rbx
0x14000ebb9  lea     rcx, aUnknownJobStat; "Unknown job status %1!d! for job %2"
0x14000ebc0  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000ebc5  mov     rcx, rbx; struct _Job *
0x14000ebc8  call    ?SuspendJob@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::SuspendJob(_Job &)
0x14000ebcd  jmp     short loc_14000EC3F
0x14000ebcf  mov     rcx, rbx; struct _Job *
0x14000ebd2  call    ?HandleJobRetryDownload@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobRetryDownload(_Job &)
0x14000ebd7  mov     edi, eax
0x14000ebd9  test    eax, eax
0x14000ebdb  js      short loc_14000EC41
0x14000ebdd  mov     rcx, rbx; struct _Job *
0x14000ebe0  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000ebe5  test    al, al
0x14000ebe7  jz      short loc_14000EC41
0x14000ebe9  mov     rcx, rbx; struct _Job *
0x14000ebec  call    ?HandleJobCheckDownload@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobCheckDownload(_Job &)
0x14000ebf1  mov     edi, eax
0x14000ebf3  test    eax, eax
0x14000ebf5  js      short loc_14000EC41
0x14000ebf7  mov     rcx, rbx; struct _Job *
0x14000ebfa  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000ebff  test    al, al
0x14000ec01  jz      short loc_14000EC41
0x14000ec03  mov     rcx, rbx; struct _Job *
0x14000ec06  call    ?HandleJobRetryEnforcement@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobRetryEnforcement(_Job &)
0x14000ec0b  mov     edi, eax
0x14000ec0d  test    eax, eax
0x14000ec0f  js      short loc_14000EC41
0x14000ec11  mov     rcx, rbx; struct _Job *
0x14000ec14  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000ec19  test    al, al
0x14000ec1b  jz      short loc_14000EC41
0x14000ec1d  mov     rcx, rbx; struct _Job *
0x14000ec20  call    ?HandleJobCheckEnforcement@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobCheckEnforcement(_Job &)
0x14000ec25  mov     edi, eax
0x14000ec27  test    eax, eax
0x14000ec29  js      short loc_14000EC41
0x14000ec2b  mov     rcx, rbx; struct _Job *
0x14000ec2e  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000ec33  test    al, al
0x14000ec35  jz      short loc_14000EC41
0x14000ec37  mov     rcx, rbx; struct _Job *
0x14000ec3a  call    ?HandleEnforcementStatusReport@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleEnforcementStatusReport(_Job &)
0x14000ec3f  mov     edi, eax
0x14000ec41  mov     rbx, [rsp+38h+arg_0]
0x14000ec46  mov     eax, edi
0x14000ec48  add     rsp, 30h
0x14000ec4c  pop     rdi
0x14000ec4d  retn
```
