# AfdSuperDisconnect

- ea: `0x1400343d0`
- end: `0x140034650`
- name: `AfdSuperDisconnect`
- size: `640`
- prototype: `__int64 __fastcall(PIRP Irp)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14002fd7c`
- `0x1400343d0`
- `0x140042270`
- `0x1400436b8`
- `0x140055870`
- `0x140055d74`
- `0x140072870`
- `0x14009214c`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034436`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003447d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034436`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003447d`
- `ntoskrnl!IofCompleteRequest` at `0x140034638`
- `ntoskrnl!IofCompleteRequest` at `0x140034638`
- `ntoskrnl!IoIs32bitProcess` at `0x140034413`
- `ntoskrnl!IoIs32bitProcess` at `0x140034413`

## pseudocode

```c
__int64 __fastcall AfdSuperDisconnect(PIRP Irp, __int64 a2)
{
  __int64 v4; // r14
  unsigned int v5; // esi
  BOOLEAN v6; // al
  KPROCESSOR_MODE RequestorMode; // cl
  int ULongFromUser; // eax
  char v9; // al
  int v11; // [rsp+68h] [rbp+10h] BYREF
  int v12; // [rsp+70h] [rbp+18h] BYREF
  __int64 v13; // [rsp+78h] [rbp+20h]

  v11 = 0;
  v4 = *(_QWORD *)(*(_QWORD *)(a2 + 48) + 24LL);
  v13 = v4;
  if ( *(_WORD *)v4 == 6909 )
  {
    v5 = -1073741574;
LABEL_37:
    if ( (BYTE2(xmmword_1400875E0) & 4) != 0 )
      WPP_SF_qqD(1042, 60, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids, Irp, v4, v5);
    Irp->IoStatus.Information = 0;
    Irp->IoStatus.Status = v5;
    IofCompleteRequest(Irp, 0);
    return v5;
  }
  v6 = IoIs32bitProcess(Irp);
  RequestorMode = Irp->RequestorMode;
  if ( v6 )
  {
    v12 = 0;
    if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
      ExRaiseDatatypeMisalignment();
    if ( RequestorMode )
    {
      ULongFromUser = RtlReadULongFromUser(*(_QWORD *)(a2 + 32));
      v12 = ULongFromUser;
    }
    else
    {
      RtlCopyVolatileMemory(&v12, *(const void **)(a2 + 32), 4u);
      ULongFromUser = v12;
    }
    goto LABEL_10;
  }
  if ( RequestorMode && (*(_BYTE *)(a2 + 32) & 3) != 0 )
    ExRaiseDatatypeMisalignment();
  if ( RequestorMode )
  {
    ULongFromUser = RtlReadULongFromUser(*(_QWORD *)(a2 + 32));
LABEL_10:
    v11 = ULongFromUser;
    goto LABEL_17;
  }
  RtlCopyVolatileMemory(&v11, *(const void **)(a2 + 32), 4u);
  ULongFromUser = v11;
LABEL_17:
  if ( (ULongFromUser & 0xFFFFFFFD) != 0 )
  {
    v5 = -1073741811;
    goto LABEL_37;
  }
  *((_DWORD *)&Irp->Tail.CompletionKey + 2) = ULongFromUser | 1;
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(v4 + 368), *(unsigned __int8 *)(v4 + 2), 0) )
  {
    v5 = -1073741504;
    goto LABEL_37;
  }
  if ( *(_WORD *)v4 != 0xAFD2 || (v9 = *(_BYTE *)(v4 + 2), v9 != 4) && (v9 != 7 || (v11 & 2) == 0) )
  {
    v5 = -1073741504;
    _InterlockedExchange((volatile __int32 *)(v4 + 368), 0);
    goto LABEL_37;
  }
  if ( (v11 & 2) != 0 )
    *(_BYTE *)(v4 + 2) = 7;
  Irp->AssociatedIrp.MasterIrp = 0;
  Irp->Tail.Overlay.ListEntry.Flink = 0;
  Irp->Tail.Overlay.ListEntry.Blink = (struct _LIST_ENTRY *)1;
  Irp->IoStatus.Status = 0;
  Irp->IoStatus.Information = 0;
  Irp->Tail.Overlay.CurrentStackLocation->Control |= 1u;
  Irp->Tail.Overlay.DeviceQueueEntry.DeviceListEntry.Flink = 0;
  *((_DWORD *)&Irp->Tail.CompletionKey + 3) = 1;
  Irp->Tail.Overlay.DeviceQueueEntry.SortKey = 2;
  if ( !_InterlockedCompareExchange64((volatile signed __int64 *)(v4 + 360), (signed __int64)Irp, 0)
    || !(unsigned __int8)AfdEnqueueTPacketsIrp(v4, Irp) )
  {
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)AfdCancelTPackets);
    if ( (*(_DWORD *)(v4 + 8) & 0x800) != 0 || Irp->Cancel )
      AfdAbortTPackets((__int64)Irp, -1073741536);
    else
      AfdPerformTpDisconnect(Irp);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)&Irp->Tail.CompletionKey + 3, 0xFFFFFFFF) == 1 )
      AfdCompleteTPackets(Irp);
  }
  return 259;
}

```

## disassembly

```asm
0x1400343d0  mov     [rsp+arg_0], rcx
0x1400343d5  push    rbx
0x1400343d6  push    rsi
0x1400343d7  push    r14
0x1400343d9  sub     rsp, 40h
0x1400343dd  mov     rsi, rdx
0x1400343e0  mov     rbx, rcx
0x1400343e3  xor     eax, eax
0x1400343e5  mov     [rsp+58h+arg_8], eax
0x1400343e9  mov     rax, [rdx+30h]
0x1400343ed  mov     r14, [rax+18h]
0x1400343f1  mov     [rsp+58h+arg_18], r14
0x1400343f6  mov     eax, 1AFDh
0x1400343fb  cmp     [r14], ax
0x1400343ff  jnz     short loc_14003440B
0x140034401  mov     esi, 0C00000FAh
0x140034406  jmp     loc_1400345FD
0x14003440b  mov     [rsp+58h+var_28], 0
0x140034413  call    cs:__imp_IoIs32bitProcess
0x14003441a  nop     dword ptr [rax+rax+00h]
0x14003441f  mov     cl, [rbx+40h]
0x140034422  test    al, al
0x140034424  jz      short loc_140034473
0x140034426  xor     eax, eax
0x140034428  mov     [rsp+58h+arg_10], eax
0x14003442c  test    cl, cl
0x14003442e  jz      short loc_140034443
0x140034430  test    byte ptr [rsi+20h], 3
0x140034434  jz      short loc_140034443
0x140034436  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14003443d  nop     dword ptr [rax+rax+00h]
0x140034442  int     3; Trap to Debugger
0x140034443  mov     rdx, [rsi+20h]; Src
0x140034447  test    cl, cl
0x140034449  jz      short loc_140034459
0x14003444b  mov     rcx, rdx
0x14003444e  call    RtlReadULongFromUser
0x140034453  mov     [rsp+58h+arg_10], eax
0x140034457  jmp     short loc_14003446D
0x140034459  mov     r8d, 4; Size
0x14003445f  lea     rcx, [rsp+58h+arg_10]; void *
0x140034464  call    RtlCopyVolatileMemory
0x140034469  mov     eax, [rsp+58h+arg_10]
0x14003446d  mov     [rsp+58h+arg_8], eax
0x140034471  jmp     short loc_1400344B0
0x140034473  test    cl, cl
0x140034475  jz      short loc_14003448A
0x140034477  test    byte ptr [rsi+20h], 3
0x14003447b  jz      short loc_14003448A
0x14003447d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140034484  nop     dword ptr [rax+rax+00h]
0x140034489  int     3; Trap to Debugger
0x14003448a  mov     rdx, [rsi+20h]; Src
0x14003448e  test    cl, cl
0x140034490  jz      short loc_14003449C
0x140034492  mov     rcx, rdx
0x140034495  call    RtlReadULongFromUser
0x14003449a  jmp     short loc_14003446D
0x14003449c  mov     r8d, 4; Size
0x1400344a2  lea     rcx, [rsp+58h+arg_8]; void *
0x1400344a7  call    RtlCopyVolatileMemory
0x1400344ac  mov     eax, [rsp+58h+arg_8]
0x1400344b0  test    eax, 0FFFFFFFDh
0x1400344b5  jz      short loc_1400344C8
0x1400344b7  mov     [rsp+58h+var_28], 0C000000Dh
0x1400344bf  mov     esi, [rsp+58h+var_28]
0x1400344c3  jmp     loc_1400345FD
0x1400344c8  mov     edx, 1
0x1400344cd  or      eax, edx
0x1400344cf  mov     [rbx+80h], eax
0x1400344d5  movzx   ecx, byte ptr [r14+2]
0x1400344da  xor     eax, eax
0x1400344dc  lock cmpxchg [r14+170h], ecx
0x1400344e5  jz      short loc_1400344F1
0x1400344e7  mov     esi, 0C0000140h
0x1400344ec  jmp     loc_1400345FD
0x1400344f1  mov     eax, 0AFD2h
0x1400344f6  cmp     [r14], ax
0x1400344fa  jnz     loc_1400345DF
0x140034500  mov     al, [r14+2]
0x140034504  cmp     al, 4
0x140034506  jz      short loc_14003451B
0x140034508  cmp     al, 7
0x14003450a  jnz     loc_1400345DF
0x140034510  test    byte ptr [rsp+58h+arg_8], 2
0x140034515  jz      loc_1400345DF
0x14003451b  test    byte ptr [rsp+58h+arg_8], 2
0x140034520  jz      short loc_140034527
0x140034522  mov     byte ptr [r14+2], 7
0x140034527  mov     qword ptr [rbx+18h], 0
0x14003452f  mov     qword ptr [rbx+0A8h], 0
0x14003453a  mov     [rbx+0B0h], rdx
0x140034541  mov     dword ptr [rbx+30h], 0
0x140034548  mov     qword ptr [rbx+38h], 0
0x140034550  mov     rax, [rbx+0B8h]
0x140034557  or      [rax+3], dl
0x14003455a  mov     qword ptr [rbx+78h], 0
0x140034562  mov     [rbx+84h], edx
0x140034568  mov     dword ptr [rbx+88h], 2
0x140034572  xor     eax, eax
0x140034574  lock cmpxchg [r14+168h], rbx
0x14003457d  jz      short loc_14003458E
0x14003457f  mov     rdx, rbx
0x140034582  mov     rcx, r14
0x140034585  call    AfdEnqueueTPacketsIrp
0x14003458a  test    al, al
0x14003458c  jnz     short loc_1400345D8
0x14003458e  lea     rax, AfdCancelTPackets
0x140034595  xchg    rax, [rbx+68h]
0x140034599  mov     eax, [r14+8]
0x14003459d  bt      eax, 0Bh
0x1400345a1  jb      short loc_1400345B3
0x1400345a3  cmp     byte ptr [rbx+44h], 0
0x1400345a7  jnz     short loc_1400345B3
0x1400345a9  mov     rcx, rbx
0x1400345ac  call    AfdPerformTpDisconnect
0x1400345b1  jmp     short loc_1400345C0
0x1400345b3  mov     edx, 0C0000120h
0x1400345b8  mov     rcx, rbx
0x1400345bb  call    AfdAbortTPackets
0x1400345c0  or      eax, 0FFFFFFFFh
0x1400345c3  lock xadd [rbx+84h], eax
0x1400345cb  cmp     eax, 1
0x1400345ce  jnz     short loc_1400345D8
0x1400345d0  mov     rcx, rbx; Irp
0x1400345d3  call    AfdCompleteTPackets
0x1400345d8  mov     eax, 103h
0x1400345dd  jmp     short loc_140034646
0x1400345df  mov     esi, 0C0000140h
0x1400345e4  xor     eax, eax
0x1400345e6  xchg    eax, [r14+170h]
0x1400345ed  jmp     short loc_1400345FD
0x1400345ef  mov     rbx, [rsp+58h+arg_0]
0x1400345f4  mov     esi, [rsp+58h+var_28]
0x1400345f8  mov     r14, [rsp+58h+arg_18]
0x1400345fd  test    byte ptr cs:xmmword_1400875E0+2, 4
0x140034604  jz      short loc_140034628
0x140034606  mov     edx, 3Ch ; '<'
0x14003460b  mov     ecx, 412h
0x140034610  mov     [rsp+58h+var_30], esi
0x140034614  mov     [rsp+58h+var_38], r14
0x140034619  mov     r9, rbx
0x14003461c  lea     r8, WPP_854aaf7e57ed31daf99bd98e8a0637b6_Traceguids
0x140034623  call    WPP_SF_qqD
0x140034628  mov     qword ptr [rbx+38h], 0
0x140034630  mov     [rbx+30h], esi
0x140034633  xor     edx, edx; PriorityBoost
0x140034635  mov     rcx, rbx; Irp
0x140034638  call    cs:__imp_IofCompleteRequest
0x14003463f  nop     dword ptr [rax+rax+00h]
0x140034644  mov     eax, esi
0x140034646  add     rsp, 40h
0x14003464a  pop     r14
0x14003464c  pop     rsi
0x14003464d  pop     rbx
0x14003464e  retn
0x140073b61  push    rbp
0x140073b63  sub     rsp, 30h
0x140073b67  mov     rbp, rdx
0x140073b6a  mov     r8, rcx
0x140073b6d  lea     r9, [rbp+30h]
0x140073b71  mov     edx, 2219h
0x140073b76  lea     rcx, aMinioSocketsWi_12; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x140073b7d  call    AfdExceptionFilter
0x140073b82  nop
0x140073b83  add     rsp, 30h
0x140073b87  pop     rbp
0x140073b88  retn
```
