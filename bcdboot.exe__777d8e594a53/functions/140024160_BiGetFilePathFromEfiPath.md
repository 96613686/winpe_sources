# BiGetFilePathFromEfiPath

- ea: `0x140024160`
- end: `0x1400242b6`
- name: `BiGetFilePathFromEfiPath`
- size: `342`
- prototype: `__int64 __fastcall(__int64, _QWORD *, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x140022e8c`
- `0x140024cf0`

## callees

- `0x1400133e4`
- `0x140024160`
- `0x1400265e2`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x14002420b`
- `ntdll!RtlAllocateHeap` at `0x14002420b`

## string_xrefs

- `0x140024221`: `BiGetFilePathFromEfiPath failed %x`

## pseudocode

```c
__int64 __fastcall BiGetFilePathFromEfiPath(__int64 a1, _QWORD *a2, unsigned int *a3)
{
  unsigned int v6; // ebx
  unsigned int v7; // r8d
  __int64 i; // rdx
  unsigned int v9; // ecx
  unsigned int v10; // r14d
  _WORD *Heap; // rax
  _WORD *v12; // rbp
  _WORD *v13; // rsi
  __int64 j; // rdi
  size_t v15; // rbx

  if ( (*(_BYTE *)a1 & 0x7F) == 0x7F )
  {
    v6 = -1073741766;
LABEL_15:
    BiLogMessage(4, L"BiGetFilePathFromEfiPath failed %x", v6);
    return v6;
  }
  v7 = 0;
  for ( i = a1 + *(unsigned __int16 *)(a1 + 2); (*(_BYTE *)i & 0x7F) != 0x7F; i += *(unsigned __int16 *)(i + 2) )
  {
    if ( *(_BYTE *)i == 4 && *(_BYTE *)(i + 1) == 4 )
    {
      v9 = *(unsigned __int16 *)(i + 2);
      if ( v9 < 4 )
      {
        v6 = -1073741675;
        goto LABEL_15;
      }
      v7 = v9 + v7 - 4;
    }
  }
  if ( v7 )
  {
    v10 = v7 + 2;
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v7 + 2);
    v12 = Heap;
    if ( !Heap )
    {
      v6 = -1073741670;
      goto LABEL_15;
    }
    v13 = Heap;
    for ( j = a1 + *(unsigned __int16 *)(a1 + 2); (*(_BYTE *)j & 0x7F) != 0x7F; j += *(unsigned __int16 *)(j + 2) )
    {
      if ( *(_BYTE *)j == 4 && *(_BYTE *)(j + 1) == 4 )
      {
        v15 = (unsigned int)*(unsigned __int16 *)(j + 2) - 4;
        memcpy_0(v13, (const void *)(j + 4), v15);
        v13 = (_WORD *)((char *)v13 + v15);
      }
    }
    *a2 = v12;
    *v13 = 0;
    v6 = 0;
    *a3 = v10;
  }
  else
  {
    return (unsigned int)-1073741275;
  }
  return v6;
}

```

## disassembly

```asm
0x140024160  push    rbx
0x140024162  push    rbp
0x140024163  push    rsi
0x140024164  push    rdi
0x140024165  push    r12
0x140024167  push    r14
0x140024169  push    r15
0x14002416b  sub     rsp, 20h
0x14002416f  mov     al, [rcx]
0x140024171  mov     r15, r8
0x140024174  and     al, 7Fh
0x140024176  mov     r12, rdx
0x140024179  mov     rbx, rcx
0x14002417c  cmp     al, 7Fh
0x14002417e  jnz     short loc_14002418A
0x140024180  mov     ebx, 0C000003Ah
0x140024185  jmp     loc_14002421E
0x14002418a  movzx   edx, byte ptr [rcx+3]
0x14002418e  xor     r8d, r8d
0x140024191  movzx   eax, byte ptr [rcx+2]
0x140024195  shl     rdx, 8
0x140024199  or      rdx, rax
0x14002419c  add     rdx, rbx
0x14002419f  mov     al, [rdx]
0x1400241a1  and     al, 7Fh
0x1400241a3  cmp     al, 7Fh
0x1400241a5  jz      short loc_1400241E6
0x1400241a7  cmp     byte ptr [rdx], 4
0x1400241aa  jnz     short loc_1400241CB
0x1400241ac  cmp     byte ptr [rdx+1], 4
0x1400241b0  jnz     short loc_1400241CB
0x1400241b2  movzx   ecx, byte ptr [rdx+3]
0x1400241b6  movzx   eax, byte ptr [rdx+2]
0x1400241ba  shl     ecx, 8
0x1400241bd  or      ecx, eax
0x1400241bf  cmp     ecx, 4
0x1400241c2  jb      short loc_1400241DF
0x1400241c4  add     r8d, 0FFFFFFFCh
0x1400241c8  add     r8d, ecx
0x1400241cb  movzx   ecx, byte ptr [rdx+3]
0x1400241cf  movzx   eax, byte ptr [rdx+2]
0x1400241d3  shl     rcx, 8
0x1400241d7  or      rcx, rax
0x1400241da  add     rdx, rcx
0x1400241dd  jmp     short loc_14002419F
0x1400241df  mov     ebx, 0C0000095h
0x1400241e4  jmp     short loc_14002421E
0x1400241e6  test    r8d, r8d
0x1400241e9  jnz     short loc_1400241F5
0x1400241eb  mov     ebx, 0C0000225h
0x1400241f0  jmp     loc_1400242A5
0x1400241f5  mov     rcx, gs:60h
0x1400241fe  lea     r14d, [r8+2]
0x140024202  mov     r8d, r14d; Size
0x140024205  xor     edx, edx; Flags
0x140024207  mov     rcx, [rcx+30h]; HeapHandle
0x14002420b  call    cs:__imp_RtlAllocateHeap
0x140024211  mov     rbp, rax
0x140024214  test    rax, rax
0x140024217  jnz     short loc_140024234
0x140024219  mov     ebx, 0C000009Ah
0x14002421e  mov     r8d, ebx
0x140024221  lea     rdx, aBigetfilepathf; "BiGetFilePathFromEfiPath failed %x"
0x140024228  mov     ecx, 4
0x14002422d  call    BiLogMessage
0x140024232  jmp     short loc_1400242A5
0x140024234  movzx   edi, byte ptr [rbx+3]
0x140024238  mov     rsi, rbp
0x14002423b  movzx   eax, byte ptr [rbx+2]
0x14002423f  shl     rdi, 8
0x140024243  or      rdi, rax
0x140024246  add     rdi, rbx
0x140024249  mov     al, [rdi]
0x14002424b  and     al, 7Fh
0x14002424d  cmp     al, 7Fh
0x14002424f  jz      short loc_140024297
0x140024251  cmp     byte ptr [rdi], 4
0x140024254  jnz     short loc_140024283
0x140024256  cmp     byte ptr [rdi+1], 4
0x14002425a  jnz     short loc_140024283
0x14002425c  movzx   ecx, byte ptr [rdi+3]
0x140024260  lea     rdx, [rdi+4]; Src
0x140024264  movzx   eax, byte ptr [rdi+2]
0x140024268  shl     rcx, 8
0x14002426c  or      rcx, rax
0x14002426f  sub     rcx, 4
0x140024273  mov     ebx, ecx
0x140024275  mov     r8d, ecx; Size
0x140024278  mov     rcx, rsi; void *
0x14002427b  call    memcpy_0
0x140024280  add     rsi, rbx
0x140024283  movzx   ecx, byte ptr [rdi+3]
0x140024287  movzx   eax, byte ptr [rdi+2]
0x14002428b  shl     rcx, 8
0x14002428f  or      rcx, rax
0x140024292  add     rdi, rcx
0x140024295  jmp     short loc_140024249
0x140024297  xor     eax, eax
0x140024299  mov     [r12], rbp
0x14002429d  mov     [rsi], ax
0x1400242a0  xor     ebx, ebx
0x1400242a2  mov     [r15], r14d
0x1400242a5  mov     eax, ebx
0x1400242a7  add     rsp, 20h
0x1400242ab  pop     r15
0x1400242ad  pop     r14
0x1400242af  pop     r12
0x1400242b1  pop     rdi
0x1400242b2  pop     rsi
0x1400242b3  pop     rbp
0x1400242b4  pop     rbx
0x1400242b5  retn
```
