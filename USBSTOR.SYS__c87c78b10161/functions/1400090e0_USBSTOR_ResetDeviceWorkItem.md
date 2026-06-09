# USBSTOR_ResetDeviceWorkItem

- ea: `0x1400090e0`
- end: `0x1400094a5`
- name: `USBSTOR_ResetDeviceWorkItem`
- size: `965`
- prototype: `IO_WORKITEM_ROUTINE_EX`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140003630`
- `0x140003b90`
- `0x140007ff0`
- `0x1400090e0`
- `0x14000a08c`
- `0x14000a210`
- `0x1400105e8`
- `0x140010664`

## import_xrefs

- `ntoskrnl!IoCancelIrp` at `0x14000917c`
- `ntoskrnl!IoCancelIrp` at `0x14000917c`
- `ntoskrnl!IofCompleteRequest` at `0x1400091ef`
- `ntoskrnl!IofCompleteRequest` at `0x1400091ef`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000919c`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000919c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009350`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400093eb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009350`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400093eb`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000923f`
- `ntoskrnl!KeDelayExecutionThread` at `0x14000923f`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000944b`
- `ntoskrnl!IoReleaseRemoveLockEx` at `0x14000944b`
- `ntoskrnl!KeLowerIrql` at `0x1400091fd`
- `ntoskrnl!KeLowerIrql` at `0x1400091fd`
- `ntoskrnl!KfRaiseIrql` at `0x1400091d8`
- `ntoskrnl!KfRaiseIrql` at `0x1400091d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009386`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009403`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009386`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009403`

## pseudocode

```c
void __fastcall USBSTOR_ResetDeviceWorkItem(struct _DEVICE_OBJECT *IoObject, _DWORD *Context, PIO_WORKITEM IoWorkItem)
{
  __int64 v5; // rdx
  char *DeviceExtension; // rdi
  int IsDeviceConnected; // esi
  __int64 v8; // r8
  KIRQL v9; // bl
  unsigned int i; // ebx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF
  struct _KLOCK_QUEUE_HANDLE v12; // [rsp+48h] [rbp-30h] BYREF
  union _LARGE_INTEGER Interval; // [rsp+80h] [rbp+8h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  USBSTOR_LogEntry(1464095570, IoObject, 0, 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 172, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  DeviceExtension = (char *)IoObject->DeviceExtension;
  IsDeviceConnected = 0;
  v8 = *((_QWORD *)DeviceExtension + 41);
  if ( v8 )
  {
    USBSTOR_LogEntry(828666738, IoObject, v8, 0);
    IoCancelIrp(*((PIRP *)DeviceExtension + 41));
    KeWaitForSingleObject(DeviceExtension + 336, Executive, 0, 0, 0);
    USBSTOR_LogEntry(845443954, IoObject, *((_QWORD *)DeviceExtension + 41), 0);
    if ( !Context )
      Context = *(_DWORD **)(*(_QWORD *)(*((_QWORD *)DeviceExtension + 41) + 184LL) + 16LL);
    v9 = KfRaiseIrql(2u);
    IofCompleteRequest(*((PIRP *)DeviceExtension + 41), 0);
    KeLowerIrql(v9);
    *((_QWORD *)DeviceExtension + 41) = 0;
  }
  for ( i = 0; i < 3; ++i )
  {
    if ( Context && Context[10] == 5 )
    {
      Interval.QuadPart = -1000000;
      KeDelayExecutionThread(0, 0, &Interval);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 173, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      IsDeviceConnected = -1073741823;
    }
    else
    {
      if ( !DeviceExtension[1876] )
      {
        IsDeviceConnected = USBSTOR_IsDeviceConnected(IoObject);
        if ( IsDeviceConnected < 0 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 174, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
          }
          break;
        }
      }
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 175, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      LOBYTE(v5) = DeviceExtension[1876];
      IsDeviceConnected = USBSTOR_ResetDevice(IoObject, v5);
      if ( IsDeviceConnected >= 0 )
      {
        USBSTOR_LogEntry(862221170, IoObject, 0, 0);
        break;
      }
    }
  }
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
  *((_DWORD *)DeviceExtension + 32) &= ~8u;
  if ( IsDeviceConnected < 0 )
  {
    USBSTOR_LogEntry(878998386, IoObject, 0, 0);
    *((_DWORD *)DeviceExtension + 32) |= 0x10u;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( !*((_DWORD *)DeviceExtension + 30) )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 176, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    *((_DWORD *)DeviceExtension + 30) = 1;
  }
  memset(&v12, 0, sizeof(v12));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &v12);
  *((_DWORD *)DeviceExtension + 32) &= ~0x20u;
  KeReleaseInStackQueuedSpinLock(&v12);
  if ( Context )
  {
    USBSTOR_LogEntry(895775602, IoObject, 0, 0);
    UsbStorPumpNextRequest(Context);
  }
  UsbStorStartNextPacket(IoObject);
  IoReleaseRemoveLockEx((PIO_REMOVE_LOCK)(DeviceExtension + 1832), USBSTOR_ResetDeviceWorkItem, 0x20u);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 177, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
}

```

## disassembly

```asm
0x1400090e0  mov     [rsp+arg_8], rbx
0x1400090e5  mov     [rsp+arg_10], rbp
0x1400090ea  push    rsi
0x1400090eb  push    rdi
0x1400090ec  push    r14
0x1400090ee  sub     rsp, 60h
0x1400090f2  mov     r14, rdx
0x1400090f5  mov     rbp, rcx
0x1400090f8  mov     rdx, rcx
0x1400090fb  xorps   xmm0, xmm0
0x1400090fe  xor     eax, eax
0x140009100  mov     ecx, 57445352h
0x140009105  xor     r9d, r9d
0x140009108  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14000910d  xor     r8d, r8d
0x140009110  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140009115  call    USBSTOR_LogEntry
0x14000911a  mov     rcx, cs:WPP_GLOBAL_Control
0x140009121  lea     rax, WPP_GLOBAL_Control
0x140009128  cmp     rcx, rax
0x14000912b  jz      short loc_14000914F
0x14000912d  mov     eax, [rcx+2Ch]
0x140009130  test    al, 1
0x140009132  jz      short loc_14000914F
0x140009134  cmp     byte ptr [rcx+29h], 5
0x140009138  jb      short loc_14000914F
0x14000913a  mov     rcx, [rcx+18h]
0x14000913e  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009145  mov     edx, 0ACh
0x14000914a  call    WPP_SF_
0x14000914f  mov     rdi, [rbp+40h]
0x140009153  xor     esi, esi
0x140009155  mov     r8, [rdi+148h]
0x14000915c  test    r8, r8
0x14000915f  jz      loc_140009210
0x140009165  xor     r9d, r9d
0x140009168  mov     rdx, rbp
0x14000916b  mov     ecx, 31647372h
0x140009170  call    USBSTOR_LogEntry
0x140009175  mov     rcx, [rdi+148h]; Irp
0x14000917c  call    cs:__imp_IoCancelIrp
0x140009183  nop     dword ptr [rax+rax+00h]
0x140009188  lea     rcx, [rdi+150h]; Object
0x14000918f  mov     [rsp+78h+Timeout], rsi; Timeout
0x140009194  xor     r9d, r9d; Alertable
0x140009197  xor     r8d, r8d; WaitMode
0x14000919a  xor     edx, edx; WaitReason
0x14000919c  call    cs:__imp_KeWaitForSingleObject
0x1400091a3  nop     dword ptr [rax+rax+00h]
0x1400091a8  mov     r8, [rdi+148h]
0x1400091af  xor     r9d, r9d
0x1400091b2  mov     rdx, rbp
0x1400091b5  mov     ecx, 32647372h
0x1400091ba  call    USBSTOR_LogEntry
0x1400091bf  test    r14, r14
0x1400091c2  jnz     short loc_1400091D6
0x1400091c4  mov     rax, [rdi+148h]
0x1400091cb  mov     rcx, [rax+0B8h]
0x1400091d2  mov     r14, [rcx+10h]
0x1400091d6  mov     cl, 2; NewIrql
0x1400091d8  call    cs:__imp_KfRaiseIrql
0x1400091df  nop     dword ptr [rax+rax+00h]
0x1400091e4  mov     rcx, [rdi+148h]; Irp
0x1400091eb  xor     edx, edx; PriorityBoost
0x1400091ed  mov     bl, al
0x1400091ef  call    cs:__imp_IofCompleteRequest
0x1400091f6  nop     dword ptr [rax+rax+00h]
0x1400091fb  mov     cl, bl; NewIrql
0x1400091fd  call    cs:__imp_KeLowerIrql
0x140009204  nop     dword ptr [rax+rax+00h]
0x140009209  mov     [rdi+148h], rsi
0x140009210  xor     ebx, ebx
0x140009212  cmp     ebx, 3
0x140009215  jnb     loc_140009341
0x14000921b  test    r14, r14
0x14000921e  jz      short loc_14000928A
0x140009220  cmp     dword ptr [r14+28h], 5
0x140009225  jnz     short loc_14000928A
0x140009227  lea     r8, [rsp+78h+Interval]; Interval
0x14000922f  mov     qword ptr [rsp+78h+Interval], 0FFFFFFFFFFF0BDC0h
0x14000923b  xor     edx, edx; Alertable
0x14000923d  xor     ecx, ecx; WaitMode
0x14000923f  call    cs:__imp_KeDelayExecutionThread
0x140009246  nop     dword ptr [rax+rax+00h]
0x14000924b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009252  lea     rax, WPP_GLOBAL_Control
0x140009259  cmp     rcx, rax
0x14000925c  jz      short loc_140009283
0x14000925e  mov     eax, [rcx+2Ch]
0x140009261  test    al, 1
0x140009263  jz      short loc_140009283
0x140009265  cmp     byte ptr [rcx+29h], 2
0x140009269  jb      short loc_140009283
0x14000926b  mov     rcx, [rcx+18h]
0x14000926f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009276  mov     edx, 0ADh
0x14000927b  mov     r9d, ebx
0x14000927e  call    WPP_SF_d
0x140009283  mov     esi, 0C0000001h
0x140009288  jmp     short loc_1400092ED
0x14000928a  cmp     byte ptr [rdi+754h], 0
0x140009291  jnz     short loc_1400092A1
0x140009293  mov     rcx, rbp
0x140009296  call    USBSTOR_IsDeviceConnected
0x14000929b  mov     esi, eax
0x14000929d  test    eax, eax
0x14000929f  js      short loc_1400092F4
0x1400092a1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092a8  lea     rax, WPP_GLOBAL_Control
0x1400092af  cmp     rcx, rax
0x1400092b2  jz      short loc_1400092D9
0x1400092b4  mov     eax, [rcx+2Ch]
0x1400092b7  test    al, 1
0x1400092b9  jz      short loc_1400092D9
0x1400092bb  cmp     byte ptr [rcx+29h], 2
0x1400092bf  jb      short loc_1400092D9
0x1400092c1  mov     rcx, [rcx+18h]
0x1400092c5  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400092cc  mov     edx, 0AFh
0x1400092d1  mov     r9d, ebx
0x1400092d4  call    WPP_SF_d
0x1400092d9  mov     dl, [rdi+754h]
0x1400092df  mov     rcx, rbp
0x1400092e2  call    USBSTOR_ResetDevice
0x1400092e7  mov     esi, eax
0x1400092e9  test    eax, eax
0x1400092eb  jns     short loc_14000932E
0x1400092ed  inc     ebx
0x1400092ef  jmp     loc_140009212
0x1400092f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1400092fb  lea     rax, WPP_GLOBAL_Control
0x140009302  cmp     rcx, rax
0x140009305  jz      short loc_140009341
0x140009307  mov     eax, [rcx+2Ch]
0x14000930a  test    al, 1
0x14000930c  jz      short loc_140009341
0x14000930e  cmp     byte ptr [rcx+29h], 2
0x140009312  jb      short loc_140009341
0x140009314  mov     rcx, [rcx+18h]
0x140009318  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000931f  mov     edx, 0AEh
0x140009324  mov     r9d, ebx
0x140009327  call    WPP_SF_d
0x14000932c  jmp     short loc_140009341
0x14000932e  xor     r9d, r9d
0x140009331  xor     r8d, r8d
0x140009334  mov     rdx, rbp
0x140009337  mov     ecx, 33647372h
0x14000933c  call    USBSTOR_LogEntry
0x140009341  lea     rbx, [rdi+90h]
0x140009348  mov     rcx, rbx; SpinLock
0x14000934b  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140009350  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009357  nop     dword ptr [rax+rax+00h]
0x14000935c  and     dword ptr [rdi+80h], 0FFFFFFF7h
0x140009363  test    esi, esi
0x140009365  jns     short loc_140009381
0x140009367  xor     r9d, r9d
0x14000936a  xor     r8d, r8d
0x14000936d  mov     rdx, rbp
0x140009370  mov     ecx, 34647372h
0x140009375  call    USBSTOR_LogEntry
0x14000937a  or      dword ptr [rdi+80h], 10h
0x140009381  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140009386  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000938d  nop     dword ptr [rax+rax+00h]
0x140009392  cmp     dword ptr [rdi+78h], 0
0x140009396  jnz     short loc_1400093D4
0x140009398  mov     rcx, cs:WPP_GLOBAL_Control
0x14000939f  lea     rax, WPP_GLOBAL_Control
0x1400093a6  cmp     rcx, rax
0x1400093a9  jz      short loc_1400093CD
0x1400093ab  mov     eax, [rcx+2Ch]
0x1400093ae  test    al, 1
0x1400093b0  jz      short loc_1400093CD
0x1400093b2  cmp     byte ptr [rcx+29h], 2
0x1400093b6  jb      short loc_1400093CD
0x1400093b8  mov     rcx, [rcx+18h]
0x1400093bc  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400093c3  mov     edx, 0B0h
0x1400093c8  call    WPP_SF_
0x1400093cd  mov     dword ptr [rdi+78h], 1
0x1400093d4  xorps   xmm0, xmm0
0x1400093d7  lea     rdx, [rsp+78h+var_30]; LockHandle
0x1400093dc  xor     eax, eax
0x1400093de  mov     rcx, rbx; SpinLock
0x1400093e1  movups  xmmword ptr [rsp+78h+var_30.LockQueue.Next], xmm0
0x1400093e6  mov     qword ptr [rsp+78h+var_30.OldIrql], rax
0x1400093eb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400093f2  nop     dword ptr [rax+rax+00h]
0x1400093f7  and     dword ptr [rdi+80h], 0FFFFFFDFh
0x1400093fe  lea     rcx, [rsp+78h+var_30]; LockHandle
0x140009403  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000940a  nop     dword ptr [rax+rax+00h]
0x14000940f  test    r14, r14
0x140009412  jz      short loc_14000942F
0x140009414  xor     r9d, r9d
0x140009417  xor     r8d, r8d
0x14000941a  mov     rdx, rbp
0x14000941d  mov     ecx, 35647372h
0x140009422  call    USBSTOR_LogEntry
0x140009427  mov     rcx, r14
0x14000942a  call    UsbStorPumpNextRequest
0x14000942f  mov     rcx, rbp; DeviceObject
0x140009432  call    UsbStorStartNextPacket
0x140009437  lea     rcx, [rdi+728h]; RemoveLock
0x14000943e  mov     r8d, 20h ; ' '; RemlockSize
0x140009444  lea     rdx, USBSTOR_ResetDeviceWorkItem; Tag
0x14000944b  call    cs:__imp_IoReleaseRemoveLockEx
0x140009452  nop     dword ptr [rax+rax+00h]
0x140009457  mov     rcx, cs:WPP_GLOBAL_Control
0x14000945e  lea     rax, WPP_GLOBAL_Control
0x140009465  cmp     rcx, rax
0x140009468  jz      short loc_14000948F
0x14000946a  mov     eax, [rcx+2Ch]
0x14000946d  test    al, 1
0x14000946f  jz      short loc_14000948F
0x140009471  cmp     byte ptr [rcx+29h], 5
0x140009475  jb      short loc_14000948F
0x140009477  mov     rcx, [rcx+18h]
0x14000947b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009482  mov     edx, 0B1h
0x140009487  mov     r9d, esi
0x14000948a  call    WPP_SF_d
0x14000948f  lea     r11, [rsp+78h+var_18]
0x140009494  mov     rbx, [r11+28h]
0x140009498  mov     rbp, [r11+30h]
0x14000949c  mov     rsp, r11
0x14000949f  pop     r14
0x1400094a1  pop     rdi
0x1400094a2  pop     rsi
0x1400094a3  retn
```
