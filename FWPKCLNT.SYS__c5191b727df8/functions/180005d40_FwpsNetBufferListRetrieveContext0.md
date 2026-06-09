# FwpsNetBufferListRetrieveContext0

- ea: `0x180005d40`
- end: `0x1800060a7`
- name: `FwpsNetBufferListRetrieveContext0`
- size: `871`
- prototype: `NTSTATUS __stdcall(NET_BUFFER_LIST *netBufferList, UINT64 contextTag, BOOLEAN removeContext, UINT32 flags, UINT64 *context)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001d450`

## callees

- `0x180004904`
- `0x180005d40`
- `0x1800063b0`
- `0x180006a1c`
- `0x180006dd4`
- `0x18000de60`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005e8b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005ef2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005e8b`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x180005ef2`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180005e6e`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x180005e6e`
- `ntoskrnl!MmBadPointer` at `0x180005d8f`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180005f20`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x180005f20`
- `ntoskrnl!ObfDereferenceObject` at `0x180005df6`
- `ntoskrnl!ObfDereferenceObject` at `0x180005df6`
- `ntoskrnl!KeGetCurrentIrql` at `0x180005e53`
- `ntoskrnl!KeGetCurrentIrql` at `0x180005e53`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006020`
- `ntoskrnl!RtlRemoveEntryHashTable` at `0x180006020`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18000608f`
- `ntoskrnl!RtlEndEnumerationHashTable` at `0x18000608f`
- `NETIO!WfpNblInfoGet` at `0x180005d77`
- `NETIO!WfpNblInfoGet` at `0x180005d77`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x180005e08`
- `NETIO!WfpNblInfoDestroyIfUnused` at `0x180005e08`

## pseudocode

```c
// local variable allocation has failed, the output may be wrong!
NTSTATUS __stdcall FwpsNetBufferListRetrieveContext0(
        NET_BUFFER_LIST *netBufferList,
        UINT64 contextTag,
        BOOLEAN removeContext,
        UINT32 flags,
        UINT64 *context)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 v10; // rax
  char *v11; // rdx
  void *v12; // rcx
  NTSTATUS v13; // ebx
  char v15; // r15
  KIRQL CurrentIrql; // bl
  __int64 v17; // rdx
  __int64 TaggedContextList; // rax
  __int64 v19; // r14
  _DWORD *v20; // rdx
  NTSTATUS v21; // eax
  _QWORD *v22; // rax
  _QWORD *v23; // rcx
  _QWORD *v24; // r14
  _QWORD *v25; // [rsp+30h] [rbp-38h] BYREF
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+38h] [rbp-30h] BYREF
  _QWORD *v27; // [rsp+70h] [rbp+8h] BYREF

  if ( !netBufferList )
  {
    v13 = -1071513572;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x1000) != 0 )
    {
      WPP_SF_sd(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0xAu,
        removeContext,
        "FwpsNetBufferListRetrieveContext0",
        -1071513572);
    }
    return v13;
  }
  if ( !flags )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    v8 = (_DWORD *)WfpNblInfoGet(netBufferList);
    v9 = v8;
    if ( !v8 || v8 == MmBadPointer )
      return -1073741275;
    if ( contextTag - 1 > 3 && contextTag - 65537 > 3
      || (contextTag > 4 ? (v10 = (unsigned int)(contextTag - 65533)) : (v10 = (unsigned int)(contextTag - 1)),
          (v11 = (char *)&v9[16 * v10 + 12 + 2 * v10]) == 0) )
    {
      v15 = 0;
      CurrentIrql = KeGetCurrentIrql();
      KeAcquireInStackQueuedSpinLock(&SpinLock, &LockHandle);
      if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
      {
        v17 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType
                                                              * KeGetCurrentProcessorNumberEx(0));
        *(_QWORD *)(v17 + 8) = MEMORY[0xFFFFF78000000008];
        *(_DWORD *)v17 = 4;
      }
      TaggedContextList = FwppGetTaggedContextList(netBufferList);
      v19 = TaggedContextList;
      if ( TaggedContextList )
      {
        v22 = (_QWORD *)(TaggedContextList + 128);
        v27 = v22;
        v23 = v22;
        v25 = v22;
        while ( *(_BYTE *)(v19 + 184) || *(_QWORD *)(v19 + 16) != contextTag )
        {
          v24 = (_QWORD *)*v22;
          v22 = v24;
          v27 = v24;
          if ( v24 == v23 )
            goto LABEL_24;
          v19 = (__int64)(v24 - 16);
        }
        v15 = 1;
        if ( removeContext )
        {
          FwppRemoveTaggedContextFromNetBufferList(netBufferList, v19, &v25, &v27);
          WfpObjectDereference(v19 + 72);
        }
        if ( context )
          *context = *(_QWORD *)(v19 + 8);
        if ( removeContext )
        {
          RtlRemoveEntryHashTable(&HashTable, (PRTL_DYNAMIC_HASH_TABLE_ENTRY)(v19 + 96), 0);
          *(_BYTE *)(v19 + 184) = 1;
          WfpObjectDereference(v19 + 72);
        }
      }
LABEL_24:
      if ( byte_1800486F8 )
      {
        RtlEndEnumerationHashTable(qword_1800486C8, &Enumerator);
        byte_1800486F8 = 0;
      }
      if ( WPP_MAIN_CB.DeviceExtension )
      {
        v20 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension
                         + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
        if ( *v20 == 4 )
          *v20 = 0;
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v21 = -1073741275;
      if ( v15 )
        return 0;
      return v21;
    }
    if ( !v11[1] )
      return -1073741275;
    if ( context )
      *context = *((_QWORD *)v11 + 1);
    if ( removeContext )
    {
      v12 = (void *)*((_QWORD *)v11 + 5);
      v11[1] = 0;
      if ( v12 )
        ObfDereferenceObject(v12);
      --v9[10];
      WfpNblInfoDestroyIfUnused(netBufferList);
    }
    return 0;
  }
  return WfpReportSysErrorAsNtStatus((__int64)netBufferList, (int)"FwpsNetBufferListRetrieveContext0", -1071513547);
}

```

## disassembly

```asm
0x180005d40  mov     [rsp+arg_18], rbx
0x180005d45  push    rbp
0x180005d46  push    rsi
0x180005d47  push    rdi
0x180005d48  sub     rsp, 50h
0x180005d4c  movzx   ebp, r8b
0x180005d50  mov     rsi, rdx
0x180005d53  mov     rdi, rcx
0x180005d56  test    rcx, rcx
0x180005d59  jz      loc_180005F4A
0x180005d5f  test    r9d, r9d
0x180005d62  jnz     loc_18000605E
0x180005d68  xorps   xmm0, xmm0
0x180005d6b  xor     eax, eax
0x180005d6d  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x180005d72  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x180005d77  call    cs:__imp_WfpNblInfoGet
0x180005d7e  nop     dword ptr [rax+rax+00h]
0x180005d83  mov     rbx, rax
0x180005d86  test    rax, rax
0x180005d89  jz      loc_180005E18
0x180005d8f  mov     rcx, cs:MmBadPointer
0x180005d96  cmp     rax, [rcx]
0x180005d99  jz      short loc_180005E18
0x180005d9b  lea     rcx, [rsi-1]
0x180005d9f  cmp     rcx, 3
0x180005da3  ja      loc_180005E32
0x180005da9  cmp     rsi, 4
0x180005dad  ja      loc_180005F9D
0x180005db3  lea     eax, [rsi-1]
0x180005db6  lea     rdx, ds:6[rax*8]
0x180005dbe  add     rdx, rax
0x180005dc1  lea     rdx, [rbx+rdx*8]
0x180005dc5  test    rdx, rdx
0x180005dc8  jz      short loc_180005E43
0x180005dca  cmp     byte ptr [rdx+1], 0
0x180005dce  jz      short loc_180005E18
0x180005dd0  mov     rcx, [rsp+68h+context]
0x180005dd8  test    rcx, rcx
0x180005ddb  jz      short loc_180005DE4
0x180005ddd  mov     rax, [rdx+8]
0x180005de1  mov     [rcx], rax
0x180005de4  test    bpl, bpl
0x180005de7  jz      short loc_180005E14
0x180005de9  mov     rcx, [rdx+28h]; Object
0x180005ded  mov     byte ptr [rdx+1], 0
0x180005df1  test    rcx, rcx
0x180005df4  jz      short loc_180005E02
0x180005df6  call    cs:__imp_ObfDereferenceObject
0x180005dfd  nop     dword ptr [rax+rax+00h]
0x180005e02  dec     dword ptr [rbx+28h]
0x180005e05  mov     rcx, rdi
0x180005e08  call    cs:__imp_WfpNblInfoDestroyIfUnused
0x180005e0f  nop     dword ptr [rax+rax+00h]
0x180005e14  xor     ebx, ebx
0x180005e16  jmp     short loc_180005E1F
0x180005e18  mov     rbx, 0FFFFFFFFC0000225h
0x180005e1f  mov     eax, ebx
0x180005e21  mov     rbx, [rsp+68h+arg_18]
0x180005e29  add     rsp, 50h
0x180005e2d  pop     rdi
0x180005e2e  pop     rsi
0x180005e2f  pop     rbp
0x180005e30  retn
0x180005e32  lea     rcx, [rsi-10001h]
0x180005e39  cmp     rcx, 3
0x180005e3d  jbe     loc_180005DA9
0x180005e43  mov     [rsp+68h+arg_8], r14
0x180005e48  mov     [rsp+68h+arg_10], r15
0x180005e50  xor     r15b, r15b
0x180005e53  call    cs:__imp_KeGetCurrentIrql
0x180005e5a  nop     dword ptr [rax+rax+00h]
0x180005e5f  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x180005e64  movzx   ebx, al
0x180005e67  lea     rcx, SpinLock; SpinLock
0x180005e6e  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x180005e75  nop     dword ptr [rax+rax+00h]
0x180005e7a  cmp     bl, 2
0x180005e7d  jz      short loc_180005EBF
0x180005e7f  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x180005e87  jz      short loc_180005EBF
0x180005e89  xor     ecx, ecx; ProcNumber
0x180005e8b  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180005e92  nop     dword ptr [rax+rax+00h]
0x180005e97  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x180005e9e  mov     ecx, eax
0x180005ea0  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180005ea7  mov     rdx, [rcx+rax]
0x180005eab  mov     rax, ds:0FFFFF78000000008h
0x180005eb5  mov     [rdx+8], rax
0x180005eb9  mov     dword ptr [rdx], 4
0x180005ebf  mov     rcx, rdi
0x180005ec2  call    FwppGetTaggedContextList
0x180005ec7  mov     r14, rax
0x180005eca  test    rax, rax
0x180005ecd  jnz     loc_180005FAF
0x180005ed3  cmp     cs:byte_1800486F8, 0
0x180005eda  mov     r14, [rsp+68h+arg_8]
0x180005edf  jnz     loc_180006081
0x180005ee5  xor     ebx, ebx
0x180005ee7  cmp     cs:WPP_MAIN_CB.DeviceExtension, rbx
0x180005eee  jz      short loc_180005F1B
0x180005ef0  xor     ecx, ecx; ProcNumber
0x180005ef2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x180005ef9  nop     dword ptr [rax+rax+00h]
0x180005efe  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x180005f05  mov     ecx, eax
0x180005f07  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x180005f0e  mov     rdx, [rcx+rax]
0x180005f12  cmp     dword ptr [rdx], 4
0x180005f15  jz      loc_180005FA8
0x180005f1b  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x180005f20  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x180005f27  nop     dword ptr [rax+rax+00h]
0x180005f2c  test    r15b, r15b
0x180005f2f  mov     rax, 0FFFFFFFFC0000225h
0x180005f36  mov     r15, [rsp+68h+arg_10]
0x180005f3e  cmovnz  rax, rbx
0x180005f42  mov     rbx, rax
0x180005f45  jmp     loc_180005E1F
0x180005f4a  mov     rcx, cs:WPP_GLOBAL_Control
0x180005f51  lea     rax, WPP_GLOBAL_Control
0x180005f58  mov     rbx, 0FFFFFFFFC022001Ch
0x180005f5f  cmp     rcx, rax
0x180005f62  jz      loc_180005E1F
0x180005f68  cmp     byte ptr [rcx+29h], 2
0x180005f6c  jb      loc_180005E1F
0x180005f72  test    dword ptr [rcx+2Ch], 1000h
0x180005f79  jz      loc_180005E1F
0x180005f7f  mov     rcx, [rcx+18h]
0x180005f83  lea     r9, aFwpsnetbufferl; "FwpsNetBufferListRetrieveContext0"
0x180005f8a  mov     edx, 0Ah
0x180005f8f  mov     [rsp+68h+var_48], ebx
0x180005f93  call    WPP_SF_sd
0x180005f98  jmp     loc_180005E1F
0x180005f9d  lea     eax, [rsi-0FFFDh]
0x180005fa3  jmp     loc_180005DB6
0x180005fa8  mov     [rdx], ebx
0x180005faa  jmp     loc_180005F1B
0x180005faf  sub     rax, 0FFFFFFFFFFFFFF80h
0x180005fb3  mov     [rsp+68h+arg_0], rax
0x180005fb8  mov     rcx, rax
0x180005fbb  mov     [rsp+68h+var_38], rax
0x180005fc0  cmp     [r14+0B8h], r15b
0x180005fc7  jnz     short loc_180006041
0x180005fc9  cmp     [r14+10h], rsi
0x180005fcd  jnz     short loc_180006041
0x180005fcf  mov     r15b, 1
0x180005fd2  test    bpl, bpl
0x180005fd5  jz      short loc_180005FF5
0x180005fd7  lea     r9, [rsp+68h+arg_0]
0x180005fdc  mov     rdx, r14
0x180005fdf  lea     r8, [rsp+68h+var_38]
0x180005fe4  mov     rcx, rdi
0x180005fe7  call    FwppRemoveTaggedContextFromNetBufferList
0x180005fec  lea     rcx, [r14+48h]
0x180005ff0  call    WfpObjectDereference
0x180005ff5  mov     rcx, [rsp+68h+context]
0x180005ffd  test    rcx, rcx
0x180006000  jz      short loc_180006009
0x180006002  mov     rax, [r14+8]
0x180006006  mov     [rcx], rax
0x180006009  test    bpl, bpl
0x18000600c  jz      loc_180005ED3
0x180006012  lea     rdx, [r14+60h]; Entry
0x180006016  xor     r8d, r8d; Context
0x180006019  lea     rcx, HashTable; HashTable
0x180006020  call    cs:__imp_RtlRemoveEntryHashTable
0x180006027  nop     dword ptr [rax+rax+00h]
0x18000602c  lea     rcx, [r14+48h]
0x180006030  mov     [r14+0B8h], r15b
0x180006037  call    WfpObjectDereference
0x18000603c  jmp     loc_180005ED3
0x180006041  mov     r14, [rax]
0x180006044  mov     rax, r14
0x180006047  mov     [rsp+68h+arg_0], rax
0x18000604c  cmp     r14, rcx
0x18000604f  jz      loc_180005ED3
0x180006055  add     r14, 0FFFFFFFFFFFFFF80h
0x180006059  jmp     loc_180005FC0
0x18000605e  mov     r8d, 0C0220035h
0x180006064  lea     rdx, aFwpsnetbufferl; "FwpsNetBufferListRetrieveContext0"
0x18000606b  call    WfpReportSysErrorAsNtStatus
0x180006070  mov     rbx, [rsp+68h+arg_18]
0x180006078  add     rsp, 50h
0x18000607c  pop     rdi
0x18000607d  pop     rsi
0x18000607e  pop     rbp
0x18000607f  retn
0x180006081  mov     rcx, cs:qword_1800486C8; HashTable
0x180006088  lea     rdx, Enumerator; Enumerator
0x18000608f  call    cs:__imp_RtlEndEnumerationHashTable
0x180006096  nop     dword ptr [rax+rax+00h]
0x18000609b  mov     cs:byte_1800486F8, 0
0x1800060a2  jmp     loc_180005EE5
```
