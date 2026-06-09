# VfsLinkCcb

- ea: `0x14000d7b8`
- end: `0x14000d860`
- name: `VfsLinkCcb`
- size: `168`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f188`

## callees

- `0x14000d7b8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d84a`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d84a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d83e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d83e`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d7e9`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d7e9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d7d7`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d7d7`

## pseudocode

```c
void __fastcall VfsLinkCcb(__int64 a1, _BYTE *a2)
{
  __int64 v2; // rsi
  __int64 v5; // rbx
  _QWORD *v6; // rdx

  v2 = *(_QWORD *)(a1 + 24);
  if ( a2 )
    *a2 = 0;
  v5 = *(_QWORD *)(v2 + 120);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite((PERESOURCE)(v5 + 56), 1u);
  if ( a2 && (*(_DWORD *)(v2 + 272) & 1) != 0 )
  {
    *a2 = 1;
  }
  else
  {
    v6 = *(_QWORD **)(v2 + 264);
    if ( *v6 != v2 + 256 )
      __fastfail(3u);
    *(_QWORD *)(a1 + 8) = v2 + 256;
    *(_QWORD *)(a1 + 16) = v6;
    *v6 = a1 + 8;
    *(_QWORD *)(v2 + 264) = a1 + 8;
    *(_DWORD *)(a1 + 4) |= 1u;
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(v2 + 120) + 56LL));
  KeLeaveCriticalRegion();
}

```

## disassembly

```asm
0x14000d7b8  push    rbx
0x14000d7ba  push    rbp
0x14000d7bb  push    rsi
0x14000d7bc  push    rdi
0x14000d7bd  sub     rsp, 28h
0x14000d7c1  mov     rsi, [rcx+18h]
0x14000d7c5  mov     rdi, rdx
0x14000d7c8  mov     rbp, rcx
0x14000d7cb  test    rdx, rdx
0x14000d7ce  jz      short loc_14000D7D3
0x14000d7d0  mov     byte ptr [rdx], 0
0x14000d7d3  mov     rbx, [rsi+78h]
0x14000d7d7  call    cs:__imp_KeEnterCriticalRegion
0x14000d7de  nop     dword ptr [rax+rax+00h]
0x14000d7e3  mov     dl, 1; Wait
0x14000d7e5  lea     rcx, [rbx+38h]; Resource
0x14000d7e9  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000d7f0  nop     dword ptr [rax+rax+00h]
0x14000d7f5  test    rdi, rdi
0x14000d7f8  jz      short loc_14000D809
0x14000d7fa  mov     eax, [rsi+110h]
0x14000d800  test    al, 1
0x14000d802  jz      short loc_14000D809
0x14000d804  mov     byte ptr [rdi], 1
0x14000d807  jmp     short loc_14000D836
0x14000d809  lea     rcx, [rsi+100h]
0x14000d810  mov     rdx, [rcx+8]
0x14000d814  cmp     [rdx], rcx
0x14000d817  jz      short loc_14000D820
0x14000d819  mov     ecx, 3
0x14000d81e  int     29h; Win8: RtlFailFast(ecx)
0x14000d820  lea     rax, [rbp+8]
0x14000d824  mov     [rax], rcx
0x14000d827  mov     [rax+8], rdx
0x14000d82b  mov     [rdx], rax
0x14000d82e  mov     [rcx+8], rax
0x14000d832  or      dword ptr [rbp+4], 1
0x14000d836  mov     rcx, [rsi+78h]
0x14000d83a  add     rcx, 38h ; '8'; Resource
0x14000d83e  call    cs:__imp_ExReleaseResourceLite
0x14000d845  nop     dword ptr [rax+rax+00h]
0x14000d84a  call    cs:__imp_KeLeaveCriticalRegion
0x14000d851  nop     dword ptr [rax+rax+00h]
0x14000d856  add     rsp, 28h
0x14000d85a  pop     rdi
0x14000d85b  pop     rsi
0x14000d85c  pop     rbp
0x14000d85d  pop     rbx
0x14000d85e  retn
```
