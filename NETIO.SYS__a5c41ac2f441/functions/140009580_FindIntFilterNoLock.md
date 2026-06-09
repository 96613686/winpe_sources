# FindIntFilterNoLock

- ea: `0x140009580`
- end: `0x140009767`
- name: `FindIntFilterNoLock`
- size: `487`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x140008900`
- `0x14001b7b0`

## callees

- `0x140009520`
- `0x140009580`
- `0x140009770`
- `0x140009e00`
- `0x14001cfe0`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400095f7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400096d4`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400095f7`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1400096d4`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400095ba`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400095ba`
- `NDIS!NdisAcquireRWLockRead` at `0x1400095db`
- `NDIS!NdisAcquireRWLockRead` at `0x140009677`
- `NDIS!NdisAcquireRWLockRead` at `0x1400095db`
- `NDIS!NdisAcquireRWLockRead` at `0x140009677`
- `NDIS!NdisReleaseRWLock` at `0x1400096b6`
- `NDIS!NdisReleaseRWLock` at `0x140009708`
- `NDIS!NdisReleaseRWLock` at `0x1400096b6`
- `NDIS!NdisReleaseRWLock` at `0x140009708`

## string_xrefs

- `0x140009643`: `FeAcquireWriteEngineLock`
- `0x140009747`: `FeAcquireReadEngineLock`

## pseudocode

```c
__int64 __fastcall FindIntFilterNoLock(unsigned __int16 a1, __int64 a2, _QWORD *a3)
{
  PNPAGED_LOOKASIDE_LIST v3; // rdi
  KIRQL CurrentIrql; // bl
  __int64 v8; // rdx
  __int64 Flink_low; // rcx
  __int64 IntFilter; // rbx
  PNPAGED_LOOKASIDE_LIST v11; // rdi
  _DWORD *v12; // rdx
  struct _LOCK_STATE_EX v14; // [rsp+20h] [rbp-48h] BYREF
  _QWORD v15[8]; // [rsp+28h] [rbp-40h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+88h] [rbp+20h] BYREF

  v3 = gWfpGlobal;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v15[0] = 0;
  *(_WORD *)&v14.OldIrql = 0;
  v14.Flags = 0;
  CurrentIrql = KeGetCurrentIrql();
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)v3[1].L.ListHead.Alignment, &LockState, 0);
  if ( CurrentIrql != 2 && gWfpPerProContext )
  {
    v8 = *(_QWORD *)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    *(_QWORD *)(v8 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v8 = 4;
  }
  Flink_low = LODWORD(gWfpGlobal[1].L.ListEntry.Flink);
  if ( (_DWORD)Flink_low == 2 )
  {
    IntFilter = WfpReportSysErrorAsNtStatus(Flink_low, "FeAcquireWriteEngineLock", 3221225473LL, 1);
    if ( IntFilter )
    {
      WfpReleaseFastWriteLock(&gWfpGlobal[1], &LockState);
      WfpReportError(IntFilter, "FeAcquireReadEngineLock");
LABEL_14:
      WfpReportError(IntFilter, "FindIntFilterNoLock");
      return IntFilter;
    }
  }
  NdisAcquireRWLockRead((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &v14, 1u);
  IntFilter = FindIntFilter(a1, a2, v15);
  if ( !IntFilter )
    *a3 = v15[0];
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &v14);
  v11 = gWfpGlobal;
  if ( gWfpPerProContext )
  {
    v12 = *(_DWORD **)(gWfpPerProContextSize * KeGetCurrentProcessorNumberEx(0) + gWfpPerProContext);
    if ( *v12 == 4 )
      *v12 = 0;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)v11[1].L.ListHead.Alignment, &LockState);
  if ( IntFilter )
    goto LABEL_14;
  return IntFilter;
}

```

## disassembly

```asm
0x140009580  mov     r11, rsp
0x140009583  push    rbx
0x140009584  push    rbp
0x140009585  push    rsi
0x140009586  push    rdi
0x140009587  push    r14
0x140009589  push    r15
0x14000958b  sub     rsp, 38h
0x14000958f  mov     rdi, cs:gWfpGlobal
0x140009596  xor     eax, eax
0x140009598  xor     r15d, r15d
0x14000959b  mov     [r11+20h], ax
0x1400095a0  mov     [r11+22h], al
0x1400095a4  mov     r14, r8
0x1400095a7  mov     [r11-40h], r15
0x1400095ab  mov     rsi, rdx
0x1400095ae  mov     word ptr [rsp+68h+var_48.OldIrql], ax
0x1400095b3  movzx   ebp, cx
0x1400095b6  mov     [rsp+68h+var_48.Flags], al
0x1400095ba  call    cs:__imp_KeGetCurrentIrql
0x1400095c1  nop     dword ptr [rax+rax+00h]
0x1400095c6  mov     rcx, [rdi+80h]; Lock
0x1400095cd  lea     rdx, [rsp+68h+LockState]; LockState
0x1400095d5  xor     r8d, r8d; Flags
0x1400095d8  movzx   ebx, al
0x1400095db  call    cs:__imp_NdisAcquireRWLockRead
0x1400095e2  nop     dword ptr [rax+rax+00h]
0x1400095e7  cmp     bl, 2
0x1400095ea  jz      short loc_14000962B
0x1400095ec  cmp     cs:gWfpPerProContext, r15
0x1400095f3  jz      short loc_14000962B
0x1400095f5  xor     ecx, ecx; ProcNumber
0x1400095f7  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400095fe  nop     dword ptr [rax+rax+00h]
0x140009603  imul    eax, cs:gWfpPerProContextSize
0x14000960a  mov     ecx, eax
0x14000960c  mov     rax, cs:gWfpPerProContext
0x140009613  mov     rdx, [rcx+rax]
0x140009617  mov     rax, ds:0FFFFF78000000008h
0x140009621  mov     [rdx+8], rax
0x140009625  mov     dword ptr [rdx], 4
0x14000962b  mov     rax, cs:gWfpGlobal
0x140009632  mov     ecx, [rax+0C0h]
0x140009638  cmp     ecx, 2
0x14000963b  jnz     short loc_140009661
0x14000963d  mov     r9d, 1
0x140009643  lea     rdx, aFeacquirewrite; "FeAcquireWriteEngineLock"
0x14000964a  mov     r8d, 0C0000001h
0x140009650  call    WfpReportSysErrorAsNtStatus
0x140009655  mov     rbx, rax
0x140009658  test    rax, rax
0x14000965b  jnz     loc_14000972F
0x140009661  mov     rcx, cs:gWfpGlobal
0x140009668  lea     rdx, [rsp+68h+var_48]; LockState
0x14000966d  mov     r8b, 1; Flags
0x140009670  mov     rcx, [rcx+6C0h]; Lock
0x140009677  call    cs:__imp_NdisAcquireRWLockRead
0x14000967e  nop     dword ptr [rax+rax+00h]
0x140009683  lea     r8, [rsp+68h+var_40]
0x140009688  mov     rdx, rsi
0x14000968b  movzx   ecx, bp
0x14000968e  call    FindIntFilter
0x140009693  mov     rbx, rax
0x140009696  test    rax, rax
0x140009699  jnz     short loc_1400096A3
0x14000969b  mov     rax, [rsp+68h+var_40]
0x1400096a0  mov     [r14], rax
0x1400096a3  mov     rcx, cs:gWfpGlobal
0x1400096aa  lea     rdx, [rsp+68h+var_48]; LockState
0x1400096af  mov     rcx, [rcx+6C0h]; Lock
0x1400096b6  call    cs:__imp_NdisReleaseRWLock
0x1400096bd  nop     dword ptr [rax+rax+00h]
0x1400096c2  cmp     cs:gWfpPerProContext, r15
0x1400096c9  mov     rdi, cs:gWfpGlobal
0x1400096d0  jz      short loc_1400096F9
0x1400096d2  xor     ecx, ecx; ProcNumber
0x1400096d4  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x1400096db  nop     dword ptr [rax+rax+00h]
0x1400096e0  imul    eax, cs:gWfpPerProContextSize
0x1400096e7  mov     ecx, eax
0x1400096e9  mov     rax, cs:gWfpPerProContext
0x1400096f0  mov     rdx, [rcx+rax]
0x1400096f4  cmp     dword ptr [rdx], 4
0x1400096f7  jz      short loc_14000972A
0x1400096f9  mov     rcx, [rdi+80h]; Lock
0x140009700  lea     rdx, [rsp+68h+LockState]; LockState
0x140009708  call    cs:__imp_NdisReleaseRWLock
0x14000970f  nop     dword ptr [rax+rax+00h]
0x140009714  test    rbx, rbx
0x140009717  jnz     short loc_140009756
0x140009719  mov     rax, rbx
0x14000971c  add     rsp, 38h
0x140009720  pop     r15
0x140009722  pop     r14
0x140009724  pop     rdi
0x140009725  pop     rsi
0x140009726  pop     rbp
0x140009727  pop     rbx
0x140009728  retn
0x14000972a  mov     [rdx], r15d
0x14000972d  jmp     short loc_1400096F9
0x14000972f  mov     rcx, cs:gWfpGlobal
0x140009736  lea     rdx, [rsp+68h+LockState]
0x14000973e  sub     rcx, 0FFFFFFFFFFFFFF80h
0x140009742  call    WfpReleaseFastWriteLock
0x140009747  lea     rdx, aFeacquirereade; "FeAcquireReadEngineLock"
0x14000974e  mov     rcx, rbx
0x140009751  call    WfpReportError
0x140009756  lea     rdx, aFindintfiltern; "FindIntFilterNoLock"
0x14000975d  mov     rcx, rbx
0x140009760  call    WfpReportError
0x140009765  jmp     short loc_140009719
```
