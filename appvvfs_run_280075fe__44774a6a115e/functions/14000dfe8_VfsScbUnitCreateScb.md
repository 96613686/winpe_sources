# VfsScbUnitCreateScb

- ea: `0x14000dfe8`
- end: `0x14000e09a`
- name: `VfsScbUnitCreateScb`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000f188`

## callees

- `0x14000d3b4`
- `0x14000dfe8`

## import_xrefs

- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e078`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000e078`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e06c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000e06c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e01b`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000e01b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e00a`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000e00a`

## pseudocode

```c
__int64 __fastcall VfsScbUnitCreateScb(__int64 a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  struct _ERESOURCE *v4; // rbx
  __int64 v9; // rax
  int v10; // ebx
  __int64 v11; // rcx
  __int64 v13; // [rsp+48h] [rbp+10h] BYREF

  v4 = *(struct _ERESOURCE **)(a2 + 8);
  KeEnterCriticalRegion();
  ExAcquireResourceExclusiveLite(v4, 1u);
  v9 = *(_QWORD *)(a2 + 16);
  v13 = v9;
  if ( v9 )
  {
    v10 = 0;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 276));
    *a4 = v9;
  }
  else
  {
    v10 = VfsCreateScb(a1, (void *)a2, a3, &v13);
    if ( v10 >= 0 )
    {
      v11 = v13;
      *(_QWORD *)(a2 + 16) = v13;
      *a4 = v11;
    }
  }
  ExReleaseResourceLite(*(PERESOURCE *)(a2 + 8));
  KeLeaveCriticalRegion();
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x14000dfe8  mov     [rsp+arg_0], rbx
0x14000dfed  mov     [rsp+arg_10], rbp
0x14000dff2  push    rsi
0x14000dff3  push    rdi
0x14000dff4  push    r14
0x14000dff6  sub     rsp, 20h
0x14000dffa  mov     rbx, [rdx+8]
0x14000dffe  mov     rsi, r9
0x14000e001  mov     rbp, r8
0x14000e004  mov     rdi, rdx
0x14000e007  mov     r14, rcx
0x14000e00a  call    cs:__imp_KeEnterCriticalRegion
0x14000e011  nop     dword ptr [rax+rax+00h]
0x14000e016  mov     dl, 1; Wait
0x14000e018  mov     rcx, rbx; Resource
0x14000e01b  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000e022  nop     dword ptr [rax+rax+00h]
0x14000e027  mov     rax, [rdi+10h]
0x14000e02b  mov     [rsp+38h+arg_8], rax
0x14000e030  test    rax, rax
0x14000e033  jz      short loc_14000E043
0x14000e035  xor     ebx, ebx
0x14000e037  lock inc dword ptr [rax+114h]
0x14000e03e  mov     [rsi], rax
0x14000e041  jmp     short loc_14000E068
0x14000e043  lea     r9, [rsp+38h+arg_8]
0x14000e048  mov     r8, rbp
0x14000e04b  mov     rdx, rdi
0x14000e04e  mov     rcx, r14
0x14000e051  call    VfsCreateScb
0x14000e056  mov     ebx, eax
0x14000e058  test    eax, eax
0x14000e05a  js      short loc_14000E068
0x14000e05c  mov     rcx, [rsp+38h+arg_8]
0x14000e061  mov     [rdi+10h], rcx
0x14000e065  mov     [rsi], rcx
0x14000e068  mov     rcx, [rdi+8]; Resource
0x14000e06c  call    cs:__imp_ExReleaseResourceLite
0x14000e073  nop     dword ptr [rax+rax+00h]
0x14000e078  call    cs:__imp_KeLeaveCriticalRegion
0x14000e07f  nop     dword ptr [rax+rax+00h]
0x14000e084  mov     rbp, [rsp+38h+arg_10]
0x14000e089  mov     eax, ebx
0x14000e08b  mov     rbx, [rsp+38h+arg_0]
0x14000e090  add     rsp, 20h
0x14000e094  pop     r14
0x14000e096  pop     rdi
0x14000e097  pop     rsi
0x14000e098  retn
```
