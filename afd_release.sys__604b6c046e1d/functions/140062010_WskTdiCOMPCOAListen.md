# WskTdiCOMPCOAListen

- ea: `0x140062010`
- end: `0x14006239d`
- name: `WskTdiCOMPCOAListen`
- size: `909`
- prototype: `__int64 __fastcall(__int64, IRP *, __int64 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x140003670`
- `0x140005b60`
- `0x140015990`
- `0x140062010`
- `0x14006280c`
- `0x140062880`
- `0x1400726a0`
- `0x140072780`
- `0x140072800`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140062078`
- `ntoskrnl!IoFreeIrp` at `0x1400621e1`
- `ntoskrnl!IoFreeIrp` at `0x14006235d`
- `ntoskrnl!IoFreeIrp` at `0x140062078`
- `ntoskrnl!IoFreeIrp` at `0x1400621e1`
- `ntoskrnl!IoFreeIrp` at `0x14006235d`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062069`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400621d2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400621fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400622bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006234e`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062069`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400621d2`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400621fc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400622bc`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006234e`
- `ntoskrnl!IoReuseIrp` at `0x140062210`
- `ntoskrnl!IoReuseIrp` at `0x1400622d0`
- `ntoskrnl!IoReuseIrp` at `0x140062210`
- `ntoskrnl!IoReuseIrp` at `0x1400622d0`
- `ntoskrnl!IofCallDriver` at `0x1400622a1`
- `ntoskrnl!IofCallDriver` at `0x1400622a1`

## pseudocode

```c
__int64 __fastcall WskTdiCOMPCOAListen(__int64 a1, IRP *a2, __int64 *a3)
{
  __int64 v3; // rbx
  __int64 v6; // r14
  __int64 v7; // rcx
  unsigned __int16 *v8; // r15
  size_t v9; // rbp
  void *ZeroedFromLookasideList; // rax
  size_t v11; // rdx
  __int64 v12; // rcx
  __int64 PoolPriority; // rax
  struct _IO_STACK_LOCATION *v14; // rax
  struct _IO_STACK_LOCATION *v15; // rcx
  struct _FILE_OBJECT *v16; // rax
  struct _IO_STACK_LOCATION *CurrentStackLocation; // rax
  __int128 v19; // [rsp+20h] [rbp-58h] BYREF
  __int128 v20; // [rsp+30h] [rbp-48h]
  __int64 v21; // [rsp+40h] [rbp-38h]

  v3 = *a3;
  v19 = 0;
  v21 = 0;
  v20 = 0;
  v6 = *(_QWORD *)(v3 + 192);
  if ( !*(_BYTE *)(v6 + 2) )
  {
    if ( !*(_QWORD *)(v6 + 288) || a2->IoStatus.Status < 0 )
      goto LABEL_23;
    v7 = a3[6];
    v8 = (unsigned __int16 *)(v7 + 6);
    if ( (*(_DWORD *)(v3 + 16) & 0x10) != 0 )
    {
      v11 = SOCKADDR_SIZE(0x17u);
      if ( (unsigned int)v11 > (unsigned int)AfdStandardAddressLength )
        PoolPriority = AfdAllocatePoolPriority(64, v11, 1382311489, 0);
      else
        PoolPriority = (__int64)AfdAllocateZeroedFromLookasideList(v12, v11);
      *(_QWORD *)(v3 + 200) = PoolPriority;
      if ( !PoolPriority )
        goto LABEL_23;
      IN6ADDR_SETV4MAPPED(PoolPriority, v8 + 2, 0, v8[1]);
    }
    else
    {
      v9 = (unsigned __int16)(*(_WORD *)(v7 + 4) + 2);
      if ( (unsigned int)v9 > (unsigned int)AfdStandardAddressLength )
        ZeroedFromLookasideList = (void *)AfdAllocatePoolPriority(64, v9, 1382311489, 0);
      else
        ZeroedFromLookasideList = AfdAllocateZeroedFromLookasideList(v7, v9);
      *(_QWORD *)(v3 + 200) = ZeroedFromLookasideList;
      if ( !ZeroedFromLookasideList )
        goto LABEL_23;
      memmove(ZeroedFromLookasideList, v8, v9);
    }
    *(_QWORD *)&v19 = v3;
    DWORD2(v19) = _InterlockedIncrement(&dword_140087748);
    *((_QWORD *)&v20 + 1) = *(_QWORD *)(v3 + 200);
    *(_QWORD *)&v20 = *(_QWORD *)(v6 + 48);
    *(_DWORD *)(v3 + 256) = DWORD2(v19);
    (*(void (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)(v6 + 288) + 16LL))(*(_QWORD *)(v6 + 280), &v19);
    switch ( (_DWORD)v21 )
    {
      case 1:
        ExFreeToNPagedLookasideList(&stru_1400877C0, a3);
        IoReuseIrp(a2, -1073741823);
        a2->RequestorMode = 0;
        a2->Tail.Overlay.Thread = KeGetCurrentThread();
        a2->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(v3 + 152);
        CurrentStackLocation = a2->Tail.Overlay.CurrentStackLocation;
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)WskTdiCOMPAccept;
        CurrentStackLocation[-1].Context = (PVOID)v3;
        CurrentStackLocation[-1].Control = -32;
        v15 = a2->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v15[-1].MajorFunction = 1295;
        v15[-1].DeviceObject = *(PDEVICE_OBJECT *)(v3 + 160);
        v16 = *(struct _FILE_OBJECT **)(v3 + 152);
        v15[-1].Parameters.WMI.ProviderId = 0;
        break;
      case 2:
        ExFreeToNPagedLookasideList(&stru_1400877C0, a3);
        IoReuseIrp(a2, -1073741823);
        a2->RequestorMode = 0;
        a2->Tail.Overlay.Thread = KeGetCurrentThread();
        a2->Tail.Overlay.OriginalFileObject = *(PFILE_OBJECT *)(v3 + 152);
        v14 = a2->Tail.Overlay.CurrentStackLocation;
        v14[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPCOAReject;
        v14[-1].Context = (PVOID)v3;
        v14[-1].Control = -32;
        v15 = a2->Tail.Overlay.CurrentStackLocation;
        *(_WORD *)&v15[-1].MajorFunction = 1551;
        v15[-1].DeviceObject = *(PDEVICE_OBJECT *)(v3 + 160);
        v16 = *(struct _FILE_OBJECT **)(v3 + 152);
        v15[-1].Parameters.WMI.ProviderId = 2;
        v15[-1].Parameters.Read.ByteOffset.QuadPart = 0;
        v15[-1].Parameters.CreatePipe.Parameters = 0;
        break;
      case 3:
        ExFreeToNPagedLookasideList(&stru_1400877C0, a3);
        IoFreeIrp(a2);
        return 3221225494LL;
      default:
LABEL_23:
        ExFreeToNPagedLookasideList(&stru_1400877C0, a3);
        IoFreeIrp(a2);
        WskTdiCloseConnectionAndPopulate(v3);
        return 3221225494LL;
    }
    v15[-1].Parameters.QueryDirectory.FileName = 0;
    v15[-1].FileObject = v16;
    IofCallDriver(*(PDEVICE_OBJECT *)(v3 + 160), a2);
    return 3221225494LL;
  }
  ExFreeToNPagedLookasideList(&stru_1400877C0, a3);
  IoFreeIrp(a2);
  WskTdiCloseEndpoint(v3, 0);
  return 3221225494LL;
}

```

## disassembly

```asm
0x140062010  mov     [rsp+arg_0], rbx
0x140062015  mov     [rsp+arg_18], rbp
0x14006201a  push    rsi
0x14006201b  push    rdi
0x14006201c  push    r13
0x14006201e  push    r14
0x140062020  push    r15
0x140062022  sub     rsp, 50h
0x140062026  mov     rax, cs:__security_cookie
0x14006202d  xor     rax, rsp
0x140062030  mov     [rsp+78h+var_30], rax
0x140062035  mov     rbx, [r8]
0x140062038  xorps   xmm0, xmm0
0x14006203b  xor     eax, eax
0x14006203d  mov     rsi, r8
0x140062040  movups  [rsp+78h+var_58], xmm0
0x140062045  mov     [rsp+78h+var_38], rax
0x14006204a  mov     rdi, rdx
0x14006204d  movups  [rsp+78h+var_48], xmm0
0x140062052  mov     r14, [rbx+0C0h]
0x140062059  cmp     [r14+2], al
0x14006205d  jz      short loc_140062093
0x14006205f  mov     rdx, r8; Entry
0x140062062  lea     rcx, stru_1400877C0; Lookaside
0x140062069  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062070  nop     dword ptr [rax+rax+00h]
0x140062075  mov     rcx, rdi; Irp
0x140062078  call    cs:__imp_IoFreeIrp
0x14006207f  nop     dword ptr [rax+rax+00h]
0x140062084  xor     edx, edx
0x140062086  mov     rcx, rbx
0x140062089  call    WskTdiCloseEndpoint
0x14006208e  jmp     loc_140062371
0x140062093  cmp     [r14+120h], rax
0x14006209a  jz      loc_140062344
0x1400620a0  cmp     [rdx+30h], eax
0x1400620a3  jl      loc_140062344
0x1400620a9  mov     rcx, [r8+30h]
0x1400620ad  mov     r13d, 2
0x1400620b3  mov     eax, [rbx+10h]
0x1400620b6  lea     r15, [rcx+6]
0x1400620ba  test    al, 10h
0x1400620bc  jnz     short loc_14006210C
0x1400620be  movzx   eax, word ptr [rcx+4]
0x1400620c2  add     ax, r13w
0x1400620c6  movzx   ebp, ax
0x1400620c9  cmp     ebp, cs:AfdStandardAddressLength
0x1400620cf  mov     edx, ebp
0x1400620d1  ja      short loc_1400620DA
0x1400620d3  call    AfdAllocateZeroedFromLookasideList
0x1400620d8  jmp     short loc_1400620EC
0x1400620da  xor     r9d, r9d
0x1400620dd  mov     r8d, 52646641h
0x1400620e3  lea     ecx, [r9+40h]
0x1400620e7  call    AfdAllocatePoolPriority
0x1400620ec  mov     [rbx+0C8h], rax
0x1400620f3  test    rax, rax
0x1400620f6  jz      loc_140062344
0x1400620fc  mov     r8, rbp; Size
0x1400620ff  mov     rdx, r15; Src
0x140062102  mov     rcx, rax; void *
0x140062105  call    memmove
0x14006210a  jmp     short loc_14006215E
0x14006210c  mov     ecx, 17h; af
0x140062111  call    SOCKADDR_SIZE
0x140062116  movzx   edx, al
0x140062119  cmp     edx, cs:AfdStandardAddressLength
0x14006211f  ja      short loc_140062128
0x140062121  call    AfdAllocateZeroedFromLookasideList
0x140062126  jmp     short loc_14006213A
0x140062128  xor     r9d, r9d
0x14006212b  mov     r8d, 52646641h
0x140062131  lea     ecx, [r9+40h]
0x140062135  call    AfdAllocatePoolPriority
0x14006213a  mov     [rbx+0C8h], rax
0x140062141  test    rax, rax
0x140062144  jz      loc_140062344
0x14006214a  movzx   r9d, word ptr [r15+2]
0x14006214f  lea     rdx, [r15+4]
0x140062153  xor     r8d, r8d
0x140062156  mov     rcx, rax
0x140062159  call    IN6ADDR_SETV4MAPPED
0x14006215e  mov     edx, 1
0x140062163  lock xadd cs:dword_140087748, edx
0x14006216b  mov     qword ptr [rsp+78h+var_58], rbx
0x140062170  inc     edx
0x140062172  mov     dword ptr [rsp+78h+var_58+8], edx
0x140062176  mov     rax, [rbx+0C8h]
0x14006217d  mov     qword ptr [rsp+78h+var_48+8], rax
0x140062182  mov     rax, [r14+30h]
0x140062186  mov     qword ptr [rsp+78h+var_48], rax
0x14006218b  mov     [rbx+100h], edx
0x140062191  lea     rdx, [rsp+78h+var_58]
0x140062196  mov     rax, [r14+120h]
0x14006219d  mov     rcx, [r14+118h]
0x1400621a4  mov     rax, [rax+10h]
0x1400621a8  call    _guard_dispatch_icall
0x1400621ad  mov     ecx, dword ptr [rsp+78h+var_38]
0x1400621b1  sub     ecx, 1
0x1400621b4  jz      loc_1400622B2
0x1400621ba  sub     ecx, 1
0x1400621bd  jz      short loc_1400621F2
0x1400621bf  cmp     ecx, 1
0x1400621c2  jnz     loc_140062344
0x1400621c8  mov     rdx, rsi; Entry
0x1400621cb  lea     rcx, stru_1400877C0; Lookaside
0x1400621d2  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400621d9  nop     dword ptr [rax+rax+00h]
0x1400621de  mov     rcx, rdi; Irp
0x1400621e1  call    cs:__imp_IoFreeIrp
0x1400621e8  nop     dword ptr [rax+rax+00h]
0x1400621ed  jmp     loc_140062371
0x1400621f2  mov     rdx, rsi; Entry
0x1400621f5  lea     rcx, stru_1400877C0; Lookaside
0x1400621fc  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062203  nop     dword ptr [rax+rax+00h]
0x140062208  mov     edx, 0C0000001h; Iostatus
0x14006220d  mov     rcx, rdi; Irp
0x140062210  call    cs:__imp_IoReuseIrp
0x140062217  nop     dword ptr [rax+rax+00h]
0x14006221c  mov     byte ptr [rdi+40h], 0
0x140062220  lea     rcx, WskTdiCOMPCOAReject
0x140062227  mov     rax, gs:188h
0x140062230  mov     [rdi+98h], rax
0x140062237  mov     rax, [rbx+98h]
0x14006223e  mov     [rdi+0C0h], rax
0x140062245  mov     rax, [rdi+0B8h]
0x14006224c  mov     [rax-10h], rcx
0x140062250  mov     [rax-8], rbx
0x140062254  mov     byte ptr [rax-45h], 0E0h
0x140062258  mov     rcx, [rdi+0B8h]
0x14006225f  mov     word ptr [rcx-48h], 60Fh
0x140062265  mov     rax, [rbx+0A0h]
0x14006226c  mov     [rcx-20h], rax
0x140062270  mov     rax, [rbx+98h]
0x140062277  mov     [rcx-40h], r13
0x14006227b  mov     qword ptr [rcx-30h], 0
0x140062283  mov     qword ptr [rcx-28h], 0
0x14006228b  mov     qword ptr [rcx-38h], 0
0x140062293  mov     rdx, rdi; Irp
0x140062296  mov     [rcx-18h], rax
0x14006229a  mov     rcx, [rbx+0A0h]; DeviceObject
0x1400622a1  call    cs:__imp_IofCallDriver
0x1400622a8  nop     dword ptr [rax+rax+00h]
0x1400622ad  jmp     loc_140062371
0x1400622b2  mov     rdx, rsi; Entry
0x1400622b5  lea     rcx, stru_1400877C0; Lookaside
0x1400622bc  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400622c3  nop     dword ptr [rax+rax+00h]
0x1400622c8  mov     edx, 0C0000001h; Iostatus
0x1400622cd  mov     rcx, rdi; Irp
0x1400622d0  call    cs:__imp_IoReuseIrp
0x1400622d7  nop     dword ptr [rax+rax+00h]
0x1400622dc  mov     byte ptr [rdi+40h], 0
0x1400622e0  lea     rcx, WskTdiCOMPAccept
0x1400622e7  mov     rax, gs:188h
0x1400622f0  mov     [rdi+98h], rax
0x1400622f7  mov     rax, [rbx+98h]
0x1400622fe  mov     [rdi+0C0h], rax
0x140062305  mov     rax, [rdi+0B8h]
0x14006230c  mov     [rax-10h], rcx
0x140062310  mov     [rax-8], rbx
0x140062314  mov     byte ptr [rax-45h], 0E0h
0x140062318  mov     rcx, [rdi+0B8h]
0x14006231f  mov     word ptr [rcx-48h], 50Fh
0x140062325  mov     rax, [rbx+0A0h]
0x14006232c  mov     [rcx-20h], rax
0x140062330  mov     rax, [rbx+98h]
0x140062337  mov     qword ptr [rcx-40h], 0
0x14006233f  jmp     loc_14006228B
0x140062344  mov     rdx, rsi; Entry
0x140062347  lea     rcx, stru_1400877C0; Lookaside
0x14006234e  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062355  nop     dword ptr [rax+rax+00h]
0x14006235a  mov     rcx, rdi; Irp
0x14006235d  call    cs:__imp_IoFreeIrp
0x140062364  nop     dword ptr [rax+rax+00h]
0x140062369  mov     rcx, rbx
0x14006236c  call    WskTdiCloseConnectionAndPopulate
0x140062371  mov     eax, 0C0000016h
0x140062376  mov     rcx, [rsp+78h+var_30]
0x14006237b  xor     rcx, rsp; StackCookie
0x14006237e  call    __security_check_cookie
0x140062383  lea     r11, [rsp+78h+var_28]
0x140062388  mov     rbx, [r11+30h]
0x14006238c  mov     rbp, [r11+48h]
0x140062390  mov     rsp, r11
0x140062393  pop     r15
0x140062395  pop     r14
0x140062397  pop     r13
0x140062399  pop     rdi
0x14006239a  pop     rsi
0x14006239b  retn
```
