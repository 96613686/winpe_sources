# BfsCreateDirectory

- ea: `0x14001093c`
- end: `0x140010cbf`
- name: `BfsCreateDirectory`
- size: `899`
- prototype: `__int64 __fastcall(__int64, __int64, int, _QWORD *)`
- caller_count: `5`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x140006330`
- `0x140006fa4`
- `0x1400104ec`
- `0x140011194`
- `0x140012608`

## callees

- `0x140001008`
- `0x14001093c`
- `0x140011838`
- `0x140011994`
- `0x140011cd4`
- `0x140011ea8`
- `0x140012328`
- `0x1400125a8`
- `0x140013860`
- `0x140013c80`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140010bd1`
- `ntoskrnl!ExInitializePushLock` at `0x140010bd1`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010b34`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140010b34`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b60`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010c17`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010b60`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010c17`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400109b4`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x1400109b4`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400109d3`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400109d3`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010bff`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010bff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c89`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010bbf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010c89`
- `ntoskrnl!ExAllocatePool2` at `0x140010a54`
- `ntoskrnl!ExAllocatePool2` at `0x140010a83`
- `ntoskrnl!ExAllocatePool2` at `0x140010aa9`
- `ntoskrnl!ExAllocatePool2` at `0x140010a54`
- `ntoskrnl!ExAllocatePool2` at `0x140010a83`
- `ntoskrnl!ExAllocatePool2` at `0x140010aa9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400109a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010b23`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400109a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010b23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400109df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010b6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010c23`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400109df`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010b6c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010c23`

## pseudocode

```c
__int64 __fastcall BfsCreateDirectory(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  __int64 result; // rax
  _DWORD *Entry; // rbx
  int v10; // r14d
  _QWORD *Pool2; // rax
  int v12; // r8d
  int v13; // r9d
  __int64 v14; // rbx
  __int64 v15; // rax
  _DWORD *v16; // rsi
  __int64 v17; // rax
  __int64 *v18; // rcx
  int v19; // ecx
  NTSTATUS Block; // ebx
  _QWORD *v21; // rsi
  int TableContext; // [rsp+20h] [rbp-E0h]
  _BYTE v23[8]; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD *v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[18]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD *v27; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]

  memset(v25, 0, 0x88u);
  v23[0] = 0;
  result = BfsLocateDirectory(a1 + 24, a2, a4);
  if ( (int)result < 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(a1, 0);
    Entry = (_DWORD *)BfsFindEntry(a1, a2);
    ExReleasePushLockSharedEx(a1, 0);
    KeLeaveCriticalRegion();
    if ( Entry )
    {
      if ( !Entry[3] )
        return 3221225522LL;
    }
    else
    {
      if ( a3 == 1 )
        return 3221226021LL;
      if ( (a3 & 3) != 0 )
      {
        Entry = BfsInsertDirectoryEntry(a1, 2, 0, 0, a2);
        if ( !Entry )
          return 3221225495LL;
      }
    }
    v10 = Entry[3];
    Pool2 = (_QWORD *)ExAllocatePool2(256, 16, 1215522370);
    v25[2] = Pool2;
    if ( Pool2 )
    {
      Pool2[1] = Pool2;
      *Pool2 = Pool2;
      while ( 1 )
      {
        v14 = ExAllocatePool2(256, 32, 1282631234);
        if ( !v14 )
          break;
        v15 = ExAllocatePool2(256, 0x4000, 1651729986);
        v16 = (_DWORD *)v15;
        if ( !v15 )
          break;
        *(_QWORD *)(v14 + 16) = v15;
        *(_DWORD *)(v14 + 24) = v10;
        v17 = v25[2];
        v18 = *(__int64 **)(v25[2] + 8LL);
        if ( *v18 != v25[2] )
          __fastfail(3u);
        *(_QWORD *)v14 = v25[2];
        *(_QWORD *)(v14 + 8) = v18;
        *v18 = v14;
        *(_QWORD *)(v17 + 8) = v14;
        Block = BfsReadBlock(*(_QWORD *)(a1 + 8), v10, v16);
        if ( Block < 0 )
          goto LABEL_19;
        v10 = v16[1];
        if ( !v10 )
        {
          v25[1] = *(_QWORD *)(a1 + 8);
          v24 = v25;
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(a1 + 24, 0);
          Block = BfsInsertDirectory(a1 + 24, a2, &v24, v23);
          if ( Block >= 0 )
          {
            v21 = v24;
            if ( v23[0] )
            {
              ExInitializePushLock(v24 + 3);
              RtlInitializeGenericTableAvl(
                (PRTL_AVL_TABLE)(v21 + 4),
                BfsCompareTableEntries,
                BfsAllocateTableEntry,
                BfsFreeTableEntry,
                0);
              _InterlockedIncrement((volatile signed __int32 *)(a1 + 144));
            }
            else
            {
              BfsFreeDirectoryBlockList(v25[2]);
              ExFreePoolWithTag((PVOID)v25[2], 0);
            }
            ExReleasePushLockExclusiveEx(a1 + 24, 0);
            KeLeaveCriticalRegion();
            *a4 = v21;
            return (unsigned int)Block;
          }
          ExReleasePushLockExclusiveEx(a1 + 24, 0);
          KeLeaveCriticalRegion();
LABEL_19:
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_29;
          LODWORD(v24) = Block;
          v27 = &v24;
          goto LABEL_28;
        }
      }
    }
    v19 = -1073741801;
    Block = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v27 = &v24;
      LODWORD(v24) = -1073741801;
LABEL_28:
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v19, (int)&byte_140016D91, v12, v13, TableContext, &v26);
    }
LABEL_29:
    BfsFreeDirectoryBlockList(v25[2]);
    ExFreePoolWithTag((PVOID)v25[2], 0);
    return (unsigned int)Block;
  }
  return result;
}

```

## disassembly

```asm
0x14001093c  mov     [rsp-8+arg_10], rbx
0x140010941  push    rbp
0x140010942  push    rsi
0x140010943  push    rdi
0x140010944  push    r12
0x140010946  push    r13
0x140010948  push    r14
0x14001094a  push    r15
0x14001094c  lea     rbp, [rsp-10h]
0x140010951  sub     rsp, 110h
0x140010958  mov     rax, cs:__security_cookie
0x14001095f  xor     rax, rsp
0x140010962  mov     [rbp+40h+var_40], rax
0x140010966  mov     esi, r8d
0x140010969  mov     r12, rdx
0x14001096c  mov     rdi, rcx
0x14001096f  xor     edx, edx; Val
0x140010971  mov     r8d, 88h; Size
0x140010977  lea     rcx, [rsp+140h+var_100]; void *
0x14001097c  mov     r13, r9
0x14001097f  call    memset
0x140010984  lea     r15, [rdi+18h]
0x140010988  mov     [rsp+140h+var_110], 0
0x14001098d  mov     rcx, r15
0x140010990  mov     r8, r13
0x140010993  mov     rdx, r12
0x140010996  call    BfsLocateDirectory
0x14001099b  test    eax, eax
0x14001099d  jns     loc_140010C97
0x1400109a3  call    cs:__imp_KeEnterCriticalRegion
0x1400109aa  nop     dword ptr [rax+rax+00h]
0x1400109af  xor     edx, edx
0x1400109b1  mov     rcx, rdi
0x1400109b4  call    cs:__imp_ExAcquirePushLockSharedEx
0x1400109bb  nop     dword ptr [rax+rax+00h]
0x1400109c0  mov     rdx, r12
0x1400109c3  mov     rcx, rdi
0x1400109c6  call    BfsFindEntry
0x1400109cb  xor     edx, edx
0x1400109cd  mov     rcx, rdi
0x1400109d0  mov     rbx, rax
0x1400109d3  call    cs:__imp_ExReleasePushLockSharedEx
0x1400109da  nop     dword ptr [rax+rax+00h]
0x1400109df  call    cs:__imp_KeLeaveCriticalRegion
0x1400109e6  nop     dword ptr [rax+rax+00h]
0x1400109eb  test    rbx, rbx
0x1400109ee  jnz     short loc_140010A2E
0x1400109f0  cmp     esi, 1
0x1400109f3  jnz     short loc_1400109FF
0x1400109f5  mov     eax, 0C0000225h
0x1400109fa  jmp     loc_140010C97
0x1400109ff  test    sil, 3
0x140010a03  jz      short loc_140010A3E
0x140010a05  xor     r9d, r9d
0x140010a08  mov     [rsp+140h+TableContext], r12
0x140010a0d  xor     r8d, r8d
0x140010a10  mov     rcx, rdi
0x140010a13  lea     edx, [r9+2]
0x140010a17  call    BfsInsertDirectoryEntry
0x140010a1c  mov     rbx, rax
0x140010a1f  test    rax, rax
0x140010a22  jnz     short loc_140010A3E
0x140010a24  mov     eax, 0C0000017h
0x140010a29  jmp     loc_140010C97
0x140010a2e  cmp     dword ptr [rbx+0Ch], 0
0x140010a32  jnz     short loc_140010A3E
0x140010a34  mov     eax, 0C0000032h
0x140010a39  jmp     loc_140010C97
0x140010a3e  mov     r14d, [rbx+0Ch]
0x140010a42  mov     esi, 100h
0x140010a47  mov     ecx, esi
0x140010a49  mov     edx, 10h
0x140010a4e  mov     r8d, 48736642h
0x140010a54  call    cs:__imp_ExAllocatePool2
0x140010a5b  nop     dword ptr [rax+rax+00h]
0x140010a60  mov     [rsp+140h+P], rax
0x140010a65  test    rax, rax
0x140010a68  jz      loc_140010C3C
0x140010a6e  mov     [rax+8], rax
0x140010a72  mov     [rax], rax
0x140010a75  mov     edx, 20h ; ' '
0x140010a7a  mov     r8d, 4C736642h
0x140010a80  mov     rcx, rsi
0x140010a83  call    cs:__imp_ExAllocatePool2
0x140010a8a  nop     dword ptr [rax+rax+00h]
0x140010a8f  mov     rbx, rax
0x140010a92  test    rax, rax
0x140010a95  jz      loc_140010C3C
0x140010a9b  mov     edx, 4000h
0x140010aa0  mov     r8d, 62736642h
0x140010aa6  mov     rcx, rsi
0x140010aa9  call    cs:__imp_ExAllocatePool2
0x140010ab0  nop     dword ptr [rax+rax+00h]
0x140010ab5  mov     rsi, rax
0x140010ab8  test    rax, rax
0x140010abb  jz      loc_140010C3C
0x140010ac1  mov     [rbx+10h], rax
0x140010ac5  mov     [rbx+18h], r14d
0x140010ac9  mov     rax, [rsp+140h+P]
0x140010ace  mov     rcx, [rax+8]
0x140010ad2  cmp     [rcx], rax
0x140010ad5  jnz     loc_140010C35
0x140010adb  mov     [rbx], rax
0x140010ade  mov     r8, rsi
0x140010ae1  mov     [rbx+8], rcx
0x140010ae5  mov     edx, r14d
0x140010ae8  mov     [rcx], rbx
0x140010aeb  mov     [rax+8], rbx
0x140010aef  mov     rcx, [rdi+8]
0x140010af3  call    BfsReadBlock
0x140010af8  mov     ebx, eax
0x140010afa  test    eax, eax
0x140010afc  js      short loc_140010B78
0x140010afe  mov     r14d, [rsi+4]
0x140010b02  mov     esi, 100h
0x140010b07  test    r14d, r14d
0x140010b0a  jnz     loc_140010A75
0x140010b10  mov     rax, [rdi+8]
0x140010b14  mov     [rsp+140h+var_F8], rax
0x140010b19  lea     rax, [rsp+140h+var_100]
0x140010b1e  mov     [rsp+140h+var_108], rax
0x140010b23  call    cs:__imp_KeEnterCriticalRegion
0x140010b2a  nop     dword ptr [rax+rax+00h]
0x140010b2f  xor     edx, edx
0x140010b31  mov     rcx, r15
0x140010b34  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140010b3b  nop     dword ptr [rax+rax+00h]
0x140010b40  lea     r9, [rsp+140h+var_110]
0x140010b45  mov     rdx, r12
0x140010b48  lea     r8, [rsp+140h+var_108]
0x140010b4d  mov     rcx, r15
0x140010b50  call    BfsInsertDirectory
0x140010b55  mov     ebx, eax
0x140010b57  test    eax, eax
0x140010b59  jns     short loc_140010BA2
0x140010b5b  xor     edx, edx
0x140010b5d  mov     rcx, r15
0x140010b60  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010b67  nop     dword ptr [rax+rax+00h]
0x140010b6c  call    cs:__imp_KeLeaveCriticalRegion
0x140010b73  nop     dword ptr [rax+rax+00h]
0x140010b78  mov     eax, cs:dword_140019000
0x140010b7e  cmp     eax, 3
0x140010b81  jbe     loc_140010C78
0x140010b87  lea     rax, [rsp+140h+var_108]
0x140010b8c  mov     dword ptr [rsp+140h+var_108], ebx
0x140010b90  mov     [rbp+40h+var_50], rax
0x140010b94  lea     rax, [rbp+40h+var_70]
0x140010b98  mov     [rsp+140h+var_118], rax
0x140010b9d  jmp     loc_140010C64
0x140010ba2  cmp     [rsp+140h+var_110], 0
0x140010ba7  mov     rsi, [rsp+140h+var_108]
0x140010bac  jnz     short loc_140010BCD
0x140010bae  mov     rcx, [rsp+140h+P]
0x140010bb3  call    BfsFreeDirectoryBlockList
0x140010bb8  mov     rcx, [rsp+140h+P]; P
0x140010bbd  xor     edx, edx; Tag
0x140010bbf  call    cs:__imp_ExFreePoolWithTag
0x140010bc6  nop     dword ptr [rax+rax+00h]
0x140010bcb  jmp     short loc_140010C12
0x140010bcd  lea     rcx, [rsi+18h]; PushLock
0x140010bd1  call    cs:__imp_ExInitializePushLock
0x140010bd8  nop     dword ptr [rax+rax+00h]
0x140010bdd  lea     rcx, [rsi+20h]; Table
0x140010be1  mov     [rsp+140h+TableContext], 0; TableContext
0x140010bea  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140010bf1  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x140010bf8  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140010bff  call    cs:__imp_RtlInitializeGenericTableAvl
0x140010c06  nop     dword ptr [rax+rax+00h]
0x140010c0b  lock inc dword ptr [rdi+90h]
0x140010c12  xor     edx, edx
0x140010c14  mov     rcx, r15
0x140010c17  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010c1e  nop     dword ptr [rax+rax+00h]
0x140010c23  call    cs:__imp_KeLeaveCriticalRegion
0x140010c2a  nop     dword ptr [rax+rax+00h]
0x140010c2f  mov     [r13+0], rsi
0x140010c33  jmp     short loc_140010C95
0x140010c35  mov     ecx, 3
0x140010c3a  int     29h; Win8: RtlFailFast(ecx)
0x140010c3c  mov     eax, cs:dword_140019000
0x140010c42  mov     ecx, 0C0000017h; int
0x140010c47  mov     ebx, ecx
0x140010c49  cmp     eax, 3
0x140010c4c  jbe     short loc_140010C78
0x140010c4e  lea     rax, [rsp+140h+var_108]
0x140010c53  mov     [rbp+40h+var_50], rax
0x140010c57  lea     rax, [rbp+40h+var_70]
0x140010c5b  mov     [rsp+140h+var_118], rax; PEVENT_DATA_DESCRIPTOR
0x140010c60  mov     dword ptr [rsp+140h+var_108], ecx
0x140010c64  lea     rdx, byte_140016D91; int
0x140010c6b  mov     [rbp+40h+var_48], 4
0x140010c73  call    _tlgWriteTransfer_EtwWriteTransfer
0x140010c78  mov     rcx, [rsp+140h+P]
0x140010c7d  call    BfsFreeDirectoryBlockList
0x140010c82  mov     rcx, [rsp+140h+P]; P
0x140010c87  xor     edx, edx; Tag
0x140010c89  call    cs:__imp_ExFreePoolWithTag
0x140010c90  nop     dword ptr [rax+rax+00h]
0x140010c95  mov     eax, ebx
0x140010c97  mov     rcx, [rbp+40h+var_40]
0x140010c9b  xor     rcx, rsp; StackCookie
0x140010c9e  call    __security_check_cookie
0x140010ca3  mov     rbx, [rsp+140h+arg_10]
0x140010cab  add     rsp, 110h
0x140010cb2  pop     r15
0x140010cb4  pop     r14
0x140010cb6  pop     r13
0x140010cb8  pop     r12
0x140010cba  pop     rdi
0x140010cbb  pop     rsi
0x140010cbc  pop     rbp
0x140010cbd  retn
```
