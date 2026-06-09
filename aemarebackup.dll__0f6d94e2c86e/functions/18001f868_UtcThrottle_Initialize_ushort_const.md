# UtcThrottle::Initialize(ushort const *)

- ea: `0x18001f868`
- end: `0x18001fc04`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `924`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002543c`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x18001f868`
- `0x18001fdf4`
- `0x18004c020`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8f1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f8f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f9f5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001f9f5`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x18001fafa`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x18001fafa`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001fb9f`
- `api-ms-win-core-synch-l1-1-0!SetWaitableTimer` at `0x18001fb9f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbde`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fbde`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb65`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa07`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fa96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fade`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb0c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb65`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbb0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001fbb0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001fa41`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001fa84`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001fa41`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x18001fa84`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001fac8`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001fb53`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001fac8`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x18001fb53`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbd0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fbd0`

## string_xrefs

- `0x18001f9bc`: `Failed to initialize security descriptor [%d]`
- `0x18001fa0f`: `Failed to create event [%d]`
- `0x18001fa5d`: `Failed to create named semaphore [%d]`
- `0x18001fa9e`: `Failed to create semaphore [%d]`
- `0x18001fb12`: `Failed to open named timer [%d]`
- `0x18001fb24`: `Failed to create named timer [%d]`
- `0x18001fb6d`: `Failed to create timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+40h] [rbp-C0h] BYREF
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
  EnterCriticalSection(&stru_18011AD18);
  DueTime.QuadPart = (LONGLONG)&stru_18011AD18;
  if ( byte_18011AD40 )
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
  if ( !qword_18011AD10 )
  {
    qword_18011AD10 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_18011AD10 )
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
  byte_18011AD40 = 1;
LABEL_40:
  v10 = 0;
LABEL_41:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  LeaveCriticalSection(&stru_18011AD18);
  return v10;
}

```

## disassembly

```asm
0x18001f868  push    rbp
0x18001f86a  push    rbx
0x18001f86b  push    rsi
0x18001f86c  push    r12
0x18001f86e  push    r14
0x18001f870  lea     rbp, [rsp-3B0h]
0x18001f878  sub     rsp, 4B0h
0x18001f87f  mov     rax, cs:__security_cookie
0x18001f886  xor     rax, rsp
0x18001f889  mov     [rbp+3D0h+var_30], rax
0x18001f890  xorps   xmm0, xmm0
0x18001f893  xor     eax, eax
0x18001f895  movups  xmmword ptr [rsp+4D0h+var_478.Revision], xmm0
0x18001f89a  movups  xmmword ptr [rsp+4D0h+var_478.Group], xmm0
0x18001f89f  mov     [rsp+4D0h+var_478.Dacl], rax
0x18001f8a4  xor     esi, esi
0x18001f8a6  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.nLength], 18h
0x18001f8af  mov     qword ptr [rsp+4D0h+SemaphoreAttributes.bInheritHandle], rsi
0x18001f8b4  mov     [rsp+4D0h+hMem], rsi
0x18001f8b9  mov     ebx, 208h
0x18001f8be  mov     r8d, ebx; Size
0x18001f8c1  xor     edx, edx; Val
0x18001f8c3  lea     rcx, [rbp+3D0h+Name]; void *
0x18001f8ca  call    memset_0
0x18001f8cf  mov     r8d, ebx; Size
0x18001f8d2  xor     edx, edx; Val
0x18001f8d4  lea     rcx, [rbp+3D0h+TimerName]; void *
0x18001f8d8  call    memset_0
0x18001f8dd  lea     rax, [rsp+4D0h+var_478]
0x18001f8e2  mov     [rsp+4D0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x18001f8e7  lea     r12, stru_18011AD18
0x18001f8ee  mov     rcx, r12; lpCriticalSection
0x18001f8f1  call    cs:__imp_EnterCriticalSection
0x18001f8f7  mov     qword ptr [rsp+4D0h+DueTime], r12
0x18001f8fc  cmp     cs:byte_18011AD40, sil
0x18001f903  jnz     loc_18001FBC4
0x18001f909  mov     r9d, 7FFFFFFEh
0x18001f90f  mov     ecx, r9d
0x18001f912  lea     r10, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x18001f919  mov     edx, 104h
0x18001f91e  mov     r8d, edx
0x18001f921  lea     rax, [rbp+3D0h+Name]
0x18001f928  lea     r14d, [rsi+1]
0x18001f92c  test    rcx, rcx
0x18001f92f  jz      short loc_18001F94F
0x18001f931  movzx   r11d, word ptr [r10]
0x18001f935  test    r11w, r11w
0x18001f939  jz      short loc_18001F94F
0x18001f93b  add     r10, 2
0x18001f93f  mov     [rax], r11w
0x18001f943  add     rax, 2
0x18001f947  sub     rcx, r14
0x18001f94a  sub     r8, r14
0x18001f94d  jnz     short loc_18001F92C
0x18001f94f  lea     rcx, [rax-2]
0x18001f953  test    r8, r8
0x18001f956  cmovnz  rcx, rax
0x18001f95a  mov     [rcx], si
0x18001f95d  jnz     short loc_18001F969
0x18001f95f  mov     ebx, 0Eh
0x18001f964  jmp     loc_18001FBC6
0x18001f969  lea     rcx, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x18001f970  lea     rax, [rbp+3D0h+TimerName]
0x18001f974  test    r9, r9
0x18001f977  jz      short loc_18001F997
0x18001f979  movzx   r8d, word ptr [rcx]
0x18001f97d  test    r8w, r8w
0x18001f981  jz      short loc_18001F997
0x18001f983  add     rcx, 2
0x18001f987  mov     [rax], r8w
0x18001f98b  add     rax, 2
0x18001f98f  sub     r9, r14
0x18001f992  sub     rdx, r14
0x18001f995  jnz     short loc_18001F974
0x18001f997  lea     rcx, [rax-2]
0x18001f99b  test    rdx, rdx
0x18001f99e  cmovnz  rcx, rax; this
0x18001f9a2  mov     [rcx], si
0x18001f9a5  jz      short loc_18001F95F
0x18001f9a7  lea     r8, [rsp+4D0h+hMem]; struct _ACL **
0x18001f9ac  lea     rdx, [rsp+4D0h+var_478]; struct _SECURITY_DESCRIPTOR *
0x18001f9b1  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x18001f9b6  mov     ebx, eax
0x18001f9b8  test    eax, eax
0x18001f9ba  jz      short loc_18001F9E1
0x18001f9bc  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x18001f9c3  mov     r8d, 7Bh ; '{'
0x18001f9c9  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x18001f9cd  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x18001f9d4  mov     ecx, r14d
0x18001f9d7  call    AslLogCallPrintf
0x18001f9dc  jmp     loc_18001FBC6
0x18001f9e1  cmp     cs:qword_18011AD10, rsi
0x18001f9e8  jnz     short loc_18001FA1E
0x18001f9ea  xor     r9d, r9d; lpName
0x18001f9ed  xor     r8d, r8d; bInitialState
0x18001f9f0  mov     edx, r14d; bManualReset
0x18001f9f3  xor     ecx, ecx; lpEventAttributes
0x18001f9f5  call    cs:__imp_CreateEventW
0x18001f9fb  mov     cs:qword_18011AD10, rax
0x18001fa02  test    rax, rax
0x18001fa05  jnz     short loc_18001FA1E
0x18001fa07  call    cs:__imp_GetLastError
0x18001fa0d  mov     ebx, eax
0x18001fa0f  lea     r9, aFailedToCreate_2; "Failed to create event [%d]"
0x18001fa16  mov     r8d, 85h
0x18001fa1c  jmp     short loc_18001F9C9
0x18001fa1e  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rsi; UtcThrottle InventoryCoreUtcThrottle
0x18001fa25  jnz     loc_18001FAB0
0x18001fa2b  lea     r9, [rbp+3D0h+Name]; lpName
0x18001fa32  mov     ebx, 14h
0x18001fa37  mov     r8d, ebx; lMaximumCount
0x18001fa3a  mov     edx, ebx; lInitialCount
0x18001fa3c  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x18001fa41  call    cs:__imp_CreateSemaphoreW
0x18001fa47  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x18001fa4e  test    rax, rax
0x18001fa51  jnz     short loc_18001FAB0
0x18001fa53  call    cs:__imp_GetLastError
0x18001fa59  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x18001fa5d  lea     r9, aFailedToCreate_4; "Failed to create named semaphore [%d]"
0x18001fa64  lea     r8d, [rbx+7Ch]
0x18001fa68  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x18001fa6f  lea     ecx, [rbx-11h]
0x18001fa72  call    AslLogCallPrintf
0x18001fa77  xor     r9d, r9d; lpName
0x18001fa7a  mov     r8d, ebx; lMaximumCount
0x18001fa7d  mov     edx, ebx; lInitialCount
0x18001fa7f  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x18001fa84  call    cs:__imp_CreateSemaphoreW
0x18001fa8a  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x18001fa91  test    rax, rax
0x18001fa94  jnz     short loc_18001FAB0
0x18001fa96  call    cs:__imp_GetLastError
0x18001fa9c  mov     ebx, eax
0x18001fa9e  lea     r9, aFailedToCreate_3; "Failed to create semaphore [%d]"
0x18001faa5  mov     r8d, 96h
0x18001faab  jmp     loc_18001F9C9
0x18001fab0  cmp     cs:hObject, rsi
0x18001fab7  jnz     loc_18001FBBD
0x18001fabd  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x18001fac1  xor     edx, edx; bManualReset
0x18001fac3  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x18001fac8  call    cs:__imp_CreateWaitableTimerW
0x18001face  mov     cs:hObject, rax
0x18001fad5  test    rax, rax
0x18001fad8  jnz     loc_18001FB7F
0x18001fade  call    cs:__imp_GetLastError
0x18001fae4  mov     r8d, 0B7h
0x18001faea  cmp     eax, r8d
0x18001faed  jnz     short loc_18001FB24
0x18001faef  lea     r8, [rbp+3D0h+TimerName]; lpTimerName
0x18001faf3  xor     edx, edx; bInheritHandle
0x18001faf5  mov     ecx, 100000h; dwDesiredAccess
0x18001fafa  call    cs:__imp_OpenWaitableTimerW
0x18001fb00  mov     cs:hObject, rax
0x18001fb07  test    rax, rax
0x18001fb0a  jnz     short loc_18001FB40
0x18001fb0c  call    cs:__imp_GetLastError
0x18001fb12  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x18001fb19  mov     r8d, 0B2h
0x18001fb1f  mov     ecx, r14d
0x18001fb22  jmp     short loc_18001FB30
0x18001fb24  lea     r9, aFailedToCreate_5; "Failed to create named timer [%d]"
0x18001fb2b  mov     ecx, 3
0x18001fb30  mov     dword ptr [rsp+4D0h+lpArgToCompletionRoutine], eax
0x18001fb34  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x18001fb3b  call    AslLogCallPrintf
0x18001fb40  cmp     cs:hObject, rsi
0x18001fb47  jnz     short loc_18001FBBD
0x18001fb49  xor     r8d, r8d; lpTimerName
0x18001fb4c  xor     edx, edx; bManualReset
0x18001fb4e  lea     rcx, [rsp+4D0h+SemaphoreAttributes]; lpTimerAttributes
0x18001fb53  call    cs:__imp_CreateWaitableTimerW
0x18001fb59  mov     cs:hObject, rax
0x18001fb60  test    rax, rax
0x18001fb63  jnz     short loc_18001FB7F
0x18001fb65  call    cs:__imp_GetLastError
0x18001fb6b  mov     ebx, eax
0x18001fb6d  lea     r9, aFailedToCreate_1; "Failed to create timer [%d]"
0x18001fb74  mov     r8d, 0C5h
0x18001fb7a  jmp     loc_18001F9C9
0x18001fb7f  mov     qword ptr [rsp+4D0h+DueTime], 0FFFFFFFFFF676980h
0x18001fb88  mov     [rsp+4D0h+fResume], esi; fResume
0x18001fb8c  mov     [rsp+4D0h+lpArgToCompletionRoutine], rsi; lpArgToCompletionRoutine
0x18001fb91  xor     r9d, r9d; pfnCompletionRoutine
0x18001fb94  xor     r8d, r8d; lPeriod
0x18001fb97  lea     rdx, [rsp+4D0h+DueTime]; lpDueTime
0x18001fb9c  mov     rcx, rax; hTimer
0x18001fb9f  call    cs:__imp_SetWaitableTimer
0x18001fba5  test    eax, eax
0x18001fba7  jnz     short loc_18001FBBD
0x18001fba9  mov     rcx, cs:hObject; hObject
0x18001fbb0  call    cs:__imp_CloseHandle
0x18001fbb6  mov     cs:hObject, rsi
0x18001fbbd  mov     cs:byte_18011AD40, r14b
0x18001fbc4  mov     ebx, esi
0x18001fbc6  mov     rcx, [rsp+4D0h+hMem]; hMem
0x18001fbcb  test    rcx, rcx
0x18001fbce  jz      short loc_18001FBDB
0x18001fbd0  call    cs:__imp_LocalFree
0x18001fbd6  mov     [rsp+4D0h+hMem], rsi
0x18001fbdb  mov     rcx, r12; lpCriticalSection
0x18001fbde  call    cs:__imp_LeaveCriticalSection
0x18001fbe4  mov     eax, ebx
0x18001fbe6  mov     rcx, [rbp+3D0h+var_30]
0x18001fbed  xor     rcx, rsp; StackCookie
0x18001fbf0  call    __security_check_cookie
0x18001fbf5  add     rsp, 4B0h
0x18001fbfc  pop     r14
0x18001fbfe  pop     r12
0x18001fc00  pop     rsi
0x18001fc01  pop     rbx
0x18001fc02  pop     rbp
0x18001fc03  retn
```
