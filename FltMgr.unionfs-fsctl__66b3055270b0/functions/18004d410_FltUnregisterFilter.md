# FltUnregisterFilter

- ea: `0x18004d410`
- end: `0x18004d7cb`
- name: `FltUnregisterFilter`
- size: `955`
- prototype: `void __stdcall(PFLT_FILTER Filter)`
- caller_count: `1`
- callee_count: `20`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180085c70`

## callees

- `0x180009f20`
- `0x18000d600`
- `0x18000ff70`
- `0x180010400`
- `0x180015240`
- `0x180024c00`
- `0x18004c7a4`
- `0x18004d410`
- `0x18004d7e0`
- `0x18004da1c`
- `0x180054aa8`
- `0x180055f14`
- `0x180056d30`
- `0x18005dcc0`
- `0x180063b40`
- `0x180063f70`
- `0x1800648b0`
- `0x180067030`
- `0x180077be0`
- `0x180078820`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x18004d5c6`
- `ntoskrnl!KeInitializeEvent` at `0x18004d5c6`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004d68b`
- `ntoskrnl!KeWaitForSingleObject` at `0x18004d68b`
- `ntoskrnl!IoGetStackLimits` at `0x18004d776`
- `ntoskrnl!IoGetStackLimits` at `0x18004d776`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18004d452`
- `ntoskrnl!ExInitializeFastOwnerEntry` at `0x18004d452`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18004d4ed`
- `ntoskrnl!ExAcquireFastResourceShared` at `0x18004d4ed`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004d4d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004d6c8`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004d4d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x18004d6c8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d560`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d599`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d70f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d560`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d599`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x18004d70f`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d554`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d58d`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d703`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d554`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d58d`
- `ntoskrnl!ExReleaseFastResource` at `0x18004d703`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18004d665`
- `ntoskrnl!ExCleanupAutoExpandPushLock` at `0x18004d665`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18004d6dd`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x18004d6dd`
- `ntoskrnl!ExDeleteFastResource` at `0x18004d69a`
- `ntoskrnl!ExDeleteFastResource` at `0x18004d69a`
- `ntoskrnl!ExRundownCompleted` at `0x18004d6bc`
- `ntoskrnl!ExRundownCompleted` at `0x18004d6bc`

## pseudocode

```c
void __stdcall FltUnregisterFilter(PFLT_FILTER Filter)
{
  _FLTP_FRAME *Frame; // r13
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r12
  int v6; // ecx
  _LIST_ENTRY *p_rList; // r15
  __int64 v8; // r8
  char *i; // rdi
  int v10; // r8d
  unsigned int mCount; // eax
  _LIST_ENTRY *p_mList; // rdi
  struct _LIST_ENTRY *Flink; // rcx
  struct _LIST_ENTRY *v14; // rax
  __int64 v15; // r8
  void (__fastcall *OldDriverUnload)(_DRIVER_OBJECT *); // rcx
  unsigned __int64 HighLimit[2]; // [rsp+30h] [rbp-99h] BYREF
  struct _KEVENT v18[3]; // [rsp+40h] [rbp-89h] BYREF
  _BYTE v19[144]; // [rsp+90h] [rbp-39h] BYREF
  unsigned __int64 LowLimit; // [rsp+130h] [rbp+67h] BYREF

  memset(v18, 0, sizeof(v18));
  memset(v19, 0, 0x48u);
  ExInitializeFastOwnerEntry(v19);
  Frame = Filter->Frame;
  v5 = (unsigned int)FltpStartingToDrainObject(Filter, v3, v4);
  if ( (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 813, 3223060491LL) >= 0 )
  {
    if ( (Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits & 0x20) != 0 )
      McTemplateU0sw_EtwWriteTransfer(
        v6,
        (unsigned int)RegSup_c829,
        (unsigned int)"FltUnregisterFilter",
        Filter->Name.Length >> 1,
        (__int64)Filter->Name.Buffer);
    p_rList = &Filter->InstanceList.rList;
LABEL_6:
    KeEnterCriticalRegion();
    LOBYTE(v8) = 1;
    ExAcquireFastResourceShared(&Filter->InstanceList, v19, v8);
    for ( i = (char *)p_rList->Flink; i != (char *)p_rList; i = *(char **)i )
    {
      if ( (*((_DWORD *)i - 30) & 1) == 0 && (*((_DWORD *)i - 10) & 4) == 0 )
      {
        v5 = (unsigned int)FltObjectReference(i - 120);
        if ( (int)FltpDbgStatus(v5, "minkernel\\fs\\filtermgr\\filter\\regsup.c", 883, 3223060491LL) >= 0 )
        {
          ExReleaseFastResource(&Filter->InstanceList, v19);
          KeLeaveCriticalRegion();
          FltpFreeInstance(i - 120, 2 * (Filter->Flags & 1u) + 2, v10);
          goto LABEL_6;
        }
      }
    }
    ExReleaseFastResource(&Filter->InstanceList, v19);
    KeLeaveCriticalRegion();
    FltpRemoveVolumeContextsForFilter(Filter);
    if ( Filter->VerifierExtension )
    {
      *(_QWORD *)&v18[0].Header.Lock = Filter;
      KeInitializeEvent(&v18[2], NotificationEvent, 0);
      LODWORD(v18[0].Header.WaitListHead.Flink) = 4780322;
      v18[1].Header.WaitListHead.Flink = (struct _LIST_ENTRY *)FltpvDoLostObjectCheck;
      v18[0].Header.WaitListHead.Blink = 0;
      v18[1].Header.WaitListHead.Blink = (struct _LIST_ENTRY *)v18;
      FltpQueueThrottledWorkItem(&v18[0].Header.WaitListHead, 1);
    }
    FltObjectDereference(Filter);
    FltpObjectRundownWait(Filter);
    mCount = Filter->PortList.mCount;
    if ( mCount >= 2 )
    {
      p_mList = &Filter->PortList.mList;
      do
      {
        Filter->PortList.mCount = mCount - 2;
        Flink = p_mList->Flink;
        if ( p_mList->Flink->Blink != p_mList || (v14 = Flink->Flink, Flink->Flink->Blink != Flink) )
          __fastfail(3u);
        p_mList->Flink = v14;
        v14->Blink = p_mList;
        Flink->Flink = 0;
        FltpTerminateConnection(Flink);
        mCount = Filter->PortList.mCount;
      }
      while ( mCount >= 2 );
    }
    ExCleanupAutoExpandPushLock(&Filter->PortLock);
    if ( Filter->VerifierExtension )
      KeWaitForSingleObject(&v18[2], Executive, 0, 0, 0);
    ExDeleteFastResource(&Filter->InstanceList);
    FltpCleanupContextRegistration((__int64)Filter);
    if ( (Filter->Base.Flags & 2) == 0 )
      _InterlockedOr((volatile signed __int32 *)Filter, 2u);
    ExRundownCompleted(&Filter->Base.RundownRef);
    KeEnterCriticalRegion();
    LOBYTE(v15) = 1;
    ExAcquireFastResourceExclusive(&Frame->RegisteredFilters, 0, v15);
    if ( !(unsigned int)FltpGetActiveFilterCount(Frame) )
      FltpCleanupFileObjectContextsForLastFilterRemoval(Frame);
    ExReleaseFastResource(&Frame->RegisteredFilters, 0);
    KeLeaveCriticalRegion();
    OldDriverUnload = Filter->OldDriverUnload;
    if ( OldDriverUnload )
      Filter->DriverObject->DriverUnload = (PDRIVER_UNLOAD)OldDriverUnload;
    FltpFreeUnicodeString(&Filter->DefaultAltitude);
    FltpCleanupFilterVerifier(Filter);
    FltpLogEventWithObjectID(&FLTMGR_FILTER_UNLOADED, 0);
    if ( (unsigned int)dword_18003DAA8 > 5 )
    {
      HighLimit[0] = 0;
      LowLimit = 0;
      IoGetStackLimits(&LowLimit, HighLimit);
      if ( (unsigned __int64)HighLimit - LowLimit >= 0x200 )
        FltpTelemetryFilterUnregistration((unsigned int)v5, Filter);
      else
        _InterlockedIncrement(&dword_18003FFB0);
    }
    FltpObjectPointerDereference(Filter);
  }
  else
  {
    FltObjectDereference(Filter);
  }
}

```

## disassembly

```asm
0x18004d410  push    rbp
0x18004d412  push    rbx
0x18004d413  push    rsi
0x18004d414  push    rdi
0x18004d415  push    r12
0x18004d417  push    r13
0x18004d419  push    r14
0x18004d41b  push    r15
0x18004d41d  lea     rbp, [rsp-1Fh]
0x18004d422  sub     rsp, 0E8h
0x18004d429  mov     rbx, rcx
0x18004d42c  mov     edi, 48h ; 'H'
0x18004d431  mov     r8d, edi; Size
0x18004d434  lea     rcx, [rsp+120h+var_E0]; void *
0x18004d439  xor     edx, edx; Val
0x18004d43b  call    memset
0x18004d440  mov     r8d, edi; Size
0x18004d443  lea     rcx, [rbp+57h+var_90]; void *
0x18004d447  xor     edx, edx; Val
0x18004d449  call    memset
0x18004d44e  lea     rcx, [rbp+57h+var_90]
0x18004d452  call    cs:__imp_ExInitializeFastOwnerEntry
0x18004d459  nop     dword ptr [rax+rax+00h]
0x18004d45e  mov     r13, [rbx+38h]
0x18004d462  mov     rcx, rbx
0x18004d465  call    FltpStartingToDrainObject
0x18004d46a  xor     esi, esi
0x18004d46c  lea     rdx, aMinkernelFsFil_16; "minkernel\\fs\\filtermgr\\filter\\regsu"...
0x18004d473  mov     ecx, eax
0x18004d475  mov     [rsp+120h+Timeout], rsi
0x18004d47a  mov     r8d, 32Dh
0x18004d480  mov     r9d, 0C01C000Bh
0x18004d486  mov     r12d, eax
0x18004d489  call    FltpDbgStatus
0x18004d48e  test    eax, eax
0x18004d490  jns     short loc_18004D49F
0x18004d492  mov     rcx, rbx; FltObject
0x18004d495  call    FltObjectDereference
0x18004d49a  jmp     loc_18004D7B6
0x18004d49f  test    cs:Microsoft_Windows_FltMgrTrace_20460e0498193c4b075e7d2a13c945f3EnableBits, 20h
0x18004d4a6  jz      short loc_18004D4CC
0x18004d4a8  movzx   r9d, word ptr [rbx+40h]
0x18004d4ad  lea     r8, aFltunregisterf; "FltUnregisterFilter"
0x18004d4b4  mov     rax, [rbx+48h]
0x18004d4b8  lea     rdx, RegSup_c829
0x18004d4bf  shr     r9d, 1
0x18004d4c2  mov     [rsp+120h+Timeout], rax
0x18004d4c7  call    McTemplateU0sw_EtwWriteTransfer
0x18004d4cc  lea     r14, [rbx+70h]
0x18004d4d0  lea     r15, [rbx+0D8h]
0x18004d4d7  call    cs:__imp_KeEnterCriticalRegion
0x18004d4de  nop     dword ptr [rax+rax+00h]
0x18004d4e3  mov     r8b, 1
0x18004d4e6  lea     rdx, [rbp+57h+var_90]
0x18004d4ea  mov     rcx, r14
0x18004d4ed  call    cs:__imp_ExAcquireFastResourceShared
0x18004d4f4  nop     dword ptr [rax+rax+00h]
0x18004d4f9  mov     rdi, [r15]
0x18004d4fc  cmp     rdi, r15
0x18004d4ff  jz      loc_18004D586
0x18004d505  lea     rsi, [rdi-78h]
0x18004d509  mov     eax, [rsi]
0x18004d50b  test    al, 1
0x18004d50d  jnz     short loc_18004D548
0x18004d50f  mov     eax, [rsi+50h]
0x18004d512  test    al, 4
0x18004d514  jnz     short loc_18004D548
0x18004d516  mov     rcx, rsi; FltObject
0x18004d519  call    FltObjectReference
0x18004d51e  mov     r8d, 373h
0x18004d524  mov     [rsp+120h+Timeout], 0
0x18004d52d  mov     r9d, 0C01C000Bh
0x18004d533  lea     rdx, aMinkernelFsFil_16; "minkernel\\fs\\filtermgr\\filter\\regsu"...
0x18004d53a  mov     ecx, eax
0x18004d53c  mov     r12d, eax
0x18004d53f  call    FltpDbgStatus
0x18004d544  test    eax, eax
0x18004d546  jns     short loc_18004D54D
0x18004d548  mov     rdi, [rdi]
0x18004d54b  jmp     short loc_18004D4FC
0x18004d54d  lea     rdx, [rbp+57h+var_90]
0x18004d551  mov     rcx, r14
0x18004d554  call    cs:__imp_ExReleaseFastResource
0x18004d55b  nop     dword ptr [rax+rax+00h]
0x18004d560  call    cs:__imp_KeLeaveCriticalRegion
0x18004d567  nop     dword ptr [rax+rax+00h]
0x18004d56c  mov     edx, [rbx+60h]
0x18004d56f  mov     rcx, rsi; FltObject
0x18004d572  and     edx, 1
0x18004d575  lea     edx, ds:2[rdx*2]
0x18004d57c  call    FltpFreeInstance
0x18004d581  jmp     loc_18004D4D7
0x18004d586  lea     rdx, [rbp+57h+var_90]
0x18004d58a  mov     rcx, r14
0x18004d58d  call    cs:__imp_ExReleaseFastResource
0x18004d594  nop     dword ptr [rax+rax+00h]
0x18004d599  call    cs:__imp_KeLeaveCriticalRegion
0x18004d5a0  nop     dword ptr [rax+rax+00h]
0x18004d5a5  mov     rcx, rbx; Filter
0x18004d5a8  call    FltpRemoveVolumeContextsForFilter
0x18004d5ad  xor     esi, esi
0x18004d5af  cmp     [rbx+0F0h], rsi
0x18004d5b6  jz      short loc_18004D5FF
0x18004d5b8  xor     r8d, r8d; State
0x18004d5bb  mov     [rsp+120h+var_E0], rbx
0x18004d5c0  xor     edx, edx; Type
0x18004d5c2  lea     rcx, [rbp+57h+Event]; Event
0x18004d5c6  call    cs:__imp_KeInitializeEvent
0x18004d5cd  nop     dword ptr [rax+rax+00h]
0x18004d5d2  lea     rax, FltpvDoLostObjectCheck
0x18004d5d9  mov     [rsp+120h+var_D8], 48F122h
0x18004d5e1  mov     [rbp+57h+var_C0], rax
0x18004d5e5  lea     edx, [rsi+1]
0x18004d5e8  lea     rax, [rsp+120h+var_E0]
0x18004d5ed  mov     [rbp+57h+var_D0], rsi
0x18004d5f1  lea     rcx, [rsp+120h+var_D8]
0x18004d5f6  mov     [rbp+57h+var_B8], rax
0x18004d5fa  call    FltpQueueThrottledWorkItem
0x18004d5ff  mov     rcx, rbx; FltObject
0x18004d602  call    FltObjectDereference
0x18004d607  mov     rcx, rbx
0x18004d60a  call    FltpObjectRundownWait
0x18004d60f  mov     eax, [rbx+2A8h]
0x18004d615  cmp     eax, 2
0x18004d618  jb      short loc_18004D65E
0x18004d61a  lea     rdi, [rbx+298h]
0x18004d621  add     eax, 0FFFFFFFEh
0x18004d624  mov     [rbx+2A8h], eax
0x18004d62a  mov     rcx, [rdi]; Object
0x18004d62d  cmp     [rcx+8], rdi
0x18004d631  jnz     loc_18004D79C
0x18004d637  mov     rax, [rcx]
0x18004d63a  cmp     [rax+8], rcx
0x18004d63e  jnz     loc_18004D79C
0x18004d644  mov     [rdi], rax
0x18004d647  mov     [rax+8], rdi
0x18004d64b  mov     [rcx], rsi
0x18004d64e  call    FltpTerminateConnection
0x18004d653  mov     eax, [rbx+2A8h]
0x18004d659  cmp     eax, 2
0x18004d65c  jnb     short loc_18004D621
0x18004d65e  lea     rcx, [rbx+2B0h]
0x18004d665  call    cs:__imp_ExCleanupAutoExpandPushLock
0x18004d66c  nop     dword ptr [rax+rax+00h]
0x18004d671  cmp     [rbx+0F0h], rsi
0x18004d678  jz      short loc_18004D697
0x18004d67a  xor     r9d, r9d; Alertable
0x18004d67d  mov     [rsp+120h+Timeout], rsi; Timeout
0x18004d682  xor     r8d, r8d; WaitMode
0x18004d685  lea     rcx, [rbp+57h+Event]; Object
0x18004d689  xor     edx, edx; WaitReason
0x18004d68b  call    cs:__imp_KeWaitForSingleObject
0x18004d692  nop     dword ptr [rax+rax+00h]
0x18004d697  mov     rcx, r14
0x18004d69a  call    cs:__imp_ExDeleteFastResource
0x18004d6a1  nop     dword ptr [rax+rax+00h]
0x18004d6a6  mov     rcx, rbx
0x18004d6a9  call    FltpCleanupContextRegistration
0x18004d6ae  mov     eax, [rbx]
0x18004d6b0  test    al, 2
0x18004d6b2  jnz     short loc_18004D6B8
0x18004d6b4  lock or dword ptr [rbx], 2
0x18004d6b8  lea     rcx, [rbx+8]; RunRef
0x18004d6bc  call    cs:__imp_ExRundownCompleted
0x18004d6c3  nop     dword ptr [rax+rax+00h]
0x18004d6c8  call    cs:__imp_KeEnterCriticalRegion
0x18004d6cf  nop     dword ptr [rax+rax+00h]
0x18004d6d4  mov     r8b, 1
0x18004d6d7  lea     rcx, [r13+48h]
0x18004d6db  xor     edx, edx
0x18004d6dd  call    cs:__imp_ExAcquireFastResourceExclusive
0x18004d6e4  nop     dword ptr [rax+rax+00h]
0x18004d6e9  mov     rcx, r13
0x18004d6ec  call    FltpGetActiveFilterCount
0x18004d6f1  test    eax, eax
0x18004d6f3  jnz     short loc_18004D6FD
0x18004d6f5  mov     rcx, r13
0x18004d6f8  call    FltpCleanupFileObjectContextsForLastFilterRemoval
0x18004d6fd  xor     edx, edx
0x18004d6ff  lea     rcx, [r13+48h]
0x18004d703  call    cs:__imp_ExReleaseFastResource
0x18004d70a  nop     dword ptr [rax+rax+00h]
0x18004d70f  call    cs:__imp_KeLeaveCriticalRegion
0x18004d716  nop     dword ptr [rax+rax+00h]
0x18004d71b  mov     rcx, [rbx+1B8h]
0x18004d722  test    rcx, rcx
0x18004d725  jz      short loc_18004D72F
0x18004d727  mov     rax, [rbx+68h]
0x18004d72b  mov     [rax+68h], rcx
0x18004d72f  lea     rcx, [rbx+50h]
0x18004d733  call    FltpFreeUnicodeString
0x18004d738  mov     rcx, rbx
0x18004d73b  call    FltpCleanupFilterVerifier
0x18004d740  mov     r8, [rbx+68h]
0x18004d744  lea     rcx, FLTMGR_FILTER_UNLOADED; EventDescriptor
0x18004d74b  xor     r9d, r9d
0x18004d74e  mov     [rsp+120h+Timeout], rsi; __int64
0x18004d753  mov     edx, r12d
0x18004d756  call    FltpLogEventWithObjectID
0x18004d75b  cmp     cs:dword_18003DAA8, 5
0x18004d762  jbe     short loc_18004D7AE
0x18004d764  lea     rdx, [rsp+120h+HighLimit]; HighLimit
0x18004d769  mov     [rsp+120h+HighLimit], rsi
0x18004d76e  lea     rcx, [rbp+57h+LowLimit]; LowLimit
0x18004d772  mov     [rbp+57h+LowLimit], rsi
0x18004d776  call    cs:__imp_IoGetStackLimits
0x18004d77d  nop     dword ptr [rax+rax+00h]
0x18004d782  lea     rax, [rsp+120h+HighLimit]
0x18004d787  sub     rax, [rbp+57h+LowLimit]
0x18004d78b  cmp     rax, 200h
0x18004d791  jnb     short loc_18004D7A3
0x18004d793  lock inc cs:dword_18003FFB0
0x18004d79a  jmp     short loc_18004D7AE
0x18004d79c  mov     ecx, 3
0x18004d7a1  int     29h; Win8: RtlFailFast(ecx)
0x18004d7a3  mov     rdx, rbx
0x18004d7a6  mov     ecx, r12d
0x18004d7a9  call    FltpTelemetryFilterUnregistration
0x18004d7ae  mov     rcx, rbx
0x18004d7b1  call    FltpObjectPointerDereference
0x18004d7b6  add     rsp, 0E8h
0x18004d7bd  pop     r15
0x18004d7bf  pop     r14
0x18004d7c1  pop     r13
0x18004d7c3  pop     r12
0x18004d7c5  pop     rdi
0x18004d7c6  pop     rsi
0x18004d7c7  pop     rbx
0x18004d7c8  pop     rbp
0x18004d7c9  retn
```
