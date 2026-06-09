# USBSTOR_CbwCompletion

- ea: `0x140001de0`
- end: `0x1400023a4`
- name: `USBSTOR_CbwCompletion`
- size: `1476`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x140001008`
- `0x140001de0`
- `0x140002a70`
- `0x140002fd0`
- `0x140003630`
- `0x140004910`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400021cb`
- `ntoskrnl!KeSetEvent` at `0x1400021cb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001e42`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001efa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001f7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002064`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400021fb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001e42`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001efa`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140001f7e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140002064`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400021fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001ea0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001f2b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001fdc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400020c2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002182`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002255`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001ea0`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001f2b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140001fdc`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400020c2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002182`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140002255`

## pseudocode

```c
__int64 __fastcall USBSTOR_CbwCompletion(_QWORD *a1, IRP *a2)
{
  __int64 Status; // rdi
  __int64 v5; // rax
  _DWORD *v6; // rdi
  void *v7; // r12
  __int64 v8; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // r15
  PIO_SECURITY_CONTEXT SecurityContext; // r14
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebp
  __int64 v14; // r8
  __int64 v15; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  __int64 v19; // r8
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-48h] BYREF

  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 147, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( P )
  {
    Status = a2->IoStatus.Status;
    KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
    *(_DWORD *)qword_14001A190 = 1129792067;
    *(_QWORD *)(qword_14001A190 + 8) = a1;
    *(_QWORD *)(qword_14001A190 + 16) = a2;
    *(_QWORD *)(qword_14001A190 + 24) = Status;
    if ( qword_14001A190 <= (unsigned __int64)P )
      v5 = qword_14001A198 - 32;
    else
      v5 = qword_14001A190 - 32;
    qword_14001A190 = v5;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  v6 = (_DWORD *)a1[8];
  if ( *v6 == 558842960 )
  {
    a1 = (_QWORD *)*((_QWORD *)v6 + 2);
    v7 = v6;
    v6 = (_DWORD *)a1[8];
  }
  else
  {
    v7 = 0;
    if ( *v6 != 558842950 )
    {
      v6 = 0;
      a1 = 0;
    }
  }
  v8 = a1[8];
  CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
  memset(&LockHandle, 0, sizeof(LockHandle));
  SecurityContext = CurrentStackLocation->Parameters.Create.SecurityContext;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v8 + 144), &LockHandle);
  *(_DWORD *)(v8 + 128) &= ~2u;
  if ( (*(_DWORD *)(v8 + 128) & 8) != 0 )
  {
    USBSTOR_LogEntry(827609667, a1, a2, SecurityContext);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    v17 = *(_QWORD *)(v8 + 1168);
    a2->Tail.Overlay.CurrentStackLocation->Parameters.WMI.ProviderId = v17;
    a2->IoStatus.Status = -1073741643;
    a2->IoStatus.Information = 0;
    *(_BYTE *)(v17 + 3) = 9;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v17);
    KeSetEvent((PRKEVENT)(v8 + 336), 0, 0);
    memset(&LockHandle, 0, sizeof(LockHandle));
    if ( P )
    {
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      *(_DWORD *)qword_14001A190 = 829907555;
      *(_QWORD *)(qword_14001A190 + 8) = a1;
      *(_QWORD *)(qword_14001A190 + 16) = a2;
      *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
      if ( qword_14001A190 <= (unsigned __int64)P )
        v18 = qword_14001A198 - 32;
      else
        v18 = qword_14001A190 - 32;
      qword_14001A190 = v18;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 148, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225494LL;
  }
  else
  {
    *(_QWORD *)(v8 + 328) = 0;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    if ( a2->IoStatus.Status >= 0 )
    {
      if ( a2->MdlAddress && (HIDWORD(SecurityContext->AccessState) & 0xC0) != 0
        || SecurityContext != *((PIO_SECURITY_CONTEXT *)v6 + 146) )
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( P )
        {
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          *(_DWORD *)qword_14001A190 = 863461987;
          *(_QWORD *)(qword_14001A190 + 8) = a1;
          *(_QWORD *)(qword_14001A190 + 16) = a2;
          *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
          if ( qword_14001A190 <= (unsigned __int64)P )
            v11 = qword_14001A198 - 32;
          else
            v11 = qword_14001A190 - 32;
          qword_14001A190 = v11;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        v12 = USBSTOR_DataTransfer(a1, a2);
        v13 = v12;
        if ( v12 < 0 )
        {
          v14 = *((_QWORD *)v6 + 146);
          CurrentStackLocation->Parameters.WMI.ProviderId = v14;
          a2->IoStatus.Status = v12;
          a2->IoStatus.Information = 0;
          *(_BYTE *)(v14 + 3) = 4;
          USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v14);
          USBSTOR_QueueResetDevice(a1, v7);
          goto LABEL_26;
        }
      }
      else
      {
        memset(&LockHandle, 0, sizeof(LockHandle));
        if ( P )
        {
          KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
          *(_DWORD *)qword_14001A190 = 880239203;
          *(_QWORD *)(qword_14001A190 + 8) = a1;
          *(_QWORD *)(qword_14001A190 + 16) = a2;
          *(_QWORD *)(qword_14001A190 + 24) = SecurityContext;
          if ( qword_14001A190 <= (unsigned __int64)P )
            v15 = qword_14001A198 - 32;
          else
            v15 = qword_14001A190 - 32;
          qword_14001A190 = v15;
          KeReleaseInStackQueuedSpinLock(&LockHandle);
        }
        BYTE3(SecurityContext->SecurityQos) = 1;
        USBSTOR_CswTransfer(a1, a2);
      }
      v13 = -1073741802;
LABEL_26:
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 151, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
      return v13;
    }
    USBSTOR_LogEntry(846684771, a2->IoStatus.Status, (int)v6[99], 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        149,
        WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
        (unsigned int)a2->IoStatus.Status,
        v6[99]);
    }
    v19 = *((_QWORD *)v6 + 146);
    CurrentStackLocation->Parameters.WMI.ProviderId = v19;
    a2->IoStatus.Status = -1073741435;
    a2->IoStatus.Information = 0;
    *(_BYTE *)(v19 + 3) = 14;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, v19);
    USBSTOR_QueueResetDevice(a1, v7);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 150, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 3221225861LL;
  }
}

```

## disassembly

```asm
0x140001de0  mov     [rsp+arg_8], rbx
0x140001de5  mov     [rsp+arg_10], rbp
0x140001dea  push    rsi
0x140001deb  push    rdi
0x140001dec  push    r13
0x140001dee  push    r14
0x140001df0  push    r15
0x140001df2  sub     rsp, 50h
0x140001df6  mov     rsi, rdx
0x140001df9  mov     rbx, rcx
0x140001dfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140001e03  lea     r13, WPP_GLOBAL_Control
0x140001e0a  cmp     rcx, r13
0x140001e0d  jz      short loc_140001E1A
0x140001e0f  mov     eax, [rcx+2Ch]
0x140001e12  test    al, 1
0x140001e14  jnz     loc_140002284
0x140001e1a  xor     eax, eax
0x140001e1c  xorps   xmm0, xmm0
0x140001e1f  cmp     cs:P, rax
0x140001e26  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140001e2b  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140001e30  jz      short loc_140001EAC
0x140001e32  movsxd  rdi, dword ptr [rsi+30h]
0x140001e36  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140001e3b  lea     rcx, SpinLock; SpinLock
0x140001e42  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001e49  nop     dword ptr [rax+rax+00h]
0x140001e4e  mov     rax, cs:qword_14001A190
0x140001e55  mov     dword ptr [rax], 43574243h
0x140001e5b  mov     rax, cs:qword_14001A190
0x140001e62  mov     [rax+8], rbx
0x140001e66  mov     rax, cs:qword_14001A190
0x140001e6d  mov     [rax+10h], rsi
0x140001e71  mov     rax, cs:qword_14001A190
0x140001e78  mov     [rax+18h], rdi
0x140001e7c  mov     rax, cs:qword_14001A190
0x140001e83  cmp     rax, cs:P
0x140001e8a  jbe     loc_14000211A
0x140001e90  sub     rax, 20h ; ' '
0x140001e94  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140001e99  mov     cs:qword_14001A190, rax
0x140001ea0  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001ea7  nop     dword ptr [rax+rax+00h]
0x140001eac  mov     rdi, [rbx+40h]
0x140001eb0  mov     [rsp+78h+arg_0], r12
0x140001eb8  mov     eax, [rdi]
0x140001eba  cmp     eax, 214F4450h
0x140001ebf  jnz     loc_1400022A8
0x140001ec5  mov     rbx, [rdi+10h]
0x140001ec9  mov     r12, rdi
0x140001ecc  mov     rdi, [rbx+40h]
0x140001ed0  mov     rbp, [rbx+40h]
0x140001ed4  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140001ed9  mov     r15, [rsi+0B8h]
0x140001ee0  xorps   xmm0, xmm0
0x140001ee3  xor     eax, eax
0x140001ee5  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140001eea  lea     rcx, [rbp+90h]; SpinLock
0x140001ef1  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140001ef6  mov     r14, [r15+8]
0x140001efa  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001f01  nop     dword ptr [rax+rax+00h]
0x140001f06  and     dword ptr [rbp+80h], 0FFFFFFFDh
0x140001f0d  mov     eax, [rbp+80h]
0x140001f13  test    al, 8
0x140001f15  jnz     loc_14000216A
0x140001f1b  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140001f20  mov     qword ptr [rbp+148h], 0
0x140001f2b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001f32  nop     dword ptr [rax+rax+00h]
0x140001f37  movsxd  rax, dword ptr [rsi+30h]
0x140001f3b  test    eax, eax
0x140001f3d  js      loc_1400022E3
0x140001f43  cmp     qword ptr [rsi+8], 0
0x140001f48  jz      loc_140002033
0x140001f4e  mov     eax, [r14+0Ch]
0x140001f52  test    al, 0C0h
0x140001f54  jz      loc_140002033
0x140001f5a  xor     eax, eax
0x140001f5c  xorps   xmm0, xmm0
0x140001f5f  cmp     cs:P, rax
0x140001f66  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140001f6b  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140001f70  jz      short loc_140001FE8
0x140001f72  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x140001f77  lea     rcx, SpinLock; SpinLock
0x140001f7e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140001f85  nop     dword ptr [rax+rax+00h]
0x140001f8a  mov     rax, cs:qword_14001A190
0x140001f91  mov     dword ptr [rax], 33776263h
0x140001f97  mov     rax, cs:qword_14001A190
0x140001f9e  mov     [rax+8], rbx
0x140001fa2  mov     rax, cs:qword_14001A190
0x140001fa9  mov     [rax+10h], rsi
0x140001fad  mov     rax, cs:qword_14001A190
0x140001fb4  mov     [rax+18h], r14
0x140001fb8  mov     rax, cs:qword_14001A190
0x140001fbf  cmp     rax, cs:P
0x140001fc6  jbe     loc_14000215A
0x140001fcc  sub     rax, 20h ; ' '
0x140001fd0  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140001fd5  mov     cs:qword_14001A190, rax
0x140001fdc  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140001fe3  nop     dword ptr [rax+rax+00h]
0x140001fe8  mov     rdx, rsi; Irp
0x140001feb  mov     rcx, rbx; Object
0x140001fee  call    USBSTOR_DataTransfer
0x140001ff3  mov     ebp, eax
0x140001ff5  test    eax, eax
0x140001ff7  jns     loc_1400020DE
0x140001ffd  mov     r8, [rdi+490h]
0x140002004  mov     rdx, rsi
0x140002007  mov     [r15+8], r8
0x14000200b  mov     rcx, rbx; Object
0x14000200e  mov     [rsi+30h], eax
0x140002011  mov     qword ptr [rsi+38h], 0
0x140002019  mov     byte ptr [r8+3], 4
0x14000201e  call    USBSTOR_TranslateCDBComplete
0x140002023  mov     rdx, r12; Context
0x140002026  mov     rcx, rbx; Object
0x140002029  call    USBSTOR_QueueResetDevice
0x14000202e  jmp     loc_1400020E3
0x140002033  cmp     r14, [rdi+490h]
0x14000203a  jnz     loc_140001F5A
0x140002040  xor     eax, eax
0x140002042  xorps   xmm0, xmm0
0x140002045  cmp     cs:P, rax
0x14000204c  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x140002051  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x140002056  jz      short loc_1400020CE
0x140002058  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14000205d  lea     rcx, SpinLock; SpinLock
0x140002064  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000206b  nop     dword ptr [rax+rax+00h]
0x140002070  mov     rax, cs:qword_14001A190
0x140002077  mov     dword ptr [rax], 34776263h
0x14000207d  mov     rax, cs:qword_14001A190
0x140002084  mov     [rax+8], rbx
0x140002088  mov     rax, cs:qword_14001A190
0x14000208f  mov     [rax+10h], rsi
0x140002093  mov     rax, cs:qword_14001A190
0x14000209a  mov     [rax+18h], r14
0x14000209e  mov     rax, cs:qword_14001A190
0x1400020a5  cmp     rax, cs:P
0x1400020ac  jbe     loc_14000214A
0x1400020b2  sub     rax, 20h ; ' '
0x1400020b6  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x1400020bb  mov     cs:qword_14001A190, rax
0x1400020c2  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400020c9  nop     dword ptr [rax+rax+00h]
0x1400020ce  mov     rdx, rsi; Irp
0x1400020d1  mov     byte ptr [r14+3], 1
0x1400020d6  mov     rcx, rbx; Object
0x1400020d9  call    USBSTOR_CswTransfer
0x1400020de  mov     ebp, 0C0000016h
0x1400020e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1400020ea  cmp     rcx, r13
0x1400020ed  jz      short loc_1400020F6
0x1400020ef  mov     eax, [rcx+2Ch]
0x1400020f2  test    al, 1
0x1400020f4  jnz     short loc_14000212A
0x1400020f6  mov     eax, ebp
0x1400020f8  mov     r12, [rsp+78h+arg_0]
0x140002100  lea     r11, [rsp+78h+var_28]
0x140002105  mov     rbx, [r11+38h]
0x140002109  mov     rbp, [r11+40h]
0x14000210d  mov     rsp, r11
0x140002110  pop     r15
0x140002112  pop     r14
0x140002114  pop     r13
0x140002116  pop     rdi
0x140002117  pop     rsi
0x140002118  retn
0x14000211a  mov     rax, cs:qword_14001A198
0x140002121  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002125  jmp     loc_140001E94
0x14000212a  cmp     byte ptr [rcx+29h], 5
0x14000212e  jb      short loc_1400020F6
0x140002130  mov     rcx, [rcx+18h]
0x140002134  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000213b  mov     edx, 97h
0x140002140  mov     r9d, ebp
0x140002143  call    WPP_SF_d
0x140002148  jmp     short loc_1400020F6
0x14000214a  mov     rax, cs:qword_14001A198
0x140002151  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002155  jmp     loc_1400020B6
0x14000215a  mov     rax, cs:qword_14001A198
0x140002161  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002165  jmp     loc_140001FD0
0x14000216a  mov     r9, r14
0x14000216d  mov     r8, rsi
0x140002170  mov     rdx, rbx
0x140002173  mov     ecx, 31545243h
0x140002178  call    USBSTOR_LogEntry
0x14000217d  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x140002182  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140002189  nop     dword ptr [rax+rax+00h]
0x14000218e  mov     r8, [rbp+490h]
0x140002195  mov     rdx, rsi
0x140002198  mov     rax, [rsi+0B8h]
0x14000219f  mov     rcx, rbx; Object
0x1400021a2  mov     [rax+8], r8
0x1400021a6  mov     dword ptr [rsi+30h], 0C00000B5h
0x1400021ad  mov     qword ptr [rsi+38h], 0
0x1400021b5  mov     byte ptr [r8+3], 9
0x1400021ba  call    USBSTOR_TranslateCDBComplete
0x1400021bf  lea     rcx, [rbp+150h]; Event
0x1400021c6  xor     r8d, r8d; Wait
0x1400021c9  xor     edx, edx; Increment
0x1400021cb  call    cs:__imp_KeSetEvent
0x1400021d2  nop     dword ptr [rax+rax+00h]
0x1400021d7  xor     eax, eax
0x1400021d9  xorps   xmm0, xmm0
0x1400021dc  cmp     cs:P, rax
0x1400021e3  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x1400021e8  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x1400021ed  jz      short loc_140002261
0x1400021ef  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x1400021f4  lea     rcx, SpinLock; SpinLock
0x1400021fb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140002202  nop     dword ptr [rax+rax+00h]
0x140002207  mov     rax, cs:qword_14001A190
0x14000220e  mov     dword ptr [rax], 31776263h
0x140002214  mov     rax, cs:qword_14001A190
0x14000221b  mov     [rax+8], rbx
0x14000221f  mov     rax, cs:qword_14001A190
0x140002226  mov     [rax+10h], rsi
0x14000222a  mov     rax, cs:qword_14001A190
0x140002231  mov     [rax+18h], r14
0x140002235  mov     rax, cs:qword_14001A190
0x14000223c  cmp     rax, cs:P
0x140002243  jbe     short loc_140002277
0x140002245  sub     rax, 20h ; ' '
0x140002249  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14000224e  mov     cs:qword_14001A190, rax
0x140002255  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000225c  nop     dword ptr [rax+rax+00h]
0x140002261  mov     rcx, cs:WPP_GLOBAL_Control
0x140002268  cmp     rcx, r13
0x14000226b  jnz     short loc_1400022BF
0x14000226d  mov     eax, 0C0000016h
0x140002272  jmp     loc_1400020F8
0x140002277  mov     rax, cs:qword_14001A198
0x14000227e  add     rax, 0FFFFFFFFFFFFFFE0h
0x140002282  jmp     short loc_140002249
0x140002284  cmp     byte ptr [rcx+29h], 5
0x140002288  jb      loc_140001E1A
0x14000228e  mov     rcx, [rcx+18h]
0x140002292  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002299  mov     edx, 93h
0x14000229e  call    WPP_SF_
0x1400022a3  jmp     loc_140001E1A
0x1400022a8  xor     r12d, r12d
0x1400022ab  cmp     eax, 214F4446h
0x1400022b0  jz      loc_140001ED0
0x1400022b6  xor     edi, edi
0x1400022b8  xor     ebx, ebx
0x1400022ba  jmp     loc_140001ED0
0x1400022bf  mov     eax, [rcx+2Ch]
0x1400022c2  test    al, 1
0x1400022c4  jz      short loc_14000226D
0x1400022c6  cmp     byte ptr [rcx+29h], 2
0x1400022ca  jb      short loc_14000226D
0x1400022cc  mov     rcx, [rcx+18h]
0x1400022d0  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400022d7  mov     edx, 94h
0x1400022dc  call    WPP_SF_
0x1400022e1  jmp     short loc_14000226D
0x1400022e3  movsxd  r8, dword ptr [rdi+18Ch]
0x1400022ea  mov     rdx, rax
0x1400022ed  xor     r9d, r9d
0x1400022f0  mov     ecx, 32776263h
0x1400022f5  call    USBSTOR_LogEntry
0x1400022fa  mov     rcx, cs:WPP_GLOBAL_Control
0x140002301  cmp     rcx, r13
0x140002304  jz      short loc_140002336
0x140002306  mov     eax, [rcx+2Ch]
0x140002309  test    al, 1
0x14000230b  jz      short loc_140002336
0x14000230d  cmp     byte ptr [rcx+29h], 2
0x140002311  jb      short loc_140002336
0x140002313  mov     eax, [rdi+18Ch]
0x140002319  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140002320  mov     r9d, [rsi+30h]
0x140002324  mov     edx, 95h
0x140002329  mov     rcx, [rcx+18h]
0x14000232d  mov     [rsp+78h+var_58], eax
0x140002331  call    WPP_SF_DD
0x140002336  mov     r8, [rdi+490h]
0x14000233d  mov     rdx, rsi
0x140002340  mov     [r15+8], r8
0x140002344  mov     rcx, rbx; Object
0x140002347  mov     dword ptr [rsi+30h], 0C0000185h
0x14000234e  mov     qword ptr [rsi+38h], 0
0x140002356  mov     byte ptr [r8+3], 0Eh
0x14000235b  call    USBSTOR_TranslateCDBComplete
0x140002360  mov     rdx, r12; Context
0x140002363  mov     rcx, rbx; Object
  ... truncated ...
```
