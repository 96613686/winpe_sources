# USBSTOR_IssueInternalCdbToLun

- ea: `0x1400266ac`
- end: `0x1400269e6`
- name: `USBSTOR_IssueInternalCdbToLun`
- size: `826`
- prototype: `__int64 __usercall@<rax>(PDEVICE_OBJECT DeviceObject@<rcx>, __int64, void *Src, char, int)`
- caller_count: `9`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400217c8`
- `0x140021e34`
- `0x140021ff4`
- `0x1400259cc`
- `0x140025d60`
- `0x14002605c`
- `0x1400263a4`
- `0x1400264d0`
- `0x140026678`

## callees

- `0x1400105e8`
- `0x140010664`
- `0x140012994`
- `0x140013a40`
- `0x140013d40`
- `0x1400266ac`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140026940`
- `ntoskrnl!IoFreeIrp` at `0x140026940`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026846`
- `ntoskrnl!MmBuildMdlForNonPagedPool` at `0x140026846`
- `ntoskrnl!IoAllocateMdl` at `0x14002682b`
- `ntoskrnl!IoAllocateMdl` at `0x14002682b`
- `ntoskrnl!ExAllocatePool2` at `0x140026727`
- `ntoskrnl!ExAllocatePool2` at `0x140026747`
- `ntoskrnl!ExAllocatePool2` at `0x140026727`
- `ntoskrnl!ExAllocatePool2` at `0x140026747`
- `ntoskrnl!IoFreeMdl` at `0x140026964`
- `ntoskrnl!IoFreeMdl` at `0x140026964`
- `ntoskrnl!IofCallDriver` at `0x1400268ae`
- `ntoskrnl!IofCallDriver` at `0x1400268ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002698d`
- `ntoskrnl!ExFreePoolWithTag` at `0x140026975`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002698d`
- `ntoskrnl!KeInitializeEvent` at `0x14002676c`
- `ntoskrnl!KeInitializeEvent` at `0x14002676c`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400268d9`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400268d9`
- `ntoskrnl!KeClearEvent` at `0x14002687d`
- `ntoskrnl!KeClearEvent` at `0x14002687d`
- `ntoskrnl!IoAllocateIrp` at `0x140026793`
- `ntoskrnl!IoAllocateIrp` at `0x140026793`

## pseudocode

```c
__int64 __fastcall USBSTOR_IssueInternalCdbToLun(
        PDEVICE_OBJECT DeviceObject,
        char a2,
        __int64 a3,
        void *a4,
        ULONG *a5,
        void *Src,
        unsigned __int8 a7,
        int a8)
{
  unsigned int v9; // edi
  ULONG *Pool2; // rbx
  void *v11; // r15
  struct _MDL *v12; // rsi
  unsigned int i; // r14d
  PIRP Irp; // rax
  IRP *v15; // rbp
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  ULONG v17; // edx
  struct _MDL *Mdl; // rax
  struct _IO_STACK_LOCATION *v19; // rax
  __int64 v20; // rdx
  NTSTATUS v21; // edi
  __int64 v22; // r8
  int v23; // eax
  struct _KEVENT Event; // [rsp+30h] [rbp-58h] BYREF

  memset(&Event, 0, sizeof(Event));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xB8u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  v9 = -1073741670;
  Pool2 = (ULONG *)ExAllocatePool2(64, 88, 1396788565);
  if ( Pool2 )
  {
    v11 = (void *)ExAllocatePool2(64, 18, 1396788565);
    if ( v11 )
    {
      v12 = 0;
      KeInitializeEvent(&Event, SynchronizationEvent, 0);
      for ( i = 0; i < 3; ++i )
      {
        Irp = IoAllocateIrp(DeviceObject->StackSize, 0);
        v15 = Irp;
        if ( !Irp )
          break;
        CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].MajorFunction = 15;
        CurrentStackLocation[-1].Parameters.WMI.ProviderId = (ULONG_PTR)Pool2;
        memset(Pool2, 0, 0x58u);
        v17 = *a5;
        *((_BYTE *)Pool2 + 7) = a2;
        *(_WORD *)Pool2 = 88;
        *((_QWORD *)Pool2 + 3) = a4;
        *((_BYTE *)Pool2 + 10) = a7;
        *((_BYTE *)Pool2 + 11) = 18;
        *((_QWORD *)Pool2 + 4) = v11;
        Pool2[4] = v17;
        if ( v17 )
        {
          Pool2[3] = 320;
          if ( !i )
          {
            Mdl = IoAllocateMdl(a4, v17, 0, 0, 0);
            v12 = Mdl;
            if ( !Mdl )
            {
              IoFreeIrp(v15);
              v9 = -1073741670;
              goto LABEL_28;
            }
            MmBuildMdlForNonPagedPool(Mdl);
          }
        }
        else
        {
          Pool2[3] = 288;
        }
        v15->MdlAddress = v12;
        Pool2[5] = a8;
        *((_QWORD *)Pool2 + 6) = v15;
        memmove(Pool2 + 18, Src, a7);
        KeClearEvent(&Event);
        v19 = v15->Tail.Overlay.CurrentStackLocation;
        v19[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)USBSTOR_InternalCDBCompletionRoutine;
        v19[-1].Context = &Event;
        v19[-1].Control = -32;
        v21 = IofCallDriver(DeviceObject, v15);
        if ( v21 == 259 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_dDD(
            WPP_GLOBAL_Control->AttachedDevice,
            v20,
            v22,
            i,
            v21,
            *((unsigned __int8 *)Pool2 + 3),
            *(_QWORD *)&Event.Header.Lock,
            Event.Header.WaitListHead.Flink,
            Event.Header.WaitListHead.Blink);
        }
        v23 = *((_BYTE *)Pool2 + 3) & 0x3F;
        if ( v23 == 1 || v23 == 18 )
        {
          v9 = 0;
          *a5 = Pool2[4];
          break;
        }
        v9 = -1073741823;
      }
      if ( v12 )
        IoFreeMdl(v12);
LABEL_28:
      ExFreePoolWithTag(v11, 0);
    }
    ExFreePoolWithTag(Pool2, 0);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0xBAu,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      v9);
  }
  return v9;
}

```

## disassembly

```asm
0x1400266ac  mov     [rsp+arg_0], rbx
0x1400266b1  mov     [rsp+VirtualAddress], r9
0x1400266b6  mov     [rsp+arg_8], dl
0x1400266ba  push    rbp
0x1400266bb  push    rsi
0x1400266bc  push    rdi
0x1400266bd  push    r12
0x1400266bf  push    r13
0x1400266c1  push    r14
0x1400266c3  push    r15
0x1400266c5  sub     rsp, 50h
0x1400266c9  xorps   xmm0, xmm0
0x1400266cc  xor     eax, eax
0x1400266ce  movups  xmmword ptr [rsp+88h+Event.Header], xmm0
0x1400266d3  mov     [rsp+88h+Event.Header.WaitListHead.Blink], rax
0x1400266d8  mov     r13, rcx
0x1400266db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400266e2  lea     r14, WPP_GLOBAL_Control
0x1400266e9  cmp     rcx, r14
0x1400266ec  jz      short loc_140026710
0x1400266ee  mov     eax, [rcx+2Ch]
0x1400266f1  test    al, 1
0x1400266f3  jz      short loc_140026710
0x1400266f5  cmp     byte ptr [rcx+29h], 5
0x1400266f9  jb      short loc_140026710
0x1400266fb  mov     rcx, [rcx+18h]
0x1400266ff  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x140026706  mov     edx, 0B8h
0x14002670b  call    WPP_SF_
0x140026710  mov     edx, 58h ; 'X'
0x140026715  mov     esi, 53414D55h
0x14002671a  mov     r8d, esi
0x14002671d  mov     edi, 0C000009Ah
0x140026722  lea     ebp, [rdx-18h]
0x140026725  mov     ecx, ebp
0x140026727  call    cs:__imp_ExAllocatePool2
0x14002672e  nop     dword ptr [rax+rax+00h]
0x140026733  mov     rbx, rax
0x140026736  test    rax, rax
0x140026739  jz      loc_140026999
0x14002673f  mov     r8d, esi
0x140026742  lea     edx, [rbp-2Eh]
0x140026745  mov     ecx, ebp
0x140026747  call    cs:__imp_ExAllocatePool2
0x14002674e  nop     dword ptr [rax+rax+00h]
0x140026753  mov     r15, rax
0x140026756  test    rax, rax
0x140026759  jz      loc_140026988
0x14002675f  xor     r8d, r8d; State
0x140026762  lea     edx, [rbp-3Fh]; Type
0x140026765  lea     rcx, [rsp+88h+Event]; Event
0x14002676a  xor     esi, esi
0x14002676c  call    cs:__imp_KeInitializeEvent
0x140026773  nop     dword ptr [rax+rax+00h]
0x140026778  mov     r12, [rsp+88h+arg_20]
0x140026780  xor     r14d, r14d
0x140026783  cmp     r14d, 3
0x140026787  jnb     loc_14002695C
0x14002678d  mov     cl, [r13+4Ch]; StackSize
0x140026791  xor     edx, edx; ChargeQuota
0x140026793  call    cs:__imp_IoAllocateIrp
0x14002679a  nop     dword ptr [rax+rax+00h]
0x14002679f  mov     rbp, rax
0x1400267a2  test    rax, rax
0x1400267a5  jz      loc_14002695C
0x1400267ab  mov     rax, [rax+0B8h]
0x1400267b2  mov     edi, 58h ; 'X'
0x1400267b7  mov     r8d, edi; Size
0x1400267ba  xor     edx, edx; Val
0x1400267bc  mov     rcx, rbx; void *
0x1400267bf  mov     byte ptr [rax-48h], 0Fh
0x1400267c3  mov     [rax-40h], rbx
0x1400267c7  call    memset
0x1400267cc  mov     al, [rsp+88h+arg_8]
0x1400267d3  mov     edx, [r12]; Length
0x1400267d7  mov     [rbx+7], al
0x1400267da  mov     rax, [rsp+88h+VirtualAddress]
0x1400267e2  mov     [rbx], di
0x1400267e5  movzx   edi, [rsp+88h+arg_30]
0x1400267ed  mov     [rbx+18h], rax
0x1400267f1  mov     [rbx+0Ah], dil
0x1400267f5  mov     byte ptr [rbx+0Bh], 12h
0x1400267f9  mov     [rbx+20h], r15
0x1400267fd  mov     [rbx+10h], edx
0x140026800  test    edx, edx
0x140026802  jnz     short loc_14002680D
0x140026804  mov     dword ptr [rbx+0Ch], 120h
0x14002680b  jmp     short loc_140026852
0x14002680d  mov     dword ptr [rbx+0Ch], 140h
0x140026814  test    r14d, r14d
0x140026817  jnz     short loc_140026852
0x140026819  xor     r9d, r9d; ChargeQuota
0x14002681c  mov     [rsp+88h+Irp], 0; Irp
0x140026825  xor     r8d, r8d; SecondaryBuffer
0x140026828  mov     rcx, rax; VirtualAddress
0x14002682b  call    cs:__imp_IoAllocateMdl
0x140026832  nop     dword ptr [rax+rax+00h]
0x140026837  mov     rsi, rax
0x14002683a  test    rax, rax
0x14002683d  jz      loc_14002693D
0x140026843  mov     rcx, rax; MemoryDescriptorList
0x140026846  call    cs:__imp_MmBuildMdlForNonPagedPool
0x14002684d  nop     dword ptr [rax+rax+00h]
0x140026852  mov     eax, [rsp+88h+arg_38]
0x140026859  lea     rcx, [rbx+48h]; void *
0x14002685d  mov     rdx, [rsp+88h+Src]; Src
0x140026865  mov     r8, rdi; Size
0x140026868  mov     [rbp+8], rsi
0x14002686c  mov     [rbx+14h], eax
0x14002686f  mov     [rbx+30h], rbp
0x140026873  call    memmove
0x140026878  lea     rcx, [rsp+88h+Event]; Event
0x14002687d  call    cs:__imp_KeClearEvent
0x140026884  nop     dword ptr [rax+rax+00h]
0x140026889  mov     rax, [rbp+0B8h]
0x140026890  lea     rcx, USBSTOR_InternalCDBCompletionRoutine
0x140026897  mov     rdx, rbp; Irp
0x14002689a  mov     [rax-10h], rcx
0x14002689e  lea     rcx, [rsp+88h+Event]
0x1400268a3  mov     [rax-8], rcx
0x1400268a7  mov     rcx, r13; DeviceObject
0x1400268aa  mov     byte ptr [rax-45h], 0E0h
0x1400268ae  call    cs:__imp_IofCallDriver
0x1400268b5  nop     dword ptr [rax+rax+00h]
0x1400268ba  mov     edi, eax
0x1400268bc  cmp     eax, 103h
0x1400268c1  jnz     short loc_1400268E5
0x1400268c3  xor     r9d, r9d; Alertable
0x1400268c6  mov     [rsp+88h+Irp], 0; Timeout
0x1400268cf  xor     r8d, r8d; WaitMode
0x1400268d2  lea     rcx, [rsp+88h+Event]; Object
0x1400268d7  xor     edx, edx; WaitReason
0x1400268d9  call    cs:__imp_KeWaitForSingleObject
0x1400268e0  nop     dword ptr [rax+rax+00h]
0x1400268e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400268ec  lea     rax, WPP_GLOBAL_Control
0x1400268f3  cmp     rcx, rax
0x1400268f6  jz      short loc_14002691D
0x1400268f8  mov     eax, [rcx+2Ch]
0x1400268fb  test    al, 1
0x1400268fd  jz      short loc_14002691D
0x1400268ff  cmp     byte ptr [rcx+29h], 4
0x140026903  jb      short loc_14002691D
0x140026905  movzx   eax, byte ptr [rbx+3]
0x140026909  mov     r9d, r14d
0x14002690c  mov     rcx, [rcx+18h]
0x140026910  mov     [rsp+88h+var_60], eax
0x140026914  mov     dword ptr [rsp+88h+Irp], edi
0x140026918  call    WPP_SF_dDD
0x14002691d  movzx   eax, byte ptr [rbx+3]
0x140026921  and     eax, 0FFFFFF3Fh
0x140026926  cmp     eax, 1
0x140026929  jz      short loc_140026953
0x14002692b  cmp     eax, 12h
0x14002692e  jz      short loc_140026953
0x140026930  mov     edi, 0C0000001h
0x140026935  inc     r14d
0x140026938  jmp     loc_140026783
0x14002693d  mov     rcx, rbp; Irp
0x140026940  call    cs:__imp_IoFreeIrp
0x140026947  nop     dword ptr [rax+rax+00h]
0x14002694c  mov     edi, 0C000009Ah
0x140026951  jmp     short loc_140026970
0x140026953  mov     eax, [rbx+10h]
0x140026956  xor     edi, edi
0x140026958  mov     [r12], eax
0x14002695c  test    rsi, rsi
0x14002695f  jz      short loc_140026970
0x140026961  mov     rcx, rsi; Mdl
0x140026964  call    cs:__imp_IoFreeMdl
0x14002696b  nop     dword ptr [rax+rax+00h]
0x140026970  xor     edx, edx; Tag
0x140026972  mov     rcx, r15; P
0x140026975  call    cs:__imp_ExFreePoolWithTag
0x14002697c  nop     dword ptr [rax+rax+00h]
0x140026981  lea     r14, WPP_GLOBAL_Control
0x140026988  xor     edx, edx; Tag
0x14002698a  mov     rcx, rbx; P
0x14002698d  call    cs:__imp_ExFreePoolWithTag
0x140026994  nop     dword ptr [rax+rax+00h]
0x140026999  mov     rcx, cs:WPP_GLOBAL_Control
0x1400269a0  cmp     rcx, r14
0x1400269a3  jz      short loc_1400269CB
0x1400269a5  mov     edx, [rcx+2Ch]
0x1400269a8  test    dl, 1
0x1400269ab  jz      short loc_1400269CB
0x1400269ad  cmp     byte ptr [rcx+29h], 5
0x1400269b1  jb      short loc_1400269CB
0x1400269b3  mov     rcx, [rcx+18h]
0x1400269b7  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x1400269be  mov     edx, 0BAh
0x1400269c3  mov     r9d, edi
0x1400269c6  call    WPP_SF_d
0x1400269cb  mov     rbx, [rsp+88h+arg_0]
0x1400269d3  mov     eax, edi
0x1400269d5  add     rsp, 50h
0x1400269d9  pop     r15
0x1400269db  pop     r14
0x1400269dd  pop     r13
0x1400269df  pop     r12
0x1400269e1  pop     rdi
0x1400269e2  pop     rsi
0x1400269e3  pop     rbp
0x1400269e4  retn
```
