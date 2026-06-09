# RefsFsdShutdown(_DEVICE_OBJECT *,_IRP *)

- ea: `0x1402d81c0`
- end: `0x1402d83e5`
- name: `?RefsFsdShutdown@@YAJPEAU_DEVICE_OBJECT@@PEAU_IRP@@@Z`
- size: `549`
- prototype: `int(struct _DEVICE_OBJECT *, struct _IRP *)`
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

## callees

- `0x14000e0e0`
- `0x140050b60`
- `0x140075660`
- `0x1400e6524`
- `0x140102fb8`
- `0x140110b24`
- `0x1401f3fc0`
- `0x1402d1744`
- `0x1402d81c0`
- `0x1402e6648`
- `0x1402fb01c`
- `0x140332720`

## import_xrefs

- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d8268`
- `ntoskrnl!IoSetTopLevelIrp` at `0x1402d8268`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402d8201`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1402d8201`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1402d821a`
- `ntoskrnl!IoPropagateActivityIdToThread` at `0x1402d821a`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402d83af`
- `ntoskrnl!IoClearActivityIdThread` at `0x1402d83af`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d83bb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1402d83bb`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d828b`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d8312`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d828b`
- `ntoskrnl!ExAcquireFastResourceExclusive` at `0x1402d8312`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d82a4`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d838a`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d82a4`
- `ntoskrnl!ExReleaseFastResource` at `0x1402d838a`

## pseudocode

```c
__int64 __fastcall RefsFsdShutdown(struct _DEVICE_OBJECT *a1, struct _IRP *a2)
{
  int v3; // esi
  struct _TOP_LEVEL_CONTEXT *v4; // rax
  __int64 v5; // r8
  struct _TOP_LEVEL_CONTEXT *v6; // rbx
  __int64 v7; // r8
  __int64 v9; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v11; // [rsp+48h] [rbp-B8h]
  __int128 v12; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_SUBJECT_CONTEXT v13; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v14; // [rsp+68h] [rbp-98h]
  __int64 v15; // [rsp+C8h] [rbp-38h]

  v10 = 0;
  v11 = 0;
  v12 = 0;
  v9 = 0;
  KeEnterCriticalRegion();
  v3 = IoPropagateActivityIdToThread(a2, &v12, &v9);
  RefsInitializeLocalIrpContext(a2, (struct _LARGE_IRP_CONTEXT *)&v13);
  v4 = RefsInitializeTopLevelIrp((struct _TOP_LEVEL_CONTEXT *)&v10, 0, 0);
  v6 = v4;
  if ( !*((_QWORD *)v4 + 2) )
  {
    *((_DWORD *)v4 + 1) = 1397140410;
    *((_QWORD *)v4 + 2) = &v13;
    v14 |= 0x100000uLL;
    IoSetTopLevelIrp((PIRP)v4);
  }
  LOBYTE(v5) = 1;
  v15 = *((_QWORD *)v6 + 2);
  ExAcquireFastResourceExclusive(&unk_1402680B8, 0, v5);
  LODWORD(dword_1402682AC) = (unsigned int)dword_1402682AC | 0x1000;
  ExReleaseFastResource(&unk_1402680B8, 0);
  if ( dword_140268858 )
  {
    RefsForEachVcb((struct _IRP_CONTEXT *)&v13, 0, RefsShutdownVolumeWorker<1>, 0, 0);
    RefsForEachVcb(
      (struct _IRP_CONTEXT *)&v13,
      0,
      (void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *))RefsNotifyVirtualDiskOfShutdownWorker,
      0,
      0);
  }
  RefsForEachVcb((struct _IRP_CONTEXT *)&v13, 0, RefsShutdownVolumeWorker<0>, 0, 0);
  LOBYTE(v7) = 1;
  ExAcquireFastResourceExclusive(&unk_1402680B8, 0, v7);
  TlgAggregateFlush();
  TlgUnregisterAggregateProvider(&dword_140247230);
  TraceLoggingUnregister_EtwUnregister(&dword_1402471F8);
  RegHandle = 0;
  McGenEventUnregister_EtwUnregister();
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 10, &WPP_8f08cc763a303a1a0d74e9065145e684_Traceguids);
  }
  WppCleanupKm();
  ExReleaseFastResource(&unk_1402680B8, 0);
  RefsCompleteRequest(&v13, a2, 0);
  if ( v3 >= 0 )
    IoClearActivityIdThread(v9);
  KeLeaveCriticalRegion();
  return 0;
}

```

## disassembly

```asm
0x1402d81c0  push    rbp
0x1402d81c2  push    rbx
0x1402d81c3  push    rsi
0x1402d81c4  push    rdi
0x1402d81c5  lea     rbp, [rsp-298h]
0x1402d81cd  sub     rsp, 398h
0x1402d81d4  mov     rax, cs:__security_cookie
0x1402d81db  xor     rax, rsp
0x1402d81de  mov     [rbp+2B0h+var_30], rax
0x1402d81e5  xorps   xmm0, xmm0
0x1402d81e8  xor     eax, eax
0x1402d81ea  movups  [rsp+3B0h+var_378], xmm0
0x1402d81ef  mov     [rsp+3B0h+var_368], rax
0x1402d81f4  mov     rdi, rdx
0x1402d81f7  movups  [rsp+3B0h+var_360], xmm0
0x1402d81fc  mov     [rsp+3B0h+var_380], rax
0x1402d8201  call    cs:__imp_KeEnterCriticalRegion
0x1402d8208  nop     dword ptr [rax+rax+00h]
0x1402d820d  lea     r8, [rsp+3B0h+var_380]
0x1402d8212  mov     rcx, rdi
0x1402d8215  lea     rdx, [rsp+3B0h+var_360]
0x1402d821a  call    cs:__imp_IoPropagateActivityIdToThread
0x1402d8221  nop     dword ptr [rax+rax+00h]
0x1402d8226  lea     rdx, [rsp+3B0h+var_350]; struct _LARGE_IRP_CONTEXT *
0x1402d822b  mov     rcx, rdi; struct _IRP *
0x1402d822e  mov     esi, eax
0x1402d8230  call    ?RefsInitializeLocalIrpContext@@YAJPEAU_IRP@@PEAU_LARGE_IRP_CONTEXT@@@Z; RefsInitializeLocalIrpContext(_IRP *,_LARGE_IRP_CONTEXT *)
0x1402d8235  xor     r8d, r8d; unsigned __int8
0x1402d8238  lea     rcx, [rsp+3B0h+var_378]; struct _TOP_LEVEL_CONTEXT *
0x1402d823d  xor     edx, edx; unsigned __int8
0x1402d823f  call    ?RefsInitializeTopLevelIrp@@YAPEAU_TOP_LEVEL_CONTEXT@@PEAU1@EE@Z; RefsInitializeTopLevelIrp(_TOP_LEVEL_CONTEXT *,uchar,uchar)
0x1402d8244  mov     rbx, rax
0x1402d8247  cmp     qword ptr [rax+10h], 0
0x1402d824c  jnz     short loc_1402D8274
0x1402d824e  mov     dword ptr [rax+4], 5346ABBAh
0x1402d8255  mov     rcx, rbx; Irp
0x1402d8258  lea     rax, [rsp+3B0h+var_350]
0x1402d825d  mov     [rbx+10h], rax
0x1402d8261  bts     [rsp+3B0h+var_348], 14h
0x1402d8268  call    cs:__imp_IoSetTopLevelIrp
0x1402d826f  nop     dword ptr [rax+rax+00h]
0x1402d8274  mov     rax, [rbx+10h]
0x1402d8278  mov     r8b, 1
0x1402d827b  lea     rbx, unk_1402680B8
0x1402d8282  mov     [rbp+2B0h+var_2E8], rax
0x1402d8286  mov     rcx, rbx
0x1402d8289  xor     edx, edx
0x1402d828b  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402d8292  nop     dword ptr [rax+rax+00h]
0x1402d8297  bts     cs:dword_1402682AC, 0Ch
0x1402d829f  xor     edx, edx
0x1402d82a1  mov     rcx, rbx
0x1402d82a4  call    cs:__imp_ExReleaseFastResource
0x1402d82ab  nop     dword ptr [rax+rax+00h]
0x1402d82b0  cmp     cs:dword_140268858, 0
0x1402d82b7  jbe     short loc_1402D82EF
0x1402d82b9  xor     r9d, r9d; void *
0x1402d82bc  mov     [rsp+3B0h+var_390], 0; unsigned __int8
0x1402d82c1  lea     r8, ??$RefsShutdownVolumeWorker@$00@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAX@Z; void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *)
0x1402d82c8  xor     edx, edx; unsigned __int8 (*)(struct _IRP_CONTEXT *, struct _VCB *)
0x1402d82ca  lea     rcx, [rsp+3B0h+var_350]; struct _IRP_CONTEXT *
0x1402d82cf  call    ?RefsForEachVcb@@YAXPEAU_IRP_CONTEXT@@P6AE0PEAU_VCB@@@ZP6AX01PEAX@Z3E@Z; RefsForEachVcb(_IRP_CONTEXT *,uchar (*)(_IRP_CONTEXT *,_VCB *),void (*)(_IRP_CONTEXT *,_VCB *,void *),void *,uchar)
0x1402d82d4  xor     r9d, r9d; void *
0x1402d82d7  mov     [rsp+3B0h+var_390], 0; unsigned __int8
0x1402d82dc  lea     r8, ?RefsNotifyVirtualDiskOfShutdownWorker@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAX@Z; void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *)
0x1402d82e3  xor     edx, edx; unsigned __int8 (*)(struct _IRP_CONTEXT *, struct _VCB *)
0x1402d82e5  lea     rcx, [rsp+3B0h+var_350]; struct _IRP_CONTEXT *
0x1402d82ea  call    ?RefsForEachVcb@@YAXPEAU_IRP_CONTEXT@@P6AE0PEAU_VCB@@@ZP6AX01PEAX@Z3E@Z; RefsForEachVcb(_IRP_CONTEXT *,uchar (*)(_IRP_CONTEXT *,_VCB *),void (*)(_IRP_CONTEXT *,_VCB *,void *),void *,uchar)
0x1402d82ef  xor     r9d, r9d; void *
0x1402d82f2  mov     [rsp+3B0h+var_390], 0; unsigned __int8
0x1402d82f7  lea     r8, ??$RefsShutdownVolumeWorker@$0A@@@YAXPEAU_IRP_CONTEXT@@PEAU_VCB@@PEAX@Z; void (*)(struct _IRP_CONTEXT *, struct _VCB *, void *)
0x1402d82fe  xor     edx, edx; unsigned __int8 (*)(struct _IRP_CONTEXT *, struct _VCB *)
0x1402d8300  lea     rcx, [rsp+3B0h+var_350]; struct _IRP_CONTEXT *
0x1402d8305  call    ?RefsForEachVcb@@YAXPEAU_IRP_CONTEXT@@P6AE0PEAU_VCB@@@ZP6AX01PEAX@Z3E@Z; RefsForEachVcb(_IRP_CONTEXT *,uchar (*)(_IRP_CONTEXT *,_VCB *),void (*)(_IRP_CONTEXT *,_VCB *,void *),void *,uchar)
0x1402d830a  mov     r8b, 1
0x1402d830d  xor     edx, edx
0x1402d830f  mov     rcx, rbx
0x1402d8312  call    cs:__imp_ExAcquireFastResourceExclusive
0x1402d8319  nop     dword ptr [rax+rax+00h]
0x1402d831e  call    TlgAggregateFlush
0x1402d8323  lea     rcx, dword_140247230
0x1402d832a  call    TlgUnregisterAggregateProvider
0x1402d832f  lea     rcx, dword_1402471F8
0x1402d8336  call    TraceLoggingUnregister_EtwUnregister
0x1402d833b  mov     cs:RegHandle, 0
0x1402d8346  call    McGenEventUnregister_EtwUnregister
0x1402d834b  mov     rcx, cs:WPP_GLOBAL_Control
0x1402d8352  lea     rax, WPP_GLOBAL_Control
0x1402d8359  cmp     rcx, rax
0x1402d835c  jz      short loc_1402D8380
0x1402d835e  mov     eax, [rcx+2Ch]
0x1402d8361  test    al, 2
0x1402d8363  jz      short loc_1402D8380
0x1402d8365  cmp     byte ptr [rcx+29h], 2
0x1402d8369  jb      short loc_1402D8380
0x1402d836b  mov     rcx, [rcx+18h]
0x1402d836f  lea     r8, WPP_8f08cc763a303a1a0d74e9065145e684_Traceguids
0x1402d8376  mov     edx, 0Ah
0x1402d837b  call    WPP_SF_
0x1402d8380  call    WppCleanupKm
0x1402d8385  xor     edx, edx
0x1402d8387  mov     rcx, rbx
0x1402d838a  call    cs:__imp_ExReleaseFastResource
0x1402d8391  nop     dword ptr [rax+rax+00h]
0x1402d8396  xor     r8d, r8d; Status
0x1402d8399  lea     rcx, [rsp+3B0h+var_350]; struct _IRP_CONTEXT *
0x1402d839e  mov     rdx, rdi; Irp
0x1402d83a1  call    ?RefsCompleteRequest@@YAXPEAU_IRP_CONTEXT@@PEAU_IRP@@J@Z; RefsCompleteRequest(_IRP_CONTEXT *,_IRP *,long)
0x1402d83a6  test    esi, esi
0x1402d83a8  js      short loc_1402D83BB
0x1402d83aa  mov     rcx, [rsp+3B0h+var_380]
0x1402d83af  call    cs:__imp_IoClearActivityIdThread
0x1402d83b6  nop     dword ptr [rax+rax+00h]
0x1402d83bb  call    cs:__imp_KeLeaveCriticalRegion
0x1402d83c2  nop     dword ptr [rax+rax+00h]
0x1402d83c7  xor     eax, eax
0x1402d83c9  mov     rcx, [rbp+2B0h+var_30]
0x1402d83d0  xor     rcx, rsp; StackCookie
0x1402d83d3  call    __security_check_cookie
0x1402d83d8  add     rsp, 398h
0x1402d83df  pop     rdi
0x1402d83e0  pop     rsi
0x1402d83e1  pop     rbx
0x1402d83e2  pop     rbp
0x1402d83e3  retn
```
