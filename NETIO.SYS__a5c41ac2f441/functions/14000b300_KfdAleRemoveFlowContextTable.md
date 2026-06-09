# KfdAleRemoveFlowContextTable

- ea: `0x14000b300`
- end: `0x14000b522`
- name: `KfdAleRemoveFlowContextTable`
- size: `546`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000b2b0`

## callees

- `0x14000b300`
- `0x14004faf8`

## import_xrefs

- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000b45a`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x14000b45a`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b4c6`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14000b4c6`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b432`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14000b432`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b3e1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b472`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b3e1`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b472`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3a8`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b3a8`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b3c3`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14000b3c3`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b49c`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14000b49c`

## pseudocode

```c
void __fastcall KfdAleRemoveFlowContextTable(struct _LIST_ENTRY *a1)
{
  ULONG_PTR v2; // rbx
  KIRQL CurrentIrql; // di
  __int64 v4; // rdx
  PRTL_DYNAMIC_HASH_TABLE_ENTRY i; // rax
  _DWORD *v6; // rdx
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+20h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-20h] BYREF

  memset(&Context, 0, sizeof(Context));
  memset(&LockHandle, 0, sizeof(LockHandle));
  _mm_lfence();
  v2 = ((unsigned __int64)a1 >> 56)
     + 37
     * (BYTE6(a1)
      + 37
      * (BYTE5(a1)
       + 37 * (BYTE4(a1) + 37 * (BYTE3(a1) + 37 * (BYTE2(a1) + 37 * (BYTE1(a1) + 37LL * (unsigned __int8)a1))))));
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock(&handleTableLock, &LockHandle);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v4 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v4 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v4 = 4;
  }
  if ( !v2 )
    v2 = -1;
  for ( i = RtlLookupEntryHashTable(&handleTable, v2, &Context); i; i = RtlGetNextEntryHashTable(&handleTable, &Context) )
  {
    if ( i[1].Linkage.Flink == a1 )
    {
      RtlRemoveEntryHashTable(&handleTable, i, 0);
      goto LABEL_10;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 3u
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10000) != 0 )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_9bead0a5ff0231214eb4a33e05b22688_Traceguids);
  }
LABEL_10:
  if ( gWfpPerProContext )
  {
    v6 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v6 == 4 )
      *v6 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
}

```

## disassembly

```asm
0x14000b300  mov     [rsp+arg_0], rbx
0x14000b305  mov     [rsp+arg_8], rsi
0x14000b30a  push    rdi
0x14000b30b  sub     rsp, 50h
0x14000b30f  xor     eax, eax
0x14000b311  xorps   xmm0, xmm0
0x14000b314  xorps   xmm1, xmm1
0x14000b317  mov     [rsp+58h+Context.Signature], rax
0x14000b31c  movups  xmmword ptr [rsp+58h+Context.ChainHead], xmm0
0x14000b321  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x14000b326  mov     rsi, rcx
0x14000b329  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm1
0x14000b32e  lfence
0x14000b331  movzx   eax, cl
0x14000b334  imul    rdx, rax, 25h ; '%'
0x14000b338  mov     rax, rcx
0x14000b33b  shr     rax, 8
0x14000b33f  movzx   eax, al
0x14000b342  add     rdx, rax
0x14000b345  mov     rax, rsi
0x14000b348  shr     rax, 10h
0x14000b34c  movzx   eax, al
0x14000b34f  imul    rcx, rdx, 25h ; '%'
0x14000b353  add     rcx, rax
0x14000b356  mov     rax, rsi
0x14000b359  shr     rax, 18h
0x14000b35d  movzx   eax, al
0x14000b360  imul    rdx, rcx, 25h ; '%'
0x14000b364  add     rdx, rax
0x14000b367  mov     rax, rsi
0x14000b36a  shr     rax, 20h
0x14000b36e  movzx   eax, al
0x14000b371  imul    rcx, rdx, 25h ; '%'
0x14000b375  add     rcx, rax
0x14000b378  mov     rax, rsi
0x14000b37b  shr     rax, 28h
0x14000b37f  movzx   eax, al
0x14000b382  imul    rdx, rcx, 25h ; '%'
0x14000b386  add     rdx, rax
0x14000b389  mov     rax, rsi
0x14000b38c  shr     rax, 30h
0x14000b390  movzx   eax, al
0x14000b393  imul    rcx, rdx, 25h ; '%'
0x14000b397  add     rcx, rax
0x14000b39a  mov     rax, rsi
0x14000b39d  imul    rbx, rcx, 25h ; '%'
0x14000b3a1  shr     rax, 38h
0x14000b3a5  add     rbx, rax
0x14000b3a8  call    cs:__imp_KeGetCurrentIrql
0x14000b3af  nop     dword ptr [rax+rax+00h]
0x14000b3b4  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x14000b3b9  movzx   edi, al
0x14000b3bc  lea     rcx, handleTableLock; SpinLock
0x14000b3c3  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14000b3ca  nop     dword ptr [rax+rax+00h]
0x14000b3cf  cmp     dil, 2
0x14000b3d3  jz      short loc_14000B415
0x14000b3d5  cmp     cs:gWfpPerProContext, 0
0x14000b3dd  jz      short loc_14000B415
0x14000b3df  xor     ecx, ecx; ProcNumber
0x14000b3e1  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b3e8  nop     dword ptr [rax+rax+00h]
0x14000b3ed  imul    eax, cs:gWfpPerProContextSize
0x14000b3f4  mov     ecx, eax
0x14000b3f6  mov     rax, cs:gWfpPerProContext
0x14000b3fd  mov     rdx, [rcx+rax]
0x14000b401  mov     rax, ds:0FFFFF78000000008h
0x14000b40b  mov     [rdx+8], rax
0x14000b40f  mov     dword ptr [rdx], 4
0x14000b415  test    rbx, rbx
0x14000b418  lea     r8, [rsp+58h+Context]; Context
0x14000b41d  mov     rax, 0FFFFFFFFFFFFFFFFh
0x14000b424  lea     rcx, handleTable; HashTable
0x14000b42b  cmovz   rbx, rax
0x14000b42f  mov     rdx, rbx; Signature
0x14000b432  call    cs:__imp_RtlLookupEntryHashTable
0x14000b439  nop     dword ptr [rax+rax+00h]
0x14000b43e  test    rax, rax
0x14000b441  jz      loc_14000B4D7
0x14000b447  lea     rcx, handleTable; HashTable
0x14000b44e  cmp     [rax+18h], rsi
0x14000b452  jnz     short loc_14000B4C1
0x14000b454  xor     r8d, r8d; Context
0x14000b457  mov     rdx, rax; Entry
0x14000b45a  call    cs:__imp_RtlRemoveEntryHashTable
0x14000b461  nop     dword ptr [rax+rax+00h]
0x14000b466  cmp     cs:gWfpPerProContext, 0
0x14000b46e  jz      short loc_14000B497
0x14000b470  xor     ecx, ecx; ProcNumber
0x14000b472  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b479  nop     dword ptr [rax+rax+00h]
0x14000b47e  imul    eax, cs:gWfpPerProContextSize
0x14000b485  mov     ecx, eax
0x14000b487  mov     rax, cs:gWfpPerProContext
0x14000b48e  mov     rdx, [rcx+rax]
0x14000b492  cmp     dword ptr [rdx], 4
0x14000b495  jz      short loc_14000B4B9
0x14000b497  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x14000b49c  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14000b4a3  nop     dword ptr [rax+rax+00h]
0x14000b4a8  mov     rbx, [rsp+58h+arg_0]
0x14000b4ad  mov     rsi, [rsp+58h+arg_8]
0x14000b4b2  add     rsp, 50h
0x14000b4b6  pop     rdi
0x14000b4b7  retn
0x14000b4b9  mov     dword ptr [rdx], 0
0x14000b4bf  jmp     short loc_14000B497
0x14000b4c1  lea     rdx, [rsp+58h+Context]; Context
0x14000b4c6  call    cs:__imp_RtlGetNextEntryHashTable
0x14000b4cd  nop     dword ptr [rax+rax+00h]
0x14000b4d2  jmp     loc_14000B43E
0x14000b4d7  mov     rcx, cs:WPP_GLOBAL_Control
0x14000b4de  lea     rax, WPP_GLOBAL_Control
0x14000b4e5  cmp     rcx, rax
0x14000b4e8  jz      loc_14000B466
0x14000b4ee  cmp     byte ptr [rcx+29h], 3
0x14000b4f2  jb      loc_14000B466
0x14000b4f8  test    dword ptr [rcx+2Ch], 10000h
0x14000b4ff  jz      loc_14000B466
0x14000b505  mov     rcx, [rcx+18h]
0x14000b509  lea     r8, WPP_9bead0a5ff0231214eb4a33e05b22688_Traceguids
0x14000b510  mov     edx, 0Ah
0x14000b515  mov     r9, rsi
0x14000b518  call    WPP_SF_q
0x14000b51d  jmp     loc_14000B466
```
