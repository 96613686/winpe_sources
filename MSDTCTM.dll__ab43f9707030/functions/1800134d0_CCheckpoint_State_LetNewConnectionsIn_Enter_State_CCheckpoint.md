# CCheckpoint_State_LetNewConnectionsIn::Enter_State(CCheckpoint *)

- ea: `0x1800134d0`
- end: `0x180013677`
- name: `?Enter_State@CCheckpoint_State_LetNewConnectionsIn@@UEAAXPEAVCCheckpoint@@@Z`
- size: `423`
- prototype: `void(CCheckpoint_State_LetNewConnectionsIn *__hidden this, struct CCheckpoint *)`
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800134d0`
- `0x180013a24`
- `0x18006e904`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800135ee`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800135ee`

## string_xrefs

- `0x180013506`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180013530`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x180013599`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x1800135ce`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x18001362d`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`
- `0x18001365f`: `com\complus\dtc\dtc\tm\src\tmcheckp.cpp`

## pseudocode

```c
void __fastcall CCheckpoint_State_LetNewConnectionsIn::Enter_State(
        CCheckpoint_State_LetNewConnectionsIn *this,
        struct CCheckpoint *a2)
{
  CTmTrace *v4; // rcx
  CTmTrace *v5; // rcx
  __int64 v6; // rcx
  CTmTrace *v7; // rcx
  CTmTrace *v8; // rcx
  CTmTrace *v9; // rcx
  bool v10; // zf
  CTmTrace *v11; // rcx
  struct ICliqueSignal *v12; // [rsp+40h] [rbp+18h] BYREF

  v12 = 0;
  if ( (*(unsigned int (__fastcall **)(struct IConnectionManager *))(*(_QWORD *)g_pIConnMgr + 32LL))(g_pIConnMgr) )
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
  (*(void (__fastcall **)(CCheckpoint_State_LetNewConnectionsIn *, struct CCheckpoint *))(*(_QWORD *)this + 104LL))(
    this,
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
0x1800134d0  mov     [rsp+arg_0], rbx
0x1800134d5  push    rdi
0x1800134d6  sub     rsp, 20h
0x1800134da  mov     rdi, rcx
0x1800134dd  mov     [rsp+28h+arg_10], 0
0x1800134e6  mov     rcx, cs:?g_pIConnMgr@@3PEAUIConnectionManager@@EA; IConnectionManager * g_pIConnMgr
0x1800134ed  mov     rbx, rdx
0x1800134f0  mov     rax, [rcx]
0x1800134f3  mov     rax, [rax+20h]
0x1800134f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134fc  test    eax, eax
0x1800134fe  jz      short loc_180013513
0x180013500  mov     r8d, 3F2h; int
0x180013506  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x18001350d  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x180013513  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x18001351a  mov     rax, [rcx]
0x18001351d  mov     rax, [rax+18h]
0x180013521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013526  test    eax, eax
0x180013528  jz      short loc_18001353D
0x18001352a  mov     r8d, 3FBh; int
0x180013530  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x180013537  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x18001353d  mov     rcx, cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180013544  mov     rax, [rcx]
0x180013547  mov     rax, [rax+10h]
0x18001354b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013550  mov     rcx, [rbx+170h]
0x180013557  lea     r8, [rbx+60h]
0x18001355b  mov     dword ptr [rbx+1D8h], 1
0x180013565  mov     rax, rbx
0x180013568  neg     rax
0x18001356b  mov     cs:?g_pIConnMgrConfig@@3PEAUIConnectionManagerConfig2@@EA, 0; IConnectionManagerConfig2 * g_pIConnMgrConfig
0x180013576  mov     r9, [rcx]
0x180013579  sbb     rdx, rdx
0x18001357c  and     rdx, r8
0x18001357f  lea     r8, ?g_dwCheckpointSignalCookie@@3KA; ulong g_dwCheckpointSignalCookie
0x180013586  mov     rax, [r9+40h]
0x18001358a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001358f  test    eax, eax
0x180013591  jz      short loc_1800135A6
0x180013593  mov     r8d, 409h; int
0x180013599  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x1800135a0  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x1800135a6  mov     rcx, [rbx+170h]
0x1800135ad  lea     r8, [rsp+28h+arg_10]
0x1800135b2  lea     rdx, IID_ICliqueSignal
0x1800135b9  mov     rax, [rcx]
0x1800135bc  mov     rax, [rax]
0x1800135bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800135c4  test    eax, eax
0x1800135c6  jz      short loc_1800135DB
0x1800135c8  mov     r8d, 412h; int
0x1800135ce  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x1800135d5  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x1800135db  mov     rax, [rsp+28h+arg_10]
0x1800135e0  mov     rcx, cs:?g_hevTmStarted@@3PEAXEA; hEvent
0x1800135e7  mov     cs:?g_pICheckpointCliqueSignal@@3PEAUICliqueSignal@@EA, rax; ICliqueSignal * g_pICheckpointCliqueSignal
0x1800135ee  call    cs:__imp_SetEvent
0x1800135f4  mov     dword ptr [rbx+1D4h], 1
0x1800135fe  mov     rdx, rbx
0x180013601  mov     rax, [rdi]
0x180013604  mov     rcx, rdi
0x180013607  mov     rax, [rax+68h]
0x18001360b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013610  cmp     dword ptr [rbx+1D4h], 0
0x180013617  lea     rax, ?g_CCheckpoint_SubState_TimerRunning_TimerRunning@@3VCCheckpoint_SubState_TimerRunning_TimerRunning@@A; CCheckpoint_SubState_TimerRunning_TimerRunning g_CCheckpoint_SubState_TimerRunning_TimerRunning
0x18001361e  mov     [rbx+168h], rax
0x180013625  jnz     short loc_18001363A
0x180013627  mov     r8d, 439h; int
0x18001362d  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x180013634  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x18001363a  mov     rcx, [rbx+1C8h]
0x180013641  mov     rax, [rcx]
0x180013644  mov     rax, [rax+8]
0x180013648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001364d  mov     rcx, rbx; this
0x180013650  call    ?SetCheckpointTimer@CCheckpoint@@AEAAJXZ; CCheckpoint::SetCheckpointTimer(void)
0x180013655  test    eax, eax
0x180013657  jz      short loc_18001366C
0x180013659  mov     r8d, 444h; int
0x18001365f  lea     rdx, aComComplusDtcD_90; "com\\complus\\dtc\\dtc\\tm\\src\\tmchec"...
0x180013666  call    ?InternalError@CTmTrace@@QEAAXPEBDH@Z; CTmTrace::InternalError(char const *,int)
0x18001366c  mov     rbx, [rsp+28h+arg_0]
0x180013671  add     rsp, 20h
0x180013675  pop     rdi
0x180013676  retn
```
