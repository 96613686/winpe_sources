# ScoCxn_Initialize(_SCO_CONNECTION *,_SCO_INTERFACE *,unsigned __int64 *,ulong,ulong)

- ea: `0x140137508`
- end: `0x1401377e2`
- name: `?ScoCxn_Initialize@@YAJPEAU_SCO_CONNECTION@@PEAU_SCO_INTERFACE@@PEA_KKK@Z`
- size: `730`
- prototype: `__int64 __usercall@<rax>(PVOID Tag@<rcx>, struct _SCO_INTERFACE *@<rdx>, unsigned __int64 *@<r8>, unsigned int@<r9d>, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x140132efc`

## callees

- `0x140005690`
- `0x140005c04`
- `0x140045e0c`
- `0x140132d9c`
- `0x140137508`
- `0x140161a44`
- `0x140161c78`
- `0x140162f00`

## import_xrefs

- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140137704`
- `ntoskrnl!IoAcquireRemoveLockEx` at `0x140137704`
- `ntoskrnl!KeInitializeDpc` at `0x1401375cc`
- `ntoskrnl!KeInitializeDpc` at `0x140137601`
- `ntoskrnl!KeInitializeDpc` at `0x1401375cc`
- `ntoskrnl!KeInitializeDpc` at `0x140137601`
- `ntoskrnl!KeInitializeTimerEx` at `0x1401375e4`
- `ntoskrnl!KeInitializeTimerEx` at `0x140137619`
- `ntoskrnl!KeInitializeTimerEx` at `0x1401375e4`
- `ntoskrnl!KeInitializeTimerEx` at `0x140137619`
- `ntoskrnl!KeInitializeSpinLock` at `0x14013759a`
- `ntoskrnl!KeInitializeSpinLock` at `0x14013759a`

## pseudocode

```c
__int64 __fastcall ScoCxn_Initialize(
        char *Tag,
        struct _SCO_INTERFACE *a2,
        unsigned __int64 *a3,
        unsigned int a4,
        unsigned int a5)
{
  struct _REF_OBJ *v5; // rbx
  NTSTATUS v9; // eax
  int v10; // edx
  int v11; // r8d
  unsigned int v12; // ebx
  __int64 v14; // [rsp+48h] [rbp-50h]
  unsigned int v15; // [rsp+A0h] [rbp+8h] BYREF

  *(_DWORD *)Tag = 1314407251;
  v5 = (struct _REF_OBJ *)(Tag + 8);
  *((_WORD *)Tag + 236) = -1;
  *((_QWORD *)Tag + 58) = *a3;
  *((_DWORD *)Tag + 46) = a2->InterfaceType;
  v15 = 0;
  RefObj_InitEx(
    (_DWORD)Tag + 8,
    (unsigned int)ScoCxn_Destroy,
    (_DWORD)Tag,
    714,
    (__int64)"onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\scoconnection.cpp",
    BthLib_RefObjDebugEnabled);
  *((_QWORD *)Tag + 4) = a2;
  RefObj_AddRefEx(&a2->RefObj, Tag, 717, "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\scoconnection.cpp");
  KeInitializeSpinLock((PKSPIN_LOCK)Tag + 19);
  *((_QWORD *)Tag + 21) = 0;
  *((_QWORD *)Tag + 85) = Tag + 672;
  *((_QWORD *)Tag + 84) = Tag + 672;
  KeInitializeDpc((PRKDPC)(Tag + 264), ScoCxnS_SignalTimeoutDpc, 0);
  KeInitializeTimerEx((PKTIMER)(Tag + 200), SynchronizationTimer);
  KeInitializeDpc((PRKDPC)(Tag + 392), ScoCxnS_ConfigTimerDpc, 0);
  KeInitializeTimerEx((PKTIMER)(Tag + 328), SynchronizationTimer);
  SCO_INIT_CLIENT_FLAGS(a4, &v15);
  HCI_InitClientEx(
    (struct HCI_CLIENT *)(Tag + 40),
    (void (*)(struct HCI_CLIENT *, struct HCI_L2CAP_DATA *, int, unsigned __int8, unsigned __int8, struct _GUID *))ScoCxnS_HciConnectCallback,
    0,
    0,
    0,
    v5,
    TypeSco,
    v15,
    0,
    0,
    2u);
  LockedList_Init(Tag + 592, Tag + 608);
  *((_QWORD *)Tag + 79) = ScoCxnS_SignalIrpCancel;
  *((_QWORD *)Tag + 80) = BthCompleteRequestExternal;
  *((_QWORD *)Tag + 82) = 0;
  *((_DWORD *)Tag + 162) = 0;
  Tag[664] = 0;
  Tag[652] = 0;
  LockedList_Init(Tag + 992, Tag + 1008);
  Tag[1040] = 1;
  *((_QWORD *)Tag + 129) = 0;
  LockedList_Init(Tag + 936, Tag + 952);
  Tag[984] = 0;
  *((_QWORD *)Tag + 122) = 0;
  v9 = IoAcquireRemoveLockEx(
         &a2->DevExt->RemoveLock,
         Tag,
         "onecore\\drivers\\wdm\\bluetooth\\drivers\\bthport\\src\\scoconnection.cpp",
         0x311u,
         0x20u);
  v12 = v9;
  if ( v9 >= 0 )
  {
    *((_DWORD *)Tag + 41) |= 1u;
    v12 = 0;
    *((_DWORD *)Tag + 286) = (a5 != 2) + 1;
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 2u) )
      LOBYTE(v10) = 0;
    LOBYTE(v11) = 1;
    WPP_RECORDER_AND_TRACE_SF_d(
      WPP_GLOBAL_Control->AttachedDevice,
      v10,
      v11,
      WPP_GLOBAL_Control->DeviceExtension,
      2,
      4,
      27,
      (__int64)WPP_c82f5777c0b73a20e7817411fb777e73_Traceguids,
      v9);
  }
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) == 0 || (LOBYTE(v10) = 1, BYTE1(WPP_GLOBAL_Control->Timer) < 4u) )
    LOBYTE(v10) = 0;
  LOBYTE(v11) = 1;
  LODWORD(v14) = v12;
  WPP_RECORDER_AND_TRACE_SF_qL(
    WPP_GLOBAL_Control->AttachedDevice,
    v10,
    v11,
    WPP_GLOBAL_Control->DeviceExtension,
    4,
    4,
    28,
    (__int64)WPP_c82f5777c0b73a20e7817411fb777e73_Traceguids,
    (char)Tag,
    v14);
  return v12;
}

```

## disassembly

```asm
0x140137508  mov     r11, rsp
0x14013750b  push    rbx
0x14013750c  push    rbp
0x14013750d  push    rsi
0x14013750e  push    rdi
0x14013750f  push    r12
0x140137511  push    r14
0x140137513  sub     rsp, 68h
0x140137517  mov     dword ptr [rcx], 4E584353h
0x14013751d  lea     rbx, [rcx+8]
0x140137521  mov     word ptr [rcx+1D8h], 0FFFFh
0x14013752a  lea     rbp, aOnecoreDrivers_22; "onecore\\drivers\\wdm\\bluetooth\\drive"...
0x140137531  mov     rax, [r8]
0x140137534  mov     edi, r9d
0x140137537  mov     [rcx+1D0h], rax
0x14013753e  mov     rsi, rdx
0x140137541  mov     eax, [rdx+30h]
0x140137544  mov     r14, rcx
0x140137547  mov     [rcx+0B8h], eax
0x14013754d  lea     rdx, ?ScoCxn_Destroy@@YAXPEAU_REF_OBJ@@@Z; ScoCxn_Destroy(_REF_OBJ *)
0x140137554  mov     al, cs:BthLib_RefObjDebugEnabled
0x14013755a  mov     r8, rcx
0x14013755d  mov     byte ptr [rsp+98h+var_70], al
0x140137561  xor     r12d, r12d
0x140137564  mov     r9d, 2CAh
0x14013756a  mov     [r11-78h], rbp
0x14013756e  mov     rcx, rbx
0x140137571  mov     [r11+8], r12d
0x140137575  call    RefObj_InitEx
0x14013757a  lea     rcx, [rsi+8]
0x14013757e  mov     [r14+20h], rsi
0x140137582  mov     r9, rbp
0x140137585  mov     r8d, 2CDh
0x14013758b  mov     rdx, r14
0x14013758e  call    RefObj_AddRefEx
0x140137593  lea     rcx, [r14+98h]; SpinLock
0x14013759a  call    cs:__imp_KeInitializeSpinLock
0x1401375a1  nop     dword ptr [rax+rax+00h]
0x1401375a6  lea     rax, [r14+2A0h]
0x1401375ad  mov     [r14+0A8h], r12
0x1401375b4  lea     rcx, [r14+108h]; Dpc
0x1401375bb  mov     [rax+8], rax
0x1401375bf  xor     r8d, r8d; DeferredContext
0x1401375c2  mov     [rax], rax
0x1401375c5  lea     rdx, ?ScoCxnS_SignalTimeoutDpc@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x1401375cc  call    cs:__imp_KeInitializeDpc
0x1401375d3  nop     dword ptr [rax+rax+00h]
0x1401375d8  lea     rcx, [r14+0C8h]; Timer
0x1401375df  lea     edx, [r12+1]; Type
0x1401375e4  call    cs:__imp_KeInitializeTimerEx
0x1401375eb  nop     dword ptr [rax+rax+00h]
0x1401375f0  lea     rcx, [r14+188h]; Dpc
0x1401375f7  xor     r8d, r8d; DeferredContext
0x1401375fa  lea     rdx, ?ScoCxnS_ConfigTimerDpc@@YAXPEAU_KDPC@@PEAX11@Z; DeferredRoutine
0x140137601  call    cs:__imp_KeInitializeDpc
0x140137608  nop     dword ptr [rax+rax+00h]
0x14013760d  lea     rcx, [r14+148h]; Timer
0x140137614  lea     edx, [r12+1]; Type
0x140137619  call    cs:__imp_KeInitializeTimerEx
0x140137620  nop     dword ptr [rax+rax+00h]
0x140137625  lea     rdx, [rsp+98h+arg_0]; unsigned int *
0x14013762d  mov     ecx, edi; unsigned int
0x14013762f  call    ?SCO_INIT_CLIENT_FLAGS@@YAXKPEAK@Z; SCO_INIT_CLIENT_FLAGS(ulong,ulong *)
0x140137634  mov     eax, [rsp+98h+arg_0]
0x14013763b  lea     rcx, [r14+28h]; struct HCI_CLIENT *
0x14013763f  mov     [rsp+98h+var_48], 2; unsigned int
0x140137647  lea     rdx, ?ScoCxnS_HciConnectCallback@@YAXPEAUHCI_CLIENT@@PEAUHCI_L2CAP_DATA@@JEEPEAU_GUID@@@Z; void (*)(struct HCI_CLIENT *, struct HCI_L2CAP_DATA *, int, unsigned __int8, unsigned __int8, struct _GUID *)
0x14013764e  mov     [rsp+98h+var_50], r12b; char
0x140137653  xor     r9d, r9d; int (*)(struct HCI_CLIENT *, struct HCI_L2CAP_DATA *, enum _LINK_PROPERTY_TYPE, unsigned __int8, void *)
0x140137656  mov     [rsp+98h+var_58], r12d; unsigned int
0x14013765b  xor     r8d, r8d; void (*)(struct HCI_CLIENT *, struct HCI_L2CAP_DATA *)
0x14013765e  mov     [rsp+98h+var_60], eax; unsigned int
0x140137662  mov     [rsp+98h+var_68], 3; enum _HCI_CLIENT_TYPE
0x14013766a  mov     [rsp+98h+var_70], rbx; struct _REF_OBJ *
0x14013766f  mov     qword ptr [rsp+98h+RemlockSize], r12; unsigned __int64 *
0x140137674  call    ?HCI_InitClientEx@@YAXPEAUHCI_CLIENT@@P6AX0PEAUHCI_L2CAP_DATA@@JEEPEAU_GUID@@@ZP6AX01@ZP6AJ01W4_LINK_PROPERTY_TYPE@@EPEAX@ZPEA_KPEAU_REF_OBJ@@W4_HCI_CLIENT_TYPE@@KKEK@Z; HCI_InitClientEx(HCI_CLIENT *,void (*)(HCI_CLIENT *,HCI_L2CAP_DATA *,long,uchar,uchar,_GUID *),void (*)(HCI_CLIENT *,HCI_L2CAP_DATA *),long (*)(HCI_CLIENT *,HCI_L2CAP_DATA *,_LINK_PROPERTY_TYPE,uchar,void *),unsigned __int64 *,_REF_OBJ *,_HCI_CLIENT_TYPE,ulong,ulong,uchar,ulong)
0x140137679  lea     rbx, [r14+250h]
0x140137680  lea     rdx, [rbx+10h]
0x140137684  mov     rcx, rbx
0x140137687  call    LockedList_Init
0x14013768c  lea     rax, ?ScoCxnS_SignalIrpCancel@@YAXPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z; ScoCxnS_SignalIrpCancel(_DEVICE_OBJECT *,_IRP *)
0x140137693  mov     [rbx+28h], rax
0x140137697  lea     rax, ?BthCompleteRequestExternal@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@J@Z; BthCompleteRequestExternal(_DEVICE_OBJECT *,_IRP *,long)
0x14013769e  mov     [rbx+30h], rax
0x1401376a2  mov     [rbx+40h], r12
0x1401376a6  mov     [rbx+38h], r12d
0x1401376aa  mov     [rbx+48h], r12b
0x1401376ae  mov     [rbx+3Ch], r12b
0x1401376b2  lea     rbx, [r14+3E0h]
0x1401376b9  lea     rdx, [rbx+10h]
0x1401376bd  mov     rcx, rbx
0x1401376c0  call    LockedList_Init
0x1401376c5  mov     byte ptr [rbx+30h], 1
0x1401376c9  mov     [rbx+28h], r12
0x1401376cd  lea     rbx, [r14+3A8h]
0x1401376d4  lea     rdx, [rbx+10h]
0x1401376d8  mov     rcx, rbx
0x1401376db  call    LockedList_Init
0x1401376e0  mov     [rbx+30h], r12b
0x1401376e4  mov     r9d, 311h; Line
0x1401376ea  mov     [rbx+28h], r12
0x1401376ee  mov     r8, rbp; File
0x1401376f1  mov     rcx, [rsi+20h]
0x1401376f5  mov     rdx, r14; Tag
0x1401376f8  add     rcx, 38h ; '8'; RemoveLock
0x1401376fc  mov     [rsp+98h+RemlockSize], 20h ; ' '; RemlockSize
0x140137704  call    cs:__imp_IoAcquireRemoveLockEx
0x14013770b  nop     dword ptr [rax+rax+00h]
0x140137710  lea     rsi, WPP_c82f5777c0b73a20e7817411fb777e73_Traceguids
0x140137717  mov     ebx, eax
0x140137719  lea     edi, [r12+4]
0x14013771e  test    eax, eax
0x140137720  jns     short loc_140137769
0x140137722  mov     r10, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140137729  mov     ecx, [r10+2Ch]
0x14013772d  test    cl, 8
0x140137730  jz      short loc_14013773B
0x140137732  cmp     byte ptr [r10+29h], 2
0x140137737  mov     dl, 1
0x140137739  jnb     short loc_14013773E
0x14013773b  mov     dl, r12b
0x14013773e  mov     r9, [r10+40h]
0x140137742  mov     r8b, 1
0x140137745  mov     rcx, [r10+18h]
0x140137749  mov     [rsp+98h+var_58], eax
0x14013774d  mov     qword ptr [rsp+98h+var_60], rsi
0x140137752  mov     word ptr [rsp+98h+var_68], 1Bh
0x140137759  mov     dword ptr [rsp+98h+var_70], edi
0x14013775d  mov     byte ptr [rsp+98h+RemlockSize], 2
0x140137762  call    WPP_RECORDER_AND_TRACE_SF_d
0x140137767  jmp     short loc_14013778B
0x140137769  or      dword ptr [r14+0A4h], 1
0x140137771  mov     eax, r12d
0x140137774  cmp     [rsp+98h+arg_20], 2
0x14013777c  mov     ebx, r12d
0x14013777f  setnz   al
0x140137782  inc     eax
0x140137784  mov     [r14+478h], eax
0x14013778b  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140137792  mov     eax, [rcx+2Ch]
0x140137795  test    al, 8
0x140137797  jz      short loc_1401377A1
0x140137799  mov     dl, 1
0x14013779b  cmp     [rcx+29h], dil
0x14013779f  jnb     short loc_1401377A4
0x1401377a1  mov     dl, r12b
0x1401377a4  mov     r9, [rcx+40h]
0x1401377a8  mov     r8b, 1
0x1401377ab  mov     rcx, [rcx+18h]
0x1401377af  mov     dword ptr [rsp+98h+var_50], ebx
0x1401377b3  mov     qword ptr [rsp+98h+var_58], r14
0x1401377b8  mov     qword ptr [rsp+98h+var_60], rsi
0x1401377bd  mov     word ptr [rsp+98h+var_68], 1Ch
0x1401377c4  mov     dword ptr [rsp+98h+var_70], edi
0x1401377c8  mov     byte ptr [rsp+98h+RemlockSize], dil
0x1401377cd  call    WPP_RECORDER_AND_TRACE_SF_qL
0x1401377d2  mov     eax, ebx
0x1401377d4  add     rsp, 68h
0x1401377d8  pop     r14
0x1401377da  pop     r12
0x1401377dc  pop     rdi
0x1401377dd  pop     rsi
0x1401377de  pop     rbp
0x1401377df  pop     rbx
0x1401377e0  retn
```
