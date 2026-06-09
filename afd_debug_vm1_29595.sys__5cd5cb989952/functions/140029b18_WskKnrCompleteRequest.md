# WskKnrCompleteRequest

- ea: `0x140029b18`
- end: `0x140029cc6`
- name: `WskKnrCompleteRequest`
- size: `430`
- prototype: `__int64 __fastcall(PERESOURCE Resource)`
- caller_count: `7`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140028ac8`
- `0x140028de0`
- `0x140029724`
- `0x140041d20`
- `0x140068330`
- `0x140068640`
- `0x140068df4`

## callees

- `0x14001087c`
- `0x140029b18`
- `0x140029ccc`
- `0x140068d08`
- `0x14009304c`

## import_xrefs

- `ntoskrnl!PsReturnPoolQuota` at `0x140029c6d`
- `ntoskrnl!PsReturnPoolQuota` at `0x140029c6d`
- `ntoskrnl!IofCompleteRequest` at `0x140029bd7`
- `ntoskrnl!IofCompleteRequest` at `0x140029bd7`
- `ntoskrnl!ObfDereferenceObject` at `0x140029c83`
- `ntoskrnl!ObfDereferenceObject` at `0x140029c83`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140029b68`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x140029b68`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140029b4d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140029b4d`

## pseudocode

```c
__int64 __fastcall WskKnrCompleteRequest(PERESOURCE Resource)
{
  struct _LIST_ENTRY *Blink; // rcx
  _DWORD *v3; // rdi
  void *v4; // rcx
  union _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60 *v6; // rax
  __int64 v7; // rdx
  char **OwnerThread; // rcx
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+30h] [rbp-28h] BYREF

  Blink = Resource[1].SystemResourcesList.Blink;
  v3 = &Resource[1].OwnerEntry.8 + 1;
  if ( Blink )
  {
    memset(&LockHandle, 0, sizeof(LockHandle));
    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)&Blink[1].Blink, &LockHandle);
    if ( (*v3 & 8) != 0 )
    {
      v6 = (union _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60 *)&Resource[1].OwnerTable[10].0;
      v7 = *(_QWORD *)&v6->0;
      if ( *(union _OWNER_ENTRY::$818A6BB8E639852A52D20A2B257A1D60 **)(*(_QWORD *)&v6->0 + 8LL) != v6
        || (OwnerThread = (char **)Resource[1].OwnerTable[11].OwnerThread, *OwnerThread != (char *)v6) )
      {
        __fastfail(3u);
      }
      *OwnerThread = (char *)v7;
      *(_QWORD *)(v7 + 8) = OwnerThread;
      *v3 &= ~8u;
    }
    KeReleaseInStackQueuedSpinLock(&LockHandle);
  }
  if ( Resource[1].OwnerEntry.TableSize == -1073610729 )
    Resource[1].OwnerEntry.TableSize = -1073741127;
  v4 = *(void **)&Resource[1].NumberOfSharedWaiters;
  if ( v4 )
  {
    WskKnrReleaseRpcBinding(v4, (PKSPIN_LOCK)(Resource[1].CreatorBackTraceIndex + 24));
    *(_QWORD *)&Resource[1].NumberOfSharedWaiters = 0;
  }
  if ( (*v3 & 4) != 0 )
  {
    PsReturnPoolQuota(*(PEPROCESS *)Resource[1].Reserved2, (POOL_TYPE)512, 0xD8u);
    ObfDereferenceObject(*(PVOID *)Resource[1].Reserved2);
  }
  if ( Resource[1].SystemResourcesList.Blink )
    AfdWskDereferenceClient();
  if ( (BYTE3(xmmword_1400875E0) & 1) != 0 )
    WPP_SF_qD(1048, 18, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids, Resource, Resource[1].OwnerEntry.TableSize);
  LODWORD(Resource[1].OwnerTable[3].OwnerThread) = Resource[1].OwnerEntry.0;
  *(_QWORD *)&Resource[1].OwnerTable[3].0 = 0;
  IofCompleteRequest((PIRP)Resource[1].OwnerTable, 0);
  return WskKnrFreeRequest(Resource);
}

```

## disassembly

```asm
0x140029b18  mov     [rsp+arg_0], rbx
0x140029b1d  push    rdi
0x140029b1e  sub     rsp, 50h
0x140029b22  mov     rbx, rcx
0x140029b25  mov     rcx, [rcx+70h]
0x140029b29  lea     rdi, [rbx+0A4h]
0x140029b30  test    rcx, rcx
0x140029b33  jz      short loc_140029B74
0x140029b35  xorps   xmm0, xmm0
0x140029b38  lea     rdx, [rsp+58h+LockHandle]; LockHandle
0x140029b3d  xor     eax, eax
0x140029b3f  add     rcx, 18h; SpinLock
0x140029b43  movups  xmmword ptr [rsp+58h+LockHandle.LockQueue.Next], xmm0
0x140029b48  mov     qword ptr [rsp+58h+LockHandle.OldIrql], rax
0x140029b4d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140029b54  nop     dword ptr [rax+rax+00h]
0x140029b59  mov     eax, [rdi]
0x140029b5b  test    al, 8
0x140029b5d  jnz     loc_140029BF7
0x140029b63  lea     rcx, [rsp+58h+LockHandle]; LockHandle
0x140029b68  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140029b6f  nop     dword ptr [rax+rax+00h]
0x140029b74  cmp     dword ptr [rbx+0A0h], 0C0020017h
0x140029b7e  jz      loc_140029C29
0x140029b84  mov     rcx, [rbx+0B0h]; P
0x140029b8b  test    rcx, rcx
0x140029b8e  jnz     loc_140029C38
0x140029b94  mov     eax, [rdi]
0x140029b96  test    al, 4
0x140029b98  jnz     loc_140029C58
0x140029b9e  mov     rcx, [rbx+70h]
0x140029ba2  test    rcx, rcx
0x140029ba5  jnz     loc_140029C94
0x140029bab  test    byte ptr cs:xmmword_1400875E0+3, 1
0x140029bb2  jnz     loc_140029C9E
0x140029bb8  mov     rcx, [rbx+78h]
0x140029bbc  xor     edx, edx; PriorityBoost
0x140029bbe  mov     eax, [rbx+0A0h]
0x140029bc4  mov     [rcx+30h], eax
0x140029bc7  mov     rax, [rbx+78h]
0x140029bcb  mov     qword ptr [rax+38h], 0
0x140029bd3  mov     rcx, [rbx+78h]; Irp
0x140029bd7  call    cs:__imp_IofCompleteRequest
0x140029bde  nop     dword ptr [rax+rax+00h]
0x140029be3  mov     rcx, rbx; Resource
0x140029be6  call    WskKnrFreeRequest
0x140029beb  mov     rbx, [rsp+58h+arg_0]
0x140029bf0  add     rsp, 50h
0x140029bf4  pop     rdi
0x140029bf5  retn
0x140029bf7  mov     rax, [rbx+78h]
0x140029bfb  add     rax, 0A8h
0x140029c01  mov     rdx, [rax]
0x140029c04  cmp     [rdx+8], rax
0x140029c08  jnz     short loc_140029C22
0x140029c0a  mov     rcx, [rax+8]
0x140029c0e  cmp     [rcx], rax
0x140029c11  jnz     short loc_140029C22
0x140029c13  mov     [rcx], rdx
0x140029c16  mov     [rdx+8], rcx
0x140029c1a  and     dword ptr [rdi], 0FFFFFFF7h
0x140029c1d  jmp     loc_140029B63
0x140029c22  mov     ecx, 3
0x140029c27  int     29h; Win8: RtlFailFast(ecx)
0x140029c29  mov     dword ptr [rbx+0A0h], 0C00002B9h
0x140029c33  jmp     loc_140029B84
0x140029c38  mov     rdx, [rbx+0C0h]
0x140029c3f  add     rdx, 18h; SpinLock
0x140029c43  call    WskKnrReleaseRpcBinding
0x140029c48  mov     qword ptr [rbx+0B0h], 0
0x140029c53  jmp     loc_140029B94
0x140029c58  mov     rcx, [rbx+0B8h]
0x140029c5f  mov     edx, 200h; PoolType
0x140029c64  mov     r8d, 0D8h; Amount
0x140029c6a  mov     rcx, [rcx]; Process
0x140029c6d  call    cs:__imp_PsReturnPoolQuota
0x140029c74  nop     dword ptr [rax+rax+00h]
0x140029c79  mov     rcx, [rbx+0B8h]
0x140029c80  mov     rcx, [rcx]; Object
0x140029c83  call    cs:__imp_ObfDereferenceObject
0x140029c8a  nop     dword ptr [rax+rax+00h]
0x140029c8f  jmp     loc_140029B9E
0x140029c94  call    AfdWskDereferenceClient
0x140029c99  jmp     loc_140029BAB
0x140029c9e  mov     eax, [rbx+0A0h]
0x140029ca4  lea     r8, WPP_94fe28d3e31530297cd1de9a853d4bda_Traceguids
0x140029cab  mov     edx, 12h
0x140029cb0  mov     [rsp+58h+var_38], eax
0x140029cb4  mov     ecx, 418h
0x140029cb9  mov     r9, rbx
0x140029cbc  call    WPP_SF_qD
0x140029cc1  jmp     loc_140029BB8
```
