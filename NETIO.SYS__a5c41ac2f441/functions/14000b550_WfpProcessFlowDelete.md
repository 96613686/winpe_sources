# WfpProcessFlowDelete

- ea: `0x14000b550`
- end: `0x14000b80f`
- name: `WfpProcessFlowDelete`
- size: `703`
- prototype: `void __fastcall(__int64, unsigned __int16 **)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x14000b2b0`
- `0x14000b530`

## callees

- `0x140006c40`
- `0x14000b550`
- `0x14000ba10`
- `0x14000bb9c`
- `0x14000bc60`
- `0x140078080`

## import_xrefs

- `ntoskrnl!ObfDereferenceObject` at `0x14000b7c0`
- `ntoskrnl!ObfDereferenceObject` at `0x14000b7c0`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b5ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b608`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b6c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b716`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b5ae`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b608`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b6c3`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x14000b716`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b572`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b687`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b572`
- `ntoskrnl!KeGetCurrentIrql` at `0x14000b687`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b7ee`
- `NDIS!NdisReleaseRWLock` at `0x14000b639`
- `NDIS!NdisReleaseRWLock` at `0x14000b74b`
- `NDIS!NdisReleaseRWLock` at `0x14000b639`
- `NDIS!NdisReleaseRWLock` at `0x14000b74b`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b590`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b6a5`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b590`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000b6a5`

## pseudocode

```c
void __fastcall WfpProcessFlowDelete(__int64 a1, unsigned __int16 **a2)
{
  PNPAGED_LOOKASIDE_LIST v2; // rbx
  KIRQL CurrentIrql; // di
  __int64 v6; // rdx
  unsigned __int16 *v7; // rbx
  bool v8; // zf
  PNPAGED_LOOKASIDE_LIST v9; // rdi
  _DWORD *v10; // rdx
  unsigned int i; // r14d
  PNPAGED_LOOKASIDE_LIST v12; // rsi
  __int64 v13; // rbp
  KIRQL v14; // di
  __int64 v15; // rdx
  __int64 v16; // rsi
  PNPAGED_LOOKASIDE_LIST v17; // rdi
  _DWORD *v18; // rdx
  __int64 v19; // r9
  unsigned int v20; // edi
  unsigned __int16 v21; // bp
  struct _LOCK_STATE_EX LockState; // [rsp+58h] [rbp+10h] BYREF
  void (__fastcall *v23)(_QWORD, _QWORD, __int64); // [rsp+60h] [rbp+18h] BYREF
  PVOID Object; // [rsp+68h] [rbp+20h] BYREF

  v2 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v2[3].L.AllocateEx, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v6 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v6 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v6 = 4;
  }
  v7 = *a2;
  if ( *a2 )
    *((_DWORD *)v7 + 1) |= 1u;
  v8 = gWfpPerProContext == 0;
  *a2 = (unsigned __int16 *)1;
  v9 = gWfpGlobal;
  if ( !v8 )
  {
    v10 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v10 == 4 )
      *v10 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v9[3].L.AllocateEx, &LockState);
  if ( v7 )
  {
    for ( i = 0; i < *v7; ++i )
    {
      v12 = gWfpGlobal;
      v13 = *((_QWORD *)v7 + 1) + 32LL * i;
      v14 = KeGetCurrentIrql();
      NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)v12[3].L.AllocateEx, &LockState, 0);
      if ( v14 != 2 && gWfpPerProContext )
      {
        v15 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        *(_QWORD *)(v15 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v15 = 4;
      }
      v8 = gWfpPerProContext == 0;
      v16 = *(_QWORD *)(v13 + 16);
      *(_QWORD *)(v13 + 16) = 0;
      v17 = gWfpGlobal;
      if ( !v8 )
      {
        v18 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
        if ( *v18 == 4 )
          *v18 = 0;
      }
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v17[3].L.AllocateEx, &LockState);
      v19 = *(_QWORD *)(v13 + 24);
      v20 = *(_DWORD *)(v13 + 12);
      v21 = *(_WORD *)(v13 + 8);
      v23 = 0;
      if ( v19 )
        StreamDeleteCalloutContext(a1, v21, v20);
      if ( v16 )
      {
        Object = 0;
        FeGetCalloutFlowDelete(v20, &v23, &Object);
        FeDeRefCalloutFlowContext(v20);
        v23(v21, v20, v16);
        if ( Object )
          ObfDereferenceObject(Object);
      }
    }
    WfpPoolFree(v7 + 4);
    ExFreePoolWithTag(v7, 0);
  }
}

```

## disassembly

```asm
0x14000b550  push    rbx
0x14000b552  push    rsi
0x14000b553  push    rdi
0x14000b554  push    r15
0x14000b556  sub     rsp, 28h
0x14000b55a  mov     rbx, cs:gWfpGlobal
0x14000b561  xor     eax, eax
0x14000b563  mov     word ptr [rsp+48h+LockState.OldIrql], ax
0x14000b568  mov     rsi, rdx
0x14000b56b  mov     [rsp+48h+LockState.Flags], al
0x14000b56f  mov     r15, rcx
0x14000b572  call    cs:__imp_KeGetCurrentIrql
0x14000b579  nop     dword ptr [rax+rax+00h]
0x14000b57e  mov     rcx, [rbx+1B0h]; Lock
0x14000b585  lea     rdx, [rsp+48h+LockState]; LockState
0x14000b58a  xor     r8d, r8d; Flags
0x14000b58d  movzx   edi, al
0x14000b590  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b597  nop     dword ptr [rax+rax+00h]
0x14000b59c  cmp     dil, 2
0x14000b5a0  jz      short loc_14000B5E2
0x14000b5a2  cmp     cs:gWfpPerProContext, 0
0x14000b5aa  jz      short loc_14000B5E2
0x14000b5ac  xor     ecx, ecx; ProcNumber
0x14000b5ae  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b5b5  nop     dword ptr [rax+rax+00h]
0x14000b5ba  imul    eax, cs:gWfpPerProContextSize
0x14000b5c1  mov     ecx, eax
0x14000b5c3  mov     rax, cs:gWfpPerProContext
0x14000b5ca  mov     rdx, [rcx+rax]
0x14000b5ce  mov     rax, ds:0FFFFF78000000008h
0x14000b5d8  mov     [rdx+8], rax
0x14000b5dc  mov     dword ptr [rdx], 4
0x14000b5e2  mov     rbx, [rsi]
0x14000b5e5  test    rbx, rbx
0x14000b5e8  jz      short loc_14000B5EE
0x14000b5ea  or      dword ptr [rbx+4], 1
0x14000b5ee  cmp     cs:gWfpPerProContext, 0
0x14000b5f6  mov     qword ptr [rsi], 1
0x14000b5fd  mov     rdi, cs:gWfpGlobal
0x14000b604  jz      short loc_14000B62D
0x14000b606  xor     ecx, ecx; ProcNumber
0x14000b608  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b60f  nop     dword ptr [rax+rax+00h]
0x14000b614  imul    eax, cs:gWfpPerProContextSize
0x14000b61b  mov     ecx, eax
0x14000b61d  mov     rax, cs:gWfpPerProContext
0x14000b624  mov     rdx, [rcx+rax]
0x14000b628  cmp     dword ptr [rdx], 4
0x14000b62b  jz      short loc_14000B655
0x14000b62d  mov     rcx, [rdi+1B0h]; Lock
0x14000b634  lea     rdx, [rsp+48h+LockState]; LockState
0x14000b639  call    cs:__imp_NdisReleaseRWLock
0x14000b640  nop     dword ptr [rax+rax+00h]
0x14000b645  test    rbx, rbx
0x14000b648  jnz     short loc_14000B65D
0x14000b64a  add     rsp, 28h
0x14000b64e  pop     r15
0x14000b650  pop     rdi
0x14000b651  pop     rsi
0x14000b652  pop     rbx
0x14000b653  retn
0x14000b655  mov     dword ptr [rdx], 0
0x14000b65b  jmp     short loc_14000B62D
0x14000b65d  mov     [rsp+48h+var_28], r14
0x14000b662  xor     eax, eax
0x14000b664  xor     r14d, r14d
0x14000b667  cmp     ax, [rbx]
0x14000b66a  jnb     loc_14000B7E0
0x14000b670  mov     [rsp+48h+arg_0], rbp
0x14000b675  mov     rsi, cs:gWfpGlobal
0x14000b67c  mov     ebp, r14d
0x14000b67f  shl     rbp, 5
0x14000b683  add     rbp, [rbx+8]
0x14000b687  call    cs:__imp_KeGetCurrentIrql
0x14000b68e  nop     dword ptr [rax+rax+00h]
0x14000b693  mov     rcx, [rsi+1B0h]; Lock
0x14000b69a  lea     rdx, [rsp+48h+LockState]; LockState
0x14000b69f  xor     r8d, r8d; Flags
0x14000b6a2  movzx   edi, al
0x14000b6a5  call    cs:__imp_NdisAcquireRWLockWrite
0x14000b6ac  nop     dword ptr [rax+rax+00h]
0x14000b6b1  cmp     dil, 2
0x14000b6b5  jz      short loc_14000B6F7
0x14000b6b7  cmp     cs:gWfpPerProContext, 0
0x14000b6bf  jz      short loc_14000B6F7
0x14000b6c1  xor     ecx, ecx; ProcNumber
0x14000b6c3  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b6ca  nop     dword ptr [rax+rax+00h]
0x14000b6cf  imul    eax, cs:gWfpPerProContextSize
0x14000b6d6  mov     ecx, eax
0x14000b6d8  mov     rax, cs:gWfpPerProContext
0x14000b6df  mov     rdx, [rcx+rax]
0x14000b6e3  mov     rax, ds:0FFFFF78000000008h
0x14000b6ed  mov     [rdx+8], rax
0x14000b6f1  mov     dword ptr [rdx], 4
0x14000b6f7  cmp     cs:gWfpPerProContext, 0
0x14000b6ff  mov     rsi, [rbp+10h]
0x14000b703  mov     qword ptr [rbp+10h], 0
0x14000b70b  mov     rdi, cs:gWfpGlobal
0x14000b712  jz      short loc_14000B73F
0x14000b714  xor     ecx, ecx; ProcNumber
0x14000b716  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x14000b71d  nop     dword ptr [rax+rax+00h]
0x14000b722  imul    eax, cs:gWfpPerProContextSize
0x14000b729  mov     ecx, eax
0x14000b72b  mov     rax, cs:gWfpPerProContext
0x14000b732  mov     rdx, [rcx+rax]
0x14000b736  cmp     dword ptr [rdx], 4
0x14000b739  jz      loc_14000B804
0x14000b73f  mov     rcx, [rdi+1B0h]; Lock
0x14000b746  lea     rdx, [rsp+48h+LockState]; LockState
0x14000b74b  call    cs:__imp_NdisReleaseRWLock
0x14000b752  nop     dword ptr [rax+rax+00h]
0x14000b757  mov     r9, [rbp+18h]
0x14000b75b  mov     edi, [rbp+0Ch]
0x14000b75e  movzx   ebp, word ptr [rbp+8]
0x14000b762  mov     [rsp+48h+arg_10], 0
0x14000b76b  test    r9, r9
0x14000b76e  jz      short loc_14000B77E
0x14000b770  mov     r8d, edi
0x14000b773  movzx   edx, bp
0x14000b776  mov     rcx, r15
0x14000b779  call    StreamDeleteCalloutContext
0x14000b77e  test    rsi, rsi
0x14000b781  jz      short loc_14000B7CC
0x14000b783  lea     r8, [rsp+48h+Object]
0x14000b788  mov     [rsp+48h+Object], 0
0x14000b791  lea     rdx, [rsp+48h+arg_10]
0x14000b796  mov     ecx, edi
0x14000b798  call    FeGetCalloutFlowDelete
0x14000b79d  mov     ecx, edi
0x14000b79f  call    FeDeRefCalloutFlowContext
0x14000b7a4  mov     rax, [rsp+48h+arg_10]
0x14000b7a9  mov     r8, rsi
0x14000b7ac  mov     edx, edi
0x14000b7ae  movzx   ecx, bp
0x14000b7b1  call    _guard_dispatch_icall
0x14000b7b6  mov     rcx, [rsp+48h+Object]; Object
0x14000b7bb  test    rcx, rcx
0x14000b7be  jz      short loc_14000B7CC
0x14000b7c0  call    cs:__imp_ObfDereferenceObject
0x14000b7c7  nop     dword ptr [rax+rax+00h]
0x14000b7cc  movzx   eax, word ptr [rbx]
0x14000b7cf  inc     r14d
0x14000b7d2  cmp     r14d, eax
0x14000b7d5  jb      loc_14000B675
0x14000b7db  mov     rbp, [rsp+48h+arg_0]
0x14000b7e0  lea     rcx, [rbx+8]
0x14000b7e4  call    WfpPoolFree
0x14000b7e9  xor     edx, edx; Tag
0x14000b7eb  mov     rcx, rbx; P
0x14000b7ee  call    cs:__imp_ExFreePoolWithTag
0x14000b7f5  nop     dword ptr [rax+rax+00h]
0x14000b7fa  mov     r14, [rsp+48h+var_28]
0x14000b7ff  jmp     loc_14000B64A
0x14000b804  mov     dword ptr [rdx], 0
0x14000b80a  jmp     loc_14000B73F
```
