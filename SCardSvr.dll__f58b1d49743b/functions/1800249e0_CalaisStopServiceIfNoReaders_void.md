# CalaisStopServiceIfNoReaders(void)

- ea: `0x1800249e0`
- end: `0x180024ab0`
- name: `?CalaisStopServiceIfNoReaders@@YAXXZ`
- size: `208`
- prototype: `void __fastcall(__int64, __int64, const unsigned __int8 *, const unsigned __int8 *)`
- caller_count: `2`
- callee_count: `7`
- tags: `service_task`

## callers

- `0x180010f50`
- `0x18002a970`

## callees

- `0x1800075d0`
- `0x180012380`
- `0x1800123a0`
- `0x1800140f0`
- `0x1800249e0`
- `0x180028b78`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeAllConditionVariable` at `0x180024aa9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024a8d`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180024a8d`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024a08`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180024a08`

## pseudocode

```c
void __fastcall CalaisStopServiceIfNoReaders(
        __int64 a1,
        __int64 a2,
        const unsigned __int8 *a3,
        const unsigned __int8 *a4)
{
  __int64 v4; // rcx
  char v5; // [rsp+30h] [rbp+8h] BYREF

  COwnCriticalSection::COwnCriticalSection((COwnCriticalSection *)&v5, qword_18004BA68, a3, a4);
  while ( g_hCalaisShutdown && WaitForSingleObject(g_hCalaisShutdown, 0) == 258 )
  {
    if ( !l_dwReaderActionsInProgress )
    {
      if ( !(unsigned int)CalaisCountReaders() )
      {
        WppTraceIndent(v4, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            12,
            &WPP_8a7e721a78d23c9895a250a251c6a58b_Traceguids,
            WPP_pszIndent);
        }
        SetEvent(hEvent);
      }
      break;
    }
    (*(void (__fastcall **)(struct CCriticalSectionObject *, RTL_CONDITION_VARIABLE *))(*(_QWORD *)qword_18004BA68 + 24LL))(
      qword_18004BA68,
      &l_cvReaderAsyncActionFinished);
  }
  COwnCriticalSection::~COwnCriticalSection((COwnCriticalSection *)&v5);
  WakeAllConditionVariable(&l_cvReaderAsyncActionFinished);
}

```

## disassembly

```asm
0x1800249e0  sub     rsp, 28h
0x1800249e4  mov     rdx, cs:qword_18004BA68; struct CCriticalSectionObject *
0x1800249eb  lea     rcx, [rsp+28h+arg_0]; this
0x1800249f0  call    ??0COwnCriticalSection@@QEAA@PEAVCCriticalSectionObject@@PEBE1@Z; COwnCriticalSection::COwnCriticalSection(CCriticalSectionObject *,uchar const *,uchar const *)
0x1800249f5  nop
0x1800249f6  mov     rcx, cs:?g_hCalaisShutdown@@3PEAXEA; hHandle
0x1800249fd  test    rcx, rcx
0x180024a00  jz      loc_180024A94
0x180024a06  xor     edx, edx; dwMilliseconds
0x180024a08  call    cs:__imp_WaitForSingleObject
0x180024a0e  cmp     eax, 102h
0x180024a13  jnz     short loc_180024A94
0x180024a15  cmp     cs:?l_dwReaderActionsInProgress@@3KA, 0; ulong l_dwReaderActionsInProgress
0x180024a1c  jbe     short loc_180024A3A
0x180024a1e  mov     rcx, cs:qword_18004BA68
0x180024a25  mov     rax, [rcx]
0x180024a28  lea     rdx, ?l_cvReaderAsyncActionFinished@@3U_RTL_CONDITION_VARIABLE@@A; _RTL_CONDITION_VARIABLE l_cvReaderAsyncActionFinished
0x180024a2f  mov     rax, [rax+18h]
0x180024a33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a38  jmp     short loc_1800249F6
0x180024a3a  call    ?CalaisCountReaders@@YAKXZ; CalaisCountReaders(void)
0x180024a3f  test    eax, eax
0x180024a41  jnz     short loc_180024A94
0x180024a43  lea     edx, [rax+2]
0x180024a46  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180024a4b  lea     rax, WPP_GLOBAL_Control
0x180024a52  mov     rcx, cs:WPP_GLOBAL_Control
0x180024a59  cmp     rcx, rax
0x180024a5c  jz      short loc_180024A86
0x180024a5e  test    byte ptr [rcx+1Ch], 1
0x180024a62  jz      short loc_180024A86
0x180024a64  cmp     byte ptr [rcx+19h], 4
0x180024a68  jb      short loc_180024A86
0x180024a6a  mov     edx, 0Ch
0x180024a6f  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180024a76  lea     r8, WPP_8a7e721a78d23c9895a250a251c6a58b_Traceguids
0x180024a7d  mov     rcx, [rcx+10h]
0x180024a81  call    WPP_SF_s
0x180024a86  mov     rcx, cs:hEvent; hEvent
0x180024a8d  call    cs:__imp_SetEvent
0x180024a93  nop
0x180024a94  lea     rcx, [rsp+28h+arg_0]; this
0x180024a99  call    ??1COwnCriticalSection@@QEAA@XZ; COwnCriticalSection::~COwnCriticalSection(void)
0x180024a9e  lea     rcx, ?l_cvReaderAsyncActionFinished@@3U_RTL_CONDITION_VARIABLE@@A; _RTL_CONDITION_VARIABLE l_cvReaderAsyncActionFinished
0x180024aa5  add     rsp, 28h
0x180024aa9  jmp     cs:__imp_WakeAllConditionVariable
```
