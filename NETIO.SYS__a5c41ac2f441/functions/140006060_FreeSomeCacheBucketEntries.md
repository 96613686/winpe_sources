# FreeSomeCacheBucketEntries

- ea: `0x140006060`
- end: `0x140006232`
- name: `FreeSomeCacheBucketEntries`
- size: `466`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14001aa50`
- `0x14001ce18`

## callees

- `0x140001464`
- `0x140004bf0`
- `0x140006060`
- `0x140006c40`
- `0x140008350`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140006106`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x140006106`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000609c`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14000609c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400061d1`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x1400061d1`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000614d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000614d`

## pseudocode

```c
void __fastcall FreeSomeCacheBucketEntries(__int64 a1, _QWORD **a2)
{
  KSPIN_LOCK *v4; // rcx
  unsigned int v5; // ebp
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  _QWORD *v8; // rsi
  int v9; // ecx
  int v10; // ecx
  int v11; // ecx
  _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF

  v4 = (KSPIN_LOCK *)(*(_QWORD *)(a1 + 24) + 8LL);
  v5 = 0;
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLockAtDpcLevel(v4, &LockHandle);
  while ( 1 )
  {
    v6 = *a2;
    if ( *a2 == a2 || v5 >= 0x32 )
      break;
    if ( (_QWORD **)v6[1] != a2 || (v7 = (_QWORD *)*v6, *(_QWORD **)(*v6 + 8LL) != v6) )
      __fastfail(3u);
    *a2 = v7;
    v8 = v6 - 4;
    v7[1] = a2;
    *(_OWORD *)v6 = 0;
    RtlRemoveEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 8), (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v6 - 4), 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x2000) != 0 )
    {
      WPP_SF_qq(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_98687f0bf5ea3e300b9458f4256a8986_Traceguids, v8, v8[9]);
    }
    _InterlockedDecrement((volatile signed __int32 *)(a1 + 4));
    v9 = *(_DWORD *)(a1 + 32);
    if ( v9 == 4 )
    {
      WfpPoolFree(v8 + 12);
      v8[12] = 0;
    }
    else
    {
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 1;
        if ( v11 )
        {
          if ( v11 == 1 )
          {
            WfpPoolFree(v8 + 11);
            WfpPoolFree(v8 + 19);
            WfpPoolFree(v8 + 21);
          }
        }
        else
        {
          WfpPoolFree(v8 + 11);
          WfpPoolFree(v8 + 14);
          WfpPoolFree(v8 + 16);
        }
      }
      else
      {
        FreeConditions(v8[9], *((unsigned int *)v8 + 16));
        FreeMatchBufListInternal((_QWORD *)v8[10]);
      }
    }
    if ( v8 )
      ExFreePoolWithTag(v8, 0);
    ++v5;
  }
  KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
}

```

## disassembly

```asm
0x140006060  mov     [rsp+arg_10], rbp
0x140006065  mov     [rsp+arg_18], rdi
0x14000606a  push    r12
0x14000606c  push    r14
0x14000606e  push    r15
0x140006070  sub     rsp, 50h
0x140006074  mov     r14, rcx
0x140006077  mov     rdi, rdx
0x14000607a  mov     rcx, [rcx+18h]
0x14000607e  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x140006083  xor     r12d, r12d
0x140006086  xorps   xmm0, xmm0
0x140006089  xor     eax, eax
0x14000608b  add     rcx, 8; SpinLock
0x14000608f  mov     ebp, r12d
0x140006092  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x140006097  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x14000609c  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x1400060a3  nop     dword ptr [rax+rax+00h]
0x1400060a8  mov     [rsp+68h+arg_0], rbx
0x1400060ad  lea     r15, WPP_GLOBAL_Control
0x1400060b4  mov     [rsp+68h+arg_8], rsi
0x1400060b9  nop     dword ptr [rax+00000000h]
0x1400060c0  mov     rax, [rdi]
0x1400060c3  cmp     rax, rdi
0x1400060c6  jz      loc_1400061CC
0x1400060cc  cmp     ebp, 32h ; '2'
0x1400060cf  jnb     loc_1400061CC
0x1400060d5  cmp     [rax+8], rdi
0x1400060d9  jz      short loc_1400060E2
0x1400060db  mov     ecx, 3
0x1400060e0  int     29h; Win8: RtlFailFast(ecx)
0x1400060e2  mov     rcx, [rax]
0x1400060e5  cmp     [rcx+8], rax
0x1400060e9  jnz     short loc_1400060DB
0x1400060eb  mov     [rdi], rcx
0x1400060ee  lea     rsi, [rax-20h]
0x1400060f2  mov     [rcx+8], rdi
0x1400060f6  xorps   xmm0, xmm0
0x1400060f9  movups  xmmword ptr [rax], xmm0
0x1400060fc  mov     rcx, [r14+8]; HashTable
0x140006100  xor     r8d, r8d; Context
0x140006103  mov     rdx, rsi; Entry
0x140006106  call    cs:__imp_RtlRemoveEntryHashTable
0x14000610d  nop     dword ptr [rax+rax+00h]
0x140006112  mov     rcx, cs:WPP_GLOBAL_Control
0x140006119  cmp     rcx, r15
0x14000611c  jz      short loc_140006128
0x14000611e  cmp     byte ptr [rcx+29h], 5
0x140006122  jnb     loc_1400061FF
0x140006128  lock dec dword ptr [r14+4]
0x14000612d  mov     ecx, [r14+20h]
0x140006131  cmp     ecx, 4
0x140006134  jnz     short loc_140006160
0x140006136  lea     rcx, [rsi+60h]
0x14000613a  call    WfpPoolFree
0x14000613f  mov     [rsi+60h], r12
0x140006143  test    rsi, rsi
0x140006146  jz      short loc_140006159
0x140006148  xor     edx, edx; Tag
0x14000614a  mov     rcx, rsi; P
0x14000614d  call    cs:__imp_ExFreePoolWithTag
0x140006154  nop     dword ptr [rax+rax+00h]
0x140006159  inc     ebp
0x14000615b  jmp     loc_1400060C0
0x140006160  sub     ecx, 1
0x140006163  jz      short loc_140006192
0x140006165  sub     ecx, 1
0x140006168  jz      short loc_1400061A9
0x14000616a  cmp     ecx, 1
0x14000616d  jnz     short loc_140006143
0x14000616f  lea     rcx, [rsi+58h]
0x140006173  call    WfpPoolFree
0x140006178  lea     rcx, [rsi+98h]
0x14000617f  call    WfpPoolFree
0x140006184  lea     rcx, [rsi+0A8h]
0x14000618b  call    WfpPoolFree
0x140006190  jmp     short loc_140006143
0x140006192  mov     edx, [rsi+40h]
0x140006195  mov     rcx, [rsi+48h]
0x140006199  call    FreeConditions
0x14000619e  mov     rcx, [rsi+50h]; Entry
0x1400061a2  call    FreeMatchBufListInternal
0x1400061a7  jmp     short loc_140006143
0x1400061a9  lea     rcx, [rsi+58h]
0x1400061ad  call    WfpPoolFree
0x1400061b2  lea     rcx, [rsi+70h]
0x1400061b6  call    WfpPoolFree
0x1400061bb  lea     rcx, [rsi+80h]
0x1400061c2  call    WfpPoolFree
0x1400061c7  jmp     loc_140006143
0x1400061cc  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x1400061d1  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x1400061d8  nop     dword ptr [rax+rax+00h]
0x1400061dd  mov     rsi, [rsp+68h+arg_8]
0x1400061e2  lea     r11, [rsp+68h+var_18]
0x1400061e7  mov     rbp, [r11+30h]
0x1400061eb  mov     rdi, [r11+38h]
0x1400061ef  mov     rbx, [rsp+68h+arg_0]
0x1400061f4  mov     rsp, r11
0x1400061f7  pop     r15
0x1400061f9  pop     r14
0x1400061fb  pop     r12
0x1400061fd  retn
0x1400061ff  test    dword ptr [rcx+2Ch], 2000h
0x140006206  jz      loc_140006128
0x14000620c  mov     rax, [rsi+48h]
0x140006210  lea     r8, WPP_98687f0bf5ea3e300b9458f4256a8986_Traceguids
0x140006217  mov     rcx, [rcx+18h]
0x14000621b  mov     edx, 0Bh
0x140006220  mov     r9, rsi
0x140006223  mov     [rsp+68h+var_48], rax
0x140006228  call    WPP_SF_qq
0x14000622d  jmp     loc_140006128
```
