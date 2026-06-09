# DpspAttemptScenarioCompletionEx

- ea: `0x180002090`
- end: `0x18000250a`
- name: `DpspAttemptScenarioCompletionEx`
- size: `1146`
- prototype: `__int64 __fastcall(struct INSTANCEINFO *)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x180001830`
- `0x180002510`
- `0x180003830`
- `0x180004de4`
- `0x18000c21c`
- `0x180014df0`

## callees

- `0x180001100`
- `0x180001ff0`
- `0x180002090`
- `0x1800057b0`
- `0x180005ec0`
- `0x180007360`
- `0x180007500`
- `0x180009090`
- `0x18001585c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002488`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002488`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000211c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002190`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000211c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180002190`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000214f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002359`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002408`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000214f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002359`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180002408`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000210d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000210d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022b2`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800022bc`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002242`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800020ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002215`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180002242`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000247e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000247e`

## string_xrefs

- `0x1800020b7`: `DpspAttemptScenarioCompletionEx`
- `0x18000228c`: `DpspInstanceCompleteNotification`
- `0x1800022f9`: `DpspInstanceCompleteNotification`
- `0x18000238e`: `DpspRemoveInstanceFromList`

## pseudocode

```c
__int64 __fastcall DpspAttemptScenarioCompletionEx(struct INSTANCEINFO *a1)
{
  __int64 result; // rax
  unsigned int v3; // ebp
  __int64 v4; // rcx
  __int64 v5; // rcx
  signed __int32 v6; // edx
  int v7; // eax
  bool v8; // zf
  __int64 v9; // rax
  int v10; // r14d
  int v11; // r15d
  __int64 v12; // rdi
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rcx
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  int v18; // eax
  const struct _GUID *v19; // rcx
  int v20; // r8d
  signed int InstanceDirectorySize; // eax
  bool v22; // sf
  __int64 Args; // [rsp+20h] [rbp-38h]
  __int64 v24; // [rsp+70h] [rbp+18h] BYREF
  struct INSTANCEINFO *v25; // [rsp+78h] [rbp+20h] BYREF

  result = DpspAttemptScenarioCompletion(a1);
  v3 = result;
  if ( (int)result < 0 )
  {
    WdipTraceError(
      (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\trace.cpp",
      (__int64)L"DpspAttemptScenarioCompletionEx",
      1402,
      (const wchar_t *)L"Error = %d",
      (unsigned __int16)result);
    if ( _interlockedbittestandreset((volatile signed __int32 *)a1 + 26, 4u) )
    {
      v4 = *((_QWORD *)a1 + 101);
      if ( v4 )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v4 + 64));
        --*(_DWORD *)(*((_QWORD *)a1 + 101) + 44LL);
        v5 = *((_QWORD *)a1 + 101);
        if ( v5 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v5 + 64));
      }
    }
    if ( a1 )
      AcquireSRWLockExclusive((PSRWLOCK)a1 + 2);
    DpspSendClientFeedback(a1, 4, v3);
    if ( (*((_DWORD *)a1 + 26) & 0x20) != 0 )
      _InterlockedOr((volatile signed __int32 *)a1 + 26, 4u);
    _InterlockedAnd((volatile signed __int32 *)a1 + 26, 0xFFFFFBFF);
    if ( a1 )
      ReleaseSRWLockExclusive((PSRWLOCK)a1 + 2);
    *((_DWORD *)a1 + 33) = 0;
    v6 = *((_DWORD *)a1 + 18);
    v25 = a1;
    if ( v6 > 1 )
    {
      do
      {
        v7 = _InterlockedCompareExchange((volatile signed __int32 *)a1 + 18, v6 - 1, v6);
        if ( v6 == v7 )
          return v3;
        v6 = v7;
      }
      while ( v7 > 1 );
    }
    AcquireSRWLockExclusive(&g_SRWInstanceList);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)a1 + 18, 0xFFFFFFFF) != 1 )
    {
LABEL_40:
      ReleaseSRWLockExclusive(&g_SRWInstanceList);
      return v3;
    }
    v8 = *((_QWORD *)a1 + 152) == 0;
    LODWORD(v24) = 0;
    if ( !v8 && (*((_DWORD *)a1 + 26) & 0x20) == 0 )
    {
      _InterlockedOr((volatile signed __int32 *)a1 + 26, 0x200u);
      v9 = *((unsigned int *)a1 + 28);
      if ( (unsigned int)v9 <= *((_DWORD *)a1 + 29) )
      {
        v10 = 0;
        v11 = 1;
        while ( 1 )
        {
          v12 = *((_QWORD *)a1 + v9 + 102);
          if ( !v12 )
          {
            LODWORD(Args) = 16389;
            LOWORD(v10) = 16389;
            WdipTraceError(
              (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
              (__int64)L"DpspInstanceCompleteNotification",
              1229,
              (const wchar_t *)L"Error = %d",
              Args);
            goto LABEL_37;
          }
          EnterCriticalSection((LPCRITICAL_SECTION)(v12 + 64));
          if ( (*(_BYTE *)(v12 + 152) & 0x20) != 0 && *(_DWORD *)(v12 + 24) == 2 )
          {
            v13 = *(_QWORD *)(v12 + 176);
            if ( v13 )
              EnterCriticalSection((LPCRITICAL_SECTION)(v13 + 72));
            if ( **(_DWORD **)(v12 + 176) == 2 )
            {
              *((_QWORD *)a1 + 101) = v12;
              v14 = DpspValidateSession((struct __SESSIONINFO *)v12, a1);
              v10 = v14;
              if ( v14 < 0 )
              {
                LODWORD(Args) = (unsigned __int16)v14;
                WdipTraceError(
                  (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpscli.cpp",
                  (__int64)L"DpspInstanceCompleteNotification",
                  1261,
                  (const wchar_t *)L"Error = %d",
                  Args);
                v10 = 0;
              }
            }
            v15 = *(_QWORD *)(v12 + 176);
            if ( v15 )
              LeaveCriticalSection((LPCRITICAL_SECTION)(v15 + 72));
          }
          LeaveCriticalSection((LPCRITICAL_SECTION)(v12 + 64));
          if ( (_DWORD)v24 == 1 )
            break;
          v9 = (unsigned int)++*((_DWORD *)a1 + 28);
          if ( (unsigned int)v9 > *((_DWORD *)a1 + 29) )
            goto LABEL_34;
        }
        v11 = 0;
LABEL_34:
        if ( v10 >= 0 )
          goto LABEL_38;
LABEL_37:
        LODWORD(Args) = (unsigned __int16)v10;
        WdipTraceError(
          (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
          (__int64)L"DpspDecrementInstanceReference",
          968,
          (const wchar_t *)L"Error = %d",
          Args);
LABEL_38:
        if ( !v11 )
        {
          _InterlockedIncrement((volatile signed __int32 *)a1 + 18);
          goto LABEL_40;
        }
      }
    }
    v16 = g_pInstanceHead;
    if ( g_pInstanceHead )
    {
      if ( (struct INSTANCEINFO *)g_pInstanceHead == a1 )
      {
        g_pInstanceHead = *(_QWORD *)(g_pInstanceHead + 1232);
      }
      else
      {
        while ( 1 )
        {
          v17 = (_QWORD *)(v16 + 1232);
          v16 = *(_QWORD *)(v16 + 1232);
          if ( (struct INSTANCEINFO *)v16 == a1 )
            break;
          if ( !v16 )
            goto LABEL_49;
        }
        *v17 = *((_QWORD *)a1 + 154);
      }
    }
    else
    {
      LODWORD(Args) = 87;
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\util.cpp",
        (__int64)L"DpspRemoveInstanceFromList",
        839,
        (const wchar_t *)L"Error = %d",
        Args);
    }
LABEL_49:
    g_lExpectedClientMessageCount += *((_DWORD *)a1 + 19);
    ReleaseSRWLockExclusive(&g_SRWInstanceList);
    v18 = *((_DWORD *)a1 + 26);
    v24 = 0;
    if ( (v18 & 0x80u) != 0 )
    {
      v19 = (const struct _GUID *)*((_QWORD *)a1 + 152);
      if ( v19 )
      {
        InstanceDirectorySize = DpspGetInstanceDirectorySize(v19, (const struct _GUID *)((char *)a1 + 24), &v24);
        if ( InstanceDirectorySize >= 0 )
        {
          if ( v24 + _InterlockedExchangeAdd64(&g_CurrentDirSize, v24) < g_DirSizeLimit
            || SetEvent(g_hDataRetentionControl) )
          {
            goto LABEL_62;
          }
          InstanceDirectorySize = GetLastError();
          v22 = InstanceDirectorySize < 0;
          if ( InstanceDirectorySize > 0 )
          {
            InstanceDirectorySize = (unsigned __int16)InstanceDirectorySize | 0x80070000;
            v22 = InstanceDirectorySize < 0;
          }
          if ( !v22 )
            goto LABEL_62;
          v20 = 116;
        }
        else
        {
          v20 = 96;
        }
        LODWORD(Args) = (unsigned __int16)InstanceDirectorySize;
      }
      else
      {
        LODWORD(Args) = 16389;
        v20 = 90;
      }
      WdipTraceError(
        (__int64)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpsdataret.cpp",
        (__int64)L"DpspCheckDiskUsage",
        v20,
        (const wchar_t *)L"Error = %d",
        Args);
    }
LABEL_62:
    if ( *((int *)a1 + 33) < 0 )
    {
      if ( (*((_DWORD *)a1 + 26) & 8) != 0 )
        DpspRaiseScenarioDMFailedEvent((__int64)a1, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_SCENARIO_DM_FAILED);
      else
        DpspRaiseScenarioDPSFailedEvent((__int64)a1, (const EVENT_DESCRIPTOR *)WDI_DPS_EVENT_SCENARIO_DPS_FAILED);
    }
    DpspFreeSpecificInstanceInfo(&v25);
    return v3;
  }
  return result;
}

```

## disassembly

```asm
0x180002090  push    rbx
0x180002092  push    rbp
0x180002093  sub     rsp, 48h
0x180002097  mov     rbx, rcx
0x18000209a  call    DpspAttemptScenarioCompletion
0x18000209f  mov     ebp, eax
0x1800020a1  test    eax, eax
0x1800020a3  jns     loc_180002503
0x1800020a9  movzx   ecx, bp
0x1800020ac  lea     r9, aErrorD; "Error = %d"
0x1800020b3  mov     dword ptr [rsp+58h+Args], ecx; Args
0x1800020b7  lea     rdx, aDpspattemptsce; "DpspAttemptScenarioCompletionEx"
0x1800020be  lea     rcx, aClientcoreBase_7; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800020c5  mov     [rsp+58h+var_18], rdi
0x1800020ca  mov     r8d, 57Ah; int
0x1800020d0  call    WdipTraceError
0x1800020d5  lock btr dword ptr [rbx+68h], 4
0x1800020db  jnb     short loc_180002113
0x1800020dd  mov     rcx, [rbx+328h]
0x1800020e4  test    rcx, rcx
0x1800020e7  jz      short loc_180002113
0x1800020e9  add     rcx, 40h ; '@'; lpCriticalSection
0x1800020ed  call    cs:__imp_EnterCriticalSection
0x1800020f3  mov     rax, [rbx+328h]
0x1800020fa  dec     dword ptr [rax+2Ch]
0x1800020fd  mov     rcx, [rbx+328h]
0x180002104  test    rcx, rcx
0x180002107  jz      short loc_180002113
0x180002109  add     rcx, 40h ; '@'; lpCriticalSection
0x18000210d  call    cs:__imp_LeaveCriticalSection
0x180002113  test    rbx, rbx
0x180002116  jz      short loc_180002122
0x180002118  lea     rcx, [rbx+10h]; SRWLock
0x18000211c  call    cs:__imp_AcquireSRWLockExclusive
0x180002122  mov     r8d, ebp
0x180002125  mov     edx, 4
0x18000212a  mov     rcx, rbx
0x18000212d  call    DpspSendClientFeedback
0x180002132  mov     eax, [rbx+68h]
0x180002135  test    al, 20h
0x180002137  jz      short loc_18000213E
0x180002139  lock or dword ptr [rbx+68h], 4
0x18000213e  lock and dword ptr [rbx+68h], 0FFFFFBFFh
0x180002146  test    rbx, rbx
0x180002149  jz      short loc_180002155
0x18000214b  lea     rcx, [rbx+10h]; SRWLock
0x18000214f  call    cs:__imp_ReleaseSRWLockExclusive
0x180002155  mov     dword ptr [rbx+84h], 0
0x18000215f  mov     edx, [rbx+48h]
0x180002162  mov     [rsp+58h+arg_18], rbx
0x180002167  cmp     edx, 1
0x18000216a  jle     short loc_180002189
0x18000216c  nop     dword ptr [rax+00h]
0x180002170  lea     ecx, [rdx-1]
0x180002173  mov     eax, edx
0x180002175  lock cmpxchg [rbx+48h], ecx
0x18000217a  cmp     edx, eax
0x18000217c  jz      loc_1800024FC
0x180002182  mov     edx, eax
0x180002184  cmp     eax, 1
0x180002187  jg      short loc_180002170
0x180002189  lea     rcx, g_SRWInstanceList; SRWLock
0x180002190  call    cs:__imp_AcquireSRWLockExclusive
0x180002196  mov     eax, 0FFFFFFFFh
0x18000219b  lock xadd [rbx+48h], eax
0x1800021a0  cmp     eax, 1
0x1800021a3  jnz     loc_180002352
0x1800021a9  cmp     qword ptr [rbx+4C0h], 0
0x1800021b1  mov     dword ptr [rsp+58h+arg_10], 0
0x1800021b9  jz      loc_18000236D
0x1800021bf  mov     eax, [rbx+68h]
0x1800021c2  test    al, 20h
0x1800021c4  jnz     loc_18000236D
0x1800021ca  lock or dword ptr [rbx+68h], 200h
0x1800021d2  mov     eax, [rbx+70h]
0x1800021d5  cmp     eax, [rbx+74h]
0x1800021d8  ja      loc_18000236D
0x1800021de  mov     [rsp+58h+var_20], r14
0x1800021e3  xor     r14d, r14d
0x1800021e6  mov     [rsp+58h+var_28], r15
0x1800021eb  mov     r15d, 1
0x1800021f1  mov     [rsp+58h+arg_0], rsi
0x1800021f6  nop     word ptr [rax+rax+00000000h]
0x180002200  mov     rdi, [rbx+rax*8+330h]
0x180002208  test    rdi, rdi
0x18000220b  jz      loc_1800022E4
0x180002211  lea     rcx, [rdi+40h]; lpCriticalSection
0x180002215  call    cs:__imp_EnterCriticalSection
0x18000221b  test    byte ptr [rdi+98h], 20h
0x180002222  jz      loc_1800022B8
0x180002228  cmp     dword ptr [rdi+18h], 2
0x18000222c  jnz     loc_1800022B8
0x180002232  mov     rcx, [rdi+0B0h]
0x180002239  test    rcx, rcx
0x18000223c  jz      short loc_180002248
0x18000223e  add     rcx, 48h ; 'H'; lpCriticalSection
0x180002242  call    cs:__imp_EnterCriticalSection
0x180002248  mov     rax, [rdi+0B0h]
0x18000224f  cmp     dword ptr [rax], 2
0x180002252  jnz     short loc_1800022A2
0x180002254  mov     r9d, 3
0x18000225a  mov     [rbx+328h], rdi
0x180002261  lea     r8, [rsp+58h+arg_10]
0x180002266  mov     rdx, rbx; struct INSTANCEINFO *
0x180002269  mov     rcx, rdi; struct __SESSIONINFO *
0x18000226c  call    DpspValidateSession
0x180002271  mov     r14d, eax
0x180002274  test    eax, eax
0x180002276  jns     short loc_1800022A2
0x180002278  movzx   eax, ax
0x18000227b  lea     r9, aErrorD; "Error = %d"
0x180002282  mov     r8d, 4EDh; int
0x180002288  mov     dword ptr [rsp+58h+Args], eax; Args
0x18000228c  lea     rdx, aDpspinstanceco; "DpspInstanceCompleteNotification"
0x180002293  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000229a  call    WdipTraceError
0x18000229f  xor     r14d, r14d
0x1800022a2  mov     rcx, [rdi+0B0h]
0x1800022a9  test    rcx, rcx
0x1800022ac  jz      short loc_1800022B8
0x1800022ae  add     rcx, 48h ; 'H'; lpCriticalSection
0x1800022b2  call    cs:__imp_LeaveCriticalSection
0x1800022b8  lea     rcx, [rdi+40h]; lpCriticalSection
0x1800022bc  call    cs:__imp_LeaveCriticalSection
0x1800022c2  cmp     dword ptr [rsp+58h+arg_10], r15d
0x1800022c7  jz      short loc_1800022DA
0x1800022c9  inc     dword ptr [rbx+70h]
0x1800022cc  mov     eax, [rbx+70h]
0x1800022cf  cmp     eax, [rbx+74h]
0x1800022d2  jbe     loc_180002200
0x1800022d8  jmp     short loc_1800022DD
0x1800022da  xor     r15d, r15d
0x1800022dd  test    r14d, r14d
0x1800022e0  jns     short loc_18000233A
0x1800022e2  jmp     short loc_180002312
0x1800022e4  lea     r9, aErrorD; "Error = %d"
0x1800022eb  mov     dword ptr [rsp+58h+Args], 4005h; Args
0x1800022f3  mov     r8d, 4CDh; int
0x1800022f9  lea     rdx, aDpspinstanceco; "DpspInstanceCompleteNotification"
0x180002300  lea     rcx, aClientcoreBase_12; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002307  mov     r14d, 80004005h
0x18000230d  call    WdipTraceError
0x180002312  movzx   eax, r14w
0x180002316  lea     r9, aErrorD; "Error = %d"
0x18000231d  mov     r8d, 3C8h; int
0x180002323  mov     dword ptr [rsp+58h+Args], eax; Args
0x180002327  lea     rdx, aDpspdecrementi; "DpspDecrementInstanceReference"
0x18000232e  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180002335  call    WdipTraceError
0x18000233a  mov     r14, [rsp+58h+var_20]
0x18000233f  test    r15d, r15d
0x180002342  mov     r15, [rsp+58h+var_28]
0x180002347  mov     rsi, [rsp+58h+arg_0]
0x18000234c  jnz     short loc_18000236D
0x18000234e  lock inc dword ptr [rbx+48h]
0x180002352  lea     rcx, g_SRWInstanceList; SRWLock
0x180002359  call    cs:__imp_ReleaseSRWLockExclusive
0x18000235f  mov     rdi, [rsp+58h+var_18]
0x180002364  mov     eax, ebp
0x180002366  add     rsp, 48h
0x18000236a  pop     rbp
0x18000236b  pop     rbx
0x18000236c  retn
0x18000236d  mov     rdx, cs:g_pInstanceHead
0x180002374  test    rdx, rdx
0x180002377  jnz     short loc_1800023A3
0x180002379  lea     r9, aErrorD; "Error = %d"
0x180002380  mov     dword ptr [rsp+58h+Args], 57h ; 'W'; Args
0x180002388  mov     r8d, 347h; int
0x18000238e  lea     rdx, aDpspremoveinst_0; "DpspRemoveInstanceFromList"
0x180002395  lea     rcx, aClientcoreBase_11; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x18000239c  call    WdipTraceError
0x1800023a1  jmp     short loc_1800023F0
0x1800023a3  mov     rax, cs:g_pInstanceHead
0x1800023aa  cmp     rax, rbx
0x1800023ad  jnz     short loc_1800023D0
0x1800023af  mov     rax, cs:g_pInstanceHead
0x1800023b6  mov     rcx, [rax+4D0h]
0x1800023bd  mov     cs:g_pInstanceHead, rcx
0x1800023c4  jmp     short loc_1800023F0
0x1800023d0  lea     rcx, [rdx+4D0h]
0x1800023d7  mov     rdx, [rcx]
0x1800023da  cmp     rdx, rbx
0x1800023dd  jz      short loc_1800023E6
0x1800023df  test    rdx, rdx
0x1800023e2  jnz     short loc_1800023D0
0x1800023e4  jmp     short loc_1800023F0
0x1800023e6  mov     rax, [rbx+4D0h]
0x1800023ed  mov     [rcx], rax
0x1800023f0  mov     ecx, cs:g_lExpectedClientMessageCount
0x1800023f6  mov     eax, [rbx+4Ch]
0x1800023f9  add     ecx, eax
0x1800023fb  mov     cs:g_lExpectedClientMessageCount, ecx
0x180002401  lea     rcx, g_SRWInstanceList; SRWLock
0x180002408  call    cs:__imp_ReleaseSRWLockExclusive
0x18000240e  mov     eax, [rbx+68h]
0x180002411  mov     [rsp+58h+arg_10], 0
0x18000241a  test    al, al
0x18000241c  jns     loc_1800024C5
0x180002422  mov     rcx, [rbx+4C0h]; struct _GUID *
0x180002429  test    rcx, rcx
0x18000242c  jnz     short loc_18000243E
0x18000242e  mov     dword ptr [rsp+58h+Args], 4005h
0x180002436  mov     r8d, 5Ah ; 'Z'
0x18000243c  jmp     short loc_1800024AB
0x18000243e  lea     rdx, [rbx+18h]; struct _GUID *
0x180002442  lea     r8, [rsp+58h+arg_10]; __int64 *
0x180002447  call    ?DpspGetInstanceDirectorySize@@YAJPEBU_GUID@@0PEA_J@Z; DpspGetInstanceDirectorySize(_GUID const *,_GUID const *,__int64 *)
0x18000244c  test    eax, eax
0x18000244e  jns     short loc_180002458
0x180002450  mov     r8d, 60h ; '`'
0x180002456  jmp     short loc_1800024A4
0x180002458  mov     rdx, cs:g_DirSizeLimit
0x18000245f  mov     rax, [rsp+58h+arg_10]
0x180002464  lock xadd cs:g_CurrentDirSize, rax
0x18000246d  add     rax, [rsp+58h+arg_10]
0x180002472  cmp     rax, rdx
0x180002475  jl      short loc_1800024C5
0x180002477  mov     rcx, cs:g_hDataRetentionControl; hEvent
0x18000247e  call    cs:__imp_SetEvent
0x180002484  test    eax, eax
0x180002486  jnz     short loc_1800024C5
0x180002488  call    cs:__imp_GetLastError
0x18000248e  test    eax, eax
0x180002490  jle     short loc_18000249C
0x180002492  movzx   eax, ax
0x180002495  or      eax, 80070000h
0x18000249a  test    eax, eax
0x18000249c  jns     short loc_1800024C5
0x18000249e  mov     r8d, 74h ; 't'; int
0x1800024a4  movzx   eax, ax
0x1800024a7  mov     dword ptr [rsp+58h+Args], eax; Args
0x1800024ab  lea     r9, aErrorD; "Error = %d"
0x1800024b2  lea     rdx, aDpspcheckdisku; "DpspCheckDiskUsage"
0x1800024b9  lea     rcx, aClientcoreBase_1; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800024c0  call    WdipTraceError
0x1800024c5  cmp     dword ptr [rbx+84h], 0
0x1800024cc  jge     short loc_1800024F2
0x1800024ce  mov     eax, [rbx+68h]
0x1800024d1  mov     rcx, rbx
0x1800024d4  test    al, 8
0x1800024d6  jz      short loc_1800024E6
0x1800024d8  lea     rdx, WDI_DPS_EVENT_SCENARIO_DM_FAILED
0x1800024df  call    DpspRaiseScenarioDMFailedEvent
0x1800024e4  jmp     short loc_1800024F2
0x1800024e6  lea     rdx, WDI_DPS_EVENT_SCENARIO_DPS_FAILED
0x1800024ed  call    DpspRaiseScenarioDPSFailedEvent
0x1800024f2  lea     rcx, [rsp+58h+arg_18]
0x1800024f7  call    DpspFreeSpecificInstanceInfo
0x1800024fc  mov     rdi, [rsp+58h+var_18]
0x180002501  mov     eax, ebp
0x180002503  add     rsp, 48h
0x180002507  pop     rbp
0x180002508  pop     rbx
0x180002509  retn
```
