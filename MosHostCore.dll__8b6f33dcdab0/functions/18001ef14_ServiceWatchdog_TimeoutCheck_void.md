# ServiceWatchdog::TimeoutCheck(void)

- ea: `0x18001ef14`
- end: `0x18001f192`
- name: `?TimeoutCheck@ServiceWatchdog@@AEAAXXZ`
- size: `638`
- prototype: `void __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001eae0`

## callees

- `0x180003410`
- `0x180003f7c`
- `0x180009d0c`
- `0x180009db4`
- `0x18001ebb8`
- `0x18001ebec`
- `0x18001ef14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef50`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ef50`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f169`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f169`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef6a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001ef6a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f03d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001f03d`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001f15f`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x18001f15f`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ef60`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x18001ef60`
- `mapsbtsvc!MapsBackgroundTransferService_TakeBitsSnapshot` at `0x18001f0fd`
- `mapsbtsvc!MapsBackgroundTransferService_TakeBitsSnapshot` at `0x18001f0fd`
- `MosStorage!MosStorageGetCurrentLocation` at `0x18001f06f`
- `MosStorage!MosStorageGetCurrentLocation` at `0x18001f06f`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ef97`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001f08b`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001ef97`
- `ZTrace_Maps!ZTraceReportIgnore` at `0x18001f08b`

## string_xrefs

- `0x18001ef8e`: `ServiceWatchdog::TimeoutCheck`
- `0x18001f082`: `ServiceWatchdog::TimeoutCheck`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ServiceWatchdog::TimeoutCheck(LPCRITICAL_SECTION lpCriticalSection)
{
  signed int LastError; // eax
  DWORD v3; // esi
  char v4; // r12
  char v5; // r13
  char v6; // al
  bool v7; // bl
  int CurrentLocation; // eax
  int OwningThread; // r14d
  unsigned __int8 v10; // r15
  OfflineMapsTelemetry *v11; // rax
  ULONG_PTR v12; // rbx
  bool v13; // [rsp+60h] [rbp-A0h]
  unsigned __int64 UnbiasedTime[3]; // [rsp+68h] [rbp-98h] BYREF
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v16; // [rsp+294h] [rbp+194h]
  unsigned int v17; // [rsp+6E0h] [rbp+5E0h]

  UnbiasedTime[0] = (unsigned __int64)lpCriticalSection[3].LockSemaphore;
  EnterCriticalSection(lpCriticalSection);
  UnbiasedTime[1] = (unsigned __int64)lpCriticalSection;
  if ( !QueryUnbiasedInterruptTime(UnbiasedTime) )
  {
    LastError = GetLastError();
    if ( LastError )
    {
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      LastError = -2143748092;
    }
    ZTraceReportIgnore(LastError, "ServiceWatchdog::TimeoutCheck", 106, lpCriticalSection);
  }
  if ( UnbiasedTime[0] - (unsigned __int64)lpCriticalSection[3].LockSemaphore > 10000
                                                                              * (unsigned __int64)LODWORD(lpCriticalSection[3].SpinCount) )
  {
    v3 = 0;
    v4 = std::_Func_class<bool,enum MapsClientType>::operator()(&lpCriticalSection[1].SpinCount, 0);
    v5 = std::_Func_class<bool,enum MapsClientType>::operator()(&lpCriticalSection[1].SpinCount, 1);
    v6 = std::_Func_class<bool,enum MapsClientType>::operator()(&lpCriticalSection[1].SpinCount, 4);
    v13 = v6;
    switch ( HIDWORD(lpCriticalSection[3].OwningThread) )
    {
      case 1:
        v3 = -2080374703;
        break;
      case 2:
        v3 = -2080374701;
        break;
      case 3:
        v3 = -2080374699;
        break;
      case 4:
        v3 = -2080374697;
        break;
      case 5:
        v3 = -2080374695;
        break;
    }
    v7 = !v4 && !v5 && !v6 && !IsDebuggerPresent();
    if ( !BYTE4(lpCriticalSection[3].SpinCount) )
    {
      memset_0(&pExceptionRecord, 0, 0x670u);
      CurrentLocation = MosStorageGetCurrentLocation((struct _STORAGE_DEVICE_DATA *)&pExceptionRecord);
      if ( CurrentLocation < 0 )
        ZTraceReportIgnore(CurrentLocation, "ServiceWatchdog::TimeoutCheck", 148, lpCriticalSection);
      OwningThread = (int)lpCriticalSection[3].OwningThread;
      v10 = pExceptionRecord.ExceptionFlags != 0;
      if ( OfflineMapsTelemetry::IsEnabled() )
      {
        v11 = OfflineMapsTelemetry::Instance();
        OfflineMapsTelemetry::MapsBrokerServiceWatchdogTimeout_(
          v11,
          v10,
          v16,
          v17,
          v7,
          v4,
          v5,
          v13,
          (struct _FILETIME)lpCriticalSection[4].DebugInfo,
          OwningThread,
          v3);
      }
      BYTE4(lpCriticalSection[3].SpinCount) = 1;
    }
    if ( v7 )
    {
      v12 = MapsBackgroundTransferService_TakeBitsSnapshot();
      if ( ((HIDWORD(lpCriticalSection[3].OwningThread) - 3) & 0xFFFFFFFD) == 0
        && (((_DWORD)v12 - 1722) & 0xFFFFFFFB) == 0 )
      {
        v3 = -2080374759;
      }
      memset_0(&pExceptionRecord, 0, sizeof(pExceptionRecord));
      pExceptionRecord.ExceptionCode = v3;
      pExceptionRecord.NumberParameters = 2;
      pExceptionRecord.ExceptionInformation[0] = v12;
      pExceptionRecord.ExceptionInformation[1] = SLODWORD(lpCriticalSection[3].OwningThread);
      RaiseFailFastException(&pExceptionRecord, 0, 1u);
    }
  }
  LeaveCriticalSection(lpCriticalSection);
}

```

## disassembly

```asm
0x18001ef14  push    rbp
0x18001ef16  push    rbx
0x18001ef17  push    rsi
0x18001ef18  push    rdi
0x18001ef19  push    r12
0x18001ef1b  push    r13
0x18001ef1d  push    r14
0x18001ef1f  push    r15
0x18001ef21  lea     rbp, [rsp-608h]
0x18001ef29  sub     rsp, 708h
0x18001ef30  mov     rax, cs:__security_cookie
0x18001ef37  xor     rax, rsp
0x18001ef3a  mov     [rbp+640h+var_50], rax
0x18001ef41  mov     rdi, rcx
0x18001ef44  mov     rax, [rcx+90h]
0x18001ef4b  mov     [rsp+740h+UnbiasedTime], rax
0x18001ef50  call    cs:__imp_EnterCriticalSection
0x18001ef56  mov     [rsp+740h+var_6D0], rdi
0x18001ef5b  lea     rcx, [rsp+740h+UnbiasedTime]; UnbiasedTime
0x18001ef60  call    cs:__imp_QueryUnbiasedInterruptTime
0x18001ef66  test    eax, eax
0x18001ef68  jnz     short loc_18001EF9D
0x18001ef6a  call    cs:__imp_GetLastError
0x18001ef70  test    eax, eax
0x18001ef72  jz      short loc_18001EF80
0x18001ef74  jle     short loc_18001EF85
0x18001ef76  movzx   eax, ax
0x18001ef79  or      eax, 80070000h
0x18001ef7e  jmp     short loc_18001EF85
0x18001ef80  mov     eax, 80390004h
0x18001ef85  mov     r9, rdi
0x18001ef88  mov     r8d, 6Ah ; 'j'
0x18001ef8e  lea     rdx, aServicewatchdo_0; "ServiceWatchdog::TimeoutCheck"
0x18001ef95  mov     ecx, eax
0x18001ef97  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001ef9d  mov     eax, [rdi+98h]
0x18001efa3  imul    rcx, rax, 2710h
0x18001efaa  mov     rax, [rsp+740h+UnbiasedTime]
0x18001efaf  sub     rax, [rdi+90h]
0x18001efb6  cmp     rax, rcx
0x18001efb9  jbe     loc_18001F166
0x18001efbf  xor     esi, esi
0x18001efc1  lea     rbx, [rdi+48h]
0x18001efc5  xor     edx, edx
0x18001efc7  mov     rcx, rbx
0x18001efca  call    ??R?$_Func_class@_NW4MapsClientType@@@std@@QEBA_NW4MapsClientType@@@Z; std::_Func_class<bool,MapsClientType>::operator()(MapsClientType)
0x18001efcf  mov     r12b, al
0x18001efd2  lea     edx, [rsi+1]
0x18001efd5  mov     rcx, rbx
0x18001efd8  call    ??R?$_Func_class@_NW4MapsClientType@@@std@@QEBA_NW4MapsClientType@@@Z; std::_Func_class<bool,MapsClientType>::operator()(MapsClientType)
0x18001efdd  mov     r13b, al
0x18001efe0  lea     edx, [rsi+4]
0x18001efe3  mov     rcx, rbx
0x18001efe6  call    ??R?$_Func_class@_NW4MapsClientType@@@std@@QEBA_NW4MapsClientType@@@Z; std::_Func_class<bool,MapsClientType>::operator()(MapsClientType)
0x18001efeb  mov     [rsp+740h+var_6E0], al
0x18001efef  mov     edx, [rdi+8Ch]
0x18001eff5  sub     edx, 1
0x18001eff8  jz      short loc_18001F02A
0x18001effa  sub     edx, 1
0x18001effd  jz      short loc_18001F023
0x18001efff  sub     edx, 1
0x18001f002  jz      short loc_18001F01C
0x18001f004  sub     edx, 1
0x18001f007  jz      short loc_18001F015
0x18001f009  cmp     edx, 1
0x18001f00c  jnz     short loc_18001F02F
0x18001f00e  mov     esi, 84000059h
0x18001f013  jmp     short loc_18001F02F
0x18001f015  mov     esi, 84000057h
0x18001f01a  jmp     short loc_18001F02F
0x18001f01c  mov     esi, 84000055h
0x18001f021  jmp     short loc_18001F02F
0x18001f023  mov     esi, 84000053h
0x18001f028  jmp     short loc_18001F02F
0x18001f02a  mov     esi, 84000051h
0x18001f02f  test    r12b, r12b
0x18001f032  jnz     short loc_18001F04B
0x18001f034  test    r13b, r13b
0x18001f037  jnz     short loc_18001F04B
0x18001f039  test    al, al
0x18001f03b  jnz     short loc_18001F04B
0x18001f03d  call    cs:__imp_IsDebuggerPresent
0x18001f043  test    eax, eax
0x18001f045  jnz     short loc_18001F04B
0x18001f047  mov     bl, 1
0x18001f049  jmp     short loc_18001F04D
0x18001f04b  xor     bl, bl
0x18001f04d  cmp     byte ptr [rdi+9Ch], 0
0x18001f054  jnz     loc_18001F0F9
0x18001f05a  xor     edx, edx; Val
0x18001f05c  mov     r8d, 670h; Size
0x18001f062  lea     rcx, [rbp+640h+pExceptionRecord]; void *
0x18001f066  call    memset_0
0x18001f06b  lea     rcx, [rbp+640h+pExceptionRecord]
0x18001f06f  call    cs:__imp_?MosStorageGetCurrentLocation@@YAJPEAU_STORAGE_DEVICE_DATA@@@Z; MosStorageGetCurrentLocation(_STORAGE_DEVICE_DATA *)
0x18001f075  test    eax, eax
0x18001f077  jns     short loc_18001F091
0x18001f079  mov     r9, rdi
0x18001f07c  mov     r8d, 94h
0x18001f082  lea     rdx, aServicewatchdo_0; "ServiceWatchdog::TimeoutCheck"
0x18001f089  mov     ecx, eax
0x18001f08b  call    cs:__imp_?ZTraceReportIgnore@@YAXHPEBDHPEBX@Z; ZTraceReportIgnore(int,char const *,int,void const *)
0x18001f091  mov     r14d, [rdi+88h]
0x18001f098  cmp     [rbp+640h+pExceptionRecord.ExceptionFlags], 0
0x18001f09c  setnz   r15b
0x18001f0a0  call    ?IsEnabled@OfflineMapsTelemetry@@SA_NE_K@Z; OfflineMapsTelemetry::IsEnabled(uchar,unsigned __int64)
0x18001f0a5  test    al, al
0x18001f0a7  jz      short loc_18001F0F2
0x18001f0a9  call    ?Instance@OfflineMapsTelemetry@@KAPEAV1@XZ; OfflineMapsTelemetry::Instance(void)
0x18001f0ae  mov     rcx, [rdi+0A0h]
0x18001f0b5  mov     [rsp+740h+var_6F0], esi; int
0x18001f0b9  mov     [rsp+740h+var_6F8], r14d; int
0x18001f0be  mov     qword ptr [rsp+740h+var_700.dwLowDateTime], rcx; struct _FILETIME
0x18001f0c3  mov     cl, [rsp+740h+var_6E0]
0x18001f0c7  mov     [rsp+740h+var_708], cl; bool
0x18001f0cb  mov     [rsp+740h+var_710], r13b; bool
0x18001f0d0  mov     [rsp+740h+var_718], r12b; bool
0x18001f0d5  mov     [rsp+740h+var_720], bl; bool
0x18001f0d9  mov     r9d, [rbp+640h+var_60]; unsigned int
0x18001f0e0  mov     r8d, [rbp+640h+var_4AC]; unsigned int
0x18001f0e7  mov     dl, r15b; bool
0x18001f0ea  mov     rcx, rax; this
0x18001f0ed  call    ?MapsBrokerServiceWatchdogTimeout_@OfflineMapsTelemetry@@QEAAX_NII0000U_FILETIME@@HJ@Z; OfflineMapsTelemetry::MapsBrokerServiceWatchdogTimeout_(bool,uint,uint,bool,bool,bool,bool,_FILETIME,int,long)
0x18001f0f2  mov     byte ptr [rdi+9Ch], 1
0x18001f0f9  test    bl, bl
0x18001f0fb  jz      short loc_18001F166
0x18001f0fd  call    cs:__imp_?MapsBackgroundTransferService_TakeBitsSnapshot@@YAJXZ; MapsBackgroundTransferService_TakeBitsSnapshot(void)
0x18001f103  movsxd  rbx, eax
0x18001f106  mov     ecx, [rdi+8Ch]
0x18001f10c  sub     ecx, 3
0x18001f10f  test    ecx, 0FFFFFFFDh
0x18001f115  jnz     short loc_18001F12B
0x18001f117  lea     ecx, [rbx-6BAh]
0x18001f11d  test    ecx, 0FFFFFFFBh
0x18001f123  mov     eax, 84000019h
0x18001f128  cmovz   esi, eax
0x18001f12b  xor     edx, edx; Val
0x18001f12d  mov     r8d, 98h; Size
0x18001f133  lea     rcx, [rbp+640h+pExceptionRecord]; void *
0x18001f137  call    memset_0
0x18001f13c  mov     [rbp+640h+pExceptionRecord.ExceptionCode], esi
0x18001f13f  mov     [rbp+640h+pExceptionRecord.NumberParameters], 2
0x18001f146  mov     [rbp+640h+pExceptionRecord.ExceptionInformation], rbx
0x18001f14a  movsxd  rax, dword ptr [rdi+88h]
0x18001f151  mov     [rbp+640h+pExceptionRecord.ExceptionInformation+8], rax
0x18001f155  xor     edx, edx; pContextRecord
0x18001f157  lea     r8d, [rdx+1]; dwFlags
0x18001f15b  lea     rcx, [rbp+640h+pExceptionRecord]; pExceptionRecord
0x18001f15f  call    cs:__imp_RaiseFailFastException
0x18001f165  nop
0x18001f166  mov     rcx, rdi; lpCriticalSection
0x18001f169  call    cs:__imp_LeaveCriticalSection
0x18001f16f  mov     rcx, [rbp+640h+var_50]
0x18001f176  xor     rcx, rsp; StackCookie
0x18001f179  call    __security_check_cookie
0x18001f17e  add     rsp, 708h
0x18001f185  pop     r15
0x18001f187  pop     r14
0x18001f189  pop     r13
0x18001f18b  pop     r12
0x18001f18d  pop     rdi
0x18001f18e  pop     rsi
0x18001f18f  pop     rbx
0x18001f190  pop     rbp
0x18001f191  retn
```
