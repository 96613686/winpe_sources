# DpspDecrementInstanceReference

- ea: `0x180012670`
- end: `0x180012841`
- name: `DpspDecrementInstanceReference`
- size: `465`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180001010`

## callees

- `0x180005ec0`
- `0x180006360`
- `0x180007360`
- `0x180007500`
- `0x180007f80`
- `0x180009090`
- `0x180012670`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800126ed`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800126ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800127f6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001270c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800127f6`

## string_xrefs

- `0x180012772`: `DpspRemoveInstanceFromList`

## pseudocode

```c
void __fastcall DpspDecrementInstanceReference(__int64 *a1)
{
  int v1; // r8d
  __int64 v2; // rbx
  signed __int32 v3; // edx
  int v4; // eax
  int v5; // eax
  int v6; // r8d
  __int64 v7; // rcx
  _QWORD *v8; // rdx
  __int64 Args; // [rsp+20h] [rbp-18h]
  int v10; // [rsp+40h] [rbp+8h] BYREF
  __int64 v11; // [rsp+48h] [rbp+10h] BYREF

  v10 = 1;
  if ( !a1 )
  {
    v1 = 918;
LABEL_3:
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (__int64)L"DpspDecrementInstanceReference",
      v1,
      (const wchar_t *)L"Error = %d",
      87);
    return;
  }
  v2 = *a1;
  if ( !*a1 )
  {
    v1 = 919;
    goto LABEL_3;
  }
  v3 = *(_DWORD *)(v2 + 72);
  v11 = *a1;
  if ( v3 <= 1 )
  {
LABEL_9:
    AcquireSRWLockExclusive(&g_SRWInstanceList);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v2 + 72), 0xFFFFFFFF) != 1 )
    {
LABEL_10:
      ReleaseSRWLockExclusive(&g_SRWInstanceList);
      return;
    }
    v5 = DpspInstanceCompleteNotification((struct INSTANCEINFO *)v2, &v10);
    if ( v5 < 0 )
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (__int64)L"DpspDecrementInstanceReference",
        968,
        (const wchar_t *)L"Error = %d",
        (unsigned __int16)v5);
    if ( !v10 )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v2 + 72));
      goto LABEL_10;
    }
    if ( v2 )
    {
      v7 = g_pInstanceHead;
      if ( g_pInstanceHead )
      {
        if ( g_pInstanceHead == v2 )
        {
          g_pInstanceHead = *(_QWORD *)(g_pInstanceHead + 1232);
        }
        else
        {
          while ( 1 )
          {
            v8 = (_QWORD *)(v7 + 1232);
            v7 = *(_QWORD *)(v7 + 1232);
            if ( v7 == v2 )
              break;
            if ( !v7 )
              goto LABEL_26;
          }
          *v8 = *(_QWORD *)(v2 + 1232);
        }
        goto LABEL_26;
      }
      v6 = 839;
    }
    else
    {
      v6 = 835;
    }
    LODWORD(Args) = 87;
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
      (__int64)L"DpspRemoveInstanceFromList",
      v6,
      (const wchar_t *)L"Error = %d",
      Args);
LABEL_26:
    g_lExpectedClientMessageCount += *(_DWORD *)(v2 + 76);
    ReleaseSRWLockExclusive(&g_SRWInstanceList);
    DpspCheckDiskUsage(v2);
    if ( *(int *)(v2 + 132) < 0 )
    {
      if ( (*(_DWORD *)(v2 + 104) & 8) != 0 )
        DpspRaiseScenarioDMFailedEvent(v2, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_SCENARIO_DM_FAILED);
      else
        DpspRaiseScenarioDPSFailedEvent(v2, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_SCENARIO_DPS_FAILED);
    }
    DpspFreeSpecificInstanceInfo((__int64)&v11);
    return;
  }
  while ( 1 )
  {
    v4 = _InterlockedCompareExchange((volatile signed __int32 *)(v2 + 72), v3 - 1, v3);
    if ( v3 == v4 )
      break;
    v3 = v4;
    if ( v4 <= 1 )
      goto LABEL_9;
  }
}

```

## disassembly

```asm
0x180012670  push    rbx
0x180012672  sub     rsp, 30h
0x180012676  mov     [rsp+38h+arg_0], 1
0x18001267e  test    rcx, rcx
0x180012681  jnz     short loc_1800126B0
0x180012683  mov     r8d, 396h; int
0x180012689  lea     r9, aErrorD; "Error = %d"
0x180012690  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180012698  lea     rdx, aDpspdecrementi; "DpspDecrementInstanceReference"
0x18001269f  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800126a6  call    WdipTraceError
0x1800126ab  jmp     loc_18001283B
0x1800126b0  mov     rbx, [rcx]
0x1800126b3  test    rbx, rbx
0x1800126b6  jnz     short loc_1800126C0
0x1800126b8  mov     r8d, 397h
0x1800126be  jmp     short loc_180012689
0x1800126c0  mov     edx, [rbx+48h]
0x1800126c3  mov     [rsp+38h+arg_8], rbx
0x1800126c8  cmp     edx, 1
0x1800126cb  jle     short loc_1800126E6
0x1800126cd  lea     ecx, [rdx-1]
0x1800126d0  mov     eax, edx
0x1800126d2  lock cmpxchg [rbx+48h], ecx
0x1800126d7  cmp     edx, eax
0x1800126d9  jz      loc_18001283B
0x1800126df  mov     edx, eax
0x1800126e1  cmp     eax, 1
0x1800126e4  jg      short loc_1800126CD
0x1800126e6  lea     rcx, g_SRWInstanceList; SRWLock
0x1800126ed  call    cs:__imp_AcquireSRWLockExclusive
0x1800126f3  or      eax, 0FFFFFFFFh
0x1800126f6  lock xadd [rbx+48h], eax
0x1800126fb  cmp     eax, 1
0x1800126fe  jz      short loc_180012713
0x180012700  lea     rcx, g_SRWInstanceList
0x180012707  add     rsp, 30h
0x18001270b  pop     rbx
0x18001270c  jmp     cs:__imp_ReleaseSRWLockExclusive
0x180012713  lea     rdx, [rsp+38h+arg_0]
0x180012718  mov     rcx, rbx; struct INSTANCEINFO *
0x18001271b  call    DpspInstanceCompleteNotification
0x180012720  test    eax, eax
0x180012722  jns     short loc_18001274B
0x180012724  movzx   eax, ax
0x180012727  lea     r9, aErrorD; "Error = %d"
0x18001272e  mov     r8d, 3C8h; int
0x180012734  mov     dword ptr [rsp+38h+Args], eax; Args
0x180012738  lea     rdx, aDpspdecrementi; "DpspDecrementInstanceReference"
0x18001273f  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012746  call    WdipTraceError
0x18001274b  cmp     [rsp+38h+arg_0], 0
0x180012750  jnz     short loc_180012758
0x180012752  lock inc dword ptr [rbx+48h]
0x180012756  jmp     short loc_180012700
0x180012758  test    rbx, rbx
0x18001275b  jnz     short loc_180012787
0x18001275d  mov     r8d, 343h; int
0x180012763  lea     r9, aErrorD; "Error = %d"
0x18001276a  mov     dword ptr [rsp+38h+Args], 57h ; 'W'; Args
0x180012772  lea     rdx, aDpspremoveinst_0; "DpspRemoveInstanceFromList"
0x180012779  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180012780  call    WdipTraceError
0x180012785  jmp     short loc_1800127DE
0x180012787  mov     rcx, cs:g_pInstanceHead
0x18001278e  test    rcx, rcx
0x180012791  jnz     short loc_18001279B
0x180012793  mov     r8d, 347h
0x180012799  jmp     short loc_180012763
0x18001279b  mov     rax, cs:g_pInstanceHead
0x1800127a2  cmp     rax, rbx
0x1800127a5  jnz     short loc_1800127BE
0x1800127a7  mov     rax, cs:g_pInstanceHead
0x1800127ae  mov     rcx, [rax+4D0h]
0x1800127b5  mov     cs:g_pInstanceHead, rcx
0x1800127bc  jmp     short loc_1800127DE
0x1800127be  lea     rdx, [rcx+4D0h]
0x1800127c5  mov     rcx, [rdx]
0x1800127c8  cmp     rcx, rbx
0x1800127cb  jz      short loc_1800127D4
0x1800127cd  test    rcx, rcx
0x1800127d0  jnz     short loc_1800127BE
0x1800127d2  jmp     short loc_1800127DE
0x1800127d4  mov     rax, [rbx+4D0h]
0x1800127db  mov     [rdx], rax
0x1800127de  mov     edx, cs:g_lExpectedClientMessageCount
0x1800127e4  lea     rcx, g_SRWInstanceList; SRWLock
0x1800127eb  mov     eax, [rbx+4Ch]
0x1800127ee  add     edx, eax
0x1800127f0  mov     cs:g_lExpectedClientMessageCount, edx
0x1800127f6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800127fc  mov     rcx, rbx
0x1800127ff  call    DpspCheckDiskUsage
0x180012804  cmp     dword ptr [rbx+84h], 0
0x18001280b  jge     short loc_180012831
0x18001280d  mov     eax, [rbx+68h]
0x180012810  mov     rcx, rbx
0x180012813  test    al, 8
0x180012815  jz      short loc_180012825
0x180012817  lea     rdx, WDI_DPS_EVENT_SCENARIO_DM_FAILED
0x18001281e  call    DpspRaiseScenarioDMFailedEvent
0x180012823  jmp     short loc_180012831
0x180012825  lea     rdx, WDI_DPS_EVENT_SCENARIO_DPS_FAILED
0x18001282c  call    DpspRaiseScenarioDPSFailedEvent
0x180012831  lea     rcx, [rsp+38h+arg_8]
0x180012836  call    DpspFreeSpecificInstanceInfo
0x18001283b  add     rsp, 30h
0x18001283f  pop     rbx
0x180012840  retn
```
