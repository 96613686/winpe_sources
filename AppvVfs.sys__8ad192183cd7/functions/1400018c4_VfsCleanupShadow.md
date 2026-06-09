# VfsCleanupShadow

- ea: `0x1400018c4`
- end: `0x1400019e2`
- name: `VfsCleanupShadow`
- size: `286`
- prototype: `__int64 __fastcall(__int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x1400011c0`

## callees

- `0x1400018c4`
- `0x140005dc8`
- `0x140007a14`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140001937`
- `ntoskrnl!IoRemoveShareAccess` at `0x140001937`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001962`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001962`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001956`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001956`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400018ec`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400018ec`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018da`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400018da`
- `FLTMGR!FltClose` at `0x140001994`
- `FLTMGR!FltClose` at `0x1400019ad`
- `FLTMGR!FltClose` at `0x140001994`
- `FLTMGR!FltClose` at `0x1400019ad`

## pseudocode

```c
__int64 __fastcall VfsCleanupShadow(__int64 a1, __int64 a2, __int64 a3)
{
  __int64 v3; // rbx
  __int64 v7; // r9
  _QWORD *v8; // rax
  void *v9; // rcx
  void *v10; // rcx
  void *v11; // rcx

  v3 = *(_QWORD *)(a2 + 120);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v3 + 56), 1u);
  v7 = *(_QWORD *)(a3 + 8);
  if ( *(_QWORD *)(v7 + 8) != a3 + 8 || (v8 = *(_QWORD **)(a3 + 16), *v8 != a3 + 8) )
    __fastfail(3u);
  *v8 = v7;
  *(_QWORD *)(v7 + 8) = v8;
  *(_DWORD *)(a3 + 4) &= ~1u;
  if ( (*(_DWORD *)(a3 + 4) & 0x20) != 0 )
  {
    IoRemoveShareAccess(*(PFILE_OBJECT *)(a3 + 96), (PSHARE_ACCESS)(*(_QWORD *)(a3 + 24) + 284LL));
    *(_DWORD *)(a3 + 4) &= ~0x20u;
  }
  _InterlockedDecrement((volatile signed __int32 *)(a2 + 280));
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 120) + 56LL));
  KeLeaveCriticalRegion();
  VfsProcessDeleteOnCleanupShadow(a1, a2, a3);
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 16) + 8LL) + 80LL) |= 0x4000u;
  v9 = *(void **)(a3 + 56);
  if ( v9 )
  {
    FltClose(v9);
    *(_QWORD *)(a3 + 56) = 0;
  }
  v10 = *(void **)(a3 + 80);
  if ( v10 )
  {
    FltClose(v10);
    *(_QWORD *)(a3 + 80) = 0;
  }
  v11 = *(void **)(a3 + 120);
  if ( v11 )
  {
    VfsDeleteDirQueryContext(v11);
    *(_QWORD *)(a3 + 120) = 0;
  }
  return 0;
}

```

## disassembly

```asm
0x1400018c4  push    rbx
0x1400018c6  push    rbp
0x1400018c7  push    rsi
0x1400018c8  push    rdi
0x1400018c9  sub     rsp, 28h
0x1400018cd  mov     rbx, [rdx+78h]
0x1400018d1  mov     rdi, r8
0x1400018d4  mov     rsi, rdx
0x1400018d7  mov     rbp, rcx
0x1400018da  call    cs:__imp_KeEnterCriticalRegion
0x1400018e1  nop     dword ptr [rax+rax+00h]
0x1400018e6  mov     dl, 1; Wait
0x1400018e8  lea     rcx, [rbx+38h]; Resource
0x1400018ec  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400018f3  nop     dword ptr [rax+rax+00h]
0x1400018f8  lea     r8, [rdi+8]
0x1400018fc  mov     r9, [r8]
0x1400018ff  cmp     [r9+8], r8
0x140001903  jnz     loc_1400019DB
0x140001909  mov     rax, [r8+8]
0x14000190d  cmp     [rax], r8
0x140001910  jnz     loc_1400019DB
0x140001916  mov     [rax], r9
0x140001919  mov     [r9+8], rax
0x14000191d  and     dword ptr [rdi+4], 0FFFFFFFEh
0x140001921  mov     eax, [rdi+4]
0x140001924  test    al, 20h
0x140001926  jz      short loc_140001947
0x140001928  mov     rdx, [rdi+18h]
0x14000192c  mov     rcx, [rdi+60h]; FileObject
0x140001930  add     rdx, 11Ch; ShareAccess
0x140001937  call    cs:__imp_IoRemoveShareAccess
0x14000193e  nop     dword ptr [rax+rax+00h]
0x140001943  and     dword ptr [rdi+4], 0FFFFFFDFh
0x140001947  lock dec dword ptr [rsi+118h]
0x14000194e  mov     rcx, [rsi+78h]
0x140001952  add     rcx, 38h ; '8'; Resource
0x140001956  call    cs:__imp_ExReleaseResourceLite
0x14000195d  nop     dword ptr [rax+rax+00h]
0x140001962  call    cs:__imp_KeLeaveCriticalRegion
0x140001969  nop     dword ptr [rax+rax+00h]
0x14000196e  mov     r8, rdi
0x140001971  mov     rdx, rsi
0x140001974  mov     rcx, rbp
0x140001977  call    VfsProcessDeleteOnCleanupShadow
0x14000197c  mov     rax, [rbp+10h]
0x140001980  xor     ebx, ebx
0x140001982  mov     rcx, [rax+8]
0x140001986  bts     dword ptr [rcx+50h], 0Eh
0x14000198b  mov     rcx, [rdi+38h]; FileHandle
0x14000198f  test    rcx, rcx
0x140001992  jz      short loc_1400019A4
0x140001994  call    cs:__imp_FltClose
0x14000199b  nop     dword ptr [rax+rax+00h]
0x1400019a0  mov     [rdi+38h], rbx
0x1400019a4  mov     rcx, [rdi+50h]; FileHandle
0x1400019a8  test    rcx, rcx
0x1400019ab  jz      short loc_1400019BD
0x1400019ad  call    cs:__imp_FltClose
0x1400019b4  nop     dword ptr [rax+rax+00h]
0x1400019b9  mov     [rdi+50h], rbx
0x1400019bd  mov     rcx, [rdi+78h]; Entry
0x1400019c1  test    rcx, rcx
0x1400019c4  jz      short loc_1400019CF
0x1400019c6  call    VfsDeleteDirQueryContext
0x1400019cb  mov     [rdi+78h], rbx
0x1400019cf  xor     eax, eax
0x1400019d1  add     rsp, 28h
0x1400019d5  pop     rdi
0x1400019d6  pop     rsi
0x1400019d7  pop     rbp
0x1400019d8  pop     rbx
0x1400019d9  retn
0x1400019db  mov     ecx, 3
0x1400019e0  int     29h; Win8: RtlFailFast(ecx)
```
