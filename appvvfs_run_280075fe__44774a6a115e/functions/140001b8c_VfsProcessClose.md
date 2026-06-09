# VfsProcessClose

- ea: `0x140001b8c`
- end: `0x140001c85`
- name: `VfsProcessClose`
- size: `249`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000aa90`

## callees

- `0x140001b8c`
- `0x14000d618`
- `0x14000d868`

## import_xrefs

- `ntoskrnl!IoRemoveShareAccess` at `0x140001c27`
- `ntoskrnl!IoRemoveShareAccess` at `0x140001c27`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c4f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140001c4f`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001c43`
- `ntoskrnl!ExReleaseResourceLite` at `0x140001c43`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001be0`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140001be0`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001bce`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140001bce`

## pseudocode

```c
__int64 __fastcall VfsProcessClose(_QWORD *a1, _QWORD *a2, __int64 a3)
{
  __int64 v5; // rbx
  __int64 v6; // rdx
  _QWORD *v7; // rax

  a1[3] = 0;
  a1[4] = 0;
  a1[2] = 0;
  _InterlockedDecrement((volatile signed __int32 *)(a2[17] + 24LL));
  if ( (*(_DWORD *)(a3 + 4) & 1) != 0 )
  {
    v5 = *(_QWORD *)(*(_QWORD *)(a3 + 24) + 120LL);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v5 + 56), 1u);
    v6 = *(_QWORD *)(a3 + 8);
    if ( *(_QWORD *)(v6 + 8) != a3 + 8 || (v7 = *(_QWORD **)(a3 + 16), *v7 != a3 + 8) )
      __fastfail(3u);
    *v7 = v6;
    *(_QWORD *)(v6 + 8) = v7;
    *(_DWORD *)(a3 + 4) &= ~1u;
    if ( (*(_DWORD *)(a3 + 4) & 0x20) != 0 )
    {
      IoRemoveShareAccess(*(PFILE_OBJECT *)(a3 + 96), (PSHARE_ACCESS)(*(_QWORD *)(a3 + 24) + 284LL));
      *(_DWORD *)(a3 + 4) &= ~0x20u;
    }
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a3 + 24) + 120LL) + 56LL));
    KeLeaveCriticalRegion();
  }
  VfsScbClose(a2);
  VfsDeleteCcb((_QWORD *)a3);
  return 0;
}

```

## disassembly

```asm
0x140001b8c  mov     [rsp+arg_0], rbx
0x140001b91  mov     [rsp+arg_8], rsi
0x140001b96  push    rdi
0x140001b97  sub     rsp, 20h
0x140001b9b  xor     eax, eax
0x140001b9d  mov     rdi, r8
0x140001ba0  mov     [rcx+18h], rax
0x140001ba4  mov     rsi, rdx
0x140001ba7  mov     [rcx+20h], rax
0x140001bab  mov     [rcx+10h], rax
0x140001baf  mov     rax, [rdx+88h]
0x140001bb6  lock dec dword ptr [rax+18h]
0x140001bba  mov     eax, [r8+4]
0x140001bbe  test    al, 1
0x140001bc0  jz      loc_140001C5B
0x140001bc6  mov     rax, [r8+18h]
0x140001bca  mov     rbx, [rax+78h]
0x140001bce  call    cs:__imp_KeEnterCriticalRegion
0x140001bd5  nop     dword ptr [rax+rax+00h]
0x140001bda  mov     dl, 1; Wait
0x140001bdc  lea     rcx, [rbx+38h]; Resource
0x140001be0  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140001be7  nop     dword ptr [rax+rax+00h]
0x140001bec  lea     rcx, [rdi+8]
0x140001bf0  mov     rdx, [rcx]
0x140001bf3  cmp     [rdx+8], rcx
0x140001bf7  jnz     loc_140001C7E
0x140001bfd  mov     rax, [rcx+8]
0x140001c01  cmp     [rax], rcx
0x140001c04  jnz     short loc_140001C7E
0x140001c06  mov     [rax], rdx
0x140001c09  mov     [rdx+8], rax
0x140001c0d  and     dword ptr [rdi+4], 0FFFFFFFEh
0x140001c11  mov     eax, [rdi+4]
0x140001c14  test    al, 20h
0x140001c16  jz      short loc_140001C37
0x140001c18  mov     rdx, [rdi+18h]
0x140001c1c  mov     rcx, [rdi+60h]; FileObject
0x140001c20  add     rdx, 11Ch; ShareAccess
0x140001c27  call    cs:__imp_IoRemoveShareAccess
0x140001c2e  nop     dword ptr [rax+rax+00h]
0x140001c33  and     dword ptr [rdi+4], 0FFFFFFDFh
0x140001c37  mov     rax, [rdi+18h]
0x140001c3b  mov     rcx, [rax+78h]
0x140001c3f  add     rcx, 38h ; '8'; Resource
0x140001c43  call    cs:__imp_ExReleaseResourceLite
0x140001c4a  nop     dword ptr [rax+rax+00h]
0x140001c4f  call    cs:__imp_KeLeaveCriticalRegion
0x140001c56  nop     dword ptr [rax+rax+00h]
0x140001c5b  mov     rcx, rsi; Entry
0x140001c5e  call    VfsScbClose
0x140001c63  mov     rcx, rdi; Entry
0x140001c66  call    VfsDeleteCcb
0x140001c6b  mov     rbx, [rsp+28h+arg_0]
0x140001c70  xor     eax, eax
0x140001c72  mov     rsi, [rsp+28h+arg_8]
0x140001c77  add     rsp, 20h
0x140001c7b  pop     rdi
0x140001c7c  retn
0x140001c7e  mov     ecx, 3
0x140001c83  int     29h; Win8: RtlFailFast(ecx)
```
