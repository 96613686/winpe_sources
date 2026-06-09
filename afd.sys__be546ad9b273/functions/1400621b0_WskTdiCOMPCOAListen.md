# WskTdiCOMPCOAListen

- ea: `0x1400621b0`
- end: `0x14006253d`
- name: `WskTdiCOMPCOAListen`
- size: `909`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002150`
- `0x140003670`
- `0x140005b60`
- `0x140015990`
- `0x1400621b0`
- `0x1400629ac`
- `0x140062a20`
- `0x140072840`
- `0x140072920`
- `0x140072980`

## import_xrefs

- `ntoskrnl!IoFreeIrp` at `0x140062218`
- `ntoskrnl!IoFreeIrp` at `0x140062381`
- `ntoskrnl!IoFreeIrp` at `0x1400624fd`
- `ntoskrnl!IoFreeIrp` at `0x140062218`
- `ntoskrnl!IoFreeIrp` at `0x140062381`
- `ntoskrnl!IoFreeIrp` at `0x1400624fd`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062209`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062372`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006239c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006245c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400624ee`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062209`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140062372`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006239c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x14006245c`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400624ee`
- `ntoskrnl!IoReuseIrp` at `0x1400623b0`
- `ntoskrnl!IoReuseIrp` at `0x140062470`
- `ntoskrnl!IoReuseIrp` at `0x1400623b0`
- `ntoskrnl!IoReuseIrp` at `0x140062470`
- `ntoskrnl!IofCallDriver` at `0x140062441`
- `ntoskrnl!IofCallDriver` at `0x140062441`

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
        CurrentStackLocation[-1].CompletionRoutine = (PIO_COMPLETION_ROUTINE)&WskTdiCOMPAccept;
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
0x1400621b0  mov     [rsp+arg_0], rbx
0x1400621b5  mov     [rsp+arg_18], rbp
0x1400621ba  push    rsi
0x1400621bb  push    rdi
0x1400621bc  push    r13
0x1400621be  push    r14
0x1400621c0  push    r15
0x1400621c2  sub     rsp, 50h
0x1400621c6  mov     rax, cs:__security_cookie
0x1400621cd  xor     rax, rsp
0x1400621d0  mov     [rsp+78h+var_30], rax
0x1400621d5  mov     rbx, [r8]
0x1400621d8  xorps   xmm0, xmm0
0x1400621db  xor     eax, eax
0x1400621dd  mov     rsi, r8
0x1400621e0  movups  [rsp+78h+var_58], xmm0
0x1400621e5  mov     [rsp+78h+var_38], rax
0x1400621ea  mov     rdi, rdx
0x1400621ed  movups  [rsp+78h+var_48], xmm0
0x1400621f2  mov     r14, [rbx+0C0h]
0x1400621f9  cmp     [r14+2], al
0x1400621fd  jz      short loc_140062233
0x1400621ff  mov     rdx, r8; Entry
0x140062202  lea     rcx, stru_1400877C0; Lookaside
0x140062209  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062210  nop     dword ptr [rax+rax+00h]
0x140062215  mov     rcx, rdi; Irp
0x140062218  call    cs:__imp_IoFreeIrp
0x14006221f  nop     dword ptr [rax+rax+00h]
0x140062224  xor     edx, edx
0x140062226  mov     rcx, rbx
0x140062229  call    WskTdiCloseEndpoint
0x14006222e  jmp     loc_140062511
0x140062233  cmp     [r14+120h], rax
0x14006223a  jz      loc_1400624E4
0x140062240  cmp     [rdx+30h], eax
0x140062243  jl      loc_1400624E4
0x140062249  mov     rcx, [r8+30h]
0x14006224d  mov     r13d, 2
0x140062253  mov     eax, [rbx+10h]
0x140062256  lea     r15, [rcx+6]
0x14006225a  test    al, 10h
0x14006225c  jnz     short loc_1400622AC
0x14006225e  movzx   eax, word ptr [rcx+4]
0x140062262  add     ax, r13w
0x140062266  movzx   ebp, ax
0x140062269  cmp     ebp, cs:AfdStandardAddressLength
0x14006226f  mov     edx, ebp
0x140062271  ja      short loc_14006227A
0x140062273  call    AfdAllocateZeroedFromLookasideList
0x140062278  jmp     short loc_14006228C
0x14006227a  xor     r9d, r9d
0x14006227d  mov     r8d, 52646641h
0x140062283  lea     ecx, [r9+40h]
0x140062287  call    AfdAllocatePoolPriority
0x14006228c  mov     [rbx+0C8h], rax
0x140062293  test    rax, rax
0x140062296  jz      loc_1400624E4
0x14006229c  mov     r8, rbp; Size
0x14006229f  mov     rdx, r15; Src
0x1400622a2  mov     rcx, rax; void *
0x1400622a5  call    memmove
0x1400622aa  jmp     short loc_1400622FE
0x1400622ac  mov     ecx, 17h; af
0x1400622b1  call    SOCKADDR_SIZE
0x1400622b6  movzx   edx, al
0x1400622b9  cmp     edx, cs:AfdStandardAddressLength
0x1400622bf  ja      short loc_1400622C8
0x1400622c1  call    AfdAllocateZeroedFromLookasideList
0x1400622c6  jmp     short loc_1400622DA
0x1400622c8  xor     r9d, r9d
0x1400622cb  mov     r8d, 52646641h
0x1400622d1  lea     ecx, [r9+40h]
0x1400622d5  call    AfdAllocatePoolPriority
0x1400622da  mov     [rbx+0C8h], rax
0x1400622e1  test    rax, rax
0x1400622e4  jz      loc_1400624E4
0x1400622ea  movzx   r9d, word ptr [r15+2]
0x1400622ef  lea     rdx, [r15+4]
0x1400622f3  xor     r8d, r8d
0x1400622f6  mov     rcx, rax
0x1400622f9  call    IN6ADDR_SETV4MAPPED
0x1400622fe  mov     edx, 1
0x140062303  lock xadd cs:dword_140087748, edx
0x14006230b  mov     qword ptr [rsp+78h+var_58], rbx
0x140062310  inc     edx
0x140062312  mov     dword ptr [rsp+78h+var_58+8], edx
0x140062316  mov     rax, [rbx+0C8h]
0x14006231d  mov     qword ptr [rsp+78h+var_48+8], rax
0x140062322  mov     rax, [r14+30h]
0x140062326  mov     qword ptr [rsp+78h+var_48], rax
0x14006232b  mov     [rbx+100h], edx
0x140062331  lea     rdx, [rsp+78h+var_58]
0x140062336  mov     rax, [r14+120h]
0x14006233d  mov     rcx, [r14+118h]
0x140062344  mov     rax, [rax+10h]
0x140062348  call    _guard_dispatch_icall
0x14006234d  mov     ecx, dword ptr [rsp+78h+var_38]
0x140062351  sub     ecx, 1
0x140062354  jz      loc_140062452
0x14006235a  sub     ecx, 1
0x14006235d  jz      short loc_140062392
0x14006235f  cmp     ecx, 1
0x140062362  jnz     loc_1400624E4
0x140062368  mov     rdx, rsi; Entry
0x14006236b  lea     rcx, stru_1400877C0; Lookaside
0x140062372  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062379  nop     dword ptr [rax+rax+00h]
0x14006237e  mov     rcx, rdi; Irp
0x140062381  call    cs:__imp_IoFreeIrp
0x140062388  nop     dword ptr [rax+rax+00h]
0x14006238d  jmp     loc_140062511
0x140062392  mov     rdx, rsi; Entry
0x140062395  lea     rcx, stru_1400877C0; Lookaside
0x14006239c  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400623a3  nop     dword ptr [rax+rax+00h]
0x1400623a8  mov     edx, 0C0000001h; Iostatus
0x1400623ad  mov     rcx, rdi; Irp
0x1400623b0  call    cs:__imp_IoReuseIrp
0x1400623b7  nop     dword ptr [rax+rax+00h]
0x1400623bc  mov     byte ptr [rdi+40h], 0
0x1400623c0  lea     rcx, WskTdiCOMPCOAReject
0x1400623c7  mov     rax, gs:188h
0x1400623d0  mov     [rdi+98h], rax
0x1400623d7  mov     rax, [rbx+98h]
0x1400623de  mov     [rdi+0C0h], rax
0x1400623e5  mov     rax, [rdi+0B8h]
0x1400623ec  mov     [rax-10h], rcx
0x1400623f0  mov     [rax-8], rbx
0x1400623f4  mov     byte ptr [rax-45h], 0E0h
0x1400623f8  mov     rcx, [rdi+0B8h]
0x1400623ff  mov     word ptr [rcx-48h], 60Fh
0x140062405  mov     rax, [rbx+0A0h]
0x14006240c  mov     [rcx-20h], rax
0x140062410  mov     rax, [rbx+98h]
0x140062417  mov     [rcx-40h], r13
0x14006241b  mov     qword ptr [rcx-30h], 0
0x140062423  mov     qword ptr [rcx-28h], 0
0x14006242b  mov     qword ptr [rcx-38h], 0
0x140062433  mov     rdx, rdi; Irp
0x140062436  mov     [rcx-18h], rax
0x14006243a  mov     rcx, [rbx+0A0h]; DeviceObject
0x140062441  call    cs:__imp_IofCallDriver
0x140062448  nop     dword ptr [rax+rax+00h]
0x14006244d  jmp     loc_140062511
0x140062452  mov     rdx, rsi; Entry
0x140062455  lea     rcx, stru_1400877C0; Lookaside
0x14006245c  call    cs:__imp_ExFreeToNPagedLookasideList
0x140062463  nop     dword ptr [rax+rax+00h]
0x140062468  mov     edx, 0C0000001h; Iostatus
0x14006246d  mov     rcx, rdi; Irp
0x140062470  call    cs:__imp_IoReuseIrp
0x140062477  nop     dword ptr [rax+rax+00h]
0x14006247c  mov     byte ptr [rdi+40h], 0
0x140062480  lea     rcx, WskTdiCOMPAccept
0x140062487  mov     rax, gs:188h
0x140062490  mov     [rdi+98h], rax
0x140062497  mov     rax, [rbx+98h]
0x14006249e  mov     [rdi+0C0h], rax
0x1400624a5  mov     rax, [rdi+0B8h]
0x1400624ac  mov     [rax-10h], rcx
0x1400624b0  mov     [rax-8], rbx
0x1400624b4  mov     byte ptr [rax-45h], 0E0h
0x1400624b8  mov     rcx, [rdi+0B8h]
0x1400624bf  mov     word ptr [rcx-48h], 50Fh
0x1400624c5  mov     rax, [rbx+0A0h]
0x1400624cc  mov     [rcx-20h], rax
0x1400624d0  mov     rax, [rbx+98h]
0x1400624d7  mov     qword ptr [rcx-40h], 0
0x1400624df  jmp     loc_14006242B
0x1400624e4  mov     rdx, rsi; Entry
0x1400624e7  lea     rcx, stru_1400877C0; Lookaside
0x1400624ee  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400624f5  nop     dword ptr [rax+rax+00h]
0x1400624fa  mov     rcx, rdi; Irp
0x1400624fd  call    cs:__imp_IoFreeIrp
0x140062504  nop     dword ptr [rax+rax+00h]
0x140062509  mov     rcx, rbx
0x14006250c  call    WskTdiCloseConnectionAndPopulate
0x140062511  mov     eax, 0C0000016h
0x140062516  mov     rcx, [rsp+78h+var_30]
0x14006251b  xor     rcx, rsp; StackCookie
0x14006251e  call    __security_check_cookie
0x140062523  lea     r11, [rsp+78h+var_28]
0x140062528  mov     rbx, [r11+30h]
0x14006252c  mov     rbp, [r11+48h]
0x140062530  mov     rsp, r11
0x140062533  pop     r15
0x140062535  pop     r14
0x140062537  pop     r13
0x140062539  pop     rdi
0x14006253a  pop     rsi
0x14006253b  retn
```
