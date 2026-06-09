# CConnectJob::StartConnectRoamTask(CConnectJob::_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS,CConnectJob::_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS,_WDI_ASSOC_STATUS *)

- ea: `0x1400b511c`
- end: `0x1400b58e2`
- name: `?StartConnectRoamTask@CConnectJob@@AEAAHW4_START_CONNECT_ROAM_CANDIDATE_LIST_CREATION_OPTIONS@1@W4_START_CONNECT_ROAM_NO_CANDIDATE_CONTINUE_OPTIONS@1@PEAW4_WDI_ASSOC_STATUS@@@Z`
- size: `1990`
- prototype: ``
- caller_count: `2`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400a2644`
- `0x1400adae0`

## callees

- `0x14000688c`
- `0x14000c940`
- `0x140018270`
- `0x14001d4c0`
- `0x14001e2c0`
- `0x14001eed0`
- `0x14002a9f8`
- `0x14002aaec`
- `0x14002bd34`
- `0x14002ed50`
- `0x14002ef48`
- `0x140030b60`
- `0x140032d30`
- `0x140061178`
- `0x1400625a0`
- `0x140063240`
- `0x14006403c`
- `0x1400683ac`
- `0x140071720`
- `0x1400b0128`
- `0x1400b511c`
- `0x1400b7bcc`
- `0x1400dfd40`

## pseudocode

```c
__int64 __fastcall CConnectJob::StartConnectRoamTask(unsigned __int64 a1, int a2, int a3, _DWORD *a4)
{
  unsigned __int16 v6; // dx
  CAdapter *v7; // rcx
  struct CPort *PortFromPortId; // r13
  CPropertyCache *PortPropertyCache; // rax
  int v12; // r8d
  unsigned int PropertyULongOrDefault; // r12d
  const struct _DOT11_SSID *v14; // rdx
  unsigned int v15; // ebx
  int v16; // r9d
  CPropertyCache *v17; // rax
  CPropertyCache *v18; // rax
  unsigned int v19; // eax
  void *v20; // rcx
  unsigned int RoamTaskTlv; // eax
  unsigned int v22; // r14d
  int v23; // r9d
  char v24; // r15
  struct CPort *v25; // rax
  int v26; // edx
  int v27; // r8d
  unsigned int *v28; // rax
  unsigned int v29; // ecx
  char v30; // al
  __int64 v31; // rax
  unsigned __int64 v32; // rdi
  unsigned __int64 v33; // rbx
  unsigned __int64 CurrentTime; // rax
  int v35; // r9d
  _DWORD *v36; // r8
  __int64 v37; // rax
  CPropertyCache *v38; // rax
  int v39; // eax
  int v40; // edx
  int v41; // r8d
  CPropertyCache *v42; // rax
  int v43; // eax
  int v44; // edx
  int v45; // r8d
  CPropertyCache *v46; // rax
  CPropertyCache *v47; // rax
  unsigned __int8 *v49; // [rsp+20h] [rbp-98h]
  int v50; // [rsp+30h] [rbp-88h]
  __int64 v51; // [rsp+38h] [rbp-80h]
  int v52; // [rsp+38h] [rbp-80h]
  struct DeviceCommand *v53; // [rsp+C0h] [rbp+8h] BYREF

  v6 = *(_WORD *)(a1 + 52);
  v7 = *(CAdapter **)(a1 + 536);
  v53 = 0;
  PortFromPortId = CAdapter::GetPortFromPortId(v7, v6);
  PortPropertyCache = COidJobBase::GetPortPropertyCache((COidJobBase *)a1);
  PropertyULongOrDefault = CPropertyCache::GetPropertyULongOrDefault(PortPropertyCache, 0x86u, 0);
  v14 = &WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids;
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 5;
    WPP_RECORDER_SF_qD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      v12,
      376,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16));
  }
  if ( *((_QWORD *)PortFromPortId + 9) )
    *(_QWORD *)(*((_QWORD *)PortFromPortId + 9) + 96LL) = CSystem::get_CurrentTime();
  *a4 = 6;
  if ( *(_BYTE *)(a1 + 596) )
  {
    v15 = -1073741823;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v15;
    v16 = 377;
    v52 = -1073741823;
    goto LABEL_76;
  }
  v17 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64, const struct _DOT11_SSID *))(*(_QWORD *)(*(_QWORD *)(a1 + 536) + 8LL)
                                                                                         + 8LL))(
                            *(_QWORD *)(a1 + 536) + 8LL,
                            v14);
  if ( CPropertyCache::GetPropertyBooleanOrDefault(v17, 0x2Eu, 0)
    || (v18 = (CPropertyCache *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(*(_QWORD *)(a1 + 536) + 8LL) + 8LL))(*(_QWORD *)(a1 + 536) + 8LL),
        CPropertyCache::GetPropertyBooleanOrDefault(v18, 0x2Fu, 0)) )
  {
    v15 = -1071439870;
    if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      return v15;
    v16 = 378;
    v52 = -1071439870;
LABEL_76:
    v50 = *(_DWORD *)(a1 + 16);
LABEL_77:
    LOBYTE(v14) = 2;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      v12,
      v16,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      a1,
      v50,
      v52);
    goto LABEL_78;
  }
  v12 = a1 + 620;
  v15 = 0;
  if ( !*(_DWORD *)(a1 + 620) )
  {
    v49 = (unsigned __int8 *)((a1 + 576) & ((unsigned __int128)-(__int128)a1 >> 64));
    v19 = NotificationManager::RegisterForNotifications(
            *(_QWORD *)(a1 + 536) + 1072LL,
            76,
            0,
            *(unsigned __int16 *)(a1 + 52));
    v15 = v19;
    if ( v19 )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v15;
      v16 = 379;
      v52 = v19;
      v50 = *(_DWORD *)(a1 + 16);
      goto LABEL_77;
    }
  }
  v20 = *(void **)(a1 + 1312);
  if ( v20 )
  {
    operator delete(v20);
    *(_QWORD *)(a1 + 1312) = 0;
    *(_DWORD *)(a1 + 1320) = 0;
  }
  if ( a2 )
  {
    v22 = 0;
  }
  else
  {
    RoamTaskTlv = CConnectJob::PickCandidates(
                    (CConnectJob *)a1,
                    (struct _WFC_CONNECTION_PROFILE_PARAMETERS *)(a1 + 976));
    v22 = 0;
    v15 = RoamTaskTlv;
    if ( RoamTaskTlv )
    {
      if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
        return v15;
      v23 = 380;
      goto LABEL_22;
    }
  }
  if ( !*(_DWORD *)(a1 + 644) && a3 != 1 )
  {
    *a4 = 6;
    goto LABEL_78;
  }
  *a4 = 0;
  v24 = 0;
  if ( (*(_DWORD *)(a1 + 632) & 4) == 0
    || (v24 = 1,
        v25 = CAdapter::GetPortFromPortId(*(CAdapter **)(a1 + 536), *(_WORD *)(a1 + 52)),
        (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)v25 + 59) + 24LL))(*((_QWORD *)v25 + 59), 3)) )
  {
    v28 = (unsigned int *)(a1 + 1320);
    if ( v24 )
    {
      RoamTaskTlv = CConnectJob::GenerateRoamTaskTlv(
                      (CConnectJob *)a1,
                      (unsigned int *)(a1 + 1320),
                      (unsigned __int8 **)(a1 + 1312));
      v15 = RoamTaskTlv;
      if ( RoamTaskTlv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v15;
        v23 = 382;
        goto LABEL_22;
      }
LABEL_39:
      if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
      {
        v29 = *(_DWORD *)(a1 + 644);
        v30 = 3;
        LOBYTE(v14) = 4;
        if ( v29 < 3 )
          v30 = *(_DWORD *)(a1 + 644);
        WPP_RECORDER_SF_qDdd(
          WPP_GLOBAL_Control->DeviceExtension,
          (_DWORD)v14,
          v12,
          384,
          (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
          a1,
          *(_DWORD *)(a1 + 16),
          v29,
          v30);
      }
      if ( *(_DWORD *)(a1 + 644) )
      {
        do
        {
          if ( v22 >= 3 )
            break;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          {
            v31 = *(_QWORD *)(a1 + 8LL * v22 + 656);
            v32 = *(_QWORD *)(v31 + 672);
            v33 = *(_QWORD *)(v31 + 632);
            CurrentTime = CSystem::get_CurrentTime();
            if ( v33 <= v32 )
              v33 = v32;
            v36 = *(_DWORD **)(a1 + 8LL * v22 + 656);
            WPP_RECORDER_SF_qDdd_MAC_dddd(
              WPP_GLOBAL_Control->DeviceExtension,
              (CurrentTime - v33) / 0x2710,
              (_DWORD)v36,
              v35,
              (_DWORD)v49,
              a1,
              *(_DWORD *)(a1 + 16),
              v22,
              v36[188],
              (__int64)(v36 + 8),
              v36[149],
              v36[171],
              v36[170],
              (CurrentTime - v33) / 0x2710);
          }
          ++v22;
        }
        while ( v22 < *(_DWORD *)(a1 + 644) );
      }
      RoamTaskTlv = Task::Initialize(
                      (enum _WDF_EXECUTION_LEVEL)(a1 + 1496),
                      (struct NotificationManager *)(*(_QWORD *)(a1 + 536) + 1072LL),
                      (struct DeviceCommandScheduler *)(*(_QWORD *)(a1 + 536) + 1120LL),
                      (struct EventQueue *)(*(_QWORD *)(a1 + 536) + 736LL));
      v15 = RoamTaskTlv;
      if ( RoamTaskTlv )
      {
        if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
          return v15;
        v23 = 386;
      }
      else
      {
        RoamTaskTlv = Task::get_TaskDeviceCommand((Task *)(a1 + 1496), &v53);
        v15 = RoamTaskTlv;
        if ( RoamTaskTlv )
        {
          if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            return v15;
          v23 = 387;
        }
        else
        {
          RoamTaskTlv = DeviceCommand::Initialize(
                          v53,
                          *(_WORD *)(a1 + 52),
                          v24 != 0 ? 100 : 6,
                          *(_DWORD *)(a1 + 1320),
                          *(unsigned __int8 **)(a1 + 1312));
          v15 = RoamTaskTlv;
          if ( RoamTaskTlv )
          {
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return v15;
            v23 = 388;
          }
          else
          {
            v37 = *((_QWORD *)PortFromPortId + 9);
            if ( v37 )
            {
              *(_BYTE *)(v37 + 1) = 1;
              *(_DWORD *)(*((_QWORD *)PortFromPortId + 9) + 32LL) = 6;
            }
            v38 = COidJobBase::GetPortPropertyCache((COidJobBase *)a1);
            v39 = CPropertyCache::SetPropertyBoolean(v38, 0x52u, 0);
            if ( v39 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v51) = v39;
              LOBYTE(v40) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v40,
                v41,
                389,
                (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                a1,
                *(_DWORD *)(a1 + 16),
                v51);
            }
            v42 = COidJobBase::GetPortPropertyCache((COidJobBase *)a1);
            v43 = CPropertyCache::SetPropertyULong(v42, 0x54u, 0xFFFFu);
            if ( v43 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            {
              LODWORD(v51) = v43;
              LOBYTE(v44) = 2;
              WPP_RECORDER_SF_qDD(
                WPP_GLOBAL_Control->DeviceExtension,
                v44,
                v45,
                390,
                (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                a1,
                *(_DWORD *)(a1 + 16),
                v51);
            }
            v46 = COidJobBase::GetPortPropertyCache((COidJobBase *)a1);
            v15 = CPropertyCache::SetPropertyBuffer(v46, 0x88u, 0, 0);
            if ( v15 )
              goto LABEL_78;
            v47 = COidJobBase::GetPortPropertyCache((COidJobBase *)a1);
            CPropertyCache::SetPropertyULong(v47, 0x86u, PropertyULongOrDefault + 1);
            RoamTaskTlv = CJobBase::StartTask((CJobBase *)a1, (struct Task *)(a1 + 1496));
            v15 = RoamTaskTlv;
            if ( !RoamTaskTlv )
            {
              if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              {
                LOBYTE(v14) = 4;
                WPP_RECORDER_SF_qD(
                  WPP_GLOBAL_Control->DeviceExtension,
                  (_DWORD)v14,
                  v12,
                  392,
                  (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
                  a1,
                  *(_DWORD *)(a1 + 16));
              }
              *(_DWORD *)(a1 + 592) = 8;
              goto LABEL_78;
            }
            if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
              return v15;
            v23 = 391;
          }
        }
      }
      goto LABEL_22;
    }
  }
  else
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      LOBYTE(v26) = 4;
      WPP_RECORDER_SF_qD(
        WPP_GLOBAL_Control->DeviceExtension,
        v26,
        v27,
        381,
        (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
        a1,
        *(_DWORD *)(a1 + 16));
    }
    v24 = 0;
    v28 = (unsigned int *)(a1 + 1320);
  }
  RoamTaskTlv = CConnectJob::GenerateConnectTaskTlv(
                  (CConnectJob *)a1,
                  (*(_BYTE *)(a1 + 632) & 1) == 0,
                  v28,
                  (unsigned __int8 **)(a1 + 1312));
  v15 = RoamTaskTlv;
  if ( !RoamTaskTlv )
    goto LABEL_39;
  if ( WPP_RECORDER_INITIALIZED == (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    return v15;
  v23 = 383;
LABEL_22:
  LOBYTE(v14) = 2;
  LODWORD(v51) = RoamTaskTlv;
  WPP_RECORDER_SF_qDD(
    WPP_GLOBAL_Control->DeviceExtension,
    (_DWORD)v14,
    v12,
    v23,
    (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
    a1,
    *(_DWORD *)(a1 + 16),
    v51);
LABEL_78:
  if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED
    && (BYTE1(WPP_GLOBAL_Control->Timer) >= 5u || LOWORD(WPP_GLOBAL_Control->DeviceType)) )
  {
    LOBYTE(v14) = 5;
    LODWORD(v51) = v15;
    WPP_RECORDER_SF_qDD(
      WPP_GLOBAL_Control->DeviceExtension,
      (_DWORD)v14,
      v12,
      393,
      (__int64)&WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids,
      a1,
      *(_DWORD *)(a1 + 16),
      v51);
  }
  return v15;
}

```

## disassembly

```asm
0x1400b511c  mov     rax, rsp
0x1400b511f  push    rbx
0x1400b5120  push    rbp
0x1400b5121  push    rsi
0x1400b5122  push    rdi
0x1400b5123  push    r12
0x1400b5125  push    r13
0x1400b5127  push    r14
0x1400b5129  push    r15
0x1400b512b  sub     rsp, 78h
0x1400b512f  mov     r14d, edx
0x1400b5132  mov     rbp, rcx
0x1400b5135  movzx   edx, word ptr [rcx+34h]; unsigned __int16
0x1400b5139  xor     edi, edi
0x1400b513b  mov     rcx, [rcx+218h]; this
0x1400b5142  mov     rsi, r9
0x1400b5145  mov     r15d, r8d
0x1400b5148  mov     [rax+8], rdi
0x1400b514c  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400b5151  mov     rcx, rbp; this
0x1400b5154  mov     r13, rax
0x1400b5157  call    ?GetPortPropertyCache@COidJobBase@@IEAAPEAVCPortPropertyCache@@XZ; COidJobBase::GetPortPropertyCache(void)
0x1400b515c  xor     r8d, r8d; unsigned int
0x1400b515f  mov     edx, 86h; unsigned int
0x1400b5164  mov     rcx, rax; this
0x1400b5167  call    ?GetPropertyULongOrDefault@CPropertyCache@@QEAAKKK@Z; CPropertyCache::GetPropertyULongOrDefault(ulong,ulong)
0x1400b516c  mov     r12d, eax
0x1400b516f  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b5176  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b517d  lea     rdx, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b5184  jz      short loc_1400B51BB
0x1400b5186  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b518d  cmp     byte ptr [rcx+29h], 5
0x1400b5191  jnb     short loc_1400B5199
0x1400b5193  cmp     [rcx+48h], di
0x1400b5197  jz      short loc_1400B51BB
0x1400b5199  mov     eax, [rbp+10h]
0x1400b519c  mov     r9d, 178h
0x1400b51a2  mov     rcx, [rcx+40h]
0x1400b51a6  mov     [rsp+0B8h+var_88], eax
0x1400b51aa  mov     [rsp+0B8h+var_90], rbp
0x1400b51af  mov     [rsp+0B8h+var_98], rdx
0x1400b51b4  mov     dl, 5
0x1400b51b6  call    WPP_RECORDER_SF_qD
0x1400b51bb  cmp     [r13+48h], rdi
0x1400b51bf  jz      short loc_1400B51CE
0x1400b51c1  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400b51c6  mov     rcx, [r13+48h]
0x1400b51ca  mov     [rcx+60h], rax
0x1400b51ce  mov     dword ptr [rsi], 6
0x1400b51d4  cmp     [rbp+254h], dil
0x1400b51db  jz      short loc_1400B5209
0x1400b51dd  mov     ebx, 0C0000001h
0x1400b51e2  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b51e9  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b51f0  jz      loc_1400B58CE
0x1400b51f6  mov     r9d, 179h
0x1400b51fc  mov     dword ptr [rsp+0B8h+var_80], 0C0000001h
0x1400b5204  jmp     loc_1400B585E
0x1400b5209  mov     rcx, [rbp+218h]
0x1400b5210  add     rcx, 8
0x1400b5214  mov     rax, [rcx]
0x1400b5217  mov     rax, [rax+8]
0x1400b521b  call    _guard_dispatch_icall
0x1400b5220  xor     r8d, r8d; unsigned __int8
0x1400b5223  mov     rcx, rax; this
0x1400b5226  lea     edx, [r8+2Eh]; unsigned int
0x1400b522a  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400b522f  test    al, al
0x1400b5231  jnz     loc_1400B583B
0x1400b5237  mov     rcx, [rbp+218h]
0x1400b523e  add     rcx, 8
0x1400b5242  mov     rax, [rcx]
0x1400b5245  mov     rax, [rax+8]
0x1400b5249  call    _guard_dispatch_icall
0x1400b524e  xor     r8d, r8d; unsigned __int8
0x1400b5251  mov     rcx, rax; this
0x1400b5254  lea     edx, [r8+2Fh]; unsigned int
0x1400b5258  call    ?GetPropertyBooleanOrDefault@CPropertyCache@@QEAAEKE@Z; CPropertyCache::GetPropertyBooleanOrDefault(ulong,uchar)
0x1400b525d  test    al, al
0x1400b525f  jnz     loc_1400B583B
0x1400b5265  lea     r8, [rbp+26Ch]
0x1400b526c  mov     ebx, edi
0x1400b526e  cmp     [r8], edi
0x1400b5271  jnz     short loc_1400B52DF
0x1400b5273  movzx   r9d, word ptr [rbp+34h]
0x1400b5278  lea     rcx, [rbp+240h]
0x1400b527f  mov     [rsp+0B8h+var_90], r8
0x1400b5284  mov     rax, rbp
0x1400b5287  neg     rax
0x1400b528a  sbb     rdx, rdx
0x1400b528d  xor     r8d, r8d
0x1400b5290  and     rdx, rcx
0x1400b5293  mov     rcx, [rbp+218h]
0x1400b529a  mov     [rsp+0B8h+var_98], rdx
0x1400b529f  add     rcx, 430h
0x1400b52a6  lea     edx, [r8+4Ch]
0x1400b52aa  call    ?RegisterForNotifications@NotificationManager@@QEAAHW4_WDI_INDICATION_TYPE@@KGPEAVINotifyDeviceIndicationCallback@@PEAK@Z; NotificationManager::RegisterForNotifications(_WDI_INDICATION_TYPE,ulong,ushort,INotifyDeviceIndicationCallback *,ulong *)
0x1400b52af  mov     ebx, eax
0x1400b52b1  test    eax, eax
0x1400b52b3  jz      short loc_1400B52DF
0x1400b52b5  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b52bc  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b52c3  jz      loc_1400B58CE
0x1400b52c9  mov     ecx, [rbp+10h]
0x1400b52cc  mov     r9d, 17Bh
0x1400b52d2  mov     dword ptr [rsp+0B8h+var_80], eax
0x1400b52d6  mov     [rsp+0B8h+var_88], ecx
0x1400b52da  jmp     loc_1400B5865
0x1400b52df  lea     rdi, [rbp+520h]
0x1400b52e6  mov     rcx, [rdi]; void *
0x1400b52e9  test    rcx, rcx
0x1400b52ec  jz      short loc_1400B5304
0x1400b52ee  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400b52f3  mov     qword ptr [rdi], 0
0x1400b52fa  mov     dword ptr [rbp+528h], 0
0x1400b5304  test    r14d, r14d
0x1400b5307  jnz     short loc_1400B536E
0x1400b5309  lea     rdx, [rbp+3D0h]; struct _WFC_CONNECTION_PROFILE_PARAMETERS *
0x1400b5310  mov     rcx, rbp; this
0x1400b5313  call    ?PickCandidates@CConnectJob@@AEAAHPEAU_WFC_CONNECTION_PROFILE_PARAMETERS@@@Z; CConnectJob::PickCandidates(_WFC_CONNECTION_PROFILE_PARAMETERS *)
0x1400b5318  xor     r14d, r14d
0x1400b531b  mov     ebx, eax
0x1400b531d  test    eax, eax
0x1400b531f  jz      short loc_1400B5371
0x1400b5321  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b5328  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b532f  jz      loc_1400B58CE
0x1400b5335  mov     r9d, 17Ch
0x1400b533b  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b5342  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b5349  mov     dl, 2
0x1400b534b  mov     dword ptr [rsp+0B8h+var_80], eax
0x1400b534f  mov     eax, [rbp+10h]
0x1400b5352  mov     [rsp+0B8h+var_88], eax
0x1400b5356  mov     rcx, [rcx+40h]
0x1400b535a  mov     [rsp+0B8h+var_90], rbp
0x1400b535f  mov     [rsp+0B8h+var_98], r15
0x1400b5364  call    WPP_RECORDER_SF_qDD
0x1400b5369  jmp     loc_1400B588B
0x1400b536e  xor     r14d, r14d
0x1400b5371  cmp     [rbp+284h], r14d
0x1400b5378  ja      short loc_1400B5399
0x1400b537a  cmp     r15d, 1
0x1400b537e  jz      short loc_1400B5399
0x1400b5380  mov     dword ptr [rsi], 6
0x1400b5386  lea     r15, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b538d  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b5394  jmp     loc_1400B588B
0x1400b5399  mov     [rsi], r14d
0x1400b539c  mov     r15b, r14b
0x1400b539f  mov     eax, [rbp+278h]
0x1400b53a5  test    al, 4
0x1400b53a7  jz      short loc_1400B5425
0x1400b53a9  movzx   edx, word ptr [rbp+34h]; unsigned __int16
0x1400b53ad  mov     r15b, 1
0x1400b53b0  mov     rcx, [rbp+218h]; this
0x1400b53b7  call    ?GetPortFromPortId@CAdapter@@QEAAPEAVCPort@@G@Z; CAdapter::GetPortFromPortId(ushort)
0x1400b53bc  mov     edx, 3
0x1400b53c1  mov     rcx, [rax+1D8h]
0x1400b53c8  mov     rax, [rcx]
0x1400b53cb  mov     rax, [rax+18h]
0x1400b53cf  call    _guard_dispatch_icall
0x1400b53d4  test    rax, rax
0x1400b53d7  jnz     short loc_1400B5425
0x1400b53d9  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b53e0  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b53e7  jz      short loc_1400B5419
0x1400b53e9  mov     eax, [rbp+10h]
0x1400b53ec  mov     r9d, 17Dh
0x1400b53f2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b53f9  mov     dl, 4
0x1400b53fb  mov     [rsp+0B8h+var_88], eax
0x1400b53ff  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b5406  mov     [rsp+0B8h+var_90], rbp
0x1400b540b  mov     [rsp+0B8h+var_98], rax
0x1400b5410  mov     rcx, [rcx+40h]
0x1400b5414  call    WPP_RECORDER_SF_qD
0x1400b5419  mov     r15b, r14b
0x1400b541c  lea     rax, [rbp+528h]
0x1400b5423  jmp     short loc_1400B546B
0x1400b5425  lea     rax, [rbp+528h]
0x1400b542c  test    r15b, r15b
0x1400b542f  jz      short loc_1400B5464
0x1400b5431  mov     r8, rdi; unsigned __int8 **
0x1400b5434  mov     rdx, rax; unsigned int *
0x1400b5437  mov     rcx, rbp; this
0x1400b543a  call    ?GenerateRoamTaskTlv@CConnectJob@@AEAAHPEAKPEAPEAE@Z; CConnectJob::GenerateRoamTaskTlv(ulong *,uchar * *)
0x1400b543f  mov     ebx, eax
0x1400b5441  test    eax, eax
0x1400b5443  jz      short loc_1400B54A2
0x1400b5445  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b544c  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b5453  jz      loc_1400B58CE
0x1400b5459  mov     r9d, 17Eh
0x1400b545f  jmp     loc_1400B533B
0x1400b5464  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b546b  mov     dl, [rbp+278h]
0x1400b5471  mov     r9, rdi; unsigned __int8 **
0x1400b5474  not     dl
0x1400b5476  mov     r8, rax; unsigned int *
0x1400b5479  and     dl, 1; bool
0x1400b547c  mov     rcx, rbp; this
0x1400b547f  call    ?GenerateConnectTaskTlv@CConnectJob@@AEAAH_NPEAKPEAPEAE@Z; CConnectJob::GenerateConnectTaskTlv(bool,ulong *,uchar * *)
0x1400b5484  mov     ebx, eax
0x1400b5486  test    eax, eax
0x1400b5488  jz      short loc_1400B54A2
0x1400b548a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b5491  jz      loc_1400B58CE
0x1400b5497  mov     r9d, 17Fh
0x1400b549d  jmp     loc_1400B533B
0x1400b54a2  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b54a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b54b0  jz      short loc_1400B5501
0x1400b54b2  mov     ecx, [rbp+284h]
0x1400b54b8  mov     eax, 3
0x1400b54bd  cmp     ecx, eax
0x1400b54bf  mov     r9d, 180h
0x1400b54c5  mov     dl, 4
0x1400b54c7  cmovb   eax, ecx
0x1400b54ca  mov     [rsp+0B8h+var_78], eax
0x1400b54ce  mov     eax, [rbp+10h]
0x1400b54d1  mov     dword ptr [rsp+0B8h+var_80], ecx
0x1400b54d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b54dc  mov     [rsp+0B8h+var_88], eax
0x1400b54e0  lea     rax, WPP_54405addb41d3096058a1ee6dddc76fe_Traceguids
0x1400b54e7  mov     [rsp+0B8h+var_90], rbp
0x1400b54ec  mov     [rsp+0B8h+var_98], rax
0x1400b54f1  mov     rcx, [rcx+40h]
0x1400b54f5  call    WPP_RECORDER_SF_qDdd
0x1400b54fa  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b5501  cmp     dword ptr [rbp+284h], 0
0x1400b5508  jbe     loc_1400B55DA
0x1400b550e  cmp     r14d, 3
0x1400b5512  jnb     loc_1400B55DA
0x1400b5518  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400b551f  jz      loc_1400B55CA
0x1400b5525  mov     esi, r14d
0x1400b5528  mov     rax, [rbp+rsi*8+290h]
0x1400b5530  mov     rdi, [rax+2A0h]
0x1400b5537  mov     rbx, [rax+278h]
0x1400b553e  call    ?get_CurrentTime@CSystem@@SA_KXZ; CSystem::get_CurrentTime(void)
0x1400b5543  mov     r8, [rbp+rsi*8+290h]
0x1400b554b  mov     rcx, rax
0x1400b554e  cmp     rbx, rdi
0x1400b5551  mov     rax, 346DC5D63886594Bh
0x1400b555b  cmovbe  rbx, rdi
0x1400b555f  sub     rcx, rbx
0x1400b5562  mul     rcx
0x1400b5565  mov     eax, [r8+2A8h]
0x1400b556c  lea     rcx, [r8+20h]
0x1400b5570  shr     rdx, 0Bh
0x1400b5574  mov     [rsp+0B8h+var_50], edx
0x1400b5578  mov     [rsp+0B8h+var_58], eax
0x1400b557c  mov     eax, [r8+2ACh]
0x1400b5583  mov     [rsp+0B8h+var_60], eax
0x1400b5587  mov     eax, [r8+254h]
0x1400b558e  mov     [rsp+0B8h+var_68], eax
0x1400b5592  mov     eax, [r8+2F0h]
0x1400b5599  mov     [rsp+0B8h+var_70], rcx
0x1400b559e  mov     rcx, cs:WPP_GLOBAL_Control
0x1400b55a5  mov     [rsp+0B8h+var_78], eax
0x1400b55a9  mov     eax, [rbp+10h]
0x1400b55ac  mov     dword ptr [rsp+0B8h+var_80], r14d
0x1400b55b1  mov     rcx, [rcx+40h]
0x1400b55b5  mov     [rsp+0B8h+var_88], eax
0x1400b55b9  mov     [rsp+0B8h+var_90], rbp
0x1400b55be  call    WPP_RECORDER_SF_qDdd_MAC_dddd
0x1400b55c3  lea     rax, WPP_RECORDER_INITIALIZED
0x1400b55ca  inc     r14d
0x1400b55cd  cmp     r14d, [rbp+284h]
0x1400b55d4  jb      loc_1400B550E
0x1400b55da  mov     rdx, [rbp+218h]
0x1400b55e1  lea     rdi, [rbp+5D8h]
0x1400b55e8  mov     rcx, rdi; this
0x1400b55eb  lea     r9, [rdx+2E0h]; struct EventQueue *
0x1400b55f2  lea     r8, [rdx+460h]; struct DeviceCommandScheduler *
0x1400b55f9  add     rdx, 430h; struct NotificationManager *
0x1400b5600  call    ?Initialize@Task@@QEAAHPEAVNotificationManager@@PEAVDeviceCommandScheduler@@PEAVEventQueue@@@Z; Task::Initialize(NotificationManager *,DeviceCommandScheduler *,EventQueue *)
0x1400b5605  xor     r14d, r14d
0x1400b5608  mov     ebx, eax
0x1400b560a  test    eax, eax
0x1400b560c  jz      short loc_1400B562D
0x1400b560e  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b5615  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b561c  jz      loc_1400B58CE
0x1400b5622  mov     r9d, 182h
0x1400b5628  jmp     loc_1400B533B
0x1400b562d  lea     rdx, [rsp+0B8h+arg_0]; struct DeviceCommand **
0x1400b5635  mov     rcx, rdi; this
0x1400b5638  call    ?get_TaskDeviceCommand@Task@@QEAAHPEAPEAVDeviceCommand@@@Z; Task::get_TaskDeviceCommand(DeviceCommand * *)
0x1400b563d  mov     ebx, eax
0x1400b563f  test    eax, eax
0x1400b5641  jz      short loc_1400B5662
0x1400b5643  lea     rsi, WPP_RECORDER_INITIALIZED
0x1400b564a  cmp     cs:WPP_RECORDER_INITIALIZED, rsi
0x1400b5651  jz      loc_1400B58CE
0x1400b5657  mov     r9d, 183h
0x1400b565d  jmp     loc_1400B533B
0x1400b5662  mov     rax, [rbp+520h]
  ... truncated ...
```
