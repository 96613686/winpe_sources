# USBSTOR_ClientBulkCompletionRoutine

- ea: `0x14000f640`
- end: `0x14000f9e9`
- name: `USBSTOR_ClientBulkCompletionRoutine`
- size: `937`
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
- `0x140009f90`
- `0x14000a3f4`
- `0x14000bdc0`
- `0x14000f640`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140012448`

## import_xrefs

- `ntoskrnl!IoFreeMdl` at `0x14000f6f3`
- `ntoskrnl!IoFreeMdl` at `0x14000f6f3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f84e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000f84e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f866`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000f866`

## pseudocode

```c
__int64 __fastcall USBSTOR_ClientBulkCompletionRoutine(struct _DEVICE_OBJECT *a1, IRP *a2)
{
  _DWORD *DeviceExtension; // rsi
  void *v5; // r15
  struct _MDL *v6; // rcx
  __int64 SecurityContext; // rbx
  unsigned int v9; // r14d
  __int64 v10; // r9
  unsigned int v11; // ebx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-58h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 103, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1129005635, a1, a2, a2->IoStatus.Status);
  DeviceExtension = a1->DeviceExtension;
  if ( *DeviceExtension == 558842960 )
  {
    a1 = (struct _DEVICE_OBJECT *)*((_QWORD *)DeviceExtension + 2);
    v5 = DeviceExtension;
    DeviceExtension = a1->DeviceExtension;
  }
  else
  {
    v5 = 0;
    if ( *DeviceExtension != 558842950 )
    {
      DeviceExtension = 0;
      a1 = 0;
    }
  }
  v6 = (struct _MDL *)*((_QWORD *)DeviceExtension + 55);
  SecurityContext = (__int64)a2->Tail.Overlay.CurrentStackLocation->Parameters.Create.SecurityContext;
  if ( v6 != a2->MdlAddress )
    IoFreeMdl(v6);
  if ( (unsigned __int8)USBSTOR_CheckRequestTimeOut(a1) )
  {
    USBSTOR_LogEntry(829121123, a1, a2, SecurityContext);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 104, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 0;
  }
  else if ( a2->IoStatus.Status >= 0 )
  {
    *(_BYTE *)(SecurityContext + 3) = DeviceExtension[107] < *(_DWORD *)(SecurityContext + 16) ? 18 : 1;
    *(_DWORD *)(SecurityContext + 16) = DeviceExtension[107];
    v10 = (unsigned int)DeviceExtension[107];
    if ( *((_QWORD *)DeviceExtension + 14) )
    {
      USBSTOR_LogEntry(913007203, a1, a2, v10);
      USBSTOR_IssueInterruptRequest(a1, a2);
      v11 = -1073741802;
    }
    else
    {
      USBSTOR_LogEntry(929784419, a1, a2, v10);
      a2->IoStatus.Status = 0;
      USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
      a2->IoStatus.Information = *(unsigned int *)(SecurityContext + 16);
      USBSTOR_SetSrbPending(DeviceExtension, 0);
      UsbStorPumpNextRequest(v5);
      UsbStorStartNextPacket(a1);
      v11 = 0;
    }
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 107, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return v11;
  }
  else
  {
    USBSTOR_LogEntry(845898339, a2->IoStatus.Status, (int)DeviceExtension[99], 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        105,
        WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
        (unsigned int)a2->IoStatus.Status,
        DeviceExtension[99]);
    }
    if ( (DeviceExtension[99] & 0xFFFFFFF) == 4 )
    {
      *(_WORD *)(SecurityContext + 3) = 516;
      *(_DWORD *)(SecurityContext + 16) = DeviceExtension[107];
      if ( (*(_DWORD *)(SecurityContext + 12) & 0x20) == 0
        && *(_BYTE *)(SecurityContext + 11)
        && *(_QWORD *)(SecurityContext + 32) )
      {
        USBSTOR_LogEntry(862675555, a1, a2, SecurityContext);
        v9 = -1073741802;
      }
      else
      {
        USBSTOR_LogEntry(879452771, a1, a2, SecurityContext);
        v9 = -1073741435;
        a2->IoStatus.Information = 0;
        a2->IoStatus.Status = -1073741435;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
        DeviceExtension[32] |= 4u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
      }
      USBSTOR_QueueResetPipe(a1, v5);
    }
    else
    {
      USBSTOR_LogEntry(896229987, a1, a2, SecurityContext);
      a2->IoStatus.Information = 0;
      v9 = -1073741435;
      a2->IoStatus.Status = -1073741435;
      *(_BYTE *)(SecurityContext + 3) = 14;
      USBSTOR_TranslateCDBComplete(a1, (__int64)a2, SecurityContext);
      USBSTOR_QueueResetDevice(a1, v5);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 106, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
      }
    }
    return v9;
  }
}

```

## disassembly

```asm
0x14000f640  mov     r11, rsp
0x14000f643  push    rbx
0x14000f644  push    rbp
0x14000f645  push    rsi
0x14000f646  push    rdi
0x14000f647  push    r14
0x14000f649  push    r15
0x14000f64b  sub     rsp, 58h
0x14000f64f  xor     eax, eax
0x14000f651  xorps   xmm0, xmm0
0x14000f654  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000f659  mov     [r11-48h], rax
0x14000f65d  mov     rdi, rdx
0x14000f660  mov     rbp, rcx
0x14000f663  mov     [r11+8], eax
0x14000f667  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f66e  lea     rax, WPP_GLOBAL_Control
0x14000f675  lea     r14, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000f67c  cmp     rcx, rax
0x14000f67f  jz      short loc_14000F69F
0x14000f681  mov     eax, [rcx+2Ch]
0x14000f684  test    al, 1
0x14000f686  jz      short loc_14000F69F
0x14000f688  cmp     byte ptr [rcx+29h], 5
0x14000f68c  jb      short loc_14000F69F
0x14000f68e  mov     rcx, [rcx+18h]
0x14000f692  mov     edx, 67h ; 'g'
0x14000f697  mov     r8, r14
0x14000f69a  call    WPP_SF_
0x14000f69f  movsxd  r9, dword ptr [rdi+30h]
0x14000f6a3  mov     r8, rdi
0x14000f6a6  mov     rdx, rbp
0x14000f6a9  mov     ecx, 434B4243h
0x14000f6ae  call    USBSTOR_LogEntry
0x14000f6b3  mov     rsi, [rbp+40h]
0x14000f6b7  mov     eax, [rsi]
0x14000f6b9  cmp     eax, 214F4450h
0x14000f6be  jnz     short loc_14000F6CD
0x14000f6c0  mov     rbp, [rsi+10h]
0x14000f6c4  mov     r15, rsi
0x14000f6c7  mov     rsi, [rbp+40h]
0x14000f6cb  jmp     short loc_14000F6DB
0x14000f6cd  xor     r15d, r15d
0x14000f6d0  cmp     eax, 214F4446h
0x14000f6d5  jz      short loc_14000F6DB
0x14000f6d7  xor     esi, esi
0x14000f6d9  xor     ebp, ebp
0x14000f6db  mov     rax, [rdi+0B8h]
0x14000f6e2  mov     rcx, [rsi+1B8h]; Mdl
0x14000f6e9  mov     rbx, [rax+8]
0x14000f6ed  cmp     rcx, [rdi+8]
0x14000f6f1  jz      short loc_14000F6FF
0x14000f6f3  call    cs:__imp_IoFreeMdl
0x14000f6fa  nop     dword ptr [rax+rax+00h]
0x14000f6ff  lea     r9, [rsp+88h+arg_0]
0x14000f707  mov     r8, rbx
0x14000f70a  mov     rdx, rdi
0x14000f70d  mov     rcx, rbp; Object
0x14000f710  call    USBSTOR_CheckRequestTimeOut
0x14000f715  test    al, al
0x14000f717  jz      short loc_14000F769
0x14000f719  mov     r9, rbx
0x14000f71c  mov     r8, rdi
0x14000f71f  mov     rdx, rbp
0x14000f722  mov     ecx, 316B6263h
0x14000f727  call    USBSTOR_LogEntry
0x14000f72c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f733  lea     rax, WPP_GLOBAL_Control
0x14000f73a  cmp     rcx, rax
0x14000f73d  jz      short loc_14000F75D
0x14000f73f  mov     eax, [rcx+2Ch]
0x14000f742  test    al, 1
0x14000f744  jz      short loc_14000F75D
0x14000f746  cmp     byte ptr [rcx+29h], 2
0x14000f74a  jb      short loc_14000F75D
0x14000f74c  mov     rcx, [rcx+18h]
0x14000f750  mov     edx, 68h ; 'h'
0x14000f755  mov     r8, r14
0x14000f758  call    WPP_SF_
0x14000f75d  mov     eax, [rsp+88h+arg_0]
0x14000f764  jmp     loc_14000F9DB
0x14000f769  movsxd  rax, dword ptr [rdi+30h]
0x14000f76d  test    eax, eax
0x14000f76f  jns     loc_14000F90F
0x14000f775  movsxd  r8, dword ptr [rsi+18Ch]
0x14000f77c  mov     rdx, rax
0x14000f77f  xor     r9d, r9d
0x14000f782  mov     ecx, 326B6263h
0x14000f787  call    USBSTOR_LogEntry
0x14000f78c  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f793  lea     rax, WPP_GLOBAL_Control
0x14000f79a  cmp     rcx, rax
0x14000f79d  jz      short loc_14000F7CB
0x14000f79f  mov     eax, [rcx+2Ch]
0x14000f7a2  test    al, 1
0x14000f7a4  jz      short loc_14000F7CB
0x14000f7a6  cmp     byte ptr [rcx+29h], 2
0x14000f7aa  jb      short loc_14000F7CB
0x14000f7ac  mov     eax, [rsi+18Ch]
0x14000f7b2  mov     edx, 69h ; 'i'
0x14000f7b7  mov     r9d, [rdi+30h]
0x14000f7bb  mov     r8, r14
0x14000f7be  mov     rcx, [rcx+18h]
0x14000f7c2  mov     [rsp+88h+var_68], eax
0x14000f7c6  call    WPP_SF_DD
0x14000f7cb  mov     eax, [rsi+18Ch]
0x14000f7d1  and     eax, 0FFFFFFFh
0x14000f7d6  cmp     eax, 4
0x14000f7d9  jnz     loc_14000F893
0x14000f7df  mov     word ptr [rbx+3], 204h
0x14000f7e5  mov     eax, [rsi+1ACh]
0x14000f7eb  mov     [rbx+10h], eax
0x14000f7ee  mov     eax, [rbx+0Ch]
0x14000f7f1  test    al, 20h
0x14000f7f3  jnz     short loc_14000F81D
0x14000f7f5  cmp     byte ptr [rbx+0Bh], 0
0x14000f7f9  jz      short loc_14000F81D
0x14000f7fb  cmp     qword ptr [rbx+20h], 0
0x14000f800  jz      short loc_14000F81D
0x14000f802  mov     r9, rbx
0x14000f805  mov     r8, rdi
0x14000f808  mov     rdx, rbp
0x14000f80b  mov     ecx, 336B6263h
0x14000f810  call    USBSTOR_LogEntry
0x14000f815  mov     r14d, 0C0000016h
0x14000f81b  jmp     short loc_14000F880
0x14000f81d  mov     r9, rbx
0x14000f820  mov     r8, rdi
0x14000f823  mov     rdx, rbp
0x14000f826  mov     ecx, 346B6263h
0x14000f82b  call    USBSTOR_LogEntry
0x14000f830  mov     r14d, 0C0000185h
0x14000f836  mov     qword ptr [rdi+38h], 0
0x14000f83e  lea     rcx, [rsi+90h]; SpinLock
0x14000f845  mov     [rdi+30h], r14d
0x14000f849  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000f84e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000f855  nop     dword ptr [rax+rax+00h]
0x14000f85a  or      dword ptr [rsi+80h], 4
0x14000f861  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000f866  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000f86d  nop     dword ptr [rax+rax+00h]
0x14000f872  mov     r8, rbx
0x14000f875  mov     rdx, rdi
0x14000f878  mov     rcx, rbp; Object
0x14000f87b  call    USBSTOR_TranslateCDBComplete
0x14000f880  mov     rdx, r15; Context
0x14000f883  mov     rcx, rbp; Object
0x14000f886  call    USBSTOR_QueueResetPipe
0x14000f88b  mov     eax, r14d
0x14000f88e  jmp     loc_14000F9DB
0x14000f893  mov     r9, rbx
0x14000f896  mov     r8, rdi
0x14000f899  mov     rdx, rbp
0x14000f89c  mov     ecx, 356B6263h
0x14000f8a1  call    USBSTOR_LogEntry
0x14000f8a6  mov     qword ptr [rdi+38h], 0
0x14000f8ae  mov     r14d, 0C0000185h
0x14000f8b4  mov     [rdi+30h], r14d
0x14000f8b8  mov     r8, rbx
0x14000f8bb  mov     rdx, rdi
0x14000f8be  mov     byte ptr [rbx+3], 0Eh
0x14000f8c2  mov     rcx, rbp; Object
0x14000f8c5  call    USBSTOR_TranslateCDBComplete
0x14000f8ca  mov     rdx, r15; Context
0x14000f8cd  mov     rcx, rbp; Object
0x14000f8d0  call    USBSTOR_QueueResetDevice
0x14000f8d5  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f8dc  lea     rax, WPP_GLOBAL_Control
0x14000f8e3  cmp     rcx, rax
0x14000f8e6  jz      short loc_14000F88B
0x14000f8e8  mov     eax, [rcx+2Ch]
0x14000f8eb  test    al, 1
0x14000f8ed  jz      short loc_14000F88B
0x14000f8ef  cmp     byte ptr [rcx+29h], 2
0x14000f8f3  jb      short loc_14000F88B
0x14000f8f5  mov     rcx, [rcx+18h]
0x14000f8f9  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000f900  mov     edx, 6Ah ; 'j'
0x14000f905  call    WPP_SF_
0x14000f90a  jmp     loc_14000F88B
0x14000f90f  mov     eax, [rbx+10h]
0x14000f912  mov     r8, rdi
0x14000f915  cmp     [rsi+1ACh], eax
0x14000f91b  mov     rdx, rbp
0x14000f91e  sbb     al, al
0x14000f920  and     al, 11h
0x14000f922  inc     al
0x14000f924  mov     [rbx+3], al
0x14000f927  mov     eax, [rsi+1ACh]
0x14000f92d  mov     [rbx+10h], eax
0x14000f930  cmp     qword ptr [rsi+70h], 0
0x14000f935  mov     r9d, [rsi+1ACh]
0x14000f93c  jz      short loc_14000F95E
0x14000f93e  mov     ecx, 366B6263h
0x14000f943  call    USBSTOR_LogEntry
0x14000f948  mov     rdx, rdi; Irp
0x14000f94b  mov     rcx, rbp; Object
0x14000f94e  call    USBSTOR_IssueInterruptRequest
0x14000f953  mov     r14d, 0C0000016h
0x14000f959  mov     ebx, r14d
0x14000f95c  jmp     short loc_14000F9A0
0x14000f95e  mov     ecx, 376B6263h
0x14000f963  call    USBSTOR_LogEntry
0x14000f968  xor     r14d, r14d
0x14000f96b  mov     r8, rbx
0x14000f96e  mov     rdx, rdi
0x14000f971  mov     [rdi+30h], r14d
0x14000f975  mov     rcx, rbp; Object
0x14000f978  call    USBSTOR_TranslateCDBComplete
0x14000f97d  mov     eax, [rbx+10h]
0x14000f980  xor     edx, edx
0x14000f982  mov     rcx, rsi
0x14000f985  mov     [rdi+38h], rax
0x14000f989  call    USBSTOR_SetSrbPending
0x14000f98e  mov     rcx, r15
0x14000f991  call    UsbStorPumpNextRequest
0x14000f996  mov     rcx, rbp; DeviceObject
0x14000f999  call    UsbStorStartNextPacket
0x14000f99e  xor     ebx, ebx
0x14000f9a0  mov     rcx, cs:WPP_GLOBAL_Control
0x14000f9a7  lea     rax, WPP_GLOBAL_Control
0x14000f9ae  cmp     rcx, rax
0x14000f9b1  jz      short loc_14000F9D9
0x14000f9b3  mov     edx, [rcx+2Ch]
0x14000f9b6  test    dl, 1
0x14000f9b9  jz      short loc_14000F9D9
0x14000f9bb  cmp     byte ptr [rcx+29h], 5
0x14000f9bf  jb      short loc_14000F9D9
0x14000f9c1  mov     rcx, [rcx+18h]
0x14000f9c5  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000f9cc  mov     edx, 6Bh ; 'k'
0x14000f9d1  mov     r9d, r14d
0x14000f9d4  call    WPP_SF_d
0x14000f9d9  mov     eax, ebx
0x14000f9db  add     rsp, 58h
0x14000f9df  pop     r15
0x14000f9e1  pop     r14
0x14000f9e3  pop     rdi
0x14000f9e4  pop     rsi
0x14000f9e5  pop     rbp
0x14000f9e6  pop     rbx
0x14000f9e7  retn
```
