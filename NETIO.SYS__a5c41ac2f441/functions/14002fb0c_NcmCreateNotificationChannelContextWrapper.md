# NcmCreateNotificationChannelContextWrapper

- ea: `0x14002fb0c`
- end: `0x14002fca2`
- name: `NcmCreateNotificationChannelContextWrapper`
- size: `406`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14002fa70`

## callees

- `0x14002ebb4`
- `0x14002fb0c`
- `0x14002fca8`
- `0x140031300`

## import_xrefs

- `ntoskrnl!wcsnlen` at `0x14002fbf1`
- `ntoskrnl!wcsnlen` at `0x14002fbf1`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002fb5b`
- `ntoskrnl!PsGetCurrentProcessId` at `0x14002fb5b`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002fc75`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14002fc75`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002fbaf`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14002fbaf`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002fb45`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14002fb45`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fb79`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14002fb79`

## pseudocode

```c
__int64 __fastcall NcmCreateNotificationChannelContextWrapper(unsigned int *a1, __int64 a2)
{
  unsigned int NotificationChannelContext; // ebx
  unsigned int v6; // ebp
  ULONG_PTR v7; // rdx
  struct _RTL_DYNAMIC_HASH_TABLE_ENTRY *v8; // rbx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY v10; // rdi
  size_t v11; // rax
  __int64 v12; // r9
  ULONG_PTR *j; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-58h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-40h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  memset(&Context, 0, sizeof(Context));
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  while ( dword_14009B060 )
    ;
  if ( (unsigned int)PsGetCurrentProcessId() == dword_14009B004 )
  {
    v6 = *a1;
    v7 = *a1;
    v8 = 0;
    *(_OWORD *)&Context.ChainHead = 0;
    for ( i = RtlLookupEntryHashTable(&stru_14009B030, v7, &Context);
          ;
          i = RtlGetNextEntryHashTable(&stru_14009B030, &Context) )
    {
      v10 = i;
      if ( !i )
        break;
      if ( LODWORD(i[1].Linkage.Flink) == *a1 )
      {
        if ( HIDWORD(i[1].Linkage.Blink[1].Blink) != *(_DWORD *)(a2 + 128)
          || (v11 = wcsnlen((const wchar_t *)(a2 + 132), 0x104u),
              wmemcmp((const wchar_t *)&v10[1].Linkage.Blink[2], (const wchar_t *)(a2 + 132), v11))
          || *(_DWORD *)(v12 + 552) != *(_DWORD *)(a2 + 664)
          || *(_DWORD *)(v12 + 556) != *(_DWORD *)(a2 + 668) )
        {
          NotificationChannelContext = -1073741811;
          goto LABEL_5;
        }
        v8 = v10;
        for ( j = (ULONG_PTR *)v10[1].Signature; j != &v10[1].Signature; j = (ULONG_PTR *)*j )
        {
          if ( j[5] == *((_QWORD *)a1 + 1) )
          {
            NcmModifyNotificationChannelContext(j, a2, &LockHandle);
            NotificationChannelContext = 0;
            goto LABEL_5;
          }
        }
        break;
      }
    }
    NotificationChannelContext = NcmCreateNotificationChannelContext(v8, v6, (__int64)a1, a2);
  }
  else
  {
    NotificationChannelContext = -1073741790;
  }
LABEL_5:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  return NotificationChannelContext;
}

```

## disassembly

```asm
0x14002fb0c  push    rbx
0x14002fb0e  push    rbp
0x14002fb0f  push    rsi
0x14002fb10  push    rdi
0x14002fb11  push    r14
0x14002fb13  sub     rsp, 50h
0x14002fb17  xor     eax, eax
0x14002fb19  mov     rsi, rdx
0x14002fb1c  mov     r14, rcx
0x14002fb1f  mov     qword ptr [rsp+78h+LockHandle.OldIrql], rax
0x14002fb24  xorps   xmm0, xmm0
0x14002fb27  mov     [rsp+78h+Context.Signature], rax
0x14002fb2c  xorps   xmm1, xmm1
0x14002fb2f  lea     rdx, [rsp+78h+LockHandle]; LockHandle
0x14002fb34  lea     rcx, SpinLock; SpinLock
0x14002fb3b  movups  xmmword ptr [rsp+78h+LockHandle.LockQueue.Next], xmm0
0x14002fb40  movups  xmmword ptr [rsp+78h+Context.ChainHead], xmm1
0x14002fb45  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14002fb4c  nop     dword ptr [rax+rax+00h]
0x14002fb51  mov     eax, cs:dword_14009B060
0x14002fb57  test    eax, eax
0x14002fb59  jnz     short loc_14002FB51
0x14002fb5b  call    cs:__imp_PsGetCurrentProcessId
0x14002fb62  nop     dword ptr [rax+rax+00h]
0x14002fb67  cmp     eax, cs:dword_14009B004
0x14002fb6d  jz      short loc_14002FB93
0x14002fb6f  mov     ebx, 0C0000022h
0x14002fb74  lea     rcx, [rsp+78h+LockHandle]; LockHandle
0x14002fb79  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14002fb80  nop     dword ptr [rax+rax+00h]
0x14002fb85  mov     eax, ebx
0x14002fb87  add     rsp, 50h
0x14002fb8b  pop     r14
0x14002fb8d  pop     rdi
0x14002fb8e  pop     rsi
0x14002fb8f  pop     rbp
0x14002fb90  pop     rbx
0x14002fb91  retn
0x14002fb93  mov     ebp, [r14]
0x14002fb96  lea     r8, [rsp+78h+Context]; Context
0x14002fb9b  xorps   xmm0, xmm0
0x14002fb9e  lea     rcx, stru_14009B030; HashTable
0x14002fba5  mov     edx, ebp; Signature
0x14002fba7  xor     ebx, ebx
0x14002fba9  movdqu  xmmword ptr [rsp+78h+Context.ChainHead], xmm0
0x14002fbaf  call    cs:__imp_RtlLookupEntryHashTable
0x14002fbb6  nop     dword ptr [rax+rax+00h]
0x14002fbbb  mov     rdi, rax
0x14002fbbe  test    rax, rax
0x14002fbc1  jz      loc_14002FC8B
0x14002fbc7  mov     ecx, [r14]
0x14002fbca  cmp     [rax+18h], ecx
0x14002fbcd  jnz     loc_14002FC69
0x14002fbd3  mov     rcx, [rax+20h]
0x14002fbd7  mov     eax, [rsi+80h]
0x14002fbdd  cmp     [rcx+1Ch], eax
0x14002fbe0  jnz     short loc_14002FC14
0x14002fbe2  lea     rbx, [rsi+84h]
0x14002fbe9  mov     edx, 104h; MaxCount
0x14002fbee  mov     rcx, rbx; Src
0x14002fbf1  call    cs:__imp_wcsnlen
0x14002fbf8  nop     dword ptr [rax+rax+00h]
0x14002fbfd  mov     r9, [rdi+20h]
0x14002fc01  mov     rdx, rbx; S2
0x14002fc04  mov     r8, rax; N
0x14002fc07  lea     rcx, [r9+20h]; S1
0x14002fc0b  call    wmemcmp
0x14002fc10  test    eax, eax
0x14002fc12  jz      short loc_14002FC1E
0x14002fc14  mov     ebx, 0C000000Dh
0x14002fc19  jmp     loc_14002FB74
0x14002fc1e  mov     eax, [rsi+298h]
0x14002fc24  cmp     [r9+228h], eax
0x14002fc2b  jnz     short loc_14002FC14
0x14002fc2d  mov     eax, [rsi+29Ch]
0x14002fc33  cmp     [r9+22Ch], eax
0x14002fc3a  jnz     short loc_14002FC14
0x14002fc3c  lea     rdx, [rdi+28h]
0x14002fc40  mov     rbx, rdi
0x14002fc43  mov     rcx, [rdx]
0x14002fc46  cmp     rcx, rdx
0x14002fc49  jz      short loc_14002FC8B
0x14002fc4b  mov     rax, [r14+8]
0x14002fc4f  cmp     [rcx+28h], rax
0x14002fc53  jnz     short loc_14002FC86
0x14002fc55  lea     r8, [rsp+78h+LockHandle]
0x14002fc5a  mov     rdx, rsi
0x14002fc5d  call    NcmModifyNotificationChannelContext
0x14002fc62  xor     ebx, ebx
0x14002fc64  jmp     loc_14002FB74
0x14002fc69  lea     rdx, [rsp+78h+Context]; Context
0x14002fc6e  lea     rcx, stru_14009B030; HashTable
0x14002fc75  call    cs:__imp_RtlGetNextEntryHashTable
0x14002fc7c  nop     dword ptr [rax+rax+00h]
0x14002fc81  jmp     loc_14002FBBB
0x14002fc86  mov     rcx, [rcx]
0x14002fc89  jmp     short loc_14002FC46
0x14002fc8b  mov     r9, rsi
0x14002fc8e  mov     r8, r14
0x14002fc91  mov     edx, ebp
0x14002fc93  mov     rcx, rbx; P
0x14002fc96  call    NcmCreateNotificationChannelContext
0x14002fc9b  mov     ebx, eax
0x14002fc9d  jmp     loc_14002FB74
```
