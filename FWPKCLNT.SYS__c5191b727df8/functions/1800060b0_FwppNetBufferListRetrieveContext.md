# FwppNetBufferListRetrieveContext

- ea: `0x1800060b0`
- end: `0x1800063a5`
- name: `FwppNetBufferListRetrieveContext`
- size: `757`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005060`
- `0x1800056d0`

## callees

- `0x1800060b0`
- `0x1800063b0`
- `0x180006a1c`
- `0x180006dd4`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800061fb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180006261`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x1800061fb`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180006261`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800061de`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1800061de`
- `ntoskrnl!MmBadPointer` at `0x1800060ed`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000628b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000628b`
- `ntoskrnl!ObfDereferenceObject` at `0x18000615c`
- `ntoskrnl!ObfDereferenceObject` at `0x18000615c`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800061c3`
- `ntoskrnl!KeGetCurrentIrql` at `0x1800061c3`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006341`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006341`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18000638d`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18000638d`
- `NETIO!WfpNblInfoGet` at `0x1800060d5`
- `NETIO!WfpNblInfoGet` at `0x1800060d5`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000616e`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x18000616e`

## pseudocode

```c
__int64 __fastcall FwppNetBufferListRetrieveContext(__int64 a1, unsigned __int64 a2, char a3, __int64 a4, _QWORD *a5)
{
  _DWORD *v8; // rbx
  unsigned __int64 v9; // rax
  _DWORD *v10; // rdx
  void *v11; // rcx
  __int64 result; // rax
  char v13; // r15
  KIRQL CurrentIrql; // bl
  __int64 v15; // rdx
  __int64 TaggedContextList; // rax
  __int64 v17; // r14
  _DWORD *v18; // rdx
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  _QWORD *v21; // r14
  _QWORD *v22; // [rsp+20h] [rbp-48h] BYREF
  _QWORD *v23; // [rsp+28h] [rbp-40h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-38h] BYREF

  memset(&LockHandle, 0, sizeof(LockHandle));
  v8 = (_DWORD *)WfpNblInfoGet(a1);
  if ( !v8 || v8 == MmBadPointer )
    return -1073741275;
  if ( a2 - 1 <= 3 || a2 - 65537 <= 3 )
  {
    v9 = a2 > 4 ? (unsigned int)(a2 - 65533) : (unsigned int)(a2 - 1);
    v10 = &v8[16 * v9 + 12 + 2 * v9];
    if ( v10 )
    {
      if ( *((_BYTE *)v10 + 1) )
      {
        if ( a5 )
          *a5 = *((_QWORD *)v10 + 1);
        if ( a3 )
        {
          v11 = (void *)*((_QWORD *)v10 + 5);
          *((_BYTE *)v10 + 1) = 0;
          if ( v11 )
            ObfDereferenceObject(v11);
          --v8[10];
          WfpNblInfoDestroyIfUnused(a1);
        }
        return 0;
      }
      return -1073741275;
    }
  }
  v13 = 0;
  CurrentIrql = KeGetCurrentIrql();
  KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
  if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
  {
    v15 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
    *(_QWORD *)(v15 + 8) = MEMORY[0xFFFFF78000000008];
    *(_DWORD *)v15 = 4;
  }
  TaggedContextList = FwppGetTaggedContextList(a1);
  v17 = TaggedContextList;
  if ( TaggedContextList )
  {
    v19 = (_QWORD *)(TaggedContextList + 128);
    v22 = v19;
    v20 = v19;
    v23 = v19;
    while ( *(_BYTE *)(v17 + 184) || *(_QWORD *)(v17 + 16) != a2 )
    {
      v21 = (_QWORD *)*v19;
      v19 = v21;
      v22 = v21;
      if ( v21 == v20 )
        goto LABEL_21;
      v17 = (__int64)(v21 - 16);
    }
    v13 = 1;
    if ( a3 )
    {
      FwppRemoveTaggedContextFromNetBufferList(a1, v17, &v23, &v22);
      WfpObjectDereference(v17 + 72);
    }
    if ( a5 )
      *a5 = *(_QWORD *)(v17 + 8);
    if ( a3 )
    {
      RtlRemoveEntryHashTable(&HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v17 + 96), 0);
      *(_BYTE *)(v17 + 184) = 1;
      WfpObjectDereference(v17 + 72);
    }
  }
LABEL_21:
  if ( byte_1800486F8 )
  {
    RtlEndEnumerationHashTable(qword_1800486C8, &Enumerator);
    byte_1800486F8 = 0;
  }
  if ( WPP_MAIN_CB.DeviceExtension )
  {
    v18 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
    if ( *v18 == 4 )
      *v18 = 0;
  }
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  result = -1073741275;
  if ( v13 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x1800060b0  mov     [rsp+arg_10], rbx
0x1800060b5  push    rbp
0x1800060b6  push    rsi
0x1800060b7  push    rdi
0x1800060b8  sub     rsp, 50h
0x1800060bc  xorps   xmm0, xmm0
0x1800060bf  xor     eax, eax
0x1800060c1  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x1800060c6  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x1800060cb  movzx   ebp, r8b
0x1800060cf  mov     rdi, rdx
0x1800060d2  mov     rsi, rcx
0x1800060d5  call    cs:__imp_WfpNblInfoGet
0x1800060dc  nop     dword ptr [rax+rax+00h]
0x1800060e1  mov     rbx, rax
0x1800060e4  test    rax, rax
0x1800060e7  jz      loc_18000618D
0x1800060ed  mov     rax, cs:MmBadPointer
0x1800060f4  cmp     rbx, [rax]
0x1800060f7  jz      loc_18000618D
0x1800060fd  lea     rax, [rdi-1]
0x180006101  cmp     rax, 3
0x180006105  ja      loc_1800061A5
0x18000610b  cmp     rdi, 4
0x18000610f  ja      loc_1800062BD
0x180006115  lea     eax, [rdi-1]
0x180006118  lea     rdx, ds:6[rax*8]
0x180006120  add     rdx, rax
0x180006123  lea     rdx, [rbx+rdx*8]
0x180006127  test    rdx, rdx
0x18000612a  jz      loc_1800061B6
0x180006130  cmp     byte ptr [rdx+1], 0
0x180006134  jz      short loc_18000618D
0x180006136  mov     rcx, [rsp+68h+arg_20]
0x18000613e  test    rcx, rcx
0x180006141  jz      short loc_18000614A
0x180006143  mov     rax, [rdx+8]
0x180006147  mov     [rcx], rax
0x18000614a  test    bpl, bpl
0x18000614d  jz      short loc_18000617A
0x18000614f  mov     rcx, [rdx+28h]; Object
0x180006153  mov     byte ptr [rdx+1], 0
0x180006157  test    rcx, rcx
0x18000615a  jz      short loc_180006168
0x18000615c  call    cs:__imp_ObfDereferenceObject
0x180006163  nop     dword ptr [rax+rax+00h]
0x180006168  dec     dword ptr [rbx+28h]
0x18000616b  mov     rcx, rsi
0x18000616e  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x180006175  nop     dword ptr [rax+rax+00h]
0x18000617a  xor     eax, eax
0x18000617c  mov     rbx, [rsp+68h+arg_10]
0x180006184  add     rsp, 50h
0x180006188  pop     rdi
0x180006189  pop     rsi
0x18000618a  pop     rbp
0x18000618b  retn
0x18000618d  mov     rax, 0FFFFFFFFC0000225h
0x180006194  mov     rbx, [rsp+68h+arg_10]
0x18000619c  add     rsp, 50h
0x1800061a0  pop     rdi
0x1800061a1  pop     rsi
0x1800061a2  pop     rbp
0x1800061a3  retn
0x1800061a5  lea     rax, [rdi-10001h]
0x1800061ac  cmp     rax, 3
0x1800061b0  jbe     loc_18000610B
0x1800061b6  mov     [rsp+68h+arg_0], r14
0x1800061bb  mov     [rsp+68h+arg_8], r15
0x1800061c0  xor     r15b, r15b
0x1800061c3  call    cs:__imp_KeGetCurrentIrql
0x1800061ca  nop     dword ptr [rax+rax+00h]
0x1800061cf  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x1800061d4  movzx   ebx, al
0x1800061d7  lea     rcx, SpinLock; SpinLock
0x1800061de  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1800061e5  nop     dword ptr [rax+rax+00h]
0x1800061ea  cmp     bl, 2
0x1800061ed  jz      short loc_18000622F
0x1800061ef  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x1800061f7  jz      short loc_18000622F
0x1800061f9  xor     ecx, ecx; ProcNumber
0x1800061fb  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180006202  nop     dword ptr [rax+rax+00h]
0x180006207  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x18000620e  mov     ecx, eax
0x180006210  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180006217  mov     rdx, [rcx+rax]
0x18000621b  mov     rax, ds:0FFFFF78000000008h
0x180006225  mov     [rdx+8], rax
0x180006229  mov     dword ptr [rdx], 4
0x18000622f  mov     rcx, rsi
0x180006232  call    FwppGetTaggedContextList
0x180006237  mov     r14, rax
0x18000623a  test    rax, rax
0x18000623d  jnz     loc_1800062D0
0x180006243  cmp     cs:byte_1800486F8, 0
0x18000624a  mov     r14, [rsp+68h+arg_0]
0x18000624f  jnz     loc_18000637F
0x180006255  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x18000625d  jz      short loc_180006286
0x18000625f  xor     ecx, ecx; ProcNumber
0x180006261  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180006268  nop     dword ptr [rax+rax+00h]
0x18000626d  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x180006274  mov     ecx, eax
0x180006276  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000627d  mov     rdx, [rcx+rax]
0x180006281  cmp     dword ptr [rdx], 4
0x180006284  jz      short loc_1800062C8
0x180006286  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x18000628b  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180006292  nop     dword ptr [rax+rax+00h]
0x180006297  mov     rbx, [rsp+68h+arg_10]
0x18000629f  xor     ecx, ecx
0x1800062a1  test    r15b, r15b
0x1800062a4  mov     rax, 0FFFFFFFFC0000225h
0x1800062ab  mov     r15, [rsp+68h+arg_8]
0x1800062b0  cmovnz  rax, rcx
0x1800062b4  add     rsp, 50h
0x1800062b8  pop     rdi
0x1800062b9  pop     rsi
0x1800062ba  pop     rbp
0x1800062bb  retn
0x1800062bd  lea     eax, [rdi-0FFFDh]
0x1800062c3  jmp     loc_180006118
0x1800062c8  mov     dword ptr [rdx], 0
0x1800062ce  jmp     short loc_180006286
0x1800062d0  sub     rax, 0FFFFFFFFFFFFFF80h
0x1800062d4  mov     [rsp+68h+var_48], rax
0x1800062d9  mov     rcx, rax
0x1800062dc  mov     [rsp+68h+var_40], rax
0x1800062e1  cmp     [r14+0B8h], r15b
0x1800062e8  jnz     short loc_180006362
0x1800062ea  cmp     [r14+10h], rdi
0x1800062ee  jnz     short loc_180006362
0x1800062f0  mov     r15b, 1
0x1800062f3  test    bpl, bpl
0x1800062f6  jz      short loc_180006316
0x1800062f8  lea     r9, [rsp+68h+var_48]
0x1800062fd  mov     rdx, r14
0x180006300  lea     r8, [rsp+68h+var_40]
0x180006305  mov     rcx, rsi
0x180006308  call    FwppRemoveTaggedContextFromNetBufferList
0x18000630d  lea     rcx, [r14+48h]
0x180006311  call    WfpObjectDereference
0x180006316  mov     rcx, [rsp+68h+arg_20]
0x18000631e  test    rcx, rcx
0x180006321  jz      short loc_18000632A
0x180006323  mov     rax, [r14+8]
0x180006327  mov     [rcx], rax
0x18000632a  test    bpl, bpl
0x18000632d  jz      loc_180006243
0x180006333  lea     rdx, [r14+60h]; Entry
0x180006337  xor     r8d, r8d; Context
0x18000633a  lea     rcx, HashTable; HashTable
0x180006341  call    cs:__imp_RtlRemoveEntryHashTable
0x180006348  nop     dword ptr [rax+rax+00h]
0x18000634d  lea     rcx, [r14+48h]
0x180006351  mov     [r14+0B8h], r15b
0x180006358  call    WfpObjectDereference
0x18000635d  jmp     loc_180006243
0x180006362  mov     r14, [rax]
0x180006365  mov     rax, r14
0x180006368  mov     [rsp+68h+var_48], rax
0x18000636d  cmp     r14, rcx
0x180006370  jz      loc_180006243
0x180006376  add     r14, 0FFFFFFFFFFFFFF80h
0x18000637a  jmp     loc_1800062E1
0x18000637f  mov     rcx, cs:qword_1800486C8; HashTable
0x180006386  lea     rdx, Enumerator; Enumerator
0x18000638d  call    cs:__imp_RtlEndEnumerationHashTable
0x180006394  nop     dword ptr [rax+rax+00h]
0x180006399  mov     cs:byte_1800486F8, 0
0x1800063a0  jmp     loc_180006255
```
