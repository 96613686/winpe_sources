# MpWatchDog::CWdResController::MonitorJob(void)

- ea: `0x140098270`
- end: `0x140098989`
- name: `?MonitorJob@CWdResController@MpWatchDog@@AEAAKXZ`
- size: `1817`
- prototype: `unsigned int __fastcall(MpWatchDog::CWdResController *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140098990`

## callees

- `0x1400014e8`
- `0x14000175c`
- `0x1400177d4`
- `0x1400177dc`
- `0x14003a5c0`
- `0x14007d1e0`
- `0x14007d210`
- `0x140097808`
- `0x140098270`
- `0x14009929c`
- `0x140166990`

## import_xrefs

- `KERNEL32!K32GetProcessMemoryInfo` at `0x1400985ea`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1400985ea`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400982f7`
- `KERNEL32!GetQueuedCompletionStatus` at `0x1400982f7`
- `KERNEL32!QueryInformationJobObject` at `0x140098390`
- `KERNEL32!QueryInformationJobObject` at `0x140098390`
- `KERNEL32!GetCurrentProcess` at `0x1400985d7`
- `KERNEL32!GetCurrentProcess` at `0x1400985d7`
- `KERNEL32!GetLastError` at `0x140098690`
- `KERNEL32!GetLastError` at `0x14009891b`
- `KERNEL32!GetLastError` at `0x140098690`
- `KERNEL32!GetLastError` at `0x14009891b`

## pseudocode

```c
__int64 __fastcall MpWatchDog::CWdResController::MonitorJob(MpWatchDog::CWdResController *this)
{
  void *v2; // rcx
  __int64 v3; // r9
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  char v5; // di
  char v6; // si
  __int64 v7; // rcx
  HANDLE CurrentProcess; // rax
  unsigned __int64 v9; // r8
  signed int LastError; // eax
  struct _RTL_CRITICAL_SECTION *v11; // rdi
  __int64 v12; // rcx
  __int64 v13; // rdx
  signed int v14; // eax
  bool v15; // sf
  int v17; // [rsp+ACh] [rbp-7Ch] BYREF
  int v18; // [rsp+B0h] [rbp-78h] BYREF
  int v19; // [rsp+B4h] [rbp-74h] BYREF
  int v20; // [rsp+B8h] [rbp-70h] BYREF
  int v21; // [rsp+BCh] [rbp-6Ch] BYREF
  int v22; // [rsp+C0h] [rbp-68h] BYREF
  __int64 v23; // [rsp+C4h] [rbp-64h] BYREF
  __int64 v24; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v25; // [rsp+D8h] [rbp-50h] BYREF
  __int64 v26; // [rsp+E0h] [rbp-48h] BYREF
  __int64 v27; // [rsp+E8h] [rbp-40h] BYREF
  __int64 v28; // [rsp+F0h] [rbp-38h] BYREF
  __int64 v29; // [rsp+F8h] [rbp-30h] BYREF
  __int64 v30; // [rsp+100h] [rbp-28h] BYREF
  __int64 v31; // [rsp+108h] [rbp-20h] BYREF
  LPOVERLAPPED Overlapped; // [rsp+110h] [rbp-18h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+118h] [rbp-10h] BYREF
  unsigned __int64 CompletionKey; // [rsp+120h] [rbp-8h] BYREF
  _BYTE ppsmemCounters[80]; // [rsp+128h] [rbp+0h] BYREF
  _DWORD JobObjectInformation[20]; // [rsp+178h] [rbp+50h] BYREF

  if ( *((_BYTE *)this + 64) )
    return 0;
  while ( 1 )
  {
    v2 = *(void **)this;
    NumberOfBytesTransferred = 0;
    CompletionKey = 0;
    Overlapped = 0;
    if ( !GetQueuedCompletionStatus(v2, &NumberOfBytesTransferred, &CompletionKey, &Overlapped, 0xFFFFFFFF) )
      break;
    switch ( NumberOfBytesTransferred )
    {
      case 6u:
        ++dword_1401E7354;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_39;
        v13 = 30;
LABEL_69:
        WPP_SF_d(*(_QWORD *)(v12 + 16), v13, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids, (unsigned int)Overlapped);
        goto LABEL_39;
      case 7u:
        --dword_1401E7354;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_39;
        v13 = 31;
        goto LABEL_69;
      case 8u:
        --dword_1401E7354;
        v12 = WPP_GLOBAL_Control;
        if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) == 0 )
          goto LABEL_39;
        v13 = 32;
        goto LABEL_69;
    }
    if ( NumberOfBytesTransferred != 9 )
    {
      if ( NumberOfBytesTransferred == 11 )
      {
        memset(JobObjectInformation, 0, sizeof(JobObjectInformation));
        if ( QueryInformationJobObject(
               *((HANDLE *)this + 1),
               MaxJobObjectInfoClass|JobObjectBasicAccountingInformation,
               JobObjectInformation,
               0x50u,
               0)
          && (JobObjectInformation[1] & 0x40000) != 0 )
        {
          v3 = (unsigned int)(*((_DWORD *)this + 17) + 1);
          *((_DWORD *)this + 17) = v3;
          if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
            WPP_SF_d(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 29, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids, v3);
          v4 = g_pcsAsimovLock;
          if ( g_pcsAsimovLock )
          {
            Mtxlock(g_pcsAsimovLock);
            if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
              && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
              && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) )
            {
              LODWORD(v24) = *((_DWORD *)this + 8);
              v31 = 0x2000000;
              v17 = *((_DWORD *)g_aAsimov + 18);
              v18 = *((_DWORD *)g_aAsimov + 17);
              v19 = *((_DWORD *)g_aAsimov + 16);
              v20 = *((unsigned __int8 *)g_aAsimov + 60);
              v21 = *((unsigned __int8 *)g_aAsimov + 59);
              v22 = *((unsigned __int8 *)g_aAsimov + 58);
              LODWORD(v23) = *((unsigned __int8 *)g_aAsimov + 57);
              HIDWORD(v23) = *((unsigned __int8 *)g_aAsimov + 56);
              v25 = *((_QWORD *)g_aAsimov + 6);
              v26 = *((_QWORD *)g_aAsimov + 5);
              v27 = *((_QWORD *)g_aAsimov + 4);
              v28 = *((_QWORD *)g_aAsimov + 3);
              v29 = *((_QWORD *)g_aAsimov + 2);
              v30 = *((_QWORD *)g_aAsimov + 1);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                g_hMpAsimovProvider,
                (int)&byte_1401B944B,
                (__int64)&v31,
                (__int64)&v30,
                (__int64)&v29,
                (__int64)&v28,
                (__int64)&v27,
                (__int64)&v26,
                (__int64)&v25,
                (__int64)&v23 + 4,
                (__int64)&v23,
                (__int64)&v22,
                (__int64)&v21,
                (__int64)&v20,
                (__int64)&v19,
                (__int64)&v18,
                (__int64)&v17,
                (__int64)&v24);
            }
            Mtxunlock(v4);
          }
          if ( *((_DWORD *)this + 17) > 0x32u )
            MpWatchDog::CWdResController::DisableNotifications(this, 0x40000u);
        }
      }
      else if ( NumberOfBytesTransferred == -1 )
      {
        if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 0x10) != 0 )
        {
          WPP_SF_(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 38, &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids);
        }
        *((_BYTE *)this + 64) = 1;
      }
      goto LABEL_39;
    }
    v5 = 0;
    v6 = *((_BYTE *)MpWatchDog::gMpWdConfigManager + 13);
    if ( dword_1401E7354 != 1 )
    {
      v5 = 1;
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) == 0 )
        goto LABEL_31;
      WPP_SF_d(
        *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
        33,
        &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
        (unsigned int)dword_1401E7354);
    }
    v7 = WPP_GLOBAL_Control;
LABEL_31:
    if ( v6 || v5 )
      goto LABEL_50;
    memset(ppsmemCounters, 0, sizeof(ppsmemCounters));
    *(_DWORD *)ppsmemCounters = 80;
    CurrentProcess = GetCurrentProcess();
    if ( !K32GetProcessMemoryInfo(CurrentProcess, (PPROCESS_MEMORY_COUNTERS)ppsmemCounters, 0x50u) )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_d(
            *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
            36,
            &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
            (unsigned int)LastError);
LABEL_49:
          v7 = WPP_GLOBAL_Control;
        }
LABEL_50:
        if ( (_UNKNOWN *)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
          WPP_SF_d(
            *(_QWORD *)(v7 + 16),
            37,
            &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
            *((unsigned int *)this + 7));
      }
LABEL_53:
      v11 = g_pcsAsimovLock;
      if ( g_pcsAsimovLock )
      {
        Mtxlock(g_pcsAsimovLock);
        if ( **(_DWORD **)&g_hMpAsimovProvider > 5u
          && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 16LL) & 0x400000000000LL) != 0
          && (*(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) & 0x400000000000LL) == *(_QWORD *)(*(_QWORD *)&g_hMpAsimovProvider + 24LL) )
        {
          v31 = (unsigned __int64)*((unsigned int *)this + 7) << 20;
          v23 = *(_QWORD *)((char *)g_aAsimov + 68);
          v22 = *((_DWORD *)g_aAsimov + 16);
          v21 = *((unsigned __int8 *)g_aAsimov + 60);
          v20 = *((unsigned __int8 *)g_aAsimov + 59);
          v19 = *((unsigned __int8 *)g_aAsimov + 58);
          v18 = *((unsigned __int8 *)g_aAsimov + 57);
          v17 = *((unsigned __int8 *)g_aAsimov + 56);
          v30 = *((_QWORD *)g_aAsimov + 6);
          v29 = *((_QWORD *)g_aAsimov + 5);
          v28 = *((_QWORD *)g_aAsimov + 4);
          v27 = *((_QWORD *)g_aAsimov + 3);
          v26 = *((_QWORD *)g_aAsimov + 2);
          v25 = *((_QWORD *)g_aAsimov + 1);
          v24 = 0x2000000;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
            g_hMpAsimovProvider,
            (int)&byte_1401B9347,
            (__int64)&v24,
            (__int64)&v25,
            (__int64)&v26,
            (__int64)&v27,
            (__int64)&v28,
            (__int64)&v29,
            (__int64)&v30,
            (__int64)&v17,
            (__int64)&v18,
            (__int64)&v19,
            (__int64)&v20,
            (__int64)&v21,
            (__int64)&v22,
            (__int64)&v23,
            (__int64)&v23 + 4,
            (__int64)&v31);
        }
        Mtxunlock(v11);
      }
      MpWatchDog::CWdResController::DisableNotifications(this, 0x200u);
      __fastfail(7u);
    }
    v9 = *((unsigned int *)this + 7);
    if ( *(_QWORD *)&ppsmemCounters[16] >> 20 >= v9 || *(_QWORD *)&ppsmemCounters[72] >> 20 >= v9 )
    {
      v7 = WPP_GLOBAL_Control;
      if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
        {
          WPP_SF_III(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 34);
          goto LABEL_49;
        }
        goto LABEL_50;
      }
      goto LABEL_53;
    }
    if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 2) != 0 )
    {
      _mm_lfence();
      WPP_SF_III(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 35);
    }
LABEL_39:
    if ( *((_BYTE *)this + 64) )
      return 0;
  }
  if ( Overlapped )
    goto LABEL_39;
  v14 = GetLastError();
  v15 = v14 < 0;
  if ( v14 > 0 )
  {
    v14 = (unsigned __int16)v14 | 0x80070000;
    v15 = v14 < 0;
  }
  if ( !v15 )
    goto LABEL_39;
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 1) != 0 )
    WPP_SF_d(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      39,
      &WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids,
      (unsigned int)v14);
  return 0;
}

```

## disassembly

```asm
0x140098270  mov     rax, rsp
0x140098273  mov     [rax+10h], rbx
0x140098277  mov     [rax+18h], rsi
0x14009827b  mov     [rax+20h], rdi
0x14009827f  push    rbp
0x140098280  push    r13
0x140098282  push    r15
0x140098284  lea     rbp, [rax-0C8h]
0x14009828b  sub     rsp, 1D0h
0x140098292  mov     rax, cs:__security_cookie
0x140098299  xor     rax, rsp
0x14009829c  mov     [rbp+0C0h+var_20], rax
0x1400982a3  mov     al, [rcx+40h]
0x1400982a6  mov     rbx, rcx
0x1400982a9  test    al, al
0x1400982ab  jnz     loc_14009895B
0x1400982b1  lea     r15, WPP_GLOBAL_Control
0x1400982b8  mov     rsi, 400000000000h
0x1400982c2  lea     r13, WPP_bec90da150e13ee7c70ca1df805af0de_Traceguids
0x1400982c9  mov     rcx, [rbx]; CompletionPort
0x1400982cc  lea     r9, [rbp+0C0h+Overlapped]; lpOverlapped
0x1400982d0  lea     r8, [rbp+0C0h+CompletionKey]; lpCompletionKey
0x1400982d4  mov     [rbp+0C0h+NumberOfBytesTransferred], 0
0x1400982db  lea     rdx, [rbp+0C0h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x1400982df  mov     [rbp+0C0h+CompletionKey], 0
0x1400982e7  mov     [rbp+0C0h+Overlapped], 0
0x1400982ef  mov     [rsp+1E0h+dwMilliseconds], 0FFFFFFFFh; dwMilliseconds
0x1400982f7  call    cs:__imp_GetQueuedCompletionStatus
0x1400982fd  test    eax, eax
0x1400982ff  jz      loc_140098910
0x140098305  mov     eax, [rbp+0C0h+NumberOfBytesTransferred]
0x140098308  cmp     eax, 6
0x14009830b  jz      loc_1400988D6
0x140098311  cmp     eax, 7
0x140098314  jz      loc_1400988AF
0x14009831a  cmp     eax, 8
0x14009831d  jz      loc_140098888
0x140098323  cmp     eax, 9
0x140098326  jz      loc_140098566
0x14009832c  cmp     eax, 0Bh
0x14009832f  jz      short loc_140098366
0x140098331  cmp     eax, 0FFFFFFFFh
0x140098334  jnz     loc_140098654
0x14009833a  mov     rcx, cs:WPP_GLOBAL_Control
0x140098341  cmp     rcx, r15
0x140098344  jz      short loc_14009835D
0x140098346  test    byte ptr [rcx+1Ch], 10h
0x14009834a  jz      short loc_14009835D
0x14009834c  mov     rcx, [rcx+10h]
0x140098350  mov     edx, 26h ; '&'
0x140098355  mov     r8, r13
0x140098358  call    WPP_SF_
0x14009835d  mov     byte ptr [rbx+40h], 1
0x140098361  jmp     loc_140098654
0x140098366  xor     edx, edx; Val
0x140098368  lea     rcx, [rbp+0C0h+JobObjectInformation]; void *
0x14009836c  lea     r8d, [rdx+50h]; Size
0x140098370  call    memset
0x140098375  mov     rcx, [rbx+8]; hJob
0x140098379  lea     r8, [rbp+0C0h+JobObjectInformation]; lpJobObjectInformation
0x14009837d  mov     r9d, 50h ; 'P'; cbJobObjectInformationLength
0x140098383  mov     qword ptr [rsp+1E0h+dwMilliseconds], 0; lpReturnLength
0x14009838c  lea     edx, [r9-43h]; JobObjectInformationClass
0x140098390  call    cs:__imp_QueryInformationJobObject
0x140098396  test    eax, eax
0x140098398  jz      loc_140098654
0x14009839e  test    [rbp+0C0h+var_6C], 40000h
0x1400983a5  jz      loc_140098654
0x1400983ab  mov     r9d, [rbx+44h]
0x1400983af  inc     r9d
0x1400983b2  mov     [rbx+44h], r9d
0x1400983b6  mov     rcx, cs:WPP_GLOBAL_Control
0x1400983bd  cmp     rcx, r15
0x1400983c0  jz      short loc_1400983D9
0x1400983c2  test    byte ptr [rcx+1Ch], 2
0x1400983c6  jz      short loc_1400983D9
0x1400983c8  mov     rcx, [rcx+10h]
0x1400983cc  mov     edx, 1Dh
0x1400983d1  mov     r8, r13
0x1400983d4  call    WPP_SF_d
0x1400983d9  mov     rdi, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x1400983e0  test    rdi, rdi
0x1400983e3  jz      loc_14009854A
0x1400983e9  mov     rcx, rdi; lpCriticalSection
0x1400983ec  call    _Mtxlock
0x1400983f1  mov     r8, cs:g_hMpAsimovProvider
0x1400983f8  cmp     dword ptr [r8], 5
0x1400983fc  jbe     loc_140098542
0x140098402  test    [r8+10h], rsi
0x140098406  jz      loc_140098542
0x14009840c  mov     rax, [r8+18h]
0x140098410  and     rax, rsi
0x140098413  cmp     rax, [r8+18h]
0x140098417  jnz     loc_140098542
0x14009841d  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x140098424  lea     rdx, byte_1401B944B; int
0x14009842b  mov     eax, [rbx+20h]
0x14009842e  mov     dword ptr [rbp+0C0h+var_118], eax
0x140098431  mov     [rbp+0C0h+var_E0], 2000000h
0x140098439  mov     eax, [rcx+48h]
0x14009843c  mov     dword ptr [rbp+0C0h+var_13C], eax
0x14009843f  mov     eax, [rcx+44h]
0x140098442  mov     dword ptr [rbp+0C0h+var_13C+4], eax
0x140098445  mov     eax, [rcx+40h]
0x140098448  mov     dword ptr [rbp+0C0h+var_134], eax
0x14009844b  movzx   eax, byte ptr [rcx+3Ch]
0x14009844f  mov     dword ptr [rbp+0C0h+var_134+4], eax
0x140098452  movzx   eax, byte ptr [rcx+3Bh]
0x140098456  mov     dword ptr [rbp+0C0h+var_12C], eax
0x140098459  movzx   eax, byte ptr [rcx+3Ah]
0x14009845d  mov     dword ptr [rbp+0C0h+var_12C+4], eax
0x140098460  movzx   eax, byte ptr [rcx+39h]
0x140098464  mov     dword ptr [rbp+0C0h+var_124], eax
0x140098467  movzx   eax, byte ptr [rcx+38h]
0x14009846b  mov     dword ptr [rbp+0C0h+var_124+4], eax
0x14009846e  mov     rax, [rcx+30h]
0x140098472  mov     [rbp+0C0h+var_110], rax
0x140098476  mov     rax, [rcx+28h]
0x14009847a  mov     [rbp+0C0h+var_108], rax
0x14009847e  mov     rax, [rcx+20h]
0x140098482  mov     [rbp+0C0h+var_100], rax
0x140098486  mov     rax, [rcx+18h]
0x14009848a  mov     [rbp+0C0h+var_F8], rax
0x14009848e  mov     rax, [rcx+10h]
0x140098492  mov     [rbp+0C0h+var_F0], rax
0x140098496  mov     rax, [rcx+8]
0x14009849a  mov     rcx, r8; int
0x14009849d  mov     [rbp+0C0h+var_E8], rax
0x1400984a1  lea     rax, [rbp+0C0h+var_118]
0x1400984a5  mov     [rsp+1E0h+var_148], rax; __int64
0x1400984ad  lea     rax, [rbp+0C0h+var_13C]
0x1400984b1  mov     [rsp+1E0h+var_150], rax; __int64
0x1400984b9  lea     rax, [rbp+0C0h+var_13C+4]
0x1400984bd  mov     [rsp+1E0h+var_158], rax; __int64
0x1400984c5  lea     rax, [rbp+0C0h+var_134]
0x1400984c9  mov     [rsp+1E0h+var_160], rax; __int64
0x1400984d1  lea     rax, [rbp+0C0h+var_134+4]
0x1400984d5  mov     [rsp+1E0h+var_168], rax; __int64
0x1400984da  lea     rax, [rbp+0C0h+var_12C]
0x1400984de  mov     [rsp+1E0h+var_170], rax; __int64
0x1400984e3  lea     rax, [rbp+0C0h+var_12C+4]
0x1400984e7  mov     [rsp+1E0h+var_178], rax; __int64
0x1400984ec  lea     rax, [rbp+0C0h+var_124]
0x1400984f0  mov     [rsp+1E0h+var_180], rax; __int64
0x1400984f5  lea     rax, [rbp+0C0h+var_124+4]
0x1400984f9  mov     [rsp+1E0h+var_188], rax; __int64
0x1400984fe  lea     rax, [rbp+0C0h+var_110]
0x140098502  mov     [rsp+1E0h+var_190], rax; __int64
0x140098507  lea     rax, [rbp+0C0h+var_108]
0x14009850b  mov     [rsp+1E0h+var_198], rax; __int64
0x140098510  lea     rax, [rbp+0C0h+var_100]
0x140098514  mov     [rsp+1E0h+var_1A0], rax; __int64
0x140098519  lea     rax, [rbp+0C0h+var_F8]
0x14009851d  mov     [rsp+1E0h+var_1A8], rax; __int64
0x140098522  lea     rax, [rbp+0C0h+var_F0]
0x140098526  mov     [rsp+1E0h+var_1B0], rax; __int64
0x14009852b  lea     rax, [rbp+0C0h+var_E8]
0x14009852f  mov     [rsp+1E0h+var_1B8], rax; __int64
0x140098534  lea     rax, [rbp+0C0h+var_E0]
0x140098538  mov     qword ptr [rsp+1E0h+dwMilliseconds], rax; __int64
0x14009853d  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@_W@@U2@U2@U2@U2@U2@U?$_tlgWrapperByVal@$03@@U3@U3@U3@U3@U3@U3@U3@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@_W@@44444AEBU?$_tlgWrapperByVal@$03@@55555555@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x140098542  mov     rcx, rdi; lpCriticalSection
0x140098545  call    _Mtxunlock
0x14009854a  cmp     dword ptr [rbx+44h], 32h ; '2'
0x14009854e  jbe     loc_140098654
0x140098554  mov     edx, 40000h; unsigned int
0x140098559  mov     rcx, rbx; this
0x14009855c  call    ?DisableNotifications@CWdResController@MpWatchDog@@AEAAXK@Z; MpWatchDog::CWdResController::DisableNotifications(ulong)
0x140098561  jmp     loc_140098654
0x140098566  mov     rax, cs:?gMpWdConfigManager@MpWatchDog@@3PEAVWdConfigManager@1@EA; MpWatchDog::WdConfigManager * MpWatchDog::gMpWdConfigManager
0x14009856d  xor     dil, dil
0x140098570  mov     sil, [rax+0Dh]
0x140098574  nop
0x140098575  mov     r9d, cs:dword_1401E7354
0x14009857c  cmp     r9d, 1
0x140098580  jz      short loc_1400985A8
0x140098582  mov     dil, 1
0x140098585  mov     rcx, cs:WPP_GLOBAL_Control
0x14009858c  cmp     rcx, r15
0x14009858f  jz      short loc_1400985AF
0x140098591  test    [rcx+1Ch], dil
0x140098595  jz      short loc_1400985AF
0x140098597  mov     rcx, [rcx+10h]
0x14009859b  mov     edx, 21h ; '!'
0x1400985a0  mov     r8, r13
0x1400985a3  call    WPP_SF_d
0x1400985a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400985af  test    sil, sil
0x1400985b2  jnz     loc_1400986CF
0x1400985b8  test    dil, dil
0x1400985bb  jnz     loc_1400986CF
0x1400985c1  xor     edx, edx; Val
0x1400985c3  lea     rcx, [rbp+0C0h+ppsmemCounters]; void *
0x1400985c7  lea     r8d, [rdx+50h]; Size
0x1400985cb  call    memset
0x1400985d0  mov     [rbp+0C0h+ppsmemCounters.cb], 50h ; 'P'
0x1400985d7  call    cs:__imp_GetCurrentProcess
0x1400985dd  mov     r8d, 50h ; 'P'; cb
0x1400985e3  lea     rdx, [rbp+0C0h+ppsmemCounters]; ppsmemCounters
0x1400985e7  mov     rcx, rax; Process
0x1400985ea  call    cs:__imp_K32GetProcessMemoryInfo
0x1400985f0  test    eax, eax
0x1400985f2  jz      loc_140098690
0x1400985f8  mov     r9, [rbp+0C0h+ppsmemCounters.WorkingSetSize]
0x1400985fc  mov     rax, [rbp+0C0h+var_78]
0x140098600  mov     r8d, [rbx+1Ch]
0x140098604  shr     r9, 14h
0x140098608  shr     rax, 14h
0x14009860c  cmp     r9, r8
0x14009860f  jnb     short loc_140098664
0x140098611  cmp     rax, r8
0x140098614  jnb     short loc_140098664
0x140098616  mov     rcx, cs:WPP_GLOBAL_Control
0x14009861d  cmp     rcx, r15
0x140098620  jz      short loc_14009864A
0x140098622  test    byte ptr [rcx+1Ch], 2
0x140098626  jz      short loc_14009864A
0x140098628  lfence
0x14009862b  mov     rcx, cs:WPP_GLOBAL_Control
0x140098632  mov     edx, 23h ; '#'
0x140098637  mov     [rsp+1E0h+var_1B8], r8
0x14009863c  mov     qword ptr [rsp+1E0h+dwMilliseconds], rax
0x140098641  mov     rcx, [rcx+10h]
0x140098645  call    WPP_SF_III
0x14009864a  mov     rsi, 400000000000h
0x140098654  mov     al, [rbx+40h]
0x140098657  test    al, al
0x140098659  jz      loc_1400982C9
0x14009865f  jmp     loc_14009895B
0x140098664  mov     rcx, cs:WPP_GLOBAL_Control
0x14009866b  cmp     rcx, r15
0x14009866e  jz      short loc_1400986EF
0x140098670  test    byte ptr [rcx+1Ch], 1
0x140098674  jz      short loc_1400986CF
0x140098676  mov     rcx, [rcx+10h]
0x14009867a  mov     edx, 22h ; '"'
0x14009867f  mov     [rsp+1E0h+var_1B8], r8
0x140098684  mov     qword ptr [rsp+1E0h+dwMilliseconds], rax
0x140098689  call    WPP_SF_III
0x14009868e  jmp     short loc_1400986C8
0x140098690  call    cs:__imp_GetLastError
0x140098696  test    eax, eax
0x140098698  jle     short loc_1400986A2
0x14009869a  movzx   eax, ax
0x14009869d  or      eax, 80070000h
0x1400986a2  mov     rcx, cs:WPP_GLOBAL_Control
0x1400986a9  cmp     rcx, r15
0x1400986ac  jz      short loc_1400986EF
0x1400986ae  test    byte ptr [rcx+1Ch], 1
0x1400986b2  jz      short loc_1400986CF
0x1400986b4  mov     rcx, [rcx+10h]
0x1400986b8  mov     edx, 24h ; '$'
0x1400986bd  mov     r9d, eax
0x1400986c0  mov     r8, r13
0x1400986c3  call    WPP_SF_d
0x1400986c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400986cf  cmp     rcx, r15
0x1400986d2  jz      short loc_1400986EF
0x1400986d4  test    byte ptr [rcx+1Ch], 2
0x1400986d8  jz      short loc_1400986EF
0x1400986da  mov     r9d, [rbx+1Ch]
0x1400986de  mov     edx, 25h ; '%'
0x1400986e3  mov     rcx, [rcx+10h]
0x1400986e7  mov     r8, r13
0x1400986ea  call    WPP_SF_d
0x1400986ef  mov     rdi, cs:?g_pcsAsimovLock@@3PEAVCMpCriticalSection@CommonUtil@@EA; CommonUtil::CMpCriticalSection * g_pcsAsimovLock
0x1400986f6  test    rdi, rdi
0x1400986f9  jz      loc_14009886F
0x1400986ff  mov     rcx, rdi; lpCriticalSection
0x140098702  call    _Mtxlock
0x140098707  mov     r8, cs:g_hMpAsimovProvider
0x14009870e  cmp     dword ptr [r8], 5
0x140098712  jbe     loc_140098867
0x140098718  mov     rcx, 400000000000h
0x140098722  test    [r8+10h], rcx
0x140098726  jz      loc_140098867
0x14009872c  mov     rax, [r8+18h]
0x140098730  and     rax, rcx
0x140098733  cmp     rax, [r8+18h]
0x140098737  jnz     loc_140098867
0x14009873d  mov     rcx, cs:?g_aAsimov@@3PEAVCMpAsimov@@EA; CMpAsimov * g_aAsimov
0x140098744  lea     rdx, byte_1401B9347; int
0x14009874b  mov     eax, [rbx+1Ch]
0x14009874e  shl     rax, 14h
0x140098752  mov     [rbp+0C0h+var_E0], rax
0x140098756  mov     eax, [rcx+48h]
0x140098759  mov     dword ptr [rbp+0C0h+var_124+4], eax
0x14009875c  mov     eax, [rcx+44h]
0x14009875f  mov     dword ptr [rbp+0C0h+var_124], eax
0x140098762  mov     eax, [rcx+40h]
0x140098765  mov     dword ptr [rbp+0C0h+var_12C+4], eax
0x140098768  movzx   eax, byte ptr [rcx+3Ch]
0x14009876c  mov     dword ptr [rbp+0C0h+var_12C], eax
0x14009876f  movzx   eax, byte ptr [rcx+3Bh]
0x140098773  mov     dword ptr [rbp+0C0h+var_134+4], eax
0x140098776  movzx   eax, byte ptr [rcx+3Ah]
0x14009877a  mov     dword ptr [rbp+0C0h+var_134], eax
0x14009877d  movzx   eax, byte ptr [rcx+39h]
0x140098781  mov     dword ptr [rbp+0C0h+var_13C+4], eax
0x140098784  movzx   eax, byte ptr [rcx+38h]
  ... truncated ...
```
