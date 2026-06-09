# SdbpCreateSearchPathPartsFromPath

- ea: `0x18002c5c0`
- end: `0x18002c6f4`
- name: `SdbpCreateSearchPathPartsFromPath`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18002c488`

## callees

- `0x18000f114`
- `0x18002c5c0`

## import_xrefs

- `ntdll!wcschr` at `0x18002c5ec`
- `ntdll!wcschr` at `0x18002c5ec`
- `ntdll!RtlAllocateHeap` at `0x18002c61c`
- `ntdll!RtlAllocateHeap` at `0x18002c61c`

## string_xrefs

- `0x18002c68e`: `SdbpCreateSearchPathPartsFromPath`
- `0x18002c6ae`: `Failed to allocate search path parts`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchPathPartsFromPath(const wchar_t *a1, _QWORD *a2)
{
  const wchar_t *v3; // rdi
  int i; // ebx
  wchar_t *v5; // rax
  _DWORD *Heap; // rax
  _DWORD *v7; // r9
  unsigned int v8; // r10d
  __int64 v9; // rax
  _WORD *v10; // r8
  const wchar_t *j; // rdx
  __int64 v13; // rcx

  v3 = a1;
  if ( a1 )
  {
    for ( i = *a1 != 0; ; ++i )
    {
      v5 = wcschr(a1, 0x3Bu);
      if ( !v5 )
        break;
      a1 = v5 + 1;
    }
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 48LL * (unsigned int)(i - 1) + 56);
    v7 = Heap;
    if ( Heap )
    {
      *Heap = i;
      v8 = 0;
      v9 = -1;
      v10 = 0;
      do
        ++v9;
      while ( v3[v9] );
      for ( j = &v3[v9]; ; --j )
      {
        if ( j < v3 )
        {
          *a2 = v7;
          return 1;
        }
        if ( *j == 92 )
          break;
        if ( *j != 59 )
          goto LABEL_11;
LABEL_20:
        if ( v10 )
        {
          if ( *j == 59 )
            ++j;
          v13 = 6LL * v8++;
          v7[2 * v13 + 4] = v10 - j + 1;
          v10 = 0;
          *(_QWORD *)&v7[2 * v13 + 2] = j;
        }
LABEL_12:
        ;
      }
      if ( !v10 )
        v10 = j;
LABEL_11:
      if ( v3 != j )
        goto LABEL_12;
      goto LABEL_20;
    }
    AslLogCallPrintf(1, "SdbpCreateSearchPathPartsFromPath", 3282, "Failed to allocate search path parts");
  }
  else
  {
    AslLogCallPrintf(1, "SdbpCreateSearchPathPartsFromPath", 3253, "Invalid argument");
  }
  return 0;
}

```

## disassembly

```asm
0x18002c5c0  push    rbx
0x18002c5c2  push    rbp
0x18002c5c3  push    rdi
0x18002c5c4  push    r14
0x18002c5c6  push    r15
0x18002c5c8  sub     rsp, 20h
0x18002c5cc  xor     ebp, ebp
0x18002c5ce  mov     r14, rdx
0x18002c5d1  mov     rdi, rcx
0x18002c5d4  test    rcx, rcx
0x18002c5d7  jz      loc_18002C681
0x18002c5dd  cmp     [rcx], bp
0x18002c5e0  lea     r15d, [rbp+3Bh]
0x18002c5e4  mov     ebx, ebp
0x18002c5e6  setnz   bl
0x18002c5e9  mov     edx, r15d; Ch
0x18002c5ec  call    cs:__imp_wcschr
0x18002c5f2  test    rax, rax
0x18002c5f5  jnz     loc_18002C6A3
0x18002c5fb  mov     rcx, gs:60h
0x18002c604  lea     eax, [rbx-1]
0x18002c607  lea     r8, [rax+rax*2]
0x18002c60b  mov     edx, 8; Flags
0x18002c610  shl     r8, 4
0x18002c614  add     r8, 38h ; '8'; Size
0x18002c618  mov     rcx, [rcx+30h]; HeapHandle
0x18002c61c  call    cs:__imp_RtlAllocateHeap
0x18002c622  mov     r9, rax
0x18002c625  test    rax, rax
0x18002c628  jz      loc_18002C6AE
0x18002c62e  mov     [rax], ebx
0x18002c630  mov     r10d, ebp
0x18002c633  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002c637  mov     r8, rbp
0x18002c63a  inc     rax
0x18002c63d  cmp     [rdi+rax*2], bp
0x18002c641  jnz     short loc_18002C63A
0x18002c643  lea     rdx, [rdi+rax*2]
0x18002c647  cmp     rdx, rdi
0x18002c64a  jb      short loc_18002C663
0x18002c64c  cmp     word ptr [rdx], 5Ch ; '\'
0x18002c650  jz      short loc_18002C677
0x18002c652  cmp     [rdx], r15w
0x18002c656  jz      short loc_18002C6BD
0x18002c658  cmp     rdi, rdx
0x18002c65b  jz      short loc_18002C6BD
0x18002c65d  sub     rdx, 2
0x18002c661  jmp     short loc_18002C647
0x18002c663  mov     [r14], r9
0x18002c666  mov     eax, 1
0x18002c66b  add     rsp, 20h
0x18002c66f  pop     r15
0x18002c671  pop     r14
0x18002c673  pop     rdi
0x18002c674  pop     rbp
0x18002c675  pop     rbx
0x18002c676  retn
0x18002c677  test    r8, r8
0x18002c67a  jnz     short loc_18002C658
0x18002c67c  mov     r8, rdx
0x18002c67f  jmp     short loc_18002C658
0x18002c681  lea     r9, aInvalidArgumen; "Invalid argument"
0x18002c688  mov     r8d, 0CB5h
0x18002c68e  lea     rdx, aSdbpcreatesear; "SdbpCreateSearchPathPartsFromPath"
0x18002c695  mov     ecx, 1
0x18002c69a  call    AslLogCallPrintf
0x18002c69f  xor     eax, eax
0x18002c6a1  jmp     short loc_18002C66B
0x18002c6a3  inc     ebx
0x18002c6a5  lea     rcx, [rax+2]
0x18002c6a9  jmp     loc_18002C5E9
0x18002c6ae  lea     r9, aFailedToAlloca_20; "Failed to allocate search path parts"
0x18002c6b5  mov     r8d, 0CD2h
0x18002c6bb  jmp     short loc_18002C68E
0x18002c6bd  test    r8, r8
0x18002c6c0  jz      short loc_18002C65D
0x18002c6c2  cmp     [rdx], r15w
0x18002c6c6  jnz     short loc_18002C6CC
0x18002c6c8  add     rdx, 2
0x18002c6cc  sub     r8, rdx
0x18002c6cf  mov     eax, r10d
0x18002c6d2  sar     r8, 1
0x18002c6d5  inc     r8d
0x18002c6d8  lea     rcx, [rax+rax*2]
0x18002c6dc  add     rcx, rcx
0x18002c6df  inc     r10d
0x18002c6e2  mov     [r9+rcx*8+10h], r8d
0x18002c6e7  mov     r8, rbp
0x18002c6ea  mov     [r9+rcx*8+8], rdx
0x18002c6ef  jmp     loc_18002C65D
```
