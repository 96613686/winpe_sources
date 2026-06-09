# BiSrvQueryBrokeredEvent

- ea: `0x18000ac6c`
- end: `0x18000ae52`
- name: `BiSrvQueryBrokeredEvent`
- size: `486`
- prototype: `__int64 __fastcall(PSID Sid1, void *Source1)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000af90`
- `0x180091ca0`

## callees

- `0x1800075f8`
- `0x1800095b0`
- `0x18000a430`
- `0x18000ac6c`
- `0x18000d7c0`
- `0x18000da50`
- `0x18001027c`
- `0x1800121b0`
- `0x1800394a8`
- `0x18003a62c`
- `0x180043424`
- `0x180078e24`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18000adb9`
- `ntdll!RtlFreeHeap` at `0x18000adcd`
- `ntdll!RtlFreeHeap` at `0x18000adb9`
- `ntdll!RtlFreeHeap` at `0x18000adcd`
- `ntdll!RtlEqualSid` at `0x18000ad1b`
- `ntdll!RtlEqualSid` at `0x18000ad51`
- `ntdll!RtlEqualSid` at `0x18000ad1b`
- `ntdll!RtlEqualSid` at `0x18000ad51`

## pseudocode

```c
__int64 __fastcall BiSrvQueryBrokeredEvent(PSID Sid1, void *Source1, _DWORD *a3, _QWORD *a4)
{
  unsigned int v4; // eax
  __int64 v9; // rcx
  int BrokeredEvent; // ebx
  __int64 v11; // r8
  __int64 v12; // r9
  int v13; // esi
  struct _BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *v14; // rcx
  volatile signed __int32 *v15; // rdi
  void *v16; // rdx
  void *v17; // rdx
  __int64 v18; // rdx
  void *v20; // [rsp+40h] [rbp-38h] BYREF
  PVOID P; // [rsp+90h] [rbp+18h] BYREF
  void *v22; // [rsp+98h] [rbp+20h] BYREF

  v4 = dword_1800C3098;
  P = 0;
  *a3 = 0;
  *a4 = 0;
  if ( v4 > 4 )
  {
    v22 = Source1;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
      (__int64)Sid1,
      (unsigned __int8 *)byte_1800B4451,
      (__int64)a3,
      (__int64)a4,
      (__int64 *)&v22);
  }
  BipStorageSynchronizeWithInitialization();
  BrokeredEvent = BipLookupEventByGuid(Source1);
  if ( BrokeredEvent < 0 )
  {
    v13 = 10;
    goto LABEL_26;
  }
  BipAcquireGlobalLock(v9);
  v15 = (volatile signed __int32 *)P;
  if ( *((int *)P + 6) < 0 )
  {
    BrokeredEvent = -1073741275;
    v13 = 20;
    goto LABEL_18;
  }
  if ( !Sid1 || (v16 = (void *)*((_QWORD *)P + 21)) != 0 && RtlEqualSid(Sid1, v16) )
  {
LABEL_16:
    v13 = 0;
    BrokeredEvent = BipQueryBrokeredEvent(v15, a3, a4);
    if ( BrokeredEvent < 0 )
      v13 = 40;
    goto LABEL_18;
  }
  if ( *((_QWORD *)v15 + 23) && (unsigned __int8)BipIsDeviceHoloLens(v14) )
  {
    v17 = (void *)*((_QWORD *)v15 + 23);
    if ( !v17 || (BrokeredEvent = 0, !RtlEqualSid(Sid1, v17)) )
      BrokeredEvent = -1073741823;
    if ( BrokeredEvent >= 0 )
      goto LABEL_16;
  }
  else
  {
    BrokeredEvent = -1073741823;
  }
  v13 = 30;
LABEL_18:
  BipLockWatchdogContextDisarmWatchdog(v14);
  LOBYTE(v18) = 1;
  BipSyncReleaseLock(&BipGlobalLock, v18);
  if ( _InterlockedExchangeAdd(v15 + 7, 0xFFFFFFFF) == 1 )
  {
    if ( *((_DWORD *)v15 + 12) == 1 )
    {
      BipEventQueueDestroy((struct _BI_LOCK *)&qword_1800C4600);
    }
    else if ( *((_DWORD *)v15 + 12) == 2 )
    {
      BipWorkItemCheckQueueDestroy((struct _BI_WORK_ITEM *)v15);
    }
    else
    {
      RtlFreeHeap(BipHeap, 0, (PVOID)v15);
    }
  }
LABEL_26:
  if ( (unsigned int)dword_1800C3098 > 4 )
  {
    v20 = Source1;
    LODWORD(P) = v13;
    LODWORD(v22) = BrokeredEvent;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      v9,
      (unsigned __int8 *)byte_1800B4713,
      v11,
      v12,
      (__int64)&v22,
      (__int64)&P,
      (__int64 *)&v20);
  }
  return (unsigned int)BrokeredEvent;
}

```

## disassembly

```asm
0x18000ac6c  mov     r11, rsp
0x18000ac6f  mov     [r11+8], rbx
0x18000ac73  push    rbp
0x18000ac74  push    rsi
0x18000ac75  push    rdi
0x18000ac76  push    r14
0x18000ac78  push    r15
0x18000ac7a  sub     rsp, 50h
0x18000ac7e  mov     eax, cs:dword_1800C3098
0x18000ac84  mov     r14, r9
0x18000ac87  mov     qword ptr [r11+18h], 0
0x18000ac8f  mov     r15, r8
0x18000ac92  mov     dword ptr [r8], 0
0x18000ac99  mov     rbp, rdx
0x18000ac9c  mov     qword ptr [r9], 0
0x18000aca3  mov     rsi, rcx
0x18000aca6  cmp     eax, 4
0x18000aca9  jbe     short loc_18000ACC3
0x18000acab  mov     [r11+20h], rdx
0x18000acaf  lea     rax, [r11+20h]
0x18000acb3  lea     rdx, byte_1800B4451
0x18000acba  mov     [r11-58h], rax
0x18000acbe  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18000acc3  call    BipStorageSynchronizeWithInitialization
0x18000acc8  lea     rdx, [rsp+78h+P]
0x18000acd0  mov     rcx, rbp; Source1
0x18000acd3  call    BipLookupEventByGuid
0x18000acd8  mov     ebx, eax
0x18000acda  test    eax, eax
0x18000acdc  jns     short loc_18000ACE8
0x18000acde  mov     esi, 0Ah
0x18000ace3  jmp     loc_18000ADEE
0x18000ace8  call    BipAcquireGlobalLock
0x18000aced  mov     rdi, [rsp+78h+P]
0x18000acf5  cmp     dword ptr [rdi+18h], 0
0x18000acf9  jge     short loc_18000AD07
0x18000acfb  mov     ebx, 0C0000225h
0x18000ad00  mov     esi, 14h
0x18000ad05  jmp     short loc_18000AD7E
0x18000ad07  test    rsi, rsi
0x18000ad0a  jz      short loc_18000AD64
0x18000ad0c  mov     rdx, [rdi+0A8h]; Sid2
0x18000ad13  test    rdx, rdx
0x18000ad16  jz      short loc_18000AD25
0x18000ad18  mov     rcx, rsi; Sid1
0x18000ad1b  call    cs:__imp_RtlEqualSid
0x18000ad21  test    al, al
0x18000ad23  jnz     short loc_18000AD64
0x18000ad25  cmp     qword ptr [rdi+0B8h], 0
0x18000ad2d  jz      loc_18000ADC1
0x18000ad33  call    BipIsDeviceHoloLens
0x18000ad38  test    al, al
0x18000ad3a  jz      loc_18000ADC1
0x18000ad40  mov     rdx, [rdi+0B8h]; Sid2
0x18000ad47  test    rdx, rdx
0x18000ad4a  jz      short loc_18000AD5B
0x18000ad4c  mov     rcx, rsi; Sid1
0x18000ad4f  xor     ebx, ebx
0x18000ad51  call    cs:__imp_RtlEqualSid
0x18000ad57  test    al, al
0x18000ad59  jnz     short loc_18000AD60
0x18000ad5b  mov     ebx, 0C0000001h
0x18000ad60  test    ebx, ebx
0x18000ad62  js      short loc_18000ADC6
0x18000ad64  mov     r8, r14
0x18000ad67  mov     rdx, r15
0x18000ad6a  mov     rcx, rdi
0x18000ad6d  call    BipQueryBrokeredEvent
0x18000ad72  xor     esi, esi
0x18000ad74  mov     ebx, eax
0x18000ad76  test    ebx, ebx
0x18000ad78  lea     eax, [rsi+28h]
0x18000ad7b  cmovs   esi, eax
0x18000ad7e  call    ?BipLockWatchdogContextDisarmWatchdog@@YAXPEAU_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT@@@Z; BipLockWatchdogContextDisarmWatchdog(_BI_GLOBAL_LOCK_WATCHDOG_CONTEXT *)
0x18000ad83  mov     dl, 1
0x18000ad85  lea     rcx, BipGlobalLock
0x18000ad8c  call    BipSyncReleaseLock
0x18000ad91  or      eax, 0FFFFFFFFh
0x18000ad94  lock xadd [rdi+1Ch], eax
0x18000ad99  cmp     eax, 1
0x18000ad9c  jnz     short loc_18000ADEE
0x18000ad9e  mov     ecx, [rdi+30h]
0x18000ada1  sub     ecx, eax
0x18000ada3  jz      short loc_18000ADDF
0x18000ada5  sub     ecx, eax
0x18000ada7  jz      short loc_18000ADD5
0x18000ada9  xor     edx, edx; Flags
0x18000adab  mov     r8, rdi; P
0x18000adae  cmp     ecx, eax
0x18000adb0  mov     rcx, cs:BipHeap; HeapHandle
0x18000adb7  jz      short loc_18000ADCD
0x18000adb9  call    cs:__imp_RtlFreeHeap
0x18000adbf  jmp     short loc_18000ADEE
0x18000adc1  mov     ebx, 0C0000001h
0x18000adc6  mov     esi, 1Eh
0x18000adcb  jmp     short loc_18000AD7E
0x18000adcd  call    cs:__imp_RtlFreeHeap
0x18000add3  jmp     short loc_18000ADEE
0x18000add5  mov     rcx, rdi; struct _BI_WORK_ITEM *
0x18000add8  call    BipWorkItemCheckQueueDestroy
0x18000addd  jmp     short loc_18000ADEE
0x18000addf  mov     rdx, rdi
0x18000ade2  lea     rcx, qword_1800C4600; struct _BI_LOCK *
0x18000ade9  call    BipEventQueueDestroy
0x18000adee  mov     eax, cs:dword_1800C3098
0x18000adf4  cmp     eax, 4
0x18000adf7  jbe     short loc_18000AE3C
0x18000adf9  lea     rax, [rsp+78h+var_38]
0x18000adfe  mov     [rsp+78h+var_38], rbp
0x18000ae03  mov     [rsp+78h+var_48], rax
0x18000ae08  lea     rdx, byte_1800B4713
0x18000ae0f  lea     rax, [rsp+78h+P]
0x18000ae17  mov     dword ptr [rsp+78h+P], esi
0x18000ae1e  mov     [rsp+78h+var_50], rax
0x18000ae23  lea     rax, [rsp+78h+arg_18]
0x18000ae2b  mov     [rsp+78h+var_58], rax
0x18000ae30  mov     dword ptr [rsp+78h+arg_18], ebx
0x18000ae37  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x18000ae3c  mov     eax, ebx
0x18000ae3e  mov     rbx, [rsp+78h+arg_0]
0x18000ae46  add     rsp, 50h
0x18000ae4a  pop     r15
0x18000ae4c  pop     r14
0x18000ae4e  pop     rdi
0x18000ae4f  pop     rsi
0x18000ae50  pop     rbp
0x18000ae51  retn
```
