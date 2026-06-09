# UtcThrottle::Initialize(ushort const *)

- ea: `0x180064688`
- end: `0x1800649a0`
- name: `?Initialize@UtcThrottle@@QEAAKPEBG@Z`
- size: `792`
- prototype: `unsigned int __fastcall(UtcThrottle *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18002cef4`

## callees

- `0x180006cc0`
- `0x1800197d4`
- `0x1800515b8`
- `0x1800538c0`
- `0x180059920`
- `0x18005a8bc`
- `0x180064688`
- `0x1800649a8`
- `0x1800667b4`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x1800647be`
- `KERNEL32!CreateEventW` at `0x1800647be`
- `KERNEL32!CreateSemaphoreW` at `0x18006480b`
- `KERNEL32!CreateSemaphoreW` at `0x18006484e`
- `KERNEL32!CreateSemaphoreW` at `0x18006480b`
- `KERNEL32!CreateSemaphoreW` at `0x18006484e`
- `KERNEL32!OpenWaitableTimerW` at `0x1800648c5`
- `KERNEL32!OpenWaitableTimerW` at `0x1800648c5`
- `KERNEL32!CreateWaitableTimerW` at `0x180064893`
- `KERNEL32!CreateWaitableTimerW` at `0x180064921`
- `KERNEL32!CreateWaitableTimerW` at `0x180064893`
- `KERNEL32!CreateWaitableTimerW` at `0x180064921`
- `KERNEL32!LocalFree` at `0x180064965`
- `KERNEL32!LocalFree` at `0x180064965`
- `KERNEL32!GetLastError` at `0x1800647d0`
- `KERNEL32!GetLastError` at `0x18006481d`
- `KERNEL32!GetLastError` at `0x180064860`
- `KERNEL32!GetLastError` at `0x1800648a9`
- `KERNEL32!GetLastError` at `0x1800648d7`
- `KERNEL32!GetLastError` at `0x180064933`
- `KERNEL32!GetLastError` at `0x1800647d0`
- `KERNEL32!GetLastError` at `0x18006481d`
- `KERNEL32!GetLastError` at `0x180064860`
- `KERNEL32!GetLastError` at `0x1800648a9`
- `KERNEL32!GetLastError` at `0x1800648d7`
- `KERNEL32!GetLastError` at `0x180064933`

## string_xrefs

- `0x180064781`: `Failed to initialize security descriptor [%d]`
- `0x1800647d8`: `Failed to create event [%d]`
- `0x180064827`: `Failed to create named semaphore [%d]`
- `0x180064868`: `Failed to create semaphore [%d]`
- `0x1800648dd`: `Failed to open named timer [%d]`
- `0x1800648f1`: `Failed to create named timer [%d]`
- `0x18006493b`: `Failed to create timer [%d]`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UtcThrottle::Initialize(UtcThrottle *this, const unsigned __int16 *a2)
{
  unsigned __int64 v2; // r10
  DWORD LastError; // ebx
  UtcThrottle *v4; // rcx
  const char *v5; // r9
  int v6; // r8d
  UtcThrottle *v7; // rcx
  DWORD v8; // eax
  int v9; // r8d
  const char *v10; // r9
  int v11; // ecx
  HLOCAL hMem; // [rsp+38h] [rbp-D0h] BYREF
  struct _SECURITY_ATTRIBUTES SemaphoreAttributes; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v15; // [rsp+58h] [rbp-B0h] BYREF
  _SECURITY_DESCRIPTOR v16; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v17; // [rsp+88h] [rbp-80h]
  WCHAR TimerName[264]; // [rsp+98h] [rbp-70h] BYREF
  WCHAR Name[264]; // [rsp+2A8h] [rbp+1A0h] BYREF

  *(_QWORD *)&v16.Revision = -2;
  memset(&v16.Owner, 0, 32);
  v17 = 0;
  *(_QWORD *)&SemaphoreAttributes.nLength = 24;
  *(_QWORD *)&SemaphoreAttributes.bInheritHandle = 0;
  hMem = 0;
  memset_0(Name, 0, 0x208u);
  memset_0(TimerName, 0, 0x208u);
  SemaphoreAttributes.lpSecurityDescriptor = &v16.Owner;
  wil::EnterCriticalSection(&v15, &CriticalSection);
  if ( byte_180182430 )
    goto LABEL_27;
  if ( (int)StringCchCopyW(Name, 0x104u, L"Global\\AmiUtcThrottlingSemaphore") < 0
    || (int)StringCchCopyW(TimerName, v2, L"Global\\AmiUtcThrottlingTimer2") < 0 )
  {
    LastError = 14;
    goto LABEL_28;
  }
  LastError = UtcThrottle::InitializeSecurityDesc(v4, (struct _SECURITY_DESCRIPTOR *)&v16.Owner, (struct _ACL **)&hMem);
  if ( LastError )
  {
    v5 = "Failed to initialize security descriptor [%d]";
    v6 = 123;
LABEL_7:
    AslLogCallPrintf(1, (unsigned int)"UtcThrottle::Initialize", v6, (_DWORD)v5);
    goto LABEL_28;
  }
  if ( !qword_180182400 )
  {
    qword_180182400 = (__int64)CreateEventW(0, 1, 0, 0);
    if ( !qword_180182400 )
    {
      LastError = GetLastError();
      v5 = "Failed to create event [%d]";
      v6 = 133;
      goto LABEL_7;
    }
  }
  if ( !InventoryCoreUtcThrottle )
  {
    InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, Name);
    if ( !InventoryCoreUtcThrottle )
    {
      GetLastError();
      AslLogCallPrintf(
        3,
        (unsigned int)"UtcThrottle::Initialize",
        144,
        (unsigned int)"Failed to create named semaphore [%d]");
      InventoryCoreUtcThrottle = CreateSemaphoreW(&SemaphoreAttributes, 20, 20, 0);
      if ( !InventoryCoreUtcThrottle )
      {
        LastError = GetLastError();
        v5 = "Failed to create semaphore [%d]";
        v6 = 150;
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
    UtcThrottle::SetTimer(v7);
    goto LABEL_26;
  }
  v8 = GetLastError();
  v9 = 183;
  if ( v8 == 183 )
  {
    hObject = OpenWaitableTimerW(0x100000u, 0, TimerName);
    if ( hObject )
      goto LABEL_22;
    GetLastError();
    v10 = "Failed to open named timer [%d]";
    v9 = 178;
    v11 = 1;
  }
  else
  {
    v10 = "Failed to create named timer [%d]";
    v11 = 3;
  }
  AslLogCallPrintf(v11, (unsigned int)"UtcThrottle::Initialize", v9, (_DWORD)v10);
LABEL_22:
  if ( !hObject )
  {
    hObject = CreateWaitableTimerW(&SemaphoreAttributes, 0, 0);
    if ( !hObject )
    {
      LastError = GetLastError();
      v5 = "Failed to create timer [%d]";
      v6 = 197;
      goto LABEL_7;
    }
    goto LABEL_25;
  }
LABEL_26:
  byte_180182430 = 1;
LABEL_27:
  LastError = 0;
LABEL_28:
  if ( hMem )
  {
    LocalFree(hMem);
    hMem = 0;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v15);
  return LastError;
}

```

## disassembly

```asm
0x180064688  mov     rax, rsp
0x18006468b  push    rbp
0x18006468c  lea     rbp, [rax-3C8h]
0x180064693  sub     rsp, 4C0h
0x18006469a  mov     qword ptr [rsp+4C0h+var_468.Revision], 0FFFFFFFFFFFFFFFEh
0x1800646a3  mov     [rax+8], rbx
0x1800646a7  mov     rax, cs:__security_cookie
0x1800646ae  xor     rax, rsp
0x1800646b1  mov     [rbp+3C0h+var_10], rax
0x1800646b8  xorps   xmm0, xmm0
0x1800646bb  xor     eax, eax
0x1800646bd  movups  xmmword ptr [rsp+4C0h+var_468.Owner], xmm0
0x1800646c2  movups  xmmword ptr [rsp+4C0h+var_468.Sacl], xmm0
0x1800646c7  mov     [rbp+3C0h+var_440], rax
0x1800646cb  mov     qword ptr [rsp+4C0h+SemaphoreAttributes.nLength], 18h
0x1800646d4  mov     qword ptr [rsp+4C0h+SemaphoreAttributes.bInheritHandle], rax
0x1800646d9  mov     [rsp+4C0h+hMem], rax
0x1800646de  mov     ebx, 208h
0x1800646e3  mov     r8d, ebx; Size
0x1800646e6  xor     edx, edx; Val
0x1800646e8  lea     rcx, [rbp+3C0h+Name]; void *
0x1800646ef  call    memset_0
0x1800646f4  mov     r8d, ebx; Size
0x1800646f7  xor     edx, edx; Val
0x1800646f9  lea     rcx, [rbp+3C0h+TimerName]; void *
0x1800646fd  call    memset_0
0x180064702  lea     rax, [rsp+4C0h+var_468.Owner]
0x180064707  mov     [rsp+4C0h+SemaphoreAttributes.lpSecurityDescriptor], rax
0x18006470c  lea     rdx, CriticalSection
0x180064713  lea     rcx, [rsp+4C0h+var_470]
0x180064718  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18006471d  nop
0x18006471e  cmp     cs:byte_180182430, 0
0x180064725  jnz     loc_180064959
0x18006472b  lea     r8, aGlobalAmiutcth_0; "Global\\AmiUtcThrottlingSemaphore"
0x180064732  mov     r10d, 104h
0x180064738  mov     edx, r10d; unsigned __int64
0x18006473b  lea     rcx, [rbp+3C0h+Name]; unsigned __int16 *
0x180064742  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064747  test    eax, eax
0x180064749  jns     short loc_180064755
0x18006474b  mov     ebx, 0Eh
0x180064750  jmp     loc_18006495B
0x180064755  lea     r8, aGlobalAmiutcth; "Global\\AmiUtcThrottlingTimer2"
0x18006475c  mov     rdx, r10; unsigned __int64
0x18006475f  lea     rcx, [rbp+3C0h+TimerName]; unsigned __int16 *
0x180064763  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180064768  test    eax, eax
0x18006476a  js      short loc_18006474B
0x18006476c  lea     r8, [rsp+4C0h+hMem]; struct _ACL **
0x180064771  lea     rdx, [rsp+4C0h+var_468.Owner]; struct _SECURITY_DESCRIPTOR *
0x180064776  call    ?InitializeSecurityDesc@UtcThrottle@@AEAAKAEAU_SECURITY_DESCRIPTOR@@AEAPEAU_ACL@@@Z; UtcThrottle::InitializeSecurityDesc(_SECURITY_DESCRIPTOR &,_ACL * &)
0x18006477b  mov     ebx, eax
0x18006477d  test    eax, eax
0x18006477f  jz      short loc_1800647A8
0x180064781  lea     r9, aFailedToInitia; "Failed to initialize security descripto"...
0x180064788  mov     r8d, 7Bh ; '{'
0x18006478e  mov     [rsp+20h], eax
0x180064792  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180064799  mov     ecx, 1
0x18006479e  call    AslLogCallPrintf
0x1800647a3  jmp     loc_18006495B
0x1800647a8  cmp     cs:qword_180182400, 0
0x1800647b0  jnz     short loc_1800647E7
0x1800647b2  xor     r9d, r9d; lpName
0x1800647b5  xor     r8d, r8d; bInitialState
0x1800647b8  lea     edx, [r9+1]; bManualReset
0x1800647bc  xor     ecx, ecx; lpEventAttributes
0x1800647be  call    cs:__imp_CreateEventW
0x1800647c4  mov     cs:qword_180182400, rax
0x1800647cb  test    rax, rax
0x1800647ce  jnz     short loc_1800647E7
0x1800647d0  call    cs:__imp_GetLastError
0x1800647d6  mov     ebx, eax
0x1800647d8  lea     r9, aFailedToCreate_4; "Failed to create event [%d]"
0x1800647df  mov     r8d, 85h
0x1800647e5  jmp     short loc_18006478E
0x1800647e7  cmp     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, 0; UtcThrottle InventoryCoreUtcThrottle
0x1800647ef  jnz     loc_18006487A
0x1800647f5  lea     r9, [rbp+3C0h+Name]; lpName
0x1800647fc  mov     ebx, 14h
0x180064801  mov     r8d, ebx; lMaximumCount
0x180064804  mov     edx, ebx; lInitialCount
0x180064806  lea     rcx, [rsp+4C0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x18006480b  call    cs:__imp_CreateSemaphoreW
0x180064811  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x180064818  test    rax, rax
0x18006481b  jnz     short loc_18006487A
0x18006481d  call    cs:__imp_GetLastError
0x180064823  mov     [rsp+20h], eax
0x180064827  lea     r9, aFailedToCreate_7; "Failed to create named semaphore [%d]"
0x18006482e  lea     r8d, [rbx+7Ch]
0x180064832  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180064839  lea     ecx, [rbx-11h]
0x18006483c  call    AslLogCallPrintf
0x180064841  xor     r9d, r9d; lpName
0x180064844  mov     r8d, ebx; lMaximumCount
0x180064847  mov     edx, ebx; lInitialCount
0x180064849  lea     rcx, [rsp+4C0h+SemaphoreAttributes]; lpSemaphoreAttributes
0x18006484e  call    cs:__imp_CreateSemaphoreW
0x180064854  mov     cs:?InventoryCoreUtcThrottle@@3VUtcThrottle@@A, rax; UtcThrottle InventoryCoreUtcThrottle
0x18006485b  test    rax, rax
0x18006485e  jnz     short loc_18006487A
0x180064860  call    cs:__imp_GetLastError
0x180064866  mov     ebx, eax
0x180064868  lea     r9, aFailedToCreate_6; "Failed to create semaphore [%d]"
0x18006486f  mov     r8d, 96h
0x180064875  jmp     loc_18006478E
0x18006487a  cmp     cs:hObject, 0
0x180064882  jnz     loc_180064952
0x180064888  lea     r8, [rbp+3C0h+TimerName]; lpTimerName
0x18006488c  xor     edx, edx; bManualReset
0x18006488e  lea     rcx, [rsp+4C0h+SemaphoreAttributes]; lpTimerAttributes
0x180064893  call    cs:__imp_CreateWaitableTimerW
0x180064899  mov     cs:hObject, rax
0x1800648a0  test    rax, rax
0x1800648a3  jnz     loc_18006494D
0x1800648a9  call    cs:__imp_GetLastError
0x1800648af  mov     r8d, 0B7h
0x1800648b5  cmp     eax, r8d
0x1800648b8  jnz     short loc_1800648F1
0x1800648ba  lea     r8, [rbp+3C0h+TimerName]; lpTimerName
0x1800648be  xor     edx, edx; bInheritHandle
0x1800648c0  mov     ecx, 100000h; dwDesiredAccess
0x1800648c5  call    cs:__imp_OpenWaitableTimerW
0x1800648cb  mov     cs:hObject, rax
0x1800648d2  test    rax, rax
0x1800648d5  jnz     short loc_18006490D
0x1800648d7  call    cs:__imp_GetLastError
0x1800648dd  lea     r9, aFailedToOpenNa; "Failed to open named timer [%d]"
0x1800648e4  mov     r8d, 0B2h
0x1800648ea  mov     ecx, 1
0x1800648ef  jmp     short loc_1800648FD
0x1800648f1  lea     r9, aFailedToCreate_8; "Failed to create named timer [%d]"
0x1800648f8  mov     ecx, 3
0x1800648fd  mov     [rsp+20h], eax
0x180064901  lea     rdx, aUtcthrottleIni; "UtcThrottle::Initialize"
0x180064908  call    AslLogCallPrintf
0x18006490d  cmp     cs:hObject, 0
0x180064915  jnz     short loc_180064952
0x180064917  xor     r8d, r8d; lpTimerName
0x18006491a  xor     edx, edx; bManualReset
0x18006491c  lea     rcx, [rsp+4C0h+SemaphoreAttributes]; lpTimerAttributes
0x180064921  call    cs:__imp_CreateWaitableTimerW
0x180064927  mov     cs:hObject, rax
0x18006492e  test    rax, rax
0x180064931  jnz     short loc_18006494D
0x180064933  call    cs:__imp_GetLastError
0x180064939  mov     ebx, eax
0x18006493b  lea     r9, aFailedToCreate_3; "Failed to create timer [%d]"
0x180064942  mov     r8d, 0C5h
0x180064948  jmp     loc_18006478E
0x18006494d  call    ?SetTimer@UtcThrottle@@AEAAXXZ; UtcThrottle::SetTimer(void)
0x180064952  mov     cs:byte_180182430, 1
0x180064959  xor     ebx, ebx
0x18006495b  mov     rcx, [rsp+4C0h+hMem]; hMem
0x180064960  test    rcx, rcx
0x180064963  jz      short loc_180064974
0x180064965  call    cs:__imp_LocalFree
0x18006496b  mov     [rsp+4C0h+hMem], 0
0x180064974  lea     rcx, [rsp+4C0h+var_470]
0x180064979  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x18006497e  mov     eax, ebx
0x180064980  mov     rcx, [rbp+3C0h+var_10]
0x180064987  xor     rcx, rsp; StackCookie
0x18006498a  call    __security_check_cookie
0x18006498f  mov     rbx, [rsp+4C0h+arg_0]
0x180064997  add     rsp, 4C0h
0x18006499e  pop     rbp
0x18006499f  retn
```
