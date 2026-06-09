# CreateSubAllocator

- ea: `0x180006dd4`
- end: `0x180006e5e`
- name: `CreateSubAllocator`
- size: `138`
- prototype: `_QWORD *__fastcall(__int64)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180001d10`
- `0x180002720`
- `0x180003348`

## callees

- `0x180006dd4`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006dfd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006e23`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006dfd`
- `api-ms-win-core-memory-l1-1-0!VirtualAlloc` at `0x180006e23`

## pseudocode

```c
_QWORD *__fastcall CreateSubAllocator(__int64 a1)
{
  SIZE_T v1; // rbx
  _QWORD *v2; // rcx

  v1 = (a1 + 0xFFFF) & 0xFFFFFFFFFFFF0000uLL;
  v2 = VirtualAlloc(0, v1, 0x1000u, 4u);
  if ( v2 || v1 > 0x10000 && (v1 = 0x10000, (v2 = VirtualAlloc(0, 0x10000u, 0x1000u, 4u)) != 0) )
  {
    v2[1] = v2;
    v2[2] = v2 + 5;
    v2[3] = (char *)v2 + v1;
    v2[4] = 0x10000;
    *v2 = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x180006dd4  mov     [rsp+arg_0], rbx
0x180006dd9  push    rdi
0x180006dda  sub     rsp, 20h
0x180006dde  lea     rbx, [rcx+0FFFFh]
0x180006de5  mov     r9d, 4; flProtect
0x180006deb  and     rbx, 0FFFFFFFFFFFF0000h
0x180006df2  mov     r8d, 1000h; flAllocationType
0x180006df8  mov     rdx, rbx; dwSize
0x180006dfb  xor     ecx, ecx; lpAddress
0x180006dfd  call    cs:__imp_VirtualAlloc
0x180006e03  mov     rcx, rax; lpAddress
0x180006e06  mov     edi, 10000h
0x180006e0b  test    rax, rax
0x180006e0e  jnz     short loc_180006E31
0x180006e10  cmp     rbx, rdi
0x180006e13  jbe     short loc_180006E50
0x180006e15  lea     r9d, [rax+4]; flProtect
0x180006e19  mov     r8d, 1000h; flAllocationType
0x180006e1f  mov     edx, edi; dwSize
0x180006e21  mov     ebx, edi
0x180006e23  call    cs:__imp_VirtualAlloc
0x180006e29  mov     rcx, rax
0x180006e2c  test    rax, rax
0x180006e2f  jz      short loc_180006E50
0x180006e31  lea     rax, [rcx+28h]
0x180006e35  mov     [rcx+8], rcx
0x180006e39  mov     [rcx+10h], rax
0x180006e3d  lea     rax, [rbx+rcx]
0x180006e41  mov     [rcx+18h], rax
0x180006e45  mov     [rcx+20h], rdi
0x180006e49  mov     qword ptr [rcx], 0
0x180006e50  mov     rbx, [rsp+28h+arg_0]
0x180006e55  mov     rax, rcx
0x180006e58  add     rsp, 20h
0x180006e5c  pop     rdi
0x180006e5d  retn
```
