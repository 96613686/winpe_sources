# WimCbDismountVolume

- ea: `0x140026c00`
- end: `0x140026d42`
- name: `WimCbDismountVolume`
- size: `322`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x14000fb90`
- `0x140022cf4`
- `0x140022e2c`
- `0x140026c00`
- `0x14002df00`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026d2b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140026d2b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c7f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026cd7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026d1f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026c7f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026cd7`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140026d1f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026c46`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140026c46`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c5e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026ca4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026cff`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026c5e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026ca4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140026cff`

## pseudocode

```c
void __fastcall WimCbDismountVolume(__int64 a1)
{
  _QWORD *i; // rbx
  volatile signed __int32 *v3; // rsi
  volatile signed __int32 *v4; // rbx

  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 8) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_Z(
      WPP_GLOBAL_Control->AttachedDevice,
      20,
      WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids,
      a1 - (unsigned int)dword_14001A2FC + 64);
  KeEnterCriticalRegion();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  for ( i = *(_QWORD **)(a1 + 8); i != (_QWORD *)(a1 + 8); i = (_QWORD *)*i )
  {
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
    WimFSFDismountOverlay(i, 1);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  }
  v3 = *(volatile signed __int32 **)(a1 + 24);
  if ( v3 != (volatile signed __int32 *)(a1 + 24) )
  {
    do
    {
      _InterlockedIncrement(v3 + 14);
      v4 = *(volatile signed __int32 **)v3;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
      WimFSFSuspendOverlaysForBackingFile(v3);
      WimFSFDereferenceBackingFile((PVOID)v3);
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
      v3 = v4;
    }
    while ( v4 != (volatile signed __int32 *)(a1 + 24) );
  }
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a1 - (unsigned int)dword_14001A2FC));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x140026c00  push    rbx
0x140026c02  push    rsi
0x140026c03  push    rdi
0x140026c04  push    r14
0x140026c06  sub     rsp, 28h
0x140026c0a  mov     rdi, rcx
0x140026c0d  mov     rcx, cs:WPP_GLOBAL_Control
0x140026c14  mov     eax, [rcx+2Ch]
0x140026c17  test    al, 8
0x140026c19  jz      short loc_140026C46
0x140026c1b  cmp     byte ptr [rcx+29h], 4
0x140026c1f  jb      short loc_140026C46
0x140026c21  mov     eax, cs:dword_14001A2FC
0x140026c27  lea     r8, WPP_ea753fa6f9d83b7566c7b1a5ff90ffd6_Traceguids
0x140026c2e  mov     rcx, [rcx+18h]
0x140026c32  mov     r9, rdi
0x140026c35  sub     r9, rax
0x140026c38  mov     edx, 14h
0x140026c3d  add     r9, 40h ; '@'
0x140026c41  call    WPP_SF_Z
0x140026c46  call    cs:__imp_KeEnterCriticalRegion
0x140026c4d  nop     dword ptr [rax+rax+00h]
0x140026c52  mov     eax, cs:dword_14001A2FC
0x140026c58  mov     rcx, rdi
0x140026c5b  sub     rcx, rax; FastMutex
0x140026c5e  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026c65  nop     dword ptr [rax+rax+00h]
0x140026c6a  lea     rsi, [rdi+8]
0x140026c6e  mov     rbx, [rsi]
0x140026c71  jmp     short loc_140026CB3
0x140026c73  mov     eax, cs:dword_14001A2FC
0x140026c79  mov     rcx, rdi
0x140026c7c  sub     rcx, rax; FastMutex
0x140026c7f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026c86  nop     dword ptr [rax+rax+00h]
0x140026c8b  mov     edx, 1
0x140026c90  mov     rcx, rbx
0x140026c93  call    WimFSFDismountOverlay
0x140026c98  mov     eax, cs:dword_14001A2FC
0x140026c9e  mov     rcx, rdi
0x140026ca1  sub     rcx, rax; FastMutex
0x140026ca4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026cab  nop     dword ptr [rax+rax+00h]
0x140026cb0  mov     rbx, [rbx]
0x140026cb3  cmp     rbx, rsi
0x140026cb6  jnz     short loc_140026C73
0x140026cb8  lea     r14, [rdi+18h]
0x140026cbc  mov     rsi, [r14]
0x140026cbf  cmp     rsi, r14
0x140026cc2  jz      short loc_140026D13
0x140026cc4  lock inc dword ptr [rsi+38h]
0x140026cc8  mov     eax, cs:dword_14001A2FC
0x140026cce  mov     rcx, rdi
0x140026cd1  mov     rbx, [rsi]
0x140026cd4  sub     rcx, rax; FastMutex
0x140026cd7  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026cde  nop     dword ptr [rax+rax+00h]
0x140026ce3  mov     rcx, rsi
0x140026ce6  call    WimFSFSuspendOverlaysForBackingFile
0x140026ceb  mov     rcx, rsi; P
0x140026cee  call    WimFSFDereferenceBackingFile
0x140026cf3  mov     eax, cs:dword_14001A2FC
0x140026cf9  mov     rcx, rdi
0x140026cfc  sub     rcx, rax; FastMutex
0x140026cff  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140026d06  nop     dword ptr [rax+rax+00h]
0x140026d0b  mov     rsi, rbx
0x140026d0e  cmp     rbx, r14
0x140026d11  jnz     short loc_140026CC4
0x140026d13  mov     eax, cs:dword_14001A2FC
0x140026d19  sub     rdi, rax
0x140026d1c  mov     rcx, rdi; FastMutex
0x140026d1f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140026d26  nop     dword ptr [rax+rax+00h]
0x140026d2b  call    cs:__imp_KeLeaveCriticalRegion
0x140026d32  nop     dword ptr [rax+rax+00h]
0x140026d37  add     rsp, 28h
0x140026d3b  pop     r14
0x140026d3d  pop     rdi
0x140026d3e  pop     rsi
0x140026d3f  pop     rbx
0x140026d40  retn
```
