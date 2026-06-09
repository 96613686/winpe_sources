# AfdSendQueuedTPSend

- ea: `0x1400563d8`
- end: `0x14005665e`
- name: `AfdSendQueuedTPSend`
- size: `646`
- prototype: `void __fastcall(__int64, struct _LIST_ENTRY *, __int64, __int64)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x14003f568`
- `0x140042250`
- `0x140056664`

## callees

- `0x14000ce60`
- `0x14000de50`
- `0x14000ea50`
- `0x140010360`
- `0x140011350`
- `0x140011670`
- `0x14002c9d0`
- `0x14002cae0`
- `0x1400563d8`

## import_xrefs

- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140056560`
- `ntoskrnl!IoReleaseCancelSpinLock` at `0x140056560`
- `ntoskrnl!IofCompleteRequest` at `0x140056646`
- `ntoskrnl!IofCompleteRequest` at `0x140056646`
- `ntoskrnl!IofCallDriver` at `0x140056516`
- `ntoskrnl!IofCallDriver` at `0x140056516`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005654d`
- `ntoskrnl!IoAcquireCancelSpinLock` at `0x14005654d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140056586`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140056586`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140056575`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140056575`

## pseudocode

```c
void __fastcall AfdSendQueuedTPSend(__int64 a1, struct _LIST_ENTRY *a2, __int64 a3, __int64 a4)
{
  int v7; // eax
  unsigned __int64 Entry; // rax
  __int64 *v9; // rax
  unsigned int v10; // ecx
  int v11; // r9d
  __int64 v12; // rdx
  unsigned int v13; // ecx
  __int64 i; // rax
  __int64 v15; // rcx
  char *v16; // rcx
  __int64 v17; // rcx
  CCHAR v18; // dl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+40h] [rbp-28h] BYREF
  KIRQL Irql; // [rsp+80h] [rbp+18h] BYREF

  _InterlockedExchange64((volatile __int64 *)(a3 + 104), 0);
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
        v16 = *(char **)(a3 + 160);
        *(_QWORD *)(a3 + 160) = 0;
      }
      else
      {
        v16 = 0;
      }
      if ( *(_WORD *)a1 == 0xAFD1 )
      {
        if ( v16 )
        {
          AfdTLFastDgramSendComplete(v16, -1073741536, 0, a4);
        }
        else
        {
          *(_QWORD *)(a3 + 136) = 1;
          AfdTLVcSendDgramComplete(a3, -1073741536, 0);
        }
      }
      else if ( v16 )
      {
        AfdTLBufferedSendComplete((__int64)v16, -1073741536, 0);
      }
      else
      {
        v17 = *(_QWORD *)(a1 + 192);
        _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(v17 + 8) + 248LL));
        *(_QWORD *)(a3 + 128) = v17;
        AfdTLSendComplete((PIRP)a3, -1073741536, 0);
      }
    }
    else
    {
      --*(_BYTE *)(a3 + 67);
      *(_QWORD *)(a3 + 184) -= 72LL;
      v18 = AfdPriorityBoost;
      *(_DWORD *)(a3 + 48) = -1073741536;
      *(_QWORD *)(a3 + 56) = 0;
      IofCompleteRequest((PIRP)a3, v18);
    }
    return;
  }
  if ( (*(_DWORD *)(a1 + 8) & 0x800) != 0 || (*(_DWORD *)(a3 + 136) & 1) != 0 )
  {
    if ( !*(_BYTE *)(a3 + 68) )
      goto LABEL_25;
    goto LABEL_24;
  }
  v7 = *(_DWORD *)(a3 + 136);
  if ( (*(_DWORD *)(a1 + 8) & 0x100) != 0 )
  {
    if ( (v7 & 0x200) != 0 )
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
        v9 = *(__int64 **)(a3 + 8);
        v10 = 0;
        while ( v9 )
        {
          v10 += *((_DWORD *)v9 + 10);
          v9 = (__int64 *)*v9;
        }
        AfdTLVcSendDgram((PIRP)a3, a1, v10);
      }
    }
    else
    {
      v11 = (*(_DWORD *)(a3 + 128) >> 5) & 1;
      *(_DWORD *)(a3 + 128) = 0;
      if ( Entry )
      {
        AfdTLStartBufferedVcSend(
          a2,
          *(_QWORD *)(Entry + 56),
          *(_DWORD *)(*(_QWORD *)(Entry + 56) + 40LL),
          v11,
          (struct _KSPIN_LOCK_QUEUE *)Entry);
      }
      else
      {
        v12 = *(_QWORD *)(a3 + 8);
        v13 = 0;
        for ( i = v12; i; i = *(_QWORD *)i )
          v13 += *(_DWORD *)(i + 40);
        AfdTLStartVcSend(a2, v12, a3, v13, v11, (PIRP)a3, 1);
      }
    }
  }
  else
  {
    v15 = *(_QWORD *)(a3 + 184);
    if ( (v7 & 0x200) == 0 )
      _InterlockedIncrement((volatile signed __int32 *)(a1 + 248));
    IofCallDriver(*(PDEVICE_OBJECT *)(v15 - 32), (PIRP)a3);
  }
}

```

## disassembly

```asm
0x1400563d8  mov     [rsp+arg_0], rbx
0x1400563dd  push    rdi
0x1400563de  sub     rsp, 60h
0x1400563e2  xor     eax, eax
0x1400563e4  mov     rbx, r8
0x1400563e7  xchg    rax, [r8+68h]
0x1400563eb  cmp     byte ptr [r8+44h], 0
0x1400563f0  mov     r10, rdx
0x1400563f3  mov     rdi, rcx
0x1400563f6  jnz     loc_14005652E
0x1400563fc  mov     eax, [rcx+8]
0x1400563ff  bt      eax, 0Bh
0x140056403  jb      loc_140056527
0x140056409  mov     eax, [r8+88h]
0x140056410  test    al, 1
0x140056412  jnz     loc_140056527
0x140056418  mov     eax, [rcx+8]
0x14005641b  bt      eax, 8
0x14005641f  mov     eax, [r8+88h]
0x140056426  jnb     loc_1400564FB
0x14005642c  bt      eax, 9
0x140056430  jnb     short loc_140056446
0x140056432  mov     rax, [r8+0A0h]
0x140056439  mov     qword ptr [r8+0A0h], 0
0x140056444  jmp     short loc_140056448
0x140056446  xor     eax, eax
0x140056448  mov     edx, 0AFD1h
0x14005644d  cmp     [rcx], dx
0x140056450  jnz     short loc_14005648A
0x140056452  test    rax, rax
0x140056455  jz      short loc_140056464
0x140056457  mov     rdx, rax
0x14005645a  call    AfdTLFastDgramSend
0x14005645f  jmp     loc_140056652
0x140056464  mov     rax, [r8+8]
0x140056468  xor     ecx, ecx
0x14005646a  jmp     short loc_140056472
0x14005646c  add     ecx, [rax+28h]
0x14005646f  mov     rax, [rax]
0x140056472  test    rax, rax
0x140056475  jnz     short loc_14005646C
0x140056477  mov     r8d, ecx
0x14005647a  mov     rdx, rdi
0x14005647d  mov     rcx, rbx; Irp
0x140056480  call    AfdTLVcSendDgram
0x140056485  jmp     loc_140056652
0x14005648a  mov     r9d, [r8+80h]
0x140056491  shr     r9d, 5
0x140056495  and     r9d, 1; int
0x140056499  mov     dword ptr [r8+80h], 0
0x1400564a4  test    rax, rax
0x1400564a7  jnz     short loc_1400564E1
0x1400564a9  mov     rdx, [r8+8]
0x1400564ad  xor     ecx, ecx
0x1400564af  mov     rax, rdx
0x1400564b2  test    rdx, rdx
0x1400564b5  jz      short loc_1400564C2
0x1400564b7  add     ecx, [rax+28h]
0x1400564ba  mov     rax, [rax]
0x1400564bd  test    rax, rax
0x1400564c0  jnz     short loc_1400564B7
0x1400564c2  mov     [rsp+68h+var_38], 1
0x1400564c7  mov     [rsp+68h+var_40], rbx
0x1400564cc  mov     dword ptr [rsp+68h+Entry], r9d
0x1400564d1  mov     r9d, ecx
0x1400564d4  mov     rcx, r10
0x1400564d7  call    AfdTLStartVcSend
0x1400564dc  jmp     loc_140056652
0x1400564e1  mov     rdx, [rax+38h]; int
0x1400564e5  mov     rcx, r10; int
0x1400564e8  mov     [rsp+68h+Entry], rax; Entry
0x1400564ed  mov     r8d, [rdx+28h]; int
0x1400564f1  call    AfdTLStartBufferedVcSend
0x1400564f6  jmp     loc_140056652
0x1400564fb  mov     rcx, [r8+0B8h]
0x140056502  mov     rdx, rbx; Irp
0x140056505  bt      eax, 9
0x140056509  jb      short loc_140056512
0x14005650b  lock inc dword ptr [rdi+0F8h]
0x140056512  mov     rcx, [rcx-20h]; DeviceObject
0x140056516  call    cs:__imp_IofCallDriver
0x14005651d  nop     dword ptr [rax+rax+00h]
0x140056522  jmp     loc_140056652
0x140056527  cmp     byte ptr [r8+44h], 0
0x14005652c  jz      short loc_140056592
0x14005652e  xorps   xmm0, xmm0
0x140056531  mov     [rsp+68h+Irql], 0
0x140056539  xor     eax, eax
0x14005653b  lea     rcx, [rsp+68h+Irql]; Irql
0x140056543  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x140056548  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x14005654d  call    cs:__imp_IoAcquireCancelSpinLock
0x140056554  nop     dword ptr [rax+rax+00h]
0x140056559  mov     cl, [rsp+68h+Irql]; Irql
0x140056560  call    cs:__imp_IoReleaseCancelSpinLock
0x140056567  nop     dword ptr [rax+rax+00h]
0x14005656c  lea     rcx, [rdi+38h]; SpinLock
0x140056570  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140056575  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005657c  nop     dword ptr [rax+rax+00h]
0x140056581  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x140056586  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005658d  nop     dword ptr [rax+rax+00h]
0x140056592  mov     eax, [rdi+8]
0x140056595  bt      eax, 8
0x140056599  jnb     loc_140056623
0x14005659f  mov     eax, [rbx+88h]
0x1400565a5  bt      eax, 9
0x1400565a9  jnb     short loc_1400565BF
0x1400565ab  mov     rcx, [rbx+0A0h]
0x1400565b2  mov     qword ptr [rbx+0A0h], 0
0x1400565bd  jmp     short loc_1400565C1
0x1400565bf  xor     ecx, ecx; Entry
0x1400565c1  mov     edx, 0AFD1h
0x1400565c6  xor     r8d, r8d
0x1400565c9  cmp     [rdi], dx
0x1400565cc  mov     edx, 0C0000120h
0x1400565d1  jnz     short loc_1400565F4
0x1400565d3  test    rcx, rcx
0x1400565d6  jz      short loc_1400565DF
0x1400565d8  call    AfdTLFastDgramSendComplete
0x1400565dd  jmp     short loc_140056652
0x1400565df  mov     rcx, rbx; __int64
0x1400565e2  mov     qword ptr [rbx+88h], 1
0x1400565ed  call    AfdTLVcSendDgramComplete
0x1400565f2  jmp     short loc_140056652
0x1400565f4  test    rcx, rcx
0x1400565f7  jnz     short loc_14005661C
0x1400565f9  mov     rcx, [rdi+0C0h]
0x140056600  mov     rax, [rcx+8]
0x140056604  lock inc dword ptr [rax+0F8h]
0x14005660b  mov     [rbx+80h], rcx
0x140056612  mov     rcx, rbx; Irp
0x140056615  call    AfdTLSendComplete
0x14005661a  jmp     short loc_140056652
0x14005661c  call    AfdTLBufferedSendComplete
0x140056621  jmp     short loc_140056652
0x140056623  dec     byte ptr [rbx+43h]
0x140056626  mov     rcx, rbx; Irp
0x140056629  add     qword ptr [rbx+0B8h], 0FFFFFFFFFFFFFFB8h
0x140056631  mov     dl, cs:AfdPriorityBoost; PriorityBoost
0x140056637  mov     dword ptr [rbx+30h], 0C0000120h
0x14005663e  mov     qword ptr [rbx+38h], 0
0x140056646  call    cs:__imp_IofCompleteRequest
0x14005664d  nop     dword ptr [rax+rax+00h]
0x140056652  mov     rbx, [rsp+68h+arg_0]
0x140056657  add     rsp, 60h
0x14005665b  pop     rdi
0x14005665c  retn
```
