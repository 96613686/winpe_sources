# CReader::TransactionTimeoutStop(void)

- ea: `0x18000d9c0`
- end: `0x18000dc94`
- name: `?TransactionTimeoutStop@CReader@@IEAAXXZ`
- size: `724`
- prototype: `void __fastcall(CReader *__hidden this)`
- caller_count: `10`
- callee_count: `7`
- tags: ``

## callers

- `0x180004730`
- `0x180006ad0`
- `0x18000f770`
- `0x18000fc90`
- `0x18000fcf0`
- `0x180018d4c`
- `0x18002a504`
- `0x18002d62c`
- `0x18002dcc4`
- `0x18002e770`

## callees

- `0x1800075d0`
- `0x18000d7a0`
- `0x18000d9c0`
- `0x18000e4b0`
- `0x180028b78`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000daf9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000daf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc77`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000dc77`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dab9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000dab9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000db2c`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000db2c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000da0c`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18000da0c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da1a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000da1a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CReader::TransactionTimeoutStop(CReader *this)
{
  char v2; // di
  struct _TP_TIMER *v3; // rcx
  DWORD CurrentThreadId; // eax
  unsigned __int64 v5; // rdx
  char *v6; // rcx
  DWORD v7; // r9d
  int v8; // r10d
  int v9; // ebx
  __int64 v10; // rbx
  __int64 v11; // rcx
  int v12; // r8d
  unsigned int i; // eax
  bool v14; // zf
  int j; // edi
  __int64 pExceptionObject; // [rsp+48h] [rbp+10h] BYREF

  if ( g_fDisableTransactionTimeoutDelay )
    return;
  v2 = 0;
  CLockWrite::CLockWrite((CLockWrite *)&pExceptionObject, (CReader *)((char *)this + 56));
  v3 = (struct _TP_TIMER *)*((_QWORD *)this + 89);
  if ( v3 && IsThreadpoolTimerSet(v3) )
  {
    CurrentThreadId = GetCurrentThreadId();
    v7 = CurrentThreadId;
    v8 = `WppTraceIndent'::`2'::idxCurrentThread;
    if ( `WppTraceIndent'::`2'::idxCurrentThread == -1 )
    {
      v8 = 0;
      `WppTraceIndent'::`2'::idxCurrentThread = 0;
      LODWORD(`WppTraceIndent'::`2'::ThreadTable) = CurrentThreadId;
      dword_18004BD54 = 0;
    }
    else
    {
      if ( `WppTraceIndent'::`2'::idxCurrentThread == -2
        || *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * `WppTraceIndent'::`2'::idxCurrentThread) != CurrentThreadId )
      {
        v12 = -1;
        for ( i = 0; ; ++i )
        {
          v14 = i == 32;
          if ( i >= 0x20 )
            break;
          v6 = (char *)(int)i;
          v5 = *((unsigned int *)&`WppTraceIndent'::`2'::ThreadTable + 2 * (int)i);
          if ( (_DWORD)v5 == v7 )
          {
            v8 = i;
            `WppTraceIndent'::`2'::idxCurrentThread = i;
            v14 = i == 32;
            break;
          }
          if ( v12 == -1 && !(_DWORD)v5 )
            v12 = i;
        }
        if ( v14 )
        {
          if ( v12 == -1 )
          {
            `WppTraceIndent'::`2'::idxCurrentThread = -2;
            goto LABEL_31;
          }
          v8 = v12;
          `WppTraceIndent'::`2'::idxCurrentThread = v12;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12) = v7;
          *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v12 + 1) = 0;
        }
      }
      if ( v8 < 0 )
      {
LABEL_31:
        v9 = 0;
LABEL_9:
        `WppTraceIndent'::`2'::szIndentPrefix[0] = 0;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          for ( j = 1; j <= v9; ++j )
          {
            if ( (unsigned int)StringCbCatA(v6, v5, "..") )
              break;
          }
        }
        StringCbCatA(v6, v5, " ");
        WPP_pszIndent = `WppTraceIndent'::`2'::szIndentPrefix;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            23,
            WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids,
            `WppTraceIndent'::`2'::szIndentPrefix);
        }
        v2 = 1;
        SetThreadpoolTimer(*((PTP_TIMER *)this + 89), 0, 0, 0);
        goto LABEL_13;
      }
    }
    v9 = *((_DWORD *)&`WppTraceIndent'::`2'::ThreadTable + 2 * v8 + 1);
    goto LABEL_9;
  }
LABEL_13:
  v10 = pExceptionObject;
  if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)pExceptionObject + 16LL))(pExceptionObject) )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v10)(v10, 0, 0);
    v14 = (*(_DWORD *)(v10 + 60))-- == 1;
    if ( v14 )
    {
      *(_QWORD *)(v10 + 104) = 0;
      if ( !SetEvent(*(HANDLE *)(v10 + 88)) )
      {
        LODWORD(pExceptionObject) = GetLastError();
        throw (ulong *)&pExceptionObject;
      }
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 8LL))(v10);
  }
  if ( v2 )
  {
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 89), 1);
  }
  else
  {
    WppTraceIndent(v11, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids, WPP_pszIndent);
    }
  }
}

```

## disassembly

```asm
0x18000d9c0  mov     [rsp+arg_0], rbx
0x18000d9c5  mov     [rsp+arg_10], rbp
0x18000d9ca  push    rsi
0x18000d9cb  push    rdi
0x18000d9cc  push    r14
0x18000d9ce  sub     rsp, 20h
0x18000d9d2  mov     rsi, rcx
0x18000d9d5  cmp     cs:?g_fDisableTransactionTimeoutDelay@@3_NA, 0; bool g_fDisableTransactionTimeoutDelay
0x18000d9dc  jnz     loc_18000DB32
0x18000d9e2  xor     dil, dil
0x18000d9e5  lea     rdx, [rcx+38h]; struct CAccessLock *
0x18000d9e9  lea     rcx, [rsp+38h+pExceptionObject]; this
0x18000d9ee  call    ??0CLockWrite@@QEAA@PEAVCAccessLock@@@Z; CLockWrite::CLockWrite(CAccessLock *)
0x18000d9f3  mov     rcx, [rsi+2C8h]; pti
0x18000d9fa  xor     ebp, ebp
0x18000d9fc  lea     r14, WPP_GLOBAL_Control
0x18000da03  test    rcx, rcx
0x18000da06  jz      loc_18000DAC0
0x18000da0c  call    cs:__imp_IsThreadpoolTimerSet
0x18000da12  test    eax, eax
0x18000da14  jz      loc_18000DAC0
0x18000da1a  call    cs:__imp_GetCurrentThreadId
0x18000da20  mov     r9d, eax
0x18000da23  lea     rbx, ?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000da2a  movsxd  r10, cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000da31  cmp     r10d, 0FFFFFFFFh
0x18000da35  jz      loc_18000DC02
0x18000da3b  cmp     r10d, 0FFFFFFFEh
0x18000da3f  jz      loc_18000DB45
0x18000da45  cmp     [rbx+r10*8], eax
0x18000da49  jnz     loc_18000DB45
0x18000da4f  test    r10d, r10d
0x18000da52  js      loc_18000DB92
0x18000da58  movsxd  rax, r10d
0x18000da5b  mov     ebx, [rbx+rax*8+4]
0x18000da5f  mov     cs:?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA, dil; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000da66  mov     rax, cs:WPP_GLOBAL_Control
0x18000da6d  test    byte ptr [rax+1Ch], 2
0x18000da71  jnz     loc_18000DC1D
0x18000da77  lea     r8, asc_18003BC60; " "
0x18000da7e  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000da83  lea     r9, ?szIndentPrefix@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PADA; char near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::szIndentPrefix
0x18000da8a  mov     cs:?WPP_pszIndent@@3PEADEA, r9; char * WPP_pszIndent
0x18000da91  mov     rcx, cs:WPP_GLOBAL_Control
0x18000da98  cmp     rcx, r14
0x18000da9b  jz      short loc_18000DAA7
0x18000da9d  test    byte ptr [rcx+1Ch], 10h
0x18000daa1  jnz     loc_18000DC53
0x18000daa7  mov     dil, 1
0x18000daaa  xor     r9d, r9d; msWindowLength
0x18000daad  xor     r8d, r8d; msPeriod
0x18000dab0  xor     edx, edx; pftDueTime
0x18000dab2  mov     rcx, [rsi+2C8h]; pti
0x18000dab9  call    cs:__imp_SetThreadpoolTimer
0x18000dabf  nop
0x18000dac0  mov     rbx, [rsp+38h+pExceptionObject]
0x18000dac5  mov     rax, [rbx]
0x18000dac8  mov     rcx, rbx
0x18000dacb  mov     rax, [rax+10h]
0x18000dacf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dad4  test    eax, eax
0x18000dad6  jnz     short loc_18000DB17
0x18000dad8  mov     rax, [rbx]
0x18000dadb  xor     r8d, r8d
0x18000dade  xor     edx, edx
0x18000dae0  mov     rcx, rbx
0x18000dae3  mov     rax, [rax]
0x18000dae6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daeb  add     dword ptr [rbx+3Ch], 0FFFFFFFFh
0x18000daef  jnz     short loc_18000DB07
0x18000daf1  mov     [rbx+68h], rbp
0x18000daf5  mov     rcx, [rbx+58h]; hEvent
0x18000daf9  call    cs:__imp_SetEvent
0x18000daff  test    eax, eax
0x18000db01  jz      loc_18000DC77
0x18000db07  mov     rax, [rbx]
0x18000db0a  mov     rcx, rbx
0x18000db0d  mov     rax, [rax+8]
0x18000db11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db16  nop
0x18000db17  test    dil, dil
0x18000db1a  jz      loc_18000DBB3
0x18000db20  mov     edx, 1; fCancelPendingCallbacks
0x18000db25  mov     rcx, [rsi+2C8h]; pti
0x18000db2c  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000db32  mov     rbx, [rsp+38h+arg_0]
0x18000db37  mov     rbp, [rsp+38h+arg_10]
0x18000db3c  add     rsp, 20h
0x18000db40  pop     r14
0x18000db42  pop     rdi
0x18000db43  pop     rsi
0x18000db44  retn
0x18000db45  mov     r8d, 0FFFFFFFFh
0x18000db4b  mov     eax, ebp
0x18000db4d  nop     dword ptr [rax]
0x18000db50  cmp     eax, 20h ; ' '
0x18000db53  jnb     short loc_18000DB7C
0x18000db55  movsxd  rcx, eax
0x18000db58  mov     edx, [rbx+rcx*8]
0x18000db5b  cmp     edx, r9d
0x18000db5e  jz      short loc_18000DB70
0x18000db60  cmp     r8d, 0FFFFFFFFh
0x18000db64  jnz     short loc_18000DB6C
0x18000db66  test    edx, edx
0x18000db68  cmovz   r8d, eax
0x18000db6c  inc     eax
0x18000db6e  jmp     short loc_18000DB50
0x18000db70  mov     r10d, eax
0x18000db73  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, eax; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000db79  cmp     eax, 20h ; ' '
0x18000db7c  jnz     loc_18000DA4F
0x18000db82  cmp     r8d, 0FFFFFFFFh
0x18000db86  jnz     short loc_18000DB99
0x18000db88  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, 0FFFFFFFEh; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000db92  mov     ebx, ebp
0x18000db94  jmp     loc_18000DA5F
0x18000db99  mov     r10d, r8d
0x18000db9c  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, r8d; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000dba3  movsxd  rax, r8d
0x18000dba6  mov     [rbx+rax*8], r9d
0x18000dbaa  mov     [rbx+rax*8+4], ebp
0x18000dbae  jmp     loc_18000DA4F
0x18000dbb3  mov     edx, 2
0x18000dbb8  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x18000dbbd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000dbc4  cmp     rcx, r14
0x18000dbc7  jz      loc_18000DB32
0x18000dbcd  test    byte ptr [rcx+1Ch], 10h
0x18000dbd1  jz      loc_18000DB32
0x18000dbd7  cmp     byte ptr [rcx+19h], 4
0x18000dbdb  jb      loc_18000DB32
0x18000dbe1  mov     edx, 18h
0x18000dbe6  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x18000dbed  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18000dbf4  mov     rcx, [rcx+10h]
0x18000dbf8  call    WPP_SF_s
0x18000dbfd  jmp     loc_18000DB32
0x18000dc02  mov     r10d, ebp
0x18000dc05  mov     cs:?idxCurrentThread@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4HA, ebp; int `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::idxCurrentThread
0x18000dc0b  mov     cs:?ThreadTable@?1??WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z@4PAU_ThreadEntry@?1??1@YAX01@Z@A, r9d; `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::_ThreadEntry near * `WppTraceIndent(char * *,_WppTraceIndentType)'::`2'::ThreadTable
0x18000dc12  mov     cs:dword_18004BD54, ebp
0x18000dc18  jmp     loc_18000DA58
0x18000dc1d  cmp     byte ptr [rax+19h], 5
0x18000dc21  jb      loc_18000DA77
0x18000dc27  mov     edi, 1
0x18000dc2c  cmp     ebx, edi
0x18000dc2e  jl      loc_18000DA77
0x18000dc34  lea     r8, asc_1800400D4; ".."
0x18000dc3b  call    ?StringCbCatA@@YAJPEAD_KPEBD@Z; StringCbCatA(char *,unsigned __int64,char const *)
0x18000dc40  test    eax, eax
0x18000dc42  jnz     loc_18000DA77
0x18000dc48  inc     edi
0x18000dc4a  cmp     edi, ebx
0x18000dc4c  jle     short loc_18000DC34
0x18000dc4e  jmp     loc_18000DA77
0x18000dc53  cmp     byte ptr [rcx+19h], 4
0x18000dc57  jb      loc_18000DAA7
0x18000dc5d  mov     edx, 17h
0x18000dc62  lea     r8, WPP_ce5521a42e1e3d67b7f20c6956e021f8_Traceguids
0x18000dc69  mov     rcx, [rcx+10h]
0x18000dc6d  call    WPP_SF_s
0x18000dc72  jmp     loc_18000DAA7
0x18000dc77  call    cs:__imp_GetLastError
0x18000dc7d  nop
0x18000dc7e  mov     dword ptr [rsp+38h+pExceptionObject], eax
0x18000dc82  lea     rdx, _TI1K; pThrowInfo
0x18000dc89  lea     rcx, [rsp+38h+pExceptionObject]; pExceptionObject
0x18000dc8e  call    _CxxThrowException_0
```
