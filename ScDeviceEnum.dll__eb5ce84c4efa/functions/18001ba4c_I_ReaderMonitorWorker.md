# I_ReaderMonitorWorker

- ea: `0x18001ba4c`
- end: `0x18001bed9`
- name: `I_ReaderMonitorWorker`
- size: `1165`
- prototype: `__int64 __fastcall(__int64, _DWORD *, unsigned int *)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18001b8c0`

## callees

- `0x180007178`
- `0x1800071d4`
- `0x1800140d0`
- `0x18001714c`
- `0x18001aab0`
- `0x18001ad14`
- `0x18001ae54`
- `0x18001b00c`
- `0x18001b284`
- `0x18001b53c`
- `0x18001ba4c`
- `0x18001c158`
- `0x18001cc6c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be6d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bb93`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd28`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bd55`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001bdf9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001be6d`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bb14`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bc71`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bcd3`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bb14`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bc71`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x18001bcd3`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bc31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bda8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bc31`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001bda8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be29`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bb49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd00`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001bd3a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001be29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbb1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001bbb1`
- `WinSCard!SCardCancel` at `0x18001be18`
- `WinSCard!SCardCancel` at `0x18001be18`
- `WinSCard!SCardEstablishContext` at `0x18001bb63`
- `WinSCard!SCardEstablishContext` at `0x18001bb63`
- `WinSCard!SCardReleaseContext` at `0x18001be59`
- `WinSCard!SCardReleaseContext` at `0x18001be59`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bde8`
- `WinSCard!SCardReleaseStartedEvent` at `0x18001bde8`
- `WinSCard!SCardAccessStartedEvent` at `0x18001badc`
- `WinSCard!SCardAccessStartedEvent` at `0x18001badc`

## pseudocode

```c
__int64 __fastcall I_ReaderMonitorWorker(__int64 a1, _DWORD *a2, unsigned int *a3)
{
  int v3; // r15d
  unsigned int updated; // ebx
  int v8; // esi
  DWORD v9; // eax
  int v10; // r14d
  __int64 v11; // rcx
  int v12; // r12d
  DWORD v13; // eax
  DWORD v14; // eax
  int v15; // eax
  struct _RTL_CRITICAL_SECTION *v16; // r14
  _QWORD *v17; // rcx
  SCARDCONTEXT v18; // rcx
  LPVOID v19; // rcx
  int v21; // [rsp+30h] [rbp-28h] BYREF
  LPVOID lpMem; // [rsp+38h] [rbp-20h] BYREF
  HANDLE Handles[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v24; // [rsp+A0h] [rbp+48h] BYREF
  _DWORD *v25; // [rsp+A8h] [rbp+50h]
  unsigned int *v26; // [rsp+B0h] [rbp+58h]
  __int64 v27; // [rsp+B8h] [rbp+60h] BYREF

  v26 = a3;
  v25 = a2;
  v3 = 0;
  v24 = 0;
  lpMem = 0;
  LODWORD(v27) = 0;
  *(_OWORD *)Handles = 0;
  WppTraceIndent(a1, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 231, &WPP_173052b9a503333cb537dada0074ae31_Traceguids, WPP_pszIndent);
  }
  if ( !a2 || !a3 )
  {
    updated = 87;
    goto LABEL_57;
  }
  Handles[0] = SCardAccessStartedEvent();
  if ( !Handles[0] )
  {
    updated = -2146435041;
LABEL_57:
    v16 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
    goto LABEL_58;
  }
  v8 = 0;
  Handles[1] = *(HANDLE *)(a1 + 240);
  v9 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
  updated = v9;
  if ( v9 )
  {
    if ( v9 == 1 )
    {
LABEL_11:
      updated = 0;
LABEL_12:
      *v25 = 0;
      *v26 = updated;
      updated = 0;
LABEL_47:
      v8 = 0;
    }
  }
  else
  {
    EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
    v8 = 1;
    updated = SCardEstablishContext(*(_DWORD *)(a1 + 40), 0, 0, (LPSCARDCONTEXT)(a1 + 232));
    if ( updated )
      goto LABEL_53;
    updated = I_UpdateReaderStateArray(a1, &lpMem, &v24);
    if ( updated )
    {
      v3 = v24;
    }
    else
    {
      v10 = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
      v3 = v24;
      v8 = 0;
      if ( v24 > 1 )
      {
        if ( !(unsigned int)I_ReaderMonitorSetReaderActionEvent(a1) )
        {
LABEL_17:
          updated = GetLastError();
          goto LABEL_53;
        }
        v10 = 1;
      }
      updated = I_ReaderMonitorInitializeLocalWorkerState(a1);
      if ( !updated )
      {
        v12 = 0;
        while ( WaitForSingleObject(*(HANDLE *)(a1 + 240), 0) == 258 )
        {
          if ( v10 )
          {
            Handles[0] = *(HANDLE *)(a1 + 96);
            Handles[1] = *(HANDLE *)(a1 + 240);
            v13 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
            updated = v13;
            if ( v13 )
            {
              if ( v13 == 1 )
                goto LABEL_11;
              goto LABEL_47;
            }
            v10 = 0;
          }
          if ( !v12 )
          {
            updated = I_ReaderMonitorAsyncGetStatusChange(a1, (__int64)lpMem, v3);
            if ( updated )
              goto LABEL_47;
            v12 = 1;
          }
          Handles[0] = *(HANDLE *)(a1 + 352);
          Handles[1] = *(HANDLE *)(a1 + 360);
          v14 = WaitForMultipleObjectsEx(2u, Handles, 0, 0xFFFFFFFF, 0);
          updated = v14;
          if ( v14 )
          {
            if ( v14 != 1 )
              goto LABEL_47;
            updated = *(_DWORD *)(a1 + 380);
            if ( updated )
            {
              if ( updated == -2146435070 )
                goto LABEL_12;
              goto LABEL_47;
            }
            v12 = 0;
            v21 = 0;
            EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
            updated = I_ReaderMonitorHandleStatusChangeEvent(a1, (__int64 *)&lpMem, &v24, &v21, (int *)&v27);
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
            v15 = v21;
            v3 = v24;
          }
          else
          {
            EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
            I_ReaderMonitorHandleProcessingCompletedEvent(a1, (int *)&v27);
            updated = *(_DWORD *)(a1 + 376);
            LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
            v15 = 1;
          }
          v8 = 0;
          if ( v15
            && (*(_DWORD *)(a1 + 28) == 1
             || *(_DWORD *)(a1 + 28) == 2 && !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 384), 0, 0)) )
          {
            if ( !(unsigned int)I_ReaderMonitorSetReaderActionEvent(a1) )
              goto LABEL_17;
            v10 = 1;
          }
          if ( (_DWORD)v27 )
          {
            if ( updated == 8 )
              goto LABEL_12;
            goto LABEL_53;
          }
          if ( WaitForSingleObject(*(HANDLE *)(a1 + 240), 0) != 258 )
            goto LABEL_12;
        }
        goto LABEL_11;
      }
      WppTraceIndent(v11, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          232,
          (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
          WPP_pszIndent,
          updated);
      }
    }
  }
LABEL_53:
  SCardReleaseStartedEvent();
  v16 = (struct _RTL_CRITICAL_SECTION *)(a1 + 48);
  if ( v8 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
LABEL_58:
  SCardCancel(*(_QWORD *)(a1 + 232));
  I_ReaderMonitorCleanupLocalWorkerState(a1);
  EnterCriticalSection(v16);
  v17 = *(_QWORD **)(a1 + 112);
  if ( v17 )
  {
    I_ReaderListFree(v17);
    *(_QWORD *)(a1 + 112) = 0;
    I_ReaderMonitorSetReaderActionEvent(a1);
  }
  v18 = *(_QWORD *)(a1 + 232);
  if ( v18 )
  {
    SCardReleaseContext(v18);
    *(_QWORD *)(a1 + 232) = 0;
  }
  LeaveCriticalSection(v16);
  v19 = lpMem;
  if ( lpMem )
    I_FreeReaderStates(lpMem, v3);
  WppTraceIndent(v19, 1);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      233,
      (unsigned int)&WPP_173052b9a503333cb537dada0074ae31_Traceguids,
      WPP_pszIndent,
      updated);
  }
  return updated;
}

```

## disassembly

```asm
0x18001ba4c  mov     [rsp-40h+arg_10], r8
0x18001ba51  mov     [rsp-40h+arg_8], rdx
0x18001ba56  push    rbp
0x18001ba57  push    rbx
0x18001ba58  push    rsi
0x18001ba59  push    rdi
0x18001ba5a  push    r12
0x18001ba5c  push    r13
0x18001ba5e  push    r14
0x18001ba60  push    r15
0x18001ba62  mov     rbp, rsp
0x18001ba65  sub     rsp, 58h
0x18001ba69  xor     r15d, r15d
0x18001ba6c  mov     rsi, rdx
0x18001ba6f  xorps   xmm0, xmm0
0x18001ba72  mov     [rbp+arg_0], r15d
0x18001ba76  xor     edx, edx
0x18001ba78  mov     [rbp+lpMem], r15
0x18001ba7c  mov     dword ptr [rbp+arg_18], r15d
0x18001ba80  mov     rbx, r8
0x18001ba83  movups  xmmword ptr [rbp+Handles], xmm0
0x18001ba87  mov     rdi, rcx
0x18001ba8a  call    WppTraceIndent
0x18001ba8f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ba96  lea     r12, WPP_GLOBAL_Control
0x18001ba9d  cmp     rcx, r12
0x18001baa0  jz      short loc_18001BACA
0x18001baa2  test    byte ptr [rcx+1Ch], 2
0x18001baa6  jz      short loc_18001BACA
0x18001baa8  cmp     byte ptr [rcx+19h], 5
0x18001baac  jb      short loc_18001BACA
0x18001baae  mov     r9, cs:WPP_pszIndent
0x18001bab5  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001babc  mov     rcx, [rcx+10h]
0x18001bac0  mov     edx, 0E7h
0x18001bac5  call    WPP_SF_s
0x18001baca  test    rsi, rsi
0x18001bacd  jz      loc_18001BE08
0x18001bad3  test    rbx, rbx
0x18001bad6  jz      loc_18001BE08
0x18001badc  call    cs:__imp_SCardAccessStartedEvent
0x18001bae2  mov     [rbp+Handles], rax
0x18001bae6  test    rax, rax
0x18001bae9  jnz     short loc_18001BAF5
0x18001baeb  mov     ebx, 8010001Fh
0x18001baf0  jmp     loc_18001BE0D
0x18001baf5  mov     rax, [rdi+0F0h]
0x18001bafc  lea     rdx, [rbp+Handles]; lpHandles
0x18001bb00  xor     esi, esi
0x18001bb02  mov     [rbp+Handles+8], rax
0x18001bb06  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001bb0a  mov     [rsp+58h+bAlertable], esi; bAlertable
0x18001bb0e  xor     r8d, r8d; bWaitAll
0x18001bb11  lea     ecx, [rsi+2]; nCount
0x18001bb14  call    cs:__imp_WaitForMultipleObjectsEx
0x18001bb1a  mov     ebx, eax
0x18001bb1c  test    eax, eax
0x18001bb1e  jz      short loc_18001BB42
0x18001bb20  cmp     eax, 1
0x18001bb23  jnz     loc_18001BDE8
0x18001bb29  xor     ebx, ebx
0x18001bb2b  mov     rax, [rbp+arg_8]
0x18001bb2f  mov     dword ptr [rax], 0
0x18001bb35  mov     rax, [rbp+arg_10]
0x18001bb39  mov     [rax], ebx
0x18001bb3b  xor     ebx, ebx
0x18001bb3d  jmp     loc_18001BDC7
0x18001bb42  lea     r13, [rdi+30h]
0x18001bb46  mov     rcx, r13; lpCriticalSection
0x18001bb49  call    cs:__imp_EnterCriticalSection
0x18001bb4f  mov     ecx, [rdi+28h]; dwScope
0x18001bb52  lea     r9, [rdi+0E8h]; phContext
0x18001bb59  xor     r8d, r8d; pvReserved2
0x18001bb5c  xor     edx, edx; pvReserved1
0x18001bb5e  mov     esi, 1
0x18001bb63  call    cs:__imp_SCardEstablishContext
0x18001bb69  mov     ebx, eax
0x18001bb6b  test    eax, eax
0x18001bb6d  jnz     loc_18001BDE8
0x18001bb73  lea     r8, [rbp+arg_0]
0x18001bb77  mov     rcx, rdi
0x18001bb7a  lea     rdx, [rbp+lpMem]
0x18001bb7e  call    I_UpdateReaderStateArray
0x18001bb83  mov     ebx, eax
0x18001bb85  test    eax, eax
0x18001bb87  jnz     loc_18001BDE4
0x18001bb8d  mov     rcx, r13; lpCriticalSection
0x18001bb90  xor     r14d, r14d
0x18001bb93  call    cs:__imp_LeaveCriticalSection
0x18001bb99  mov     r15d, [rbp+arg_0]
0x18001bb9d  xor     esi, esi
0x18001bb9f  cmp     r15d, 1
0x18001bba3  jbe     short loc_18001BBC4
0x18001bba5  mov     rcx, rdi
0x18001bba8  call    I_ReaderMonitorSetReaderActionEvent
0x18001bbad  test    eax, eax
0x18001bbaf  jnz     short loc_18001BBBE
0x18001bbb1  call    cs:__imp_GetLastError
0x18001bbb7  mov     ebx, eax
0x18001bbb9  jmp     loc_18001BDE8
0x18001bbbe  mov     r14d, 1
0x18001bbc4  mov     rcx, rdi
0x18001bbc7  call    I_ReaderMonitorInitializeLocalWorkerState
0x18001bbcc  mov     ebx, eax
0x18001bbce  test    eax, eax
0x18001bbd0  jz      short loc_18001BC25
0x18001bbd2  mov     edx, 2
0x18001bbd7  call    WppTraceIndent
0x18001bbdc  mov     rcx, cs:WPP_GLOBAL_Control
0x18001bbe3  cmp     rcx, r12
0x18001bbe6  jz      loc_18001BDE8
0x18001bbec  test    byte ptr [rcx+1Ch], 1
0x18001bbf0  jz      loc_18001BDE8
0x18001bbf6  cmp     byte ptr [rcx+19h], 3
0x18001bbfa  jb      loc_18001BDE8
0x18001bc00  mov     r9, cs:WPP_pszIndent
0x18001bc07  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001bc0e  mov     rcx, [rcx+10h]
0x18001bc12  mov     edx, 0E8h
0x18001bc17  mov     [rsp+58h+bAlertable], ebx
0x18001bc1b  call    WPP_SF_sd
0x18001bc20  jmp     loc_18001BDE8
0x18001bc25  xor     r12d, r12d
0x18001bc28  mov     rcx, [rdi+0F0h]; hHandle
0x18001bc2f  xor     edx, edx; dwMilliseconds
0x18001bc31  call    cs:__imp_WaitForSingleObject
0x18001bc37  cmp     eax, 102h
0x18001bc3c  jnz     loc_18001BB29
0x18001bc42  test    r14d, r14d
0x18001bc45  jz      short loc_18001BC84
0x18001bc47  mov     rax, [rdi+60h]
0x18001bc4b  lea     rdx, [rbp+Handles]; lpHandles
0x18001bc4f  xor     r8d, r8d; bWaitAll
0x18001bc52  mov     [rbp+Handles], rax
0x18001bc56  mov     rax, [rdi+0F0h]
0x18001bc5d  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001bc61  mov     [rbp+Handles+8], rax
0x18001bc65  mov     [rsp+58h+bAlertable], 0; bAlertable
0x18001bc6d  lea     ecx, [r8+2]; nCount
0x18001bc71  call    cs:__imp_WaitForMultipleObjectsEx
0x18001bc77  mov     ebx, eax
0x18001bc79  test    eax, eax
0x18001bc7b  jnz     loc_18001BDBE
0x18001bc81  xor     r14d, r14d
0x18001bc84  test    r12d, r12d
0x18001bc87  jnz     short loc_18001BCA6
0x18001bc89  mov     rdx, [rbp+lpMem]
0x18001bc8d  mov     r8d, r15d
0x18001bc90  mov     rcx, rdi
0x18001bc93  call    I_ReaderMonitorAsyncGetStatusChange
0x18001bc98  mov     ebx, eax
0x18001bc9a  test    eax, eax
0x18001bc9c  jnz     loc_18001BDC7
0x18001bca2  lea     r12d, [rax+1]
0x18001bca6  mov     rax, [rdi+160h]
0x18001bcad  lea     rdx, [rbp+Handles]; lpHandles
0x18001bcb1  xor     r8d, r8d; bWaitAll
0x18001bcb4  mov     [rbp+Handles], rax
0x18001bcb8  mov     rax, [rdi+168h]
0x18001bcbf  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18001bcc3  mov     [rbp+Handles+8], rax
0x18001bcc7  mov     [rsp+58h+bAlertable], 0; bAlertable
0x18001bccf  lea     ecx, [r8+2]; nCount
0x18001bcd3  call    cs:__imp_WaitForMultipleObjectsEx
0x18001bcd9  mov     ebx, eax
0x18001bcdb  test    eax, eax
0x18001bcdd  jz      short loc_18001BD37
0x18001bcdf  cmp     eax, 1
0x18001bce2  jnz     loc_18001BDC7
0x18001bce8  mov     ebx, [rdi+17Ch]
0x18001bcee  test    ebx, ebx
0x18001bcf0  jnz     loc_18001BDCB
0x18001bcf6  xor     r12d, r12d
0x18001bcf9  mov     rcx, r13; lpCriticalSection
0x18001bcfc  mov     [rbp+var_28], r12d
0x18001bd00  call    cs:__imp_EnterCriticalSection
0x18001bd06  lea     rax, [rbp+arg_18]
0x18001bd0a  mov     rcx, rdi; int
0x18001bd0d  lea     r9, [rbp+var_28]
0x18001bd11  mov     qword ptr [rsp+58h+bAlertable], rax; __int64
0x18001bd16  lea     r8, [rbp+arg_0]
0x18001bd1a  lea     rdx, [rbp+lpMem]
0x18001bd1e  call    I_ReaderMonitorHandleStatusChangeEvent
0x18001bd23  mov     rcx, r13; lpCriticalSection
0x18001bd26  mov     ebx, eax
0x18001bd28  call    cs:__imp_LeaveCriticalSection
0x18001bd2e  mov     eax, [rbp+var_28]
0x18001bd31  mov     r15d, [rbp+arg_0]
0x18001bd35  jmp     short loc_18001BD60
0x18001bd37  mov     rcx, r13; lpCriticalSection
0x18001bd3a  call    cs:__imp_EnterCriticalSection
0x18001bd40  lea     rdx, [rbp+arg_18]
0x18001bd44  mov     rcx, rdi
0x18001bd47  call    I_ReaderMonitorHandleProcessingCompletedEvent
0x18001bd4c  mov     ebx, [rdi+178h]
0x18001bd52  mov     rcx, r13; lpCriticalSection
0x18001bd55  call    cs:__imp_LeaveCriticalSection
0x18001bd5b  mov     eax, 1
0x18001bd60  xor     esi, esi
0x18001bd62  test    eax, eax
0x18001bd64  jz      short loc_18001BD97
0x18001bd66  mov     ecx, [rdi+1Ch]
0x18001bd69  sub     ecx, 1
0x18001bd6c  jz      short loc_18001BD81
0x18001bd6e  cmp     ecx, 1
0x18001bd71  jnz     short loc_18001BD97
0x18001bd73  xor     ecx, ecx
0x18001bd75  xor     eax, eax
0x18001bd77  lock cmpxchg [rdi+180h], ecx
0x18001bd7f  jnz     short loc_18001BD97
0x18001bd81  mov     rcx, rdi
0x18001bd84  call    I_ReaderMonitorSetReaderActionEvent
0x18001bd89  test    eax, eax
0x18001bd8b  jz      loc_18001BBB1
0x18001bd91  mov     r14d, 1
0x18001bd97  cmp     dword ptr [rbp+arg_18], 0
0x18001bd9b  mov     eax, ebx
0x18001bd9d  jnz     short loc_18001BDD9
0x18001bd9f  mov     rcx, [rdi+0F0h]; hHandle
0x18001bda6  xor     edx, edx; dwMilliseconds
0x18001bda8  call    cs:__imp_WaitForSingleObject
0x18001bdae  cmp     eax, 102h
0x18001bdb3  jz      loc_18001BC28
0x18001bdb9  jmp     loc_18001BB2B
0x18001bdbe  cmp     eax, 1
0x18001bdc1  jz      loc_18001BB29
0x18001bdc7  xor     esi, esi
0x18001bdc9  jmp     short loc_18001BDE8
0x18001bdcb  cmp     ebx, 80100002h
0x18001bdd1  jz      loc_18001BB2B
0x18001bdd7  jmp     short loc_18001BDC7
0x18001bdd9  cmp     eax, 8
0x18001bddc  jz      loc_18001BB2B
0x18001bde2  jmp     short loc_18001BDE8
0x18001bde4  mov     r15d, [rbp+arg_0]
0x18001bde8  call    cs:__imp_SCardReleaseStartedEvent
0x18001bdee  lea     r14, [rdi+30h]
0x18001bdf2  test    esi, esi
0x18001bdf4  jz      short loc_18001BDFF
0x18001bdf6  mov     rcx, r14; lpCriticalSection
0x18001bdf9  call    cs:__imp_LeaveCriticalSection
0x18001bdff  lea     r12, WPP_GLOBAL_Control
0x18001be06  jmp     short loc_18001BE11
0x18001be08  mov     ebx, 57h ; 'W'
0x18001be0d  lea     r14, [rdi+30h]
0x18001be11  mov     rcx, [rdi+0E8h]; hContext
0x18001be18  call    cs:__imp_SCardCancel
0x18001be1e  mov     rcx, rdi
0x18001be21  call    I_ReaderMonitorCleanupLocalWorkerState
0x18001be26  mov     rcx, r14; lpCriticalSection
0x18001be29  call    cs:__imp_EnterCriticalSection
0x18001be2f  mov     rcx, [rdi+70h]
0x18001be33  test    rcx, rcx
0x18001be36  jz      short loc_18001BE4D
0x18001be38  call    I_ReaderListFree
0x18001be3d  mov     rcx, rdi
0x18001be40  mov     qword ptr [rdi+70h], 0
0x18001be48  call    I_ReaderMonitorSetReaderActionEvent
0x18001be4d  mov     rcx, [rdi+0E8h]; hContext
0x18001be54  test    rcx, rcx
0x18001be57  jz      short loc_18001BE6A
0x18001be59  call    cs:__imp_SCardReleaseContext
0x18001be5f  mov     qword ptr [rdi+0E8h], 0
0x18001be6a  mov     rcx, r14; lpCriticalSection
0x18001be6d  call    cs:__imp_LeaveCriticalSection
0x18001be73  mov     rcx, [rbp+lpMem]; lpMem
0x18001be77  test    rcx, rcx
0x18001be7a  jz      short loc_18001BE84
0x18001be7c  mov     edx, r15d
0x18001be7f  call    I_FreeReaderStates
0x18001be84  mov     edx, 1
0x18001be89  call    WppTraceIndent
0x18001be8e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001be95  cmp     rcx, r12
0x18001be98  jz      short loc_18001BEC6
0x18001be9a  test    byte ptr [rcx+1Ch], 2
0x18001be9e  jz      short loc_18001BEC6
0x18001bea0  cmp     byte ptr [rcx+19h], 5
0x18001bea4  jb      short loc_18001BEC6
0x18001bea6  mov     r9, cs:WPP_pszIndent
0x18001bead  lea     r8, WPP_173052b9a503333cb537dada0074ae31_Traceguids
0x18001beb4  mov     rcx, [rcx+10h]
0x18001beb8  mov     edx, 0E9h
0x18001bebd  mov     [rsp+58h+bAlertable], ebx
0x18001bec1  call    WPP_SF_sd
0x18001bec6  mov     eax, ebx
0x18001bec8  add     rsp, 58h
0x18001becc  pop     r15
0x18001bece  pop     r14
0x18001bed0  pop     r13
0x18001bed2  pop     r12
0x18001bed4  pop     rdi
0x18001bed5  pop     rsi
0x18001bed6  pop     rbx
0x18001bed7  pop     rbp
0x18001bed8  retn
```
