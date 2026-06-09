# USBSTOR_ClientCdbCompletion

- ea: `0x140009860`
- end: `0x140009ca3`
- name: `USBSTOR_ClientCdbCompletion`
- size: `1091`
- prototype: ``
- caller_count: `0`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140003630`
- `0x140003b90`
- `0x140004910`
- `0x140007ff0`
- `0x140009860`
- `0x140009f90`
- `0x14000a3f4`
- `0x14000ea94`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140011ec8`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009a6a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ab0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009c22`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009a6a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009ab0`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009c22`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009a82`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ac8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c3a`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009a82`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009ac8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009c3a`

## pseudocode

```c
__int64 __fastcall USBSTOR_ClientCdbCompletion(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  unsigned int v2; // ebx
  _DWORD *DeviceExtension; // r15
  void *v6; // r13
  __int64 SecurityContext; // r14
  int v9; // eax
  int v10; // eax
  unsigned int v11; // r12d
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v13; // [rsp+48h] [rbp-20h] BYREF

  v2 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 96, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1128416323, a1, a2, a2->IoStatus.Status);
  DeviceExtension = a1->DeviceExtension;
  if ( *DeviceExtension == 558842960 )
  {
    a1 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
    v6 = DeviceExtension;
    DeviceExtension = a1->DeviceExtension;
  }
  else
  {
    v6 = 0;
    if ( *DeviceExtension != 558842950 )
    {
      DeviceExtension = 0;
      a1 = 0;
    }
  }
  SecurityContext = (__int64)a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( (unsigned __int8)USBSTOR_CheckRequestTimeOut(a1) )
  {
    USBSTOR_LogEntry(828531811, a1, a2, SecurityContext);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 97, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 0;
  }
  if ( a2->IoStatus.Status >= 0 )
  {
    if ( a2->MdlAddress )
    {
      USBSTOR_LogEntry(912417891, a1, a2, SecurityContext);
      v10 = USBSTOR_IssueClientBulkRequest(a1, a2);
      v11 = v10;
      if ( v10 < 0 )
      {
        a2->IoStatus.Status = v10;
        a2->IoStatus.Information = 0;
        *(_BYTE *)(SecurityContext + 3) = 4;
        USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
        USBSTOR_QueueResetDevice(a1, v6);
        v2 = v11;
        goto LABEL_38;
      }
    }
    else
    {
      if ( !*((_QWORD *)DeviceExtension + 14) )
      {
        USBSTOR_LogEntry(945972323, a1, a2, SecurityContext);
        a2->IoStatus.Status = 0;
        a2->IoStatus.Information = 0;
        *(_BYTE *)(SecurityContext + 3) = 1;
        USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
        memset(&v13, 0, sizeof(v13));
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &v13);
        DeviceExtension[32] &= ~0x20u;
        KeReleaseInStackQueuedSpinLock(&v13);
        UsbStorPumpNextRequest(v6);
        UsbStorStartNextPacket(a1);
LABEL_38:
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 100, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
        }
        return v2;
      }
      USBSTOR_LogEntry(929195107, a1, a2, SecurityContext);
      *(_BYTE *)(SecurityContext + 3) = 1;
      USBSTOR_IssueInterruptRequest(a1, a2);
    }
    v2 = -1073741802;
    goto LABEL_38;
  }
  USBSTOR_LogEntry(845309027, a2->IoStatus.Status, (int)DeviceExtension[99], 0);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_DD(
      WPP_GLOBAL_Control->AttachedDevice,
      98,
      WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      (unsigned int)a2->IoStatus.Status,
      DeviceExtension[99]);
  }
  if ( (DeviceExtension[99] & 0xFFFFFFF) == 4 )
  {
    v9 = *(_DWORD *)(SecurityContext + 12);
    *(_WORD *)(SecurityContext + 3) = 516;
    *(_DWORD *)(SecurityContext + 16) = 0;
    if ( (v9 & 0x20) == 0 && *(_BYTE *)(SecurityContext + 11) && *(_QWORD *)(SecurityContext + 32) )
    {
      USBSTOR_LogEntry(862086243, a1, a2, SecurityContext);
      USBSTOR_IssueRequestSenseCdb(a1, a2, 0);
      return 3221225494LL;
    }
    USBSTOR_LogEntry(878863459, a1, a2, SecurityContext);
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741435;
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
    DeviceExtension[32] |= 4u;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
    memset(&v13, 0, sizeof(v13));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &v13);
    DeviceExtension[32] &= ~0x20u;
    KeReleaseInStackQueuedSpinLock(&v13);
    UsbStorPumpNextRequest(v6);
    UsbStorStartNextPacket(a1);
  }
  else
  {
    USBSTOR_LogEntry(895640675, a1, a2, SecurityContext);
    a2->IoStatus.Information = 0;
    a2->IoStatus.Status = -1073741435;
    *(_BYTE *)(SecurityContext + 3) = 14;
    USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
    USBSTOR_QueueResetDevice(a1, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 99, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
  }
  return 3221225861LL;
}

```

## disassembly

```asm
0x140009860  push    rbp
0x140009862  push    rbx
0x140009863  push    rsi
0x140009864  push    rdi
0x140009865  push    r12
0x140009867  push    r13
0x140009869  push    r14
0x14000986b  push    r15
0x14000986d  mov     rbp, rsp
0x140009870  sub     rsp, 68h
0x140009874  xor     eax, eax
0x140009876  xorps   xmm0, xmm0
0x140009879  xor     ebx, ebx
0x14000987b  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x14000987f  mov     [rbp+arg_0], ebx
0x140009882  mov     rdi, rdx
0x140009885  mov     rsi, rcx
0x140009888  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x14000988c  mov     rcx, cs:WPP_GLOBAL_Control
0x140009893  lea     rax, WPP_GLOBAL_Control
0x14000989a  mov     r12b, 1
0x14000989d  cmp     rcx, rax
0x1400098a0  jz      short loc_1400098C3
0x1400098a2  mov     eax, [rcx+2Ch]
0x1400098a5  test    r12b, al
0x1400098a8  jz      short loc_1400098C3
0x1400098aa  cmp     byte ptr [rcx+29h], 5
0x1400098ae  jb      short loc_1400098C3
0x1400098b0  mov     rcx, [rcx+18h]
0x1400098b4  lea     edx, [rbx+60h]
0x1400098b7  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400098be  call    WPP_SF_
0x1400098c3  movsxd  r9, dword ptr [rdi+30h]
0x1400098c7  mov     r8, rdi
0x1400098ca  mov     rdx, rsi
0x1400098cd  mov     ecx, 43424443h
0x1400098d2  call    USBSTOR_LogEntry
0x1400098d7  mov     r15, [rsi+40h]
0x1400098db  mov     eax, [r15]
0x1400098de  cmp     eax, 214F4450h
0x1400098e3  jnz     short loc_1400098F2
0x1400098e5  mov     rsi, [r15+10h]
0x1400098e9  mov     r13, r15
0x1400098ec  mov     r15, [rsi+40h]
0x1400098f0  jmp     short loc_140009902
0x1400098f2  mov     r13, rbx
0x1400098f5  cmp     eax, 214F4446h
0x1400098fa  jz      short loc_140009902
0x1400098fc  mov     r15, rbx
0x1400098ff  mov     rsi, rbx
0x140009902  mov     rax, [rdi+0B8h]
0x140009909  lea     r9, [rbp+arg_0]
0x14000990d  mov     rdx, rdi
0x140009910  mov     rcx, rsi; Object
0x140009913  mov     r14, [rax+8]
0x140009917  mov     r8, r14
0x14000991a  call    USBSTOR_CheckRequestTimeOut
0x14000991f  test    al, al
0x140009921  jz      short loc_140009974
0x140009923  mov     r9, r14
0x140009926  mov     r8, rdi
0x140009929  mov     rdx, rsi
0x14000992c  mov     ecx, 31626463h
0x140009931  call    USBSTOR_LogEntry
0x140009936  mov     rcx, cs:WPP_GLOBAL_Control
0x14000993d  lea     rax, WPP_GLOBAL_Control
0x140009944  cmp     rcx, rax
0x140009947  jz      short loc_14000996C
0x140009949  mov     eax, [rcx+2Ch]
0x14000994c  test    r12b, al
0x14000994f  jz      short loc_14000996C
0x140009951  cmp     byte ptr [rcx+29h], 2
0x140009955  jb      short loc_14000996C
0x140009957  mov     rcx, [rcx+18h]
0x14000995b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009962  mov     edx, 61h ; 'a'
0x140009967  call    WPP_SF_
0x14000996c  mov     eax, [rbp+arg_0]
0x14000996f  jmp     loc_140009C91
0x140009974  movsxd  rax, dword ptr [rdi+30h]
0x140009978  test    eax, eax
0x14000997a  jns     loc_140009B62
0x140009980  movsxd  r8, dword ptr [r15+18Ch]
0x140009987  mov     rdx, rax
0x14000998a  xor     r9d, r9d
0x14000998d  mov     ecx, 32626463h
0x140009992  call    USBSTOR_LogEntry
0x140009997  mov     rcx, cs:WPP_GLOBAL_Control
0x14000999e  lea     rax, WPP_GLOBAL_Control
0x1400099a5  cmp     rcx, rax
0x1400099a8  jz      short loc_1400099DC
0x1400099aa  mov     eax, [rcx+2Ch]
0x1400099ad  test    r12b, al
0x1400099b0  jz      short loc_1400099DC
0x1400099b2  cmp     byte ptr [rcx+29h], 2
0x1400099b6  jb      short loc_1400099DC
0x1400099b8  mov     eax, [r15+18Ch]
0x1400099bf  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400099c6  mov     r9d, [rdi+30h]
0x1400099ca  mov     edx, 62h ; 'b'
0x1400099cf  mov     rcx, [rcx+18h]
0x1400099d3  mov     [rsp+68h+var_48], eax
0x1400099d7  call    WPP_SF_DD
0x1400099dc  mov     eax, [r15+18Ch]
0x1400099e3  and     eax, 0FFFFFFFh
0x1400099e8  cmp     eax, 4
0x1400099eb  jnz     loc_140009AEC
0x1400099f1  mov     eax, [r14+0Ch]
0x1400099f5  mov     word ptr [r14+3], 204h
0x1400099fc  mov     [r14+10h], ebx
0x140009a00  test    al, 20h
0x140009a02  jnz     short loc_140009A3B
0x140009a04  cmp     [r14+0Bh], bl
0x140009a08  jz      short loc_140009A3B
0x140009a0a  cmp     [r14+20h], rbx
0x140009a0e  jz      short loc_140009A3B
0x140009a10  mov     r9, r14
0x140009a13  mov     r8, rdi
0x140009a16  mov     rdx, rsi
0x140009a19  mov     ecx, 33626463h
0x140009a1e  call    USBSTOR_LogEntry
0x140009a23  xor     r8d, r8d; __int64
0x140009a26  mov     rdx, rdi; Irp
0x140009a29  mov     rcx, rsi; Object
0x140009a2c  call    USBSTOR_IssueRequestSenseCdb
0x140009a31  mov     eax, 0C0000016h
0x140009a36  jmp     loc_140009C91
0x140009a3b  mov     r9, r14
0x140009a3e  mov     r8, rdi
0x140009a41  mov     rdx, rsi
0x140009a44  mov     ecx, 34626463h
0x140009a49  call    USBSTOR_LogEntry
0x140009a4e  mov     [rdi+38h], rbx
0x140009a52  lea     rdx, [rbp+LockHandle]; LockHandle
0x140009a56  lea     rbx, [r15+90h]
0x140009a5d  mov     r12d, 0C0000185h
0x140009a63  mov     rcx, rbx; SpinLock
0x140009a66  mov     [rdi+30h], r12d
0x140009a6a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009a71  nop     dword ptr [rax+rax+00h]
0x140009a76  or      dword ptr [r15+80h], 4
0x140009a7e  lea     rcx, [rbp+LockHandle]; LockHandle
0x140009a82  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009a89  nop     dword ptr [rax+rax+00h]
0x140009a8e  mov     r8, r14
0x140009a91  mov     rdx, rdi
0x140009a94  mov     rcx, rsi; Object
0x140009a97  call    USBSTOR_TranslateCDBComplete
0x140009a9c  xorps   xmm0, xmm0
0x140009a9f  lea     rdx, [rbp+var_20]; LockHandle
0x140009aa3  xor     eax, eax
0x140009aa5  mov     rcx, rbx; SpinLock
0x140009aa8  movups  xmmword ptr [rbp+var_20.LockQueue.Next], xmm0
0x140009aac  mov     qword ptr [rbp+var_20.OldIrql], rax
0x140009ab0  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009ab7  nop     dword ptr [rax+rax+00h]
0x140009abc  and     dword ptr [r15+80h], 0FFFFFFDFh
0x140009ac4  lea     rcx, [rbp+var_20]; LockHandle
0x140009ac8  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009acf  nop     dword ptr [rax+rax+00h]
0x140009ad4  mov     rcx, r13
0x140009ad7  call    UsbStorPumpNextRequest
0x140009adc  mov     rcx, rsi; DeviceObject
0x140009adf  call    UsbStorStartNextPacket
0x140009ae4  mov     eax, r12d
0x140009ae7  jmp     loc_140009C91
0x140009aec  mov     r9, r14
0x140009aef  mov     r8, rdi
0x140009af2  mov     rdx, rsi
0x140009af5  mov     ecx, 35626463h
0x140009afa  call    USBSTOR_LogEntry
0x140009aff  mov     [rdi+38h], rbx
0x140009b03  mov     r12d, 0C0000185h
0x140009b09  mov     [rdi+30h], r12d
0x140009b0d  mov     r8, r14
0x140009b10  mov     rdx, rdi
0x140009b13  mov     byte ptr [r14+3], 0Eh
0x140009b18  mov     rcx, rsi; Object
0x140009b1b  call    USBSTOR_TranslateCDBComplete
0x140009b20  mov     rdx, r13; Context
0x140009b23  mov     rcx, rsi; Object
0x140009b26  call    USBSTOR_QueueResetDevice
0x140009b2b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009b32  lea     rax, WPP_GLOBAL_Control
0x140009b39  cmp     rcx, rax
0x140009b3c  jz      short loc_140009AE4
0x140009b3e  mov     eax, [rcx+2Ch]
0x140009b41  test    al, 1
0x140009b43  jz      short loc_140009AE4
0x140009b45  cmp     byte ptr [rcx+29h], 2
0x140009b49  jb      short loc_140009AE4
0x140009b4b  mov     rcx, [rcx+18h]
0x140009b4f  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009b56  mov     edx, 63h ; 'c'
0x140009b5b  call    WPP_SF_
0x140009b60  jmp     short loc_140009AE4
0x140009b62  mov     r9, r14
0x140009b65  mov     r8, rdi
0x140009b68  mov     rdx, rsi
0x140009b6b  cmp     [rdi+8], rbx
0x140009b6f  jz      short loc_140009BBA
0x140009b71  mov     ecx, 36626463h
0x140009b76  call    USBSTOR_LogEntry
0x140009b7b  mov     rdx, rdi; Irp
0x140009b7e  mov     rcx, rsi; Object
0x140009b81  call    USBSTOR_IssueClientBulkRequest
0x140009b86  mov     r12d, eax
0x140009b89  test    eax, eax
0x140009b8b  jns     short loc_140009BD9
0x140009b8d  mov     [rdi+30h], eax
0x140009b90  mov     r8, r14
0x140009b93  mov     [rdi+38h], rbx
0x140009b97  mov     rdx, rdi
0x140009b9a  mov     rcx, rsi; Object
0x140009b9d  mov     byte ptr [r14+3], 4
0x140009ba2  call    USBSTOR_TranslateCDBComplete
0x140009ba7  mov     rdx, r13; Context
0x140009baa  mov     rcx, rsi; Object
0x140009bad  call    USBSTOR_QueueResetDevice
0x140009bb2  mov     ebx, r12d
0x140009bb5  jmp     loc_140009C56
0x140009bba  cmp     [r15+70h], rbx
0x140009bbe  jz      short loc_140009BE3
0x140009bc0  mov     ecx, 37626463h
0x140009bc5  call    USBSTOR_LogEntry
0x140009bca  mov     rdx, rdi; Irp
0x140009bcd  mov     [r14+3], r12b
0x140009bd1  mov     rcx, rsi; Object
0x140009bd4  call    USBSTOR_IssueInterruptRequest
0x140009bd9  mov     ebx, 0C0000016h
0x140009bde  mov     r12d, ebx
0x140009be1  jmp     short loc_140009C56
0x140009be3  mov     ecx, 38626463h
0x140009be8  call    USBSTOR_LogEntry
0x140009bed  mov     [rdi+30h], ebx
0x140009bf0  mov     r8, r14
0x140009bf3  mov     [rdi+38h], rbx
0x140009bf7  mov     rdx, rdi
0x140009bfa  mov     rcx, rsi; Object
0x140009bfd  mov     byte ptr [r14+3], 1
0x140009c02  mov     r12d, ebx
0x140009c05  call    USBSTOR_TranslateCDBComplete
0x140009c0a  xorps   xmm0, xmm0
0x140009c0d  lea     rcx, [r15+90h]; SpinLock
0x140009c14  xor     eax, eax
0x140009c16  lea     rdx, [rbp+var_20]; LockHandle
0x140009c1a  movups  xmmword ptr [rbp+var_20.LockQueue.Next], xmm0
0x140009c1e  mov     qword ptr [rbp+var_20.OldIrql], rax
0x140009c22  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009c29  nop     dword ptr [rax+rax+00h]
0x140009c2e  and     dword ptr [r15+80h], 0FFFFFFDFh
0x140009c36  lea     rcx, [rbp+var_20]; LockHandle
0x140009c3a  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009c41  nop     dword ptr [rax+rax+00h]
0x140009c46  mov     rcx, r13
0x140009c49  call    UsbStorPumpNextRequest
0x140009c4e  mov     rcx, rsi; DeviceObject
0x140009c51  call    UsbStorStartNextPacket
0x140009c56  mov     rcx, cs:WPP_GLOBAL_Control
0x140009c5d  lea     rax, WPP_GLOBAL_Control
0x140009c64  cmp     rcx, rax
0x140009c67  jz      short loc_140009C8F
0x140009c69  mov     edx, [rcx+2Ch]
0x140009c6c  test    dl, 1
0x140009c6f  jz      short loc_140009C8F
0x140009c71  cmp     byte ptr [rcx+29h], 5
0x140009c75  jb      short loc_140009C8F
0x140009c77  mov     rcx, [rcx+18h]
0x140009c7b  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009c82  mov     edx, 64h ; 'd'
0x140009c87  mov     r9d, r12d
0x140009c8a  call    WPP_SF_d
0x140009c8f  mov     eax, ebx
0x140009c91  add     rsp, 68h
0x140009c95  pop     r15
0x140009c97  pop     r14
0x140009c99  pop     r13
0x140009c9b  pop     r12
0x140009c9d  pop     rdi
0x140009c9e  pop     rsi
0x140009c9f  pop     rbx
0x140009ca0  pop     rbp
0x140009ca1  retn
```
