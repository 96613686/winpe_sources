# FwpsDereferenceNetBufferList0

- ea: `0x18000ace0`
- end: `0x18000aeba`
- name: `FwpsDereferenceNetBufferList0`
- size: `474`
- prototype: `void __stdcall(NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)`
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007080`
- `0x180007350`
- `0x18000ace0`
- `0x180020400`

## import_xrefs

- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000ad80`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000ae55`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000ad80`
- `ntoskrnl!KeGetCurrentProcessorNumberEx` at `0x18000ae55`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18000ad63`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x18000ad63`
- `ntoskrnl!MmBadPointer` at `0x18000adcd`
- `ntoskrnl!MmBadPointer` at `0x18000ade2`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000ae81`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x18000ae81`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000ad48`
- `ntoskrnl!KeGetCurrentIrql` at `0x18000ad48`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000ae34`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x18000ae34`
- `NETIO!WfpNblInfoGet` at `0x18000adb7`
- `NETIO!WfpNblInfoGet` at `0x18000adb7`
- `NETIO!WfpNblInfoGetFlags` at `0x18000acf0`
- `NETIO!WfpNblInfoGetFlags` at `0x18000ad17`
- `NETIO!WfpNblInfoGetFlags` at `0x18000acf0`
- `NETIO!WfpNblInfoGetFlags` at `0x18000ad17`

## pseudocode

```c
void __stdcall FwpsDereferenceNetBufferList0(NET_BUFFER_LIST *netBufferList, BOOLEAN dispatchLevel)
{
  KIRQL CurrentIrql; // bl
  __int64 v5; // rdx
  _QWORD *v6; // rax
  PVOID v7; // rdx
  _DWORD *v8; // r8
  _DWORD *v9; // rax
  _DWORD *v10; // rdx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+20h] [rbp-28h] BYREF
  PVOID Entry; // [rsp+60h] [rbp+18h] BYREF

  if ( (WfpNblInfoGetFlags(netBufferList) & 1) != 0 )
  {
    FwppDereferenceNetioNetBufferList(netBufferList, dispatchLevel);
    return;
  }
  if ( (WfpNblInfoGetFlags(netBufferList) & 2) != 0 && _InterlockedAdd(&gFwpL2, 1u) >= 0 )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    CurrentIrql = KeGetCurrentIrql();
    KeAcquireInStackQueuedSpinLock(&qword_1800481C0, &LockHandle);
    if ( CurrentIrql != 2 && WPP_MAIN_CB.DeviceExtension )
    {
      v5 = *(_QWORD *)((char *)WPP_MAIN_CB.DeviceExtension + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
      *(_QWORD *)(v5 + 8) = MEMORY[0xFFFFF78000000008];
      *(_DWORD *)v5 = 4;
    }
    v6 = (_QWORD *)WfpNblInfoGet(netBufferList);
    v7 = v6;
    if ( !v6 || (v8 = MmBadPointer, v6 == MmBadPointer) )
    {
      v9 = MmBadPointer;
      if ( v7 != MmBadPointer )
      {
LABEL_18:
        FwppDereferenceNetBufferListCommon(netBufferList, 0);
        if ( WPP_MAIN_CB.DeviceExtension )
        {
          v10 = *(_DWORD **)((char *)WPP_MAIN_CB.DeviceExtension
                           + WPP_MAIN_CB.DeviceType * KeGetCurrentProcessorNumberEx(0));
          if ( *v10 == 4 )
            *v10 = 0;
        }
        KeReleaseInStackQueuedSpinLock(&LockHandle);
        _InterlockedDecrement(&dword_180048700);
        (*((void (__fastcall **)(NET_BUFFER_LIST *))qword_180048108 + 3))(netBufferList);
        _InterlockedDecrement(&gFwpL2);
        return;
      }
      v8 = MmBadPointer;
    }
    else
    {
      v9 = (_DWORD *)v6[1];
    }
    if ( v9 )
    {
      if ( v9 != v8 && v9[1] == 2 )
      {
        Entry = 0;
        (*((void (__fastcall **)(NET_BUFFER_LIST *, _QWORD, PVOID *))qword_180048108 + 5))(netBufferList, 0, &Entry);
        if ( Entry )
          ExFreeToNPagedLookasideList(&stru_180048140, Entry);
      }
    }
    goto LABEL_18;
  }
}

```

## disassembly

```asm
0x18000ace0  mov     [rsp+arg_0], rbx
0x18000ace5  push    rdi
0x18000ace6  sub     rsp, 40h
0x18000acea  movzx   ebx, dl
0x18000aced  mov     rdi, rcx
0x18000acf0  call    cs:__imp_WfpNblInfoGetFlags
0x18000acf7  nop     dword ptr [rax+rax+00h]
0x18000acfc  mov     rcx, rdi
0x18000acff  test    al, 1
0x18000ad01  jz      short loc_18000AD17
0x18000ad03  movzx   edx, bl
0x18000ad06  call    FwppDereferenceNetioNetBufferList
0x18000ad0b  mov     rbx, [rsp+48h+arg_0]
0x18000ad10  add     rsp, 40h
0x18000ad14  pop     rdi
0x18000ad15  retn
0x18000ad17  call    cs:__imp_WfpNblInfoGetFlags
0x18000ad1e  nop     dword ptr [rax+rax+00h]
0x18000ad23  test    al, 2
0x18000ad25  jz      loc_18000AEAE
0x18000ad2b  lock add cs:gFwpL2, 1
0x18000ad33  js      loc_18000AEAE
0x18000ad39  xorps   xmm0, xmm0
0x18000ad3c  xor     eax, eax
0x18000ad3e  movups  xmmword ptr [rsp+48h+LockHandle.LockQueue.Next], xmm0
0x18000ad43  mov     qword ptr [rsp+48h+LockHandle.OldIrql], rax
0x18000ad48  call    cs:__imp_KeGetCurrentIrql
0x18000ad4f  nop     dword ptr [rax+rax+00h]
0x18000ad54  lea     rdx, [rsp+48h+LockHandle]; LockHandle
0x18000ad59  movzx   ebx, al
0x18000ad5c  lea     rcx, qword_1800481C0; SpinLock
0x18000ad63  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x18000ad6a  nop     dword ptr [rax+rax+00h]
0x18000ad6f  cmp     bl, 2
0x18000ad72  jz      short loc_18000ADB4
0x18000ad74  cmp     cs:WPP_MAIN_CB.DeviceExtension, 0
0x18000ad7c  jz      short loc_18000ADB4
0x18000ad7e  xor     ecx, ecx; ProcNumber
0x18000ad80  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x18000ad87  nop     dword ptr [rax+rax+00h]
0x18000ad8c  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x18000ad93  mov     ecx, eax
0x18000ad95  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000ad9c  mov     rdx, [rcx+rax]
0x18000ada0  mov     rax, ds:0FFFFF78000000008h
0x18000adaa  mov     [rdx+8], rax
0x18000adae  mov     dword ptr [rdx], 4
0x18000adb4  mov     rcx, rdi
0x18000adb7  call    cs:__imp_WfpNblInfoGet
0x18000adbe  nop     dword ptr [rax+rax+00h]
0x18000adc3  xor     ebx, ebx
0x18000adc5  mov     rdx, rax
0x18000adc8  test    rax, rax
0x18000adcb  jz      short loc_18000ADE2
0x18000adcd  mov     rcx, cs:MmBadPointer
0x18000add4  mov     r8, [rcx]
0x18000add7  cmp     rax, r8
0x18000adda  jz      short loc_18000ADE2
0x18000addc  mov     rax, [rax+8]
0x18000ade0  jmp     short loc_18000ADF4
0x18000ade2  mov     rax, cs:MmBadPointer
0x18000ade9  mov     rax, [rax]
0x18000adec  cmp     rdx, rax
0x18000adef  jnz     short loc_18000AE40
0x18000adf1  mov     r8, rax
0x18000adf4  test    rax, rax
0x18000adf7  jz      short loc_18000AE40
0x18000adf9  cmp     rax, r8
0x18000adfc  jz      short loc_18000AE40
0x18000adfe  cmp     dword ptr [rax+4], 2
0x18000ae02  jnz     short loc_18000AE40
0x18000ae04  mov     rax, cs:qword_180048108
0x18000ae0b  lea     r8, [rsp+48h+Entry]
0x18000ae10  mov     [rsp+48h+Entry], rbx
0x18000ae15  xor     edx, edx
0x18000ae17  mov     rcx, rdi
0x18000ae1a  mov     rax, [rax+28h]
0x18000ae1e  call    _guard_dispatch_icall
0x18000ae23  mov     rdx, [rsp+48h+Entry]; Entry
0x18000ae28  test    rdx, rdx
0x18000ae2b  jz      short loc_18000AE40
0x18000ae2d  lea     rcx, stru_180048140; Lookaside
0x18000ae34  call    cs:__imp_ExFreeToNPagedLookasideList
0x18000ae3b  nop     dword ptr [rax+rax+00h]
0x18000ae40  xor     edx, edx
0x18000ae42  mov     rcx, rdi
0x18000ae45  call    FwppDereferenceNetBufferListCommon
0x18000ae4a  cmp     cs:WPP_MAIN_CB.DeviceExtension, rbx
0x18000ae51  jz      short loc_18000AE7C
0x18000ae53  xor     ecx, ecx; ProcNumber
0x18000ae55  call    cs:__imp_KeGetCurrentProcessorNumberEx
0x18000ae5c  nop     dword ptr [rax+rax+00h]
0x18000ae61  imul    eax, cs:WPP_MAIN_CB.DeviceType
0x18000ae68  mov     ecx, eax
0x18000ae6a  mov     rax, cs:WPP_MAIN_CB.DeviceExtension
0x18000ae71  mov     rdx, [rcx+rax]
0x18000ae75  cmp     dword ptr [rdx], 4
0x18000ae78  jnz     short loc_18000AE7C
0x18000ae7a  mov     [rdx], ebx
0x18000ae7c  lea     rcx, [rsp+48h+LockHandle]; LockHandle
0x18000ae81  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x18000ae88  nop     dword ptr [rax+rax+00h]
0x18000ae8d  lock dec cs:dword_180048700
0x18000ae94  mov     rcx, rdi
0x18000ae97  mov     rax, cs:qword_180048108
0x18000ae9e  mov     rax, [rax+18h]
0x18000aea2  call    _guard_dispatch_icall
0x18000aea7  lock dec cs:gFwpL2
0x18000aeae  mov     rbx, [rsp+48h+arg_0]
0x18000aeb3  add     rsp, 40h
0x18000aeb7  pop     rdi
0x18000aeb8  retn
```
