# CCheckpoint_State::Change_State_LetNewConnectionsIn(CCheckpoint *)

- ea: `0x1800137dc`
- end: `0x18001399e`
- name: `?Change_State_LetNewConnectionsIn@CCheckpoint_State@@QEAAXPEAVCCheckpoint@@@Z`
- size: `450`
- prototype: `void(CCheckpoint_State *__hidden this, struct CCheckpoint *)`
- caller_count: `5`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012d60`
- `0x180013060`
- `0x180013128`
- `0x1800132b0`
- `0x180013680`

## callees

- `0x1800137dc`
- `0x180013a24`
- `0x18006e904`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013911`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180013911`

## string_xrefs

- `0x180013829`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180013853`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x1800138bc`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x1800138f1`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180013954`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180013986`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`

## pseudocode

```c
void __fastcall CCheckpoint_State::Change_State_LetNewConnectionsIn(CCheckpoint_State *this, struct CCheckpoint *a2)
{
  struct IConnectionManager *v3; // rcx
  CTmTrace *v4; // rcx
  CTmTrace *v5; // rcx
  __int64 v6; // rcx
  CTmTrace *v7; // rcx
  CTmTrace *v8; // rcx
  CTmTrace *v9; // rcx
  bool v10; // zf
  CTmTrace *v11; // rcx
  struct ICliqueSignal *v12; // [rsp+30h] [rbp+8h] BYREF

  (*(void (__fastcall **)(CCheckpoint_State *))(*(_QWORD *)this + 104LL))(this);
  v3 = g_pIConnMgr;
  *((_QWORD *)a2 + 45) = g_CCheckpoint_State_LetNewConnectionsIn;
  v12 = 0;
  if ( (*(unsigned int (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)v3 + 32LL))(v3) )
    CTmTrace::InternalError(v4, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1010);
  if ( (*(unsigned int (__fastcall **)(struct IConnectionManagerConfig2 *))(*(_QWORD *)g_pIConnMgrConfig + 24LL))(g_pIConnMgrConfig) )
    CTmTrace::InternalError(v5, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1019);
  (*(void (__fastcall **)(struct IConnectionManagerConfig2 *))(*(_QWORD *)g_pIConnMgrConfig + 16LL))(g_pIConnMgrConfig);
  v6 = *((_QWORD *)a2 + 46);
  *((_DWORD *)a2 + 118) = 1;
  g_pIConnMgrConfig = 0;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, unsigned int *))(*(_QWORD *)v6 + 64LL))(
         v6,
         ((unsigned __int64)a2 + 96) & ((unsigned __int128)-(__int128)(unsigned __int64)a2 >> 64),
         &g_dwCheckpointSignalCookie) )
  {
    CTmTrace::InternalError(v7, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1033);
  }
  if ( (***((unsigned int (__fastcall ****)(_QWORD, GUID *, struct ICliqueSignal **))a2 + 46))(
         *((_QWORD *)a2 + 46),
         &IID_ICliqueSignal,
         &v12) )
  {
    CTmTrace::InternalError(v8, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1042);
  }
  g_pICheckpointCliqueSignal = v12;
  SetEvent(g_hevTmStarted);
  *((_DWORD *)a2 + 117) = 1;
  (*((void (__fastcall **)(void ***, struct CCheckpoint *))g_CCheckpoint_State_LetNewConnectionsIn[0] + 13))(
    g_CCheckpoint_State_LetNewConnectionsIn,
    a2);
  v10 = *((_DWORD *)a2 + 117) == 0;
  *((_QWORD *)a2 + 45) = g_CCheckpoint_SubState_TimerRunning_TimerRunning;
  if ( v10 )
    CTmTrace::InternalError(v9, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1081);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)a2 + 57) + 8LL))(*((_QWORD *)a2 + 57));
  if ( (unsigned int)CCheckpoint::SetCheckpointTimer(a2) )
    CTmTrace::InternalError(v11, "com\\complus\\dtc\\dtc\\tm\\src\\tmcheckp.cpp", 1092);
}

```

## disassembly

```asm
0x1800137dc  mov     [rsp+arg_8], rbx
0x1800137e1  push    rbp
0x1800137e2  sub     rsp, 20h
0x1800137e6  mov     rax, [rcx]
0x1800137e9  mov     rbx, rdx
0x1800137ec  mov     rax, [rax+68h]
0x1800137f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137f5  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x1800137fc  lea     rbp, ?g_CCheckpoint_State_LetNewConnectionsIn@@3VCCheckpoint_State_LetNewConnectionsIn@@A; CCheckpoint_State_LetNewConnectionsIn g_CCheckpoint_State_LetNewConnectionsIn
0x180013803  mov     [rbx+168h], rbp
0x18001380a  mov     [rsp+28h+arg_0], 0
0x180013813  mov     rax, [rcx]
0x180013816  mov     rax, [rax+20h]
0x18001381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001381f  test    eax, eax
0x180013821  jz      short loc_180013836
0x180013823  mov     r8d, 3F2h; int
0x180013829  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x180013830  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x180013836  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x18001383d  mov     rax, [rcx]
0x180013840  mov     rax, [rax+18h]
0x180013844  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013849  test    eax, eax
0x18001384b  jz      short loc_180013860
0x18001384d  mov     r8d, 3FBh; int
0x180013853  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x18001385a  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x180013860  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180013867  mov     rax, [rcx]
0x18001386a  mov     rax, [rax+10h]
0x18001386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013873  mov     rcx, [rbx+170h]
0x18001387a  lea     r8, [rbx+60h]
0x18001387e  mov     dword ptr [rbx+1D8h], 1
0x180013888  mov     rax, rbx
0x18001388b  neg     rax
0x18001388e  mov     cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA, 0; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180013899  mov     r9, [rcx]
0x18001389c  sbb     rdx, rdx
0x18001389f  and     rdx, r8
0x1800138a2  lea     r8, ?g_dwCheckpointSignalCookie@@3KA; ulong g_dwCheckpointSignalCookie
0x1800138a9  mov     rax, [r9+40h]
0x1800138ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b2  test    eax, eax
0x1800138b4  jz      short loc_1800138C9
0x1800138b6  mov     r8d, 409h; int
0x1800138bc  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x1800138c3  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x1800138c9  mov     rcx, [rbx+170h]
0x1800138d0  lea     r8, [rsp+28h+arg_0]
0x1800138d5  lea     rdx, IID_ICliqueSignal
0x1800138dc  mov     rax, [rcx]
0x1800138df  mov     rax, [rax]
0x1800138e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138e7  test    eax, eax
0x1800138e9  jz      short loc_1800138FE
0x1800138eb  mov     r8d, 412h; int
0x1800138f1  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x1800138f8  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x1800138fe  mov     rax, [rsp+28h+arg_0]
0x180013903  mov     rcx, cs:?g_hevTmStarted@@3PEAXEA; hEvent
0x18001390a  mov     cs:?g_pICheckpointCliqueSignal@@3PEAUICliqueSignal@@EA, rax; ICliqueSignal * g_pICheckpointCliqueSignal
0x180013911  call    cs:__imp_SetEvent
0x180013917  mov     dword ptr [rbx+1D4h], 1
0x180013921  mov     rdx, rbx
0x180013924  mov     rax, cs:?g_CCheckpoint_State_LetNewConnectionsIn@@3VCCheckpoint_State_LetNewConnectionsIn@@A; CCheckpoint_State_LetNewConnectionsIn g_CCheckpoint_State_LetNewConnectionsIn
0x18001392b  mov     rcx, rbp
0x18001392e  mov     rax, [rax+68h]
0x180013932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013937  cmp     dword ptr [rbx+1D4h], 0
0x18001393e  lea     rax, ?g_CCheckpoint_SubState_TimerRunning_TimerRunning@@3VCCheckpoint_SubState_TimerRunning_TimerRunning@@A; CCheckpoint_SubState_TimerRunning_TimerRunning g_CCheckpoint_SubState_TimerRunning_TimerRunning
0x180013945  mov     [rbx+168h], rax
0x18001394c  jnz     short loc_180013961
0x18001394e  mov     r8d, 439h; int
0x180013954  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x18001395b  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x180013961  mov     rcx, [rbx+1C8h]
0x180013968  mov     rax, [rcx]
0x18001396b  mov     rax, [rax+8]
0x18001396f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013974  mov     rcx, rbx; this
0x180013977  call    ?SetCheckpointTimer@CCheckpoint@@AEAAJXZ; CCheckpoint::SetCheckpointTimer(void)
0x18001397c  test    eax, eax
0x18001397e  jz      short loc_180013993
0x180013980  mov     r8d, 444h; int
0x180013986  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x18001398d  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x180013993  mov     rbx, [rsp+28h+arg_8]
0x180013998  add     rsp, 20h
0x18001399c  pop     rbp
0x18001399d  retn
```
