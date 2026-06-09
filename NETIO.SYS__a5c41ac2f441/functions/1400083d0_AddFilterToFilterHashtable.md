# AddFilterToFilterHashtable

- ea: `0x1400083d0`
- end: `0x1400085e4`
- name: `AddFilterToFilterHashtable`
- size: `532`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x14004bd30`

## callees

- `0x140006c40`
- `0x1400083d0`
- `0x140009520`
- `0x140009e00`
- `0x14000a230`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlInsertEntryHashTable` at `0x140008492`
- `ntoskrnl!RtlInsertEntryHashTable` at `0x140008492`
- `ntoskrnl!ExAllocatePool2` at `0x14000842a`
- `ntoskrnl!ExAllocatePool2` at `0x14000842a`
- `NDIS!NdisReleaseRWLock` at `0x1400084d9`
- `NDIS!NdisReleaseRWLock` at `0x14000858e`
- `NDIS!NdisReleaseRWLock` at `0x1400084d9`
- `NDIS!NdisReleaseRWLock` at `0x14000858e`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000840c`
- `NDIS!NdisAcquireRWLockWrite` at `0x14000840c`

## pseudocode

```c
__int64 __fastcall AddFilterToFilterHashtable(unsigned __int16 a1, __int64 a2, __int64 a3)
{
  int v3; // ebp
  __int64 v6; // rbx
  __int64 v7; // rdi
  __int64 v8; // rcx
  __int64 v10[5]; // [rsp+30h] [rbp-28h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+78h] [rbp+20h] BYREF

  v3 = a1;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  NdisAcquireRWLockWrite((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState, 1u);
  v6 = 0;
  v10[0] = ExAllocatePool2(64, 48, 1215325783);
  v7 = v10[0];
  if ( !v10[0] )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        10,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"ExAllocatePool2",
        23);
    }
    v6 = -1073741801;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"WfpPoolAllocNonPaged",
        23);
LABEL_13:
      WfpPoolFree(v10);
      NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
      WfpReportError(v6, "AddFilterToFilterHashtable");
      return v6;
    }
  }
  if ( v6 )
    goto LABEL_13;
  *(_QWORD *)(v10[0] + 16) = ComputeFilterHash((unsigned __int16)v3, a2);
  *(_DWORD *)(v7 + 28) = v3;
  *(_QWORD *)(v7 + 32) = a2;
  *(_QWORD *)(v7 + 40) = a3;
  *(_DWORD *)(v7 + 24) = gWfpGlobal[3].L.AllocateMisses;
  if ( !RtlInsertEntryHashTable(
          *(PRTL_DYNAMIC_HASH_TABLE *)&gWfpGlobal[3].L.Depth,
          (PRTL_DYNAMIC_HASH_TABLE_ENTRY)v7,
          *(_QWORD *)(v7 + 16),
          0) )
  {
    v6 = WfpReportSysErrorAsNtStatus(v8, "RtlInsertEntryHashTable", 3221225495LL, 1);
    if ( v6 )
      goto LABEL_13;
  }
  NdisReleaseRWLock((PNDIS_RW_LOCK_EX)gWfpGlobal[13].L.ListEntry.Flink, &LockState);
  return v6;
}

```

## disassembly

```asm
0x1400083d0  mov     [rsp+arg_8], rbx
0x1400083d5  mov     [rsp+arg_10], rbp
0x1400083da  push    rsi
0x1400083db  push    rdi
0x1400083dc  push    r14
0x1400083de  sub     rsp, 40h
0x1400083e2  movzx   ebp, cx
0x1400083e5  xor     eax, eax
0x1400083e7  mov     rcx, cs:gWfpGlobal
0x1400083ee  mov     r14, r8
0x1400083f1  mov     rsi, rdx
0x1400083f4  mov     word ptr [rsp+58h+LockState.OldIrql], ax
0x1400083f9  mov     [rsp+58h+LockState.Flags], al
0x1400083fd  lea     rdx, [rsp+58h+LockState]; LockState
0x140008402  mov     r8b, 1; Flags
0x140008405  mov     rcx, [rcx+6C0h]; Lock
0x14000840c  call    cs:__imp_NdisAcquireRWLockWrite
0x140008413  nop     dword ptr [rax+rax+00h]
0x140008418  mov     edx, 30h ; '0'
0x14000841d  mov     ecx, 40h ; '@'
0x140008422  mov     r8d, 48706657h
0x140008428  xor     ebx, ebx
0x14000842a  call    cs:__imp_ExAllocatePool2
0x140008431  nop     dword ptr [rax+rax+00h]
0x140008436  mov     [rsp+58h+var_28], rax
0x14000843b  mov     rdi, rax
0x14000843e  test    rax, rax
0x140008441  jz      loc_1400084FC
0x140008447  test    rbx, rbx
0x14000844a  jnz     loc_140008571
0x140008450  mov     rdx, rsi
0x140008453  movzx   ecx, bp
0x140008456  call    ComputeFilterHash
0x14000845b  mov     [rdi+10h], rax
0x14000845f  xor     r9d, r9d; Context
0x140008462  mov     [rdi+1Ch], ebp
0x140008465  mov     rdx, rdi; Entry
0x140008468  mov     [rdi+20h], rsi
0x14000846c  mov     [rdi+28h], r14
0x140008470  mov     rax, cs:gWfpGlobal
0x140008477  mov     ecx, [rax+198h]
0x14000847d  mov     [rdi+18h], ecx
0x140008480  mov     rcx, cs:gWfpGlobal
0x140008487  mov     r8, [rdi+10h]; Signature
0x14000848b  mov     rcx, [rcx+190h]; HashTable
0x140008492  call    cs:__imp_RtlInsertEntryHashTable
0x140008499  nop     dword ptr [rax+rax+00h]
0x14000849e  test    al, al
0x1400084a0  jnz     short loc_1400084C6
0x1400084a2  mov     r9d, 1
0x1400084a8  lea     rdx, aRtlinsertentry; "RtlInsertEntryHashTable"
0x1400084af  mov     r8d, 0C0000017h
0x1400084b5  call    WfpReportSysErrorAsNtStatus
0x1400084ba  mov     rbx, rax
0x1400084bd  test    rax, rax
0x1400084c0  jnz     loc_140008571
0x1400084c6  mov     rcx, cs:gWfpGlobal
0x1400084cd  lea     rdx, [rsp+58h+LockState]; LockState
0x1400084d2  mov     rcx, [rcx+6C0h]; Lock
0x1400084d9  call    cs:__imp_NdisReleaseRWLock
0x1400084e0  nop     dword ptr [rax+rax+00h]
0x1400084e5  mov     rbp, [rsp+58h+arg_10]
0x1400084ea  mov     rax, rbx
0x1400084ed  mov     rbx, [rsp+58h+arg_8]
0x1400084f2  add     rsp, 40h
0x1400084f6  pop     r14
0x1400084f8  pop     rdi
0x1400084f9  pop     rsi
0x1400084fa  retn
0x1400084fc  mov     [rsp+58h+arg_0], r15
0x140008501  mov     rcx, cs:WPP_GLOBAL_Control
0x140008508  lea     r15, WPP_GLOBAL_Control
0x14000850f  cmp     rcx, r15
0x140008512  jz      short loc_14000851E
0x140008514  cmp     byte ptr [rcx+29h], 2
0x140008518  jnb     loc_1400085AE
0x14000851e  mov     rbx, 0FFFFFFFFC0000017h
0x140008525  mov     rcx, cs:WPP_GLOBAL_Control
0x14000852c  cmp     rcx, r15
0x14000852f  mov     r15, [rsp+58h+arg_0]
0x140008534  jz      loc_140008447
0x14000853a  cmp     byte ptr [rcx+29h], 2
0x14000853e  jb      loc_140008447
0x140008544  test    dword ptr [rcx+2Ch], 1000h
0x14000854b  jz      loc_140008447
0x140008551  mov     rcx, [rcx+18h]
0x140008555  lea     r9, aWfppoolallocno; "WfpPoolAllocNonPaged"
0x14000855c  mov     edx, 0Fh
0x140008561  mov     [rsp+58h+var_38], ebx
0x140008565  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14000856c  call    WPP_SF_sd
0x140008571  lea     rcx, [rsp+58h+var_28]
0x140008576  call    WfpPoolFree
0x14000857b  mov     rcx, cs:gWfpGlobal
0x140008582  lea     rdx, [rsp+58h+LockState]; LockState
0x140008587  mov     rcx, [rcx+6C0h]; Lock
0x14000858e  call    cs:__imp_NdisReleaseRWLock
0x140008595  nop     dword ptr [rax+rax+00h]
0x14000859a  lea     rdx, aAddfiltertofil; "AddFilterToFilterHashtable"
0x1400085a1  mov     rcx, rbx
0x1400085a4  call    WfpReportError
0x1400085a9  jmp     loc_1400084E5
0x1400085ae  test    dword ptr [rcx+2Ch], 1000h
0x1400085b5  jz      loc_14000851E
0x1400085bb  mov     rcx, [rcx+18h]
0x1400085bf  lea     r9, aExallocatepool; "ExAllocatePool2"
0x1400085c6  mov     edx, 0Ah
0x1400085cb  mov     [rsp+58h+var_38], 0C0000017h
0x1400085d3  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x1400085da  call    WPP_SF_sd
0x1400085df  jmp     loc_14000851E
```
