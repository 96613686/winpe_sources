# JobExecution::ProcessUninstallJob(_Job &)

- ea: `0x14000eea4`
- end: `0x14000f006`
- name: `?ProcessUninstallJob@JobExecution@@CAJAEAU_Job@@@Z`
- size: `354`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0x140009964`

## callees

- `0x1400074d4`
- `0x14000775c`
- `0x14000a230`
- `0x14000cd78`
- `0x14000d470`
- `0x14000dab4`
- `0x14000eea4`
- `0x14001104c`
- `0x14001a244`

## string_xrefs

- `0x14000eefc`: `+ Processing %1 uninstall job %2.  Status=%3!d!. RetryStatus=%4!d!. StatusReport=%5!d!.`
- `0x14000efa5`: `Unexpected job status %1!d! for uninstall type job %2.  Reseting back to INITIALIZED state.`

## pseudocode

```c
__int64 __fastcall JobExecution::ProcessUninstallJob(struct _Job *a1)
{
  int v1; // eax
  struct _Job *v2; // rbx
  int v3; // ecx
  unsigned int *v4; // rsi
  struct _Job *v5; // r8
  const wchar_t *v6; // rdx
  bool v7; // zf
  struct _Job *v8; // r8
  int updated; // edi
  int v12; // [rsp+20h] [rbp-18h]
  int v13; // [rsp+28h] [rbp-10h]

  v1 = *((_DWORD *)a1 + 38);
  v2 = a1;
  v3 = *((_DWORD *)a1 + 39);
  v4 = (unsigned int *)((char *)v2 + 148);
  if ( *((_QWORD *)v2 + 3) < 8u )
    v5 = v2;
  else
    v5 = *(struct _Job **)v2;
  v13 = v1;
  v6 = L"Per User";
  if ( *((_DWORD *)v2 + 90) )
    v6 = L"Per Machine";
  v12 = v3;
  LogInfo(
    L"+ Processing %1 uninstall job %2.  Status=%3!d!. RetryStatus=%4!d!. StatusReport=%5!d!.",
    v6,
    v5,
    *v4,
    v12,
    v13);
  if ( (int)*v4 > 48 )
  {
    if ( *v4 == 50 )
    {
LABEL_30:
      updated = JobExecution::HandleJobCheckEnforcement(v2);
      if ( updated < 0 || !JobExecution::ContinueProcessingJob(v2) )
        return (unsigned int)updated;
      return (unsigned int)JobExecution::HandleEnforcementStatusReport(v2);
    }
    if ( *v4 != 55 )
    {
      if ( *v4 != 60 && *v4 != 70 )
      {
        v7 = *v4 == 110;
LABEL_19:
        if ( !v7 )
        {
          if ( *((_QWORD *)v2 + 3) < 8u )
            v8 = v2;
          else
            v8 = *(struct _Job **)v2;
          LogWarn(L"Invalid processing job status %1!d! for job %2", *v4, v8);
          return (unsigned int)JobExecution::SuspendJob(v2);
        }
        goto LABEL_24;
      }
      return (unsigned int)JobExecution::HandleEnforcementStatusReport(v2);
    }
LABEL_28:
    updated = JobExecution::HandleJobRetryEnforcement(v2);
    if ( updated < 0 || !JobExecution::ContinueProcessingJob(v2) )
      return (unsigned int)updated;
    goto LABEL_30;
  }
  if ( *v4 == 48 || *v4 == 10 )
    goto LABEL_28;
  if ( *v4 != 20 && *v4 != 25 && *v4 != 30 && *v4 != 40 )
  {
    v7 = *v4 == 45;
    goto LABEL_19;
  }
LABEL_24:
  updated = JobHelper::UpdateJobStatus(v2, 10, 2147549183LL);
  if ( updated >= 0 )
  {
    if ( *((_QWORD *)v2 + 3) >= 8u )
      v2 = *(struct _Job **)v2;
    LogWarn(L"Unexpected job status %1!d! for uninstall type job %2.  Reseting back to INITIALIZED state.", *v4, v2);
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x14000eea4  mov     [rsp+arg_0], rbx
0x14000eea9  mov     [rsp+arg_8], rsi
0x14000eeae  push    rdi
0x14000eeaf  sub     rsp, 30h
0x14000eeb3  mov     eax, [rcx+98h]
0x14000eeb9  mov     rbx, rcx
0x14000eebc  mov     ecx, [rcx+9Ch]
0x14000eec2  cmp     qword ptr [rbx+18h], 8
0x14000eec7  lea     rsi, [rbx+94h]
0x14000eece  jb      short loc_14000EED5
0x14000eed0  mov     r8, [rbx]
0x14000eed3  jmp     short loc_14000EED8
0x14000eed5  mov     r8, rbx
0x14000eed8  cmp     dword ptr [rbx+168h], 0
0x14000eedf  lea     r9, aPerMachine; "Per Machine"
0x14000eee6  mov     [rsp+38h+var_10], eax
0x14000eeea  lea     rdx, aPerUser; "Per User"
0x14000eef1  cmovnz  rdx, r9
0x14000eef5  mov     [rsp+38h+var_18], ecx
0x14000eef9  mov     r9d, [rsi]
0x14000eefc  lea     rcx, aProcessing1Uni; "+ Processing %1 uninstall job %2.  Stat"...
0x14000ef03  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000ef08  cmp     dword ptr [rsi], 30h ; '0'
0x14000ef0b  mov     edx, 0Ah
0x14000ef10  jg      short loc_14000EF39
0x14000ef12  jz      loc_14000EFB6
0x14000ef18  cmp     [rsi], edx
0x14000ef1a  jz      loc_14000EFB6
0x14000ef20  cmp     dword ptr [rsi], 14h
0x14000ef23  jz      short loc_14000EF85
0x14000ef25  cmp     dword ptr [rsi], 19h
0x14000ef28  jz      short loc_14000EF85
0x14000ef2a  cmp     dword ptr [rsi], 1Eh
0x14000ef2d  jz      short loc_14000EF85
0x14000ef2f  cmp     dword ptr [rsi], 28h ; '('
0x14000ef32  jz      short loc_14000EF85
0x14000ef34  cmp     dword ptr [rsi], 2Dh ; '-'
0x14000ef37  jmp     short loc_14000EF5C
0x14000ef39  cmp     dword ptr [rsi], 32h ; '2'
0x14000ef3c  jz      loc_14000EFD0
0x14000ef42  cmp     dword ptr [rsi], 37h ; '7'
0x14000ef45  jz      short loc_14000EFB6
0x14000ef47  cmp     dword ptr [rsi], 3Ch ; '<'
0x14000ef4a  jz      loc_14000EFEA
0x14000ef50  cmp     dword ptr [rsi], 46h ; 'F'
0x14000ef53  jz      loc_14000EFEA
0x14000ef59  cmp     dword ptr [rsi], 6Eh ; 'n'
0x14000ef5c  jz      short loc_14000EF85
0x14000ef5e  cmp     qword ptr [rbx+18h], 8
0x14000ef63  jb      short loc_14000EF6A
0x14000ef65  mov     r8, [rbx]
0x14000ef68  jmp     short loc_14000EF6D
0x14000ef6a  mov     r8, rbx
0x14000ef6d  mov     edx, [rsi]
0x14000ef6f  lea     rcx, aInvalidProcess; "Invalid processing job status %1!d! for"...
0x14000ef76  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000ef7b  mov     rcx, rbx; struct _Job *
0x14000ef7e  call    ?SuspendJob@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::SuspendJob(_Job &)
0x14000ef83  jmp     short loc_14000EFF2
0x14000ef85  mov     r8d, 8000FFFFh
0x14000ef8b  mov     rcx, rbx
0x14000ef8e  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000ef93  mov     edi, eax
0x14000ef95  test    eax, eax
0x14000ef97  js      short loc_14000EFF4
0x14000ef99  cmp     qword ptr [rbx+18h], 8
0x14000ef9e  jb      short loc_14000EFA3
0x14000efa0  mov     rbx, [rbx]
0x14000efa3  mov     edx, [rsi]
0x14000efa5  lea     rcx, aUnexpectedJobS; "Unexpected job status %1!d! for uninsta"...
0x14000efac  mov     r8, rbx
0x14000efaf  call    ?LogWarn@@YAXPEBGZZ; LogWarn(ushort const *,...)
0x14000efb4  jmp     short loc_14000EFF4
0x14000efb6  mov     rcx, rbx; struct _Job *
0x14000efb9  call    ?HandleJobRetryEnforcement@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobRetryEnforcement(_Job &)
0x14000efbe  mov     edi, eax
0x14000efc0  test    eax, eax
0x14000efc2  js      short loc_14000EFF4
0x14000efc4  mov     rcx, rbx; struct _Job *
0x14000efc7  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000efcc  test    al, al
0x14000efce  jz      short loc_14000EFF4
0x14000efd0  mov     rcx, rbx; struct _Job *
0x14000efd3  call    ?HandleJobCheckEnforcement@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleJobCheckEnforcement(_Job &)
0x14000efd8  mov     edi, eax
0x14000efda  test    eax, eax
0x14000efdc  js      short loc_14000EFF4
0x14000efde  mov     rcx, rbx; struct _Job *
0x14000efe1  call    ?ContinueProcessingJob@JobExecution@@CA_NAEBU_Job@@@Z; JobExecution::ContinueProcessingJob(_Job const &)
0x14000efe6  test    al, al
0x14000efe8  jz      short loc_14000EFF4
0x14000efea  mov     rcx, rbx; struct _Job *
0x14000efed  call    ?HandleEnforcementStatusReport@JobExecution@@CAJAEAU_Job@@@Z; JobExecution::HandleEnforcementStatusReport(_Job &)
0x14000eff2  mov     edi, eax
0x14000eff4  mov     rbx, [rsp+38h+arg_0]
0x14000eff9  mov     eax, edi
0x14000effb  mov     rsi, [rsp+38h+arg_8]
0x14000f000  add     rsp, 30h
0x14000f004  pop     rdi
0x14000f005  retn
```
