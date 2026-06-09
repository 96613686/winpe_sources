# JobExecution::HandleJobRetryDownload(_Job &)

- ea: `0x14000d898`
- end: `0x14000daae`
- name: `?HandleJobRetryDownload@JobExecution@@CAJAEAU_Job@@@Z`
- size: `534`
- prototype: `__int64 __fastcall(struct _Job *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000eae8`

## callees

- `0x1400036ac`
- `0x140006480`
- `0x14000740c`
- `0x1400074d4`
- `0x14000d898`
- `0x140010a2c`
- `0x14001309c`
- `0x140013170`
- `0x140018e48`
- `0x1400196dc`
- `0x140019ba8`
- `0x140019c6c`
- `0x140019e94`
- `0x140019fcc`
- `0x14001a244`
- `0x14001a8d0`

## string_xrefs

- `0x14000d8ee`: `Job %1. Download attempt number %2!d!.`

## pseudocode

```c
__int64 __fastcall JobExecution::HandleJobRetryDownload(struct _Job *a1)
{
  struct _Job *v2; // rdx
  int JobConfig; // edi
  int DownloadLocation; // esi
  _QWORD *v5; // rdi
  int started; // eax
  int v7; // ecx
  _QWORD *v8; // r9
  _QWORD *v9; // r8
  _QWORD *v10; // r9
  _QWORD *v11; // r8
  __int64 v12; // rdx
  __int64 v14; // [rsp+30h] [rbp-58h] BYREF
  int v15; // [rsp+38h] [rbp-50h]
  char v16; // [rsp+3Ch] [rbp-4Ch]
  __int64 v17; // [rsp+40h] [rbp-48h]

  v14 = 0;
  v15 = 600;
  v16 = 1;
  v17 = 30;
  ++*((_DWORD *)a1 + 80);
  if ( *((_QWORD *)a1 + 3) < 8u )
    v2 = a1;
  else
    v2 = *(struct _Job **)a1;
  LogInfo(L"Job %1. Download attempt number %2!d!.", v2, *((unsigned int *)a1 + 80));
  JobConfig = JobHelper::GetJobConfig((struct _JobConfig *)&v14);
  if ( JobConfig < 0 || (JobConfig = JobHelper::GetNextDownloadUrl(a1), JobConfig < 0) )
  {
LABEL_30:
    LogError(L"HandleJobRetryDownload() failed.  Error = 0x%1!x!.", (unsigned int)JobConfig);
    if ( (unsigned int)(*((_DWORD *)a1 + 80) + 1) > 0xA )
      JobHelper::UpdateJobStatus(a1, 30, (unsigned int)JobConfig);
    return (unsigned int)JobConfig;
  }
  if ( !*((_QWORD *)a1 + 27) )
  {
    DownloadLocation = JobHelper::GetDownloadLocation(a1);
    if ( DownloadLocation < 0 )
    {
LABEL_8:
      JobConfig = JobHelper::UpdateJobStatus(a1, 25, (unsigned int)DownloadLocation);
      if ( JobConfig >= 0 )
        JobConfig = DownloadLocation;
      goto LABEL_30;
    }
  }
  v5 = (_QWORD *)((char *)a1 + 168);
  started = JobExecution::StartDownload((_QWORD *)a1 + 36, (_QWORD *)a1 + 32, (_QWORD *)a1 + 25, (_QWORD *)a1 + 21);
  DownloadLocation = started;
  if ( started < 0 )
  {
    if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 8) != 0 )
    {
      v8 = (_QWORD *)((char *)a1 + 32);
      if ( *((_QWORD *)a1 + 7) >= 8u )
        v8 = (_QWORD *)*v8;
      v9 = (_QWORD *)((char *)a1 + 72);
      if ( *((_QWORD *)a1 + 12) >= 8u )
        v9 = (_QWORD *)*v9;
      McTemplateU0zzd_EventWriteTransfer(
        v7,
        (unsigned int)UnableToStartAppContentDownload,
        (_DWORD)v9,
        (_DWORD)v8,
        started);
    }
    goto LABEL_8;
  }
  if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x10) != 0 )
  {
    if ( *((_QWORD *)a1 + 24) >= 8u )
      v5 = (_QWORD *)*v5;
    v10 = (_QWORD *)((char *)a1 + 32);
    if ( *((_QWORD *)a1 + 7) >= 8u )
      v10 = (_QWORD *)*v10;
    v11 = (_QWORD *)((char *)a1 + 72);
    if ( *((_QWORD *)a1 + 12) >= 8u )
      v11 = (_QWORD *)*v11;
    McTemplateU0zzz_EventWriteTransfer(
      v7,
      (unsigned int)AppContentDownloadStarted,
      (_DWORD)v11,
      (_DWORD)v10,
      (__int64)v5);
  }
  JobConfig = JobHelper::UpdateBitsJobId(a1);
  if ( JobConfig < 0 )
    goto LABEL_30;
  JobConfig = JobHelper::UpdateJobStatus(a1, 20, 0);
  if ( JobConfig < 0 )
    goto LABEL_30;
  std::wstring::wstring(&v14, L"InProgress");
  JobConfig = JobHelper::UpdateDownloadInstallStatus(a1, &v14);
  LOBYTE(v12) = 1;
  std::wstring::_Tidy(&v14, v12, 0);
  if ( JobConfig >= 0 )
    JobConfig = JobHelper::UpdateDownloadLocation(a1, (__int64)a1 + 32, (const unsigned __int16 *)a1 + 100);
  if ( JobConfig < 0 )
    goto LABEL_30;
  return (unsigned int)JobConfig;
}

```

## disassembly

```asm
0x14000d898  push    rbx
0x14000d89a  push    rbp
0x14000d89b  push    rsi
0x14000d89c  push    rdi
0x14000d89d  sub     rsp, 68h
0x14000d8a1  mov     rax, cs:__security_cookie
0x14000d8a8  xor     rax, rsp
0x14000d8ab  mov     [rsp+88h+var_38], rax
0x14000d8b0  mov     rbx, rcx
0x14000d8b3  mov     [rsp+88h+var_58], 0
0x14000d8bc  mov     [rsp+88h+var_50], 258h
0x14000d8c4  mov     [rsp+88h+var_4C], 1
0x14000d8c9  mov     [rsp+88h+var_48], 1Eh
0x14000d8d2  inc     dword ptr [rcx+140h]
0x14000d8d8  cmp     qword ptr [rcx+18h], 8
0x14000d8dd  jb      short loc_14000D8E4
0x14000d8df  mov     rdx, [rcx]
0x14000d8e2  jmp     short loc_14000D8E7
0x14000d8e4  mov     rdx, rbx
0x14000d8e7  mov     r8d, [rcx+140h]
0x14000d8ee  lea     rcx, aJob1DownloadAt; "Job %1. Download attempt number %2!d!."
0x14000d8f5  call    ?LogInfo@@YAXPEBGZZ; LogInfo(ushort const *,...)
0x14000d8fa  lea     rcx, [rsp+88h+var_58]; struct _JobConfig *
0x14000d8ff  call    ?GetJobConfig@JobHelper@@SAJAEAU_JobConfig@@@Z; JobHelper::GetJobConfig(_JobConfig &)
0x14000d904  mov     edi, eax
0x14000d906  test    eax, eax
0x14000d908  js      loc_14000DA6B
0x14000d90e  mov     rcx, rbx; struct _Job *
0x14000d911  call    ?GetNextDownloadUrl@JobHelper@@SAJAEAU_Job@@@Z; JobHelper::GetNextDownloadUrl(_Job &)
0x14000d916  mov     edi, eax
0x14000d918  test    eax, eax
0x14000d91a  js      loc_14000DA6B
0x14000d920  lea     rbp, [rbx+0C8h]
0x14000d927  cmp     qword ptr [rbp+10h], 0
0x14000d92c  jnz     short loc_14000D95D
0x14000d92e  mov     rcx, rbx; struct _Job *
0x14000d931  call    ?GetDownloadLocation@JobHelper@@SAJAEAU_Job@@@Z; JobHelper::GetDownloadLocation(_Job &)
0x14000d936  mov     esi, eax
0x14000d938  test    eax, eax
0x14000d93a  jns     short loc_14000D95D
0x14000d93c  mov     r8d, esi
0x14000d93f  mov     edx, 19h
0x14000d944  mov     rcx, rbx
0x14000d947  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000d94c  mov     edi, eax
0x14000d94e  test    eax, eax
0x14000d950  js      loc_14000DA6B
0x14000d956  mov     edi, esi
0x14000d958  jmp     loc_14000DA6B
0x14000d95d  lea     rdi, [rbx+0A8h]
0x14000d964  lea     rdx, [rbx+100h]
0x14000d96b  lea     rcx, [rbx+120h]
0x14000d972  mov     r9, rdi
0x14000d975  mov     r8, rbp
0x14000d978  call    ?StartDownload@JobExecution@@CAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@00AEAV23@@Z; JobExecution::StartDownload(std::wstring const &,std::wstring const &,std::wstring const &,std::wstring &)
0x14000d97d  mov     esi, eax
0x14000d97f  test    eax, eax
0x14000d981  jns     short loc_14000D9BA
0x14000d983  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 8
0x14000d98a  jz      short loc_14000D93C
0x14000d98c  lea     r9, [rbx+20h]
0x14000d990  cmp     qword ptr [r9+18h], 8
0x14000d995  jb      short loc_14000D99A
0x14000d997  mov     r9, [r9]
0x14000d99a  lea     r8, [rbx+48h]
0x14000d99e  cmp     qword ptr [r8+18h], 8
0x14000d9a3  jb      short loc_14000D9A8
0x14000d9a5  mov     r8, [r8]
0x14000d9a8  mov     dword ptr [rsp+88h+var_68], esi
0x14000d9ac  lea     rdx, UnableToStartAppContentDownload
0x14000d9b3  call    McTemplateU0zzd_EventWriteTransfer
0x14000d9b8  jmp     short loc_14000D93C
0x14000d9ba  test    cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits, 10h
0x14000d9c1  jz      short loc_14000D9FA
0x14000d9c3  cmp     qword ptr [rdi+18h], 8
0x14000d9c8  jb      short loc_14000D9CD
0x14000d9ca  mov     rdi, [rdi]
0x14000d9cd  lea     r9, [rbx+20h]
0x14000d9d1  cmp     qword ptr [r9+18h], 8
0x14000d9d6  jb      short loc_14000D9DB
0x14000d9d8  mov     r9, [r9]
0x14000d9db  lea     r8, [rbx+48h]
0x14000d9df  cmp     qword ptr [r8+18h], 8
0x14000d9e4  jb      short loc_14000D9E9
0x14000d9e6  mov     r8, [r8]
0x14000d9e9  mov     [rsp+88h+var_68], rdi
0x14000d9ee  lea     rdx, AppContentDownloadStarted
0x14000d9f5  call    McTemplateU0zzz_EventWriteTransfer
0x14000d9fa  mov     rcx, rbx; struct _Job *
0x14000d9fd  call    ?UpdateBitsJobId@JobHelper@@SAJAEAU_Job@@@Z; JobHelper::UpdateBitsJobId(_Job &)
0x14000da02  mov     edi, eax
0x14000da04  test    eax, eax
0x14000da06  js      short loc_14000DA6B
0x14000da08  xor     r8d, r8d
0x14000da0b  lea     edx, [r8+14h]
0x14000da0f  mov     rcx, rbx
0x14000da12  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000da17  mov     edi, eax
0x14000da19  test    eax, eax
0x14000da1b  js      short loc_14000DA6B
0x14000da1d  lea     rdx, aInprogress; "InProgress"
0x14000da24  lea     rcx, [rsp+88h+var_58]
0x14000da29  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@PEBG@Z; std::wstring::wstring(ushort const *)
0x14000da2e  nop
0x14000da2f  lea     rdx, [rsp+88h+var_58]
0x14000da34  mov     rcx, rbx
0x14000da37  call    ?UpdateDownloadInstallStatus@JobHelper@@SAJAEAU_Job@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; JobHelper::UpdateDownloadInstallStatus(_Job &,std::wstring const &)
0x14000da3c  mov     edi, eax
0x14000da3e  xor     r8d, r8d
0x14000da41  mov     dl, 1
0x14000da43  lea     rcx, [rsp+88h+var_58]
0x14000da48  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x14000da4d  mov     eax, edi
0x14000da4f  shr     eax, 1Fh
0x14000da52  test    al, al
0x14000da54  jnz     short loc_14000DA67
0x14000da56  lea     rdx, [rbx+20h]
0x14000da5a  mov     r8, rbp
0x14000da5d  mov     rcx, rbx
0x14000da60  call    ?UpdateDownloadLocation@JobHelper@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV23@0@Z; JobHelper::UpdateDownloadLocation(std::wstring const &,std::wstring &,std::wstring const &)
0x14000da65  mov     edi, eax
0x14000da67  test    edi, edi
0x14000da69  jns     short loc_14000DA96
0x14000da6b  mov     edx, edi
0x14000da6d  lea     rcx, aHandlejobretry_0; "HandleJobRetryDownload() failed.  Error"...
0x14000da74  call    ?LogError@@YAXPEBGZZ; LogError(ushort const *,...)
0x14000da79  mov     eax, [rbx+140h]
0x14000da7f  inc     eax
0x14000da81  cmp     eax, 0Ah
0x14000da84  jbe     short loc_14000DA96
0x14000da86  mov     r8d, edi
0x14000da89  mov     edx, 1Eh
0x14000da8e  mov     rcx, rbx
0x14000da91  call    ?UpdateJobStatus@JobHelper@@SAJAEAU_Job@@W4JobStatus@@K@Z; JobHelper::UpdateJobStatus(_Job &,JobStatus,ulong)
0x14000da96  mov     eax, edi
0x14000da98  mov     rcx, [rsp+88h+var_38]
0x14000da9d  xor     rcx, rsp; StackCookie
0x14000daa0  call    __security_check_cookie
0x14000daa5  add     rsp, 68h
0x14000daa9  pop     rdi
0x14000daaa  pop     rsi
0x14000daab  pop     rbp
0x14000daac  pop     rbx
0x14000daad  retn
```
