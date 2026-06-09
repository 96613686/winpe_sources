# CSchedule::Initialize(TimeInfo const &,_TASK_SCHEDULE const *,_TASK_RUNTIME_DATA const *,TaskStore *,ulong)

- ea: `0x180003fa0`
- end: `0x180004ad1`
- name: `?Initialize@CSchedule@@QEAAJAEBVTimeInfo@@PEBU_TASK_SCHEDULE@@PEBU_TASK_RUNTIME_DATA@@PEAVTaskStore@@K@Z`
- size: `2865`
- prototype: `__int64 __usercall@<rax>(CSchedule *__hidden this@<rcx>, const struct TimeInfo *@<rdx>, const struct _TASK_SCHEDULE *@<r8>, const struct _TASK_RUNTIME_DATA *@<r9>, struct TaskStore *, unsigned int)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006410`

## callees

- `0x1800025b0`
- `0x180003c10`
- `0x180003fa0`
- `0x180004ae0`
- `0x180004b30`
- `0x180004db0`
- `0x180009aa0`
- `0x18000c700`
- `0x18000dc54`
- `0x18000e634`
- `0x18000e6dc`
- `0x18000e970`
- `0x18000ea40`
- `0x18000edc8`
- `0x180010094`
- `0x180010208`
- `0x180014fbc`
- `0x180015068`
- `0x180017370`
- `0x180018498`
- `0x180018560`
- `0x18001fadc`
- `0x18001fb44`
- `0x18001ff70`
- `0x180020c30`
- `0x180022010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180004201`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180004201`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800046a2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800046a2`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800045a3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000467d`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x1800045a3`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x18000467d`

## pseudocode

```c
__int64 __fastcall CSchedule::Initialize(
        CSchedule *this,
        const struct TimeInfo *a2,
        const struct _TASK_SCHEDULE *a3,
        const struct _TASK_RUNTIME_DATA *a4,
        struct TaskStore *a5,
        unsigned int a6)
{
  const struct _TASK_SCHEDULE *v6; // r15
  int v7; // r9d
  __int64 v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rsi
  unsigned __int64 v12; // rsi
  unsigned __int64 v13; // rax
  const wchar_t *v14; // rax
  size_t v15; // r8
  void **v16; // rdi
  size_t v17; // rdx
  wchar_t *v18; // rcx
  HRESULT RPCClientSecurityInformation; // ebx
  size_t *v20; // r8
  unsigned int v21; // edx
  __int64 v22; // rcx
  __int64 v23; // rcx
  void (__fastcall ***v24)(_QWORD, __int64); // rcx
  SecurityContext *v25; // rcx
  void *v26; // rcx
  __int128 v27; // xmm0
  struct _APPCONTAINER_SECURITY_INFO **v29; // rax
  __int64 v30; // rcx
  struct _APPCONTAINER_SECURITY_INFO **v31; // rsi
  int v32; // ecx
  __int128 v33; // xmm0
  int v34; // eax
  __int128 v35; // xmm1
  bool v36; // zf
  struct TimeValue *v37; // rcx
  char v38; // r10
  __int64 v39; // rcx
  __int64 v40; // r8
  __int64 v41; // r9
  struct _TASK_TRIGGER *v42; // r11
  unsigned int v43; // eax
  struct Trigger *v44; // rax
  __int64 v45; // rcx
  _DWORD *v46; // rsi
  __int64 v47; // rcx
  int v48; // r9d
  const SYSTEMTIME *v49; // rbx
  __int64 v50; // rcx
  int v51; // r15d
  const struct _TASK_SCHEDULE *v52; // rsi
  int v53; // r14d
  __int64 v54; // r8
  struct _SCHEDULE_SID *v55; // rdx
  __int128 *v56; // rcx
  __int128 v57; // xmm0
  __int128 v58; // xmm0
  struct Trigger *v59; // rax
  struct _TASK_RUNTIME_DATA *v60; // [rsp+20h] [rbp-E0h]
  const struct _TASK_SCHEDULE *v61; // [rsp+50h] [rbp-B0h] BYREF
  FILETIME FileTime2; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME *v63; // [rsp+60h] [rbp-A0h]
  struct _TASK_RUNTIME_DATA *v64; // [rsp+68h] [rbp-98h]
  __int128 v65; // [rsp+70h] [rbp-90h] BYREF
  __int128 v66; // [rsp+80h] [rbp-80h]
  __int128 v67; // [rsp+90h] [rbp-70h]
  struct _FILETIME FileTime[2]; // [rsp+A0h] [rbp-60h] BYREF
  struct TimeInfo *v69[4]; // [rsp+B0h] [rbp-50h] BYREF
  unsigned int v70; // [rsp+158h] [rbp+58h]

  v64 = a4;
  v6 = a3;
  v7 = *((_DWORD *)this + 10);
  v61 = a3;
  v69[0] = a2;
  if ( v7 != 1 )
  {
    if ( byte_180030D06 < 0 )
      McTemplateU0jqq_EventWriteTransfer((_DWORD)this, (unsigned int)ScheduleStateChange, (_DWORD)this + 16, v7, 1);
    *((_DWORD *)this + 10) = 1;
  }
  *((_DWORD *)this + 22) = 0;
  *((_DWORD *)this + 34) = 0;
  *((_DWORD *)this + 48) = 0;
  *((_DWORD *)this + 52) = 7;
  if ( v6 && a5 )
  {
    v9 = *((_QWORD *)this + 34);
    if ( v9 )
      SecurityContext::`scalar deleting destructor'((SecurityContext *)v9, (unsigned int)a2);
    *((_QWORD *)this + 34) = 0;
    if ( !*((_DWORD *)v6 + 14) )
      goto LABEL_37;
    if ( !*((_QWORD *)v6 + 9) )
      goto LABEL_37;
    if ( !*(_QWORD *)v6 )
      goto LABEL_37;
    v70 = a6 >> 31;
    if ( (~(16 * v70 + 111) & *((_DWORD *)v6 + 2)) != 0 )
      goto LABEL_37;
    v10 = (_WORD *)*((_QWORD *)v6 + 2);
    if ( !v10 )
      goto LABEL_37;
    v9 = 256;
    do
    {
      if ( !*v10 )
        break;
      ++v10;
      --v9;
    }
    while ( v9 );
    v11 = 256 - v9;
    if ( !v9 )
    {
LABEL_37:
      if ( Microsoft_WindowsPhone_TaskSchedulerEnableBits < 0 )
        McGenEventWrite_EventWriteTransfer(v9, InvalidScheduleData, a3, 1, v69);
      RPCClientSecurityInformation = -2147024809;
      v16 = (void **)((char *)this + 32);
      goto LABEL_28;
    }
    *((_OWORD *)this + 1) = *(_OWORD *)*(_QWORD *)v6;
    *((_DWORD *)this + 11) = *((_DWORD *)v6 + 2);
    if ( (byte_180030D02 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v9, ScheduleTimeFormat);
    if ( (byte_180030D08 & 0x40) != 0 )
      McTemplateU0q_EventWriteTransfer(v9, ScheduleNQMMode);
    v12 = v11 + 1;
    v13 = 2 * v12;
    if ( !is_mul_ok(v12, 2u) )
      v13 = -1;
    v14 = (const wchar_t *)operator new[](v13, (const struct std::nothrow_t *)&std::nothrow);
    *((_QWORD *)this + 4) = v14;
    v16 = (void **)((char *)this + 32);
    if ( !v14 )
    {
      RPCClientSecurityInformation = -2147024882;
      goto LABEL_28;
    }
    RPCClientSecurityInformation = StringValidateDestW(v14, v12, v15);
    if ( RPCClientSecurityInformation < 0 )
    {
      if ( v12 )
        *v18 = 0;
    }
    else
    {
      RPCClientSecurityInformation = StringCopyWorkerW(v18, v17, v20, *((STRSAFE_PCNZWCH *)v6 + 2), (size_t)v60);
    }
    if ( RPCClientSecurityInformation < 0 )
      goto LABEL_28;
    v49 = (const SYSTEMTIME *)((char *)v6 + 24);
    LODWORD(v50) = 1601;
    if ( *((_WORD *)v6 + 12) >= 0x641u )
    {
      if ( (*((_BYTE *)this + 44) & 0x40) == 0 )
        *((_WORD *)v6 + 18) = 0;
      v51 = 1;
      v49->wMilliseconds = 0;
    }
    else
    {
      v49->wYear = 0;
      v51 = 0;
    }
    v52 = v61;
    if ( *((_WORD *)v61 + 20) >= 0x641u )
    {
      if ( (*((_BYTE *)this + 44) & 0x40) == 0 )
        *((_WORD *)v61 + 26) = 0;
      v53 = 1;
      *((_WORD *)v52 + 27) = 0;
    }
    else
    {
      *((_WORD *)v61 + 20) = 0;
      v53 = 0;
    }
    FileTime[0] = 0;
    FileTime2 = 0;
    if ( (!v51 || SystemTimeToFileTime(v49, FileTime))
      && (!v53 || SystemTimeToFileTime((const SYSTEMTIME *)((char *)v52 + 40), &FileTime2)) )
    {
      if ( !v51 )
      {
        v6 = v52;
        goto LABEL_101;
      }
      if ( !v53 || CompareFileTime(FileTime, &FileTime2) <= 0 )
      {
        v6 = v52;
        if ( (byte_180030D02 & 0x10) != 0 )
          McTemplateU0hhhhhhh_EventWriteTransfer(
            v50,
            (unsigned int)StartTimeDate,
            v49->wYear,
            *((unsigned __int16 *)v52 + 13),
            *((_WORD *)v52 + 15),
            *((_WORD *)v52 + 16),
            *((_WORD *)v52 + 17),
            *((_WORD *)v52 + 18),
            *((_WORD *)v52 + 19));
        TimeValue::Set((LPSYSTEMTIME)this + 3, FileTime);
LABEL_101:
        if ( v53 )
        {
          if ( (byte_180030D02 & 0x10) != 0 )
            McTemplateU0hhhhhhh_EventWriteTransfer(
              v50,
              (unsigned int)EndTimeDate,
              *((unsigned __int16 *)v52 + 20),
              *((unsigned __int16 *)v6 + 21),
              *((_WORD *)v6 + 23),
              *((_WORD *)v6 + 24),
              *((_WORD *)v6 + 25),
              *((_WORD *)v6 + 26),
              *((_WORD *)v6 + 27));
          TimeValue::Set((LPSYSTEMTIME)this + 6, &FileTime2);
        }
        v29 = (struct _APPCONTAINER_SECURITY_INFO **)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
        FileTime2 = (FILETIME)v29;
        v31 = v29;
        if ( v29 )
        {
          *v29 = 0;
          v29[1] = 0;
          *((_BYTE *)v29 + 16) = 0;
          *((_QWORD *)this + 34) = v29;
          if ( v64 && (v55 = (struct _SCHEDULE_SID *)*((_QWORD *)v64 + 2)) != 0 && v70 )
          {
            RPCClientSecurityInformation = SecurityContext::Initialize(
                                             (SecurityContext *)v29,
                                             v55,
                                             *((struct _APPCONTAINER_SECURITY_INFO **)v64 + 3));
          }
          else if ( *((_BYTE *)v29 + 16) )
          {
            RPCClientSecurityInformation = -2147467260;
          }
          else
          {
            RPCClientSecurityInformation = TsiGetRPCClientSecurityInformation(v29, v29 + 1);
            if ( RPCClientSecurityInformation >= 0 )
              *((_BYTE *)v31 + 16) = 1;
          }
          if ( RPCClientSecurityInformation >= 0 )
          {
            RPCClientSecurityInformation = Action::ActionFactory(
                                             this,
                                             *((struct _TASK_ACTION *const *)v6 + 9),
                                             (struct Action **)this + 27);
            if ( RPCClientSecurityInformation < 0 )
              goto LABEL_28;
            if ( v70
              && (*(unsigned int (__fastcall **)(_QWORD))(**((_QWORD **)this + 27) + 8LL))(*((_QWORD *)this + 27)) == 2 )
            {
              *((_DWORD *)this + 11) |= 2u;
            }
            v32 = *((_DWORD *)this + 11);
            DWORD2(v67) = 1;
            if ( (v32 & 8) != 0 )
            {
              v33 = *((_OWORD *)v69[0] + 14);
              v66 = *((_OWORD *)v69[0] + 15);
              LODWORD(v67) = *((_DWORD *)v69[0] + 64);
              v34 = *((_DWORD *)v69[0] + 65);
            }
            else
            {
              v33 = *((_OWORD *)v69[0] + 11);
              v66 = *((_OWORD *)v69[0] + 12);
              LODWORD(v67) = *((_DWORD *)v69[0] + 52);
              v34 = *((_DWORD *)v69[0] + 53);
            }
            DWORD1(v67) = v34;
            v35 = v67;
            v36 = (v32 & 0x40) == 0;
            v37 = (CSchedule *)((char *)this + 152);
            *(_OWORD *)((char *)this + 152) = v33;
            *(_OWORD *)((char *)this + 168) = v66;
            *(_OWORD *)((char *)this + 184) = v35;
            if ( v36 )
              AlignMinuteGranularity(v37);
            else
              AlignSecondGranularity(v37);
            v38 = byte_180030D02;
            v39 = *((unsigned __int16 *)this + 80);
            v40 = *((unsigned __int16 *)this + 82);
            v41 = *((unsigned __int16 *)this + 83);
            if ( (byte_180030D02 & 0x10) != 0 )
            {
              McTemplateU0hhhhhhh_EventWriteTransfer(
                v39,
                (unsigned int)CreateTimeDate,
                *((unsigned __int16 *)this + 76),
                *((unsigned __int16 *)this + 77),
                *((_WORD *)this + 79),
                v39,
                *((_WORD *)this + 81),
                v40,
                v41);
              v38 = byte_180030D02;
            }
            v42 = (struct _TASK_TRIGGER *)*((_QWORD *)v6 + 8);
            if ( v42 )
            {
              if ( *(_DWORD *)&v42->cbTriggerSize == 5 )
              {
                if ( (v38 & 0x40) != 0 )
                {
                  LODWORD(v61) = 5;
                  v69[2] = (struct TimeInfo *)&v61;
                  v69[3] = (struct TimeInfo *)4;
                  McGenEventWrite_EventWriteTransfer(v39, L"5", v40, 2, v69);
                }
              }
              else
              {
                *(_QWORD *)&v67 = 0;
                DWORD2(v67) = 0;
                v65 = 0;
                v66 = 0u;
                if ( *((_DWORD *)this + 22) && (unsigned int)operator>((char *)this + 48, (char *)this + 152, v40, v41) )
                {
                  v57 = *v56;
                  v66 = *((_OWORD *)this + 4);
                  *(_QWORD *)&v67 = *((_QWORD *)this + 10);
                  v65 = v57;
                  DWORD2(v67) = 1;
                }
                v43 = 0;
                if ( v70 )
                  v43 = 2;
                v44 = Trigger::Alloc(
                        this,
                        v42,
                        (CSchedule *)((char *)this + 152),
                        (const struct TimeValue *)&v65,
                        v64,
                        0,
                        v43);
                *((_QWORD *)this + 25) = v44;
                if ( v44 )
                {
                  v46 = (_DWORD *)((char *)this + 136);
                  v47 = **((unsigned int **)v6 + 8);
LABEL_63:
                  *((_DWORD *)this + 52) = v47;
                  *((_QWORD *)this + 1) = this;
                  *(_QWORD *)this = this;
                  *((_DWORD *)this + 37) = *((_DWORD *)v6 + 14);
                  if ( (byte_180030D02 & 8) != 0 )
                  {
                    McTemplateU0q_EventWriteTransfer(v47, MaxRuncount);
                    if ( (byte_180030D02 & 8) != 0 )
                      McTemplateU0q_EventWriteTransfer(v47, ScheduleFlags);
                  }
                  if ( !*((_DWORD *)this + 22) || !(unsigned int)operator<((char *)this + 152, (char *)this + 48) )
                  {
                    if ( !*v46 || (unsigned int)operator<((char *)this + 152, (char *)this + 96) )
                    {
                      v48 = *((_DWORD *)this + 10);
                      if ( v48 != 3 )
                      {
                        if ( byte_180030D06 < 0 )
                          McTemplateU0jqq_EventWriteTransfer(
                            v47,
                            (unsigned int)ScheduleStateChange,
                            (_DWORD)this + 16,
                            v48,
                            3);
                        *((_DWORD *)this + 10) = 3;
                      }
                      CSchedule::TimeTransitionsCallback(this, v69[0], 0);
                    }
                    else
                    {
                      CSchedule::SetScheduleState(this, 5);
                    }
                    return (unsigned int)RPCClientSecurityInformation;
                  }
                  v27 = *((_OWORD *)this + 3);
                  v66 = *((_OWORD *)this + 4);
                  *(_QWORD *)&v67 = *((_QWORD *)this + 10);
                  v65 = v27;
                  DWORD2(v67) = 1;
                  RPCClientSecurityInformation = CSchedule::SetNextTransitionTimer((__int64)this, (__int64 *)&v65);
                  CSchedule::SetScheduleState(this, ((RPCClientSecurityInformation >> 31) & 5u) + 2);
                  if ( RPCClientSecurityInformation >= 0 )
                    return (unsigned int)RPCClientSecurityInformation;
LABEL_28:
                  CSchedule::SetScheduleState(this, 7);
                  if ( (byte_180030D01 & 1) != 0 )
                    McTemplateU0j_EventWriteTransfer(v22, InitializeScheduleFailedGuid, *(_QWORD *)v6);
                  v23 = *((_QWORD *)this + 27);
                  if ( v23 )
                    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v23 + 64LL))(v23, 1);
                  v24 = (void (__fastcall ***)(_QWORD, __int64))*((_QWORD *)this + 25);
                  *((_QWORD *)this + 27) = 0;
                  if ( v24 )
                    (**v24)(v24, 1);
                  v25 = (SecurityContext *)*((_QWORD *)this + 34);
                  *((_QWORD *)this + 25) = 0;
                  if ( v25 )
                    SecurityContext::`scalar deleting destructor'(v25, v21);
                  v26 = *v16;
                  *((_QWORD *)this + 34) = 0;
                  operator delete[](v26);
                  *v16 = 0;
                  return (unsigned int)RPCClientSecurityInformation;
                }
                if ( (byte_180030D02 & 0x40) != 0 )
                  goto LABEL_115;
              }
            }
            else
            {
              if ( !*((_DWORD *)this + 22)
                || (v46 = (_DWORD *)((char *)this + 136), !*((_DWORD *)this + 34))
                || !(unsigned int)operator==((char *)this + 48, (char *)this + 96) )
              {
                RPCClientSecurityInformation = -2100362987;
                if ( (v38 & 0x20) != 0 )
                  McGenEventWrite_EventWriteTransfer(v39, InvalidTimes, v40, 1, v69);
                goto LABEL_28;
              }
              v58 = *((_OWORD *)this + 3);
              v63 = FileTime;
              FileTime2 = (FILETIME)5LL;
              *(_OWORD *)&FileTime[0].dwLowDateTime = v58;
              v59 = Trigger::Alloc(
                      this,
                      (struct _TASK_TRIGGER *)&FileTime2,
                      (CSchedule *)((char *)this + 152),
                      (CSchedule *)((char *)this + 48),
                      v64,
                      0,
                      2 * v70);
              *((_QWORD *)this + 25) = v59;
              if ( v59 )
              {
                *((_DWORD *)this + 20) = 1;
                v47 = 5;
                *((_DWORD *)this + 21) = 1;
                *((_DWORD *)this + 22) = 1;
                *((_QWORD *)this + 16) = 1;
                *v46 = 1;
                goto LABEL_63;
              }
              if ( (byte_180030D02 & 0x40) != 0 )
              {
LABEL_115:
                McTemplateU0q_EventWriteTransfer(v45, L"5");
                RPCClientSecurityInformation = -2100363001;
                goto LABEL_28;
              }
            }
            RPCClientSecurityInformation = -2100363001;
            goto LABEL_28;
          }
        }
        else
        {
          *((_QWORD *)this + 34) = 0;
          RPCClientSecurityInformation = -2147024882;
        }
        if ( byte_180030D02 < 0 )
          McTemplateU0q_EventWriteTransfer(v30, FailedToEstablishSecurityCredentials);
        goto LABEL_28;
      }
    }
    RPCClientSecurityInformation = -2100362987;
    if ( (byte_180030D02 & 0x20) != 0 )
      McGenEventWrite_EventWriteTransfer(v50, InvalidTimes, v54, 1, v69);
    v6 = v52;
    goto LABEL_28;
  }
  CSchedule::SetScheduleState(this, 7);
  return 2147500035LL;
}

```

## disassembly

```asm
0x180003fa0  push    rbp
0x180003fa2  push    r13
0x180003fa4  push    r15
0x180003fa6  lea     rbp, [rsp-10h]
0x180003fab  sub     rsp, 110h
0x180003fb2  mov     rax, cs:__security_cookie
0x180003fb9  xor     rax, rsp
0x180003fbc  mov     [rbp+20h+var_50], rax
0x180003fc0  mov     [rsp+120h+var_B8], r9
0x180003fc5  mov     r15, r8
0x180003fc8  mov     r9d, [rcx+28h]
0x180003fcc  mov     r13, rcx
0x180003fcf  mov     [rsp+120h+var_D0], r8
0x180003fd4  mov     [rbp+20h+var_70], rdx
0x180003fd8  cmp     r9d, 1
0x180003fdc  jz      short loc_180003FF3
0x180003fde  cmp     cs:byte_180030D06, 0
0x180003fe5  jl      loc_1800045CB
0x180003feb  mov     dword ptr [r13+28h], 1
0x180003ff3  mov     dword ptr [r13+58h], 0
0x180003ffb  mov     dword ptr [r13+88h], 0
0x180004006  mov     dword ptr [r13+0C0h], 0
0x180004011  mov     dword ptr [r13+0D0h], 7
0x18000401c  test    r15, r15
0x18000401f  jz      loc_180004ABA
0x180004025  cmp     [rbp+20h+arg_20], 0
0x18000402a  jz      loc_180004ABA
0x180004030  mov     rcx, [r13+110h]; this
0x180004037  mov     [rsp+120h+var_18], rbx
0x18000403f  test    rcx, rcx
0x180004042  jnz     loc_1800045E8
0x180004048  mov     [rsp+120h+var_20], rsi
0x180004050  mov     [rsp+120h+var_28], rdi
0x180004058  mov     qword ptr [r13+110h], 0
0x180004063  cmp     dword ptr [r15+38h], 0
0x180004068  mov     [rsp+120h+var_30], r12
0x180004070  mov     [rsp+120h+var_38], r14
0x180004078  jz      loc_180004210
0x18000407e  cmp     qword ptr [r15+48h], 0
0x180004083  jz      loc_180004210
0x180004089  mov     rdx, [r15]
0x18000408c  test    rdx, rdx
0x18000408f  jz      loc_180004210
0x180004095  mov     eax, [rbp+20h+arg_28]
0x180004098  shr     eax, 1Fh
0x18000409b  mov     [rbp+20h+arg_28], eax
0x18000409e  shl     eax, 4
0x1800040a1  add     eax, 6Fh ; 'o'
0x1800040a4  not     eax
0x1800040a6  test    [r15+8], eax
0x1800040aa  jnz     loc_180004210
0x1800040b0  mov     rax, [r15+10h]
0x1800040b4  test    rax, rax
0x1800040b7  jz      loc_180004210
0x1800040bd  mov     esi, 100h
0x1800040c2  mov     ecx, esi
0x1800040c4  cmp     word ptr [rax], 0
0x1800040c8  jz      short loc_1800040D4
0x1800040ca  add     rax, 2
0x1800040ce  sub     rcx, 1
0x1800040d2  jnz     short loc_1800040C4
0x1800040d4  sub     rsi, rcx
0x1800040d7  xor     eax, eax
0x1800040d9  test    rcx, rcx
0x1800040dc  cmovz   rsi, rax
0x1800040e0  jz      loc_180004210
0x1800040e6  movups  xmm0, xmmword ptr [rdx]
0x1800040e9  movups  xmmword ptr [r13+10h], xmm0
0x1800040ee  mov     r8d, [r15+8]
0x1800040f2  mov     [r13+2Ch], r8d
0x1800040f6  test    cs:byte_180030D02, 8
0x1800040fd  jnz     loc_1800045F2
0x180004103  test    cs:byte_180030D08, 40h
0x18000410a  jnz     loc_180004607
0x180004110  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180004117  inc     rsi
0x18000411a  mov     eax, 2
0x18000411f  mul     rsi
0x180004122  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180004129  cmovb   rax, rcx
0x18000412d  mov     rcx, rax; unsigned __int64
0x180004130  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180004135  mov     [r13+20h], rax
0x180004139  lea     rdi, [r13+20h]
0x18000413d  mov     rcx, rax; pszDest
0x180004140  test    rax, rax
0x180004143  jz      loc_180004A90
0x180004149  mov     rdx, rsi; cchDest
0x18000414c  call    StringValidateDestW
0x180004151  mov     ebx, eax
0x180004153  test    eax, eax
0x180004155  js      loc_180004620
0x18000415b  mov     r9, [r15+10h]; pszSrc
0x18000415f  call    StringCopyWorkerW
0x180004164  mov     ebx, eax
0x180004166  test    ebx, ebx
0x180004168  jns     loc_180004556
0x18000416e  mov     edx, 7
0x180004173  mov     rcx, r13
0x180004176  call    ?SetScheduleState@CSchedule@@AEAAJW4_SCHEDULE_STATE@@@Z; CSchedule::SetScheduleState(_SCHEDULE_STATE)
0x18000417b  test    cs:byte_180030D01, 1
0x180004182  jz      short loc_180004193
0x180004184  mov     r8, [r15]
0x180004187  lea     rdx, InitializeScheduleFailedGuid
0x18000418e  call    McTemplateU0j_EventWriteTransfer
0x180004193  mov     rcx, [r13+0D8h]
0x18000419a  test    rcx, rcx
0x18000419d  jz      short loc_1800041B0
0x18000419f  mov     rax, [rcx]
0x1800041a2  mov     edx, 1
0x1800041a7  mov     rax, [rax+40h]
0x1800041ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041b0  mov     rcx, [r13+0C8h]
0x1800041b7  mov     qword ptr [r13+0D8h], 0
0x1800041c2  test    rcx, rcx
0x1800041c5  jz      short loc_1800041D7
0x1800041c7  mov     rax, [rcx]
0x1800041ca  mov     edx, 1
0x1800041cf  mov     rax, [rax]
0x1800041d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041d7  mov     rcx, [r13+110h]; this
0x1800041de  mov     qword ptr [r13+0C8h], 0
0x1800041e9  test    rcx, rcx
0x1800041ec  jz      short loc_1800041F3
0x1800041ee  call    ??_GSecurityContext@@QEAAPEAXI@Z; SecurityContext::`scalar deleting destructor'(uint)
0x1800041f3  mov     rcx, [rdi]
0x1800041f6  mov     qword ptr [r13+110h], 0
0x180004201  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180004207  mov     qword ptr [rdi], 0
0x18000420e  jmp     short loc_180004284
0x180004210  cmp     cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 0
0x180004217  jl      loc_180004A9A
0x18000421d  mov     ebx, 80070057h
0x180004222  lea     rdi, [r13+20h]
0x180004226  jmp     loc_18000416E
0x18000422b  mov     rax, [r13+40h]
0x18000422f  lea     rdx, [rsp+120h+var_B0]
0x180004234  movups  xmm0, xmmword ptr [r13+30h]
0x180004239  mov     qword ptr [rbp+20h+var_A0], rax
0x18000423d  mov     rcx, r13
0x180004240  mov     rax, [r13+48h]
0x180004244  mov     qword ptr [rbp+20h+var_A0+8], rax
0x180004248  mov     eax, [r13+50h]
0x18000424c  mov     dword ptr [rbp+20h+var_90], eax
0x18000424f  mov     eax, [r13+54h]
0x180004253  mov     dword ptr [rbp+20h+var_90+4], eax
0x180004256  movups  [rsp+120h+var_B0], xmm0
0x18000425b  mov     dword ptr [rbp+20h+var_90+8], 1
0x180004262  call    ?SetNextTransitionTimer@CSchedule@@AEAAJVTimeValue@@@Z; CSchedule::SetNextTransitionTimer(TimeValue)
0x180004267  mov     edx, eax
0x180004269  mov     rcx, r13
0x18000426c  sar     edx, 1Fh
0x18000426f  mov     ebx, eax
0x180004271  and     edx, 5
0x180004274  add     edx, 2
0x180004277  call    ?SetScheduleState@CSchedule@@AEAAJW4_SCHEDULE_STATE@@@Z; CSchedule::SetScheduleState(_SCHEDULE_STATE)
0x18000427c  test    ebx, ebx
0x18000427e  js      loc_18000416E
0x180004284  mov     r14, [rsp+120h+var_38]
0x18000428c  mov     eax, ebx
0x18000428e  mov     rbx, [rsp+120h+var_18]
0x180004296  mov     r12, [rsp+120h+var_30]
0x18000429e  mov     rdi, [rsp+120h+var_28]
0x1800042a6  mov     rsi, [rsp+120h+var_20]
0x1800042ae  mov     rcx, [rbp+20h+var_50]
0x1800042b2  xor     rcx, rsp; StackCookie
0x1800042b5  call    __security_check_cookie
0x1800042ba  add     rsp, 110h
0x1800042c1  pop     r15
0x1800042c3  pop     r13
0x1800042c5  pop     rbp
0x1800042c6  retn
0x1800042c7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800042ce  mov     ecx, 18h; unsigned __int64
0x1800042d3  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800042d8  mov     qword ptr [rsp+120h+FileTime2.dwLowDateTime], rax
0x1800042dd  mov     rsi, rax
0x1800042e0  test    rax, rax
0x1800042e3  jz      loc_180004A5F
0x1800042e9  mov     qword ptr [rax], 0
0x1800042f0  mov     qword ptr [rax+8], 0
0x1800042f8  mov     byte ptr [rax+10h], 0
0x1800042fc  mov     [r13+110h], rax
0x180004303  test    rax, rax
0x180004306  jz      loc_180004A6A
0x18000430c  mov     rax, [rsp+120h+var_B8]
0x180004311  mov     r14d, [rbp+20h+arg_28]
0x180004315  test    rax, rax
0x180004318  jnz     loc_18000479D
0x18000431e  cmp     byte ptr [rsi+10h], 0
0x180004322  jnz     loc_1800047C6
0x180004328  lea     rdx, [rsi+8]; struct _APPCONTAINER_SECURITY_INFO **
0x18000432c  mov     rcx, rsi; struct _SCHEDULE_SID **
0x18000432f  call    ?TsiGetRPCClientSecurityInformation@@YAJPEAPEAU_SCHEDULE_SID@@PEAPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiGetRPCClientSecurityInformation(_SCHEDULE_SID * *,_APPCONTAINER_SECURITY_INFO * *)
0x180004334  mov     ebx, eax
0x180004336  test    eax, eax
0x180004338  js      short loc_18000433E
0x18000433a  mov     byte ptr [rsi+10h], 1
0x18000433e  test    ebx, ebx
0x180004340  js      loc_180004A6F
0x180004346  mov     rdx, [r15+48h]; struct _TASK_ACTION *
0x18000434a  lea     r8, [r13+0D8h]; struct Action **
0x180004351  mov     rcx, r13; struct CSchedule *
0x180004354  call    ?ActionFactory@Action@@SAJPEAVCSchedule@@QEAU_TASK_ACTION@@PEAPEAV1@@Z; Action::ActionFactory(CSchedule *,_TASK_ACTION * const,Action * *)
0x180004359  mov     ebx, eax
0x18000435b  test    eax, eax
0x18000435d  js      loc_18000416E
0x180004363  test    r14d, r14d
0x180004366  jnz     loc_1800047D0
0x18000436c  mov     ecx, [r13+2Ch]
0x180004370  mov     rdx, [rbp+20h+var_70]
0x180004374  mov     dword ptr [rbp+20h+var_90+8], 1
0x18000437b  test    cl, 8
0x18000437e  jnz     loc_1800047F5
0x180004384  mov     rax, [rdx+0C0h]
0x18000438b  movups  xmm0, xmmword ptr [rdx+0B0h]
0x180004392  mov     qword ptr [rbp+20h+var_A0], rax
0x180004396  mov     rax, [rdx+0C8h]
0x18000439d  mov     qword ptr [rbp+20h+var_A0+8], rax
0x1800043a1  mov     eax, [rdx+0D0h]
0x1800043a7  mov     dword ptr [rbp+20h+var_90], eax
0x1800043aa  mov     eax, [rdx+0D4h]
0x1800043b0  lea     r14, [r13+98h]
0x1800043b7  mov     dword ptr [rbp+20h+var_90+4], eax
0x1800043ba  movups  xmm1, [rbp+20h+var_90]
0x1800043be  test    cl, 40h
0x1800043c1  mov     rcx, r14; struct TimeValue *
0x1800043c4  movups  xmmword ptr [r14], xmm0
0x1800043c8  movups  xmm0, [rbp+20h+var_A0]
0x1800043cc  movups  xmmword ptr [r14+10h], xmm0
0x1800043d1  movups  xmmword ptr [r14+20h], xmm1
0x1800043d6  jz      loc_180004508
0x1800043dc  call    ?AlignSecondGranularity@@YAXAEAVTimeValue@@@Z; AlignSecondGranularity(TimeValue &)
0x1800043e1  movzx   r10d, cs:byte_180030D02
0x1800043e9  movzx   eax, word ptr [r14+6]
0x1800043ee  movzx   ecx, word ptr [r14+8]
0x1800043f3  movzx   edx, word ptr [r14+0Ah]
0x1800043f8  movzx   r8d, word ptr [r14+0Ch]
0x1800043fd  movzx   r9d, word ptr [r14+0Eh]
0x180004402  test    r10b, 10h
0x180004406  jnz     loc_180004826
0x18000440c  mov     r11, [r15+40h]
0x180004410  test    r11, r11
0x180004413  jz      loc_1800048DB
0x180004419  cmp     dword ptr [r11], 5
0x18000441d  jz      loc_180004512
0x180004423  xor     esi, esi
0x180004425  xor     eax, eax
0x180004427  xorps   xmm0, xmm0
0x18000442a  mov     qword ptr [rbp+20h+var_90], rsi
0x18000442e  mov     dword ptr [rbp+20h+var_90+8], esi
0x180004431  movups  [rsp+120h+var_B0], xmm0
0x180004436  mov     qword ptr [rbp+20h+var_A0], rax
0x18000443a  mov     qword ptr [rbp+20h+var_A0+8], rax
0x18000443e  cmp     [r13+58h], eax
0x180004442  jnz     loc_180004863
0x180004448  mov     r9, [rsp+120h+var_B8]
0x18000444d  mov     eax, esi
0x18000444f  cmp     [rbp+20h+arg_28], esi
0x180004452  mov     ecx, 2
0x180004457  mov     r8, r14; struct TimeValue *
0x18000445a  mov     rdx, r11; struct _TASK_TRIGGER *
0x18000445d  cmovnz  eax, ecx
0x180004460  mov     rcx, r13; void *
0x180004463  mov     [rsp+120h+var_F0], eax; unsigned int
0x180004467  mov     [rsp+120h+var_F8], sil; char
0x18000446c  mov     [rsp+120h+var_100], r9; struct _TASK_RUNTIME_DATA *
0x180004471  lea     r9, [rsp+120h+var_B0]; struct TimeValue *
0x180004476  call    ?Alloc@Trigger@@SAPEAV1@PEAXPEAU_TASK_TRIGGER@@AEBVTimeValue@@2PEAU_TASK_RUNTIME_DATA@@EK@Z; Trigger::Alloc(void *,_TASK_TRIGGER *,TimeValue const &,TimeValue const &,_TASK_RUNTIME_DATA *,uchar,ulong)
0x18000447b  mov     [r13+0C8h], rax
0x180004482  test    rax, rax
0x180004485  jz      loc_1800048A9
0x18000448b  mov     rax, [r15+40h]
0x18000448f  lea     rsi, [r13+88h]
0x180004496  mov     ecx, [rax]
0x180004498  mov     [r13+0D0h], ecx
0x18000449f  mov     [r13+8], r13
0x1800044a3  mov     [r13+0], r13
0x1800044a7  mov     r8d, [r15+38h]
0x1800044ab  mov     [r13+94h], r8d
0x1800044b2  movzx   eax, cs:byte_180030D02
0x1800044b9  test    al, 8
0x1800044bb  jnz     loc_1800049A4
0x1800044c1  cmp     dword ptr [r13+58h], 0
0x1800044c6  jnz     loc_1800049D4
0x1800044cc  cmp     dword ptr [rsi], 0
0x1800044cf  jnz     loc_1800049ED
0x1800044d5  mov     r9d, [r13+28h]
0x1800044d9  cmp     r9d, 3
0x1800044dd  jz      short loc_1800044F4
0x1800044df  cmp     cs:byte_180030D06, 0
0x1800044e6  jl      loc_180004A13
0x1800044ec  mov     dword ptr [r13+28h], 3
0x1800044f4  mov     rdx, [rbp+20h+var_70]; struct TimeInfo *
0x1800044f8  xor     r8d, r8d; int *
0x1800044fb  mov     rcx, r13; this
0x1800044fe  call    ?TimeTransitionsCallback@CSchedule@@QEAAJAEBVTimeInfo@@PEAH@Z; CSchedule::TimeTransitionsCallback(TimeInfo const &,int *)
0x180004503  jmp     loc_180004284
0x180004508  call    ?AlignMinuteGranularity@@YAXAEAVTimeValue@@@Z; AlignMinuteGranularity(TimeValue &)
0x18000450d  jmp     loc_1800043E1
  ... truncated ...
```
