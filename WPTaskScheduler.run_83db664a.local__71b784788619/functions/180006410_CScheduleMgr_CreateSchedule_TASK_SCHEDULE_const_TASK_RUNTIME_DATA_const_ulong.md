# CScheduleMgr::CreateSchedule(_TASK_SCHEDULE const *,_TASK_RUNTIME_DATA const *,ulong)

- ea: `0x180006410`
- end: `0x180006774`
- name: `?CreateSchedule@CScheduleMgr@@QEAAJPEBU_TASK_SCHEDULE@@PEBU_TASK_RUNTIME_DATA@@K@Z`
- size: `868`
- prototype: `int(CScheduleMgr *__hidden this, const struct _TASK_SCHEDULE *, const struct _TASK_RUNTIME_DATA *, unsigned int)`
- caller_count: `2`
- callee_count: `16`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180006380`
- `0x18001efc8`

## callees

- `0x180001ea0`
- `0x180002c04`
- `0x180003fa0`
- `0x180004db0`
- `0x180005400`
- `0x180005c30`
- `0x180006410`
- `0x18000677c`
- `0x18000cd60`
- `0x18000e970`
- `0x18000ea40`
- `0x180010094`
- `0x180017370`
- `0x180019bc4`
- `0x18001f3ec`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800064eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065b5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800065b5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CScheduleMgr::CreateSchedule(
        CScheduleMgr *this,
        const struct _TASK_SCHEDULE *a2,
        const struct _TASK_RUNTIME_DATA *a3,
        signed int a4)
{
  signed int v4; // r13d
  const struct _TASK_RUNTIME_DATA *v5; // r10
  __int64 v8; // r9
  int RPCClientSecurityInformation; // esi
  struct _APPCONTAINER_SECURITY_INFO *v10; // rax
  __int64 v11; // rcx
  CSchedule *v12; // rbx
  struct TaskStore *j; // rbp
  __int64 v15; // rcx
  _QWORD *v16; // r8
  struct TaskStore *i; // r15
  __int64 v18; // rax
  __int64 v19; // rcx
  _QWORD *v20; // r8
  __int64 v21; // rax
  struct TaskStore *v22; // rax
  struct _APPCONTAINER_SECURITY_INFO *v23; // r13
  unsigned __int16 *v24; // r8
  struct TaskStore *v25; // rcx
  _QWORD *v26; // rax
  __int64 v27; // rcx
  __int64 v28; // rdx
  _QWORD *v29; // rax
  struct _SCHEDULE_SID *v31; // [rsp+38h] [rbp-190h] BYREF
  struct _APPCONTAINER_SECURITY_INFO *v32; // [rsp+40h] [rbp-188h] BYREF
  struct _TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+50h] [rbp-178h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v34; // [rsp+160h] [rbp-68h] BYREF

  v4 = a4;
  v5 = a3;
  v34.Ptr = (ULONGLONG)a3;
  if ( a2 && (a3 = *(const struct _TASK_RUNTIME_DATA **)a2) != 0 && (v8 = *((_QWORD *)a2 + 2)) != 0 )
  {
    if ( (byte_180030D02 & 2) != 0 )
      McTemplateU0jztt_EventWriteTransfer((unsigned int)v4 >> 31, (_DWORD)a2, (_DWORD)a3, v8, v5 != 0, v4 < 0);
    RPCClientSecurityInformation = -2100363008;
    v10 = (struct _APPCONTAINER_SECURITY_INFO *)operator new(0x130u, (const struct std::nothrow_t *)&std::nothrow);
    v32 = v10;
    if ( v10 )
      v12 = CSchedule::CSchedule(v10);
    else
      v12 = 0;
    if ( v12 )
    {
      j = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      v16 = *(_QWORD **)a2;
      for ( i = *(struct TaskStore **)this; ; i = *(struct TaskStore **)i )
      {
        if ( i == this )
        {
          if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
            McTemplateU0j_EventWriteTransfer(v15, ScheduleNotFoundWarning, v16);
          goto LABEL_20;
        }
        v18 = *((_QWORD *)i + 2) - *v16;
        if ( !v18 )
          v18 = *((_QWORD *)i + 3) - v16[1];
        if ( !v18 )
          break;
      }
      if ( i )
      {
        v31 = 0;
        v32 = 0;
        RPCClientSecurityInformation = TsiGetRPCClientSecurityInformation(&v31, &v32);
        if ( RPCClientSecurityInformation < 0 )
          goto LABEL_30;
        v23 = v32;
        if ( v32 )
          v24 = **(unsigned __int16 ***)v32;
        else
          v24 = 0;
        if ( !CSchedule::IsScheduleOwner(i, *(unsigned __int16 *const *)v31, v24) )
        {
          RPCClientSecurityInformation = -2147024891;
          if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 1) != 0 )
            McTemplateU0q_EventWriteTransfer(v27, (const EVENT_DESCRIPTOR *)SecurityError, 2147942405LL);
        }
        TsiFreeAppContainerSecurityInfo(v23);
        TsiFreeScheduleSid(v31);
        if ( RPCClientSecurityInformation < 0 )
          goto LABEL_30;
        v4 = a4;
      }
LABEL_20:
      TimeInfo::TimeInfo(&TimeZoneInformation);
      RPCClientSecurityInformation = CSchedule::Initialize(
                                       v12,
                                       (const struct TimeInfo *)&TimeZoneInformation,
                                       a2,
                                       (const struct _TASK_RUNTIME_DATA *)v34.Ptr,
                                       *((struct TaskStore **)this + 7),
                                       v4);
      if ( RPCClientSecurityInformation >= 0 )
      {
        v20 = (_QWORD *)((char *)v12 + 16);
        for ( j = *(struct TaskStore **)this; ; j = *(struct TaskStore **)j )
        {
          if ( j == this )
          {
            if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
              McTemplateU0j_EventWriteTransfer(v19, ScheduleNotFoundWarning, v20);
            goto LABEL_28;
          }
          v21 = *((_QWORD *)j + 2) - *v20;
          if ( !v21 )
            v21 = *((_QWORD *)j + 3) - *((_QWORD *)v12 + 3);
          if ( !v21 )
            break;
        }
        if ( !j )
        {
LABEL_28:
          j = v12;
          goto LABEL_29;
        }
        v25 = *(struct TaskStore **)j;
        v26 = (_QWORD *)*((_QWORD *)j + 1);
        *v26 = *(_QWORD *)j;
        *((_QWORD *)v25 + 1) = v26;
LABEL_29:
        v22 = *(struct TaskStore **)this;
        *(_QWORD *)v12 = *(_QWORD *)this;
        *((_QWORD *)v12 + 1) = this;
        *((_QWORD *)v22 + 1) = v12;
        *(_QWORD *)this = v12;
        if ( (*((_BYTE *)v12 + 44) & 1) != 0 && v4 >= 0 )
        {
          RPCClientSecurityInformation = TaskStore::Persist(*((TaskStore **)this + 7), *(const struct _GUID **)a2);
          if ( RPCClientSecurityInformation < 0 )
          {
            v28 = *(_QWORD *)v12;
            v29 = (_QWORD *)*((_QWORD *)v12 + 1);
            *v29 = *(_QWORD *)v12;
            *(_QWORD *)(v28 + 8) = v29;
          }
        }
      }
LABEL_30:
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
      if ( j && j != v12 )
        CSchedule::DestroySchedule(j, 1);
      if ( RPCClientSecurityInformation < 0 )
        CSchedule::DestroySchedule(v12, 1);
    }
    if ( (byte_180030D02 & 4) != 0 )
      McTemplateU0q_EventWriteTransfer(
        v11,
        (const EVENT_DESCRIPTOR *)ConstructScheduleCompleted,
        (unsigned int)RPCClientSecurityInformation);
    return (unsigned int)RPCClientSecurityInformation;
  }
  else
  {
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(
        (__int64)this,
        (const EVENT_DESCRIPTOR *)ErrorNullPointer,
        (__int64)a3,
        1u,
        &v34);
    return 2147500035LL;
  }
}

```

## disassembly

```asm
0x180006410  push    rbx
0x180006412  push    rbp
0x180006413  push    rsi
0x180006414  push    rdi
0x180006415  push    r12
0x180006417  push    r13
0x180006419  push    r14
0x18000641b  push    r15
0x18000641d  sub     rsp, 188h
0x180006424  mov     rax, cs:__security_cookie
0x18000642b  xor     rax, rsp
0x18000642e  mov     [rsp+1C8h+var_58], rax
0x180006436  mov     r13d, r9d
0x180006439  mov     [rsp+1C8h+var_198], r9d
0x18000643e  mov     r10, r8
0x180006441  mov     qword ptr [rsp+1C8h+var_68], r8
0x180006449  mov     rdi, rdx
0x18000644c  mov     r14, rcx
0x18000644f  test    rdx, rdx
0x180006452  jz      loc_18000664F
0x180006458  mov     r8, [rdx]
0x18000645b  test    r8, r8
0x18000645e  jz      loc_18000664F
0x180006464  mov     r9, [rdx+10h]
0x180006468  test    r9, r9
0x18000646b  jz      loc_18000664F
0x180006471  test    cs:byte_180030D02, 2
0x180006478  jnz     loc_180006666
0x18000647e  mov     esi, 82CF0100h
0x180006483  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000648a  mov     ecx, 130h; unsigned __int64
0x18000648f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180006494  mov     [rsp+1C8h+var_188], rax
0x180006499  test    rax, rax
0x18000649c  jz      loc_180006616
0x1800064a2  mov     rcx, rax; this
0x1800064a5  call    ??0CSchedule@@QEAA@XZ; CSchedule::CSchedule(void)
0x1800064aa  mov     rbx, rax
0x1800064ad  test    rbx, rbx
0x1800064b0  jnz     short loc_1800064E5
0x1800064b2  test    cs:byte_180030D02, 4
0x1800064b9  jnz     loc_18000673C
0x1800064bf  mov     eax, esi
0x1800064c1  mov     rcx, [rsp+1C8h+var_58]
0x1800064c9  xor     rcx, rsp; StackCookie
0x1800064cc  call    __security_check_cookie
0x1800064d1  add     rsp, 188h
0x1800064d8  pop     r15
0x1800064da  pop     r14
0x1800064dc  pop     r13
0x1800064de  pop     r12
0x1800064e0  pop     rdi
0x1800064e1  pop     rsi
0x1800064e2  pop     rbp
0x1800064e3  pop     rbx
0x1800064e4  retn
0x1800064e5  xor     ebp, ebp
0x1800064e7  lea     rcx, [r14+10h]; lpCriticalSection
0x1800064eb  call    cs:__imp_EnterCriticalSection
0x1800064f1  mov     r8, [rdi]
0x1800064f4  mov     r15, [r14]
0x1800064f7  cmp     r15, r14
0x1800064fa  jz      short loc_18000651B
0x1800064fc  mov     rax, [r15+10h]
0x180006500  sub     rax, [r8]
0x180006503  jnz     short loc_18000650D
0x180006505  mov     rax, [r15+18h]
0x180006509  sub     rax, [r8+8]
0x18000650d  test    rax, rax
0x180006510  jz      loc_1800065DB
0x180006516  mov     r15, [r15]
0x180006519  jmp     short loc_1800064F7
0x18000651b  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180006522  jnz     loc_1800066E1
0x180006528  lea     rcx, [rsp+1C8h+TimeZoneInformation]; lpTimeZoneInformation
0x18000652d  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x180006532  mov     [rsp+1C8h+var_1A0], r13d; unsigned int
0x180006537  mov     rax, [r14+38h]
0x18000653b  mov     [rsp+1C8h+var_1A8], rax; struct TaskStore *
0x180006540  mov     r9, qword ptr [rsp+1C8h+var_68]; struct _TASK_RUNTIME_DATA *
0x180006548  mov     r8, rdi; struct _TASK_SCHEDULE *
0x18000654b  lea     rdx, [rsp+1C8h+TimeZoneInformation]; struct TimeInfo *
0x180006550  mov     rcx, rbx; this
0x180006553  call    ?Initialize@CSchedule@@QEAAJAEBVTimeInfo@@PEBU_TASK_SCHEDULE@@PEBU_TASK_RUNTIME_DATA@@PEAVTaskStore@@K@Z; CSchedule::Initialize(TimeInfo const &,_TASK_SCHEDULE const *,_TASK_RUNTIME_DATA const *,TaskStore *,ulong)
0x180006558  mov     esi, eax
0x18000655a  test    eax, eax
0x18000655c  js      short loc_1800065B1
0x18000655e  lea     r8, [rbx+10h]
0x180006562  mov     rbp, [r14]
0x180006565  cmp     rbp, r14
0x180006568  jz      loc_18000661D
0x18000656e  mov     rax, [rbp+10h]
0x180006572  sub     rax, [r8]
0x180006575  jnz     short loc_18000657F
0x180006577  mov     rax, [rbp+18h]
0x18000657b  sub     rax, [r8+8]
0x18000657f  test    rax, rax
0x180006582  jz      short loc_18000658A
0x180006584  mov     rbp, [rbp+0]
0x180006588  jmp     short loc_180006565
0x18000658a  test    rbp, rbp
0x18000658d  jnz     loc_18000663B
0x180006593  mov     rbp, rbx
0x180006596  mov     rax, [r14]
0x180006599  mov     [rbx], rax
0x18000659c  mov     [rbx+8], r14
0x1800065a0  mov     [rax+8], rbx
0x1800065a4  mov     [r14], rbx
0x1800065a7  test    byte ptr [rbx+2Ch], 1
0x1800065ab  jnz     loc_1800066F2
0x1800065b1  lea     rcx, [r14+10h]; lpCriticalSection
0x1800065b5  call    cs:__imp_LeaveCriticalSection
0x1800065bb  test    rbp, rbp
0x1800065be  jnz     loc_180006724
0x1800065c4  test    esi, esi
0x1800065c6  jns     loc_1800064B2
0x1800065cc  mov     dl, 1; bool
0x1800065ce  mov     rcx, rbx; this
0x1800065d1  call    ?DestroySchedule@CSchedule@@SAXPEAV1@_N@Z; CSchedule::DestroySchedule(CSchedule *,bool)
0x1800065d6  jmp     loc_1800064B2
0x1800065db  test    r15, r15
0x1800065de  jz      loc_180006528
0x1800065e4  mov     [rsp+1C8h+var_190], rbp
0x1800065e9  mov     [rsp+1C8h+var_188], rbp
0x1800065ee  lea     rdx, [rsp+1C8h+var_188]; struct _APPCONTAINER_SECURITY_INFO **
0x1800065f3  lea     rcx, [rsp+1C8h+var_190]; struct _SCHEDULE_SID **
0x1800065f8  call    ?TsiGetRPCClientSecurityInformation@@YAJPEAPEAU_SCHEDULE_SID@@PEAPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiGetRPCClientSecurityInformation(_SCHEDULE_SID * *,_APPCONTAINER_SECURITY_INFO * *)
0x1800065fd  mov     esi, eax
0x1800065ff  test    eax, eax
0x180006601  js      short loc_1800065B1
0x180006603  mov     r13, [rsp+1C8h+var_188]
0x180006608  test    r13, r13
0x18000660b  jz      short loc_180006686
0x18000660d  mov     rcx, [r13+0]
0x180006611  mov     r8, [rcx]
0x180006614  jmp     short loc_180006689
0x180006616  xor     ebx, ebx
0x180006618  jmp     loc_1800064AD
0x18000661d  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180006624  jz      loc_180006593
0x18000662a  lea     rdx, ScheduleNotFoundWarning
0x180006631  call    McTemplateU0j_EventWriteTransfer
0x180006636  jmp     loc_180006593
0x18000663b  mov     rcx, [rbp+0]
0x18000663f  mov     rax, [rbp+8]
0x180006643  mov     [rax], rcx
0x180006646  mov     [rcx+8], rax
0x18000664a  jmp     loc_180006596
0x18000664f  test    cs:byte_180030D04, 1
0x180006656  jnz     loc_180006750
0x18000665c  mov     eax, 80004003h
0x180006661  jmp     loc_1800064C1
0x180006666  mov     ecx, r13d
0x180006669  shr     ecx, 1Fh
0x18000666c  xor     eax, eax
0x18000666e  test    r10, r10
0x180006671  setnz   al
0x180006674  mov     [rsp+1C8h+var_1A0], ecx
0x180006678  mov     dword ptr [rsp+1C8h+var_1A8], eax
0x18000667c  call    McTemplateU0jztt_EventWriteTransfer
0x180006681  jmp     loc_18000647E
0x180006686  xor     r8d, r8d; unsigned __int16 *
0x180006689  mov     rdx, [rsp+1C8h+var_190]
0x18000668e  mov     rdx, [rdx]; unsigned __int16 *
0x180006691  mov     rcx, r15; this
0x180006694  call    ?IsScheduleOwner@CSchedule@@QEAAHQEAG0@Z; CSchedule::IsScheduleOwner(ushort * const,ushort * const)
0x180006699  test    eax, eax
0x18000669b  jnz     short loc_1800066BD
0x18000669d  mov     esi, 80070005h
0x1800066a2  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 1
0x1800066a9  jz      short loc_1800066BD
0x1800066ab  mov     r8d, 80070005h
0x1800066b1  lea     rdx, SecurityError
0x1800066b8  call    McTemplateU0q_EventWriteTransfer
0x1800066bd  mov     rcx, r13; struct _APPCONTAINER_SECURITY_INFO *
0x1800066c0  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x1800066c5  mov     rcx, [rsp+1C8h+var_190]; struct _SCHEDULE_SID *
0x1800066ca  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x1800066cf  test    esi, esi
0x1800066d1  js      loc_1800065B1
0x1800066d7  mov     r13d, [rsp+1C8h+var_198]
0x1800066dc  jmp     loc_180006528
0x1800066e1  lea     rdx, ScheduleNotFoundWarning
0x1800066e8  call    McTemplateU0j_EventWriteTransfer
0x1800066ed  jmp     loc_180006528
0x1800066f2  test    r13d, r13d
0x1800066f5  js      loc_1800065B1
0x1800066fb  mov     rdx, [rdi]; struct _GUID *
0x1800066fe  mov     rcx, [r14+38h]; this
0x180006702  call    ?Persist@TaskStore@@QEAAJAEBU_GUID@@@Z; TaskStore::Persist(_GUID const &)
0x180006707  mov     esi, eax
0x180006709  test    eax, eax
0x18000670b  jns     loc_1800065B1
0x180006711  mov     rdx, [rbx]
0x180006714  mov     rax, [rbx+8]
0x180006718  mov     [rax], rdx
0x18000671b  mov     [rdx+8], rax
0x18000671f  jmp     loc_1800065B1
0x180006724  cmp     rbp, rbx
0x180006727  jz      loc_1800065C4
0x18000672d  mov     dl, 1; bool
0x18000672f  mov     rcx, rbp; this
0x180006732  call    ?DestroySchedule@CSchedule@@SAXPEAV1@_N@Z; CSchedule::DestroySchedule(CSchedule *,bool)
0x180006737  jmp     loc_1800065C4
0x18000673c  mov     r8d, esi
0x18000673f  lea     rdx, ConstructScheduleCompleted
0x180006746  call    McTemplateU0q_EventWriteTransfer
0x18000674b  jmp     loc_1800064BF
0x180006750  lea     rax, [rsp+1C8h+var_68]
0x180006758  mov     [rsp+1C8h+var_1A8], rax
0x18000675d  mov     r9d, 1
0x180006763  lea     rdx, ErrorNullPointer
0x18000676a  call    McGenEventWrite_EventWriteTransfer
0x18000676f  jmp     loc_18000665C
```
