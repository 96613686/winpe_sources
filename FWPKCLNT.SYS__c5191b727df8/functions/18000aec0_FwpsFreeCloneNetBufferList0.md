# FwpsFreeCloneNetBufferList0

- ea: `0x18000aec0`
- end: `0x18000b290`
- name: `FwpsFreeCloneNetBufferList0`
- size: `976`
- prototype: `void __stdcall(NET_BUFFER_LIST *netBufferList, ULONG freeCloneFlags)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180009020`
- `0x18001ea0c`

## callees

- `0x180004960`
- `0x180007080`
- `0x180007350`
- `0x180007530`
- `0x180007ec0`
- `0x18000aec0`
- `0x180020400`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000b0f2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000b1ce`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000b0f2`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000b1ce`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18000b0d6`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18000b0d6`
- `ntoskrnl!MmBadPointer` at `0x18000af04`
- `ntoskrnl!MmBadPointer` at `0x18000af16`
- `ntoskrnl!MmBadPointer` at `0x18000af51`
- `ntoskrnl!MmBadPointer` at `0x18000b13d`
- `ntoskrnl!MmBadPointer` at `0x18000b152`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000b1fb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000b1fb`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000b0bb`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000b0bb`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000afa3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b031`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b1ad`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000afa3`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b031`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000b1ad`
- `NDIS!NdisFreeCloneNetBufferList` at `0x18000b265`
- `NDIS!NdisFreeCloneNetBufferList` at `0x18000b265`
- `NETIO!WfpNblInfoGet` at `0x18000aef0`
- `NETIO!WfpNblInfoGet` at `0x18000b129`
- `NETIO!WfpNblInfoGet` at `0x18000aef0`
- `NETIO!WfpNblInfoGet` at `0x18000b129`
- `NETIO!WfpNblInfoGetFlags` at `0x18000af6e`
- `NETIO!WfpNblInfoGetFlags` at `0x18000afe8`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b06b`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b08a`
- `NETIO!WfpNblInfoGetFlags` at `0x18000af6e`
- `NETIO!WfpNblInfoGetFlags` at `0x18000afe8`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b06b`
- `NETIO!WfpNblInfoGetFlags` at `0x18000b08a`
- `NETIO!NetioDereferenceNetBufferList` at `0x18000afd1`
- `NETIO!NetioDereferenceNetBufferList` at `0x18000afd1`

## pseudocode

```c
void __stdcall FwpsFreeCloneNetBufferList0(NET_BUFFER_LIST *netBufferList, ULONG freeCloneFlags)
{
  PNET_BUFFER_LIST v3; // rsi
  _QWORD *v5; // rax
  _DWORD *v6; // rbp
  PNET_BUFFER_LIST ParentNetBufferList; // rax
  PVOID v8; // rdx
  KIRQL CurrentIrql; // bl
  __int64 v10; // rdx
  _QWORD *v11; // rax
  PVOID v12; // rdx
  _DWORD *v13; // r8
  _DWORD *v14; // rax
  _DWORD *v15; // rdx
  int v16; // ebx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-48h] BYREF
  PVOID Entry; // [rsp+70h] [rbp+8h] BYREF
  PVOID v19; // [rsp+80h] [rbp+18h] BYREF

  if ( netBufferList )
  {
    Entry = 0;
    v3 = 0;
    v5 = (_QWORD *)WfpNblInfoGet(netBufferList);
    if ( !v5 || v5 == MmBadPointer )
    {
      v6 = 0;
      if ( v5 == MmBadPointer )
        v6 = MmBadPointer;
    }
    else
    {
      v6 = (_DWORD *)v5[1];
    }
    _InterlockedDecrement(&dword_180048700);
    ParentNetBufferList = netBufferList->ParentNetBufferList;
    if ( ParentNetBufferList )
    {
      _InterlockedDecrement(&ParentNetBufferList->ChildRefCount);
      v3 = ParentNetBufferList;
      netBufferList->ParentNetBufferList = 0;
    }
    if ( !v6 || v6 == MmBadPointer )
    {
LABEL_47:
      NdisFreeCloneNetBufferList(netBufferList, freeCloneFlags);
      return;
    }
    if ( (WfpNblInfoGetFlags(netBufferList) & 1) != 0 )
    {
      if ( v6[44] )
      {
        v8 = netBufferList->ProtocolReserved[3];
        Entry = v8;
        if ( v8 )
        {
          ExFreeToNPagedLookasideList(&stru_180048240, v8);
          Entry = (PVOID)0xBADBADFABADBADFALL;
        }
      }
      else if ( v3 )
      {
        NetioDereferenceNetBufferList(v3, 0);
      }
      goto LABEL_45;
    }
    if ( (WfpNblInfoGetFlags(netBufferList) & 2) != 0 )
    {
      if ( _InterlockedAdd(&gFwpL2, 1u) < 0 )
        goto LABEL_45;
      (*((void (__fastcall **)(NET_BUFFER_LIST *, _QWORD, PVOID *))qword_180048108 + 5))(netBufferList, 0, &Entry);
      if ( Entry )
      {
        ExFreeToNPagedLookasideList(&stru_180048140, Entry);
        Entry = (PVOID)0xBADBADFABADBADFALL;
      }
      (*((void (__fastcall **)(NET_BUFFER_LIST *))qword_180048108 + 1))(netBufferList);
      goto LABEL_44;
    }
    if ( !v3 )
      goto LABEL_45;
    if ( (WfpNblInfoGetFlags(v3) & 1) != 0 )
    {
      FwppDereferenceNetioNetBufferList(v3, 0);
      goto LABEL_45;
    }
    if ( (WfpNblInfoGetFlags(v3) & 2) == 0 || _InterlockedAdd(&gFwpL2, 1u) < 0 )
    {
LABEL_45:
      v16 = v6[45];
      FwppFreeWfpNblInfo(v6);
      FwppSetPacketInfo(netBufferList, 0);
      if ( v16 )
      {
        FwppFreeDeepCloneNetBufferList(netBufferList);
        return;
      }
      goto LABEL_47;
    }
    memset(&LockHandle, 0, sizeof(LockHandle));
    CurrentIrql = KeGetCurrentIrql();
    KeAcquireInStackQueuedSpinLock(&qword_1800481C0, &LockHandle);
    if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
    {
      v10 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
      *(_QWORD *)(v10 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v10 = 4;
    }
    v11 = (_QWORD *)WfpNblInfoGet(v3);
    v12 = v11;
    if ( !v11 || (v13 = MmBadPointer, v11 == MmBadPointer) )
    {
      v14 = MmBadPointer;
      if ( v12 != MmBadPointer )
      {
LABEL_40:
        FwppDereferenceNetBufferListCommon(v3, 0);
        if ( WPP_MAIN_CB.DeviceExtension )
        {
          v15 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension
                           + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
          if ( *v15 == 4 )
            *v15 = 0;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        _InterlockedDecrement(&dword_180048700);
        (*((void (__fastcall **)(PNET_BUFFER_LIST))qword_180048108 + 3))(v3);
LABEL_44:
        _InterlockedDecrement(&gFwpL2);
        goto LABEL_45;
      }
      v13 = MmBadPointer;
    }
    else
    {
      v14 = (_DWORD *)v11[1];
    }
    if ( v14 )
    {
      if ( v14 != v13 && v14[1] == 2 )
      {
        v19 = 0;
        (*((void (__fastcall **)(PNET_BUFFER_LIST, _QWORD, PVOID *))qword_180048108 + 5))(v3, 0, &v19);
        if ( v19 )
          ExFreeToNPagedLookasideList(&stru_180048140, v19);
      }
    }
    goto LABEL_40;
  }
}

```

## disassembly

```asm
0x18000aec0  test    rcx, rcx
0x18000aec3  jz      locret_18000B287
0x18000aec9  push    rdi
0x18000aeca  push    r12
0x18000aecc  push    r15
0x18000aece  sub     rsp, 50h
0x18000aed2  xor     r12d, r12d
0x18000aed5  mov     [rsp+68h+arg_18], rbp
0x18000aedd  mov     [rsp+68h+var_20], rsi
0x18000aee2  mov     r15d, edx
0x18000aee5  mov     [rsp+68h+Entry], r12
0x18000aeea  mov     esi, r12d
0x18000aeed  mov     rdi, rcx
0x18000aef0  call    cs:__imp_WfpNblInfoGet
0x18000aef7  nop     dword ptr [rax+rax+00h]
0x18000aefc  mov     r8, rax
0x18000aeff  test    rax, rax
0x18000af02  jz      short loc_18000AF16
0x18000af04  mov     rdx, cs:MmBadPointer
0x18000af0b  cmp     rax, [rdx]
0x18000af0e  jz      short loc_18000AF16
0x18000af10  mov     rbp, [rax+8]
0x18000af14  jmp     short loc_18000AF2A
0x18000af16  mov     rax, cs:MmBadPointer
0x18000af1d  mov     rbp, r12
0x18000af20  mov     rcx, [rax]
0x18000af23  cmp     r8, rcx
0x18000af26  cmovz   rbp, rcx
0x18000af2a  lock dec cs:dword_180048700
0x18000af31  mov     rax, [rdi+18h]
0x18000af35  test    rax, rax
0x18000af38  jz      short loc_18000AF48
0x18000af3a  lock dec dword ptr [rax+84h]
0x18000af41  mov     rsi, rax
0x18000af44  mov     [rdi+18h], r12
0x18000af48  test    rbp, rbp
0x18000af4b  jz      loc_18000B25F
0x18000af51  mov     rax, cs:MmBadPointer
0x18000af58  cmp     rbp, [rax]
0x18000af5b  jz      loc_18000B25F
0x18000af61  mov     [rsp+68h+arg_8], rbx
0x18000af66  mov     rcx, rdi
0x18000af69  mov     [rsp+68h+var_28], r14
0x18000af6e  call    cs:__imp_WfpNblInfoGetFlags
0x18000af75  nop     dword ptr [rax+rax+00h]
0x18000af7a  test    al, 1
0x18000af7c  jz      short loc_18000AFE2
0x18000af7e  mov     r14b, 1
0x18000af81  cmp     [rbp+0B0h], r12d
0x18000af88  jz      short loc_18000AFC3
0x18000af8a  mov     rdx, [rdi+58h]; Entry
0x18000af8e  mov     [rsp+68h+Entry], rdx
0x18000af93  test    rdx, rdx
0x18000af96  jz      loc_18000B228
0x18000af9c  lea     rcx, stru_180048240; Lookaside
0x18000afa3  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000afaa  nop     dword ptr [rax+rax+00h]
0x18000afaf  mov     rax, 0BADBADFABADBADFAh
0x18000afb9  mov     [rsp+68h+Entry], rax
0x18000afbe  jmp     loc_18000B228
0x18000afc3  test    rsi, rsi
0x18000afc6  jz      loc_18000B228
0x18000afcc  xor     edx, edx
0x18000afce  mov     rcx, rsi
0x18000afd1  call    cs:__imp_NetioDereferenceNetBufferList
0x18000afd8  nop     dword ptr [rax+rax+00h]
0x18000afdd  jmp     loc_18000B228
0x18000afe2  mov     rcx, rdi
0x18000afe5  xor     r14b, r14b
0x18000afe8  call    cs:__imp_WfpNblInfoGetFlags
0x18000afef  nop     dword ptr [rax+rax+00h]
0x18000aff4  test    al, 2
0x18000aff6  jz      short loc_18000B05F
0x18000aff8  lock add cs:gFwpL2, 1
0x18000b000  js      loc_18000B228
0x18000b006  mov     rax, cs:qword_180048108
0x18000b00d  lea     r8, [rsp+68h+Entry]
0x18000b012  xor     edx, edx
0x18000b014  mov     rcx, rdi
0x18000b017  mov     rax, [rax+28h]
0x18000b01b  call    _guard_dispatch_icall
0x18000b020  mov     rdx, [rsp+68h+Entry]; Entry
0x18000b025  test    rdx, rdx
0x18000b028  jz      short loc_18000B04C
0x18000b02a  lea     rcx, stru_180048140; Lookaside
0x18000b031  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000b038  nop     dword ptr [rax+rax+00h]
0x18000b03d  mov     rax, 0BADBADFABADBADFAh
0x18000b047  mov     [rsp+68h+Entry], rax
0x18000b04c  mov     rax, cs:qword_180048108
0x18000b053  mov     rcx, rdi
0x18000b056  mov     rax, [rax+8]
0x18000b05a  jmp     loc_18000B21C
0x18000b05f  test    rsi, rsi
0x18000b062  jz      loc_18000B228
0x18000b068  mov     rcx, rsi
0x18000b06b  call    cs:__imp_WfpNblInfoGetFlags
0x18000b072  nop     dword ptr [rax+rax+00h]
0x18000b077  mov     rcx, rsi
0x18000b07a  test    al, 1
0x18000b07c  jz      short loc_18000B08A
0x18000b07e  xor     edx, edx
0x18000b080  call    FwppDereferenceNetioNetBufferList
0x18000b085  jmp     loc_18000B228
0x18000b08a  call    cs:__imp_WfpNblInfoGetFlags
0x18000b091  nop     dword ptr [rax+rax+00h]
0x18000b096  test    al, 2
0x18000b098  jz      loc_18000B228
0x18000b09e  lock add cs:gFwpL2, 1
0x18000b0a6  js      loc_18000B228
0x18000b0ac  xorps   xmm0, xmm0
0x18000b0af  xor     eax, eax
0x18000b0b1  movups  xmmword ptr [rsp+68h+LockHandle.LockQueue.Next], xmm0
0x18000b0b6  mov     qword ptr [rsp+68h+LockHandle.OldIrql], rax
0x18000b0bb  call    cs:__imp_KeGetCurrentIrql
0x18000b0c2  nop     dword ptr [rax+rax+00h]
0x18000b0c7  lea     rdx, [rsp+68h+LockHandle]; LockHandle
0x18000b0cc  movzx   ebx, al
0x18000b0cf  lea     rcx, qword_1800481C0; SpinLock
0x18000b0d6  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x18000b0dd  nop     dword ptr [rax+rax+00h]
0x18000b0e2  cmp     bl, 2
0x18000b0e5  jz      short loc_18000B126
0x18000b0e7  cmp     cs:WPP_MAIN_CB.DeviceExtension, r12
0x18000b0ee  jz      short loc_18000B126
0x18000b0f0  xor     ecx, ecx; ProcNumber
0x18000b0f2  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x18000b0f9  nop     dword ptr [rax+rax+00h]
0x18000b0fe  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x18000b105  mov     ecx, eax
0x18000b107  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000b10e  mov     rdx, [rcx+rax]
0x18000b112  mov     rax, ds:0FFFFF78000000008h
0x18000b11c  mov     [rdx+8], rax
0x18000b120  mov     dword ptr [rdx], 4
0x18000b126  mov     rcx, rsi
0x18000b129  call    cs:__imp_WfpNblInfoGet
0x18000b130  nop     dword ptr [rax+rax+00h]
0x18000b135  mov     rdx, rax
0x18000b138  test    rax, rax
0x18000b13b  jz      short loc_18000B152
0x18000b13d  mov     rcx, cs:MmBadPointer
0x18000b144  mov     r8, [rcx]
0x18000b147  cmp     rax, r8
0x18000b14a  jz      short loc_18000B152
0x18000b14c  mov     rax, [rax+8]
0x18000b150  jmp     short loc_18000B164
0x18000b152  mov     rax, cs:MmBadPointer
0x18000b159  mov     rax, [rax]
0x18000b15c  cmp     rdx, rax
0x18000b15f  jnz     short loc_18000B1B9
0x18000b161  mov     r8, rax
0x18000b164  test    rax, rax
0x18000b167  jz      short loc_18000B1B9
0x18000b169  cmp     rax, r8
0x18000b16c  jz      short loc_18000B1B9
0x18000b16e  cmp     dword ptr [rax+4], 2
0x18000b172  jnz     short loc_18000B1B9
0x18000b174  mov     rax, cs:qword_180048108
0x18000b17b  lea     r8, [rsp+68h+arg_10]
0x18000b183  mov     [rsp+68h+arg_10], r12
0x18000b18b  xor     edx, edx
0x18000b18d  mov     rcx, rsi
0x18000b190  mov     rax, [rax+28h]
0x18000b194  call    _guard_dispatch_icall
0x18000b199  mov     rdx, [rsp+68h+arg_10]; Entry
0x18000b1a1  test    rdx, rdx
0x18000b1a4  jz      short loc_18000B1B9
0x18000b1a6  lea     rcx, stru_180048140; Lookaside
0x18000b1ad  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000b1b4  nop     dword ptr [rax+rax+00h]
0x18000b1b9  xor     edx, edx
0x18000b1bb  mov     rcx, rsi
0x18000b1be  call    FwppDereferenceNetBufferListCommon
0x18000b1c3  cmp     cs:WPP_MAIN_CB.DeviceExtension, r12
0x18000b1ca  jz      short loc_18000B1F6
0x18000b1cc  xor     ecx, ecx; ProcNumber
0x18000b1ce  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x18000b1d5  nop     dword ptr [rax+rax+00h]
0x18000b1da  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x18000b1e1  mov     ecx, eax
0x18000b1e3  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000b1ea  mov     rdx, [rcx+rax]
0x18000b1ee  cmp     dword ptr [rdx], 4
0x18000b1f1  jnz     short loc_18000B1F6
0x18000b1f3  mov     [rdx], r12d
0x18000b1f6  lea     rcx, [rsp+68h+LockHandle]; LockHandle
0x18000b1fb  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x18000b202  nop     dword ptr [rax+rax+00h]
0x18000b207  lock dec cs:dword_180048700
0x18000b20e  mov     rcx, rsi
0x18000b211  mov     rax, cs:qword_180048108
0x18000b218  mov     rax, [rax+18h]
0x18000b21c  call    _guard_dispatch_icall
0x18000b221  lock dec cs:gFwpL2
0x18000b228  mov     ebx, [rbp+0B4h]
0x18000b22e  mov     r8, rdi
0x18000b231  movzx   edx, r14b
0x18000b235  mov     rcx, rbp; Entry
0x18000b238  call    FwppFreeWfpNblInfo
0x18000b23d  xor     edx, edx
0x18000b23f  mov     rcx, rdi
0x18000b242  call    FwppSetPacketInfo
0x18000b247  mov     r14, [rsp+68h+var_28]
0x18000b24c  test    ebx, ebx
0x18000b24e  mov     rbx, [rsp+68h+arg_8]
0x18000b253  jz      short loc_18000B25F
0x18000b255  mov     rcx, rdi; CloneNetBufferList
0x18000b258  call    FwppFreeDeepCloneNetBufferList
0x18000b25d  jmp     short loc_18000B271
0x18000b25f  mov     edx, r15d; FreeCloneFlags
0x18000b262  mov     rcx, rdi; CloneNetBufferList
0x18000b265  call    cs:__imp_NdisFreeCloneNetBufferList
0x18000b26c  nop     dword ptr [rax+rax+00h]
0x18000b271  mov     rbp, [rsp+68h+arg_18]
0x18000b279  mov     rsi, [rsp+68h+var_20]
0x18000b27e  add     rsp, 50h
0x18000b282  pop     r15
0x18000b284  pop     r12
0x18000b286  pop     rdi
0x18000b287  retn
```
