# WSD::UpdateMonitor::UpdateMonitorTask::IsLastRunWithinExpectedFrequency(bool *)

- ea: `0x180066458`
- end: `0x180066678`
- name: `?IsLastRunWithinExpectedFrequency@UpdateMonitorTask@UpdateMonitor@WSD@@QEAAJPEA_N@Z`
- size: `544`
- prototype: `__int64 __fastcall(WSD::UpdateMonitor::UpdateMonitorTask *__hidden this, bool *)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180062f6c`

## callees

- `0x180004710`
- `0x18000d7fc`
- `0x180010ff0`
- `0x1800658e8`
- `0x180065ec0`
- `0x180066458`
- `0x1800e0598`
- `0x1800e7010`

## import_xrefs

- `KERNEL32!SystemTimeToFileTime` at `0x180066581`
- `KERNEL32!SystemTimeToFileTime` at `0x180066581`
- `KERNEL32!CompareFileTime` at `0x1800665c4`
- `KERNEL32!CompareFileTime` at `0x1800665c4`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006653f`
- `OLEAUT32!__imp_VariantTimeToSystemTime` at `0x18006653f`

## pseudocode

```c
__int64 __fastcall WSD::UpdateMonitor::UpdateMonitorTask::IsLastRunWithinExpectedFrequency(
        WSD::UpdateMonitor::UpdateMonitorTask *this,
        bool *a2)
{
  _QWORD *v3; // rcx
  unsigned int HoursBetweenFileTimes; // ebx
  __int64 v5; // rdx
  __int64 v7; // rcx
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  CommonUtil *v10; // rcx
  unsigned int v11; // [rsp+20h] [rbp-40h] BYREF
  struct _FILETIME FileTime; // [rsp+28h] [rbp-38h] BYREF
  DOUBLE vtime; // [rsp+30h] [rbp-30h] BYREF
  FILETIME FileTime2; // [rsp+38h] [rbp-28h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+40h] [rbp-20h] BYREF

  if ( !a2 )
  {
    v3 = WPP_GLOBAL_Control;
    HoursBetweenFileTimes = -2147024809;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return HoursBetweenFileTimes;
    v5 = 60;
LABEL_5:
    WPP_SF_d(v3[2], v5, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids, HoursBetweenFileTimes);
    return HoursBetweenFileTimes;
  }
  if ( !*((_QWORD *)this + 2) )
  {
    v3 = WPP_GLOBAL_Control;
    HoursBetweenFileTimes = -2147467261;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return HoursBetweenFileTimes;
    v5 = 61;
    goto LABEL_5;
  }
  *a2 = 0;
  v7 = *((_QWORD *)this + 2);
  vtime = 0.0;
  HoursBetweenFileTimes = (*(__int64 (__fastcall **)(__int64, DOUBLE *))(*(_QWORD *)v7 + 120LL))(v7, &vtime);
  if ( (HoursBetweenFileTimes & 0x80000000) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return HoursBetweenFileTimes;
    v5 = 62;
    goto LABEL_5;
  }
  SystemTime = 0;
  if ( !VariantTimeToSystemTime(vtime, &SystemTime) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v9 = 63;
    goto LABEL_27;
  }
  FileTime = 0;
  if ( !SystemTimeToFileTime(&SystemTime, &FileTime) )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v9 = 64;
    goto LABEL_27;
  }
  FileTime2 = CommonUtil::UtilGetSystemTimeAsFileTime(v10);
  if ( CompareFileTime(&FileTime, &FileTime2) != -1 )
  {
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      return 0;
    v9 = 65;
LABEL_27:
    WPP_SF_(v8[2], v9, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids);
    return 0;
  }
  v11 = 0;
  HoursBetweenFileTimes = WSD::UpdateMonitor::UpdateMonitorTask::GetHoursBetweenFileTimes(FileTime2, FileTime, &v11);
  if ( (HoursBetweenFileTimes & 0x80000000) != 0 )
  {
    v3 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      return HoursBetweenFileTimes;
    v5 = 66;
    goto LABEL_5;
  }
  *a2 = v11 <= WSD::UpdateMonitor::UpdateMonitorTask::GetTaskFrequencyInHours() + 24;
  return 0;
}

```

## disassembly

```asm
0x180066458  mov     [rsp-8+arg_10], rbx
0x18006645d  mov     [rsp-8+arg_18], rdi
0x180066462  push    rbp
0x180066463  mov     rbp, rsp
0x180066466  sub     rsp, 60h
0x18006646a  mov     rax, cs:__security_cookie
0x180066471  xor     rax, rsp
0x180066474  mov     [rbp+var_10], rax
0x180066478  mov     rdi, rdx
0x18006647b  test    rdx, rdx
0x18006647e  jnz     short loc_1800664BB
0x180066480  mov     rcx, cs:WPP_GLOBAL_Control
0x180066487  lea     rax, WPP_GLOBAL_Control
0x18006648e  mov     ebx, 80070057h
0x180066493  cmp     rcx, rax
0x180066496  jz      short loc_1800664B4
0x180066498  test    byte ptr [rcx+1Ch], 1
0x18006649c  jz      short loc_1800664B4
0x18006649e  lea     edx, [rdi+3Ch]
0x1800664a1  mov     rcx, [rcx+10h]
0x1800664a5  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x1800664ac  mov     r9d, ebx
0x1800664af  call    WPP_SF_d
0x1800664b4  mov     eax, ebx
0x1800664b6  jmp     loc_18006665A
0x1800664bb  cmp     qword ptr [rcx+10h], 0
0x1800664c0  jnz     short loc_1800664E7
0x1800664c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800664c9  lea     rax, WPP_GLOBAL_Control
0x1800664d0  mov     ebx, 80004003h
0x1800664d5  cmp     rcx, rax
0x1800664d8  jz      short loc_1800664B4
0x1800664da  test    byte ptr [rcx+1Ch], 1
0x1800664de  jz      short loc_1800664B4
0x1800664e0  mov     edx, 3Dh ; '='
0x1800664e5  jmp     short loc_1800664A1
0x1800664e7  mov     byte ptr [rdx], 0
0x1800664ea  xorps   xmm0, xmm0
0x1800664ed  mov     rcx, [rcx+10h]
0x1800664f1  lea     rdx, [rbp+vtime]
0x1800664f5  movsd   [rbp+vtime], xmm0
0x1800664fa  mov     rax, [rcx]
0x1800664fd  mov     rax, [rax+78h]
0x180066501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066506  mov     ebx, eax
0x180066508  test    eax, eax
0x18006650a  jns     short loc_18006652F
0x18006650c  mov     rcx, cs:WPP_GLOBAL_Control
0x180066513  lea     rax, WPP_GLOBAL_Control
0x18006651a  cmp     rcx, rax
0x18006651d  jz      short loc_1800664B4
0x18006651f  test    byte ptr [rcx+1Ch], 1
0x180066523  jz      short loc_1800664B4
0x180066525  mov     edx, 3Eh ; '>'
0x18006652a  jmp     loc_1800664A1
0x18006652f  xorps   xmm0, xmm0
0x180066532  lea     rdx, [rbp+SystemTime]; lpSystemTime
0x180066536  movups  xmmword ptr [rbp+SystemTime.wYear], xmm0
0x18006653a  movsd   xmm0, [rbp+vtime]; vtime
0x18006653f  call    cs:__imp_VariantTimeToSystemTime
0x180066545  test    eax, eax
0x180066547  jnz     short loc_180066571
0x180066549  mov     rcx, cs:WPP_GLOBAL_Control
0x180066550  lea     rax, WPP_GLOBAL_Control
0x180066557  cmp     rcx, rax
0x18006655a  jz      loc_180066658
0x180066560  test    byte ptr [rcx+1Ch], 1
0x180066564  jz      loc_180066658
0x18006656a  mov     edx, 3Fh ; '?'
0x18006656f  jmp     short loc_1800665ED
0x180066571  lea     rdx, [rbp+FileTime]; lpFileTime
0x180066575  mov     qword ptr [rbp+FileTime.dwLowDateTime], 0
0x18006657d  lea     rcx, [rbp+SystemTime]; lpSystemTime
0x180066581  call    cs:__imp_SystemTimeToFileTime
0x180066587  test    eax, eax
0x180066589  jnz     short loc_1800665B3
0x18006658b  mov     rcx, cs:WPP_GLOBAL_Control
0x180066592  lea     rax, WPP_GLOBAL_Control
0x180066599  cmp     rcx, rax
0x18006659c  jz      loc_180066658
0x1800665a2  test    byte ptr [rcx+1Ch], 1
0x1800665a6  jz      loc_180066658
0x1800665ac  mov     edx, 40h ; '@'
0x1800665b1  jmp     short loc_1800665ED
0x1800665b3  call    ?UtilGetSystemTimeAsFileTime@CommonUtil@@YA?AU_FILETIME@@XZ; CommonUtil::UtilGetSystemTimeAsFileTime(void)
0x1800665b8  lea     rdx, [rbp+FileTime2]; lpFileTime2
0x1800665bc  mov     qword ptr [rbp+FileTime2.dwLowDateTime], rax
0x1800665c0  lea     rcx, [rbp+FileTime]; lpFileTime1
0x1800665c4  call    cs:__imp_CompareFileTime
0x1800665ca  cmp     eax, 0FFFFFFFFh
0x1800665cd  jz      short loc_1800665FF
0x1800665cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800665d6  lea     rax, WPP_GLOBAL_Control
0x1800665dd  cmp     rcx, rax
0x1800665e0  jz      short loc_180066658
0x1800665e2  test    byte ptr [rcx+1Ch], 1
0x1800665e6  jz      short loc_180066658
0x1800665e8  mov     edx, 41h ; 'A'
0x1800665ed  mov     rcx, [rcx+10h]
0x1800665f1  lea     r8, WPP_28240c1d7c5b30984e84036dede81aa7_Traceguids
0x1800665f8  call    WPP_SF_
0x1800665fd  jmp     short loc_180066658
0x1800665ff  mov     rdx, qword ptr [rbp+FileTime.dwLowDateTime]; struct _FILETIME
0x180066603  lea     r8, [rbp+var_40]; unsigned int *
0x180066607  mov     rcx, qword ptr [rbp+FileTime2.dwLowDateTime]; struct _FILETIME
0x18006660b  mov     [rbp+var_40], 0
0x180066612  call    ?GetHoursBetweenFileTimes@UpdateMonitorTask@UpdateMonitor@WSD@@SAJU_FILETIME@@0PEAK@Z; WSD::UpdateMonitor::UpdateMonitorTask::GetHoursBetweenFileTimes(_FILETIME,_FILETIME,ulong *)
0x180066617  mov     ebx, eax
0x180066619  test    eax, eax
0x18006661b  jns     short loc_180066648
0x18006661d  mov     rcx, cs:WPP_GLOBAL_Control
0x180066624  lea     rax, WPP_GLOBAL_Control
0x18006662b  cmp     rcx, rax
0x18006662e  jz      loc_1800664B4
0x180066634  test    byte ptr [rcx+1Ch], 4
0x180066638  jz      loc_1800664B4
0x18006663e  mov     edx, 42h ; 'B'
0x180066643  jmp     loc_1800664A1
0x180066648  call    ?GetTaskFrequencyInHours@UpdateMonitorTask@UpdateMonitor@WSD@@SAKXZ; WSD::UpdateMonitor::UpdateMonitorTask::GetTaskFrequencyInHours(void)
0x18006664d  add     eax, 18h
0x180066650  cmp     [rbp+var_40], eax
0x180066653  setbe   al
0x180066656  mov     [rdi], al
0x180066658  xor     eax, eax
0x18006665a  mov     rcx, [rbp+var_10]
0x18006665e  xor     rcx, rsp; StackCookie
0x180066661  call    __security_check_cookie
0x180066666  lea     r11, [rsp+60h+var_s0]
0x18006666b  mov     rbx, [r11+20h]
0x18006666f  mov     rdi, [r11+28h]
0x180066673  mov     rsp, r11
0x180066676  pop     rbp
0x180066677  retn
```
