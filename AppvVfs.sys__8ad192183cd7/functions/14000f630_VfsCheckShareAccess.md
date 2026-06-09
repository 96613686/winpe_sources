# VfsCheckShareAccess

- ea: `0x14000f630`
- end: `0x14000f71d`
- name: `VfsCheckShareAccess`
- size: `237`
- prototype: `__int64 __fastcall(__int64, __int64, char, BOOLEAN)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002e90`
- `0x14000f188`

## callees

- `0x14000f630`

## import_xrefs

- `ntoskrnl!IoCheckShareAccess` at `0x14000f6d6`
- `ntoskrnl!IoCheckShareAccess` at `0x14000f6d6`
- `ntoskrnl!IoSetShareAccess` at `0x14000f6b3`
- `ntoskrnl!IoSetShareAccess` at `0x14000f6b3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f6fd`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14000f6fd`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f6f1`
- `ntoskrnl!ExReleaseResourceLite` at `0x14000f6f1`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000f67f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14000f67f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f66d`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14000f66d`

## pseudocode

```c
__int64 __fastcall VfsCheckShareAccess(__int64 a1, __int64 a2, char a3, BOOLEAN a4)
{
  __int64 v4; // r10
  struct _FILE_OBJECT *v8; // r15
  ULONG v9; // r13d
  ACCESS_MASK v10; // r12d
  __int64 v11; // rbx
  unsigned int v12; // ebx

  v4 = *(_QWORD *)(a1 + 16);
  v8 = *(struct _FILE_OBJECT **)(v4 + 8);
  v9 = *(unsigned __int16 *)(v4 + 42);
  v10 = *(_DWORD *)(*(_QWORD *)(v4 + 24) + 16LL);
  if ( !a3 )
  {
    v11 = *(_QWORD *)(a2 + 120);
    KeEnterCriticalRegion();
    ExAcquireResourceExclusiveLite((PERESOURCE)(v11 + 56), 1u);
  }
  if ( _InterlockedCompareExchange((volatile signed __int32 *)(a2 + 276), 1, 1) == 1 )
  {
    v12 = 0;
    if ( a4 )
      IoSetShareAccess(v10, v9, v8, (PSHARE_ACCESS)(a2 + 284));
  }
  else
  {
    v12 = IoCheckShareAccess(v10, v9, v8, (PSHARE_ACCESS)(a2 + 284), a4);
  }
  if ( !a3 )
  {
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(a2 + 120) + 56LL));
    KeLeaveCriticalRegion();
  }
  return v12;
}

```

## disassembly

```asm
0x14000f630  push    rbx
0x14000f632  push    rbp
0x14000f633  push    rsi
0x14000f634  push    rdi
0x14000f635  push    r12
0x14000f637  push    r13
0x14000f639  push    r14
0x14000f63b  push    r15
0x14000f63d  sub     rsp, 38h
0x14000f641  mov     r10, [rcx+10h]
0x14000f645  mov     bpl, r9b
0x14000f648  mov     r14b, r8b
0x14000f64b  mov     rsi, rdx
0x14000f64e  mov     ecx, 1
0x14000f653  mov     rax, [r10+18h]
0x14000f657  mov     r15, [r10+8]
0x14000f65b  movzx   r13d, word ptr [r10+2Ah]
0x14000f660  mov     r12d, [rax+10h]
0x14000f664  test    r8b, r8b
0x14000f667  jnz     short loc_14000F690
0x14000f669  mov     rbx, [rdx+78h]
0x14000f66d  call    cs:__imp_KeEnterCriticalRegion
0x14000f674  nop     dword ptr [rax+rax+00h]
0x14000f679  mov     dl, 1; Wait
0x14000f67b  lea     rcx, [rbx+38h]; Resource
0x14000f67f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x14000f686  nop     dword ptr [rax+rax+00h]
0x14000f68b  mov     ecx, 1
0x14000f690  mov     eax, ecx
0x14000f692  lock cmpxchg [rsi+114h], ecx
0x14000f69a  jnz     short loc_14000F6C1
0x14000f69c  xor     ebx, ebx
0x14000f69e  test    bpl, bpl
0x14000f6a1  jz      short loc_14000F6E4
0x14000f6a3  lea     r9, [rsi+11Ch]; ShareAccess
0x14000f6aa  mov     r8, r15; FileObject
0x14000f6ad  mov     edx, r13d; DesiredShareAccess
0x14000f6b0  mov     ecx, r12d; DesiredAccess
0x14000f6b3  call    cs:__imp_IoSetShareAccess
0x14000f6ba  nop     dword ptr [rax+rax+00h]
0x14000f6bf  jmp     short loc_14000F6E4
0x14000f6c1  lea     r9, [rsi+11Ch]; ShareAccess
0x14000f6c8  mov     [rsp+78h+Update], bpl; Update
0x14000f6cd  mov     r8, r15; FileObject
0x14000f6d0  mov     edx, r13d; DesiredShareAccess
0x14000f6d3  mov     ecx, r12d; DesiredAccess
0x14000f6d6  call    cs:__imp_IoCheckShareAccess
0x14000f6dd  nop     dword ptr [rax+rax+00h]
0x14000f6e2  mov     ebx, eax
0x14000f6e4  test    r14b, r14b
0x14000f6e7  jnz     short loc_14000F709
0x14000f6e9  mov     rcx, [rsi+78h]
0x14000f6ed  add     rcx, 38h ; '8'; Resource
0x14000f6f1  call    cs:__imp_ExReleaseResourceLite
0x14000f6f8  nop     dword ptr [rax+rax+00h]
0x14000f6fd  call    cs:__imp_KeLeaveCriticalRegion
0x14000f704  nop     dword ptr [rax+rax+00h]
0x14000f709  mov     eax, ebx
0x14000f70b  add     rsp, 38h
0x14000f70f  pop     r15
0x14000f711  pop     r14
0x14000f713  pop     r13
0x14000f715  pop     r12
0x14000f717  pop     rdi
0x14000f718  pop     rsi
0x14000f719  pop     rbp
0x14000f71a  pop     rbx
0x14000f71b  retn
```
