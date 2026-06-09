# RefsFsdSetInformation(_VOLUME_DEVICE_OBJECT *,_IRP *)

- ea: `0x140099db0`
- end: `0x14009a11c`
- name: `?RefsFsdSetInformation@@YAJPEAU_VOLUME_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `876`
- prototype: `int(struct _VOLUME_DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x14000b1b0`
- `0x14000e0e0`
- `0x140050ba0`
- `0x140099db0`
- `0x14009a130`
- `0x1400a069c`
- `0x1401f3fc0`
- `0x14028d92c`
- `0x14031cca8`
- `0x14033a7a8`

## import_xrefs

- `ntoskrnl!IoGetTopLevelIrp` at `0x140099e66`
- `ntoskrnl!IoGetTopLevelIrp` at `0x140099e66`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140099f6c`
- `ntoskrnl!IoSetTopLevelIrp` at `0x140099f6c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140099e37`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140099e37`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140099e53`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x140099e53`
- `ntoskrnl!IoClearActivityIdThread` at `0x14009a10b`
- `ntoskrnl!IoClearActivityIdThread` at `0x14009a10b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009a000`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14009a000`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140099f2b`
- `ntoskrnl!IoIsOperationSynchronous` at `0x140099f2b`
- `ntoskrnl!IoWithinStackLimits` at `0x140099e7d`
- `ntoskrnl!IoWithinStackLimits` at `0x140099e7d`
- `ntoskrnl!KeInitializeEvent` at `0x140099e2b`
- `ntoskrnl!KeInitializeEvent` at `0x140099e2b`

## pseudocode

```c
__int64 __fastcall RefsFsdSetInformation(struct _VOLUME_DEVICE_OBJECT *a1, struct _IRP *a2)
{
  struct _IRP_CONTEXT *v4; // rdi
  bool v5; // r15
  ULONG_PTR TopLevelIrp; // rbx
  int v7; // edx
  bool v8; // cl
  unsigned int v9; // esi
  BOOLEAN IsOperationSynchronous; // al
  __int64 v12; // rax
  struct _IRP_CONTEXT *v13; // [rsp+28h] [rbp-A0h] BYREF
  int v14; // [rsp+30h] [rbp-98h]
  int v15; // [rsp+34h] [rbp-94h]
  __int128 v16; // [rsp+38h] [rbp-90h] BYREF
  __int64 v17; // [rsp+48h] [rbp-80h]
  PIRP Irp; // [rsp+50h] [rbp-78h]
  _QWORD v19[3]; // [rsp+58h] [rbp-70h] BYREF
  struct _KEVENT Event; // [rsp+70h] [rbp-58h] BYREF
  __int128 v21; // [rsp+88h] [rbp-40h] BYREF

  Irp = a2;
  v19[2] = a2;
  v16 = 0;
  v17 = 0;
  v4 = 0;
  v13 = 0;
  v14 = 0;
  memset(&Event, 0, sizeof(Event));
  v21 = 0;
  v19[0] = 0;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  KeEnterCriticalRegion();
  v15 = IoPropagateActivityIdToThread(a2, &v21, v19);
  v5 = 0;
  TopLevelIrp = (ULONG_PTR)IoGetTopLevelIrp();
  if ( IoWithinStackLimits(TopLevelIrp, 0x18u) && (TopLevelIrp & 3) == 0 )
    v5 = *(_DWORD *)(TopLevelIrp + 4) == 1397140410;
  v8 = 1;
  if ( !TopLevelIrp )
    goto LABEL_3;
  if ( TopLevelIrp <= 0xFFFF )
  {
    v8 = 0;
LABEL_3:
    DWORD1(v16) = 0;
    *((_QWORD *)&v16 + 1) = TopLevelIrp;
    v17 = 0;
    LOBYTE(v16) = v8;
    if ( v5 )
    {
      BYTE1(v16) = 1;
      BYTE2(v16) = *(_BYTE *)(TopLevelIrp + 2);
    }
    else
    {
      *(_WORD *)((char *)&v16 + 1) = 0;
    }
    TopLevelIrp = (ULONG_PTR)&v16;
    goto LABEL_6;
  }
  if ( !v5 || (v12 = *(_QWORD *)(TopLevelIrp + 16)) != 0 && (*(_DWORD *)(v12 + 4) & 0x200) != 0 )
  {
    v7 = -2147483646;
    v8 = TopLevelIrp != 2147483650;
    goto LABEL_3;
  }
LABEL_6:
  v19[1] = TopLevelIrp;
  while ( 1 )
  {
    if ( !v4 )
    {
      IsOperationSynchronous = IoIsOperationSynchronous(a2);
      RefsInitializeIrpContext(a2, IsOperationSynchronous, 1, &v13);
      if ( *(_QWORD *)(TopLevelIrp + 16) )
      {
        v4 = v13;
      }
      else
      {
        *(_DWORD *)(TopLevelIrp + 4) = 1397140410;
        v4 = v13;
        *(_QWORD *)(TopLevelIrp + 16) = v13;
        *((_QWORD *)v4 + 1) |= 0x100000uLL;
        IoSetTopLevelIrp((PIRP)TopLevelIrp);
      }
      *((_QWORD *)v4 + 13) = *(_QWORD *)(TopLevelIrp + 16);
    }
    RefsPreRequestProcessingExtend(v4, v7);
    *((_QWORD *)v4 + 19) = &Event;
    v9 = RefsCommonSetInformation(v4, a2);
    if ( v9 != 871 )
      break;
    a2->Tail.Overlay.CurrentStackLocation->Control &= ~1u;
    RefsWaitForOplockCompletionEvent(a2, &Event);
  }
  if ( v15 >= 0 )
    IoClearActivityIdThread(v19[0]);
  KeLeaveCriticalRegion();
  return v9;
}

```

## disassembly

```asm
0x140099db0  mov     r11, rsp
0x140099db3  mov     [r11+8], rbx
0x140099db7  mov     [r11+18h], rsi
0x140099dbb  push    rdi
0x140099dbc  push    r12
0x140099dbe  push    r13
0x140099dc0  push    r14
0x140099dc2  push    r15
0x140099dc4  sub     rsp, 0A0h
0x140099dcb  mov     rax, cs:__security_cookie
0x140099dd2  xor     rax, rsp
0x140099dd5  mov     [rsp+0C8h+var_30], rax
0x140099ddd  mov     r14, rdx
0x140099de0  mov     [rsp+0C8h+Irp], rdx
0x140099de5  mov     r13, rdx
0x140099de8  mov     [rsp+0C8h+var_60], rdx
0x140099ded  xorps   xmm0, xmm0
0x140099df0  xor     eax, eax
0x140099df2  movups  [rsp+0C8h+var_90], xmm0
0x140099df7  mov     [r11-80h], rax
0x140099dfb  xor     esi, esi
0x140099dfd  mov     [rsp+0C8h+Status], esi
0x140099e01  xor     edi, edi
0x140099e03  mov     [rsp+0C8h+var_A0], rdi
0x140099e08  xor     r12d, r12d
0x140099e0b  mov     [rsp+0C8h+var_98], r12d
0x140099e10  movups  xmmword ptr [rsp+0C8h+Event.Header], xmm0
0x140099e15  mov     [r11-48h], rax
0x140099e19  movups  xmmword ptr [r11-40h], xmm0
0x140099e1e  mov     [r11-70h], rax
0x140099e22  xor     r8d, r8d; State
0x140099e25  xor     edx, edx; Type
0x140099e27  lea     rcx, [r11-58h]; Event
0x140099e2b  call    cs:__imp_KeInitializeEvent
0x140099e32  nop     dword ptr [rax+rax+00h]
0x140099e37  call    cs:__imp_KeEnterCriticalRegion
0x140099e3e  nop     dword ptr [rax+rax+00h]
0x140099e43  lea     r8, [rsp+0C8h+var_70]
0x140099e48  lea     rdx, [rsp+0C8h+var_40]
0x140099e50  mov     rcx, r13
0x140099e53  call    cs:__imp_IoPropagateActivityIdToThread
0x140099e5a  nop     dword ptr [rax+rax+00h]
0x140099e5f  mov     [rsp+0C8h+var_94], eax
0x140099e63  xor     r15b, r15b
0x140099e66  call    cs:__imp_IoGetTopLevelIrp
0x140099e6d  nop     dword ptr [rax+rax+00h]
0x140099e72  mov     rbx, rax
0x140099e75  mov     edx, 18h; RegionSize
0x140099e7a  mov     rcx, rax; RegionStart
0x140099e7d  call    cs:__imp_IoWithinStackLimits
0x140099e84  nop     dword ptr [rax+rax+00h]
0x140099e89  test    eax, eax
0x140099e8b  jnz     loc_14009A09C
0x140099e91  mov     cl, 1
0x140099e93  test    rbx, rbx
0x140099e96  jnz     loc_14009A08C
0x140099e9c  xor     r8d, r8d
0x140099e9f  mov     dword ptr [rsp+0C8h+var_90+4], r8d
0x140099ea4  mov     qword ptr [rsp+0C8h+var_90+8], rbx
0x140099ea9  mov     [rsp+0C8h+var_80], r8
0x140099eae  mov     byte ptr [rsp+0C8h+var_90], cl
0x140099eb2  test    r15b, r15b
0x140099eb5  jnz     loc_14009A0F4
0x140099ebb  mov     word ptr [rsp+0C8h+var_90+1], si
0x140099ec0  lea     rbx, [rsp+0C8h+var_90]
0x140099ec5  mov     [rsp+0C8h+var_68], rbx
0x140099eca  test    rdi, rdi
0x140099ecd  jz      short loc_140099F28
0x140099ecf  cmp     esi, 0C0000188h
0x140099ed5  jz      loc_140099F8C
0x140099edb  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140099ede  call    ?RefsPreRequestProcessingExtend@@YAXPEAU_IRP_CONTEXT@@J@Z; RefsPreRequestProcessingExtend(_IRP_CONTEXT *,long)
0x140099ee3  lea     rax, [rsp+0C8h+Event]
0x140099ee8  mov     [rdi+98h], rax
0x140099eef  mov     rdx, r14; Irp
0x140099ef2  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140099ef5  call    ?RefsCommonSetInformation@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@@Z; RefsCommonSetInformation(_IRP_CONTEXT *,_IRP *)
0x140099efa  mov     esi, eax
0x140099efc  mov     [rsp+0C8h+Status], eax
0x140099f00  cmp     eax, 367h
0x140099f05  jnz     loc_140099FAF
0x140099f0b  mov     rcx, [r13+0B8h]
0x140099f12  and     byte ptr [rcx+3], 0FEh
0x140099f16  lea     rdx, [rsp+0C8h+Event]; Event
0x140099f1b  mov     rcx, r14; Irp
0x140099f1e  call    ?RefsWaitForOplockCompletionEvent@@YAXPEAU_IRP@@PEAU_KEVENT@@@Z; RefsWaitForOplockCompletionEvent(_IRP *,_KEVENT *)
0x140099f23  jmp     loc_14009A057
0x140099f28  mov     rcx, r14; Irp
0x140099f2b  call    cs:__imp_IoIsOperationSynchronous
0x140099f32  nop     dword ptr [rax+rax+00h]
0x140099f37  movzx   edx, al; unsigned __int8
0x140099f3a  lea     r9, [rsp+0C8h+var_A0]; struct _IRP_CONTEXT **
0x140099f3f  mov     r8b, 1; unsigned __int8
0x140099f42  mov     rcx, r14; Irp
0x140099f45  call    ?RefsInitializeIrpContext@@YAJPEAU_IRP@@EEPEAPEAU_IRP_CONTEXT@@@Z; RefsInitializeIrpContext(_IRP *,uchar,uchar,_IRP_CONTEXT * *)
0x140099f4a  cmp     qword ptr [rbx+10h], 0
0x140099f4f  jnz     short loc_140099F85
0x140099f51  mov     dword ptr [rbx+4], 5346ABBAh
0x140099f58  mov     rdi, [rsp+0C8h+var_A0]
0x140099f5d  mov     [rbx+10h], rdi
0x140099f61  or      qword ptr [rdi+8], 100000h
0x140099f69  mov     rcx, rbx; Irp
0x140099f6c  call    cs:__imp_IoSetTopLevelIrp
0x140099f73  nop     dword ptr [rax+rax+00h]
0x140099f78  mov     rax, [rbx+10h]
0x140099f7c  mov     [rdi+68h], rax
0x140099f80  jmp     loc_140099EDB
0x140099f85  mov     rdi, [rsp+0C8h+var_A0]
0x140099f8a  jmp     short loc_140099F78
0x140099f8c  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140099f8f  call    ?RefsCheckpointForLogFileFull@@YAXPEAU_IRP_CONTEXT@@@Z; RefsCheckpointForLogFileFull(_IRP_CONTEXT *)
0x140099f94  inc     r12d
0x140099f97  mov     [rsp+0C8h+var_98], r12d
0x140099f9c  cmp     r12d, 2
0x140099fa0  jb      loc_140099EDB
0x140099fa6  or      dword ptr [rdi+4], 10h
0x140099faa  jmp     loc_140099EDB
0x140099faf  jmp     short loc_140099FF5
0x140099fb1  mov     r14, [rsp+0C8h+Irp]
0x140099fb6  cmp     eax, 0C0000123h
0x140099fbb  jnz     short loc_14009A03C
0x140099fbd  mov     ecx, [r14+10h]
0x140099fc1  test    cl, 2
0x140099fc4  jz      short loc_14009A03C
0x140099fc6  mov     rdi, [rsp+0C8h+var_A0]
0x140099fcb  mov     dword ptr [rdi+10h], 0
0x140099fd2  mov     esi, [rsp+0C8h+Status]
0x140099fd6  mov     r8d, esi; Status
0x140099fd9  mov     rdx, r14; Irp
0x140099fdc  mov     rcx, rdi; struct _IRP_CONTEXT *
0x140099fdf  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x140099fe4  mov     rbx, [rsp+0C8h+var_68]
0x140099fe9  mov     r12d, [rsp+0C8h+var_98]
0x140099fee  mov     r13, [rsp+0C8h+var_60]
0x140099ff3  jmp     short loc_14009A057
0x140099ff5  cmp     [rsp+0C8h+var_94], 0
0x140099ffa  jge     loc_14009A106
0x14009a000  call    cs:__imp_KeLeaveCriticalRegion
0x14009a007  nop     dword ptr [rax+rax+00h]
0x14009a00c  mov     eax, esi
0x14009a00e  mov     rcx, [rsp+0C8h+var_30]
0x14009a016  xor     rcx, rsp; StackCookie
0x14009a019  call    __security_check_cookie
0x14009a01e  lea     r11, [rsp+0C8h+var_28]
0x14009a026  mov     rbx, [r11+30h]
0x14009a02a  mov     rsi, [r11+40h]
0x14009a02e  mov     rsp, r11
0x14009a031  pop     r15
0x14009a033  pop     r14
0x14009a035  pop     r13
0x14009a037  pop     r12
0x14009a039  pop     rdi
0x14009a03a  retn
0x14009a03c  mov     r8d, eax; int
0x14009a03f  mov     rdx, r14; struct _IRP *
0x14009a042  mov     rdi, [rsp+0C8h+var_A0]
0x14009a047  mov     rcx, rdi; struct _IRP_CONTEXT *
0x14009a04a  call    ?RefsProcessException@@YAJPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsProcessException(_IRP_CONTEXT *,_IRP *,long)
0x14009a04f  mov     esi, eax
0x14009a051  mov     [rsp+0C8h+Status], eax
0x14009a055  jmp     short loc_140099FE4
0x14009a057  cmp     esi, 0C00000D8h
0x14009a05d  jz      loc_140099ECA
0x14009a063  cmp     esi, 0C00001A8h
0x14009a069  jz      loc_140099ECA
0x14009a06f  cmp     esi, 0C0000188h
0x14009a075  jz      loc_140099ECA
0x14009a07b  cmp     esi, 367h
0x14009a081  jz      loc_140099ECA
0x14009a087  jmp     loc_140099FF5
0x14009a08c  cmp     rbx, 0FFFFh
0x14009a093  ja      short loc_14009A0BE
0x14009a095  xor     cl, cl
0x14009a097  jmp     loc_140099E9C
0x14009a09c  test    bl, 3
0x14009a09f  jnz     loc_140099E91
0x14009a0a5  movzx   r15d, r15b
0x14009a0a9  mov     eax, 1
0x14009a0ae  cmp     dword ptr [rbx+4], 5346ABBAh
0x14009a0b5  cmovz   r15d, eax
0x14009a0b9  jmp     loc_140099E91
0x14009a0be  test    r15b, r15b
0x14009a0c1  jz      short loc_14009A0DD
0x14009a0c3  mov     rax, [rbx+10h]
0x14009a0c7  test    rax, rax
0x14009a0ca  jz      loc_140099EC5
0x14009a0d0  test    dword ptr [rax+4], 200h
0x14009a0d7  jz      loc_140099EC5
0x14009a0dd  movzx   ecx, cl
0x14009a0e0  xor     r8d, r8d
0x14009a0e3  mov     edx, 80000002h
0x14009a0e8  cmp     rbx, rdx
0x14009a0eb  cmovz   ecx, r8d
0x14009a0ef  jmp     loc_140099E9F
0x14009a0f4  mov     byte ptr [rsp+0C8h+var_90+1], 1
0x14009a0f9  movzx   eax, byte ptr [rbx+2]
0x14009a0fd  mov     byte ptr [rsp+0C8h+var_90+2], al
0x14009a101  jmp     loc_140099EC0
0x14009a106  mov     rcx, [rsp+0C8h+var_70]
0x14009a10b  call    cs:__imp_IoClearActivityIdThread
0x14009a112  nop     dword ptr [rax+rax+00h]
0x14009a117  jmp     loc_14009A000
0x1401f5610  push    rbp
0x1401f5612  sub     rsp, 20h
0x1401f5616  mov     rbp, rdx
0x1401f5619  mov     rdx, rcx; struct _EXCEPTION_POINTERS *
0x1401f561c  mov     rcx, [rbp+28h]; struct _IRP_CONTEXT *
0x1401f5620  call    ?RefsExceptionFilter@@YAJPEAU_IRP_CONTEXT@@PEAU_EXCEPTION_POINTERS@@@Z; RefsExceptionFilter(_IRP_CONTEXT *,_EXCEPTION_POINTERS *)
0x1401f5625  nop
0x1401f5626  add     rsp, 20h
0x1401f562a  pop     rbp
0x1401f562b  retn
```
