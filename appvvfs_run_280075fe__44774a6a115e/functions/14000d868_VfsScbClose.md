# VfsScbClose

- ea: `0x14000d868`
- end: `0x14000d9c6`
- name: `VfsScbClose`
- size: `350`
- prototype: `__int64 __fastcall(PVOID Entry)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x140001b8c`
- `0x140002b4c`
- `0x14000b2dc`
- `0x14000f188`

## callees

- `0x14000d72c`
- `0x14000d868`
- `0x14000da2c`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d895`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14000d895`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d924`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d946`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d99d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d8d7`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d924`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d946`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000d99d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d8cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d918`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d93a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d991`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d8cb`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d918`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d93a`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000d991`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d904`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d966`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d904`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000d966`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d883`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d8f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d955`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d883`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d8f2`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000d955`

## pseudocode

```c
void __fastcall VfsScbClose(__int64 Entry)
{
  __int64 v1; // rbx
  __int64 v3; // rax
  __int64 v4; // rsi
  __int64 v5; // rbx
  struct _ERESOURCE *v6; // rbx
  char v7; // bl
  char v8; // [rsp+30h] [rbp+8h] BYREF

  v1 = *(_QWORD *)(Entry + 120);
  v8 = 0;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite((PERESOURCE)(v1 + 56), 1u);
  v3 = *(_QWORD *)(Entry + 128);
  v4 = v3 + 8;
  if ( (*(_DWORD *)(v3 + 4) & 1) != 0 )
  {
    VfsScbTableCloseScb(Entry, v4, &v8);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(Entry + 120) + 56LL));
    KeLeaveCriticalRegion();
    if ( !v8 )
      return;
    v5 = *(_QWORD *)(Entry + 120);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v5 + 56), 1u);
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(Entry + 120) + 56LL));
    KeLeaveCriticalRegion();
    goto LABEL_7;
  }
  ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(Entry + 120) + 56LL));
  KeLeaveCriticalRegion();
  v6 = *(struct _ERESOURCE **)v4;
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v6, 1u);
  v7 = 0;
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)(Entry + 276), 0xFFFFFFFF) == 1 )
  {
    *(_QWORD *)(v4 + 8) = 0;
    v7 = 1;
  }
  ExReleaseResourceLite(*(PERESOURCE *)v4);
  KeLeaveCriticalRegion();
  if ( v7 )
LABEL_7:
    VfsDeleteScb((PVOID)Entry);
}

```

## disassembly

```asm
0x14000d868  mov     [rsp+arg_8], rbx
0x14000d86d  mov     [rsp+arg_10], rsi
0x14000d872  push    rdi
0x14000d873  sub     rsp, 20h
0x14000d877  mov     rbx, [rcx+78h]
0x14000d87b  mov     rdi, rcx
0x14000d87e  mov     [rsp+28h+arg_0], 0
0x14000d883  call    cs:__imp_KeEnterCriticalRegion
0x14000d88a  nop     dword ptr [rax+rax+00h]
0x14000d88f  mov     dl, 1; Wait
0x14000d891  lea     rcx, [rbx+38h]; Resource
0x14000d895  call    cs:__imp_ExAcquireResourceSharedLite
0x14000d89c  nop     dword ptr [rax+rax+00h]
0x14000d8a1  mov     rax, [rdi+80h]
0x14000d8a8  lea     rsi, [rax+8]
0x14000d8ac  mov     eax, [rax+4]
0x14000d8af  test    al, 1
0x14000d8b1  jz      short loc_14000D932
0x14000d8b3  lea     r8, [rsp+28h+arg_0]
0x14000d8b8  mov     rdx, rsi
0x14000d8bb  mov     rcx, rdi
0x14000d8be  call    VfsScbTableCloseScb
0x14000d8c3  mov     rcx, [rdi+78h]
0x14000d8c7  add     rcx, 38h ; '8'; Resource
0x14000d8cb  call    cs:__imp_ExReleaseResourceLite
0x14000d8d2  nop     dword ptr [rax+rax+00h]
0x14000d8d7  call    cs:__imp_KeLeaveCriticalRegion
0x14000d8de  nop     dword ptr [rax+rax+00h]
0x14000d8e3  cmp     [rsp+28h+arg_0], 0
0x14000d8e8  jz      loc_14000D9B5
0x14000d8ee  mov     rbx, [rdi+78h]
0x14000d8f2  call    cs:__imp_KeEnterCriticalRegion
0x14000d8f9  nop     dword ptr [rax+rax+00h]
0x14000d8fe  mov     dl, 1; Wait
0x14000d900  lea     rcx, [rbx+38h]; Resource
0x14000d904  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000d90b  nop     dword ptr [rax+rax+00h]
0x14000d910  mov     rcx, [rdi+78h]
0x14000d914  add     rcx, 38h ; '8'; Resource
0x14000d918  call    cs:__imp_ExReleaseResourceLite
0x14000d91f  nop     dword ptr [rax+rax+00h]
0x14000d924  call    cs:__imp_KeLeaveCriticalRegion
0x14000d92b  nop     dword ptr [rax+rax+00h]
0x14000d930  jmp     short loc_14000D9AD
0x14000d932  mov     rcx, [rdi+78h]
0x14000d936  add     rcx, 38h ; '8'; Resource
0x14000d93a  call    cs:__imp_ExReleaseResourceLite
0x14000d941  nop     dword ptr [rax+rax+00h]
0x14000d946  call    cs:__imp_KeLeaveCriticalRegion
0x14000d94d  nop     dword ptr [rax+rax+00h]
0x14000d952  mov     rbx, [rsi]
0x14000d955  call    cs:__imp_KeEnterCriticalRegion
0x14000d95c  nop     dword ptr [rax+rax+00h]
0x14000d961  mov     dl, 1; Wait
0x14000d963  mov     rcx, rbx; Resource
0x14000d966  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000d96d  nop     dword ptr [rax+rax+00h]
0x14000d972  xor     bl, bl
0x14000d974  or      eax, 0FFFFFFFFh
0x14000d977  lock xadd [rdi+114h], eax
0x14000d97f  cmp     eax, 1
0x14000d982  jnz     short loc_14000D98E
0x14000d984  mov     qword ptr [rsi+8], 0
0x14000d98c  mov     bl, al
0x14000d98e  mov     rcx, [rsi]; Resource
0x14000d991  call    cs:__imp_ExReleaseResourceLite
0x14000d998  nop     dword ptr [rax+rax+00h]
0x14000d99d  call    cs:__imp_KeLeaveCriticalRegion
0x14000d9a4  nop     dword ptr [rax+rax+00h]
0x14000d9a9  test    bl, bl
0x14000d9ab  jz      short loc_14000D9B5
0x14000d9ad  mov     rcx, rdi; Entry
0x14000d9b0  call    VfsDeleteScb
0x14000d9b5  mov     rbx, [rsp+28h+arg_8]
0x14000d9ba  mov     rsi, [rsp+28h+arg_10]
0x14000d9bf  add     rsp, 20h
0x14000d9c3  pop     rdi
0x14000d9c4  retn
```
