# NetioNcmIsOwningProcessRtcApp

- ea: `0x14003b1a0`
- end: `0x14003b2cc`
- name: `NetioNcmIsOwningProcessRtcApp`
- size: `300`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x14003b1a0`

## import_xrefs

- `ntoskrnl!KeLowerIrql` at `0x14003b24b`
- `ntoskrnl!KeLowerIrql` at `0x14003b24b`
- `ntoskrnl!KfRaiseIrql` at `0x14003b1dd`
- `ntoskrnl!KfRaiseIrql` at `0x14003b1dd`
- `ntoskrnl!PsGetProcessId` at `0x14003b1cc`
- `ntoskrnl!PsGetProcessId` at `0x14003b1cc`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14003b2bb`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14003b2bb`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003b230`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14003b230`
- `ntoskrnl!KeTestSpinLock` at `0x14003b209`
- `ntoskrnl!KeTestSpinLock` at `0x14003b209`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003b286`
- `ntoskrnl!KeAcquireInStackQueuedSpinLockAtDpcLevel` at `0x14003b286`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003b29e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLockFromDpcLevel` at `0x14003b29e`

## pseudocode

```c
char __fastcall NetioNcmIsOwningProcessRtcApp(struct _KPROCESS *a1)
{
  char result; // al
  char v2; // bl
  unsigned int ProcessId; // edi
  KIRQL v4; // si
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-20h] BYREF

  result = 0;
  memset(&Context, 0, sizeof(Context));
  if ( byte_14009B06C )
  {
    v2 = 0;
    ProcessId = (unsigned int)PsGetProcessId(a1);
    v4 = KfRaiseIrql(2u);
    memset(&LockHandle, 0, sizeof(LockHandle));
    _InterlockedIncrement(&dword_14009B060);
    if ( !KeTestSpinLock(&SpinLock) )
    {
      _InterlockedDecrement(&dword_14009B060);
      KeAcquireInStackQueuedSpinLockAtDpcLevel(&SpinLock, &LockHandle);
      _InterlockedIncrement(&dword_14009B060);
      KeReleaseInStackQueuedSpinLockFromDpcLevel(&LockHandle);
    }
    *(_OWORD *)&Context.ChainHead = 0;
    for ( i = RtlLookupEntryHashTable(&stru_14009B030, ProcessId, &Context);
          i;
          i = RtlGetNextEntryHashTable(&stru_14009B030, &Context) )
    {
      if ( LODWORD(i[1].Linkage.Flink) == ProcessId )
      {
        v2 = 1;
        break;
      }
    }
    _InterlockedDecrement(&dword_14009B060);
    KeLowerIrql(v4);
    return v2;
  }
  return result;
}

```

## disassembly

```asm
0x14003b1a0  mov     [rsp+arg_0], rbx
0x14003b1a5  mov     [rsp+arg_8], rsi
0x14003b1aa  push    rdi
0x14003b1ab  sub     rsp, 50h
0x14003b1af  xor     eax, eax
0x14003b1b1  xorps   xmm0, xmm0
0x14003b1b4  cmp     cs:byte_14009B06C, al
0x14003b1ba  movups  xmmword ptr [rsp+58h+Context.ChainHead], xmm0
0x14003b1bf  mov     [rsp+58h+Context.Signature], rax
0x14003b1c4  jz      loc_14003B259
0x14003b1ca  xor     bl, bl
0x14003b1cc  call    cs:__imp_PsGetProcessId
0x14003b1d3  nop     dword ptr [rax+rax+00h]
0x14003b1d8  mov     cl, 2; NewIrql
0x14003b1da  mov     rdi, rax
0x14003b1dd  call    cs:__imp_KfRaiseIrql
0x14003b1e4  nop     dword ptr [rax+rax+00h]
0x14003b1e9  mov     sil, al
0x14003b1ec  xorps   xmm0, xmm0
0x14003b1ef  xor     eax, eax
0x14003b1f1  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14003b1f6  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x14003b1fb  lock inc cs:dword_14009B060
0x14003b202  lea     rcx, SpinLock; SpinLock
0x14003b209  call    cs:__imp_KeTestSpinLock
0x14003b210  nop     dword ptr [rax+rax+00h]
0x14003b215  test    al, al
0x14003b217  jz      short loc_14003B273
0x14003b219  xorps   xmm0, xmm0
0x14003b21c  mov     edx, edi; Signature
0x14003b21e  lea     r8, [rsp+58h+Context]; Context
0x14003b223  lea     rcx, stru_14009B030; HashTable
0x14003b22a  movdqu  xmmword ptr [rsp+58h+Context.ChainHead], xmm0
0x14003b230  call    cs:__imp_RtlLookupEntryHashTable
0x14003b237  nop     dword ptr [rax+rax+00h]
0x14003b23c  test    rax, rax
0x14003b23f  jnz     short loc_14003B26A
0x14003b241  lock dec cs:dword_14009B060
0x14003b248  mov     cl, sil; NewIrql
0x14003b24b  call    cs:__imp_KeLowerIrql
0x14003b252  nop     dword ptr [rax+rax+00h]
0x14003b257  mov     al, bl
0x14003b259  mov     rbx, [rsp+58h+arg_0]
0x14003b25e  mov     rsi, [rsp+58h+arg_8]
0x14003b263  add     rsp, 50h
0x14003b267  pop     rdi
0x14003b268  retn
0x14003b26a  cmp     [rax+18h], edi
0x14003b26d  jnz     short loc_14003B2AF
0x14003b26f  mov     bl, 1
0x14003b271  jmp     short loc_14003B241
0x14003b273  lock dec cs:dword_14009B060
0x14003b27a  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14003b27f  lea     rcx, SpinLock; SpinLock
0x14003b286  call    cs:__imp_KeAcquireInStackQueuedSpinLockAtDpcLevel
0x14003b28d  nop     dword ptr [rax+rax+00h]
0x14003b292  lock inc cs:dword_14009B060
0x14003b299  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14003b29e  call    cs:__imp_KeReleaseInStackQueuedSpinLockFromDpcLevel
0x14003b2a5  nop     dword ptr [rax+rax+00h]
0x14003b2aa  jmp     loc_14003B219
0x14003b2af  lea     rdx, [rsp+58h+Context]; Context
0x14003b2b4  lea     rcx, stru_14009B030; HashTable
0x14003b2bb  call    cs:__imp_RtlGetNextEntryHashTable
0x14003b2c2  nop     dword ptr [rax+rax+00h]
0x14003b2c7  jmp     loc_14003B23C
```
