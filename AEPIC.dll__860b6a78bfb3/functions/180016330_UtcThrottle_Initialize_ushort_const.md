# UtcThrottle::Initialize(ushort const *)

- ea: `0x180016330`
- end: `0x180016642`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `786`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18001b7a4`
- `0x18003ad18`

## callees

- `0x180005890`
- `0x180006938`
- `0x180008550`
- `0x18000cb30`
- `0x180016330`
- `0x180016648`
- `0x18001a934`
- `0x1800295dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163b5`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800163b5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016460`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016460`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180016567`
- `api-ms-win-core-synch-l1-1-0!OpenWaitableTimerW` at `0x180016567`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001654b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165d5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016472`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800164bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016502`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001654b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016579`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800165d5`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180016535`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800165c3`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x180016535`
- `api-ms-win-core-synch-l1-2-1!CreateWaitableTimerW` at `0x1800165c3`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800164ad`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800164f0`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800164ad`
- `api-ms-win-core-synch-l1-2-1!CreateSemaphoreW` at `0x1800164f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016607`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016607`

## string_xrefs

- `0x180016423`: `Failed to initialize security descriptor [%d]`
- `0x18001647a`: `Failed to create event [%d]`
- `0x1800164c9`: `Failed to create named semaphore [%d]`
- `0x18001650a`: `Failed to create semaphore [%d]`
- `0x18001657f`: `Failed to open named timer [%d]`
- `0x180016593`: `Failed to create named timer [%d]`
- `0x1800165dd`: `Failed to create timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r11
  unsigned int v3; // ebx
  UtcThrottle *v4; // rcx
  DWORD LastError; // eax
  const char *v6; // r9
  __int64 v7; // r8
  DWORD v8; // eax
  UtcThrottle *v9; // rcx
  DWORD v10; // eax
  __int64 v11; // r8
  const char *v12; // r9
  __int64 v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-E0h]
  HLOCAL hMem; // [rsp+30h] [rbp-D0h] BYREF
  _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+38h] [rbp-C8h] BYREF
  struct _RTL_CRITICAL_SECTION *v18; // [rsp+50h] [rbp-B0h] BYREF
  _SECURITY_DESCRIPTOR v19; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR TimerName[264]; // [rsp+80h] [rbp-80h] BYREF
  WCHAR Name[264]; // [rsp+290h] [rbp+190h] BYREF

  memset(&v19, 0, sizeof(v19));
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v19;
  EnterCriticalSection(&CriticalSection);
  v18 = &CriticalSection;
  if ( byte_1801217C0 )
    goto LABEL_27;
  if ( StringCchCopyW(Name, 0x104u, L"Global\\AmiUtcThrottlingSemaphore") < 0
    || StringCchCopyW(TimerName, v2, L"Global\\AmiUtcThrottlingTimer2") < 0 )
  {
    v3 = 14;
    goto LABEL_28;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v4, &v19, (struct _ACL **)&hMem);
  v3 = LastError;
  if ( LastError )
  {
    v6 = "Failed to initialize security descriptor [%d]";
    v7 = 123;
LABEL_7:
    LODWORD(v15) = LastError;
    AslLogCallPrintf(1, "UtcThrottle::Initialize", v7, v6, v15);
    goto LABEL_28;
  }
  if ( !qword_180121790 )
  {
    qword_180121790 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_180121790 )
    {
      LastError = GetLastError();
      v3 = LastError;
      v6 = "Failed to create event [%d]";
      v7 = 133;
      goto LABEL_7;
    }
  }
  if ( !InventoryCoreUtcThrottle )
  {
    InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    if ( !InventoryCoreUtcThrottle )
    {
      v8 = GetLastError();
      AslLogCallPrintf(3, "UtcThrottle::Initialize", 144, "Failed to create named semaphore [%d]", v8);
      InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      if ( !InventoryCoreUtcThrottle )
      {
        LastError = GetLastError();
        v3 = LastError;
        v6 = "Failed to create semaphore [%d]";
        v7 = 150;
        goto LABEL_7;
      }
    }
  }
  if ( hObject )
    goto LABEL_26;
  hObject = CreateWaitableTimerW(&SemaphoreAttributes, 0, TimerName);
  if ( hObject )
  {
LABEL_25:
    UtcThrottle::SetTimer(v9);
    goto LABEL_26;
  }
  v10 = GetLastError();
  v11 = 183;
  if ( v10 == 183 )
  {
    hObject = OpenWaitableTimerW(0x100000u, 0, TimerName);
    if ( hObject )
      goto LABEL_22;
    v10 = GetLastError();
    v12 = "Failed to open named timer [%d]";
    v11 = 178;
    v13 = 1;
  }
  else
  {
    v12 = "Failed to create named timer [%d]";
    v13 = 3;
  }
  LODWORD(v15) = v10;
  AslLogCallPrintf(v13, "UtcThrottle::Initialize", v11, v12, v15);
LABEL_22:
  if ( !hObject )
  {
    hObject = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      v3 = LastError;
      v6 = "Failed to create timer [%d]";
      v7 = 197;
      goto LABEL_7;
    }
    goto LABEL_25;
  }
LABEL_26:
  byte_1801217C0 = 1;
LABEL_27:
  v3 = 0;
LABEL_28:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v18);
  return v3;
}

```

## disassembly

```asm
0x180016330  mov     [rsp-8+arg_0], rbx
0x180016335  push    rbp
0x180016336  lea     rbp, [rsp-3B0h]
0x18001633e  sub     rsp, 4B0h
0x180016345  mov     rax, cs:__security_cookie
0x18001634c  xor     rax, rsp
0x18001634f  mov     [rbp+3B0h+var_10], rax
0x180016356  xorps   xmm0, xmm0
0x180016359  xor     eax, eax
0x18001635b  movups  xmmword ptr [rsp+4B0h+var_458.Revision], xmm0
0x180016360  movups  xmmword ptr [rsp+4B0h+var_458.Group], xmm0
0x180016365  mov     [rsp+4B0h+var_458.Dacl], rax
0x18001636a  mov     qword ptr [rsp+4B0h+SemaphoreAttributes.nLength], 18h
0x180016373  mov     qword ptr [rsp+4B0h+SemaphoreAttributes.bInheritHandle], rax
0x180016378  mov     [rsp+4B0h+hMem], rax
0x18001637d  mov     ebx, 208h
0x180016382  mov     r8d, ebx; Size
0x180016385  xor     edx, edx; Val
0x180016387  lea     rcx, [rbp+3B0h+Name]; void *
0x18001638e  call    memset_0
0x180016393  mov     r8d, ebx; Size
0x180016396  xor     edx, edx; Val
0x180016398  lea     rcx, [rbp+3B0h+TimerName]; void *
0x18001639c  call    memset_0
0x1800163a1  lea     rax, [rsp+4B0h+var_458]
0x1800163a6  mov     [rsp+4B0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x1800163ab  lea     rbx, CriticalSection
0x1800163b2  mov     rcx, rbx; lpCriticalSection
0x1800163b5  call    cs:__imp_EnterCriticalSection
0x1800163bb  mov     [rsp+4B0h+var_460], rbx
0x1800163c0  cmp     cs:byte_1801217C0, 0
0x1800163c7  jnz     loc_1800165FB
0x1800163cd  lea     r8, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x1800163d4  mov     r11d, 104h
0x1800163da  mov     edx, r11d; unsigned __int64
0x1800163dd  lea     rcx, [rbp+3B0h+Name]; unsigned __int16 *
0x1800163e4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800163e9  test    eax, eax
0x1800163eb  jns     short loc_1800163F7
0x1800163ed  mov     ebx, 0Eh
0x1800163f2  jmp     loc_1800165FD
0x1800163f7  lea     r8, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x1800163fe  mov     rdx, r11; unsigned __int64
0x180016401  lea     rcx, [rbp+3B0h+TimerName]; unsigned __int16 *
0x180016405  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001640a  test    eax, eax
0x18001640c  js      short loc_1800163ED
0x18001640e  lea     r8, [rsp+4B0h+hMem]; struct _ACL **
0x180016413  lea     rdx, [rsp+4B0h+var_458]; struct _SECURITY_DESCRIPTOR *
0x180016418  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x18001641d  mov     ebx, eax
0x18001641f  test    eax, eax
0x180016421  jz      short loc_18001644A
0x180016423  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x18001642a  mov     r8d, 7Bh ; '{'
0x180016430  mov     [rsp+4B0h+var_490], eax
0x180016434  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x18001643b  mov     ecx, 1
0x180016440  call    AslLogCallPrintf
0x180016445  jmp     loc_1800165FD
0x18001644a  cmp     cs:qword_180121790, 0
0x180016452  jnz     short loc_180016489
0x180016454  xor     r9d, r9d; lpName
0x180016457  xor     r8d, r8d; bInitialState
0x18001645a  lea     edx, [r9+1]; bManualReset
0x18001645e  xor     ecx, ecx; lpEventAttributes
0x180016460  call    cs:__imp_CreateEventW
0x180016466  mov     cs:qword_180121790, rax
0x18001646d  test    rax, rax
0x180016470  jnz     short loc_180016489
0x180016472  call    cs:__imp_GetLastError
0x180016478  mov     ebx, eax
0x18001647a  lea     r9, aFailedToCreate_3; "Failed to create event [%d]"
0x180016481  mov     r8d, 85h
0x180016487  jmp     short loc_180016430
0x180016489  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, 0; UtcThrottle InventoryCoreUtcThrottle
0x180016491  jnz     loc_18001651C
0x180016497  lea     r9, [rbp+3B0h+Name]; lpName
0x18001649e  mov     ebx, 14h
0x1800164a3  mov     r8d, ebx; lMaximumCount
0x1800164a6  mov     edx, ebx; lInitialCount
0x1800164a8  lea     rcx, [rsp+4B0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x1800164ad  call    cs:__imp_CreateSemaphoreW
0x1800164b3  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x1800164ba  test    rax, rax
0x1800164bd  jnz     short loc_18001651C
0x1800164bf  call    cs:__imp_GetLastError
0x1800164c5  mov     [rsp+4B0h+var_490], eax
0x1800164c9  lea     r9, aFailedToCreate_5; "Failed to create named semaphore [%d]"
0x1800164d0  lea     r8d, [rbx+7Ch]
0x1800164d4  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x1800164db  lea     ecx, [rbx-11h]
0x1800164de  call    AslLogCallPrintf
0x1800164e3  xor     r9d, r9d; lpName
0x1800164e6  mov     r8d, ebx; lMaximumCount
0x1800164e9  mov     edx, ebx; lInitialCount
0x1800164eb  lea     rcx, [rsp+4B0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x1800164f0  call    cs:__imp_CreateSemaphoreW
0x1800164f6  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x1800164fd  test    rax, rax
0x180016500  jnz     short loc_18001651C
0x180016502  call    cs:__imp_GetLastError
0x180016508  mov     ebx, eax
0x18001650a  lea     r9, aFailedToCreate_4; "Failed to create semaphore [%d]"
0x180016511  mov     r8d, 96h
0x180016517  jmp     loc_180016430
0x18001651c  cmp     cs:hObject, 0
0x180016524  jnz     loc_1800165F4
0x18001652a  lea     r8, [rbp+3B0h+TimerName]; lpTimerName
0x18001652e  xor     edx, edx; bManualReset
0x180016530  lea     rcx, [rsp+4B0h+SemaphoreAttributes]; lpTimerAttributes
0x180016535  call    cs:__imp_CreateWaitableTimerW
0x18001653b  mov     cs:hObject, rax
0x180016542  test    rax, rax
0x180016545  jnz     loc_1800165EF
0x18001654b  call    cs:__imp_GetLastError
0x180016551  mov     r8d, 0B7h
0x180016557  cmp     eax, r8d
0x18001655a  jnz     short loc_180016593
0x18001655c  lea     r8, [rbp+3B0h+TimerName]; lpTimerName
0x180016560  xor     edx, edx; bInheritHandle
0x180016562  mov     ecx, 100000h; dwDesiredAccess
0x180016567  call    cs:__imp_OpenWaitableTimerW
0x18001656d  mov     cs:hObject, rax
0x180016574  test    rax, rax
0x180016577  jnz     short loc_1800165AF
0x180016579  call    cs:__imp_GetLastError
0x18001657f  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x180016586  mov     r8d, 0B2h
0x18001658c  mov     ecx, 1
0x180016591  jmp     short loc_18001659F
0x180016593  lea     r9, aFailedToCreate_6; "Failed to create named timer [%d]"
0x18001659a  mov     ecx, 3
0x18001659f  mov     [rsp+4B0h+var_490], eax
0x1800165a3  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x1800165aa  call    AslLogCallPrintf
0x1800165af  cmp     cs:hObject, 0
0x1800165b7  jnz     short loc_1800165F4
0x1800165b9  xor     r8d, r8d; lpTimerName
0x1800165bc  xor     edx, edx; bManualReset
0x1800165be  lea     rcx, [rsp+4B0h+SemaphoreAttributes]; lpTimerAttributes
0x1800165c3  call    cs:__imp_CreateWaitableTimerW
0x1800165c9  mov     cs:hObject, rax
0x1800165d0  test    rax, rax
0x1800165d3  jnz     short loc_1800165EF
0x1800165d5  call    cs:__imp_GetLastError
0x1800165db  mov     ebx, eax
0x1800165dd  lea     r9, aFailedToCreate_2; "Failed to create timer [%d]"
0x1800165e4  mov     r8d, 0C5h
0x1800165ea  jmp     loc_180016430
0x1800165ef  call    ?SetTimer@UtcThrottle@@AEAAXXZ; UtcThrottle::SetTimer(void)
0x1800165f4  mov     cs:byte_1801217C0, 1
0x1800165fb  xor     ebx, ebx
0x1800165fd  mov     rcx, [rsp+4B0h+hMem]; hMem
0x180016602  test    rcx, rcx
0x180016605  jz      short loc_180016616
0x180016607  call    cs:__imp_LocalFree
0x18001660d  mov     [rsp+4B0h+hMem], 0
0x180016616  lea     rcx, [rsp+4B0h+var_460]
0x18001661b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180016620  mov     eax, ebx
0x180016622  mov     rcx, [rbp+3B0h+var_10]
0x180016629  xor     rcx, rsp; StackCookie
0x18001662c  call    __security_check_cookie
0x180016631  mov     rbx, [rsp+4B0h+arg_0]
0x180016639  add     rsp, 4B0h
0x180016640  pop     rbp
0x180016641  retn
```
