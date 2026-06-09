# CTieredVolume::HandleVolumeDismount(bool)

- ea: `0x1400100a0`
- end: `0x1400104ed`
- name: `?HandleVolumeDismount@CTieredVolume@@AEAAJ_N@Z`
- size: `1101`
- prototype: `__int64 __fastcall(JET_API_PTR ulContext, bool)`
- caller_count: `2`
- callee_count: `13`
- tags: ``

## callers

- `0x14000ce48`
- `0x1400127dc`

## callees

- `0x14000108c`
- `0x140004aa8`
- `0x140005698`
- `0x14000c7e0`
- `0x14000c8f8`
- `0x1400100a0`
- `0x1400164c8`
- `0x1400178cc`
- `0x140017b68`
- `0x140017f74`
- `0x140018044`
- `0x14001cb9c`
- `0x14003fbb0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010213`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140010213`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010299`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400102ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400103df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010118`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140010299`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400102ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1400103df`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010101`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140010101`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400100de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010249`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001039d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400100de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140010249`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14001039d`

## pseudocode

```c
__int64 __fastcall CTieredVolume::HandleVolumeDismount(JET_API_PTR ulContext, bool a2)
{
  RTL_SRWLOCK *v2; // rsi
  int v5; // edi
  int v6; // r8d
  _QWORD *v7; // rcx
  bool v9; // dl
  int v10; // eax
  bool v11; // dl
  int v12; // eax
  bool v13; // dl
  int v14; // eax
  unsigned int v15; // ebp
  int v16; // r8d
  int v17; // ecx
  _BYTE v18[32]; // [rsp+40h] [rbp-78h] BYREF
  _DWORD *v19; // [rsp+60h] [rbp-58h]
  __int64 v20; // [rsp+68h] [rbp-50h]
  __int64 v21; // [rsp+70h] [rbp-48h]
  _DWORD v22[2]; // [rsp+78h] [rbp-40h] BYREF

  ++*(_DWORD *)(ulContext + 1680);
  v2 = (RTL_SRWLOCK *)(ulContext + 24);
  v5 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)(ulContext + 24));
  if ( !*(_WORD *)(ulContext + 165) )
  {
    v5 = 1;
    SetEvent(*(HANDLE *)(ulContext + 768));
    *(_WORD *)(ulContext + 165) = 257;
  }
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  if ( !v5 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_ZDDDq(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        23,
        v6,
        ulContext + 672,
        0,
        0,
        *(_DWORD *)(ulContext + 128),
        ulContext);
    }
    return 0;
  }
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZDDDq(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      v6,
      ulContext + 672,
      0,
      0,
      *(_DWORD *)(ulContext + 128),
      ulContext);
    v7 = WPP_GLOBAL_Control;
  }
  if ( *(_DWORD *)(ulContext + 712) )
  {
    if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
      WPP_SF_DDq(v7[2]);
    WaitForSingleObject(*(HANDLE *)(ulContext + 776), 0xFFFFFFFF);
  }
  else if ( v7 != &WPP_GLOBAL_Control && (*((_BYTE *)v7 + 28) & 1) != 0 && *((_BYTE *)v7 + 25) >= 4u )
  {
    WPP_SF_Dq(v7[2], 26);
  }
  AcquireSRWLockExclusive(v2);
  if ( !*(_BYTE *)(ulContext + 165) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_Dq(*((_QWORD *)WPP_GLOBAL_Control + 2), 27);
    }
    *(_BYTE *)(ulContext + 166) = 0;
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  CTieredVolume::CloseJetDatabases((CTieredVolume *)ulContext, a2, 1, 0);
  ReleaseSRWLockExclusive(v2);
  v10 = TieringJetDatabase::WaitForDatabaseClose((TieringJetDatabase *)(ulContext + 1344), v9);
  if ( v10 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      28,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128),
      v10);
  }
  v12 = TieringJetDatabase::WaitForDatabaseClose((TieringJetDatabase *)(ulContext + 1504), v11);
  if ( v12 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      29,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128),
      v12);
  }
  v14 = TieringJetDatabase::WaitForDatabaseClose((TieringJetDatabase *)(ulContext + 1184), v13);
  v15 = v14;
  if ( v14 < 0
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      &WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids,
      *(unsigned int *)(ulContext + 128),
      v14);
  }
  AcquireSRWLockExclusive(v2);
  CTieredVolume::TeardownMovementSession(ulContext, 1);
  CTieredVolume::CloseJetInstance((CTieredVolume *)ulContext, a2, 0);
  *(_BYTE *)(ulContext + 721) = 0;
  *(_BYTE *)(ulContext + 723) = 0;
  *(_BYTE *)(ulContext + 162) = 0;
  *(_BYTE *)(ulContext + 166) = 0;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  CTieringEngineLib::AdjustNumberActiveVolumes(*(CTieringEngineLib **)(ulContext + 16), *(_DWORD *)(ulContext + 128), 0);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_ZDq(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, v16, ulContext + 672, *(_DWORD *)(ulContext + 128), ulContext);
  }
  if ( (unsigned int)dword_14004C098 > 5
    && (qword_14004C0A8 & 0x200000000000LL) != 0
    && (qword_14004C0B0 & 0x200000000000LL) == qword_14004C0B0 )
  {
    v20 = 2;
    v19 = v22;
    v17 = *(unsigned __int16 *)(ulContext + 696);
    v21 = *(_QWORD *)(ulContext + 704);
    v22[0] = v17;
    v22[1] = 0;
    tlgWriteTransfer_EventWriteTransfer(&dword_14004C098, word_140045C82, 0, 0, 4, v18);
  }
  return v15;
}

```

## disassembly

```asm
0x1400100a0  mov     [rsp+arg_10], rbx
0x1400100a5  push    rbp
0x1400100a6  push    rsi
0x1400100a7  push    rdi
0x1400100a8  push    r14
0x1400100aa  push    r15
0x1400100ac  sub     rsp, 90h
0x1400100b3  mov     rax, cs:__security_cookie
0x1400100ba  xor     rax, rsp
0x1400100bd  mov     [rsp+0B8h+var_38], rax
0x1400100c5  inc     dword ptr [rcx+690h]
0x1400100cb  lea     rsi, [rcx+18h]
0x1400100cf  mov     rbx, rcx
0x1400100d2  xor     r15d, r15d
0x1400100d5  mov     rcx, rsi; SRWLock
0x1400100d8  mov     r14b, dl
0x1400100db  mov     edi, r15d
0x1400100de  call    cs:__imp_AcquireSRWLockExclusive
0x1400100e4  cmp     [rbx+0A5h], r15b
0x1400100eb  jnz     short loc_140010110
0x1400100ed  cmp     [rbx+0A6h], r15b
0x1400100f4  jnz     short loc_140010110
0x1400100f6  mov     rcx, [rbx+300h]; hEvent
0x1400100fd  lea     edi, [r15+1]
0x140010101  call    cs:__imp_SetEvent
0x140010107  mov     word ptr [rbx+0A5h], 101h
0x140010110  test    rsi, rsi
0x140010113  jz      short loc_14001011E
0x140010115  mov     rcx, rsi; SRWLock
0x140010118  call    cs:__imp_ReleaseSRWLockExclusive
0x14001011e  test    edi, edi
0x140010120  jnz     short loc_140010180
0x140010122  mov     rcx, cs:WPP_GLOBAL_Control
0x140010129  lea     rdi, WPP_GLOBAL_Control
0x140010130  cmp     rcx, rdi
0x140010133  jz      loc_14001029F
0x140010139  test    byte ptr [rcx+1Ch], 1
0x14001013d  jz      loc_14001029F
0x140010143  cmp     byte ptr [rcx+19h], 4
0x140010147  jb      loc_14001029F
0x14001014d  mov     eax, [rbx+80h]
0x140010153  lea     r9, [rbx+2A0h]
0x14001015a  mov     rcx, [rcx+10h]
0x14001015e  mov     edx, 17h
0x140010163  mov     [rsp+0B8h+var_80], rbx
0x140010168  mov     [rsp+0B8h+var_88], eax
0x14001016c  mov     dword ptr [rsp+0B8h+var_90], r15d
0x140010171  mov     dword ptr [rsp+0B8h+var_98], r15d
0x140010176  call    WPP_SF_ZDDDq
0x14001017b  jmp     loc_14001029F
0x140010180  mov     rcx, cs:WPP_GLOBAL_Control
0x140010187  lea     rdi, WPP_GLOBAL_Control
0x14001018e  cmp     rcx, rdi
0x140010191  jz      short loc_1400101D4
0x140010193  test    byte ptr [rcx+1Ch], 1
0x140010197  jz      short loc_1400101D4
0x140010199  cmp     byte ptr [rcx+19h], 4
0x14001019d  jb      short loc_1400101D4
0x14001019f  mov     eax, [rbx+80h]
0x1400101a5  lea     r9, [rbx+2A0h]
0x1400101ac  mov     rcx, [rcx+10h]
0x1400101b0  mov     edx, 18h
0x1400101b5  mov     [rsp+0B8h+var_80], rbx
0x1400101ba  mov     [rsp+0B8h+var_88], eax
0x1400101be  mov     dword ptr [rsp+0B8h+var_90], r15d
0x1400101c3  mov     dword ptr [rsp+0B8h+var_98], r15d
0x1400101c8  call    WPP_SF_ZDDDq
0x1400101cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400101d4  mov     r9d, [rbx+2C8h]
0x1400101db  test    r9d, r9d
0x1400101de  jz      short loc_14001021B
0x1400101e0  cmp     rcx, rdi
0x1400101e3  jz      short loc_140010209
0x1400101e5  test    byte ptr [rcx+1Ch], 1
0x1400101e9  jz      short loc_140010209
0x1400101eb  cmp     byte ptr [rcx+19h], 4
0x1400101ef  jb      short loc_140010209
0x1400101f1  mov     eax, [rbx+80h]
0x1400101f7  mov     rcx, [rcx+10h]
0x1400101fb  mov     [rsp+0B8h+var_90], rbx
0x140010200  mov     dword ptr [rsp+0B8h+var_98], eax
0x140010204  call    WPP_SF_DDq
0x140010209  mov     rcx, [rbx+308h]; hHandle
0x140010210  or      edx, 0FFFFFFFFh; dwMilliseconds
0x140010213  call    cs:__imp_WaitForSingleObject
0x140010219  jmp     short loc_140010246
0x14001021b  cmp     rcx, rdi
0x14001021e  jz      short loc_140010246
0x140010220  test    byte ptr [rcx+1Ch], 1
0x140010224  jz      short loc_140010246
0x140010226  cmp     byte ptr [rcx+19h], 4
0x14001022a  jb      short loc_140010246
0x14001022c  mov     r9d, [rbx+80h]
0x140010233  mov     edx, 1Ah
0x140010238  mov     rcx, [rcx+10h]
0x14001023c  mov     [rsp+0B8h+var_98], rbx
0x140010241  call    WPP_SF_Dq
0x140010246  mov     rcx, rsi; SRWLock
0x140010249  call    cs:__imp_AcquireSRWLockExclusive
0x14001024f  cmp     [rbx+0A5h], r15b
0x140010256  jnz     short loc_1400102A6
0x140010258  mov     rcx, cs:WPP_GLOBAL_Control
0x14001025f  cmp     rcx, rdi
0x140010262  jz      short loc_14001028A
0x140010264  test    byte ptr [rcx+1Ch], 1
0x140010268  jz      short loc_14001028A
0x14001026a  cmp     byte ptr [rcx+19h], 4
0x14001026e  jb      short loc_14001028A
0x140010270  mov     r9d, [rbx+80h]
0x140010277  mov     edx, 1Bh
0x14001027c  mov     rcx, [rcx+10h]
0x140010280  mov     [rsp+0B8h+var_98], rbx
0x140010285  call    WPP_SF_Dq
0x14001028a  mov     [rbx+0A6h], r15b
0x140010291  test    rsi, rsi
0x140010294  jz      short loc_14001029F
0x140010296  mov     rcx, rsi; SRWLock
0x140010299  call    cs:__imp_ReleaseSRWLockExclusive
0x14001029f  xor     eax, eax
0x1400102a1  jmp     loc_1400104C6
0x1400102a6  xor     r9d, r9d; bool
0x1400102a9  mov     r8b, 1; bool
0x1400102ac  mov     dl, r14b; bool
0x1400102af  mov     rcx, rbx; this
0x1400102b2  call    ?CloseJetDatabases@CTieredVolume@@QEAAX_N00@Z; CTieredVolume::CloseJetDatabases(bool,bool,bool)
0x1400102b7  mov     rcx, rsi; SRWLock
0x1400102ba  call    cs:__imp_ReleaseSRWLockExclusive
0x1400102c0  lea     rcx, [rbx+540h]; this
0x1400102c7  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x1400102cc  test    eax, eax
0x1400102ce  jns     short loc_140010308
0x1400102d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400102d7  cmp     rcx, rdi
0x1400102da  jz      short loc_140010308
0x1400102dc  test    byte ptr [rcx+1Ch], 1
0x1400102e0  jz      short loc_140010308
0x1400102e2  cmp     byte ptr [rcx+19h], 2
0x1400102e6  jb      short loc_140010308
0x1400102e8  mov     r9d, [rbx+80h]
0x1400102ef  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x1400102f6  mov     rcx, [rcx+10h]
0x1400102fa  mov     edx, 1Ch
0x1400102ff  mov     dword ptr [rsp+0B8h+var_98], eax
0x140010303  call    WPP_SF_Dd
0x140010308  lea     rcx, [rbx+5E0h]; this
0x14001030f  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x140010314  test    eax, eax
0x140010316  jns     short loc_140010350
0x140010318  mov     rcx, cs:WPP_GLOBAL_Control
0x14001031f  cmp     rcx, rdi
0x140010322  jz      short loc_140010350
0x140010324  test    byte ptr [rcx+1Ch], 1
0x140010328  jz      short loc_140010350
0x14001032a  cmp     byte ptr [rcx+19h], 2
0x14001032e  jb      short loc_140010350
0x140010330  mov     r9d, [rbx+80h]
0x140010337  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x14001033e  mov     rcx, [rcx+10h]
0x140010342  mov     edx, 1Dh
0x140010347  mov     dword ptr [rsp+0B8h+var_98], eax
0x14001034b  call    WPP_SF_Dd
0x140010350  lea     rcx, [rbx+4A0h]; this
0x140010357  call    ?WaitForDatabaseClose@TieringJetDatabase@@QEAAJ_N@Z; TieringJetDatabase::WaitForDatabaseClose(bool)
0x14001035c  mov     ebp, eax
0x14001035e  test    eax, eax
0x140010360  jns     short loc_14001039A
0x140010362  mov     rcx, cs:WPP_GLOBAL_Control
0x140010369  cmp     rcx, rdi
0x14001036c  jz      short loc_14001039A
0x14001036e  test    byte ptr [rcx+1Ch], 1
0x140010372  jz      short loc_14001039A
0x140010374  cmp     byte ptr [rcx+19h], 2
0x140010378  jb      short loc_14001039A
0x14001037a  mov     r9d, [rbx+80h]
0x140010381  lea     r8, WPP_bd87e4f049883b980cd0e6b666001fbc_Traceguids
0x140010388  mov     rcx, [rcx+10h]
0x14001038c  mov     edx, 1Eh
0x140010391  mov     dword ptr [rsp+0B8h+var_98], eax
0x140010395  call    WPP_SF_Dd
0x14001039a  mov     rcx, rsi; SRWLock
0x14001039d  call    cs:__imp_AcquireSRWLockExclusive
0x1400103a3  mov     dl, 1; bool
0x1400103a5  mov     rcx, rbx; ulContext
0x1400103a8  call    ?TeardownMovementSession@CTieredVolume@@AEAAJ_N@Z; CTieredVolume::TeardownMovementSession(bool)
0x1400103ad  xor     r8d, r8d; bool
0x1400103b0  mov     dl, r14b; bool
0x1400103b3  mov     rcx, rbx; this
0x1400103b6  call    ?CloseJetInstance@CTieredVolume@@QEAAX_N0@Z; CTieredVolume::CloseJetInstance(bool,bool)
0x1400103bb  mov     [rbx+2D1h], r15b
0x1400103c2  mov     [rbx+2D3h], r15b
0x1400103c9  mov     [rbx+0A2h], r15b
0x1400103d0  mov     [rbx+0A6h], r15b
0x1400103d7  test    rsi, rsi
0x1400103da  jz      short loc_1400103E5
0x1400103dc  mov     rcx, rsi; SRWLock
0x1400103df  call    cs:__imp_ReleaseSRWLockExclusive
0x1400103e5  mov     edx, [rbx+80h]; unsigned int
0x1400103eb  xor     r8d, r8d; bool
0x1400103ee  mov     rcx, [rbx+10h]; this
0x1400103f2  call    ?AdjustNumberActiveVolumes@CTieringEngineLib@@QEAAXK_N@Z; CTieringEngineLib::AdjustNumberActiveVolumes(ulong,bool)
0x1400103f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400103fe  cmp     rcx, rdi
0x140010401  jz      short loc_140010433
0x140010403  test    byte ptr [rcx+1Ch], 1
0x140010407  jz      short loc_140010433
0x140010409  cmp     byte ptr [rcx+19h], 4
0x14001040d  jb      short loc_140010433
0x14001040f  mov     eax, [rbx+80h]
0x140010415  lea     r9, [rbx+2A0h]
0x14001041c  mov     rcx, [rcx+10h]
0x140010420  mov     edx, 1Fh
0x140010425  mov     [rsp+0B8h+var_90], rbx
0x14001042a  mov     dword ptr [rsp+0B8h+var_98], eax
0x14001042e  call    WPP_SF_ZDq
0x140010433  mov     eax, cs:dword_14004C098
0x140010439  cmp     eax, 5
0x14001043c  jbe     loc_1400104C4
0x140010442  mov     rcx, cs:qword_14004C0B0
0x140010449  mov     rdx, 200000000000h
0x140010453  mov     rax, cs:qword_14004C0A8
0x14001045a  test    rdx, rax
0x14001045d  jz      short loc_1400104C4
0x14001045f  mov     rax, rcx
0x140010462  and     rax, rdx
0x140010465  cmp     rax, rcx
0x140010468  jnz     short loc_1400104C4
0x14001046a  mov     [rsp+0B8h+var_50], 2
0x140010473  lea     rax, [rsp+0B8h+var_40]
0x140010478  mov     [rsp+0B8h+var_58], rax
0x14001047d  lea     rdx, word_140045C82
0x140010484  mov     rax, [rbx+2C0h]
0x14001048b  xor     r9d, r9d
0x14001048e  movzx   ecx, word ptr [rbx+2B8h]
0x140010495  xor     r8d, r8d
0x140010498  mov     [rsp+0B8h+var_48], rax
0x14001049d  lea     rax, [rsp+0B8h+var_78]
0x1400104a2  mov     [rsp+0B8h+var_40], ecx
0x1400104a6  lea     rcx, dword_14004C098
0x1400104ad  mov     [rsp+0B8h+var_90], rax
0x1400104b2  mov     dword ptr [rsp+0B8h+var_98], 4
0x1400104ba  mov     [rsp+0B8h+var_3C], r15d
0x1400104bf  call    _tlgWriteTransfer_EventWriteTransfer
0x1400104c4  mov     eax, ebp
0x1400104c6  mov     rcx, [rsp+0B8h+var_38]
0x1400104ce  xor     rcx, rsp; StackCookie
0x1400104d1  call    __security_check_cookie
0x1400104d6  mov     rbx, [rsp+0B8h+arg_10]
0x1400104de  add     rsp, 90h
0x1400104e5  pop     r15
0x1400104e7  pop     r14
0x1400104e9  pop     rdi
0x1400104ea  pop     rsi
0x1400104eb  pop     rbp
0x1400104ec  retn
```
