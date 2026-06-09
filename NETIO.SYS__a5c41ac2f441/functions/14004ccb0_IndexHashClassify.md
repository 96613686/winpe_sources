# IndexHashClassify

- ea: `0x14004ccb0`
- end: `0x14004ced9`
- name: `IndexHashClassify`
- size: `553`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64 *, _QWORD *)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x140001530`
- `0x140002ed0`
- `0x140004bf0`
- `0x140008130`
- `0x14001d460`
- `0x14004ccb0`
- `0x14004efd4`

## import_xrefs

- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14004cde7`
- `ntoskrnl!RtlGetNextEntryHashTable` at `0x14004cde7`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14004cd24`
- `ntoskrnl!RtlLookupEntryHashTable` at `0x14004cd24`
- `NDIS!NdisAcquireRWLockRead` at `0x14004cd01`
- `NDIS!NdisAcquireRWLockRead` at `0x14004cd01`
- `NDIS!NdisReleaseRWLock` at `0x14004ce07`
- `NDIS!NdisReleaseRWLock` at `0x14004ce9c`
- `NDIS!NdisReleaseRWLock` at `0x14004ce07`
- `NDIS!NdisReleaseRWLock` at `0x14004ce9c`

## pseudocode

```c
__int64 __fastcall IndexHashClassify(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 *a5, _QWORD *a6)
{
  struct _NDIS_RW_LOCK_EX *v8; // rcx
  void *v9; // rsi
  void *v11; // rdi
  ULONG_PTR v12; // rax
  PRTL_DYNAMIC_HASH_TABLE_ENTRY NextEntryHashTable; // rax
  __int64 v14; // r8
  __int64 *v15; // r14
  __int64 Flink; // rbx
  int v17; // eax
  __int64 v18; // rax
  unsigned int v19; // ecx
  __int64 v20; // r8
  _QWORD *v21; // r9
  unsigned __int64 v22; // rcx
  unsigned __int64 *v23; // rax
  __int64 v24; // rbx
  __int64 inserted; // [rsp+30h] [rbp-58h] BYREF
  void *v27; // [rsp+38h] [rbp-50h] BYREF
  struct _RTL_DYNAMIC_HASH_TABLE_CONTEXT Context; // [rsp+40h] [rbp-48h] BYREF
  struct _LOCK_STATE_EX LockState; // [rsp+90h] [rbp+8h] BYREF

  inserted = 0;
  *(_WORD *)&LockState.OldIrql = 0;
  LockState.Flags = 0;
  v8 = *(struct _NDIS_RW_LOCK_EX **)a1;
  v9 = 0;
  memset(&Context, 0, sizeof(Context));
  v27 = 0;
  v11 = 0;
  NdisAcquireRWLockRead(v8, &LockState, 1u);
  v12 = ComputeIncomingHash(a1, a2);
  NextEntryHashTable = RtlLookupEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), v12, &Context);
  if ( NextEntryHashTable )
  {
    v15 = a5;
    while ( 1 )
    {
      Flink = (__int64)NextEntryHashTable[1].Linkage.Flink;
      v17 = FilterMatchEx(Flink, a2, v14, 0, (__int64)&inserted);
      if ( inserted )
        break;
      if ( v17 )
      {
        v18 = *v15;
        if ( !*v15
          || (v19 = *(_DWORD *)(v18 + 60), *(_DWORD *)(Flink + 60) > v19)
          || *(_DWORD *)(Flink + 60) < v19
          || (v20 = *(_QWORD *)(v18 + 24),
              v21 = *(_QWORD **)(Flink + 24),
              v22 = **(_QWORD **)(v20 + 16),
              v23 = (unsigned __int64 *)v21[2],
              *v23 >= v22)
          && (*v23 > v22 || *v21 > *(_QWORD *)v20) )
        {
          if ( (*(_DWORD *)(*(_QWORD *)(Flink + 24) + 40LL) & 0x1000) != 0 )
            *v15 = Flink;
          inserted = InsertFilterToMatchBuf(v9, Flink, &v27, a4);
          if ( inserted )
            break;
          v9 = v27;
          if ( !v11 )
            v11 = v27;
        }
      }
      NextEntryHashTable = RtlGetNextEntryHashTable(*(PRTL_DYNAMIC_HASH_TABLE *)(a1 + 16), &Context);
      if ( !NextEntryHashTable )
        goto LABEL_17;
    }
    NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, &LockState);
    goto LABEL_18;
  }
LABEL_17:
  NdisReleaseRWLock(*(PNDIS_RW_LOCK_EX *)a1, &LockState);
  inserted = SortMatchList(v11);
  if ( inserted )
  {
LABEL_18:
    *a6 = 0;
    FreeMatchBufListInternal(v11);
    v24 = inserted;
    if ( inserted
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        WPP_GLOBAL_Control->AttachedDevice,
        15,
        (unsigned int)WPP_dc97c17fd6903ad537f842808d057dba_Traceguids,
        (unsigned int)"IndexHashClassify",
        inserted);
    }
    return v24;
  }
  if ( v11 )
    *a6 = v11;
  return 0;
}

```

## disassembly

```asm
0x14004ccb0  mov     r11, rsp
0x14004ccb3  mov     [r11+10h], rbx
0x14004ccb7  mov     [r11+18h], rbp
0x14004ccbb  push    rsi
0x14004ccbc  push    rdi
0x14004ccbd  push    r12
0x14004ccbf  push    r14
0x14004ccc1  push    r15
0x14004ccc3  sub     rsp, 60h
0x14004ccc7  xor     eax, eax
0x14004ccc9  mov     qword ptr [r11-58h], 0
0x14004ccd1  xorps   xmm0, xmm0
0x14004ccd4  mov     [r11+8], ax
0x14004ccd9  mov     rbp, rdx
0x14004ccdc  mov     [r11+0Ah], al
0x14004cce0  mov     r15, rcx
0x14004cce3  lea     rdx, [r11+8]; LockState
0x14004cce7  mov     rcx, [rcx]; Lock
0x14004ccea  xor     esi, esi
0x14004ccec  movups  xmmword ptr [rsp+88h+Context.ChainHead], xmm0
0x14004ccf1  mov     r8b, 1; Flags
0x14004ccf4  mov     [r11-38h], rax
0x14004ccf8  mov     r12, r9
0x14004ccfb  mov     [r11-50h], rsi
0x14004ccff  xor     edi, edi
0x14004cd01  call    cs:__imp_NdisAcquireRWLockRead
0x14004cd08  nop     dword ptr [rax+rax+00h]
0x14004cd0d  mov     rdx, rbp
0x14004cd10  mov     rcx, r15
0x14004cd13  call    ComputeIncomingHash
0x14004cd18  mov     rcx, [r15+10h]; HashTable
0x14004cd1c  lea     r8, [rsp+88h+Context]; Context
0x14004cd21  mov     rdx, rax; Signature
0x14004cd24  call    cs:__imp_RtlLookupEntryHashTable
0x14004cd2b  nop     dword ptr [rax+rax+00h]
0x14004cd30  test    rax, rax
0x14004cd33  jz      loc_14004CDFC
0x14004cd39  mov     r14, [rsp+88h+arg_20]
0x14004cd41  mov     rbx, [rax+18h]
0x14004cd45  xor     r9d, r9d
0x14004cd48  lea     rax, [rsp+88h+var_58]
0x14004cd4d  mov     rcx, rbx
0x14004cd50  mov     rdx, rbp
0x14004cd53  mov     [rsp+88h+var_68], rax
0x14004cd58  call    FilterMatchEx
0x14004cd5d  cmp     [rsp+88h+var_58], 0
0x14004cd63  jnz     loc_14004CE91
0x14004cd69  test    eax, eax
0x14004cd6b  jz      short loc_14004CDDE
0x14004cd6d  mov     rax, [r14]
0x14004cd70  test    rax, rax
0x14004cd73  jz      short loc_14004CDA1
0x14004cd75  mov     ecx, [rax+3Ch]
0x14004cd78  cmp     [rbx+3Ch], ecx
0x14004cd7b  ja      short loc_14004CDA1
0x14004cd7d  jb      short loc_14004CDA1
0x14004cd7f  mov     r8, [rax+18h]
0x14004cd83  mov     r9, [rbx+18h]
0x14004cd87  mov     rax, [r8+10h]
0x14004cd8b  mov     rcx, [rax]
0x14004cd8e  mov     rax, [r9+10h]
0x14004cd92  cmp     [rax], rcx
0x14004cd95  jb      short loc_14004CDDE
0x14004cd97  ja      short loc_14004CDA1
0x14004cd99  mov     rax, [r8]
0x14004cd9c  cmp     [r9], rax
0x14004cd9f  jbe     short loc_14004CDDE
0x14004cda1  mov     rax, [rbx+18h]
0x14004cda5  test    dword ptr [rax+28h], 1000h
0x14004cdac  jz      short loc_14004CDB1
0x14004cdae  mov     [r14], rbx
0x14004cdb1  mov     r9, r12
0x14004cdb4  lea     r8, [rsp+88h+var_50]
0x14004cdb9  mov     rdx, rbx
0x14004cdbc  mov     rcx, rsi
0x14004cdbf  call    InsertFilterToMatchBuf
0x14004cdc4  mov     [rsp+88h+var_58], rax
0x14004cdc9  test    rax, rax
0x14004cdcc  jnz     loc_14004CE91
0x14004cdd2  mov     rsi, [rsp+88h+var_50]
0x14004cdd7  test    rdi, rdi
0x14004cdda  cmovz   rdi, rsi
0x14004cdde  mov     rcx, [r15+10h]; HashTable
0x14004cde2  lea     rdx, [rsp+88h+Context]; Context
0x14004cde7  call    cs:__imp_RtlGetNextEntryHashTable
0x14004cdee  nop     dword ptr [rax+rax+00h]
0x14004cdf3  test    rax, rax
0x14004cdf6  jnz     loc_14004CD41
0x14004cdfc  mov     rcx, [r15]; Lock
0x14004cdff  lea     rdx, [rsp+88h+LockState]; LockState
0x14004ce07  call    cs:__imp_NdisReleaseRWLock
0x14004ce0e  nop     dword ptr [rax+rax+00h]
0x14004ce13  mov     rcx, rdi
0x14004ce16  call    SortMatchList
0x14004ce1b  mov     [rsp+88h+var_58], rax
0x14004ce20  test    rax, rax
0x14004ce23  jz      loc_14004CEAD
0x14004ce29  mov     rax, [rsp+88h+arg_28]
0x14004ce31  mov     rcx, rdi; Entry
0x14004ce34  mov     qword ptr [rax], 0
0x14004ce3b  call    FreeMatchBufListInternal
0x14004ce40  mov     rbx, [rsp+88h+var_58]
0x14004ce45  test    rbx, rbx
0x14004ce48  jz      short loc_14004CE8C
0x14004ce4a  mov     rcx, cs:WPP_GLOBAL_Control
0x14004ce51  lea     rax, WPP_GLOBAL_Control
0x14004ce58  cmp     rcx, rax
0x14004ce5b  jz      short loc_14004CE8C
0x14004ce5d  cmp     byte ptr [rcx+29h], 2
0x14004ce61  jb      short loc_14004CE8C
0x14004ce63  test    dword ptr [rcx+2Ch], 1000h
0x14004ce6a  jz      short loc_14004CE8C
0x14004ce6c  mov     rcx, [rcx+18h]
0x14004ce70  lea     r9, aIndexhashclass; "IndexHashClassify"
0x14004ce77  mov     edx, 0Fh
0x14004ce7c  mov     dword ptr [rsp+88h+var_68], ebx
0x14004ce80  lea     r8, WPP_dc97c17fd6903ad537f842808d057dba_Traceguids
0x14004ce87  call    WPP_SF_sd
0x14004ce8c  mov     rax, rbx
0x14004ce8f  jmp     short loc_14004CEBF
0x14004ce91  mov     rcx, [r15]; Lock
0x14004ce94  lea     rdx, [rsp+88h+LockState]; LockState
0x14004ce9c  call    cs:__imp_NdisReleaseRWLock
0x14004cea3  nop     dword ptr [rax+rax+00h]
0x14004cea8  jmp     loc_14004CE29
0x14004cead  test    rdi, rdi
0x14004ceb0  jz      short loc_14004CEBD
0x14004ceb2  mov     rax, [rsp+88h+arg_28]
0x14004ceba  mov     [rax], rdi
0x14004cebd  xor     eax, eax
0x14004cebf  lea     r11, [rsp+88h+var_28]
0x14004cec4  mov     rbx, [r11+38h]
0x14004cec8  mov     rbp, [r11+40h]
0x14004cecc  mov     rsp, r11
0x14004cecf  pop     r15
0x14004ced1  pop     r14
0x14004ced3  pop     r12
0x14004ced5  pop     rdi
0x14004ced6  pop     rsi
0x14004ced7  retn
```
