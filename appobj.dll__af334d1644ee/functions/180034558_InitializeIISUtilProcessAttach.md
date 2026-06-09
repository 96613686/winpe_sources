# InitializeIISUtilProcessAttach

- ea: `0x180034558`
- end: `0x180034665`
- name: `InitializeIISUtilProcessAttach`
- size: `269`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800133cc`

## callees

- `0x18002f1c0`
- `0x18003236c`
- `0x18003366c`
- `0x180034218`
- `0x1800344ac`
- `0x180034558`
- `0x18003466c`
- `0x1800349cc`
- `0x180034ae0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345e8`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345c4`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x1800345e8`

## string_xrefs

- `0x180034595`: `servercommon\inetsrv\iis\iisrearc\core\common\util\init_iisutil.cxx`

## pseudocode

```c
__int64 __fastcall InitializeIISUtilProcessAttach(__int64 a1, DWORD a2)
{
  char v3; // [rsp+28h] [rbp-10h]

  g_dwDebugFlagsIISUtil = PuLoadDebugFlagsFromRegStr(a1, a2);
  if ( (g_dwDebugFlagsIISUtil & 3) != 0 && (g_dwDebugFlagsIISUtil & 4) != 0 )
    PuDbgPrint(
      (struct _DEBUG_PRINTS *)g_pDebug,
      "servercommon\\inetsrv\\iis\\iisrearc\\core\\common\\util\\init_iisutil.cxx",
      0x92u,
      "InitializeIISUtilProcessAttach",
      "InitializeIISUtilProcessAttach\n",
      v3);
  if ( (unsigned int)Locks_Initialize()
    && (dword_18006000C = 2, InitializeCriticalSectionAndSpinCount(&CriticalSection, 0x80000000))
    && (dword_18006000C = 3, InitializeCriticalSectionAndSpinCount(&g_csTimerWrap, 0x800003E8))
    && (g_fInitCsTimerWrap = 1, dword_18006000C = 5, (unsigned int)ALLOC_CACHE_HANDLER::Initialize())
    && (dword_18006000C = 6, (unsigned __int8)LKRHashTableInit())
    && (dword_18006000C = 7, (int)BIG_REF_TRACE::InitializeStatic() >= 0)
    && (dword_18006000C = 8, (int)EVENT_LOG::Initialize() >= 0) )
  {
    dword_18006000C = 9;
    return 1;
  }
  else
  {
    TerminateIISUtilProcessDetach();
    return 0;
  }
}

```

## disassembly

```asm
0x180034558  sub     rsp, 38h
0x18003455c  call    PuLoadDebugFlagsFromRegStr
0x180034561  test    al, 3
0x180034563  mov     cs:g_dwDebugFlagsIISUtil, eax
0x180034569  setnz   cl
0x18003456c  test    al, 4
0x18003456e  setnz   al
0x180034571  test    al, cl
0x180034573  jz      short loc_1800345A1
0x180034575  mov     rcx, cs:g_pDebug; struct _DEBUG_PRINTS *
0x18003457c  lea     rax, aInitializeiisu_0; "InitializeIISUtilProcessAttach\n"
0x180034583  lea     r9, aInitializeiisu; "InitializeIISUtilProcessAttach"
0x18003458a  mov     [rsp+38h+var_18], rax; char *
0x18003458f  mov     r8d, 92h; unsigned int
0x180034595  lea     rdx, aServercommonIn; "servercommon\\inetsrv\\iis\\iisrearc\\c"...
0x18003459c  call    PuDbgPrint
0x1800345a1  call    Locks_Initialize
0x1800345a6  test    eax, eax
0x1800345a8  jz      loc_180034659
0x1800345ae  mov     edx, 80000000h; dwSpinCount
0x1800345b3  mov     cs:dword_18006000C, 2
0x1800345bd  lea     rcx, CriticalSection; lpCriticalSection
0x1800345c4  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800345ca  test    eax, eax
0x1800345cc  jz      loc_180034659
0x1800345d2  mov     edx, 800003E8h; dwSpinCount
0x1800345d7  mov     cs:dword_18006000C, 3
0x1800345e1  lea     rcx, ?g_csTimerWrap@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x1800345e8  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x1800345ee  test    eax, eax
0x1800345f0  jz      short loc_180034659
0x1800345f2  mov     cs:?g_fInitCsTimerWrap@@3HA, 1; int g_fInitCsTimerWrap
0x1800345fc  mov     cs:dword_18006000C, 5
0x180034606  call    ?Initialize@ALLOC_CACHE_HANDLER@@SAHXZ; ALLOC_CACHE_HANDLER::Initialize(void)
0x18003460b  test    eax, eax
0x18003460d  jz      short loc_180034659
0x18003460f  mov     cs:dword_18006000C, 6
0x180034619  call    LKRHashTableInit
0x18003461e  test    al, al
0x180034620  jz      short loc_180034659
0x180034622  mov     cs:dword_18006000C, 7
0x18003462c  call    ?InitializeStatic@BIG_REF_TRACE@@SAJXZ; BIG_REF_TRACE::InitializeStatic(void)
0x180034631  test    eax, eax
0x180034633  js      short loc_180034659
0x180034635  mov     cs:dword_18006000C, 8
0x18003463f  call    ?Initialize@EVENT_LOG@@SAJXZ; EVENT_LOG::Initialize(void)
0x180034644  test    eax, eax
0x180034646  js      short loc_180034659
0x180034648  mov     cs:dword_18006000C, 9
0x180034652  mov     eax, 1
0x180034657  jmp     short loc_180034660
0x180034659  call    TerminateIISUtilProcessDetach
0x18003465e  xor     eax, eax
0x180034660  add     rsp, 38h
0x180034664  retn
```
