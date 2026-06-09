# AfdSuperDisconnect

- ea: `0x1400343b0`
- end: `0x140034630`
- name: `AfdSuperDisconnect`
- size: `640`
- prototype: `__int64 __fastcall(PIRP Irp, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14001ef30`

## callees

- `0x14002fd5c`
- `0x1400343b0`
- `0x140042250`
- `0x140043698`
- `0x1400557d0`
- `0x140055cd4`
- `0x1400726d0`
- `0x14009214c`
- `0x140094900`

## import_xrefs

- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034416`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003445d`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x140034416`
- `ntoskrnl!ExRaiseDatatypeMisalignment` at `0x14003445d`
- `ntoskrnl!IofCompleteRequest` at `0x140034618`
- `ntoskrnl!IofCompleteRequest` at `0x140034618`
- `ntoskrnl!IoIs32bitProcess` at `0x1400343f3`
- `ntoskrnl!IoIs32bitProcess` at `0x1400343f3`

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
      WPP_SF_qqD(1042, 60, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids, Irp, v4, v5);
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
    _InterlockedExchange64((volatile __int64 *)&Irp->CancelRoutine, (__int64)&AfdCancelTPackets);
    if ( (*(_DWORD *)(v4 + 8) & 0x800) != 0 || Irp->Cancel )
      AfdAbortTPackets(Irp, 3221225760LL);
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
0x1400343b0  mov     [rsp+arg_0], rcx
0x1400343b5  push    rbx
0x1400343b6  push    rsi
0x1400343b7  push    r14
0x1400343b9  sub     rsp, 40h
0x1400343bd  mov     rsi, rdx
0x1400343c0  mov     rbx, rcx
0x1400343c3  xor     eax, eax
0x1400343c5  mov     [rsp+58h+arg_8], eax
0x1400343c9  mov     rax, [rdx+30h]
0x1400343cd  mov     r14, [rax+18h]
0x1400343d1  mov     [rsp+58h+arg_18], r14
0x1400343d6  mov     eax, 1AFDh
0x1400343db  cmp     [r14], ax
0x1400343df  jnz     short loc_1400343EB
0x1400343e1  mov     esi, 0C00000FAh
0x1400343e6  jmp     loc_1400345DD
0x1400343eb  mov     [rsp+58h+var_28], 0
0x1400343f3  call    cs:__imp_IoIs32bitProcess
0x1400343fa  nop     dword ptr [rax+rax+00h]
0x1400343ff  mov     cl, [rbx+40h]
0x140034402  test    al, al
0x140034404  jz      short loc_140034453
0x140034406  xor     eax, eax
0x140034408  mov     [rsp+58h+arg_10], eax
0x14003440c  test    cl, cl
0x14003440e  jz      short loc_140034423
0x140034410  test    byte ptr [rsi+20h], 3
0x140034414  jz      short loc_140034423
0x140034416  call    cs:__imp_ExRaiseDatatypeMisalignment
0x14003441d  nop     dword ptr [rax+rax+00h]
0x140034422  int     3; Trap to Debugger
0x140034423  mov     rdx, [rsi+20h]; Src
0x140034427  test    cl, cl
0x140034429  jz      short loc_140034439
0x14003442b  mov     rcx, rdx
0x14003442e  call    RtlReadULongFromUser
0x140034433  mov     [rsp+58h+arg_10], eax
0x140034437  jmp     short loc_14003444D
0x140034439  mov     r8d, 4; Size
0x14003443f  lea     rcx, [rsp+58h+arg_10]; void *
0x140034444  call    RtlCopyVolatileMemory
0x140034449  mov     eax, [rsp+58h+arg_10]
0x14003444d  mov     [rsp+58h+arg_8], eax
0x140034451  jmp     short loc_140034490
0x140034453  test    cl, cl
0x140034455  jz      short loc_14003446A
0x140034457  test    byte ptr [rsi+20h], 3
0x14003445b  jz      short loc_14003446A
0x14003445d  call    cs:__imp_ExRaiseDatatypeMisalignment
0x140034464  nop     dword ptr [rax+rax+00h]
0x140034469  int     3; Trap to Debugger
0x14003446a  mov     rdx, [rsi+20h]; Src
0x14003446e  test    cl, cl
0x140034470  jz      short loc_14003447C
0x140034472  mov     rcx, rdx
0x140034475  call    RtlReadULongFromUser
0x14003447a  jmp     short loc_14003444D
0x14003447c  mov     r8d, 4; Size
0x140034482  lea     rcx, [rsp+58h+arg_8]; void *
0x140034487  call    RtlCopyVolatileMemory
0x14003448c  mov     eax, [rsp+58h+arg_8]
0x140034490  test    eax, 0FFFFFFFDh
0x140034495  jz      short loc_1400344A8
0x140034497  mov     [rsp+58h+var_28], 0C000000Dh
0x14003449f  mov     esi, [rsp+58h+var_28]
0x1400344a3  jmp     loc_1400345DD
0x1400344a8  mov     edx, 1
0x1400344ad  or      eax, edx
0x1400344af  mov     [rbx+80h], eax
0x1400344b5  movzx   ecx, byte ptr [r14+2]
0x1400344ba  xor     eax, eax
0x1400344bc  lock cmpxchg [r14+170h], ecx
0x1400344c5  jz      short loc_1400344D1
0x1400344c7  mov     esi, 0C0000140h
0x1400344cc  jmp     loc_1400345DD
0x1400344d1  mov     eax, 0AFD2h
0x1400344d6  cmp     [r14], ax
0x1400344da  jnz     loc_1400345BF
0x1400344e0  mov     al, [r14+2]
0x1400344e4  cmp     al, 4
0x1400344e6  jz      short loc_1400344FB
0x1400344e8  cmp     al, 7
0x1400344ea  jnz     loc_1400345BF
0x1400344f0  test    byte ptr [rsp+58h+arg_8], 2
0x1400344f5  jz      loc_1400345BF
0x1400344fb  test    byte ptr [rsp+58h+arg_8], 2
0x140034500  jz      short loc_140034507
0x140034502  mov     byte ptr [r14+2], 7
0x140034507  mov     qword ptr [rbx+18h], 0
0x14003450f  mov     qword ptr [rbx+0A8h], 0
0x14003451a  mov     [rbx+0B0h], rdx
0x140034521  mov     dword ptr [rbx+30h], 0
0x140034528  mov     qword ptr [rbx+38h], 0
0x140034530  mov     rax, [rbx+0B8h]
0x140034537  or      [rax+3], dl
0x14003453a  mov     qword ptr [rbx+78h], 0
0x140034542  mov     [rbx+84h], edx
0x140034548  mov     dword ptr [rbx+88h], 2
0x140034552  xor     eax, eax
0x140034554  lock cmpxchg [r14+168h], rbx
0x14003455d  jz      short loc_14003456E
0x14003455f  mov     rdx, rbx
0x140034562  mov     rcx, r14
0x140034565  call    AfdEnqueueTPacketsIrp
0x14003456a  test    al, al
0x14003456c  jnz     short loc_1400345B8
0x14003456e  lea     rax, AfdCancelTPackets
0x140034575  xchg    rax, [rbx+68h]
0x140034579  mov     eax, [r14+8]
0x14003457d  bt      eax, 0Bh
0x140034581  jb      short loc_140034593
0x140034583  cmp     byte ptr [rbx+44h], 0
0x140034587  jnz     short loc_140034593
0x140034589  mov     rcx, rbx
0x14003458c  call    AfdPerformTpDisconnect
0x140034591  jmp     short loc_1400345A0
0x140034593  mov     edx, 0C0000120h
0x140034598  mov     rcx, rbx
0x14003459b  call    AfdAbortTPackets
0x1400345a0  or      eax, 0FFFFFFFFh
0x1400345a3  lock xadd [rbx+84h], eax
0x1400345ab  cmp     eax, 1
0x1400345ae  jnz     short loc_1400345B8
0x1400345b0  mov     rcx, rbx; Irp
0x1400345b3  call    AfdCompleteTPackets
0x1400345b8  mov     eax, 103h
0x1400345bd  jmp     short loc_140034626
0x1400345bf  mov     esi, 0C0000140h
0x1400345c4  xor     eax, eax
0x1400345c6  xchg    eax, [r14+170h]
0x1400345cd  jmp     short loc_1400345DD
0x1400345cf  mov     rbx, [rsp+58h+arg_0]
0x1400345d4  mov     esi, [rsp+58h+var_28]
0x1400345d8  mov     r14, [rsp+58h+arg_18]
0x1400345dd  test    byte ptr cs:xmmword_1400875E0+2, 4
0x1400345e4  jz      short loc_140034608
0x1400345e6  mov     edx, 3Ch ; '<'
0x1400345eb  mov     ecx, 412h
0x1400345f0  mov     [rsp+58h+var_30], esi
0x1400345f4  mov     [rsp+58h+var_38], r14
0x1400345f9  mov     r9, rbx
0x1400345fc  lea     r8, WPP_148169eadf5b37b5a85ea383b1e42419_Traceguids
0x140034603  call    WPP_SF_qqD
0x140034608  mov     qword ptr [rbx+38h], 0
0x140034610  mov     [rbx+30h], esi
0x140034613  xor     edx, edx; PriorityBoost
0x140034615  mov     rcx, rbx; Irp
0x140034618  call    cs:__imp_IofCompleteRequest
0x14003461f  nop     dword ptr [rax+rax+00h]
0x140034624  mov     eax, esi
0x140034626  add     rsp, 40h
0x14003462a  pop     r14
0x14003462c  pop     rsi
0x14003462d  pop     rbx
0x14003462e  retn
0x1400739e1  push    rbp
0x1400739e3  sub     rsp, 30h
0x1400739e7  mov     rbp, rdx
0x1400739ea  mov     r8, rcx
0x1400739ed  lea     r9, [rbp+30h]
0x1400739f1  mov     edx, 2203h
0x1400739f6  lea     rcx, aMinioSocketsWi_12; "minio\\sockets\\winsock2\\wsp\\afdsys\\"...
0x1400739fd  call    AfdExceptionFilter
0x140073a02  nop
0x140073a03  add     rsp, 30h
0x140073a07  pop     rbp
0x140073a08  retn
```
