# USBSTOR_IssueControlRequest

- ea: `0x14000d8cc`
- end: `0x14000daa8`
- name: `USBSTOR_IssueControlRequest`
- size: `476`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, PIRP Irp@<rdx>, __int64, __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14000d7e4`
- `0x140011ec8`

## callees

- `0x140001008`
- `0x140003630`
- `0x14000d8cc`
- `0x1400105e8`
- `0x140010664`
- `0x140013d40`

## import_xrefs

- `ntoskrnl!IofCallDriver` at `0x14000da17`
- `ntoskrnl!IofCallDriver` at `0x14000da17`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d9c8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000d9c8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000da04`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000da04`

## pseudocode

```c
__int64 __fastcall USBSTOR_IssueControlRequest(
        _QWORD *Object,
        PIRP Irp,
        int a3,
        __int64 a4,
        IO_COMPLETION_ROUTINE *a5,
        void *a6)
{
  __int64 v10; // r14
  PUNICODE_STRING FileName; // r15
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  struct _IO_STACK_LOCATION *v13; // rcx
  int v14; // eax
  bool v15; // bp
  __int64 v16; // rbx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x56u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids);
  }
  USBSTOR_LogEntry(1381253961, (__int64)Object, (__int64)Irp, 0);
  v10 = Object[8];
  FileName = Irp->Tail.Overlay.CurrentStackLocation->Parameters.QueryDirectory.FileName;
  memset((void *)(v10 + 392), 0, 0x88u);
  *(_DWORD *)(v10 + 392) = 1769608;
  *(_DWORD *)(v10 + 428) = a3;
  *(_QWORD *)(v10 + 432) = a4;
  *(_WORD *)(v10 + 524) = *(unsigned __int8 *)(*(_QWORD *)(v10 + 88) + 2LL);
  CurrentStackLocation = Irp->Tail.Overlay.CurrentStackLocation;
  CurrentStackLocation[-1].MajorFunction = 15;
  CurrentStackLocation[-1].Parameters.Read.ByteOffset.LowPart = 2228227;
  CurrentStackLocation[-1].Parameters.WMI.ProviderId = v10 + 392;
  v13 = Irp->Tail.Overlay.CurrentStackLocation;
  v13[-1].CompletionRoutine = a5;
  v13[-1].Context = a6;
  v13[-1].Control = -32;
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(v10 + 144), &LockHandle);
  v14 = *(_DWORD *)(v10 + 128) | 2;
  *(_QWORD *)(v10 + 328) = Irp;
  v15 = (v14 & 0x40) != 0 && (v14 & 8) == 0;
  *(_DWORD *)(v10 + 128) = v14 & 0xFFFFFFBF;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  v16 = IofCallDriver(*(PDEVICE_OBJECT *)(v10 + 24), Irp);
  if ( v15 )
  {
    USBSTOR_LogEntry(1330926147, (__int64)Object, (__int64)Irp, (__int64)FileName);
    USBSTOR_QueueResetDevice(Object, FileName);
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
  {
    WPP_SF_d(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x57u,
      (__int64)WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids,
      v16);
  }
  USBSTOR_LogEntry(1920230249, (__int64)Object, (__int64)Irp, v16);
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14000d8cc  push    rbx
0x14000d8ce  push    rbp
0x14000d8cf  push    rsi
0x14000d8d0  push    rdi
0x14000d8d1  push    r12
0x14000d8d3  push    r13
0x14000d8d5  push    r14
0x14000d8d7  push    r15
0x14000d8d9  sub     rsp, 48h
0x14000d8dd  xorps   xmm0, xmm0
0x14000d8e0  xor     eax, eax
0x14000d8e2  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x14000d8e7  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x14000d8ec  mov     rbp, r9
0x14000d8ef  mov     r12d, r8d
0x14000d8f2  mov     rdi, rdx
0x14000d8f5  mov     rsi, rcx
0x14000d8f8  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d8ff  lea     rax, WPP_GLOBAL_Control
0x14000d906  cmp     rcx, rax
0x14000d909  jz      short loc_14000D92D
0x14000d90b  mov     eax, [rcx+2Ch]
0x14000d90e  test    al, 1
0x14000d910  jz      short loc_14000D92D
0x14000d912  cmp     byte ptr [rcx+29h], 5
0x14000d916  jb      short loc_14000D92D
0x14000d918  mov     rcx, [rcx+18h]
0x14000d91c  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000d923  mov     edx, 56h ; 'V'
0x14000d928  call    WPP_SF_
0x14000d92d  xor     r9d, r9d
0x14000d930  mov     r8, rdi
0x14000d933  mov     rdx, rsi
0x14000d936  mov     ecx, 52544349h
0x14000d93b  call    USBSTOR_LogEntry
0x14000d940  mov     r14, [rsi+40h]
0x14000d944  xor     edx, edx; Val
0x14000d946  mov     rax, [rdi+0B8h]
0x14000d94d  mov     r8d, 88h; Size
0x14000d953  lea     rbx, [r14+188h]
0x14000d95a  mov     r15, [rax+10h]
0x14000d95e  mov     rcx, rbx; void *
0x14000d961  call    memset
0x14000d966  mov     dword ptr [rbx], 1B0088h
0x14000d96c  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x14000d971  mov     [rbx+24h], r12d
0x14000d975  mov     [rbx+28h], rbp
0x14000d979  mov     rax, [r14+58h]
0x14000d97d  movzx   ecx, byte ptr [rax+2]
0x14000d981  mov     [rbx+84h], cx
0x14000d988  mov     rax, [rdi+0B8h]
0x14000d98f  mov     byte ptr [rax-48h], 0Fh
0x14000d993  mov     dword ptr [rax-30h], 220003h
0x14000d99a  mov     [rax-40h], rbx
0x14000d99e  mov     rcx, [rdi+0B8h]
0x14000d9a5  mov     rax, [rsp+88h+arg_20]
0x14000d9ad  mov     [rcx-10h], rax
0x14000d9b1  mov     rax, [rsp+88h+arg_28]
0x14000d9b9  mov     [rcx-8], rax
0x14000d9bd  mov     byte ptr [rcx-45h], 0E0h
0x14000d9c1  lea     rcx, [r14+90h]; SpinLock
0x14000d9c8  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000d9cf  nop     dword ptr [rax+rax+00h]
0x14000d9d4  mov     eax, [r14+80h]
0x14000d9db  or      eax, 2
0x14000d9de  mov     [r14+148h], rdi
0x14000d9e5  test    al, 40h
0x14000d9e7  jz      short loc_14000D9F2
0x14000d9e9  test    al, 8
0x14000d9eb  jnz     short loc_14000D9F2
0x14000d9ed  mov     bpl, 1
0x14000d9f0  jmp     short loc_14000D9F5
0x14000d9f2  xor     bpl, bpl
0x14000d9f5  and     eax, 0FFFFFFBFh
0x14000d9f8  lea     rcx, [rsp+88h+LockHandle]; LockHandle
0x14000d9fd  mov     [r14+80h], eax
0x14000da04  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000da0b  nop     dword ptr [rax+rax+00h]
0x14000da10  mov     rcx, [r14+18h]; DeviceObject
0x14000da14  mov     rdx, rdi; Irp
0x14000da17  call    cs:__imp_IofCallDriver
0x14000da1e  nop     dword ptr [rax+rax+00h]
0x14000da23  movsxd  rbx, eax
0x14000da26  test    bpl, bpl
0x14000da29  jz      short loc_14000DA49
0x14000da2b  mov     r9, r15
0x14000da2e  mov     r8, rdi
0x14000da31  mov     rdx, rsi
0x14000da34  mov     ecx, 4F545243h
0x14000da39  call    USBSTOR_LogEntry
0x14000da3e  mov     rdx, r15; Context
0x14000da41  mov     rcx, rsi; Object
0x14000da44  call    USBSTOR_QueueResetDevice
0x14000da49  mov     rcx, cs:WPP_GLOBAL_Control
0x14000da50  lea     rax, WPP_GLOBAL_Control
0x14000da57  cmp     rcx, rax
0x14000da5a  jz      short loc_14000DA81
0x14000da5c  mov     eax, [rcx+2Ch]
0x14000da5f  test    al, 1
0x14000da61  jz      short loc_14000DA81
0x14000da63  cmp     byte ptr [rcx+29h], 5
0x14000da67  jb      short loc_14000DA81
0x14000da69  mov     rcx, [rcx+18h]
0x14000da6d  lea     r8, WPP_126bfc8a3cf7366a4716999bcf163092_Traceguids
0x14000da74  mov     edx, 57h ; 'W'
0x14000da79  mov     r9d, ebx
0x14000da7c  call    WPP_SF_d
0x14000da81  mov     r9, rbx
0x14000da84  mov     r8, rdi
0x14000da87  mov     rdx, rsi
0x14000da8a  mov     ecx, 72746369h
0x14000da8f  call    USBSTOR_LogEntry
0x14000da94  mov     eax, ebx
0x14000da96  add     rsp, 48h
0x14000da9a  pop     r15
0x14000da9c  pop     r14
0x14000da9e  pop     r13
0x14000daa0  pop     r12
0x14000daa2  pop     rdi
0x14000daa3  pop     rsi
0x14000daa4  pop     rbp
0x14000daa5  pop     rbx
0x14000daa6  retn
```
