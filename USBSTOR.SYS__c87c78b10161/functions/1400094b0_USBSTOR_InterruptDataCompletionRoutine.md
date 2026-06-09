# USBSTOR_InterruptDataCompletionRoutine

- ea: `0x1400094b0`
- end: `0x140009858`
- name: `USBSTOR_InterruptDataCompletionRoutine`
- size: `936`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x140001008`
- `0x140003630`
- `0x140003b90`
- `0x140004910`
- `0x140007ff0`
- `0x1400094b0`
- `0x140009f90`
- `0x1400105e8`
- `0x140010664`
- `0x140010c60`
- `0x140012448`

## import_xrefs

- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000971a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009771`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400097d8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000971a`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140009771`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400097d8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009731`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009788`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400097ef`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009731`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140009788`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400097ef`

## pseudocode

```c
__int64 __fastcall USBSTOR_InterruptDataCompletionRoutine(struct _DEVICE_OBJECT *a1, __int64 a2)
{
  _DWORD *DeviceExtension; // rdi
  void *v5; // r12
  __int64 v6; // rbx
  unsigned int v8; // r15d
  char v9; // al
  int v10; // eax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE v12; // [rsp+48h] [rbp-20h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 110, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1380140105, a1, a2, *(int *)(a2 + 48));
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
  v6 = *(_QWORD *)(*(_QWORD *)(a2 + 184) + 8LL);
  if ( (unsigned __int8)USBSTOR_CheckRequestTimeOut(a1) )
  {
    USBSTOR_LogEntry(828597353, a1, a2, v6);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 111, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return 0;
  }
  if ( *(int *)(a2 + 48) < 0 )
  {
    USBSTOR_LogEntry(845374569, *(int *)(a2 + 48), (int)DeviceExtension[99], 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DD(
        WPP_GLOBAL_Control->AttachedDevice,
        112,
        WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
        *(unsigned int *)(a2 + 48),
        DeviceExtension[99]);
    }
    *(_QWORD *)(a2 + 56) = 0;
    v8 = -1073741435;
    *(_DWORD *)(a2 + 48) = -1073741435;
    *(_BYTE *)(v6 + 3) = 14;
    USBSTOR_TranslateCDBComplete(a1, a2, v6);
    USBSTOR_QueueResetDevice(a1, v5);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 113, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
    }
    return v8;
  }
  if ( *((_WORD *)DeviceExtension + 596) )
  {
    v9 = *(_BYTE *)(v6 + 72);
    if ( v9 != 18 && v9 != 3 )
    {
      v10 = *(_DWORD *)(v6 + 12);
      *(_WORD *)(v6 + 3) = 516;
      *(_DWORD *)(v6 + 16) = 0;
      if ( (v10 & 0x20) == 0 && *(_BYTE *)(v6 + 11) && *(_QWORD *)(v6 + 32) )
      {
        USBSTOR_LogEntry(862151785, a1, a2, v6);
        v8 = -1073741802;
      }
      else
      {
        USBSTOR_LogEntry(878929001, a1, a2, v6);
        v8 = -1073741435;
        *(_QWORD *)(a2 + 56) = 0;
        *(_DWORD *)(a2 + 48) = -1073741435;
        KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
        DeviceExtension[32] |= 4u;
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        USBSTOR_TranslateCDBComplete(a1, a2, v6);
      }
      USBSTOR_QueueResetPipe(a1, v5);
      return v8;
    }
  }
  if ( (DeviceExtension[33] & 1) != 0 )
  {
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &LockHandle);
    DeviceExtension[32] |= 4u;
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  *(_DWORD *)(a2 + 48) = 0;
  USBSTOR_TranslateCDBComplete(a1, a2, v6);
  *(_QWORD *)(a2 + 56) = *(unsigned int *)(v6 + 16);
  USBSTOR_LogEntry(895706217, a1, a2, v6);
  memset(&v12, 0, sizeof(v12));
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)DeviceExtension + 18, &v12);
  DeviceExtension[32] &= ~0x20u;
  KeReleaseInStackQueuedSpinLock(&v12);
  UsbStorPumpNextRequest(v5);
  UsbStorStartNextPacket(a1);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 114, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  return 0;
}

```

## disassembly

```asm
0x1400094b0  push    rbp
0x1400094b2  push    rbx
0x1400094b3  push    rsi
0x1400094b4  push    rdi
0x1400094b5  push    r12
0x1400094b7  push    r13
0x1400094b9  push    r14
0x1400094bb  push    r15
0x1400094bd  mov     rbp, rsp
0x1400094c0  sub     rsp, 68h
0x1400094c4  xor     eax, eax
0x1400094c6  xorps   xmm0, xmm0
0x1400094c9  xor     r13d, r13d
0x1400094cc  mov     qword ptr [rbp+LockHandle.OldIrql], rax
0x1400094d0  mov     [rbp+arg_0], r13d
0x1400094d4  mov     rsi, rdx
0x1400094d7  mov     r14, rcx
0x1400094da  movups  xmmword ptr [rbp+LockHandle.LockQueue.Next], xmm0
0x1400094de  mov     rcx, cs:WPP_GLOBAL_Control
0x1400094e5  lea     rax, WPP_GLOBAL_Control
0x1400094ec  mov     r15b, 1
0x1400094ef  cmp     rcx, rax
0x1400094f2  jz      short loc_140009516
0x1400094f4  mov     eax, [rcx+2Ch]
0x1400094f7  test    r15b, al
0x1400094fa  jz      short loc_140009516
0x1400094fc  cmp     byte ptr [rcx+29h], 5
0x140009500  jb      short loc_140009516
0x140009502  mov     rcx, [rcx+18h]
0x140009506  lea     edx, [r13+6Eh]
0x14000950a  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009511  call    WPP_SF_
0x140009516  movsxd  r9, dword ptr [rsi+30h]
0x14000951a  mov     r8, rsi
0x14000951d  mov     rdx, r14
0x140009520  mov     ecx, 52434449h
0x140009525  call    USBSTOR_LogEntry
0x14000952a  mov     rdi, [r14+40h]
0x14000952e  mov     eax, [rdi]
0x140009530  cmp     eax, 214F4450h
0x140009535  jnz     short loc_140009544
0x140009537  mov     r14, [rdi+10h]
0x14000953b  mov     r12, rdi
0x14000953e  mov     rdi, [r14+40h]
0x140009542  jmp     short loc_140009554
0x140009544  mov     r12, r13
0x140009547  cmp     eax, 214F4446h
0x14000954c  jz      short loc_140009554
0x14000954e  mov     rdi, r13
0x140009551  mov     r14, r13
0x140009554  mov     rax, [rsi+0B8h]
0x14000955b  lea     r9, [rbp+arg_0]
0x14000955f  mov     rdx, rsi
0x140009562  mov     rcx, r14; Object
0x140009565  mov     rbx, [rax+8]
0x140009569  mov     r8, rbx
0x14000956c  call    USBSTOR_CheckRequestTimeOut
0x140009571  test    al, al
0x140009573  jz      short loc_1400095C6
0x140009575  mov     r9, rbx
0x140009578  mov     r8, rsi
0x14000957b  mov     rdx, r14
0x14000957e  mov     ecx, 31636469h
0x140009583  call    USBSTOR_LogEntry
0x140009588  mov     rcx, cs:WPP_GLOBAL_Control
0x14000958f  lea     rax, WPP_GLOBAL_Control
0x140009596  cmp     rcx, rax
0x140009599  jz      short loc_1400095BE
0x14000959b  mov     eax, [rcx+2Ch]
0x14000959e  test    r15b, al
0x1400095a1  jz      short loc_1400095BE
0x1400095a3  cmp     byte ptr [rcx+29h], 2
0x1400095a7  jb      short loc_1400095BE
0x1400095a9  mov     rcx, [rcx+18h]
0x1400095ad  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400095b4  mov     edx, 6Fh ; 'o'
0x1400095b9  call    WPP_SF_
0x1400095be  mov     eax, [rbp+arg_0]
0x1400095c1  jmp     loc_140009846
0x1400095c6  movsxd  rax, dword ptr [rsi+30h]
0x1400095ca  test    eax, eax
0x1400095cc  jns     loc_140009695
0x1400095d2  movsxd  r8, dword ptr [rdi+18Ch]
0x1400095d9  mov     rdx, rax
0x1400095dc  xor     r9d, r9d
0x1400095df  mov     ecx, 32636469h
0x1400095e4  call    USBSTOR_LogEntry
0x1400095e9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400095f0  lea     rax, WPP_GLOBAL_Control
0x1400095f7  cmp     rcx, rax
0x1400095fa  jz      short loc_14000962D
0x1400095fc  mov     eax, [rcx+2Ch]
0x1400095ff  test    r15b, al
0x140009602  jz      short loc_14000962D
0x140009604  cmp     byte ptr [rcx+29h], 2
0x140009608  jb      short loc_14000962D
0x14000960a  mov     eax, [rdi+18Ch]
0x140009610  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009617  mov     r9d, [rsi+30h]
0x14000961b  mov     edx, 70h ; 'p'
0x140009620  mov     rcx, [rcx+18h]
0x140009624  mov     [rsp+68h+var_48], eax
0x140009628  call    WPP_SF_DD
0x14000962d  mov     [rsi+38h], r13
0x140009631  mov     r15d, 0C0000185h
0x140009637  mov     [rsi+30h], r15d
0x14000963b  mov     r8, rbx
0x14000963e  mov     rdx, rsi
0x140009641  mov     byte ptr [rbx+3], 0Eh
0x140009645  mov     rcx, r14; Object
0x140009648  call    USBSTOR_TranslateCDBComplete
0x14000964d  mov     rdx, r12; Context
0x140009650  mov     rcx, r14; Object
0x140009653  call    USBSTOR_QueueResetDevice
0x140009658  mov     rcx, cs:WPP_GLOBAL_Control
0x14000965f  lea     rax, WPP_GLOBAL_Control
0x140009666  cmp     rcx, rax
0x140009669  jz      short loc_14000968D
0x14000966b  mov     eax, [rcx+2Ch]
0x14000966e  test    al, 1
0x140009670  jz      short loc_14000968D
0x140009672  cmp     byte ptr [rcx+29h], 2
0x140009676  jb      short loc_14000968D
0x140009678  mov     rcx, [rcx+18h]
0x14000967c  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009683  mov     edx, 71h ; 'q'
0x140009688  call    WPP_SF_
0x14000968d  mov     eax, r15d
0x140009690  jmp     loc_140009846
0x140009695  cmp     [rdi+4A8h], r13w
0x14000969d  jz      loc_14000975B
0x1400096a3  mov     al, [rbx+48h]
0x1400096a6  cmp     al, 12h
0x1400096a8  jz      loc_14000975B
0x1400096ae  cmp     al, 3
0x1400096b0  jz      loc_14000975B
0x1400096b6  mov     eax, [rbx+0Ch]
0x1400096b9  mov     word ptr [rbx+3], 204h
0x1400096bf  mov     [rbx+10h], r13d
0x1400096c3  test    al, 20h
0x1400096c5  jnz     short loc_1400096EE
0x1400096c7  cmp     [rbx+0Bh], r13b
0x1400096cb  jz      short loc_1400096EE
0x1400096cd  cmp     [rbx+20h], r13
0x1400096d1  jz      short loc_1400096EE
0x1400096d3  mov     r9, rbx
0x1400096d6  mov     r8, rsi
0x1400096d9  mov     rdx, r14
0x1400096dc  mov     ecx, 33636469h
0x1400096e1  call    USBSTOR_LogEntry
0x1400096e6  mov     r15d, 0C0000016h
0x1400096ec  jmp     short loc_14000974B
0x1400096ee  mov     r9, rbx
0x1400096f1  mov     r8, rsi
0x1400096f4  mov     rdx, r14
0x1400096f7  mov     ecx, 34636469h
0x1400096fc  call    USBSTOR_LogEntry
0x140009701  mov     r15d, 0C0000185h
0x140009707  mov     [rsi+38h], r13
0x14000970b  lea     rcx, [rdi+90h]; SpinLock
0x140009712  mov     [rsi+30h], r15d
0x140009716  lea     rdx, [rbp+LockHandle]; LockHandle
0x14000971a  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009721  nop     dword ptr [rax+rax+00h]
0x140009726  or      dword ptr [rdi+80h], 4
0x14000972d  lea     rcx, [rbp+LockHandle]; LockHandle
0x140009731  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140009738  nop     dword ptr [rax+rax+00h]
0x14000973d  mov     r8, rbx
0x140009740  mov     rdx, rsi
0x140009743  mov     rcx, r14; Object
0x140009746  call    USBSTOR_TranslateCDBComplete
0x14000974b  mov     rdx, r12; Context
0x14000974e  mov     rcx, r14; Object
0x140009751  call    USBSTOR_QueueResetPipe
0x140009756  jmp     loc_14000968D
0x14000975b  mov     eax, [rdi+84h]
0x140009761  test    r15b, al
0x140009764  jz      short loc_140009794
0x140009766  lea     rcx, [rdi+90h]; SpinLock
0x14000976d  lea     rdx, [rbp+LockHandle]; LockHandle
0x140009771  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140009778  nop     dword ptr [rax+rax+00h]
0x14000977d  or      dword ptr [rdi+80h], 4
0x140009784  lea     rcx, [rbp+LockHandle]; LockHandle
0x140009788  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000978f  nop     dword ptr [rax+rax+00h]
0x140009794  mov     r8, rbx
0x140009797  mov     [rsi+30h], r13d
0x14000979b  mov     rdx, rsi
0x14000979e  mov     rcx, r14; Object
0x1400097a1  call    USBSTOR_TranslateCDBComplete
0x1400097a6  mov     eax, [rbx+10h]
0x1400097a9  mov     r9, rbx
0x1400097ac  mov     r8, rsi
0x1400097af  mov     [rsi+38h], rax
0x1400097b3  mov     rdx, r14
0x1400097b6  mov     ecx, 35636469h
0x1400097bb  call    USBSTOR_LogEntry
0x1400097c0  xorps   xmm0, xmm0
0x1400097c3  lea     rcx, [rdi+90h]; SpinLock
0x1400097ca  xor     eax, eax
0x1400097cc  lea     rdx, [rbp+var_20]; LockHandle
0x1400097d0  movups  xmmword ptr [rbp+var_20.LockQueue.Next], xmm0
0x1400097d4  mov     qword ptr [rbp+var_20.OldIrql], rax
0x1400097d8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400097df  nop     dword ptr [rax+rax+00h]
0x1400097e4  and     dword ptr [rdi+80h], 0FFFFFFDFh
0x1400097eb  lea     rcx, [rbp+var_20]; LockHandle
0x1400097ef  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400097f6  nop     dword ptr [rax+rax+00h]
0x1400097fb  mov     rcx, r12
0x1400097fe  call    UsbStorPumpNextRequest
0x140009803  mov     rcx, r14; DeviceObject
0x140009806  call    UsbStorStartNextPacket
0x14000980b  mov     rcx, cs:WPP_GLOBAL_Control
0x140009812  lea     rax, WPP_GLOBAL_Control
0x140009819  cmp     rcx, rax
0x14000981c  jz      short loc_140009844
0x14000981e  mov     eax, [rcx+2Ch]
0x140009821  test    r15b, al
0x140009824  jz      short loc_140009844
0x140009826  cmp     byte ptr [rcx+29h], 5
0x14000982a  jb      short loc_140009844
0x14000982c  mov     rcx, [rcx+18h]
0x140009830  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140009837  mov     edx, 72h ; 'r'
0x14000983c  xor     r9d, r9d
0x14000983f  call    WPP_SF_d
0x140009844  xor     eax, eax
0x140009846  add     rsp, 68h
0x14000984a  pop     r15
0x14000984c  pop     r14
0x14000984e  pop     r13
0x140009850  pop     r12
0x140009852  pop     rdi
0x140009853  pop     rsi
0x140009854  pop     rbx
0x140009855  pop     rbp
0x140009856  retn
```
