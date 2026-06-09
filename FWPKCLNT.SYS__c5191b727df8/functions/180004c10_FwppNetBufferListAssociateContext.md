# FwppNetBufferListAssociateContext

- ea: `0x180004c10`
- end: `0x180005059`
- name: `FwppNetBufferListAssociateContext`
- size: `1097`
- prototype: `__int64 __fastcall(int, int, int, int, __int64, __int64, PVOID Object, __int64, __int64)`
- caller_count: `3`
- callee_count: `12`
- tags: `authz_impersonation`

## callers

- `0x180004ab0`
- `0x180004b50`
- `0x18001c810`

## callees

- `0x180004904`
- `0x180004c10`
- `0x180005060`
- `0x1800063b0`
- `0x180006a1c`
- `0x180006ce0`
- `0x180006e74`
- `0x180006f60`
- `0x1800077e0`
- `0x180008aac`
- `0x18000c9b4`
- `0x1800208c0`

## import_xrefs

- `ntoskrnl!KeInitializeSpinLock` at `0x180004db8`
- `ntoskrnl!KeInitializeSpinLock` at `0x180004db8`
- `ntoskrnl!MmBadPointer` at `0x180004c58`
- `ntoskrnl!MmBadPointer` at `0x180004e9d`
- `ntoskrnl!MmBadPointer` at `0x180004ed3`
- `ntoskrnl!ObfReferenceObject` at `0x180004d37`
- `ntoskrnl!ObfReferenceObject` at `0x180004e1d`
- `ntoskrnl!ObfReferenceObject` at `0x180004d37`
- `ntoskrnl!ObfReferenceObject` at `0x180004e1d`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180004d73`
- `ntoskrnl!ExAllocateFromNPagedLookasideList` at `0x180004d73`
- `NETIO!WfpPacketTagCountIncrement` at `0x180004d4a`
- `NETIO!WfpPacketTagCountIncrement` at `0x180004d4a`
- `NETIO!WfpNblInfoGet` at `0x180004c40`
- `NETIO!WfpNblInfoGet` at `0x180004c7c`
- `NETIO!WfpNblInfoGet` at `0x180004c40`
- `NETIO!WfpNblInfoGet` at `0x180004c7c`
- `NETIO!WfpNblInfoAlloc` at `0x180004c65`
- `NETIO!WfpNblInfoAlloc` at `0x180004c65`

## string_xrefs

- `0x18000500b`: `ExAllocateFromNPagedLookasideList`
- `0x180005023`: `WfpAllocFromNPagedLookasideList`

## pseudocode

```c
__int64 __fastcall FwppNetBufferListAssociateContext(
        int a1,
        __int64 a2,
        __int16 a3,
        __int64 a4,
        unsigned __int64 a5,
        _OWORD *a6,
        PVOID Object,
        __int64 a8,
        __int64 a9)
{
  PVOID v13; // rax
  PVOID v14; // rdx
  PVOID v15; // rbx
  PVOID v16; // rcx
  __int64 v17; // rax
  PVOID v18; // r8
  _DWORD *v19; // rdi
  unsigned __int64 v20; // rsi
  __int64 v21; // rax
  char *v22; // rbx
  _OWORD *v23; // rax
  PVOID v24; // rcx
  __int64 v26; // rdi
  __int64 v27; // rcx
  char *v28; // rbx
  _OWORD *v29; // rax
  PVOID v30; // rcx
  __int64 TaggedContextList; // rax
  __int64 v32; // r14
  __int64 v33; // r14
  _QWORD *v34; // rcx
  __int64 v35; // rax
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-68h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v13 = (PVOID)WfpNblInfoGet(a2);
  v15 = v13;
  if ( !v13 || (v18 = MmBadPointer, v19 = v13, v13 == MmBadPointer) )
  {
    if ( (int)WfpNblInfoAlloc(a2) < 0 )
      goto LABEL_34;
    v17 = WfpNblInfoGet(a2);
    v19 = (_DWORD *)v17;
    if ( v15 == MmBadPointer )
    {
      v16 = MmBadPointer;
      v14 = MmBadPointer;
      *(_QWORD *)(v17 + 8) = MmBadPointer;
    }
    if ( !v17 )
    {
LABEL_34:
      v26 = WfpReportSysErrorAsNtStatus((__int64)v16, (int)"FwppGetOrAllocNblInfoContainer", -1073741801);
LABEL_32:
      if ( !v26 )
        return v26;
LABEL_44:
      WfpReportError(v26, (int)"FwppNetBufferListAssociateContext");
      return v26;
    }
  }
  v20 = a5;
  if ( ((a5 - 1) & 0xFFFFFFFFFFFEFFFCuLL) != 0
    || (a5 > 4 ? (v21 = (unsigned int)(a5 - 65533)) : (v21 = (unsigned int)(a5 - 1)),
        (v22 = (char *)&v19[16 * v21 + 12 + 2 * v21]) == 0) )
  {
    v26 = 0;
    v28 = (char *)ExAllocateFromNPagedLookasideList(&stru_180048580);
    if ( !v28 )
    {
      v35 = WfpReportSysErrorAsNtStatus(v27, (int)"ExAllocateFromNPagedLookasideList", -1073741801);
      v26 = v35;
      if ( v35 )
      {
        WfpReportError(v35, (int)"WfpAllocFromNPagedLookasideList");
        goto LABEL_44;
      }
    }
    memset(v28, 0, 0xC0u);
    *((_DWORD *)v28 + 18) = 2;
    *((_QWORD *)v28 + 11) = FwppTaggedContextCleanupRoutine;
    *((_DWORD *)v28 + 19) = 1;
    KeInitializeSpinLock((PKSPIN_LOCK)v28 + 15);
    *((_QWORD *)v28 + 6) = a8;
    *((_QWORD *)v28 + 7) = a9;
    v29 = a6;
    *((_QWORD *)v28 + 22) = a2;
    *((_WORD *)v28 + 1) = a3;
    *((_QWORD *)v28 + 1) = a4;
    *((_QWORD *)v28 + 2) = v20;
    *((_DWORD *)v28 + 16) = a1;
    if ( v29 )
      *(_OWORD *)(v28 + 24) = *v29;
    v30 = Object;
    if ( Object )
    {
      *((_QWORD *)v28 + 5) = Object;
      ObfReferenceObject(v30);
    }
    else
    {
      *((_QWORD *)v28 + 5) = 0;
    }
    TaggedContextList = FwppGetTaggedContextList(a2);
    v32 = TaggedContextList;
    if ( TaggedContextList )
    {
      if ( !(unsigned int)FwppCheckAndRemoveDuplicatedContext(v20, TaggedContextList, a2)
        || (v32 = FwppGetTaggedContextList(a2)) != 0 )
      {
        WfpAcquireSpinLock(&SpinLock, &LockHandle);
        WfpObjectInsert(v28 + 72, &unk_180048680, &a5);
        if ( v28 != (char *)v32 )
        {
          v33 = v32 + 128;
          v34 = *(_QWORD **)(v33 + 8);
          if ( *v34 != v33 )
            __fastfail(3u);
          *((_QWORD *)v28 + 16) = v33;
          *((_QWORD *)v28 + 17) = v34;
          *v34 = v28 + 128;
          *(_QWORD *)(v33 + 8) = v28 + 128;
        }
        goto LABEL_31;
      }
      v26 = FwppSetTaggedContextList(a2, v28);
      if ( !v26 )
      {
LABEL_24:
        *((_QWORD *)v28 + 17) = v28 + 128;
        *((_QWORD *)v28 + 16) = v28 + 128;
        WfpAcquireSpinLock(&SpinLock, &LockHandle);
        WfpObjectInsert(v28 + 72, &unk_180048680, &a5);
LABEL_31:
        _InterlockedIncrement((volatile signed __int32 *)v28 + 19);
        WfpObjectManagerUnlock(&unk_180048680, &LockHandle);
        goto LABEL_32;
      }
    }
    else
    {
      v26 = FwppSetTaggedContextList(a2, v28);
      if ( !v26 )
        goto LABEL_24;
    }
    if ( !v28 )
      goto LABEL_44;
    WfpObjectDereference(v28 + 72);
    goto LABEL_32;
  }
  if ( v22[1] )
    FwppRemoveDuplicatedFastContext(v19, &v19[16 * v21 + 12 + 2 * v21], a2);
  *((_QWORD *)v22 + 6) = a8;
  *((_QWORD *)v22 + 7) = a9;
  v23 = a6;
  *((_WORD *)v22 + 1) = a3;
  *((_QWORD *)v22 + 1) = a4;
  *((_QWORD *)v22 + 2) = v20;
  *((_DWORD *)v22 + 16) = a1;
  if ( v23 )
    *(_OWORD *)(v22 + 24) = *v23;
  v24 = Object;
  if ( Object )
  {
    *((_QWORD *)v22 + 5) = Object;
    ObfReferenceObject(v24);
  }
  else
  {
    *((_QWORD *)v22 + 5) = 0;
  }
  v22[1] = 1;
  ++v19[10];
  WfpPacketTagCountIncrement(v24, v14, v18);
  return 0;
}

```

## disassembly

```asm
0x180004c10  push    rbx
0x180004c12  push    rbp
0x180004c13  push    rsi
0x180004c14  push    rdi
0x180004c15  push    r12
0x180004c17  push    r13
0x180004c19  push    r14
0x180004c1b  push    r15
0x180004c1d  sub     rsp, 48h
0x180004c21  mov     r12d, ecx
0x180004c24  xorps   xmm0, xmm0
0x180004c27  xor     eax, eax
0x180004c29  mov     rcx, rdx
0x180004c2c  movups  xmmword ptr [rsp+88h+LockHandle.LockQueue.Next], xmm0
0x180004c31  mov     qword ptr [rsp+88h+LockHandle.OldIrql], rax
0x180004c36  mov     r14, r9
0x180004c39  movzx   r15d, r8w
0x180004c3d  mov     rbp, rdx
0x180004c40  call    cs:__imp_WfpNblInfoGet
0x180004c47  nop     dword ptr [rax+rax+00h]
0x180004c4c  mov     rbx, rax
0x180004c4f  test    rax, rax
0x180004c52  jnz     loc_180004E9D
0x180004c58  mov     rcx, cs:MmBadPointer
0x180004c5f  mov     rsi, [rcx]
0x180004c62  mov     rcx, rbp
0x180004c65  call    cs:__imp_WfpNblInfoAlloc
0x180004c6c  nop     dword ptr [rax+rax+00h]
0x180004c71  test    eax, eax
0x180004c73  js      loc_180004F50
0x180004c79  mov     rcx, rbp
0x180004c7c  call    cs:__imp_WfpNblInfoGet
0x180004c83  nop     dword ptr [rax+rax+00h]
0x180004c88  mov     rdi, rax
0x180004c8b  cmp     rbx, rsi
0x180004c8e  jz      loc_180004ED3
0x180004c94  test    rax, rax
0x180004c97  jz      loc_180004F50
0x180004c9d  mov     rsi, [rsp+88h+arg_20]
0x180004ca5  lea     rcx, [rsi-1]
0x180004ca9  test    rcx, 0FFFFFFFFFFFEFFFCh
0x180004cb0  jnz     loc_180004D6A
0x180004cb6  cmp     rsi, 4
0x180004cba  ja      loc_180004EC8
0x180004cc0  lea     eax, [rsi-1]
0x180004cc3  lea     rbx, ds:6[rax*8]
0x180004ccb  add     rbx, rax
0x180004cce  lea     rbx, [rdi+rbx*8]
0x180004cd2  test    rbx, rbx
0x180004cd5  jz      loc_180004D6A
0x180004cdb  cmp     byte ptr [rbx+1], 0
0x180004cdf  jnz     loc_180004EB5
0x180004ce5  mov     rax, [rsp+88h+arg_38]
0x180004ced  mov     [rbx+30h], rax
0x180004cf1  mov     rax, [rsp+88h+arg_40]
0x180004cf9  mov     [rbx+38h], rax
0x180004cfd  mov     rax, [rsp+88h+arg_28]
0x180004d05  mov     [rbx+2], r15w
0x180004d0a  mov     [rbx+8], r14
0x180004d0e  mov     [rbx+10h], rsi
0x180004d12  mov     [rbx+40h], r12d
0x180004d16  test    rax, rax
0x180004d19  jz      short loc_180004D22
0x180004d1b  movups  xmm0, xmmword ptr [rax]
0x180004d1e  movups  xmmword ptr [rbx+18h], xmm0
0x180004d22  mov     rcx, [rsp+88h+Object]; Object
0x180004d2a  test    rcx, rcx
0x180004d2d  jz      loc_180004E90
0x180004d33  mov     [rbx+28h], rcx
0x180004d37  call    cs:__imp_ObfReferenceObject
0x180004d3e  nop     dword ptr [rax+rax+00h]
0x180004d43  mov     byte ptr [rbx+1], 1
0x180004d47  inc     dword ptr [rdi+28h]
0x180004d4a  call    cs:__imp_WfpPacketTagCountIncrement
0x180004d51  nop     dword ptr [rax+rax+00h]
0x180004d56  xor     eax, eax
0x180004d58  add     rsp, 48h
0x180004d5c  pop     r15
0x180004d5e  pop     r14
0x180004d60  pop     r13
0x180004d62  pop     r12
0x180004d64  pop     rdi
0x180004d65  pop     rsi
0x180004d66  pop     rbp
0x180004d67  pop     rbx
0x180004d68  retn
0x180004d6a  lea     rcx, stru_180048580; Lookaside
0x180004d71  xor     edi, edi
0x180004d73  call    cs:__imp_ExAllocateFromNPagedLookasideList
0x180004d7a  nop     dword ptr [rax+rax+00h]
0x180004d7f  mov     rbx, rax
0x180004d82  test    rax, rax
0x180004d85  jz      loc_180005005
0x180004d8b  xor     edx, edx; Val
0x180004d8d  mov     r8d, 0C0h; Size
0x180004d93  mov     rcx, rbx; void *
0x180004d96  call    memset
0x180004d9b  lea     rax, FwppTaggedContextCleanupRoutine
0x180004da2  mov     dword ptr [rbx+48h], 2
0x180004da9  lea     rcx, [rbx+78h]; SpinLock
0x180004dad  mov     [rbx+58h], rax
0x180004db1  mov     dword ptr [rbx+4Ch], 1
0x180004db8  call    cs:__imp_KeInitializeSpinLock
0x180004dbf  nop     dword ptr [rax+rax+00h]
0x180004dc4  mov     rax, [rsp+88h+arg_38]
0x180004dcc  mov     [rbx+30h], rax
0x180004dd0  mov     rax, [rsp+88h+arg_40]
0x180004dd8  mov     [rbx+38h], rax
0x180004ddc  mov     rax, [rsp+88h+arg_28]
0x180004de4  mov     [rbx+0B0h], rbp
0x180004deb  mov     [rbx+2], r15w
0x180004df0  mov     [rbx+8], r14
0x180004df4  mov     [rbx+10h], rsi
0x180004df8  mov     [rbx+40h], r12d
0x180004dfc  test    rax, rax
0x180004dff  jz      short loc_180004E08
0x180004e01  movups  xmm0, xmmword ptr [rax]
0x180004e04  movups  xmmword ptr [rbx+18h], xmm0
0x180004e08  mov     rcx, [rsp+88h+Object]; Object
0x180004e10  test    rcx, rcx
0x180004e13  jz      loc_180004FCA
0x180004e19  mov     [rbx+28h], rcx
0x180004e1d  call    cs:__imp_ObfReferenceObject
0x180004e24  nop     dword ptr [rax+rax+00h]
0x180004e29  mov     rcx, rbp
0x180004e2c  call    FwppGetTaggedContextList
0x180004e31  mov     r14, rax
0x180004e34  test    rax, rax
0x180004e37  jnz     loc_180004EE6
0x180004e3d  mov     rdx, rbx
0x180004e40  mov     rcx, rbp
0x180004e43  call    FwppSetTaggedContextList
0x180004e48  mov     rdi, rax
0x180004e4b  test    rax, rax
0x180004e4e  jnz     loc_180005046
0x180004e54  lea     rcx, [rbx+80h]
0x180004e5b  mov     [rcx+8], rcx
0x180004e5f  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x180004e64  mov     [rcx], rcx
0x180004e67  lea     rcx, SpinLock; SpinLock
0x180004e6e  call    WfpAcquireSpinLock
0x180004e73  lea     r8, [rsp+88h+arg_20]
0x180004e7b  lea     rdx, unk_180048680
0x180004e82  lea     rcx, [rbx+48h]
0x180004e86  call    WfpObjectInsert
0x180004e8b  jmp     loc_180004F2A
0x180004e90  mov     qword ptr [rbx+28h], 0
0x180004e98  jmp     loc_180004D43
0x180004e9d  mov     r8, cs:MmBadPointer
0x180004ea4  mov     rdi, rbx
0x180004ea7  cmp     rbx, [r8]
0x180004eaa  jz      loc_180004C58
0x180004eb0  jmp     loc_180004C9D
0x180004eb5  mov     r8, rbp
0x180004eb8  mov     rdx, rbx
0x180004ebb  mov     rcx, rdi
0x180004ebe  call    FwppRemoveDuplicatedFastContext
0x180004ec3  jmp     loc_180004CE5
0x180004ec8  lea     eax, [rsi-0FFFDh]
0x180004ece  jmp     loc_180004CC3
0x180004ed3  mov     rcx, cs:MmBadPointer
0x180004eda  mov     rdx, [rcx]
0x180004edd  mov     [rax+8], rdx
0x180004ee1  jmp     loc_180004C94
0x180004ee6  mov     r8, rbp
0x180004ee9  mov     rdx, rax
0x180004eec  mov     rcx, rsi
0x180004eef  call    FwppCheckAndRemoveDuplicatedContext
0x180004ef4  test    eax, eax
0x180004ef6  jnz     short loc_180004F67
0x180004ef8  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x180004efd  lea     rcx, SpinLock; SpinLock
0x180004f04  call    WfpAcquireSpinLock
0x180004f09  lea     r8, [rsp+88h+arg_20]
0x180004f11  lea     rdx, unk_180048680
0x180004f18  lea     rcx, [rbx+48h]
0x180004f1c  call    WfpObjectInsert
0x180004f21  cmp     rbx, r14
0x180004f24  jnz     loc_180004FD7
0x180004f2a  lock inc dword ptr [rbx+4Ch]
0x180004f2e  lea     rdx, [rsp+88h+LockHandle]
0x180004f33  lea     rcx, unk_180048680
0x180004f3a  call    WfpObjectManagerUnlock
0x180004f3f  test    rdi, rdi
0x180004f42  jnz     loc_180005032
0x180004f48  mov     rax, rdi
0x180004f4b  jmp     loc_180004D58
0x180004f50  mov     r8d, 0C0000017h
0x180004f56  lea     rdx, aFwppgetoralloc; "FwppGetOrAllocNblInfoContainer"
0x180004f5d  call    WfpReportSysErrorAsNtStatus
0x180004f62  mov     rdi, rax
0x180004f65  jmp     short loc_180004F3F
0x180004f67  mov     rcx, rbp
0x180004f6a  call    FwppGetTaggedContextList
0x180004f6f  mov     r14, rax
0x180004f72  test    rax, rax
0x180004f75  jnz     short loc_180004EF8
0x180004f77  mov     rdx, rbx
0x180004f7a  mov     rcx, rbp
0x180004f7d  call    FwppSetTaggedContextList
0x180004f82  mov     rdi, rax
0x180004f85  test    rax, rax
0x180004f88  jnz     loc_180005046
0x180004f8e  lea     rax, [rbx+80h]
0x180004f95  lea     rdx, [rsp+88h+LockHandle]; LockHandle
0x180004f9a  mov     [rax+8], rax
0x180004f9e  lea     rcx, SpinLock; SpinLock
0x180004fa5  mov     [rax], rax
0x180004fa8  call    WfpAcquireSpinLock
0x180004fad  lea     r8, [rsp+88h+arg_20]
0x180004fb5  lea     rdx, unk_180048680
0x180004fbc  lea     rcx, [rbx+48h]
0x180004fc0  call    WfpObjectInsert
0x180004fc5  jmp     loc_180004F2A
0x180004fca  mov     qword ptr [rbx+28h], 0
0x180004fd2  jmp     loc_180004E29
0x180004fd7  sub     r14, 0FFFFFFFFFFFFFF80h
0x180004fdb  mov     rcx, [r14+8]
0x180004fdf  cmp     [rcx], r14
0x180004fe2  jz      short loc_180004FEB
0x180004fe4  mov     ecx, 3
0x180004fe9  int     29h; Win8: RtlFailFast(ecx)
0x180004feb  lea     rax, [rbx+80h]
0x180004ff2  mov     [rax], r14
0x180004ff5  mov     [rax+8], rcx
0x180004ff9  mov     [rcx], rax
0x180004ffc  mov     [r14+8], rax
0x180005000  jmp     loc_180004F2A
0x180005005  mov     r8d, 0C0000017h
0x18000500b  lea     rdx, aExallocatefrom; "ExAllocateFromNPagedLookasideList"
0x180005012  call    WfpReportSysErrorAsNtStatus
0x180005017  mov     rdi, rax
0x18000501a  test    rax, rax
0x18000501d  jz      loc_180004D8B
0x180005023  lea     rdx, aWfpallocfromnp; "WfpAllocFromNPagedLookasideList"
0x18000502a  mov     rcx, rax
0x18000502d  call    WfpReportError
0x180005032  lea     rdx, aFwppnetbufferl; "FwppNetBufferListAssociateContext"
0x180005039  mov     rcx, rdi
0x18000503c  call    WfpReportError
0x180005041  jmp     loc_180004F48
0x180005046  test    rbx, rbx
0x180005049  jz      short loc_180005032
0x18000504b  lea     rcx, [rbx+48h]
0x18000504f  call    WfpObjectDereference
0x180005054  jmp     loc_180004F3F
```
