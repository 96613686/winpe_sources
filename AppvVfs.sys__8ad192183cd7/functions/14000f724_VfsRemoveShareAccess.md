# VfsRemoveShareAccess

- ea: `0x14000f724`
- end: `0x14000f7a6`
- name: `VfsRemoveShareAccess`
- size: `130`
- prototype: `void __fastcall(PFILE_OBJECT FileObject, __int64, char)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000f188`

## callees

- `0x14000f724`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x14000f769`
- `ntoskrnl!IoRemoveShareAccess` at `0x14000f769`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f78e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f78e`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f782`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f782`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000f753`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000f753`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f741`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f741`

## pseudocode

```c
void __fastcall VfsRemoveShareAccess(PFILE_OBJECT FileObject, __int64 a2, char a3)
{
  __int64 v6; // rbx

  if ( !a3 )
  {
    v6 = *(_QWORD *)(a2 + 120);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v6 + 56), 1u);
  }
  IoRemoveShareAccess(FileObject, (PSHARE_ACCESS)(a2 + 284));
  if ( !a3 )
  {
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 120) + 56LL));
    KeLeaveCriticalRegion();
  }
}

```

## disassembly

```asm
0x14000f724  push    rbx
0x14000f726  push    rbp
0x14000f727  push    rsi
0x14000f728  push    rdi
0x14000f729  push    r14
0x14000f72b  sub     rsp, 20h
0x14000f72f  mov     sil, r8b
0x14000f732  mov     rbp, rdx
0x14000f735  mov     r14, rcx
0x14000f738  test    r8b, r8b
0x14000f73b  jnz     short loc_14000F75F
0x14000f73d  mov     rbx, [rdx+78h]
0x14000f741  call    cs:__imp_KeEnterCriticalRegion
0x14000f748  nop     dword ptr [rax+rax+00h]
0x14000f74d  mov     dl, 1; Wait
0x14000f74f  lea     rcx, [rbx+38h]; Resource
0x14000f753  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000f75a  nop     dword ptr [rax+rax+00h]
0x14000f75f  lea     rdx, [rbp+11Ch]; ShareAccess
0x14000f766  mov     rcx, r14; FileObject
0x14000f769  call    cs:__imp_IoRemoveShareAccess
0x14000f770  nop     dword ptr [rax+rax+00h]
0x14000f775  test    sil, sil
0x14000f778  jnz     short loc_14000F79A
0x14000f77a  mov     rcx, [rbp+78h]
0x14000f77e  add     rcx, 38h ; '8'; Resource
0x14000f782  call    cs:__imp_ExReleaseResourceLite
0x14000f789  nop     dword ptr [rax+rax+00h]
0x14000f78e  call    cs:__imp_KeLeaveCriticalRegion
0x14000f795  nop     dword ptr [rax+rax+00h]
0x14000f79a  add     rsp, 20h
0x14000f79e  pop     r14
0x14000f7a0  pop     rdi
0x14000f7a1  pop     rsi
0x14000f7a2  pop     rbp
0x14000f7a3  pop     rbx
0x14000f7a4  retn
```
