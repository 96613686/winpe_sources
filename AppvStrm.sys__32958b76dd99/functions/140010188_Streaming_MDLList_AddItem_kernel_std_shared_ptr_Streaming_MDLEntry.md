# Streaming::MDLList::AddItem(kernel_std::shared_ptr<Streaming::MDLEntry> &)

- ea: `0x140010188`
- end: `0x140010268`
- name: `?AddItem@MDLList@Streaming@@QEAAJAEAV?$shared_ptr@UMDLEntry@Streaming@@@kernel_std@@@Z`
- size: `224`
- prototype: `__int64 __fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x140010270`
- `0x1400105d8`

## callees

- `0x140010188`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010250`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140010250`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010244`
- `ntoskrnl!ExReleaseResourceLite` at `0x140010244`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400101b9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400101b9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400101a6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400101a6`
- `ntoskrnl!ExAllocatePool2` at `0x1400101df`
- `ntoskrnl!ExAllocatePool2` at `0x1400101df`

## pseudocode

```c
__int64 __fastcall Streaming::MDLList::AddItem(__int64 a1, _QWORD *a2)
{
  bool v2; // si
  _QWORD *Pool2; // rax
  _QWORD *v6; // rdx
  __int64 v7; // rax
  __int64 v8; // rcx
  unsigned int v9; // edi
  struct _ERESOURCE *v10; // rcx

  v2 = 0;
  if ( *(_QWORD *)(a1 + 8) )
  {
    KeEnterCriticalRegion();
    v2 = ExAcquireResourceExclusiveLite(*(PERESOURCE *)(a1 + 8), 1u) == 1;
  }
  Pool2 = (_QWORD *)ExAllocatePool2(256, 32, 1634559603);
  v6 = Pool2;
  if ( Pool2 )
  {
    *Pool2 = *a2;
    v7 = a2[1];
    v6[1] = v7;
    if ( v7 )
      _InterlockedAdd((volatile signed __int32 *)(v7 + 8), 1u);
    v6[3] = v6;
    v6[2] = v6;
    ++*(_DWORD *)(a1 + 16);
    v8 = *(_QWORD *)(a1 + 40);
    v9 = 0;
    v6[3] = a1 + 24;
    v6[2] = v8;
    *(_QWORD *)(v8 + 24) = v6;
    *(_QWORD *)(a1 + 40) = v6;
  }
  else
  {
    v9 = -1073741670;
  }
  if ( v2 )
  {
    v10 = *(struct _ERESOURCE **)(a1 + 8);
    if ( v10 )
    {
      ExReleaseResourceLite(v10);
      KeLeaveCriticalRegion();
    }
  }
  return v9;
}

```

## disassembly

```asm
0x140010188  push    rbx
0x14001018a  push    rbp
0x14001018b  push    rsi
0x14001018c  push    rdi
0x14001018d  sub     rsp, 28h
0x140010191  xor     sil, sil
0x140010194  mov     rdi, rdx
0x140010197  cmp     qword ptr [rcx+8], 0
0x14001019c  mov     rbx, rcx
0x14001019f  mov     ebp, 1
0x1400101a4  jz      short loc_1400101CF
0x1400101a6  call    cs:__imp_KeEnterCriticalRegion
0x1400101ad  nop     dword ptr [rax+rax+00h]
0x1400101b2  mov     rcx, [rbx+8]; Resource
0x1400101b6  mov     dl, bpl; Wait
0x1400101b9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400101c0  nop     dword ptr [rax+rax+00h]
0x1400101c5  cmp     al, bpl
0x1400101c8  movzx   esi, sil
0x1400101cc  cmovz   esi, ebp
0x1400101cf  mov     edx, 20h ; ' '
0x1400101d4  mov     ecx, 100h
0x1400101d9  mov     r8d, 616D6673h
0x1400101df  call    cs:__imp_ExAllocatePool2
0x1400101e6  nop     dword ptr [rax+rax+00h]
0x1400101eb  mov     rdx, rax
0x1400101ee  test    rax, rax
0x1400101f1  jz      short loc_140010231
0x1400101f3  mov     rcx, [rdi]
0x1400101f6  mov     [rax], rcx
0x1400101f9  mov     rax, [rdi+8]
0x1400101fd  mov     [rdx+8], rax
0x140010201  test    rax, rax
0x140010204  jz      short loc_14001020A
0x140010206  lock add [rax+8], ebp
0x14001020a  mov     [rdx+18h], rdx
0x14001020e  lea     rax, [rbx+18h]
0x140010212  mov     [rdx+10h], rdx
0x140010216  add     [rbx+10h], ebp
0x140010219  mov     rcx, [rax+10h]
0x14001021d  xor     edi, edi
0x14001021f  mov     [rdx+18h], rax
0x140010223  mov     [rdx+10h], rcx
0x140010227  mov     [rcx+18h], rdx
0x14001022b  mov     [rbx+28h], rdx
0x14001022f  jmp     short loc_140010236
0x140010231  mov     edi, 0C000009Ah
0x140010236  test    sil, sil
0x140010239  jz      short loc_14001025C
0x14001023b  mov     rcx, [rbx+8]; Resource
0x14001023f  test    rcx, rcx
0x140010242  jz      short loc_14001025C
0x140010244  call    cs:__imp_ExReleaseResourceLite
0x14001024b  nop     dword ptr [rax+rax+00h]
0x140010250  call    cs:__imp_KeLeaveCriticalRegion
0x140010257  nop     dword ptr [rax+rax+00h]
0x14001025c  mov     eax, edi
0x14001025e  add     rsp, 28h
0x140010262  pop     rdi
0x140010263  pop     rsi
0x140010264  pop     rbp
0x140010265  pop     rbx
0x140010266  retn
```
