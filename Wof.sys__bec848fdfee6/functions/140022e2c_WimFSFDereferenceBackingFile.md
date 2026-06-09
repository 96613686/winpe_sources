# WimFSFDereferenceBackingFile

- ea: `0x140022e2c`
- end: `0x140022fc4`
- name: `WimFSFDereferenceBackingFile`
- size: `408`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `5`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140022cf4`
- `0x140026c00`
- `0x140029130`
- `0x1400296d4`
- `0x14002c58c`

## callees

- `0x14000d3fc`
- `0x140022e2c`
- `0x14002881c`
- `0x14002ce9c`
- `0x14002df84`

## import_xrefs

- `ntoskrnl!KeFreeCalloutStack` at `0x140022f57`
- `ntoskrnl!KeFreeCalloutStack` at `0x140022f57`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022e6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022eb5`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022e6e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140022eb5`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022e62`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022ea9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022e62`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140022ea9`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022faa`
- `ntoskrnl!ExFreePoolWithTag` at `0x140022faa`
- `ntoskrnl!ObfDereferenceObject` at `0x140022efd`
- `ntoskrnl!ObfDereferenceObject` at `0x140022efd`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022e35`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140022e35`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022e45`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140022e45`
- `FLTMGR!FltDeletePushLock` at `0x140022f91`
- `FLTMGR!FltDeletePushLock` at `0x140022f91`
- `FLTMGR!FltClose` at `0x140022f15`
- `FLTMGR!FltClose` at `0x140022f15`

## pseudocode

```c
void __fastcall WimFSFDereferenceBackingFile(PVOID P)
{
  PFAST_MUTEX v2; // rax
  PVOID *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx

  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe(*((PFAST_MUTEX *)P + 5));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 14, 0xFFFFFFFF) == 1 )
  {
    v2 = *(PFAST_MUTEX *)P;
    if ( *(PVOID *)P != P )
    {
      if ( v2->Owner != P || (v3 = (PVOID *)*((_QWORD *)P + 1), *v3 != P) )
        __fastfail(3u);
      *v3 = v2;
      v2->Owner = v3;
    }
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)P + 5));
    KeLeaveCriticalRegion();
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids, P);
    if ( *((_QWORD *)P + 8) )
    {
      v4 = (void *)*((_QWORD *)P + 9);
      if ( v4 )
      {
        ObfDereferenceObject(v4);
        *((_QWORD *)P + 9) = 0;
      }
      FltClose(*((HANDLE *)P + 8));
      *((_QWORD *)P + 8) = 0;
    }
    v5 = (void *)*((_QWORD *)P + 122);
    if ( v5 )
    {
      WimFSFDestroyOffsetTable(v5);
      *((_QWORD *)P + 122) = 0;
    }
    if ( *((_QWORD *)P + 129) )
    {
      KeFreeCalloutStack();
      *((_QWORD *)P + 129) = 0;
    }
    v6 = (void *)*((_QWORD *)P + 127);
    if ( v6 )
    {
      WimFSFDestroyIntegrity(v6);
      *((_QWORD *)P + 127) = 0;
    }
    FltDeletePushLock((PULONG_PTR)P + 126);
    WimFSFUnInitializeDecompressionWorkspace(P);
    ExFreePoolWithTag(P, 0);
  }
  else
  {
    ExReleaseFastMutexUnsafe(*((PFAST_MUTEX *)P + 5));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x140022e2c  push    rbx
0x140022e2e  sub     rsp, 20h
0x140022e32  mov     rbx, rcx
0x140022e35  call    cs:__imp_KeEnterCriticalRegion
0x140022e3c  nop     dword ptr [rax+rax+00h]
0x140022e41  mov     rcx, [rbx+28h]; FastMutex
0x140022e45  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140022e4c  nop     dword ptr [rax+rax+00h]
0x140022e51  or      eax, 0FFFFFFFFh
0x140022e54  lock xadd [rbx+38h], eax
0x140022e59  cmp     eax, 1
0x140022e5c  jz      short loc_140022E7F
0x140022e5e  mov     rcx, [rbx+28h]; FastMutex
0x140022e62  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022e69  nop     dword ptr [rax+rax+00h]
0x140022e6e  call    cs:__imp_KeLeaveCriticalRegion
0x140022e75  nop     dword ptr [rax+rax+00h]
0x140022e7a  jmp     loc_140022FB6
0x140022e7f  mov     rax, [rbx]
0x140022e82  cmp     rax, rbx
0x140022e85  jz      short loc_140022EA5
0x140022e87  cmp     [rax+8], rbx
0x140022e8b  jnz     loc_140022FBD
0x140022e91  mov     rcx, [rbx+8]
0x140022e95  cmp     [rcx], rbx
0x140022e98  jnz     loc_140022FBD
0x140022e9e  mov     [rcx], rax
0x140022ea1  mov     [rax+8], rcx
0x140022ea5  mov     rcx, [rbx+28h]; FastMutex
0x140022ea9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140022eb0  nop     dword ptr [rax+rax+00h]
0x140022eb5  call    cs:__imp_KeLeaveCriticalRegion
0x140022ebc  nop     dword ptr [rax+rax+00h]
0x140022ec1  mov     rcx, cs:WPP_GLOBAL_Control
0x140022ec8  mov     eax, [rcx+2Ch]
0x140022ecb  test    al, 8
0x140022ecd  jz      short loc_140022EED
0x140022ecf  cmp     byte ptr [rcx+29h], 2
0x140022ed3  jb      short loc_140022EED
0x140022ed5  mov     rcx, [rcx+18h]
0x140022ed9  lea     r8, WPP_58aa16c06f40368a72f8e1151ea34c8a_Traceguids
0x140022ee0  mov     edx, 1Ch
0x140022ee5  mov     r9, rbx
0x140022ee8  call    WPP_SF_q
0x140022eed  cmp     qword ptr [rbx+40h], 0
0x140022ef2  jz      short loc_140022F29
0x140022ef4  mov     rcx, [rbx+48h]; Object
0x140022ef8  test    rcx, rcx
0x140022efb  jz      short loc_140022F11
0x140022efd  call    cs:__imp_ObfDereferenceObject
0x140022f04  nop     dword ptr [rax+rax+00h]
0x140022f09  mov     qword ptr [rbx+48h], 0
0x140022f11  mov     rcx, [rbx+40h]; FileHandle
0x140022f15  call    cs:__imp_FltClose
0x140022f1c  nop     dword ptr [rax+rax+00h]
0x140022f21  mov     qword ptr [rbx+40h], 0
0x140022f29  mov     rcx, [rbx+3D0h]; P
0x140022f30  test    rcx, rcx
0x140022f33  jz      short loc_140022F4B
0x140022f35  mov     edx, [rbx+3C8h]
0x140022f3b  call    WimFSFDestroyOffsetTable
0x140022f40  mov     qword ptr [rbx+3D0h], 0
0x140022f4b  mov     rcx, [rbx+408h]
0x140022f52  test    rcx, rcx
0x140022f55  jz      short loc_140022F6E
0x140022f57  call    cs:__imp_KeFreeCalloutStack
0x140022f5e  nop     dword ptr [rax+rax+00h]
0x140022f63  mov     qword ptr [rbx+408h], 0
0x140022f6e  mov     rcx, [rbx+3F8h]; P
0x140022f75  test    rcx, rcx
0x140022f78  jz      short loc_140022F8A
0x140022f7a  call    WimFSFDestroyIntegrity
0x140022f7f  mov     qword ptr [rbx+3F8h], 0
0x140022f8a  lea     rcx, [rbx+3F0h]; PushLock
0x140022f91  call    cs:__imp_FltDeletePushLock
0x140022f98  nop     dword ptr [rax+rax+00h]
0x140022f9d  mov     rcx, rbx
0x140022fa0  call    WimFSFUnInitializeDecompressionWorkspace
0x140022fa5  xor     edx, edx; Tag
0x140022fa7  mov     rcx, rbx; P
0x140022faa  call    cs:__imp_ExFreePoolWithTag
0x140022fb1  nop     dword ptr [rax+rax+00h]
0x140022fb6  add     rsp, 20h
0x140022fba  pop     rbx
0x140022fbb  retn
0x140022fbd  mov     ecx, 3
0x140022fc2  int     29h; Win8: RtlFailFast(ecx)
```
