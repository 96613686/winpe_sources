# CTieredVolume::~CTieredVolume(void)

- ea: `0x14000bf3c`
- end: `0x14000c320`
- name: `??1CTieredVolume@@QEAA@XZ`
- size: `996`
- prototype: `void __fastcall(JET_API_PTR ulContext)`
- caller_count: `3`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x140005284`
- `0x1400057f8`
- `0x14000761c`

## callees

- `0x140001e28`
- `0x140004a68`
- `0x140004aa8`
- `0x14000bf3c`
- `0x14000c7e0`
- `0x14000c8f8`
- `0x140014e28`
- `0x1400164c8`
- `0x14001cb9c`
- `0x14001dbf0`

## import_xrefs

- `msvcrt!free` at `0x14000c20c`
- `msvcrt!free` at `0x14000c220`
- `msvcrt!free` at `0x14000c234`
- `msvcrt!free` at `0x14000c248`
- `msvcrt!free` at `0x14000c25c`
- `msvcrt!free` at `0x14000c270`
- `msvcrt!free` at `0x14000c2a8`
- `msvcrt!free` at `0x14000c2bc`
- `msvcrt!free` at `0x14000c2d0`
- `msvcrt!free` at `0x14000c2e4`
- `msvcrt!free` at `0x14000c2f8`
- `msvcrt!free` at `0x14000c20c`
- `msvcrt!free` at `0x14000c220`
- `msvcrt!free` at `0x14000c234`
- `msvcrt!free` at `0x14000c248`
- `msvcrt!free` at `0x14000c25c`
- `msvcrt!free` at `0x14000c270`
- `msvcrt!free` at `0x14000c2a8`
- `msvcrt!free` at `0x14000c2bc`
- `msvcrt!free` at `0x14000c2d0`
- `msvcrt!free` at `0x14000c2e4`
- `msvcrt!free` at `0x14000c2f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c29b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c289`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000c29b`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000bf57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000bf64`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000bf57`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14000bf64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000bfc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroup` at `0x14000bfc9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000bfbc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x14000bfbc`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x14000c0a7`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x14000c134`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x14000c0a7`
- `api-ms-win-devices-config-l1-1-1!CM_Unregister_Notification` at `0x14000c134`

## pseudocode

```c
void __fastcall CTieredVolume::~CTieredVolume(JET_API_PTR ulContext)
{
  struct _TP_CLEANUP_GROUP *v2; // rcx
  bool v3; // dl
  int v4; // eax
  bool v5; // dl
  int v6; // eax
  unsigned int v7; // eax
  unsigned int v8; // eax
  void *v9; // rcx
  void *v10; // rcx

  *(_BYTE *)(ulContext + 165) = 1;
  SetEvent(*(HANDLE *)(ulContext + 768));
  SetEvent(*(HANDLE *)(ulContext + 776));
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      12,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128));
  }
  v2 = *(struct _TP_CLEANUP_GROUP **)(ulContext + 992);
  if ( v2 )
  {
    CloseThreadpoolCleanupGroupMembers(v2, 1, (PVOID)ulContext);
    CloseThreadpoolCleanupGroup(*(PTP_CLEANUP_GROUP *)(ulContext + 992));
    *(_QWORD *)(ulContext + 992) = 0;
    *(_QWORD *)(ulContext + 912) = 0;
    *(_QWORD *)(ulContext + 904) = 0;
  }
  CTieredVolume::CloseJetDatabases((CTieredVolume *)ulContext, 0, 1, 0);
  v4 = TieringJetDatabase::WaitForDatabaseClose((TieringJetDatabase *)(ulContext + 1344), v3);
  if ( v4 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      13,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128),
      v4);
  }
  v6 = TieringJetDatabase::WaitForDatabaseClose((TieringJetDatabase *)(ulContext + 1184), v5);
  if ( v6 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128),
      v6);
  }
  CTieredVolume::TeardownMovementSession(ulContext, 1);
  CTieredVolume::CloseJetInstance((CTieredVolume *)ulContext, 0, 0);
  if ( *(_BYTE *)(ulContext + 722) )
  {
    v7 = CM_Unregister_Notification(*(_QWORD *)(ulContext + 736));
    if ( v7 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          15,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          v7,
          *(_DWORD *)(ulContext + 128));
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *(unsigned int *)(ulContext + 128));
    }
    *(_BYTE *)(ulContext + 722) = 0;
  }
  if ( *(_BYTE *)(ulContext + 726) )
  {
    v8 = CM_Unregister_Notification(*(_QWORD *)(ulContext + 744));
    if ( v8 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
          v8,
          *(_DWORD *)(ulContext + 128));
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
           && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
           && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
        *(unsigned int *)(ulContext + 128));
    }
    *(_BYTE *)(ulContext + 726) = 0;
  }
  TieringMovementSession::Teardown((TieringMovementSession *)(ulContext + 1688));
  if ( *(_QWORD *)(ulContext + 1584) )
    *(_QWORD *)(ulContext + 1584) = 0;
  if ( *(_QWORD *)(ulContext + 1424) )
    *(_QWORD *)(ulContext + 1424) = 0;
  if ( *(_QWORD *)(ulContext + 1264) )
    *(_QWORD *)(ulContext + 1264) = 0;
  `eh vector destructor iterator'(
    (void *)(ulContext + 1008),
    0x30u,
    2u,
    ATL::CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>::~CRBMap<_FILE_EXTENT_IDENTIFIER,_FILE_EXTENT_DATA *,ATL::CElementTraits<_FILE_EXTENT_IDENTIFIER>,ATL::CElementTraits<_FILE_EXTENT_DATA *>>);
  free(*(void **)(ulContext + 896));
  *(_QWORD *)(ulContext + 896) = 0;
  free(*(void **)(ulContext + 872));
  *(_QWORD *)(ulContext + 872) = 0;
  free(*(void **)(ulContext + 864));
  *(_QWORD *)(ulContext + 864) = 0;
  free(*(void **)(ulContext + 840));
  *(_QWORD *)(ulContext + 840) = 0;
  free(*(void **)(ulContext + 832));
  *(_QWORD *)(ulContext + 832) = 0;
  free(*(void **)(ulContext + 808));
  *(_QWORD *)(ulContext + 808) = 0;
  v9 = *(void **)(ulContext + 776);
  if ( v9 )
    CloseHandle(v9);
  v10 = *(void **)(ulContext + 768);
  if ( v10 )
    CloseHandle(v10);
  free(*(void **)(ulContext + 688));
  *(_QWORD *)(ulContext + 688) = 0;
  free(*(void **)(ulContext + 664));
  *(_QWORD *)(ulContext + 664) = 0;
  free(*(void **)(ulContext + 656));
  *(_QWORD *)(ulContext + 656) = 0;
  free(*(void **)(ulContext + 632));
  *(_QWORD *)(ulContext + 632) = 0;
  free(*(void **)(ulContext + 608));
  *(_QWORD *)(ulContext + 608) = 0;
  ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(ulContext + 80);
  ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(ulContext + 32);
}

```

## disassembly

```asm
0x14000bf3c  push    rbx
0x14000bf3e  push    rbp
0x14000bf3f  push    rdi
0x14000bf40  push    r14
0x14000bf42  sub     rsp, 38h
0x14000bf46  mov     rbx, rcx
0x14000bf49  mov     byte ptr [rcx+0A5h], 1
0x14000bf50  mov     rcx, [rcx+300h]; hEvent
0x14000bf57  call    cs:__imp_SetEvent
0x14000bf5d  mov     rcx, [rbx+308h]; hEvent
0x14000bf64  call    cs:__imp_SetEvent
0x14000bf6a  lea     rbp, WPP_GLOBAL_Control
0x14000bf71  lea     r14, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14000bf78  mov     rcx, cs:WPP_GLOBAL_Control
0x14000bf7f  cmp     rcx, rbp
0x14000bf82  jz      short loc_14000BFA8
0x14000bf84  test    byte ptr [rcx+1Ch], 1
0x14000bf88  jz      short loc_14000BFA8
0x14000bf8a  cmp     byte ptr [rcx+19h], 4
0x14000bf8e  jb      short loc_14000BFA8
0x14000bf90  mov     edx, 0Ch
0x14000bf95  mov     r9d, [rbx+80h]
0x14000bf9c  mov     r8, r14
0x14000bf9f  mov     rcx, [rcx+10h]
0x14000bfa3  call    WPP_SF_d
0x14000bfa8  mov     rcx, [rbx+3E0h]; ptpcg
0x14000bfaf  xor     edi, edi
0x14000bfb1  test    rcx, rcx
0x14000bfb4  jz      short loc_14000BFE4
0x14000bfb6  mov     r8, rbx; pvCleanupContext
0x14000bfb9  lea     edx, [rdi+1]; fCancelPendingCallbacks
0x14000bfbc  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x14000bfc2  mov     rcx, [rbx+3E0h]; ptpcg
0x14000bfc9  call    cs:__imp_CloseThreadpoolCleanupGroup
0x14000bfcf  mov     [rbx+3E0h], rdi
0x14000bfd6  mov     [rbx+390h], rdi
0x14000bfdd  mov     [rbx+388h], rdi
0x14000bfe4  xor     r9d, r9d; bool
0x14000bfe7  mov     r8b, 1; bool
0x14000bfea  xor     edx, edx; bool
0x14000bfec  mov     rcx, rbx; this
0x14000bfef  call    ?CloseJetDatabases@CTieredVolume@@QEAAX_N00@Z; CTieredVolume::CloseJetDatabases(bool,bool,bool)
0x14000bff4  lea     rcx, [rbx+540h]; this
0x14000bffb  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x14000c000  test    eax, eax
0x14000c002  jns     short loc_14000C038
0x14000c004  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c00b  cmp     rcx, rbp
0x14000c00e  jz      short loc_14000C038
0x14000c010  test    byte ptr [rcx+1Ch], 1
0x14000c014  jz      short loc_14000C038
0x14000c016  cmp     byte ptr [rcx+19h], 2
0x14000c01a  jb      short loc_14000C038
0x14000c01c  mov     edx, 0Dh
0x14000c021  mov     [rsp+58h+var_38], eax
0x14000c025  mov     r9d, [rbx+80h]
0x14000c02c  mov     r8, r14
0x14000c02f  mov     rcx, [rcx+10h]
0x14000c033  call    WPP_SF_Dd
0x14000c038  lea     rcx, [rbx+4A0h]; this
0x14000c03f  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x14000c044  test    eax, eax
0x14000c046  jns     short loc_14000C07C
0x14000c048  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c04f  cmp     rcx, rbp
0x14000c052  jz      short loc_14000C07C
0x14000c054  test    byte ptr [rcx+1Ch], 1
0x14000c058  jz      short loc_14000C07C
0x14000c05a  cmp     byte ptr [rcx+19h], 2
0x14000c05e  jb      short loc_14000C07C
0x14000c060  mov     edx, 0Eh
0x14000c065  mov     [rsp+58h+var_38], eax
0x14000c069  mov     r9d, [rbx+80h]
0x14000c070  mov     r8, r14
0x14000c073  mov     rcx, [rcx+10h]
0x14000c077  call    WPP_SF_Dd
0x14000c07c  mov     dl, 1; bool
0x14000c07e  mov     rcx, rbx; ulContext
0x14000c081  call    ?TeardownMovementSession@CTieredVolume@@AEAAJ_N@Z; CTieredVolume::TeardownMovementSession(bool)
0x14000c086  xor     r8d, r8d; bool
0x14000c089  xor     edx, edx; bool
0x14000c08b  mov     rcx, rbx; this
0x14000c08e  call    ?CloseJetInstance@CTieredVolume@@QEAAX_N0@Z; CTieredVolume::CloseJetInstance(bool,bool)
0x14000c093  cmp     [rbx+2D2h], dil
0x14000c09a  jz      loc_14000C120
0x14000c0a0  mov     rcx, [rbx+2E0h]
0x14000c0a7  call    cs:__imp_CM_Unregister_Notification
0x14000c0ad  mov     r9d, eax
0x14000c0b0  test    eax, eax
0x14000c0b2  jz      short loc_14000C0E9
0x14000c0b4  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0bb  cmp     rcx, rbp
0x14000c0be  jz      short loc_14000C119
0x14000c0c0  test    byte ptr [rcx+1Ch], 1
0x14000c0c4  jz      short loc_14000C119
0x14000c0c6  cmp     byte ptr [rcx+19h], 2
0x14000c0ca  jb      short loc_14000C119
0x14000c0cc  mov     edx, 0Fh
0x14000c0d1  mov     eax, [rbx+80h]
0x14000c0d7  mov     [rsp+58h+var_38], eax
0x14000c0db  mov     r8, r14
0x14000c0de  mov     rcx, [rcx+10h]
0x14000c0e2  call    WPP_SF_Dd
0x14000c0e7  jmp     short loc_14000C119
0x14000c0e9  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c0f0  cmp     rcx, rbp
0x14000c0f3  jz      short loc_14000C119
0x14000c0f5  test    byte ptr [rcx+1Ch], 1
0x14000c0f9  jz      short loc_14000C119
0x14000c0fb  cmp     byte ptr [rcx+19h], 5
0x14000c0ff  jb      short loc_14000C119
0x14000c101  mov     edx, 10h
0x14000c106  mov     r9d, [rbx+80h]
0x14000c10d  mov     r8, r14
0x14000c110  mov     rcx, [rcx+10h]
0x14000c114  call    WPP_SF_d
0x14000c119  mov     [rbx+2D2h], dil
0x14000c120  cmp     [rbx+2D6h], dil
0x14000c127  jz      loc_14000C1AD
0x14000c12d  mov     rcx, [rbx+2E8h]
0x14000c134  call    cs:__imp_CM_Unregister_Notification
0x14000c13a  mov     r9d, eax
0x14000c13d  test    eax, eax
0x14000c13f  jz      short loc_14000C176
0x14000c141  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c148  cmp     rcx, rbp
0x14000c14b  jz      short loc_14000C1A6
0x14000c14d  test    byte ptr [rcx+1Ch], 1
0x14000c151  jz      short loc_14000C1A6
0x14000c153  cmp     byte ptr [rcx+19h], 2
0x14000c157  jb      short loc_14000C1A6
0x14000c159  mov     edx, 11h
0x14000c15e  mov     eax, [rbx+80h]
0x14000c164  mov     [rsp+58h+var_38], eax
0x14000c168  mov     r8, r14
0x14000c16b  mov     rcx, [rcx+10h]
0x14000c16f  call    WPP_SF_Dd
0x14000c174  jmp     short loc_14000C1A6
0x14000c176  mov     rcx, cs:WPP_GLOBAL_Control
0x14000c17d  cmp     rcx, rbp
0x14000c180  jz      short loc_14000C1A6
0x14000c182  test    byte ptr [rcx+1Ch], 1
0x14000c186  jz      short loc_14000C1A6
0x14000c188  cmp     byte ptr [rcx+19h], 5
0x14000c18c  jb      short loc_14000C1A6
0x14000c18e  mov     edx, 12h
0x14000c193  mov     r9d, [rbx+80h]
0x14000c19a  mov     r8, r14
0x14000c19d  mov     rcx, [rcx+10h]
0x14000c1a1  call    WPP_SF_d
0x14000c1a6  mov     [rbx+2D6h], dil
0x14000c1ad  lea     rcx, [rbx+698h]; this
0x14000c1b4  call    ?Teardown@TieringMovementSession@@QEAAJXZ; TieringMovementSession::Teardown(void)
0x14000c1b9  cmp     [rbx+630h], rdi
0x14000c1c0  jz      short loc_14000C1C9
0x14000c1c2  mov     [rbx+630h], rdi
0x14000c1c9  cmp     [rbx+590h], rdi
0x14000c1d0  jz      short loc_14000C1D9
0x14000c1d2  mov     [rbx+590h], rdi
0x14000c1d9  cmp     [rbx+4F0h], rdi
0x14000c1e0  jz      short loc_14000C1E9
0x14000c1e2  mov     [rbx+4F0h], rdi
0x14000c1e9  lea     rcx, [rbx+3F0h]; void *
0x14000c1f0  lea     r9, ??1?$CRBMap@U_FILE_EXTENT_IDENTIFIER@@PEAU_FILE_EXTENT_DATA@@V?$CElementTraits@U_FILE_EXTENT_IDENTIFIER@@@ATL@@V?$CElementTraits@PEAU_FILE_EXTENT_DATA@@@4@@ATL@@QEAA@XZ; void (*)(void *)
0x14000c1f7  mov     edx, 30h ; '0'; unsigned __int64
0x14000c1fc  lea     r8d, [rdx-2Eh]; unsigned __int64
0x14000c200  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x14000c205  mov     rcx, [rbx+380h]; Block
0x14000c20c  call    cs:__imp_free
0x14000c212  mov     [rbx+380h], rdi
0x14000c219  mov     rcx, [rbx+368h]; Block
0x14000c220  call    cs:__imp_free
0x14000c226  mov     [rbx+368h], rdi
0x14000c22d  mov     rcx, [rbx+360h]; Block
0x14000c234  call    cs:__imp_free
0x14000c23a  mov     [rbx+360h], rdi
0x14000c241  mov     rcx, [rbx+348h]; Block
0x14000c248  call    cs:__imp_free
0x14000c24e  mov     [rbx+348h], rdi
0x14000c255  mov     rcx, [rbx+340h]; Block
0x14000c25c  call    cs:__imp_free
0x14000c262  mov     [rbx+340h], rdi
0x14000c269  mov     rcx, [rbx+328h]; Block
0x14000c270  call    cs:__imp_free
0x14000c276  mov     [rbx+328h], rdi
0x14000c27d  mov     rcx, [rbx+308h]; hObject
0x14000c284  test    rcx, rcx
0x14000c287  jz      short loc_14000C28F
0x14000c289  call    cs:__imp_CloseHandle
0x14000c28f  mov     rcx, [rbx+300h]; hObject
0x14000c296  test    rcx, rcx
0x14000c299  jz      short loc_14000C2A1
0x14000c29b  call    cs:__imp_CloseHandle
0x14000c2a1  mov     rcx, [rbx+2B0h]; Block
0x14000c2a8  call    cs:__imp_free
0x14000c2ae  mov     [rbx+2B0h], rdi
0x14000c2b5  mov     rcx, [rbx+298h]; Block
0x14000c2bc  call    cs:__imp_free
0x14000c2c2  mov     [rbx+298h], rdi
0x14000c2c9  mov     rcx, [rbx+290h]; Block
0x14000c2d0  call    cs:__imp_free
0x14000c2d6  mov     [rbx+290h], rdi
0x14000c2dd  mov     rcx, [rbx+278h]; Block
0x14000c2e4  call    cs:__imp_free
0x14000c2ea  mov     [rbx+278h], rdi
0x14000c2f1  mov     rcx, [rbx+260h]; Block
0x14000c2f8  call    cs:__imp_free
0x14000c2fe  mov     [rbx+260h], rdi
0x14000c305  lea     rcx, [rbx+50h]
0x14000c309  call    ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)
0x14000c30e  lea     rcx, [rbx+20h]
0x14000c312  add     rsp, 38h
0x14000c316  pop     r14
0x14000c318  pop     rdi
0x14000c319  pop     rbp
0x14000c31a  pop     rbx
0x14000c31b  jmp     ?RemoveAll@?$CAtlList@V?$CAutoPtr@VCTierRegion@@@ATL@@V?$CAutoPtrElementTraits@VCTierRegion@@@2@@ATL@@QEAAXXZ; ATL::CAtlList<ATL::CAutoPtr<CTierRegion>,ATL::CAutoPtrElementTraits<CTierRegion>>::RemoveAll(void)
```
