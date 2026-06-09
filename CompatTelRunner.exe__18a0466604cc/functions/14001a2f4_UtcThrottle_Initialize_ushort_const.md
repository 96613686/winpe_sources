# UtcThrottle::Initialize(ushort const *)

- ea: `0x14001a2f4`
- end: `0x14001a690`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `924`
- prototype: `__int64 __fastcall(UtcThrottle *this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140019dbc`

## callees

- `0x140001ba0`
- `0x1400026c0`
- `0x1400151b0`
- `0x14001a2f4`
- `0x14001a698`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x14001a62b`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x14001a62b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a66a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14001a66a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a37d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14001a37d`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x14001a586`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x14001a586`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a481`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x14001a481`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a5f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a4df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a56a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a598`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001a5f1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a63c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14001a63c`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14001a554`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14001a5df`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14001a554`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x14001a5df`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14001a4cd`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14001a510`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14001a4cd`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x14001a510`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a65c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14001a65c`

## string_xrefs

- `0x14001a448`: `Failed to initialize security descriptor [%d]`
- `0x14001a49b`: `Failed to create event [%d]`
- `0x14001a4e9`: `Failed to create named semaphore [%d]`
- `0x14001a52a`: `Failed to create semaphore [%d]`
- `0x14001a5b0`: `Failed to create named timer [%d]`
- `0x14001a59e`: `Failed to open named timer [%d]`
- `0x14001a5f9`: `Failed to create timer [%d]`

## pseudocode

```c
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  __int64 v2; // r9
  __int64 v3; // rcx
  const wchar_t *v4; // r10
  __int64 v5; // rdx
  __int64 v6; // r8
  WCHAR *v7; // rax
  wchar_t v8; // r11
  WCHAR *v9; // rcx
  unsigned int v10; // ebx
  const wchar_t *v11; // rcx
  WCHAR *v12; // rax
  wchar_t v13; // r8
  UtcThrottle *v14; // rcx
  DWORD LastError; // eax
  const char *v16; // r9
  __int64 v17; // r8
  DWORD v18; // eax
  HANDLE v19; // rax
  DWORD v20; // eax
  __int64 v21; // r8
  const char *v22; // r9
  __int64 v23; // rcx
  LPVOID lpArgToCompletionRoutine; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  LARGE_INTEGER DueTime; // [rsp+38h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+40h] [rbp-C0h] BYREF
  _SECURITY_DESCRIPTOR v29; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR TimerName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  memset(&v29, 0, sizeof(v29));
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v29;
  EnterCriticalSection(&stru_1400C8DC8);
  DueTime.QuadPart = (LONGLONG)&stru_1400C8DC8;
  if ( byte_1400C8DF0 )
    goto LABEL_40;
  v2 = 2147483646;
  v3 = 2147483646;
  v4 = L"Global\\AmiUtcThrottlingSemaphore";
  v5 = 260;
  v6 = 260;
  v7 = Name;
  do
  {
    if ( !v3 )
      break;
    v8 = *v4;
    if ( !*v4 )
      break;
    ++v4;
    *v7++ = v8;
    --v3;
    --v6;
  }
  while ( v6 );
  v9 = v7 - 1;
  if ( v6 )
    v9 = v7;
  *v9 = 0;
  if ( !v6 )
    goto LABEL_9;
  v11 = L"Global\\AmiUtcThrottlingTimer2";
  v12 = TimerName;
  do
  {
    if ( !v2 )
      break;
    v13 = *v11;
    if ( !*v11 )
      break;
    ++v11;
    *v12++ = v13;
    --v2;
    --v5;
  }
  while ( v5 );
  v14 = (UtcThrottle *)(v12 - 1);
  if ( v5 )
    v14 = (UtcThrottle *)v12;
  *(_WORD *)v14 = 0;
  if ( !v5 )
  {
LABEL_9:
    v10 = 14;
    goto LABEL_41;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v14, &v29, (struct _ACL **)&hMem);
  v10 = LastError;
  if ( LastError )
  {
    v16 = "Failed to initialize security descriptor [%d]";
    v17 = 123;
LABEL_19:
    LODWORD(lpArgToCompletionRoutine) = LastError;
    AslLogCallPrintf(1, "UtcThrottle::Initialize", v17, v16, lpArgToCompletionRoutine);
    goto LABEL_41;
  }
  if ( !qword_1400C8DC0 )
  {
    qword_1400C8DC0 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_1400C8DC0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      v16 = "Failed to create event [%d]";
      v17 = 133;
      goto LABEL_19;
    }
  }
  if ( !InventoryCoreUtcThrottle )
  {
    InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    if ( !InventoryCoreUtcThrottle )
    {
      v18 = GetLastError();
      AslLogCallPrintf(3, "UtcThrottle::Initialize", 144, "Failed to create named semaphore [%d]", v18);
      InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      if ( !InventoryCoreUtcThrottle )
      {
        LastError = GetLastError();
        v10 = LastError;
        v16 = "Failed to create semaphore [%d]";
        v17 = 150;
        goto LABEL_19;
      }
    }
  }
  if ( hObject )
    goto LABEL_39;
  v19 = CreateWaitableTimerW(&SemaphoreAttributes, 0, TimerName);
  hObject = v19;
  if ( v19 )
  {
LABEL_37:
    DueTime.QuadPart = -10000000;
    if ( !SetWaitableTimer(v19, &DueTime, 0, 0, 0, 0) )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    goto LABEL_39;
  }
  v20 = GetLastError();
  v21 = 183;
  if ( v20 == 183 )
  {
    hObject = OpenWaitableTimerW(0x100000u, 0, TimerName);
    if ( hObject )
      goto LABEL_34;
    v20 = GetLastError();
    v22 = "Failed to open named timer [%d]";
    v21 = 178;
    v23 = 1;
  }
  else
  {
    v22 = "Failed to create named timer [%d]";
    v23 = 3;
  }
  LODWORD(lpArgToCompletionRoutine) = v20;
  AslLogCallPrintf(v23, "UtcThrottle::Initialize", v21, v22, lpArgToCompletionRoutine);
LABEL_34:
  if ( !hObject )
  {
    v19 = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    hObject = v19;
    if ( !v19 )
    {
      LastError = GetLastError();
      v10 = LastError;
      v16 = "Failed to create timer [%d]";
      v17 = 197;
      goto LABEL_19;
    }
    goto LABEL_37;
  }
LABEL_39:
  byte_1400C8DF0 = 1;
LABEL_40:
  v10 = 0;
LABEL_41:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LeaveCriticalSection(&stru_1400C8DC8);
  return v10;
}

```

## disassembly

```asm
0x14001a2f4  push    rbp
0x14001a2f6  push    rbx
0x14001a2f7  push    rsi
0x14001a2f8  push    r12
0x14001a2fa  push    r14
0x14001a2fc  lea     rbp, [rsp-3B0h]
0x14001a304  sub     rsp, 4B0h
0x14001a30b  mov     rax, cs:__security_cookie
0x14001a312  xor     rax, rsp
0x14001a315  mov     [rbp+3D0h+var_30], rax
0x14001a31c  xorps   xmm0, xmm0
0x14001a31f  xor     eax, eax
0x14001a321  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x14001a326  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x14001a32b  mov     [rsp+4D0h+var_478.Dacl], rax
0x14001a330  xor     esi, esi
0x14001a332  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x14001a33b  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rsi
0x14001a340  mov     [rsp+4D0h+hMem], rsi
0x14001a345  mov     ebx, 208h
0x14001a34a  mov     r8d, ebx; Size
0x14001a34d  xor     edx, edx; Val
0x14001a34f  lea     rcx, [rbp+3D0h+Name]; void *
0x14001a356  call    memset_0
0x14001a35b  mov     r8d, ebx; Size
0x14001a35e  xor     edx, edx; Val
0x14001a360  lea     rcx, [rbp+3D0h+TimerName]; void *
0x14001a364  call    memset_0
0x14001a369  lea     rax, [rsp+4D0h+var_478]
0x14001a36e  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x14001a373  lea     r12, stru_1400C8DC8
0x14001a37a  mov     rcx, r12; lpCriticalSection
0x14001a37d  call    cs:__imp_EnterCriticalSection
0x14001a383  mov     qword ptr [rsp+4D0h+DueTime], r12
0x14001a388  cmp     cs:byte_1400C8DF0, sil
0x14001a38f  jnz     loc_14001A650
0x14001a395  mov     r9d, 7FFFFFFEh
0x14001a39b  mov     ecx, r9d
0x14001a39e  lea     r10, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x14001a3a5  mov     edx, 104h
0x14001a3aa  mov     r8d, edx
0x14001a3ad  lea     rax, [rbp+3D0h+Name]
0x14001a3b4  lea     r14d, [rsi+1]
0x14001a3b8  test    rcx, rcx
0x14001a3bb  jz      short loc_14001A3DB
0x14001a3bd  movzx   r11d, word ptr [r10]
0x14001a3c1  test    r11w, r11w
0x14001a3c5  jz      short loc_14001A3DB
0x14001a3c7  add     r10, 2
0x14001a3cb  mov     [rax], r11w
0x14001a3cf  add     rax, 2
0x14001a3d3  sub     rcx, r14
0x14001a3d6  sub     r8, r14
0x14001a3d9  jnz     short loc_14001A3B8
0x14001a3db  lea     rcx, [rax-2]
0x14001a3df  test    r8, r8
0x14001a3e2  cmovnz  rcx, rax
0x14001a3e6  mov     [rcx], si
0x14001a3e9  jnz     short loc_14001A3F5
0x14001a3eb  mov     ebx, 0Eh
0x14001a3f0  jmp     loc_14001A652
0x14001a3f5  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x14001a3fc  lea     rax, [rbp+3D0h+TimerName]
0x14001a400  test    r9, r9
0x14001a403  jz      short loc_14001A423
0x14001a405  movzx   r8d, word ptr [rcx]
0x14001a409  test    r8w, r8w
0x14001a40d  jz      short loc_14001A423
0x14001a40f  add     rcx, 2
0x14001a413  mov     [rax], r8w
0x14001a417  add     rax, 2
0x14001a41b  sub     r9, r14
0x14001a41e  sub     rdx, r14
0x14001a421  jnz     short loc_14001A400
0x14001a423  lea     rcx, [rax-2]
0x14001a427  test    rdx, rdx
0x14001a42a  cmovnz  rcx, rax; this
0x14001a42e  mov     [rcx], si
0x14001a431  jz      short loc_14001A3EB
0x14001a433  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x14001a438  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x14001a43d  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x14001a442  mov     ebx, eax
0x14001a444  test    eax, eax
0x14001a446  jz      short loc_14001A46D
0x14001a448  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x14001a44f  mov     r8d, 7Bh ; '{'
0x14001a455  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x14001a459  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x14001a460  mov     ecx, r14d
0x14001a463  call    AslLogCallPrintf
0x14001a468  jmp     loc_14001A652
0x14001a46d  cmp     cs:qword_1400C8DC0, rsi
0x14001a474  jnz     short loc_14001A4AA
0x14001a476  xor     r9d, r9d; lpName
0x14001a479  xor     r8d, r8d; bInitialState
0x14001a47c  mov     edx, r14d; bManualReset
0x14001a47f  xor     ecx, ecx; lpEventAttributes
0x14001a481  call    cs:__imp_CreateEventW
0x14001a487  mov     cs:qword_1400C8DC0, rax
0x14001a48e  test    rax, rax
0x14001a491  jnz     short loc_14001A4AA
0x14001a493  call    cs:__imp_GetLastError
0x14001a499  mov     ebx, eax
0x14001a49b  lea     r9, aFailedToCreate_1; "Failed to create event [%d]"
0x14001a4a2  mov     r8d, 85h
0x14001a4a8  jmp     short loc_14001A455
0x14001a4aa  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rsi; UtcThrottle InventoryCoreUtcThrottle
0x14001a4b1  jnz     loc_14001A53C
0x14001a4b7  lea     r9, [rbp+3D0h+Name]; lpName
0x14001a4be  mov     ebx, 14h
0x14001a4c3  mov     r8d, ebx; lMaximumCount
0x14001a4c6  mov     edx, ebx; lInitialCount
0x14001a4c8  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x14001a4cd  call    cs:__imp_CreateSemaphoreW
0x14001a4d3  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x14001a4da  test    rax, rax
0x14001a4dd  jnz     short loc_14001A53C
0x14001a4df  call    cs:__imp_GetLastError
0x14001a4e5  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x14001a4e9  lea     r9, aFailedToCreate_3; "Failed to create named semaphore [%d]"
0x14001a4f0  lea     r8d, [rbx+7Ch]
0x14001a4f4  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x14001a4fb  lea     ecx, [rbx-11h]
0x14001a4fe  call    AslLogCallPrintf
0x14001a503  xor     r9d, r9d; lpName
0x14001a506  mov     r8d, ebx; lMaximumCount
0x14001a509  mov     edx, ebx; lInitialCount
0x14001a50b  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x14001a510  call    cs:__imp_CreateSemaphoreW
0x14001a516  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x14001a51d  test    rax, rax
0x14001a520  jnz     short loc_14001A53C
0x14001a522  call    cs:__imp_GetLastError
0x14001a528  mov     ebx, eax
0x14001a52a  lea     r9, aFailedToCreate_2; "Failed to create semaphore [%d]"
0x14001a531  mov     r8d, 96h
0x14001a537  jmp     loc_14001A455
0x14001a53c  cmp     cs:hObject, rsi
0x14001a543  jnz     loc_14001A649
0x14001a549  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x14001a54d  xor     edx, edx; bManualReset
0x14001a54f  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x14001a554  call    cs:__imp_CreateWaitableTimerW
0x14001a55a  mov     cs:hObject, rax
0x14001a561  test    rax, rax
0x14001a564  jnz     loc_14001A60B
0x14001a56a  call    cs:__imp_GetLastError
0x14001a570  mov     r8d, 0B7h
0x14001a576  cmp     eax, r8d
0x14001a579  jnz     short loc_14001A5B0
0x14001a57b  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x14001a57f  xor     edx, edx; bInheritHandle
0x14001a581  mov     ecx, 100000h; dwDesiredAccess
0x14001a586  call    cs:__imp_OpenWaitableTimerW
0x14001a58c  mov     cs:hObject, rax
0x14001a593  test    rax, rax
0x14001a596  jnz     short loc_14001A5CC
0x14001a598  call    cs:__imp_GetLastError
0x14001a59e  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x14001a5a5  mov     r8d, 0B2h
0x14001a5ab  mov     ecx, r14d
0x14001a5ae  jmp     short loc_14001A5BC
0x14001a5b0  lea     r9, aFailedToCreate_4; "Failed to create named timer [%d]"
0x14001a5b7  mov     ecx, 3
0x14001a5bc  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x14001a5c0  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x14001a5c7  call    AslLogCallPrintf
0x14001a5cc  cmp     cs:hObject, rsi
0x14001a5d3  jnz     short loc_14001A649
0x14001a5d5  xor     r8d, r8d; lpTimerName
0x14001a5d8  xor     edx, edx; bManualReset
0x14001a5da  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x14001a5df  call    cs:__imp_CreateWaitableTimerW
0x14001a5e5  mov     cs:hObject, rax
0x14001a5ec  test    rax, rax
0x14001a5ef  jnz     short loc_14001A60B
0x14001a5f1  call    cs:__imp_GetLastError
0x14001a5f7  mov     ebx, eax
0x14001a5f9  lea     r9, aFailedToCreate_0; "Failed to create timer [%d]"
0x14001a600  mov     r8d, 0C5h
0x14001a606  jmp     loc_14001A455
0x14001a60b  mov     qword ptr [rsp+4D0h+DueTime], 0FFFFFFFFFF676980h
0x14001a614  mov     [rsp+4D0h+fResume], esi; fResume
0x14001a618  mov     [rsp+4D0h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x14001a61d  xor     r9d, r9d; pfnCompletionRoutine
0x14001a620  xor     r8d, r8d; lPeriod
0x14001a623  lea     rdx, [rsp+4D0h+DueTime]; lpDueTime
0x14001a628  mov     rcx, rax; hTimer
0x14001a62b  call    cs:__imp_SetWaitableTimer
0x14001a631  test    eax, eax
0x14001a633  jnz     short loc_14001A649
0x14001a635  mov     rcx, cs:hObject; hObject
0x14001a63c  call    cs:__imp_CloseHandle
0x14001a642  mov     cs:hObject, rsi
0x14001a649  mov     cs:byte_1400C8DF0, r14b
0x14001a650  mov     ebx, esi
0x14001a652  mov     rcx, [rsp+4D0h+hMem]; hMem
0x14001a657  test    rcx, rcx
0x14001a65a  jz      short loc_14001A667
0x14001a65c  call    cs:__imp_LocalFree
0x14001a662  mov     [rsp+4D0h+hMem], rsi
0x14001a667  mov     rcx, r12; lpCriticalSection
0x14001a66a  call    cs:__imp_LeaveCriticalSection
0x14001a670  mov     eax, ebx
0x14001a672  mov     rcx, [rbp+3D0h+var_30]
0x14001a679  xor     rcx, rsp; StackCookie
0x14001a67c  call    __security_check_cookie
0x14001a681  add     rsp, 4B0h
0x14001a688  pop     r14
0x14001a68a  pop     r12
0x14001a68c  pop     rsi
0x14001a68d  pop     rbx
0x14001a68e  pop     rbp
0x14001a68f  retn
```
