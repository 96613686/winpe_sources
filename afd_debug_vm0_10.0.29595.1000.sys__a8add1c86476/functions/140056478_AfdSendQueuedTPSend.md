# AfdSendQueuedTPSend

- ea: `0x140056478`
- end: `0x1400566fe`
- name: `AfdSendQueuedTPSend`
- size: `646`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003f588`
- `0x140042270`
- `0x140056704`

## callees

- `0x14000ce60`
- `0x14000de50`
- `0x14000ea50`
- `0x140010360`
- `0x140011350`
- `0x140011670`
- `0x14002c9d0`
- `0x14002cae0`
- `0x140056478`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140056600`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140056600`
- `ntoskrnl!IofCompleteRequest` at `0x1400566e6`
- `ntoskrnl!IofCompleteRequest` at `0x1400566e6`
- `ntoskrnl!IofCallDriver` at `0x1400565b6`
- `ntoskrnl!IofCallDriver` at `0x1400565b6`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400565ed`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x1400565ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140056626`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140056626`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140056615`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140056615`

## pseudocode

```c
void __fastcall AfdSendQueuedTPSend(__int64 a1, _QWORD *a2, __int64 a3)
{
  int v4; // r10d
  int v6; // eax
  unsigned __int64 Entry; // rax
  __int64 *v8; // rax
  int v9; // ecx
  int v10; // r9d
  __int64 *v11; // rdx
  int v12; // ecx
  __int64 *i; // rax
  __int64 v14; // rcx
  char *v15; // rcx
  __int64 v16; // rcx
  CCHAR v17; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+80h] [rbp+18h] BYREF

  _InterlockedExchange64((volatile __int64 *)(a3 + 104), 0);
  v4 = (int)a2;
  if ( *(_BYTE *)(a3 + 68) )
  {
LABEL_24:
    Irql = 0;
    memset(&LockHandle, 0, sizeof(LockHandle));
    IoAcquireCancelSpinLock(&Irql);
    IoReleaseCancelSpinLock(Irql);
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)(a1 + 56), &LockHandle);
    KeReleaseInStackQueuedSpinLock(&LockHandle);
LABEL_25:
    if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
    {
      if ( (*(_DWORD *)(a3 + 136) & 0x200) != 0 )
      {
        v15 = *(char **)(a3 + 160);
        *(_QWORD *)(a3 + 160) = 0;
      }
      else
      {
        v15 = 0;
      }
      if ( *(_WORD *)a1 == 0xAFD1 )
      {
        if ( v15 )
        {
          AfdTLFastDgramSendComplete(v15, -1073741536, 0);
        }
        else
        {
          *(_QWORD *)(a3 + 136) = 1;
          AfdTLVcSendDgramComplete(a3, -1073741536, 0);
        }
      }
      else if ( v15 )
      {
        AfdTLBufferedSendComplete(v15, 3221225760LL, 0);
      }
      else
      {
        v16 = *(_QWORD *)(a1 + 192);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v16 + 8) + 248LL));
        *(_QWORD *)(a3 + 128) = v16;
        AfdTLSendComplete((PIRP)a3, -1073741536, 0);
      }
    }
    else
    {
      --*(_BYTE *)(a3 + 67);
      *(_QWORD *)(a3 + 184) -= 72LL;
      v17 = AfdPriorityBoost;
      *(_DWORD *)(a3 + 48) = -1073741536;
      *(_QWORD *)(a3 + 56) = 0;
      IofCompleteRequest((PIRP)a3, v17);
    }
    return;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x800) != 0 || (*(_DWORD *)(a3 + 136) & 1) != 0 )
  {
    if ( !*(_BYTE *)(a3 + 68) )
      goto LABEL_25;
    goto LABEL_24;
  }
  v6 = *(_DWORD *)(a3 + 136);
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    if ( (v6 & 0x200) != 0 )
    {
      Entry = *(_QWORD *)(a3 + 160);
      *(_QWORD *)(a3 + 160) = 0;
    }
    else
    {
      Entry = 0;
    }
    if ( *(_WORD *)a1 == 0xAFD1 )
    {
      if ( Entry )
      {
        AfdTLFastDgramSend(a1, Entry);
      }
      else
      {
        v8 = *(__int64 **)(a3 + 8);
        v9 = 0;
        while ( v8 )
        {
          v9 += *((_DWORD *)v8 + 10);
          v8 = (__int64 *)*v8;
        }
        AfdTLVcSendDgram((PIRP)a3);
      }
    }
    else
    {
      v10 = (*(_DWORD *)(a3 + 128) >> 5) & 1;
      *(_DWORD *)(a3 + 128) = 0;
      if ( Entry )
      {
        AfdTLStartBufferedVcSend(
          a2,
          *(_QWORD *)(Entry + 56),
          *(_DWORD *)(*(_QWORD *)(Entry + 56) + 40LL),
          v10,
          (struct _KSPIN_LOCK_QUEUE *)Entry);
      }
      else
      {
        v11 = *(__int64 **)(a3 + 8);
        v12 = 0;
        for ( i = v11; i; i = (__int64 *)*i )
          v12 += *((_DWORD *)i + 10);
        AfdTLStartVcSend(v4, (_DWORD)v11, a3, v12, v10, (PIRP)a3, 1);
      }
    }
  }
  else
  {
    v14 = *(_QWORD *)(a3 + 184);
    if ( (v6 & 0x200) == 0 )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 248));
    IofCallDriver(*(PDEVICE_OBJECT *)(v14 - 32), (PIRP)a3);
  }
}

```

## disassembly

```asm
0x140056478  mov     [rsp+arg_0], rbx
0x14005647d  push    rdi
0x14005647e  sub     rsp, 60h
0x140056482  xor     eax, eax
0x140056484  mov     rbx, r8
0x140056487  xchg    rax, [r8+68h]
0x14005648b  cmp     byte ptr [r8+44h], 0
0x140056490  mov     r10, rdx
0x140056493  mov     rdi, rcx
0x140056496  jnz     loc_1400565CE
0x14005649c  mov     eax, [rcx+8]
0x14005649f  bt      eax, 0Bh
0x1400564a3  jb      loc_1400565C7
0x1400564a9  mov     eax, [r8+88h]
0x1400564b0  test    al, 1
0x1400564b2  jnz     loc_1400565C7
0x1400564b8  mov     eax, [rcx+8]
0x1400564bb  bt      eax, 8
0x1400564bf  mov     eax, [r8+88h]
0x1400564c6  jnb     loc_14005659B
0x1400564cc  bt      eax, 9
0x1400564d0  jnb     short loc_1400564E6
0x1400564d2  mov     rax, [r8+0A0h]
0x1400564d9  mov     qword ptr [r8+0A0h], 0
0x1400564e4  jmp     short loc_1400564E8
0x1400564e6  xor     eax, eax
0x1400564e8  mov     edx, 0AFD1h
0x1400564ed  cmp     [rcx], dx
0x1400564f0  jnz     short loc_14005652A
0x1400564f2  test    rax, rax
0x1400564f5  jz      short loc_140056504
0x1400564f7  mov     rdx, rax
0x1400564fa  call    AfdTLFastDgramSend
0x1400564ff  jmp     loc_1400566F2
0x140056504  mov     rax, [r8+8]
0x140056508  xor     ecx, ecx
0x14005650a  jmp     short loc_140056512
0x14005650c  add     ecx, [rax+28h]
0x14005650f  mov     rax, [rax]
0x140056512  test    rax, rax
0x140056515  jnz     short loc_14005650C
0x140056517  mov     r8d, ecx
0x14005651a  mov     rdx, rdi
0x14005651d  mov     rcx, rbx; Irp
0x140056520  call    AfdTLVcSendDgram
0x140056525  jmp     loc_1400566F2
0x14005652a  mov     r9d, [r8+80h]
0x140056531  shr     r9d, 5
0x140056535  and     r9d, 1; int
0x140056539  mov     dword ptr [r8+80h], 0
0x140056544  test    rax, rax
0x140056547  jnz     short loc_140056581
0x140056549  mov     rdx, [r8+8]
0x14005654d  xor     ecx, ecx
0x14005654f  mov     rax, rdx
0x140056552  test    rdx, rdx
0x140056555  jz      short loc_140056562
0x140056557  add     ecx, [rax+28h]
0x14005655a  mov     rax, [rax]
0x14005655d  test    rax, rax
0x140056560  jnz     short loc_140056557
0x140056562  mov     [rsp+68h+var_38], 1
0x140056567  mov     [rsp+68h+var_40], rbx
0x14005656c  mov     dword ptr [rsp+68h+Entry], r9d
0x140056571  mov     r9d, ecx
0x140056574  mov     rcx, r10
0x140056577  call    AfdTLStartVcSend
0x14005657c  jmp     loc_1400566F2
0x140056581  mov     rdx, [rax+38h]; int
0x140056585  mov     rcx, r10; int
0x140056588  mov     [rsp+68h+Entry], rax; Entry
0x14005658d  mov     r8d, [rdx+28h]; int
0x140056591  call    AfdTLStartBufferedVcSend
0x140056596  jmp     loc_1400566F2
0x14005659b  mov     rcx, [r8+0B8h]
0x1400565a2  mov     rdx, rbx; Irp
0x1400565a5  bt      eax, 9
0x1400565a9  jb      short loc_1400565B2
0x1400565ab  lock inc dword ptr [rdi+0F8h]
0x1400565b2  mov     rcx, [rcx-20h]; DeviceObject
0x1400565b6  call    cs:__imp_IofCallDriver
0x1400565bd  nop     dword ptr [rax+rax+00h]
0x1400565c2  jmp     loc_1400566F2
0x1400565c7  cmp     byte ptr [r8+44h], 0
0x1400565cc  jz      short loc_140056632
0x1400565ce  xorps   xmm0, xmm0
0x1400565d1  mov     [rsp+68h+Irql], 0
0x1400565d9  xor     eax, eax
0x1400565db  lea     rcx, [rsp+68h+Irql]; Irql
0x1400565e3  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x1400565e8  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x1400565ed  call    cs:__imp_IoAcquireCancelSpinLock
0x1400565f4  nop     dword ptr [rax+rax+00h]
0x1400565f9  mov     cl, [rsp+68h+Irql]; Irql
0x140056600  call    cs:__imp_IoReleaseCancelSpinLock
0x140056607  nop     dword ptr [rax+rax+00h]
0x14005660c  lea     rcx, [rdi+38h]; SpinLock
0x140056610  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140056615  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005661c  nop     dword ptr [rax+rax+00h]
0x140056621  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140056626  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005662d  nop     dword ptr [rax+rax+00h]
0x140056632  mov     eax, [rdi+8]
0x140056635  bt      eax, 8
0x140056639  jnb     loc_1400566C3
0x14005663f  mov     eax, [rbx+88h]
0x140056645  bt      eax, 9
0x140056649  jnb     short loc_14005665F
0x14005664b  mov     rcx, [rbx+0A0h]
0x140056652  mov     qword ptr [rbx+0A0h], 0
0x14005665d  jmp     short loc_140056661
0x14005665f  xor     ecx, ecx; Entry
0x140056661  mov     edx, 0AFD1h
0x140056666  xor     r8d, r8d
0x140056669  cmp     [rdi], dx
0x14005666c  mov     edx, 0C0000120h
0x140056671  jnz     short loc_140056694
0x140056673  test    rcx, rcx
0x140056676  jz      short loc_14005667F
0x140056678  call    AfdTLFastDgramSendComplete
0x14005667d  jmp     short loc_1400566F2
0x14005667f  mov     rcx, rbx; __int64
0x140056682  mov     qword ptr [rbx+88h], 1
0x14005668d  call    AfdTLVcSendDgramComplete
0x140056692  jmp     short loc_1400566F2
0x140056694  test    rcx, rcx
0x140056697  jnz     short loc_1400566BC
0x140056699  mov     rcx, [rdi+0C0h]
0x1400566a0  mov     rax, [rcx+8]
0x1400566a4  lock inc dword ptr [rax+0F8h]
0x1400566ab  mov     [rbx+80h], rcx
0x1400566b2  mov     rcx, rbx; Irp
0x1400566b5  call    AfdTLSendComplete
0x1400566ba  jmp     short loc_1400566F2
0x1400566bc  call    AfdTLBufferedSendComplete
0x1400566c1  jmp     short loc_1400566F2
0x1400566c3  dec     byte ptr [rbx+43h]
0x1400566c6  mov     rcx, rbx; Irp
0x1400566c9  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x1400566d1  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x1400566d7  mov     dword ptr [rbx+30h], 0C0000120h
0x1400566de  mov     qword ptr [rbx+38h], 0
0x1400566e6  call    cs:__imp_IofCompleteRequest
0x1400566ed  nop     dword ptr [rax+rax+00h]
0x1400566f2  mov     rbx, [rsp+68h+arg_0]
0x1400566f7  add     rsp, 60h
0x1400566fb  pop     rdi
0x1400566fc  retn
```
