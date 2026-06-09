# TxfCreateTxfVscb

- ea: `0x140243c50`
- end: `0x140243f05`
- name: `TxfCreateTxfVscb`
- size: `693`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400faa5c`
- `0x14019dcc8`
- `0x140294b6c`

## callees

- `0x14000c450`
- `0x140012e70`
- `0x140059740`
- `0x140243c50`
- `0x140243f0c`

## import_xrefs

- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140243d5e`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140243d5e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7d06`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1402b7d06`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140243cbc`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x140243cbc`
- `ntoskrnl!KeInitializeEvent` at `0x140243d90`
- `ntoskrnl!KeInitializeEvent` at `0x140243d90`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7cef`
- `ntoskrnl!ExFreePoolWithTag` at `0x1402b7cef`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140243cf0`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x140243cf0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140243ca8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140243ca8`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243eac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243ee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7d45`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243e5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243eac`
- `ntoskrnl!ExReleaseResourceLite` at `0x140243ee0`
- `ntoskrnl!ExReleaseResourceLite` at `0x1402b7d45`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140243e10`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140243e10`

## pseudocode

```c
_DWORD *__fastcall TxfCreateTxfVscb(__int64 a1, __int64 a2, int a3, char a4)
{
  _DWORD *TableContext; // rdi
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rbx
  __int64 v12; // r8
  __int64 *i; // rcx
  __int64 *v14; // r14
  char v15; // dl

  NtfsAcquireSharedFcb(a1, *(_QWORD *)(a2 + 184), 0, 0);
  ExAcquireResourceExclusiveLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL), 1u);
  TableContext = ExAllocateFromLookasideListEx(&TxfVscbLookasideList);
  memset(TableContext, 0, 0x138u);
  *((_QWORD *)TableContext + 32) = ExAllocatePoolWithTag((POOL_TYPE)528, 0x38u, 0x6D667854u);
  *TableContext = 20449046;
  *((_QWORD *)TableContext + 2) = *(_QWORD *)(a2 + 528);
  if ( a3 && (*(_DWORD *)(a1 + 436) & 4) == 0 && *(_DWORD *)(a2 + 256) == 128 )
    TxfLoadVscbFileSizes(a1, TableContext, a2);
  RtlInitializeGenericTableAvl(
    (PRTL_AVL_TABLE)(TableContext + 38),
    TxfCompareChangeEntries,
    TxfAllocateChangeEntry,
    TxfFreeTableSpace,
    TableContext);
  v9 = *((_QWORD *)TableContext + 32);
  *(_DWORD *)v9 = 1;
  *(_QWORD *)(v9 + 8) = 0;
  *(_DWORD *)(v9 + 16) = 0;
  KeInitializeEvent((PRKEVENT)(v9 + 24), SynchronizationEvent, 0);
  *((_QWORD *)TableContext + 4) = *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL);
  v10 = *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL);
  if ( v10 )
  {
    *(_QWORD *)(v10 + 40) = TableContext;
    _InterlockedAdd(TableContext + 1, 1u);
  }
  *(_QWORD *)(*(_QWORD *)(a2 + 528) + 56LL) = TableContext;
  _InterlockedOr(TableContext + 2, *(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) & 0xF0000000);
  *(_DWORD *)(*(_QWORD *)(a2 + 528) + 24LL) &= 0xFFFFFFFu;
  v11 = *(_QWORD *)(a2 + 184);
  ExAcquireResourceSharedLite(*(PERESOURCE *)(*(_QWORD *)(v11 + 328) + 136LL), 1u);
  v12 = *(_QWORD *)(v11 + 328);
  for ( i = *(__int64 **)(v12 + 88); i != (__int64 *)(v12 + 88); i = (__int64 *)*i )
  {
    v14 = i;
    v15 = 1;
    if ( (*((_BYTE *)i + 78) & 8) != 0 )
    {
      if ( a4 )
      {
LABEL_12:
        if ( i != (__int64 *)(v12 + 88) )
          goto LABEL_16;
        break;
      }
      v15 = 0;
    }
    if ( v15 )
      goto LABEL_12;
  }
  ExReleaseResourceLite(*(PERESOURCE *)(v12 + 136));
  v14 = 0;
LABEL_16:
  *((_QWORD *)TableContext + 13) = v14;
  ++*((_WORD *)v14 + 38);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL));
  NtfsReleaseFcbEx(a1, *(_QWORD *)(a2 + 184), 0);
  ExReleaseResourceLite(*(PERESOURCE *)(*(_QWORD *)(*(_QWORD *)(a2 + 184) + 328LL) + 136LL));
  return TableContext;
}

```

## disassembly

```asm
0x140243c50  mov     rax, rsp
0x140243c53  mov     [rax+18h], rbx
0x140243c57  mov     [rax+10h], rdx
0x140243c5b  mov     [rax+8], rcx
0x140243c5f  push    rsi
0x140243c60  push    rdi
0x140243c61  push    r12
0x140243c63  push    r14
0x140243c65  push    r15
0x140243c67  sub     rsp, 50h
0x140243c6b  mov     r12b, r9b
0x140243c6e  mov     ebx, r8d
0x140243c71  mov     rsi, rdx
0x140243c74  mov     r15, rcx
0x140243c77  mov     qword ptr [rax-40h], 0
0x140243c7f  xor     r9d, r9d
0x140243c82  xor     r8d, r8d
0x140243c85  mov     rdx, [rdx+0B8h]
0x140243c8c  call    NtfsAcquireSharedFcb
0x140243c91  mov     rax, [rsi+0B8h]
0x140243c98  mov     rcx, [rax+148h]
0x140243c9f  mov     dl, 1; Wait
0x140243ca1  mov     rcx, [rcx+88h]; Resource
0x140243ca8  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140243caf  nop     dword ptr [rax+rax+00h]
0x140243cb4  nop
0x140243cb5  lea     rcx, TxfVscbLookasideList; Lookaside
0x140243cbc  call    cs:__imp_ExAllocateFromLookasideListEx
0x140243cc3  nop     dword ptr [rax+rax+00h]
0x140243cc8  mov     rdi, rax
0x140243ccb  mov     [rsp+78h+var_40], rax
0x140243cd0  xor     edx, edx; Val
0x140243cd2  mov     r8d, 138h; Size
0x140243cd8  mov     rcx, rax; void *
0x140243cdb  call    memset
0x140243ce0  mov     edx, 38h ; '8'; NumberOfBytes
0x140243ce5  mov     ecx, 210h; PoolType
0x140243cea  mov     r8d, 6D667854h; Tag
0x140243cf0  call    cs:__imp_ExAllocatePoolWithTag
0x140243cf7  nop     dword ptr [rax+rax+00h]
0x140243cfc  mov     [rdi+100h], rax
0x140243d03  mov     dword ptr [rdi], 1380716h
0x140243d09  mov     rax, [rsi+210h]
0x140243d10  mov     [rdi+10h], rax
0x140243d14  test    ebx, ebx
0x140243d16  jz      short loc_140243D3D
0x140243d18  mov     eax, [r15+1B4h]
0x140243d1f  test    al, 4
0x140243d21  jnz     short loc_140243D3D
0x140243d23  cmp     dword ptr [rsi+100h], 80h
0x140243d2d  jnz     short loc_140243D3D
0x140243d2f  mov     r8, rsi
0x140243d32  mov     rdx, rdi
0x140243d35  mov     rcx, r15
0x140243d38  call    TxfLoadVscbFileSizes
0x140243d3d  lea     rcx, [rdi+98h]; Table
0x140243d44  mov     [rsp+78h+TableContext], rdi; TableContext
0x140243d49  lea     r9, TxfFreeTableSpace; FreeRoutine
0x140243d50  lea     r8, TxfAllocateChangeEntry; AllocateRoutine
0x140243d57  lea     rdx, TxfCompareChangeEntries; CompareRoutine
0x140243d5e  call    cs:__imp_RtlInitializeGenericTableAvl
0x140243d65  nop     dword ptr [rax+rax+00h]
0x140243d6a  mov     rcx, [rdi+100h]
0x140243d71  mov     ebx, 1
0x140243d76  mov     [rcx], ebx
0x140243d78  mov     qword ptr [rcx+8], 0
0x140243d80  mov     dword ptr [rcx+10h], 0
0x140243d87  add     rcx, 18h; Event
0x140243d8b  xor     r8d, r8d; State
0x140243d8e  mov     edx, ebx; Type
0x140243d90  call    cs:__imp_KeInitializeEvent
0x140243d97  nop     dword ptr [rax+rax+00h]
0x140243d9c  mov     rax, [rsi+210h]
0x140243da3  mov     rcx, [rax+38h]
0x140243da7  mov     [rdi+20h], rcx
0x140243dab  mov     rax, [rsi+210h]
0x140243db2  mov     rcx, [rax+38h]
0x140243db6  test    rcx, rcx
0x140243db9  jnz     loc_140243E6E
0x140243dbf  mov     rax, [rsi+210h]
0x140243dc6  mov     [rax+38h], rdi
0x140243dca  mov     rax, [rsi+210h]
0x140243dd1  mov     ecx, [rax+18h]
0x140243dd4  and     ecx, 0F0000000h
0x140243dda  lock or [rdi+8], ecx
0x140243dde  mov     rax, [rsi+210h]
0x140243de5  and     dword ptr [rax+18h], 0FFFFFFFh
0x140243dec  mov     rbx, [rsi+0B8h]
0x140243df3  xor     r14d, r14d
0x140243df6  mov     [rsp+78h+var_38], r14
0x140243dfb  mov     [rsp+78h+var_48], r14b
0x140243e00  mov     rcx, [rbx+148h]
0x140243e07  mov     dl, 1; Wait
0x140243e09  mov     rcx, [rcx+88h]; Resource
0x140243e10  call    cs:__imp_ExAcquireResourceSharedLite
0x140243e17  nop     dword ptr [rax+rax+00h]
0x140243e1c  mov     r8, [rbx+148h]
0x140243e23  mov     rcx, [r8+58h]
0x140243e27  lea     ebx, [r14+1]
0x140243e2b  lea     r9, [r8+58h]
0x140243e2f  cmp     rcx, r9
0x140243e32  jz      short loc_140243E56
0x140243e34  mov     r14, rcx
0x140243e37  mov     [rsp+78h+var_38], rcx
0x140243e3c  mov     dl, bl
0x140243e3e  mov     [rsp+78h+var_48], bl
0x140243e42  test    byte ptr [rcx+4Eh], 8
0x140243e46  jnz     short loc_140243E7B
0x140243e48  test    dl, dl
0x140243e4a  jnz     short loc_140243E51
0x140243e4c  mov     rcx, [rcx]
0x140243e4f  jmp     short loc_140243E2B
0x140243e51  cmp     rcx, r9
0x140243e54  jnz     short loc_140243E8E
0x140243e56  mov     rcx, [r8+88h]; Resource
0x140243e5d  call    cs:__imp_ExReleaseResourceLite
0x140243e64  nop     dword ptr [rax+rax+00h]
0x140243e69  xor     r14d, r14d
0x140243e6c  jmp     short loc_140243E8E
0x140243e6e  mov     [rcx+28h], rdi
0x140243e72  lock add [rdi+4], ebx
0x140243e76  jmp     loc_140243DBF
0x140243e7b  test    r12b, r12b
0x140243e7e  jz      short loc_140243E86
0x140243e80  mov     [rsp+78h+var_48], bl
0x140243e84  jmp     short loc_140243E51
0x140243e86  xor     dl, dl
0x140243e88  mov     [rsp+78h+var_48], dl
0x140243e8c  jmp     short loc_140243E48
0x140243e8e  mov     [rdi+68h], r14
0x140243e92  add     [r14+4Ch], bx
0x140243e97  mov     rax, [rsi+0B8h]
0x140243e9e  mov     rcx, [rax+148h]
0x140243ea5  mov     rcx, [rcx+88h]; Resource
0x140243eac  call    cs:__imp_ExReleaseResourceLite
0x140243eb3  nop     dword ptr [rax+rax+00h]
0x140243eb8  nop
0x140243eb9  xor     r8d, r8d
0x140243ebc  mov     rdx, [rsi+0B8h]
0x140243ec3  mov     rcx, r15
0x140243ec6  call    NtfsReleaseFcbEx
0x140243ecb  mov     rax, [rsi+0B8h]
0x140243ed2  mov     rcx, [rax+148h]
0x140243ed9  mov     rcx, [rcx+88h]; Resource
0x140243ee0  call    cs:__imp_ExReleaseResourceLite
0x140243ee7  nop     dword ptr [rax+rax+00h]
0x140243eec  mov     rax, rdi
0x140243eef  mov     rbx, [rsp+78h+arg_10]
0x140243ef7  add     rsp, 50h
0x140243efb  pop     r15
0x140243efd  pop     r14
0x140243eff  pop     r12
0x140243f01  pop     rdi
0x140243f02  pop     rsi
0x140243f03  retn
0x1402b7cbf  push    rbx
0x1402b7cc1  push    rbp
0x1402b7cc2  sub     rsp, 38h
0x1402b7cc6  mov     rbp, rdx
0x1402b7cc9  test    cl, cl
0x1402b7ccb  jz      short loc_1402B7D13
0x1402b7ccd  mov     al, cs:NtfsStatusDebugFlags
0x1402b7cd3  mov     rbx, [rbp+38h]
0x1402b7cd7  test    rbx, rbx
0x1402b7cda  jz      short loc_1402B7D13
0x1402b7cdc  cmp     qword ptr [rbx+100h], 0
0x1402b7ce4  jz      short loc_1402B7CFC
0x1402b7ce6  xor     edx, edx; Tag
0x1402b7ce8  mov     rcx, [rbx+100h]; P
0x1402b7cef  call    cs:__imp_ExFreePoolWithTag
0x1402b7cf6  nop     dword ptr [rax+rax+00h]
0x1402b7cfb  nop
0x1402b7cfc  mov     rdx, rbx; Entry
0x1402b7cff  lea     rcx, TxfVscbLookasideList; Lookaside
0x1402b7d06  call    cs:__imp_ExFreeToLookasideListEx
0x1402b7d0d  nop     dword ptr [rax+rax+00h]
0x1402b7d12  nop
0x1402b7d13  xor     r8d, r8d
0x1402b7d16  mov     rbx, [rbp+88h]
0x1402b7d1d  mov     rdx, [rbx+0B8h]
0x1402b7d24  mov     rcx, [rbp+80h]
0x1402b7d2b  call    NtfsReleaseFcbEx
0x1402b7d30  mov     rax, [rbx+0B8h]
0x1402b7d37  mov     rcx, [rax+148h]
0x1402b7d3e  mov     rcx, [rcx+88h]; Resource
0x1402b7d45  call    cs:__imp_ExReleaseResourceLite
0x1402b7d4c  nop     dword ptr [rax+rax+00h]
0x1402b7d51  nop
0x1402b7d52  add     rsp, 38h
0x1402b7d56  pop     rbp
0x1402b7d57  pop     rbx
0x1402b7d58  retn
```
