# DriverEntry

- ea: `0x140027078`
- end: `0x140027550`
- name: `DriverEntry`
- size: `1240`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `7`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140027010`

## callees

- `0x140001348`
- `0x140004924`
- `0x140004964`
- `0x1400049ac`
- `0x140011630`
- `0x140027078`
- `0x140027558`

## import_xrefs

- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400273a5`
- `ntoskrnl!PsAllocSiloContextSlot` at `0x1400273a5`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140027145`
- `ntoskrnl!ExInitializeNPagedLookasideList` at `0x140027145`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002748b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274b1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274c4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274d7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274ea`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x14002748b`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274b1`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274c4`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274d7`
- `ntoskrnl!ExDeletePagedLookasideList` at `0x1400274ea`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002727a`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002727a`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002710f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140027178`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400271ab`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400271de`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140027211`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x14002710f`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140027178`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400271ab`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x1400271de`
- `ntoskrnl!ExInitializePagedLookasideList` at `0x140027211`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002749e`
- `ntoskrnl!ExDeleteNPagedLookasideList` at `0x14002749e`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400273e6`
- `ntoskrnl!ExInitializeResourceLite` at `0x1400273e6`
- `ntoskrnl!KeInitializeEvent` at `0x1400270dc`
- `ntoskrnl!KeInitializeEvent` at `0x1400270dc`
- `FLTMGR!FltCloseCommunicationPort` at `0x140027502`
- `FLTMGR!FltCloseCommunicationPort` at `0x140027502`
- `FLTMGR!FltStartFiltering` at `0x14002740e`
- `FLTMGR!FltStartFiltering` at `0x14002740e`
- `FLTMGR!FltCreateCommunicationPort` at `0x14002734b`
- `FLTMGR!FltCreateCommunicationPort` at `0x14002734b`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x140027293`
- `FLTMGR!FltBuildDefaultSecurityDescriptor` at `0x140027293`
- `FLTMGR!FltRegisterFilter` at `0x14002722e`
- `FLTMGR!FltRegisterFilter` at `0x14002722e`
- `FLTMGR!FltUnregisterFilter` at `0x14002751a`
- `FLTMGR!FltUnregisterFilter` at `0x14002751a`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140027361`
- `FLTMGR!FltFreeSecurityDescriptor` at `0x140027361`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  __int64 v3; // rdx
  __int64 v4; // rcx
  int started; // ebx
  __int64 v6; // r8
  int v7; // r9d
  char Depth; // [rsp+30h] [rbp-58h]
  char MaxConnections; // [rsp+38h] [rbp-50h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-38h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+A0h] [rbp+18h] BYREF

  SecurityDescriptor = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  BfTelemetryAndTracingInit(DriverObject, RegistryPath);
  FastMutex.Owner = 0;
  FastMutex.Count = 1;
  FastMutex.Contention = 0;
  KeInitializeEvent(&FastMutex.Event, SynchronizationEvent, 0);
  ExInitializePagedLookasideList(&stru_14000B280, 0, 0, 0, 0x88u, 0x63704642u, 0);
  ExInitializeNPagedLookasideList(&stru_14000B300, 0, 0, 0x200u, 0x38u, 0x636E4642u, 0);
  ExInitializePagedLookasideList(&stru_14000B380, 0, 0, 0, 0x100u, 0x65644642u, 0);
  ExInitializePagedLookasideList(&Lookaside, 0, 0, 0, 0x48u, 0x65644642u, 0);
  ExInitializePagedLookasideList(&stru_14000B480, 0, 0, 0, 0x10000u, 0x65644642u, 0);
  ExInitializePagedLookasideList(&stru_14000B500, 0, 0, 0, 0x20u, 0x65644642u, 0);
  started = FltRegisterFilter(DriverObject, &FilterRegistration, &g_BindFltState);
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v7 = 10;
      Depth = -55;
LABEL_16:
      LOBYTE(v3) = 2;
      WPP_RECORDER_SF_sDd(
        WPP_GLOBAL_Control->DeviceExtension,
        v3,
        1,
        v7,
        (__int64)WPP_5390131927d33d8db09f7c25a9551f08_Traceguids,
        (__int64)"onecore\\base\\fs\\wci\\bindflt\\filter\\bindflt.c",
        Depth,
        MaxConnections);
      goto LABEL_17;
    }
    goto LABEL_17;
  }
  McGenEventRegister_EtwRegister();
  RtlInitUnicodeString(&DestinationString, L"\\BindFltPort");
  started = FltBuildDefaultSecurityDescriptor(&SecurityDescriptor, 0x1F0001u);
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v7 = 11;
      Depth = -36;
      goto LABEL_16;
    }
LABEL_17:
    if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 1) != 0 )
      McTemplateK0d_EtwWriteTransfer(v4, v3, v6, (unsigned int)started);
    ExDeletePagedLookasideList(&stru_14000B280);
    ExDeleteNPagedLookasideList(&stru_14000B300);
    ExDeletePagedLookasideList(&stru_14000B380);
    ExDeletePagedLookasideList(&Lookaside);
    ExDeletePagedLookasideList(&stru_14000B480);
    ExDeletePagedLookasideList(&stru_14000B500);
    if ( ServerPort )
      FltCloseCommunicationPort(ServerPort);
    if ( g_BindFltState )
      FltUnregisterFilter(g_BindFltState);
    BfTelemetryAndTracingCleanup();
    return started;
  }
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  ObjectAttributes.SecurityQualityOfService = 0;
  started = FltCreateCommunicationPort(
              g_BindFltState,
              &ServerPort,
              &ObjectAttributes,
              0,
              BfPortConnect,
              BfPortDisconnect,
              BfPortMessage,
              1000);
  FltFreeSecurityDescriptor(SecurityDescriptor);
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v7 = 12;
      Depth = -14;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  started = PsAllocSiloContextSlot(0, &dword_14000B1D0);
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v7 = 13;
      Depth = -7;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  ExInitializeResourceLite(&Resource);
  qword_14000B1E0 = (__int64)&qword_14000B1D8;
  qword_14000B1D8 = (__int64)&qword_14000B1D8;
  started = FltStartFiltering(g_BindFltState);
  if ( started < 0 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      MaxConnections = started;
      v7 = 14;
      Depth = 4;
      goto LABEL_16;
    }
    goto LABEL_17;
  }
  if ( ((__int64)WPP_MAIN_CB.Queue.ListEntry.Flink & 2) != 0 )
    McTemplateK0_EtwWriteTransfer();
  return started;
}

```

## disassembly

```asm
0x140027078  mov     r11, rsp
0x14002707b  mov     [r11+8], rbx
0x14002707f  push    r14
0x140027081  sub     rsp, 80h
0x140027088  xorps   xmm0, xmm0
0x14002708b  xor     eax, eax
0x14002708d  movups  xmmword ptr [rsp+88h+ObjectAttributes.ObjectName], xmm0
0x140027092  mov     rbx, rcx
0x140027095  mov     [r11+18h], rax
0x140027099  movups  xmmword ptr [rsp+88h+ObjectAttributes+1Ch], xmm0
0x14002709e  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x1400270a3  movups  xmmword ptr [rsp+88h+ObjectAttributes.Length], xmm0
0x1400270a8  call    BfTelemetryAndTracingInit
0x1400270ad  mov     r14d, 1
0x1400270b3  mov     cs:FastMutex.Owner, 0
0x1400270be  mov     edx, r14d; Type
0x1400270c1  mov     cs:FastMutex.Count, r14d
0x1400270c8  xor     r8d, r8d; State
0x1400270cb  mov     cs:FastMutex.Contention, 0
0x1400270d5  lea     rcx, FastMutex.Event; Event
0x1400270dc  call    cs:__imp_KeInitializeEvent
0x1400270e3  nop     dword ptr [rax+rax+00h]
0x1400270e8  xor     eax, eax
0x1400270ea  lea     rcx, stru_14000B280; Lookaside
0x1400270f1  mov     [rsp+88h+Depth], ax; Depth
0x1400270f6  xor     r9d, r9d; Flags
0x1400270f9  mov     [rsp+88h+Tag], 63704642h; Tag
0x140027101  xor     r8d, r8d; Free
0x140027104  xor     edx, edx; Allocate
0x140027106  mov     [rsp+88h+Size], 88h; Size
0x14002710f  call    cs:__imp_ExInitializePagedLookasideList
0x140027116  nop     dword ptr [rax+rax+00h]
0x14002711b  xor     eax, eax
0x14002711d  lea     rcx, stru_14000B300; Lookaside
0x140027124  mov     [rsp+88h+Depth], ax; Depth
0x140027129  mov     r9d, 200h; Flags
0x14002712f  mov     [rsp+88h+Tag], 636E4642h; Tag
0x140027137  xor     r8d, r8d; Free
0x14002713a  xor     edx, edx; Allocate
0x14002713c  mov     [rsp+88h+Size], 38h ; '8'; Size
0x140027145  call    cs:__imp_ExInitializeNPagedLookasideList
0x14002714c  nop     dword ptr [rax+rax+00h]
0x140027151  xor     eax, eax
0x140027153  lea     rcx, stru_14000B380; Lookaside
0x14002715a  mov     [rsp+88h+Depth], ax; Depth
0x14002715f  xor     r9d, r9d; Flags
0x140027162  mov     [rsp+88h+Tag], 65644642h; Tag
0x14002716a  xor     r8d, r8d; Free
0x14002716d  xor     edx, edx; Allocate
0x14002716f  mov     [rsp+88h+Size], 100h; Size
0x140027178  call    cs:__imp_ExInitializePagedLookasideList
0x14002717f  nop     dword ptr [rax+rax+00h]
0x140027184  xor     eax, eax
0x140027186  lea     rcx, Lookaside; Lookaside
0x14002718d  mov     [rsp+88h+Depth], ax; Depth
0x140027192  xor     r9d, r9d; Flags
0x140027195  mov     [rsp+88h+Tag], 65644642h; Tag
0x14002719d  xor     r8d, r8d; Free
0x1400271a0  xor     edx, edx; Allocate
0x1400271a2  mov     [rsp+88h+Size], 48h ; 'H'; Size
0x1400271ab  call    cs:__imp_ExInitializePagedLookasideList
0x1400271b2  nop     dword ptr [rax+rax+00h]
0x1400271b7  xor     eax, eax
0x1400271b9  lea     rcx, stru_14000B480; Lookaside
0x1400271c0  mov     [rsp+88h+Depth], ax; Depth
0x1400271c5  xor     r9d, r9d; Flags
0x1400271c8  mov     [rsp+88h+Tag], 65644642h; Tag
0x1400271d0  xor     r8d, r8d; Free
0x1400271d3  xor     edx, edx; Allocate
0x1400271d5  mov     [rsp+88h+Size], 10000h; Size
0x1400271de  call    cs:__imp_ExInitializePagedLookasideList
0x1400271e5  nop     dword ptr [rax+rax+00h]
0x1400271ea  xor     eax, eax
0x1400271ec  lea     rcx, stru_14000B500; Lookaside
0x1400271f3  mov     [rsp+88h+Depth], ax; Depth
0x1400271f8  xor     r9d, r9d; Flags
0x1400271fb  mov     [rsp+88h+Tag], 65644642h; Tag
0x140027203  xor     r8d, r8d; Free
0x140027206  xor     edx, edx; Allocate
0x140027208  mov     [rsp+88h+Size], 20h ; ' '; Size
0x140027211  call    cs:__imp_ExInitializePagedLookasideList
0x140027218  nop     dword ptr [rax+rax+00h]
0x14002721d  lea     r8, g_BindFltState; RetFilter
0x140027224  mov     rcx, rbx; Driver
0x140027227  lea     rdx, FilterRegistration; Registration
0x14002722e  call    cs:__imp_FltRegisterFilter
0x140027235  nop     dword ptr [rax+rax+00h]
0x14002723a  mov     ebx, eax
0x14002723c  test    eax, eax
0x14002723e  jns     short loc_140027269
0x140027240  lea     rax, WPP_RECORDER_INITIALIZED
0x140027247  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002724e  jz      loc_140027473
0x140027254  mov     dword ptr [rsp+88h+MaxConnections], ebx
0x140027258  lea     r9d, [r14+9]
0x14002725c  mov     dword ptr [rsp+88h+Depth], 1C9h
0x140027264  jmp     loc_140027446
0x140027269  call    McGenEventRegister_EtwRegister
0x14002726e  lea     rdx, aBindfltport; "\\BindFltPort"
0x140027275  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14002727a  call    cs:__imp_RtlInitUnicodeString
0x140027281  nop     dword ptr [rax+rax+00h]
0x140027286  mov     edx, 1F0001h; DesiredAccess
0x14002728b  lea     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x140027293  call    cs:__imp_FltBuildDefaultSecurityDescriptor
0x14002729a  nop     dword ptr [rax+rax+00h]
0x14002729f  mov     ebx, eax
0x1400272a1  test    eax, eax
0x1400272a3  jns     short loc_1400272D0
0x1400272a5  lea     rax, WPP_RECORDER_INITIALIZED
0x1400272ac  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400272b3  jz      loc_140027473
0x1400272b9  mov     dword ptr [rsp+88h+MaxConnections], ebx
0x1400272bd  mov     r9d, 0Bh
0x1400272c3  mov     dword ptr [rsp+88h+Depth], 1DCh
0x1400272cb  jmp     loc_140027446
0x1400272d0  mov     rcx, cs:g_BindFltState; Filter
0x1400272d7  lea     rax, [rsp+88h+DestinationString]
0x1400272dc  mov     [rsp+88h+ObjectAttributes.ObjectName], rax
0x1400272e1  lea     r8, [rsp+88h+ObjectAttributes]; ObjectAttributes
0x1400272e6  mov     rax, [rsp+88h+SecurityDescriptor]
0x1400272ee  lea     rdx, ServerPort; ServerPort
0x1400272f5  mov     [rsp+88h+ObjectAttributes.SecurityDescriptor], rax
0x1400272fa  xor     r9d, r9d; ServerPortCookie
0x1400272fd  mov     dword ptr [rsp+88h+MaxConnections], 3E8h; MaxConnections
0x140027305  lea     rax, BfPortMessage
0x14002730c  mov     qword ptr [rsp+88h+Depth], rax; MessageNotifyCallback
0x140027311  lea     rax, BfPortDisconnect
0x140027318  mov     qword ptr [rsp+88h+Tag], rax; DisconnectNotifyCallback
0x14002731d  lea     rax, BfPortConnect
0x140027324  mov     [rsp+88h+Size], rax; ConnectNotifyCallback
0x140027329  mov     [rsp+88h+ObjectAttributes.Length], 30h ; '0'
0x140027331  mov     [rsp+88h+ObjectAttributes.RootDirectory], 0
0x14002733a  mov     [rsp+88h+ObjectAttributes.Attributes], 240h
0x140027342  mov     [rsp+88h+ObjectAttributes.SecurityQualityOfService], 0
0x14002734b  call    cs:__imp_FltCreateCommunicationPort
0x140027352  nop     dword ptr [rax+rax+00h]
0x140027357  mov     rcx, [rsp+88h+SecurityDescriptor]; SecurityDescriptor
0x14002735f  mov     ebx, eax
0x140027361  call    cs:__imp_FltFreeSecurityDescriptor
0x140027368  nop     dword ptr [rax+rax+00h]
0x14002736d  test    ebx, ebx
0x14002736f  jns     short loc_14002739C
0x140027371  lea     rax, WPP_RECORDER_INITIALIZED
0x140027378  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002737f  jz      loc_140027473
0x140027385  mov     dword ptr [rsp+88h+MaxConnections], ebx
0x140027389  mov     r9d, 0Ch
0x14002738f  mov     dword ptr [rsp+88h+Depth], 1F2h
0x140027397  jmp     loc_140027446
0x14002739c  lea     rdx, dword_14000B1D0
0x1400273a3  xor     ecx, ecx
0x1400273a5  call    cs:__imp_PsAllocSiloContextSlot
0x1400273ac  nop     dword ptr [rax+rax+00h]
0x1400273b1  mov     ebx, eax
0x1400273b3  test    eax, eax
0x1400273b5  jns     short loc_1400273DF
0x1400273b7  lea     rax, WPP_RECORDER_INITIALIZED
0x1400273be  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x1400273c5  jz      loc_140027473
0x1400273cb  mov     dword ptr [rsp+88h+MaxConnections], ebx
0x1400273cf  mov     r9d, 0Dh
0x1400273d5  mov     dword ptr [rsp+88h+Depth], 1F9h
0x1400273dd  jmp     short loc_140027446
0x1400273df  lea     rcx, Resource; Resource
0x1400273e6  call    cs:__imp_ExInitializeResourceLite
0x1400273ed  nop     dword ptr [rax+rax+00h]
0x1400273f2  mov     rcx, cs:g_BindFltState; Filter
0x1400273f9  lea     rax, qword_14000B1D8
0x140027400  mov     cs:qword_14000B1E0, rax
0x140027407  mov     cs:qword_14000B1D8, rax
0x14002740e  call    cs:__imp_FltStartFiltering
0x140027415  nop     dword ptr [rax+rax+00h]
0x14002741a  mov     ebx, eax
0x14002741c  test    eax, eax
0x14002741e  jns     loc_14002752D
0x140027424  lea     rax, WPP_RECORDER_INITIALIZED
0x14002742b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x140027432  jz      short loc_140027473
0x140027434  mov     dword ptr [rsp+88h+MaxConnections], ebx
0x140027438  mov     r9d, 0Eh
0x14002743e  mov     dword ptr [rsp+88h+Depth], 204h
0x140027446  mov     rcx, cs:WPP_GLOBAL_Control
0x14002744d  lea     rax, aOnecoreBaseFsW_8; "onecore\\base\\fs\\wci\\bindflt\\filter"...
0x140027454  mov     qword ptr [rsp+88h+Tag], rax
0x140027459  mov     r8d, r14d
0x14002745c  lea     rax, WPP_5390131927d33d8db09f7c25a9551f08_Traceguids
0x140027463  mov     dl, 2
0x140027465  mov     [rsp+88h+Size], rax
0x14002746a  mov     rcx, [rcx+40h]
0x14002746e  call    WPP_RECORDER_SF_sDd
0x140027473  test    byte ptr cs:WPP_MAIN_CB.Queue, r14b
0x14002747a  jz      short loc_140027484
0x14002747c  mov     r9d, ebx
0x14002747f  call    McTemplateK0d_EtwWriteTransfer
0x140027484  lea     rcx, stru_14000B280; Lookaside
0x14002748b  call    cs:__imp_ExDeletePagedLookasideList
0x140027492  nop     dword ptr [rax+rax+00h]
0x140027497  lea     rcx, stru_14000B300; Lookaside
0x14002749e  call    cs:__imp_ExDeleteNPagedLookasideList
0x1400274a5  nop     dword ptr [rax+rax+00h]
0x1400274aa  lea     rcx, stru_14000B380; Lookaside
0x1400274b1  call    cs:__imp_ExDeletePagedLookasideList
0x1400274b8  nop     dword ptr [rax+rax+00h]
0x1400274bd  lea     rcx, Lookaside; Lookaside
0x1400274c4  call    cs:__imp_ExDeletePagedLookasideList
0x1400274cb  nop     dword ptr [rax+rax+00h]
0x1400274d0  lea     rcx, stru_14000B480; Lookaside
0x1400274d7  call    cs:__imp_ExDeletePagedLookasideList
0x1400274de  nop     dword ptr [rax+rax+00h]
0x1400274e3  lea     rcx, stru_14000B500; Lookaside
0x1400274ea  call    cs:__imp_ExDeletePagedLookasideList
0x1400274f1  nop     dword ptr [rax+rax+00h]
0x1400274f6  mov     rcx, cs:ServerPort; ServerPort
0x1400274fd  test    rcx, rcx
0x140027500  jz      short loc_14002750E
0x140027502  call    cs:__imp_FltCloseCommunicationPort
0x140027509  nop     dword ptr [rax+rax+00h]
0x14002750e  mov     rcx, cs:g_BindFltState; Filter
0x140027515  test    rcx, rcx
0x140027518  jz      short loc_140027526
0x14002751a  call    cs:__imp_FltUnregisterFilter
0x140027521  nop     dword ptr [rax+rax+00h]
0x140027526  call    BfTelemetryAndTracingCleanup
0x14002752b  jmp     short loc_14002753B
0x14002752d  test    byte ptr cs:WPP_MAIN_CB.Queue, 2
0x140027534  jz      short loc_14002753B
0x140027536  call    McTemplateK0_EtwWriteTransfer
0x14002753b  mov     eax, ebx
0x14002753d  mov     rbx, [rsp+88h+arg_0]
0x140027545  add     rsp, 80h
0x14002754c  pop     r14
0x14002754e  retn
```
