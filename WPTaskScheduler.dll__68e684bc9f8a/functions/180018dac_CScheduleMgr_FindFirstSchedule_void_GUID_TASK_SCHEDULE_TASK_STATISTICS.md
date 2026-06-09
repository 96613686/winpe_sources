# CScheduleMgr::FindFirstSchedule(void * *,_GUID *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *)

- ea: `0x180018dac`
- end: `0x180019105`
- name: `?FindFirstSchedule@CScheduleMgr@@QEAAJPEAPEAXPEAU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@@Z`
- size: `857`
- prototype: `__int64 __fastcall(CScheduleMgr *__hidden this, void **, struct _GUID *, struct _TASK_SCHEDULE **, struct _TASK_STATISTICS **)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800175f0`

## callees

- `0x180002c04`
- `0x180004db0`
- `0x180005400`
- `0x18000cd60`
- `0x18000e970`
- `0x18000ea40`
- `0x180018dac`
- `0x1800192ec`
- `0x18001ffc0`
- `0x180020c30`

## import_xrefs

- `msvcrt!free` at `0x180018f7a`
- `msvcrt!free` at `0x180019056`
- `msvcrt!free` at `0x18001905f`
- `msvcrt!free` at `0x180018f7a`
- `msvcrt!free` at `0x180019056`
- `msvcrt!free` at `0x18001905f`
- `msvcrt!malloc` at `0x180018f16`
- `msvcrt!malloc` at `0x180018f66`
- `msvcrt!malloc` at `0x180018f16`
- `msvcrt!malloc` at `0x180018f66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e6b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180018e6b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001906c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019097`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018ee1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f2b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180018f87`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001906c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180019097`

## pseudocode

```c
__int64 __fastcall CScheduleMgr::FindFirstSchedule(
        CScheduleMgr *this,
        void **a2,
        struct _GUID *a3,
        struct _TASK_SCHEDULE **a4,
        struct _TASK_STATISTICS **a5)
{
  struct _SCHEDULE_SID *v6; // r15
  struct _APPCONTAINER_SECURITY_INFO *v7; // r14
  const unsigned __int16 *v9; // rcx
  __int64 v10; // r8
  int v11; // r12d
  __int64 v12; // rcx
  int RPCClientSecurityInformation; // ebx
  __int64 v14; // r8
  __int64 v15; // rcx
  CSchedule *v16; // r11
  unsigned int v17; // esi
  unsigned __int16 *v18; // r8
  __int64 v19; // rcx
  __int64 v20; // r8
  _DWORD *v21; // rax
  _DWORD *v22; // rdi
  __int64 v23; // rcx
  __int64 v24; // r8
  _OWORD *v25; // rax
  __int64 v26; // rcx
  _OWORD *v27; // rbx
  CSchedule *i; // r11
  unsigned __int16 *v29; // r8
  _OWORD *v30; // rcx
  struct _SCHEDULE_SID *v32; // [rsp+30h] [rbp-40h] BYREF
  struct _APPCONTAINER_SECURITY_INFO *v33; // [rsp+38h] [rbp-38h] BYREF
  struct _TASK_STATISTICS **v34; // [rsp+40h] [rbp-30h]
  struct _TASK_SCHEDULE **v35; // [rsp+48h] [rbp-28h]
  _QWORD v36[2]; // [rsp+50h] [rbp-20h] BYREF

  v6 = 0;
  v36[0] = a3;
  v7 = 0;
  v34 = a5;
  v32 = 0;
  v33 = 0;
  v35 = a4;
  if ( TsiCheckCallerCapabilities((const unsigned __int16 *)this) >= 0 || (v11 = 0, TsiCheckCallerCapabilities(v9) >= 0) )
    v11 = 1;
  if ( a2 && a3 )
  {
    RPCClientSecurityInformation = TsiGetRPCClientSecurityInformation(&v32, &v33);
    if ( RPCClientSecurityInformation < 0 )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(v12, FailedRetrievingCallerSID, v14, 1, v36);
      v6 = v32;
      v7 = v33;
      goto LABEL_50;
    }
    EnterCriticalSection(&CriticalSection);
    v16 = (CSchedule *)g_ScheduleMgr;
    v6 = v32;
    v17 = 0;
    v7 = v33;
    while ( v16 != (CSchedule *)&g_ScheduleMgr )
    {
      if ( v11
        || (!v7 ? (v18 = 0) : (v18 = **(unsigned __int16 ***)v7),
            CSchedule::IsScheduleOwner(v16, *(unsigned __int16 *const *)v6, v18)) )
      {
        ++v17;
      }
      v16 = *(CSchedule **)v16;
    }
    if ( (byte_180030D05 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v15, FindScheduleCount, v17);
    if ( !v17 )
    {
      RPCClientSecurityInformation = -2100362995;
      LeaveCriticalSection(&CriticalSection);
      if ( (byte_180030D05 & 0x10) != 0 )
        McGenEventWrite_EventWriteTransfer(v19, FoundNoSchedules, v20, 1, v36);
      goto LABEL_50;
    }
    v21 = malloc(0x10u);
    v22 = v21;
    if ( !v21 )
    {
      LeaveCriticalSection(&CriticalSection);
      RPCClientSecurityInformation = -2147024882;
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) == 0 )
        goto LABEL_50;
      v24 = 16;
LABEL_27:
      McTemplateU0q_EventWriteTransfer(v23, MemoryAllocationError, v24);
      goto LABEL_50;
    }
    *((_QWORD *)v21 + 1) = 0;
    v25 = malloc(16LL * v17);
    *(_QWORD *)v22 = v25;
    v27 = v25;
    if ( !v25 )
    {
      free(v22);
      LeaveCriticalSection(&CriticalSection);
      RPCClientSecurityInformation = -2147024882;
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 2) == 0 )
        goto LABEL_50;
      v24 = 16 * v17;
      goto LABEL_27;
    }
    for ( i = (CSchedule *)g_ScheduleMgr; i != (CSchedule *)&g_ScheduleMgr; i = *(CSchedule **)i )
    {
      if ( !v11 )
      {
        v29 = v7 ? **(unsigned __int16 ***)v7 : 0LL;
        if ( !CSchedule::IsScheduleOwner(i, *(unsigned __int16 *const *)v6, v29) )
          continue;
      }
      *v27++ = *((_OWORD *)i + 1);
    }
    v22[2] = v17;
    v22[3] = 0;
    if ( (byte_180030D05 & 8) != 0 )
      McTemplateU0q_EventWriteTransfer(v26, FindIndexIs, 0);
    if ( (v35 || v34)
      && (RPCClientSecurityInformation = CScheduleMgr::GetSchedule(
                                           (CScheduleMgr *)&g_ScheduleMgr,
                                           (const struct _GUID *)(*(_QWORD *)v22 + 16LL * (unsigned int)v22[3]),
                                           v35,
                                           v34,
                                           0),
          RPCClientSecurityInformation < 0) )
    {
      free(*(void **)v22);
      free(v22);
      LeaveCriticalSection(&CriticalSection);
    }
    else
    {
      v30 = (_OWORD *)(*(_QWORD *)v22 + 16LL * (unsigned int)v22[3]++);
      *(_OWORD *)v36[0] = *v30;
      LeaveCriticalSection(&CriticalSection);
      RPCClientSecurityInformation = 0;
      *a2 = v22;
    }
  }
  else
  {
    *a2 = 0;
    if ( (byte_180030D04 & 1) != 0 )
      McGenEventWrite_EventWriteTransfer(v9, ErrorNullPointer, v10, 1, v36);
    RPCClientSecurityInformation = -2147467261;
  }
LABEL_50:
  TsiFreeScheduleSid(v6);
  TsiFreeAppContainerSecurityInfo(v7);
  return (unsigned int)RPCClientSecurityInformation;
}

```

## disassembly

```asm
0x180018dac  mov     [rsp-38h+arg_0], rbx
0x180018db1  push    rbp
0x180018db2  push    rsi
0x180018db3  push    rdi
0x180018db4  push    r12
0x180018db6  push    r13
0x180018db8  push    r14
0x180018dba  push    r15
0x180018dbc  mov     rbp, rsp
0x180018dbf  sub     rsp, 70h
0x180018dc3  mov     rax, cs:__security_cookie
0x180018dca  xor     rax, rsp
0x180018dcd  mov     [rbp+var_10], rax
0x180018dd1  mov     rax, [rbp+arg_20]
0x180018dd5  mov     rbx, r8
0x180018dd8  xor     r15d, r15d
0x180018ddb  mov     [rbp+var_20], rbx
0x180018ddf  xor     r14d, r14d
0x180018de2  mov     [rbp+var_30], rax
0x180018de6  mov     [rbp+var_40], r15
0x180018dea  mov     r13, rdx
0x180018ded  mov     [rbp+var_38], r14
0x180018df1  mov     [rbp+var_28], r9
0x180018df5  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180018dfa  lea     edi, [r15+1]
0x180018dfe  test    eax, eax
0x180018e00  jns     short loc_180018E0E
0x180018e02  xor     r12d, r12d
0x180018e05  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180018e0a  test    eax, eax
0x180018e0c  js      short loc_180018E11
0x180018e0e  mov     r12d, edi
0x180018e11  test    r13, r13
0x180018e14  jz      loc_1800190A5
0x180018e1a  test    rbx, rbx
0x180018e1d  jz      loc_1800190A5
0x180018e23  lea     rdx, [rbp+var_38]; struct _APPCONTAINER_SECURITY_INFO **
0x180018e27  lea     rcx, [rbp+var_40]; struct _SCHEDULE_SID **
0x180018e2b  call    ?TsiGetRPCClientSecurityInformation@@YAJPEAPEAU_SCHEDULE_SID@@PEAPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiGetRPCClientSecurityInformation(_SCHEDULE_SID * *,_APPCONTAINER_SECURITY_INFO * *)
0x180018e30  mov     ebx, eax
0x180018e32  test    eax, eax
0x180018e34  jns     short loc_180018E64
0x180018e36  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, dil
0x180018e3d  jz      short loc_180018E57
0x180018e3f  lea     rax, [rbp+var_20]
0x180018e43  mov     r9d, edi
0x180018e46  lea     rdx, FailedRetrievingCallerSID
0x180018e4d  mov     [rsp+70h+var_50], rax
0x180018e52  call    McGenEventWrite_EventWriteTransfer
0x180018e57  mov     r15, [rbp+var_40]
0x180018e5b  mov     r14, [rbp+var_38]
0x180018e5f  jmp     loc_1800190CF
0x180018e64  lea     rcx, CriticalSection; lpCriticalSection
0x180018e6b  call    cs:__imp_EnterCriticalSection
0x180018e71  mov     r11, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180018e78  lea     rbx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180018e7f  mov     r15, [rbp+var_40]
0x180018e83  xor     esi, esi
0x180018e85  mov     r14, [rbp+var_38]
0x180018e89  jmp     short loc_180018EB4
0x180018e8b  test    r12d, r12d
0x180018e8e  jnz     short loc_180018EAF
0x180018e90  test    r14, r14
0x180018e93  jz      short loc_180018E9D
0x180018e95  mov     rax, [r14]
0x180018e98  mov     r8, [rax]
0x180018e9b  jmp     short loc_180018EA0
0x180018e9d  xor     r8d, r8d; unsigned __int16 *
0x180018ea0  mov     rdx, [r15]; unsigned __int16 *
0x180018ea3  mov     rcx, r11; this
0x180018ea6  call    ?IsScheduleOwner@CSchedule@@QEAAHQEAG0@Z; CSchedule::IsScheduleOwner(ushort * const,ushort * const)
0x180018eab  test    eax, eax
0x180018ead  jz      short loc_180018EB1
0x180018eaf  add     esi, edi
0x180018eb1  mov     r11, [r11]
0x180018eb4  cmp     r11, rbx
0x180018eb7  jnz     short loc_180018E8B
0x180018eb9  test    cs:byte_180030D05, 8
0x180018ec0  jz      short loc_180018ED1
0x180018ec2  mov     r8d, esi
0x180018ec5  lea     rdx, FindScheduleCount
0x180018ecc  call    McTemplateU0q_EventWriteTransfer
0x180018ed1  test    esi, esi
0x180018ed3  jnz     short loc_180018F11
0x180018ed5  lea     rcx, CriticalSection; lpCriticalSection
0x180018edc  mov     ebx, 82CF010Dh
0x180018ee1  call    cs:__imp_LeaveCriticalSection
0x180018ee7  test    cs:byte_180030D05, 10h
0x180018eee  jz      loc_1800190CF
0x180018ef4  lea     rax, [rbp+var_20]
0x180018ef8  mov     r9d, edi
0x180018efb  lea     rdx, FoundNoSchedules
0x180018f02  mov     [rsp+70h+var_50], rax
0x180018f07  call    McGenEventWrite_EventWriteTransfer
0x180018f0c  jmp     loc_1800190CF
0x180018f11  mov     ecx, 10h; Size
0x180018f16  call    cs:__imp_malloc
0x180018f1c  mov     rdi, rax
0x180018f1f  test    rax, rax
0x180018f22  jnz     short loc_180018F58
0x180018f24  lea     rcx, CriticalSection; lpCriticalSection
0x180018f2b  call    cs:__imp_LeaveCriticalSection
0x180018f31  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x180018f38  mov     ebx, 8007000Eh
0x180018f3d  jz      loc_1800190CF
0x180018f43  lea     r8d, [rdi+10h]
0x180018f47  lea     rdx, MemoryAllocationError
0x180018f4e  call    McTemplateU0q_EventWriteTransfer
0x180018f53  jmp     loc_1800190CF
0x180018f58  mov     ecx, esi
0x180018f5a  shl     rcx, 4; Size
0x180018f5e  mov     qword ptr [rax+8], 0
0x180018f66  call    cs:__imp_malloc
0x180018f6c  mov     [rdi], rax
0x180018f6f  mov     rbx, rax
0x180018f72  test    rax, rax
0x180018f75  jnz     short loc_180018FA7
0x180018f77  mov     rcx, rdi; Block
0x180018f7a  call    cs:__imp_free
0x180018f80  lea     rcx, CriticalSection; lpCriticalSection
0x180018f87  call    cs:__imp_LeaveCriticalSection
0x180018f8d  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 2
0x180018f94  mov     ebx, 8007000Eh
0x180018f99  jz      loc_1800190CF
0x180018f9f  shl     esi, 4
0x180018fa2  mov     r8d, esi
0x180018fa5  jmp     short loc_180018F47
0x180018fa7  mov     r11, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180018fae  lea     rax, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180018fb5  jmp     short loc_180018FF2
0x180018fb7  test    r12d, r12d
0x180018fba  jnz     short loc_180018FE2
0x180018fbc  test    r14, r14
0x180018fbf  jz      short loc_180018FC9
0x180018fc1  mov     rax, [r14]
0x180018fc4  mov     r8, [rax]
0x180018fc7  jmp     short loc_180018FCC
0x180018fc9  xor     r8d, r8d; unsigned __int16 *
0x180018fcc  mov     rdx, [r15]; unsigned __int16 *
0x180018fcf  mov     rcx, r11; this
0x180018fd2  call    ?IsScheduleOwner@CSchedule@@QEAAHQEAG0@Z; CSchedule::IsScheduleOwner(ushort * const,ushort * const)
0x180018fd7  test    eax, eax
0x180018fd9  lea     rax, ?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180018fe0  jz      short loc_180018FEF
0x180018fe2  movups  xmm0, xmmword ptr [r11+10h]
0x180018fe7  movdqu  xmmword ptr [rbx], xmm0
0x180018feb  add     rbx, 10h
0x180018fef  mov     r11, [r11]
0x180018ff2  cmp     r11, rax
0x180018ff5  jnz     short loc_180018FB7
0x180018ff7  mov     [rdi+8], esi
0x180018ffa  mov     dword ptr [rdi+0Ch], 0
0x180019001  test    cs:byte_180030D05, 8
0x180019008  jz      short loc_180019019
0x18001900a  xor     r8d, r8d
0x18001900d  lea     rdx, FindIndexIs
0x180019014  call    McTemplateU0q_EventWriteTransfer
0x180019019  mov     rax, [rbp+var_28]
0x18001901d  mov     r9, [rbp+var_30]; struct _TASK_STATISTICS **
0x180019021  test    rax, rax
0x180019024  jnz     short loc_18001902B
0x180019026  test    r9, r9
0x180019029  jz      short loc_180019074
0x18001902b  mov     edx, [rdi+0Ch]
0x18001902e  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x180019035  shl     rdx, 4
0x180019039  mov     r8, rax; struct _TASK_SCHEDULE **
0x18001903c  add     rdx, [rdi]; struct _GUID *
0x18001903f  mov     [rsp+70h+var_50], 0; struct _TASK_RUNTIME_DATA **
0x180019048  call    ?GetSchedule@CScheduleMgr@@QEAAJPEBU_GUID@@PEAPEAU_TASK_SCHEDULE@@PEAPEAU_TASK_STATISTICS@@PEAPEAU_TASK_RUNTIME_DATA@@@Z; CScheduleMgr::GetSchedule(_GUID const *,_TASK_SCHEDULE * *,_TASK_STATISTICS * *,_TASK_RUNTIME_DATA * *)
0x18001904d  mov     ebx, eax
0x18001904f  test    eax, eax
0x180019051  jns     short loc_180019074
0x180019053  mov     rcx, [rdi]; Block
0x180019056  call    cs:__imp_free
0x18001905c  mov     rcx, rdi; Block
0x18001905f  call    cs:__imp_free
0x180019065  lea     rcx, CriticalSection; lpCriticalSection
0x18001906c  call    cs:__imp_LeaveCriticalSection
0x180019072  jmp     short loc_1800190CF
0x180019074  mov     eax, [rdi+0Ch]
0x180019077  mov     ecx, eax
0x180019079  shl     rcx, 4
0x18001907d  add     rcx, [rdi]
0x180019080  inc     eax
0x180019082  mov     [rdi+0Ch], eax
0x180019085  mov     rax, [rbp+var_20]
0x180019089  movups  xmm0, xmmword ptr [rcx]
0x18001908c  lea     rcx, CriticalSection; lpCriticalSection
0x180019093  movdqu  xmmword ptr [rax], xmm0
0x180019097  call    cs:__imp_LeaveCriticalSection
0x18001909d  xor     ebx, ebx
0x18001909f  mov     [r13+0], rdi
0x1800190a3  jmp     short loc_1800190CF
0x1800190a5  mov     [r13+0], r14
0x1800190a9  test    cs:byte_180030D04, dil
0x1800190b0  jz      short loc_1800190CA
0x1800190b2  lea     rax, [rbp+var_20]
0x1800190b6  mov     r9d, edi
0x1800190b9  lea     rdx, ErrorNullPointer
0x1800190c0  mov     [rsp+70h+var_50], rax
0x1800190c5  call    McGenEventWrite_EventWriteTransfer
0x1800190ca  mov     ebx, 80004003h
0x1800190cf  mov     rcx, r15; struct _SCHEDULE_SID *
0x1800190d2  call    ?TsiFreeScheduleSid@@YAJPEAU_SCHEDULE_SID@@@Z; TsiFreeScheduleSid(_SCHEDULE_SID *)
0x1800190d7  mov     rcx, r14; struct _APPCONTAINER_SECURITY_INFO *
0x1800190da  call    ?TsiFreeAppContainerSecurityInfo@@YAJPEAU_APPCONTAINER_SECURITY_INFO@@@Z; TsiFreeAppContainerSecurityInfo(_APPCONTAINER_SECURITY_INFO *)
0x1800190df  mov     eax, ebx
0x1800190e1  mov     rcx, [rbp+var_10]
0x1800190e5  xor     rcx, rsp; StackCookie
0x1800190e8  call    __security_check_cookie
0x1800190ed  mov     rbx, [rsp+70h+arg_0]
0x1800190f5  add     rsp, 70h
0x1800190f9  pop     r15
0x1800190fb  pop     r14
0x1800190fd  pop     r13
0x1800190ff  pop     r12
0x180019101  pop     rdi
0x180019102  pop     rsi
0x180019103  pop     rbp
0x180019104  retn
```
