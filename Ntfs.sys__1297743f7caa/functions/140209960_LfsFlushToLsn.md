# LfsFlushToLsn

- ea: `0x140209960`
- end: `0x14020a00c`
- name: `LfsFlushToLsn`
- size: `1708`
- prototype: ``
- caller_count: `15`
- callee_count: `5`
- tags: ``

## callers

- `0x14004514c`
- `0x1400cc78c`
- `0x1400cf580`
- `0x140138b68`
- `0x1401d5b20`
- `0x1401d6108`
- `0x1401da26c`
- `0x140208f8c`
- `0x1402096fc`
- `0x14020a014`
- `0x14020a774`
- `0x14021ec20`
- `0x1402308d8`
- `0x14026dccc`
- `0x14027e418`

## callees

- `0x1400240c0`
- `0x140027f08`
- `0x14002f140`
- `0x14002f7e8`
- `0x140209960`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140209d8a`
- `ntoskrnl!KeSetEvent` at `0x140209f00`
- `ntoskrnl!KeSetEvent` at `0x140209d8a`
- `ntoskrnl!KeSetEvent` at `0x140209f00`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b5c`
- `ntoskrnl!KeSetPriorityThread` at `0x140209bd0`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e12`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e7d`
- `ntoskrnl!KeSetPriorityThread` at `0x140209b5c`
- `ntoskrnl!KeSetPriorityThread` at `0x140209bd0`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e12`
- `ntoskrnl!KeSetPriorityThread` at `0x140209e7d`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209b6f`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209e22`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209b6f`
- `ntoskrnl!PsEnterPriorityRegion` at `0x140209e22`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209bae`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209e5b`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209bae`
- `ntoskrnl!PsLeavePriorityRegion` at `0x140209e5b`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209bf0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209fc3`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209bf0`
- `ntoskrnl!ExIsResourceAcquiredSharedLite` at `0x140209fc3`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209c2c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209eb1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209c2c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140209eb1`
- `ntoskrnl!KeInitializeEvent` at `0x140209a87`
- `ntoskrnl!KeInitializeEvent` at `0x140209cde`
- `ntoskrnl!KeInitializeEvent` at `0x140209a87`
- `ntoskrnl!KeInitializeEvent` at `0x140209cde`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209ae0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209b86`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209d38`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209e39`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209ae0`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209b86`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209d38`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140209e39`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209ac0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209d14`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209ac0`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140209d14`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402099c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209c4f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209ecb`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1402099c5`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209c4f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140209ecb`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209c07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209fd7`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209c07`
- `ntoskrnl!ExReleaseResourceLite` at `0x140209fd7`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209aa2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209cf9`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209aa2`
- `ntoskrnl!ExIsResourceAcquiredExclusiveLite` at `0x140209cf9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209dc9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209f0e`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209dc9`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140209f0e`
- `ntoskrnl!ExRaiseStatus` at `0x140209fb2`
- `ntoskrnl!ExRaiseStatus` at `0x140209fff`
- `ntoskrnl!ExRaiseStatus` at `0x140209fb2`
- `ntoskrnl!ExRaiseStatus` at `0x140209fff`

## pseudocode

```c
__int64 __fastcall LfsFlushToLsn(__int64 a1, __int64 a2)
{
  unsigned int v4; // r15d
  bool v5; // r12
  __int64 v6; // r14
  KPRIORITY v7; // r13d
  __int64 *v8; // rax
  __int64 v9; // rdi
  __int64 v10; // rax
  __int64 v11; // rdi
  struct _ERESOURCE *v12; // rcx
  __int64 *v13; // rax
  BOOLEAN v14; // r12
  __int64 v15; // rax
  int v16; // eax
  struct _KEVENT *v17; // rcx
  _QWORD *i; // rax
  _QWORD *v19; // rcx
  char v20; // r13
  struct _ERESOURCE *v21; // rcx
  struct _KEVENT *v22; // rcx
  _QWORD *j; // rax
  _QWORD *v24; // rcx
  KPRIORITY Priority; // [rsp+30h] [rbp-D8h]
  __int128 v27; // [rsp+58h] [rbp-B0h] BYREF
  _BYTE Object[32]; // [rsp+68h] [rbp-A0h] BYREF
  __int64 v29; // [rsp+88h] [rbp-80h]
  __int128 v30; // [rsp+90h] [rbp-78h] BYREF
  _BYTE Event[32]; // [rsp+A0h] [rbp-68h] BYREF
  __int64 v32; // [rsp+C0h] [rbp-48h]
  char v33; // [rsp+110h] [rbp+8h]
  BOOLEAN IsResourceAcquiredExclusiveLite; // [rsp+120h] [rbp+18h]

  if ( !a1 || (v4 = 0, *(_WORD *)a1 != 2049) )
    ExRaiseStatus(-1073741790);
  v5 = qword_140094AF8 == 0;
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 56), 1u);
  v6 = *(_QWORD *)(a1 + 24);
  if ( v6 )
  {
    if ( (*(_DWORD *)(v6 + 428) & 0x400) == 0 )
    {
      if ( *(_WORD *)(a1 + 34) >= *(_WORD *)(*(_QWORD *)(v6 + 200) + 8LL)
        || *(_WORD *)(a1 + 32) != *(_WORD *)(*(unsigned int *)(a1 + 48) + *(_QWORD *)(v6 + 208) + 20LL) )
      {
        ExRaiseStatus(-1073741790);
      }
      v30 = 0;
      memset(Event, 0, sizeof(Event));
      v32 = 0;
      v7 = 0;
      v8 = *(__int64 **)(v6 + 200);
      v9 = a2;
      if ( a2 > *v8 )
        v9 = *v8;
      KeInitializeEvent((PRKEVENT)Event, SynchronizationEvent, 0);
      *(_QWORD *)&Event[24] = v9;
      IsResourceAcquiredExclusiveLite = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v6 + 456));
      while ( 1 )
      {
        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
        v10 = *(_QWORD *)(v6 + 456);
        if ( v9 <= *(_QWORD *)(v6 + 280) )
        {
          ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v10 + 120));
          goto LABEL_12;
        }
        if ( *(_DWORD *)(v10 + 176) )
        {
          for ( i = *(_QWORD **)(v6 + 472); i != (_QWORD *)(v6 + 472) && i[5] <= v9; i = (_QWORD *)*i )
            ;
          v19 = (_QWORD *)i[1];
          if ( (_QWORD *)*v19 != i )
LABEL_42:
            __fastfail(3u);
          v33 = 0;
          *(_QWORD *)&v30 = i;
          *((_QWORD *)&v30 + 1) = v19;
          *v19 = &v30;
          i[1] = &v30;
        }
        else
        {
          *(_DWORD *)(v10 + 176) = 1;
          *(_QWORD *)(v6 + 504) = KeGetCurrentThread();
          v33 = 1;
          v7 = KeSetPriorityThread(KeGetCurrentThread(), 16);
          PsEnterPriorityRegion();
        }
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
        if ( v33 )
          break;
        _InterlockedIncrement((volatile signed __int32 *)(v6 + 464));
        if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(v6 + 456)) )
          ExReleaseResourceLite(*(PERESOURCE *)(v6 + 456));
        KeWaitForSingleObject(Event, Executive, 0, 0, 0);
        v12 = *(struct _ERESOURCE **)(v6 + 456);
        if ( IsResourceAcquiredExclusiveLite )
          ExAcquireResourceExclusiveLite(v12, 1u);
        else
          ExAcquireResourceSharedLite(v12, 1u);
        if ( !_InterlockedDecrement((volatile signed __int32 *)(v6 + 464)) )
        {
          v17 = *(struct _KEVENT **)(v6 + 608);
          if ( v17 )
            KeSetEvent(v17, 0, 0);
        }
      }
      LfsFlushLfcbOnNewStack(v6, v9, 0, v5);
      PsLeavePriorityRegion();
      if ( v7 != 16 )
        KeSetPriorityThread(KeGetCurrentThread(), v7);
LABEL_12:
      v11 = 0x7FFFFFFFFFFFFFFFLL;
      if ( a2 == 0x7FFFFFFFFFFFFFFFLL )
        a2 = *(_QWORD *)(v6 + 280);
      if ( a2 > *(_QWORD *)(v6 + 296) )
      {
        if ( v5 )
        {
          *(_QWORD *)(v6 + 296) = *(_QWORD *)(v6 + 280);
        }
        else
        {
          v27 = 0;
          memset(Object, 0, sizeof(Object));
          v29 = 0;
          Priority = 0;
          v13 = *(__int64 **)(v6 + 200);
          if ( *v13 != 0x7FFFFFFFFFFFFFFFLL )
            v11 = *v13;
          KeInitializeEvent((PRKEVENT)Object, SynchronizationEvent, 0);
          *(_QWORD *)&Object[24] = v11;
          v14 = ExIsResourceAcquiredExclusiveLite(*(PERESOURCE *)(v6 + 456));
          while ( 1 )
          {
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
            v15 = *(_QWORD *)(v6 + 456);
            if ( v11 <= *(_QWORD *)(v6 + 280) )
            {
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v15 + 120));
              goto LABEL_34;
            }
            if ( *(_DWORD *)(v15 + 176) )
            {
              for ( j = *(_QWORD **)(v6 + 472); j != (_QWORD *)(v6 + 472) && j[5] <= v11; j = (_QWORD *)*j )
                ;
              v24 = (_QWORD *)j[1];
              if ( (_QWORD *)*v24 != j )
                goto LABEL_42;
              v20 = 0;
              *(_QWORD *)&v27 = j;
              *((_QWORD *)&v27 + 1) = v24;
              *v24 = &v27;
              j[1] = &v27;
            }
            else
            {
              *(_DWORD *)(v15 + 176) = 1;
              *(_QWORD *)(v6 + 504) = KeGetCurrentThread();
              v20 = 1;
              Priority = KeSetPriorityThread(KeGetCurrentThread(), 16);
              PsEnterPriorityRegion();
            }
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)(v6 + 456) + 120LL));
            if ( v20 )
              break;
            _InterlockedIncrement((volatile signed __int32 *)(v6 + 464));
            LfsReleaseLfcb(v6);
            KeWaitForSingleObject(Object, Executive, 0, 0, 0);
            v21 = *(struct _ERESOURCE **)(v6 + 456);
            if ( v14 )
              ExAcquireResourceExclusiveLite(v21, 1u);
            else
              ExAcquireResourceSharedLite(v21, 1u);
            if ( !_InterlockedDecrement((volatile signed __int32 *)(v6 + 464)) )
            {
              v22 = *(struct _KEVENT **)(v6 + 608);
              if ( v22 )
                KeSetEvent(v22, 0, 0);
            }
          }
          LfsFlushLfcbOnNewStack(v6, v11, 0, 0);
          PsLeavePriorityRegion();
          if ( Priority != 16 )
            KeSetPriorityThread(KeGetCurrentThread(), Priority);
LABEL_34:
          v16 = LfsFlushDiskCache(a1, a2);
          v6 = *(_QWORD *)(a1 + 24);
          if ( v16 < 0 )
          {
            if ( !v6 )
              goto LABEL_67;
            ++*(_DWORD *)(v6 + 364);
          }
        }
      }
    }
    if ( v6 )
      v4 = *(_DWORD *)(v6 + 560);
  }
LABEL_67:
  if ( ExIsResourceAcquiredSharedLite(*(PERESOURCE *)(a1 + 56)) )
    ExReleaseResourceLite(*(PERESOURCE *)(a1 + 56));
  return v4;
}

```

## disassembly

```asm
0x140209960  mov     rax, rsp
0x140209963  push    rbx
0x140209964  push    rsi
0x140209965  push    rdi
0x140209966  push    r12
0x140209968  push    r13
0x14020996a  push    r14
0x14020996c  push    r15
0x14020996e  sub     rsp, 0D0h
0x140209975  mov     rbx, rdx
0x140209978  mov     rsi, rcx
0x14020997b  mov     dword ptr [rax+20h], 0FFFFFFFFh
0x140209982  mov     dword ptr [rax+24h], 7FFFFFFFh
0x140209989  test    rcx, rcx
0x14020998c  jz      loc_140209FFA
0x140209992  xor     r15d, r15d
0x140209995  xor     cl, cl
0x140209997  mov     [rsp+108h+var_B8], rsi
0x14020999c  mov     eax, 801h
0x1402099a1  cmp     [rsi], ax
0x1402099a4  jnz     loc_140209FFA
0x1402099aa  movzx   r12d, cl
0x1402099ae  mov     eax, 1
0x1402099b3  cmp     cs:qword_140094AF8, r15
0x1402099ba  cmovz   r12d, eax
0x1402099be  movzx   edx, al; Wait
0x1402099c1  mov     rcx, [rsi+38h]; Resource
0x1402099c5  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1402099cc  nop     dword ptr [rax+rax+00h]
0x1402099d1  mov     r14, [rsi+18h]
0x1402099d5  mov     [rsp+108h+var_C0], r14
0x1402099da  test    r14, r14
0x1402099dd  jz      loc_140209FBF
0x1402099e3  mov     eax, [r14+1ACh]
0x1402099ea  bt      eax, 0Ah
0x1402099ee  jb      loc_140209B0A
0x1402099f4  mov     rax, [r14+0C8h]
0x1402099fb  movzx   ecx, word ptr [rax+8]
0x1402099ff  cmp     [rsi+22h], cx
0x140209a03  jnb     loc_140209FAD
0x140209a09  mov     ecx, [rsi+30h]
0x140209a0c  mov     rax, [r14+0D0h]
0x140209a13  movzx   ecx, word ptr [rcx+rax+14h]
0x140209a18  cmp     [rsi+20h], cx
0x140209a1c  jnz     loc_140209FAD
0x140209a22  mov     [rsp+108h+var_D0], rbx
0x140209a27  xorps   xmm0, xmm0
0x140209a2a  xor     eax, eax
0x140209a2c  movups  [rsp+108h+var_78], xmm0
0x140209a34  movups  xmmword ptr [rsp+108h+Event], xmm0
0x140209a3c  movups  xmmword ptr [rsp+108h+Event+10h], xmm0
0x140209a44  mov     [rsp+108h+var_48], rax
0x140209a4c  xor     r13d, r13d
0x140209a4f  mov     [rsp+108h+var_D4], r13d
0x140209a54  mov     rax, ds:0FFFFF78000000320h
0x140209a5e  mov     rax, [r14+0C8h]
0x140209a65  mov     rcx, [rax]
0x140209a68  mov     rdi, rbx
0x140209a6b  cmp     rbx, rcx
0x140209a6e  cmovg   rdi, rcx
0x140209a72  mov     [rsp+108h+var_D0], rdi
0x140209a77  xor     r8d, r8d; State
0x140209a7a  mov     edx, 1; Type
0x140209a7f  lea     rcx, [rsp+108h+Event]; Event
0x140209a87  call    cs:__imp_KeInitializeEvent
0x140209a8e  nop     dword ptr [rax+rax+00h]
0x140209a93  mov     qword ptr [rsp+108h+Event+18h], rdi
0x140209a9b  mov     rcx, [r14+1C8h]; Resource
0x140209aa2  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140209aa9  nop     dword ptr [rax+rax+00h]
0x140209aae  mov     [rsp+108h+arg_10], al
0x140209ab5  mov     rcx, [r14+1C8h]
0x140209abc  add     rcx, 78h ; 'x'; FastMutex
0x140209ac0  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140209ac7  nop     dword ptr [rax+rax+00h]
0x140209acc  mov     rax, [r14+1C8h]
0x140209ad3  cmp     rdi, [r14+118h]
0x140209ada  jg      short loc_140209B1F
0x140209adc  lea     rcx, [rax+78h]; FastMutex
0x140209ae0  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209ae7  nop     dword ptr [rax+rax+00h]
0x140209aec  mov     rdi, [rsp+108h+arg_18]
0x140209af4  cmp     rbx, rdi
0x140209af7  jz      loc_140209C77
0x140209afd  cmp     rbx, [r14+128h]
0x140209b04  jg      loc_140209C83
0x140209b0a  test    r14, r14
0x140209b0d  jz      loc_140209FBF
0x140209b13  mov     r15d, [r14+230h]
0x140209b1a  jmp     loc_140209FBF
0x140209b1f  cmp     dword ptr [rax+0B0h], 0
0x140209b26  jnz     loc_140209D9B
0x140209b2c  mov     dword ptr [rax+0B0h], 1
0x140209b36  mov     rax, gs:188h
0x140209b3f  mov     [r14+1F8h], rax
0x140209b46  mov     [rsp+108h+arg_0], 1
0x140209b4e  mov     rcx, gs:188h; Thread
0x140209b57  mov     edx, 10h; Priority
0x140209b5c  call    cs:__imp_KeSetPriorityThread
0x140209b63  nop     dword ptr [rax+rax+00h]
0x140209b68  mov     r13d, eax
0x140209b6b  mov     [rsp+108h+var_D4], eax
0x140209b6f  call    cs:__imp_PsEnterPriorityRegion
0x140209b76  nop     dword ptr [rax+rax+00h]
0x140209b7b  mov     rcx, [r14+1C8h]
0x140209b82  add     rcx, 78h ; 'x'; FastMutex
0x140209b86  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209b8d  nop     dword ptr [rax+rax+00h]
0x140209b92  cmp     [rsp+108h+arg_0], 0
0x140209b9a  jz      short loc_140209BE1
0x140209b9c  movzx   r9d, r12b
0x140209ba0  xor     r8d, r8d
0x140209ba3  mov     rdx, rdi
0x140209ba6  mov     rcx, r14
0x140209ba9  call    LfsFlushLfcbOnNewStack
0x140209bae  call    cs:__imp_PsLeavePriorityRegion
0x140209bb5  nop     dword ptr [rax+rax+00h]
0x140209bba  cmp     r13d, 10h
0x140209bbe  jz      loc_140209AEC
0x140209bc4  mov     rcx, gs:188h; Thread
0x140209bcd  mov     edx, r13d; Priority
0x140209bd0  call    cs:__imp_KeSetPriorityThread
0x140209bd7  nop     dword ptr [rax+rax+00h]
0x140209bdc  jmp     loc_140209AEC
0x140209be1  lock inc dword ptr [r14+1D0h]
0x140209be9  mov     rcx, [r14+1C8h]; Resource
0x140209bf0  call    cs:__imp_ExIsResourceAcquiredSharedLite
0x140209bf7  nop     dword ptr [rax+rax+00h]
0x140209bfc  test    eax, eax
0x140209bfe  jz      short loc_140209C13
0x140209c00  mov     rcx, [r14+1C8h]; Resource
0x140209c07  call    cs:__imp_ExReleaseResourceLite
0x140209c0e  nop     dword ptr [rax+rax+00h]
0x140209c13  mov     [rsp+108h+Timeout], 0; Timeout
0x140209c1c  xor     r9d, r9d; Alertable
0x140209c1f  xor     r8d, r8d; WaitMode
0x140209c22  xor     edx, edx; WaitReason
0x140209c24  lea     rcx, [rsp+108h+Event]; Object
0x140209c2c  call    cs:__imp_KeWaitForSingleObject
0x140209c33  nop     dword ptr [rax+rax+00h]
0x140209c38  mov     rcx, [r14+1C8h]; Resource
0x140209c3f  mov     dl, 1; Wait
0x140209c41  cmp     [rsp+108h+arg_10], 0
0x140209c49  jz      loc_140209DC9
0x140209c4f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140209c56  nop     dword ptr [rax+rax+00h]
0x140209c5b  mov     eax, 0FFFFFFFFh
0x140209c60  lock xadd [r14+1D0h], eax
0x140209c69  sub     eax, 1
0x140209c6c  jz      loc_140209D75
0x140209c72  jmp     loc_140209AB5
0x140209c77  mov     rbx, [r14+118h]
0x140209c7e  jmp     loc_140209AFD
0x140209c83  test    r12b, r12b
0x140209c86  jnz     loc_140209F9A
0x140209c8c  mov     [rsp+108h+var_C8], rdi
0x140209c91  xorps   xmm0, xmm0
0x140209c94  xor     eax, eax
0x140209c96  movups  [rsp+108h+var_B0], xmm0
0x140209c9b  movups  xmmword ptr [rsp+108h+Object], xmm0
0x140209ca0  movups  xmmword ptr [rsp+108h+Object+10h], xmm0
0x140209ca5  mov     [rsp+108h+var_80], rax
0x140209cad  mov     [rsp+108h+Priority], eax
0x140209cb1  mov     rax, ds:0FFFFF78000000320h
0x140209cbb  mov     rax, [r14+0C8h]
0x140209cc2  mov     rcx, [rax]
0x140209cc5  cmp     rdi, rcx
0x140209cc8  cmovg   rdi, rcx
0x140209ccc  mov     [rsp+108h+var_C8], rdi
0x140209cd1  xor     r8d, r8d; State
0x140209cd4  mov     edx, 1; Type
0x140209cd9  lea     rcx, [rsp+108h+Object]; Event
0x140209cde  call    cs:__imp_KeInitializeEvent
0x140209ce5  nop     dword ptr [rax+rax+00h]
0x140209cea  mov     qword ptr [rsp+108h+Object+18h], rdi
0x140209cf2  mov     rcx, [r14+1C8h]; Resource
0x140209cf9  call    cs:__imp_ExIsResourceAcquiredExclusiveLite
0x140209d00  nop     dword ptr [rax+rax+00h]
0x140209d05  movzx   r12d, al
0x140209d09  mov     rcx, [r14+1C8h]
0x140209d10  add     rcx, 78h ; 'x'; FastMutex
0x140209d14  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140209d1b  nop     dword ptr [rax+rax+00h]
0x140209d20  mov     rax, [r14+1C8h]
0x140209d27  cmp     rdi, [r14+118h]
0x140209d2e  jg      loc_140209DDA
0x140209d34  lea     rcx, [rax+78h]; FastMutex
0x140209d38  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209d3f  nop     dword ptr [rax+rax+00h]
0x140209d44  mov     rdx, rbx
0x140209d47  mov     rcx, rsi
0x140209d4a  call    LfsFlushDiskCache
0x140209d4f  mov     r14, [rsi+18h]
0x140209d53  mov     [rsp+108h+var_C0], r14
0x140209d58  test    eax, eax
0x140209d5a  jns     loc_140209B0A
0x140209d60  test    r14, r14
0x140209d63  jz      loc_140209FBF
0x140209d69  inc     dword ptr [r14+16Ch]
0x140209d70  jmp     loc_140209B0A
0x140209d75  mov     rcx, [r14+260h]; Event
0x140209d7c  test    rcx, rcx
0x140209d7f  jz      loc_140209C72
0x140209d85  xor     r8d, r8d; Wait
0x140209d88  xor     edx, edx; Increment
0x140209d8a  call    cs:__imp_KeSetEvent
0x140209d91  nop     dword ptr [rax+rax+00h]
0x140209d96  jmp     loc_140209C72
0x140209d9b  lea     rcx, [r14+1D8h]
0x140209da2  mov     rax, [rcx]
0x140209da5  cmp     rax, rcx
0x140209da8  jnz     short loc_140209DBE
0x140209daa  mov     rcx, [rax+8]
0x140209dae  cmp     [rcx], rax
0x140209db1  jz      loc_140209F66
0x140209db7  mov     ecx, 3
0x140209dbc  int     29h; Win8: RtlFailFast(ecx)
0x140209dbe  cmp     [rax+28h], rdi
0x140209dc2  jg      short loc_140209DAA
0x140209dc4  mov     rax, [rax]
0x140209dc7  jmp     short loc_140209DA5
0x140209dc9  call    cs:__imp_ExAcquireResourceSharedLite
0x140209dd0  nop     dword ptr [rax+rax+00h]
0x140209dd5  jmp     loc_140209C5B
0x140209dda  cmp     dword ptr [rax+0B0h], 0
0x140209de1  jnz     loc_140209F1C
0x140209de7  mov     dword ptr [rax+0B0h], 1
0x140209df1  mov     rax, gs:188h
0x140209dfa  mov     [r14+1F8h], rax
0x140209e01  mov     r13b, 1
0x140209e04  mov     rcx, gs:188h; Thread
0x140209e0d  mov     edx, 10h; Priority
0x140209e12  call    cs:__imp_KeSetPriorityThread
0x140209e19  nop     dword ptr [rax+rax+00h]
0x140209e1e  mov     [rsp+108h+Priority], eax
0x140209e22  call    cs:__imp_PsEnterPriorityRegion
0x140209e29  nop     dword ptr [rax+rax+00h]
0x140209e2e  mov     rcx, [r14+1C8h]
0x140209e35  add     rcx, 78h ; 'x'; FastMutex
0x140209e39  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140209e40  nop     dword ptr [rax+rax+00h]
0x140209e45  mov     rcx, r14
0x140209e48  test    r13b, r13b
0x140209e4b  jz      short loc_140209E8E
0x140209e4d  xor     r9d, r9d
0x140209e50  xor     r8d, r8d
0x140209e53  mov     rdx, rdi
0x140209e56  call    LfsFlushLfcbOnNewStack
0x140209e5b  call    cs:__imp_PsLeavePriorityRegion
0x140209e62  nop     dword ptr [rax+rax+00h]
0x140209e67  mov     edx, [rsp+108h+Priority]; Priority
0x140209e6b  cmp     edx, 10h
0x140209e6e  jz      loc_140209D44
0x140209e74  mov     rcx, gs:188h; Thread
0x140209e7d  call    cs:__imp_KeSetPriorityThread
0x140209e84  nop     dword ptr [rax+rax+00h]
0x140209e89  jmp     loc_140209D44
0x140209e8e  lock inc dword ptr [r14+1D0h]
0x140209e96  call    LfsReleaseLfcb
0x140209e9b  mov     [rsp+108h+Timeout], 0; Timeout
0x140209ea4  xor     r9d, r9d; Alertable
0x140209ea7  xor     r8d, r8d; WaitMode
0x140209eaa  xor     edx, edx; WaitReason
0x140209eac  lea     rcx, [rsp+108h+Object]; Object
0x140209eb1  call    cs:__imp_KeWaitForSingleObject
0x140209eb8  nop     dword ptr [rax+rax+00h]
0x140209ebd  mov     rcx, [r14+1C8h]; Resource
0x140209ec4  mov     dl, 1; Wait
0x140209ec6  test    r12b, r12b
0x140209ec9  jz      short loc_140209F0E
0x140209ecb  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140209ed2  nop     dword ptr [rax+rax+00h]
0x140209ed7  mov     eax, 0FFFFFFFFh
0x140209edc  lock xadd [r14+1D0h], eax
0x140209ee5  sub     eax, 1
0x140209ee8  jz      short loc_140209EEF
0x140209eea  jmp     loc_140209D09
0x140209eef  mov     rcx, [r14+260h]; Event
0x140209ef6  test    rcx, rcx
0x140209ef9  jz      short loc_140209EEA
0x140209efb  xor     r8d, r8d; Wait
0x140209efe  xor     edx, edx; Increment
0x140209f00  call    cs:__imp_KeSetEvent
0x140209f07  nop     dword ptr [rax+rax+00h]
0x140209f0c  jmp     short loc_140209EEA
0x140209f0e  call    cs:__imp_ExAcquireResourceSharedLite
0x140209f15  nop     dword ptr [rax+rax+00h]
0x140209f1a  jmp     short loc_140209ED7
0x140209f1c  lea     rcx, [r14+1D8h]
0x140209f23  mov     rax, [rcx]
0x140209f26  cmp     rax, rcx
0x140209f29  jnz     short loc_140209F5B
0x140209f2b  mov     rcx, [rax+8]
0x140209f2f  cmp     [rcx], rax
0x140209f32  jnz     loc_140209DB7
0x140209f38  xor     r13b, r13b
0x140209f3b  mov     qword ptr [rsp+108h+var_B0], rax
0x140209f40  mov     qword ptr [rsp+108h+var_B0+8], rcx
0x140209f45  lea     rdx, [rsp+108h+var_B0]
0x140209f4a  mov     [rcx], rdx
  ... truncated ...
```
