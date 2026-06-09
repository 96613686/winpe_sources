# CPort::StartRoamJob(CRoamReconnectJob * *,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS,_WDF_EXECUTION_LEVEL)

- ea: `0x14008af8c`
- end: `0x14008b33c`
- name: `?StartRoamJob@CPort@@QEAAHPEAPEAVCRoamReconnectJob@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@W4_WDF_EXECUTION_LEVEL@@@Z`
- size: `944`
- prototype: ``
- caller_count: `4`
- callee_count: `14`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140088270`
- `0x14008ba40`
- `0x14008bd8c`
- `0x14008bf94`

## callees

- `0x140009420`
- `0x14000c778`
- `0x14000d054`
- `0x140016d00`
- `0x14001a1e0`
- `0x14001a20c`
- `0x14001b294`
- `0x14001e2c0`
- `0x14001eed0`
- `0x1400553ac`
- `0x140083248`
- `0x14008af8c`
- `0x1400aa1c0`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CPort::StartRoamJob(__int64 a1, char **a2, int a3, unsigned int a4, unsigned int a5, int a6)
{
  unsigned int v7; // esi
  char **v9; // r14
  int v11; // r9d
  int v12; // edx
  int v13; // r8d
  int v14; // edx
  char *v15; // rdi
  unsigned int NextActivityId; // eax
  int PropertyULong; // eax
  unsigned int v18; // r9d
  __int64 v19; // r9
  int v20; // r8d
  int v21; // r9d
  WxDevice *v22; // rax
  __int64 v24; // [rsp+28h] [rbp-60h]
  __int16 v25; // [rsp+30h] [rbp-58h]
  unsigned int v26; // [rsp+90h] [rbp+8h] BYREF

  v7 = 0;
  v26 = 0;
  v9 = a2;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(a2) = 5;
    WPP_RECORDER_SF_(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      1,
      177,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids);
  }
  *v9 = 0;
  if ( !*(_DWORD *)(a1 + 388) )
  {
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v11 = 178;
    LOBYTE(a2) = 4;
    goto LABEL_32;
  }
  if ( CAdapter::IsLowPowerTransitionPending(*(CAdapter **)(a1 + 136)) )
  {
    if ( a3 == 1 && (*(_DWORD *)(a1 + 152) & 0x11) != 0 )
    {
      CPort::ConfigureRoamAtResumeForAssociationLossInPowerTransition(a1, a4, 1, a5);
    }
    else
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v7;
      LOBYTE(v12) = 4;
      WPP_RECORDER_SF_qDD(
        WPP_GLOBAL_Control->DeviceExtension,
        v12,
        v13,
        179,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a1,
        *(_WORD *)(a1 + 148),
        a3);
    }
    goto LABEL_33;
  }
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    LOBYTE(v12) = 4;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      v12,
      v13,
      180,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      a1,
      *(_WORD *)(a1 + 148),
      a3);
  }
  v15 = (char *)operator new(0x268u);
  if ( !v15 )
  {
    v7 = -1073741670;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v7;
    v11 = 181;
    LOBYTE(a2) = 2;
LABEL_32:
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)a2,
      a3,
      v11,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      a1,
      *(_WORD *)(a1 + 148));
    goto LABEL_33;
  }
  NextActivityId = IActivityId::get_NextActivityId();
  CJobBase::CJobBase((CJobBase *)v15, NextActivityId);
  *((_DWORD *)v15 + 140) = 0;
  *((_QWORD *)v15 + 1) = &CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'};
  *(_QWORD *)v15 = &CRoamReconnectJob::`vftable'{for `IOperationCompletionCallback'};
  *((_QWORD *)v15 + 67) = &CRoamReconnectJob::`vftable'{for `IDisassociationCompleteCallback'};
  v15[564] = 0;
  *((_DWORD *)v15 + 144) = 1;
  *((_QWORD *)v15 + 68) = &CRoamReconnectJob::`vftable'{for `INotifyOperationStarted'};
  *((_QWORD *)v15 + 74) = 0;
  *((_QWORD *)v15 + 69) = &CRoamReconnectJob::`vftable'{for `ITimerCallback'};
  *((_WORD *)v15 + 300) = 0;
  *(_QWORD *)(v15 + 604) = 0;
  PropertyULong = CPropertyCache::GetPropertyULong((CPropertyCache *)(a1 + 480), 0x18u, &v26);
  v18 = 1;
  if ( !PropertyULong )
    v18 = v26;
  v19 = v18 >> 4;
  LOBYTE(v19) = v19 & 1;
  v7 = CRoamReconnectJob::Initialize(v15, *(_QWORD *)(a1 + 136), *(unsigned int *)(a1 + 144), v19, a3, a4, a5);
  if ( v7 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = 182;
      v25 = *(_WORD *)(a1 + 148);
LABEL_27:
      LOBYTE(v14) = 2;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v14,
        v20,
        v21,
        (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
        a1,
        v25);
    }
  }
  else
  {
    if ( a6 == 2 )
      v15[42] = 1;
    v22 = (WxDevice *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, _QWORD, __int64 *))(WdfFunctions_01031 + 1616))(
                        WdfDriverGlobals,
                        *(_QWORD *)(*(_QWORD *)(a1 + 136) + 80LL),
                        off_14010E308);
    if ( (int)WxDevice::AddJobToPowerIdleDetectionList(
                v22,
                (struct CJobBase *const)v15,
                (struct IOperationCompletionCallback *const)((a1 + 8) & -(__int64)(a1 != 0))) >= 0 )
    {
      v7 = 0;
      *v9 = v15;
      goto LABEL_33;
    }
    v7 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v21 = 183;
      v25 = *(_WORD *)(a1 + 148);
      goto LABEL_27;
    }
  }
  (*(void (__fastcall **)(char *, __int64))(*(_QWORD *)v15 + 40LL))(v15, 1);
LABEL_33:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LODWORD(v24) = v7;
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_d(
      WPP_GLOBAL_Control->DeviceExtension,
      v14,
      1,
      184,
      (__int64)WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids,
      v24);
  }
  return v7;
}

```

## disassembly

```asm
0x14008af8c  mov     rax, rsp
0x14008af8f  push    rbx
0x14008af90  push    rbp
0x14008af91  push    rsi
0x14008af92  push    rdi
0x14008af93  push    r12
0x14008af95  push    r13
0x14008af97  push    r14
0x14008af99  push    r15
0x14008af9b  sub     rsp, 48h
0x14008af9f  xor     r12d, r12d
0x14008afa2  mov     r15d, r9d
0x14008afa5  mov     esi, r12d
0x14008afa8  mov     [rax+8], r12d
0x14008afac  mov     ebp, r8d
0x14008afaf  mov     r14, rdx
0x14008afb2  mov     rbx, rcx
0x14008afb5  lea     r13, WPP_RECORDER_INITIALIZED
0x14008afbc  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008afc3  lea     rdi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008afca  jz      short loc_14008AFFC
0x14008afcc  mov     rcx, cs:WPP_GLOBAL_Control
0x14008afd3  cmp     byte ptr [rcx+29h], 5
0x14008afd7  jnb     short loc_14008AFE0
0x14008afd9  cmp     [rcx+48h], r12w
0x14008afde  jz      short loc_14008AFFC
0x14008afe0  mov     rcx, [rcx+40h]
0x14008afe4  mov     r9d, 0B1h
0x14008afea  mov     r8d, 1
0x14008aff0  mov     [rsp+88h+var_68], rdi
0x14008aff5  mov     dl, 5
0x14008aff7  call    WPP_RECORDER_SF_
0x14008affc  mov     [r14], r12
0x14008afff  cmp     [rbx+184h], r12d
0x14008b006  jnz     short loc_14008B022
0x14008b008  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b00f  jz      loc_14008B328
0x14008b015  mov     r9d, 0B2h
0x14008b01b  mov     dl, 4
0x14008b01d  jmp     loc_14008B2C6
0x14008b022  mov     rcx, [rbx+88h]; this
0x14008b029  call    ?IsLowPowerTransitionPending@CAdapter@@QEAA_NXZ; CAdapter::IsLowPowerTransitionPending(void)
0x14008b02e  test    al, al
0x14008b030  jz      short loc_14008B09F
0x14008b032  cmp     ebp, 1
0x14008b035  jnz     short loc_14008B05C
0x14008b037  mov     eax, [rbx+98h]
0x14008b03d  test    al, 11h
0x14008b03f  jz      short loc_14008B05C
0x14008b041  mov     r9d, [rsp+88h+arg_20]
0x14008b049  mov     r8d, ebp
0x14008b04c  mov     edx, r15d
0x14008b04f  mov     rcx, rbx
0x14008b052  call    ?ConfigureRoamAtResumeForAssociationLossInPowerTransition@CPort@@QEAAHW4_WDI_ASSOC_STATUS@@W4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CPort::ConfigureRoamAtResumeForAssociationLossInPowerTransition(_WDI_ASSOC_STATUS,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ROAM_CONFIGURATION_FLAGS)
0x14008b057  jmp     loc_14008B2EB
0x14008b05c  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b063  jz      loc_14008B328
0x14008b069  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b070  mov     r9d, 0B3h
0x14008b076  movzx   eax, word ptr [rbx+94h]
0x14008b07d  mov     dl, 4
0x14008b07f  mov     [rsp+88h+var_50], ebp
0x14008b083  mov     dword ptr [rsp+88h+var_58], eax
0x14008b087  mov     rcx, [rcx+40h]
0x14008b08b  mov     [rsp+88h+var_60], rbx
0x14008b090  mov     [rsp+88h+var_68], rdi
0x14008b095  call    WPP_RECORDER_SF_qDD
0x14008b09a  jmp     loc_14008B2EB
0x14008b09f  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b0a6  jz      short loc_14008B0D9
0x14008b0a8  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b0af  mov     r9d, 0B4h
0x14008b0b5  movzx   eax, word ptr [rbx+94h]
0x14008b0bc  mov     dl, 4
0x14008b0be  mov     [rsp+88h+var_50], ebp
0x14008b0c2  mov     dword ptr [rsp+88h+var_58], eax
0x14008b0c6  mov     rcx, [rcx+40h]
0x14008b0ca  mov     [rsp+88h+var_60], rbx
0x14008b0cf  mov     [rsp+88h+var_68], rdi
0x14008b0d4  call    WPP_RECORDER_SF_qDD
0x14008b0d9  mov     ecx, 268h; unsigned __int64
0x14008b0de  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14008b0e3  mov     rdi, rax
0x14008b0e6  test    rax, rax
0x14008b0e9  jz      loc_14008B2A9
0x14008b0ef  call    ?get_NextActivityId@IActivityId@@SAKXZ; IActivityId::get_NextActivityId(void)
0x14008b0f4  mov     edx, eax; unsigned int
0x14008b0f6  mov     rcx, rdi; this
0x14008b0f9  call    ??0CJobBase@@IEAA@K@Z; CJobBase::CJobBase(ulong)
0x14008b0fe  lea     rax, ??_7CSetStaAssociationIEsJob@@6BIEventQueueCallback@@@; const CSetStaAssociationIEsJob::`vftable'{for `IEventQueueCallback'}
0x14008b105  mov     [rdi+230h], r12d
0x14008b10c  mov     [rdi+8], rax
0x14008b110  lea     rcx, ??_7CRoamReconnectJob@@6BIOperationCompletionCallback@@@; const CRoamReconnectJob::`vftable'{for `IOperationCompletionCallback'}
0x14008b117  lea     rax, ??_7CRoamReconnectJob@@6BIDisassociationCompleteCallback@@@; const CRoamReconnectJob::`vftable'{for `IDisassociationCompleteCallback'}
0x14008b11e  mov     [rdi], rcx
0x14008b121  mov     [rdi+218h], rax
0x14008b128  lea     rcx, [rbx+1E0h]; this
0x14008b12f  mov     esi, 1
0x14008b134  mov     [rdi+234h], r12b
0x14008b13b  lea     rax, ??_7CRoamReconnectJob@@6BINotifyOperationStarted@@@; const CRoamReconnectJob::`vftable'{for `INotifyOperationStarted'}
0x14008b142  mov     [rdi+240h], esi
0x14008b148  mov     [rdi+220h], rax
0x14008b14f  lea     r8, [rsp+88h+arg_0]; unsigned int *
0x14008b157  lea     rax, ??_7CRoamReconnectJob@@6BITimerCallback@@@; const CRoamReconnectJob::`vftable'{for `ITimerCallback'}
0x14008b15e  mov     [rdi+250h], r12
0x14008b165  lea     edx, [rsi+17h]; unsigned int
0x14008b168  mov     [rdi+228h], rax
0x14008b16f  mov     [rdi+258h], r12w
0x14008b177  mov     [rdi+25Ch], r12
0x14008b17e  call    ?GetPropertyULong@CPropertyCache@@QEAAHKPEAK@Z; CPropertyCache::GetPropertyULong(ulong,ulong *)
0x14008b183  mov     r9d, esi
0x14008b186  test    eax, eax
0x14008b188  jnz     short loc_14008B192
0x14008b18a  mov     r9d, [rsp+88h+arg_0]
0x14008b192  mov     eax, [rsp+88h+arg_20]
0x14008b199  mov     rcx, rdi
0x14008b19c  mov     r8d, [rbx+90h]
0x14008b1a3  mov     rdx, [rbx+88h]
0x14008b1aa  mov     dword ptr [rsp+88h+var_58], eax
0x14008b1ae  shr     r9d, 4
0x14008b1b2  and     r9b, sil
0x14008b1b5  mov     dword ptr [rsp+88h+var_60], r15d
0x14008b1ba  mov     dword ptr [rsp+88h+var_68], ebp
0x14008b1be  call    ?Initialize@CRoamReconnectJob@@QEAAHPEAVCAdapter@@K_NW4_WFC_ROAM_CONNECT_TRIGGER@@W4_WDI_ASSOC_STATUS@@W4_WDI_ROAM_CONFIGURATION_FLAGS@@@Z; CRoamReconnectJob::Initialize(CAdapter *,ulong,bool,_WFC_ROAM_CONNECT_TRIGGER,_WDI_ASSOC_STATUS,_WDI_ROAM_CONFIGURATION_FLAGS)
0x14008b1c3  mov     esi, eax
0x14008b1c5  test    eax, eax
0x14008b1c7  jz      short loc_14008B1E9
0x14008b1c9  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b1d0  jz      loc_14008B284
0x14008b1d6  movzx   ecx, word ptr [rbx+94h]
0x14008b1dd  mov     r9d, 0B6h
0x14008b1e3  mov     dword ptr [rsp+88h+var_58], ecx
0x14008b1e7  jmp     short loc_14008B261
0x14008b1e9  cmp     [rsp+88h+arg_28], 2
0x14008b1f1  jnz     short loc_14008B1F7
0x14008b1f3  mov     byte ptr [rdi+2Ah], 1
0x14008b1f7  mov     rdx, [rbx+88h]
0x14008b1fe  mov     rax, cs:WdfFunctions_01031
0x14008b205  mov     r8, cs:off_14010E308
0x14008b20c  mov     rcx, cs:WdfDriverGlobals
0x14008b213  mov     rdx, [rdx+50h]
0x14008b217  mov     rax, [rax+650h]
0x14008b21e  call    _guard_dispatch_icall
0x14008b223  lea     rdx, [rbx+8]
0x14008b227  mov     rcx, rbx
0x14008b22a  neg     rcx
0x14008b22d  mov     rcx, rax; this
0x14008b230  sbb     r8, r8
0x14008b233  and     r8, rdx; struct IOperationCompletionCallback *
0x14008b236  mov     rdx, rdi; struct CJobBase *
0x14008b239  call    ?AddJobToPowerIdleDetectionList@WxDevice@@QEAAJQEAVCJobBase@@QEAVIOperationCompletionCallback@@@Z; WxDevice::AddJobToPowerIdleDetectionList(CJobBase * const,IOperationCompletionCallback * const)
0x14008b23e  test    eax, eax
0x14008b240  jns     short loc_14008B29A
0x14008b242  mov     esi, 0C0000001h
0x14008b247  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b24e  jz      short loc_14008B284
0x14008b250  movzx   eax, word ptr [rbx+94h]
0x14008b257  mov     r9d, 0B7h
0x14008b25d  mov     dword ptr [rsp+88h+var_58], eax
0x14008b261  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b268  lea     rax, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008b26f  mov     [rsp+88h+var_60], rbx
0x14008b274  mov     dl, 2
0x14008b276  mov     [rsp+88h+var_68], rax
0x14008b27b  mov     rcx, [rcx+40h]
0x14008b27f  call    WPP_RECORDER_SF_qD
0x14008b284  mov     rax, [rdi]
0x14008b287  mov     edx, 1
0x14008b28c  mov     rcx, rdi
0x14008b28f  mov     rax, [rax+28h]
0x14008b293  call    _guard_dispatch_icall
0x14008b298  jmp     short loc_14008B2A0
0x14008b29a  mov     esi, r12d
0x14008b29d  mov     [r14], rdi
0x14008b2a0  lea     rdi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008b2a7  jmp     short loc_14008B2EB
0x14008b2a9  mov     esi, 0C000009Ah
0x14008b2ae  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b2b5  jz      short loc_14008B328
0x14008b2b7  mov     r9d, 0B5h
0x14008b2bd  lea     rdi, WPP_ec9f566a4d91355929b7c1dd2a1777a1_Traceguids
0x14008b2c4  mov     dl, 2
0x14008b2c6  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b2cd  movzx   eax, word ptr [rbx+94h]
0x14008b2d4  mov     dword ptr [rsp+88h+var_58], eax
0x14008b2d8  mov     [rsp+88h+var_60], rbx
0x14008b2dd  mov     rcx, [rcx+40h]
0x14008b2e1  mov     [rsp+88h+var_68], rdi
0x14008b2e6  call    WPP_RECORDER_SF_qD
0x14008b2eb  cmp     cs:WPP_RECORDER_INITIALIZED, r13
0x14008b2f2  jz      short loc_14008B328
0x14008b2f4  mov     rcx, cs:WPP_GLOBAL_Control
0x14008b2fb  cmp     byte ptr [rcx+29h], 5
0x14008b2ff  jnb     short loc_14008B308
0x14008b301  cmp     [rcx+48h], r12w
0x14008b306  jz      short loc_14008B328
0x14008b308  mov     rcx, [rcx+40h]
0x14008b30c  mov     r9d, 0B8h
0x14008b312  mov     dword ptr [rsp+88h+var_60], esi
0x14008b316  mov     r8d, 1
0x14008b31c  mov     dl, 5
0x14008b31e  mov     [rsp+88h+var_68], rdi
0x14008b323  call    WPP_RECORDER_SF_d
0x14008b328  mov     eax, esi
0x14008b32a  add     rsp, 48h
0x14008b32e  pop     r15
0x14008b330  pop     r14
0x14008b332  pop     r13
0x14008b334  pop     r12
0x14008b336  pop     rdi
0x14008b337  pop     rsi
0x14008b338  pop     rbp
0x14008b339  pop     rbx
0x14008b33a  retn
```
