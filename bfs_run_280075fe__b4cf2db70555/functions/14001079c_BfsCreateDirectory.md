# BfsCreateDirectory

- ea: `0x14001079c`
- end: `0x140010b28`
- name: `BfsCreateDirectory`
- size: `908`
- prototype: ``
- caller_count: `5`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1400061a0`
- `0x140006e14`
- `0x14001033c`
- `0x140010ffc`
- `0x140012478`

## callees

- `0x140001008`
- `0x14001079c`
- `0x1400116a0`
- `0x1400117fc`
- `0x140011b44`
- `0x140011d18`
- `0x140012198`
- `0x140012418`
- `0x140012b10`
- `0x140013730`
- `0x140013b40`

## import_xrefs

- `ntoskrnl!ExInitializePushLock` at `0x140010a3a`
- `ntoskrnl!ExInitializePushLock` at `0x140010a3a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001099d`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001099d`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400109c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010a80`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x1400109c9`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140010a80`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010814`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140010814`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010833`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x140010833`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010a68`
- `ntoskrnl!RtlInitializeGenericTableAvl` at `0x140010a68`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010af2`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010a28`
- `ntoskrnl!ExFreePoolWithTag` at `0x140010af2`
- `ntoskrnl!ExAllocatePool2` at `0x1400108bd`
- `ntoskrnl!ExAllocatePool2` at `0x1400108ec`
- `ntoskrnl!ExAllocatePool2` at `0x140010912`
- `ntoskrnl!ExAllocatePool2` at `0x1400108bd`
- `ntoskrnl!ExAllocatePool2` at `0x1400108ec`
- `ntoskrnl!ExAllocatePool2` at `0x140010912`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010803`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001098c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140010803`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001098c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001083f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400109d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a8c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001083f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400109d5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010a8c`

## pseudocode

```c
__int64 __fastcall BfsCreateDirectory(__int64 a1, const UNICODE_STRING *a2, int a3, PVOID **a4)
{
  __int64 result; // rax
  __int64 Entry; // rbx
  int v10; // r14d
  _QWORD *Pool2; // rax
  __int64 v12; // r8
  __int64 v13; // r9
  __int64 v14; // rbx
  __int64 v15; // rax
  _DWORD *v16; // rsi
  __int64 v17; // rax
  __int64 *v18; // rcx
  __int64 v19; // rcx
  int Block; // ebx
  PVOID *v21; // rsi
  int TableContext; // [rsp+20h] [rbp-E0h]
  unsigned __int8 v23[8]; // [rsp+30h] [rbp-D0h] BYREF
  PVOID *v24; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD v25[18]; // [rsp+40h] [rbp-C0h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v26; // [rsp+D0h] [rbp-30h] BYREF
  PVOID **v27; // [rsp+F0h] [rbp-10h]
  __int64 v28; // [rsp+F8h] [rbp-8h]

  memset(v25, 0, 0x88u);
  v23[0] = 0;
  result = BfsLocateDirectory(a1 + 24, a2, a4);
  if ( (int)result < 0 )
  {
    KeEnterCriticalRegion();
    ExAcquirePushLockSharedEx(a1, 0);
    Entry = BfsFindEntry(a1, a2);
    ExReleasePushLockSharedEx(a1, 0);
    KeLeaveCriticalRegion();
    if ( Entry )
    {
      if ( !*(_DWORD *)(Entry + 12) )
        return 3221225522LL;
    }
    else
    {
      if ( a3 == 1 )
        return 3221226021LL;
      if ( (a3 & 3) != 0 )
      {
        Entry = BfsInsertDirectoryEntry(a1, 2, 0, 0, (__int64)a2);
        if ( (unsigned int)Feature_AppSiloBfsInsertEntryValidityCheck__private_IsEnabledDeviceUsageNoInline() )
        {
          if ( !Entry )
            return 3221225495LL;
        }
      }
    }
    v10 = *(_DWORD *)(Entry + 12);
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
          goto LABEL_20;
        v10 = v16[1];
        if ( !v10 )
        {
          v25[1] = *(_QWORD *)(a1 + 8);
          v24 = (PVOID *)v25;
          KeEnterCriticalRegion();
          ExAcquirePushLockExclusiveEx(a1 + 24, 0);
          Block = BfsInsertDirectory(a1 + 24, a2, &v24, v23);
          if ( Block >= 0 )
          {
            v21 = v24;
            if ( v23[0] )
            {
              ExInitializePushLock((PULONG_PTR)v24 + 3);
              RtlInitializeGenericTableAvl(
                (PRTL_AVL_TABLE)(v21 + 4),
                (PRTL_AVL_COMPARE_ROUTINE)BfsCompareTableEntries,
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
LABEL_20:
          if ( (unsigned int)dword_140019000 <= 3 )
            goto LABEL_30;
          LODWORD(v24) = Block;
          v27 = &v24;
          goto LABEL_29;
        }
      }
    }
    v19 = 3221225495LL;
    Block = -1073741801;
    if ( (unsigned int)dword_140019000 > 3 )
    {
      v27 = &v24;
      LODWORD(v24) = -1073741801;
LABEL_29:
      v28 = 4;
      tlgWriteTransfer_EtwWriteTransfer(v19, (unsigned __int8 *)&byte_140016D91, v12, v13, TableContext, &v26);
    }
LABEL_30:
    BfsFreeDirectoryBlockList(v25[2]);
    ExFreePoolWithTag((PVOID)v25[2], 0);
    return (unsigned int)Block;
  }
  return result;
}

```

## disassembly

```asm
0x14001079c  mov     [rsp-8+arg_10], rbx
0x1400107a1  push    rbp
0x1400107a2  push    rsi
0x1400107a3  push    rdi
0x1400107a4  push    r12
0x1400107a6  push    r13
0x1400107a8  push    r14
0x1400107aa  push    r15
0x1400107ac  lea     rbp, [rsp-10h]
0x1400107b1  sub     rsp, 110h
0x1400107b8  mov     rax, cs:__security_cookie
0x1400107bf  xor     rax, rsp
0x1400107c2  mov     [rbp+40h+var_40], rax
0x1400107c6  mov     esi, r8d
0x1400107c9  mov     r12, rdx
0x1400107cc  mov     rdi, rcx
0x1400107cf  xor     edx, edx; Val
0x1400107d1  mov     r8d, 88h; Size
0x1400107d7  lea     rcx, [rsp+140h+var_100]; void *
0x1400107dc  mov     r13, r9
0x1400107df  call    memset
0x1400107e4  lea     r15, [rdi+18h]
0x1400107e8  mov     [rsp+140h+var_110], 0
0x1400107ed  mov     rcx, r15
0x1400107f0  mov     r8, r13
0x1400107f3  mov     rdx, r12
0x1400107f6  call    BfsLocateDirectory
0x1400107fb  test    eax, eax
0x1400107fd  jns     loc_140010B00
0x140010803  call    cs:__imp_KeEnterCriticalRegion
0x14001080a  nop     dword ptr [rax+rax+00h]
0x14001080f  xor     edx, edx
0x140010811  mov     rcx, rdi
0x140010814  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001081b  nop     dword ptr [rax+rax+00h]
0x140010820  mov     rdx, r12
0x140010823  mov     rcx, rdi
0x140010826  call    BfsFindEntry
0x14001082b  xor     edx, edx
0x14001082d  mov     rcx, rdi
0x140010830  mov     rbx, rax
0x140010833  call    cs:__imp_ExReleasePushLockSharedEx
0x14001083a  nop     dword ptr [rax+rax+00h]
0x14001083f  call    cs:__imp_KeLeaveCriticalRegion
0x140010846  nop     dword ptr [rax+rax+00h]
0x14001084b  test    rbx, rbx
0x14001084e  jnz     short loc_140010897
0x140010850  cmp     esi, 1
0x140010853  jnz     short loc_14001085F
0x140010855  mov     eax, 0C0000225h
0x14001085a  jmp     loc_140010B00
0x14001085f  test    sil, 3
0x140010863  jz      short loc_1400108A7
0x140010865  xor     r9d, r9d
0x140010868  mov     [rsp+140h+TableContext], r12
0x14001086d  xor     r8d, r8d
0x140010870  mov     rcx, rdi
0x140010873  lea     edx, [r9+2]
0x140010877  call    BfsInsertDirectoryEntry
0x14001087c  mov     rbx, rax
0x14001087f  call    Feature_AppSiloBfsInsertEntryValidityCheck__private_IsEnabledDeviceUsageNoInline
0x140010884  test    eax, eax
0x140010886  jz      short loc_1400108A7
0x140010888  test    rbx, rbx
0x14001088b  jnz     short loc_1400108A7
0x14001088d  mov     eax, 0C0000017h
0x140010892  jmp     loc_140010B00
0x140010897  cmp     dword ptr [rbx+0Ch], 0
0x14001089b  jnz     short loc_1400108A7
0x14001089d  mov     eax, 0C0000032h
0x1400108a2  jmp     loc_140010B00
0x1400108a7  mov     r14d, [rbx+0Ch]
0x1400108ab  mov     esi, 100h
0x1400108b0  mov     ecx, esi
0x1400108b2  mov     edx, 10h
0x1400108b7  mov     r8d, 48736642h
0x1400108bd  call    cs:__imp_ExAllocatePool2
0x1400108c4  nop     dword ptr [rax+rax+00h]
0x1400108c9  mov     [rsp+140h+P], rax
0x1400108ce  test    rax, rax
0x1400108d1  jz      loc_140010AA5
0x1400108d7  mov     [rax+8], rax
0x1400108db  mov     [rax], rax
0x1400108de  mov     edx, 20h ; ' '
0x1400108e3  mov     r8d, 4C736642h
0x1400108e9  mov     rcx, rsi
0x1400108ec  call    cs:__imp_ExAllocatePool2
0x1400108f3  nop     dword ptr [rax+rax+00h]
0x1400108f8  mov     rbx, rax
0x1400108fb  test    rax, rax
0x1400108fe  jz      loc_140010AA5
0x140010904  mov     edx, 4000h
0x140010909  mov     r8d, 62736642h
0x14001090f  mov     rcx, rsi
0x140010912  call    cs:__imp_ExAllocatePool2
0x140010919  nop     dword ptr [rax+rax+00h]
0x14001091e  mov     rsi, rax
0x140010921  test    rax, rax
0x140010924  jz      loc_140010AA5
0x14001092a  mov     [rbx+10h], rax
0x14001092e  mov     [rbx+18h], r14d
0x140010932  mov     rax, [rsp+140h+P]
0x140010937  mov     rcx, [rax+8]
0x14001093b  cmp     [rcx], rax
0x14001093e  jnz     loc_140010A9E
0x140010944  mov     [rbx], rax
0x140010947  mov     r8, rsi
0x14001094a  mov     [rbx+8], rcx
0x14001094e  mov     edx, r14d
0x140010951  mov     [rcx], rbx
0x140010954  mov     [rax+8], rbx
0x140010958  mov     rcx, [rdi+8]
0x14001095c  call    BfsReadBlock
0x140010961  mov     ebx, eax
0x140010963  test    eax, eax
0x140010965  js      short loc_1400109E1
0x140010967  mov     r14d, [rsi+4]
0x14001096b  mov     esi, 100h
0x140010970  test    r14d, r14d
0x140010973  jnz     loc_1400108DE
0x140010979  mov     rax, [rdi+8]
0x14001097d  mov     [rsp+140h+var_F8], rax
0x140010982  lea     rax, [rsp+140h+var_100]
0x140010987  mov     [rsp+140h+var_108], rax
0x14001098c  call    cs:__imp_KeEnterCriticalRegion
0x140010993  nop     dword ptr [rax+rax+00h]
0x140010998  xor     edx, edx
0x14001099a  mov     rcx, r15
0x14001099d  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x1400109a4  nop     dword ptr [rax+rax+00h]
0x1400109a9  lea     r9, [rsp+140h+var_110]
0x1400109ae  mov     rdx, r12
0x1400109b1  lea     r8, [rsp+140h+var_108]
0x1400109b6  mov     rcx, r15
0x1400109b9  call    BfsInsertDirectory
0x1400109be  mov     ebx, eax
0x1400109c0  test    eax, eax
0x1400109c2  jns     short loc_140010A0B
0x1400109c4  xor     edx, edx
0x1400109c6  mov     rcx, r15
0x1400109c9  call    cs:__imp_ExReleasePushLockExclusiveEx
0x1400109d0  nop     dword ptr [rax+rax+00h]
0x1400109d5  call    cs:__imp_KeLeaveCriticalRegion
0x1400109dc  nop     dword ptr [rax+rax+00h]
0x1400109e1  mov     eax, cs:dword_140019000
0x1400109e7  cmp     eax, 3
0x1400109ea  jbe     loc_140010AE1
0x1400109f0  lea     rax, [rsp+140h+var_108]
0x1400109f5  mov     dword ptr [rsp+140h+var_108], ebx
0x1400109f9  mov     [rbp+40h+var_50], rax
0x1400109fd  lea     rax, [rbp+40h+var_70]
0x140010a01  mov     [rsp+140h+var_118], rax
0x140010a06  jmp     loc_140010ACD
0x140010a0b  cmp     [rsp+140h+var_110], 0
0x140010a10  mov     rsi, [rsp+140h+var_108]
0x140010a15  jnz     short loc_140010A36
0x140010a17  mov     rcx, [rsp+140h+P]
0x140010a1c  call    BfsFreeDirectoryBlockList
0x140010a21  mov     rcx, [rsp+140h+P]; P
0x140010a26  xor     edx, edx; Tag
0x140010a28  call    cs:__imp_ExFreePoolWithTag
0x140010a2f  nop     dword ptr [rax+rax+00h]
0x140010a34  jmp     short loc_140010A7B
0x140010a36  lea     rcx, [rsi+18h]; PushLock
0x140010a3a  call    cs:__imp_ExInitializePushLock
0x140010a41  nop     dword ptr [rax+rax+00h]
0x140010a46  lea     rcx, [rsi+20h]; Table
0x140010a4a  mov     [rsp+140h+TableContext], 0; TableContext
0x140010a53  lea     r9, BfsFreeTableEntry; FreeRoutine
0x140010a5a  lea     r8, BfsAllocateTableEntry; AllocateRoutine
0x140010a61  lea     rdx, BfsCompareTableEntries; CompareRoutine
0x140010a68  call    cs:__imp_RtlInitializeGenericTableAvl
0x140010a6f  nop     dword ptr [rax+rax+00h]
0x140010a74  lock inc dword ptr [rdi+90h]
0x140010a7b  xor     edx, edx
0x140010a7d  mov     rcx, r15
0x140010a80  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140010a87  nop     dword ptr [rax+rax+00h]
0x140010a8c  call    cs:__imp_KeLeaveCriticalRegion
0x140010a93  nop     dword ptr [rax+rax+00h]
0x140010a98  mov     [r13+0], rsi
0x140010a9c  jmp     short loc_140010AFE
0x140010a9e  mov     ecx, 3
0x140010aa3  int     29h; Win8: RtlFailFast(ecx)
0x140010aa5  mov     eax, cs:dword_140019000
0x140010aab  mov     ecx, 0C0000017h; int
0x140010ab0  mov     ebx, ecx
0x140010ab2  cmp     eax, 3
0x140010ab5  jbe     short loc_140010AE1
0x140010ab7  lea     rax, [rsp+140h+var_108]
0x140010abc  mov     [rbp+40h+var_50], rax
0x140010ac0  lea     rax, [rbp+40h+var_70]
0x140010ac4  mov     [rsp+140h+var_118], rax; PEVENT_DATA_DESCRIPTOR
0x140010ac9  mov     dword ptr [rsp+140h+var_108], ecx
0x140010acd  lea     rdx, byte_140016D91; int
0x140010ad4  mov     [rbp+40h+var_48], 4
0x140010adc  call    _tlgWriteTransfer_EtwWriteTransfer
0x140010ae1  mov     rcx, [rsp+140h+P]
0x140010ae6  call    BfsFreeDirectoryBlockList
0x140010aeb  mov     rcx, [rsp+140h+P]; P
0x140010af0  xor     edx, edx; Tag
0x140010af2  call    cs:__imp_ExFreePoolWithTag
0x140010af9  nop     dword ptr [rax+rax+00h]
0x140010afe  mov     eax, ebx
0x140010b00  mov     rcx, [rbp+40h+var_40]
0x140010b04  xor     rcx, rsp; StackCookie
0x140010b07  call    __security_check_cookie
0x140010b0c  mov     rbx, [rsp+140h+arg_10]
0x140010b14  add     rsp, 110h
0x140010b1b  pop     r15
0x140010b1d  pop     r14
0x140010b1f  pop     r13
0x140010b21  pop     r12
0x140010b23  pop     rdi
0x140010b24  pop     rsi
0x140010b25  pop     rbp
0x140010b26  retn
```
