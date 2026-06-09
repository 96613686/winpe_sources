# ReadExtra

- ea: `0x18000d1c8`
- end: `0x18000d246`
- name: `ReadExtra`
- size: `126`
- prototype: `__int64 __fastcall(__int64, int, void *, int *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180006190`
- `0x18000b020`
- `0x18000b080`

## callees

- `0x18000d1c8`
- `0x180017365`

## pseudocode

```c
__int64 __fastcall ReadExtra(__int64 a1, int a2, void *a3, int *a4)
{
  _DWORD *v6; // rdx
  unsigned int v8; // r8d
  int v9; // ebx
  int v10; // ecx
  int v12; // eax

  v6 = *(_DWORD **)a1;
  v8 = *(_DWORD *)(a1 + 8);
  while ( 1 )
  {
    if ( v8 < 8 )
    {
      *a4 = 0;
      return 2147762291LL;
    }
    v9 = v6[1];
    if ( *v6 == a2 )
      break;
    v10 = v9 + 1;
    if ( (v9 & 1) == 0 )
      v10 = v6[1];
    v8 += -8 - v10;
    v6 = (_DWORD *)((char *)v6 + v10 + 8);
  }
  if ( a3 )
  {
    v12 = v6[1];
    if ( v9 >= *a4 )
      v12 = *a4;
    memmove_0(a3, v6 + 2, v12);
  }
  *a4 = v9;
  return 0;
}

```

## disassembly

```asm
0x18000d1c8  mov     [rsp+arg_0], rbx
0x18000d1cd  push    rdi
0x18000d1ce  sub     rsp, 20h
0x18000d1d2  mov     rdi, r9
0x18000d1d5  mov     r10d, edx
0x18000d1d8  mov     rdx, [rcx]
0x18000d1db  mov     r9, r8
0x18000d1de  mov     r8d, [rcx+8]
0x18000d1e2  jmp     short loc_18000D209
0x18000d1e4  mov     ebx, [rdx+4]
0x18000d1e7  cmp     [rdx], r10d
0x18000d1ea  jz      short loc_18000D225
0x18000d1ec  test    bl, 1
0x18000d1ef  lea     ecx, [rbx+1]
0x18000d1f2  mov     eax, 0FFFFFFF8h
0x18000d1f7  cmovz   ecx, ebx
0x18000d1fa  add     rdx, 8
0x18000d1fe  sub     eax, ecx
0x18000d200  add     r8d, eax
0x18000d203  movsxd  rax, ecx
0x18000d206  add     rdx, rax
0x18000d209  cmp     r8d, 8
0x18000d20d  jnb     short loc_18000D1E4
0x18000d20f  mov     dword ptr [rdi], 0
0x18000d215  mov     eax, 80044073h
0x18000d21a  mov     rbx, [rsp+28h+arg_0]
0x18000d21f  add     rsp, 20h
0x18000d223  pop     rdi
0x18000d224  retn
0x18000d225  test    r9, r9
0x18000d228  jz      short loc_18000D240
0x18000d22a  cmp     ebx, [rdi]
0x18000d22c  mov     eax, ebx
0x18000d22e  mov     rcx, r9; void *
0x18000d231  cmovge  eax, [rdi]
0x18000d234  add     rdx, 8; Src
0x18000d238  movsxd  r8, eax; Size
0x18000d23b  call    memmove_0
0x18000d240  mov     [rdi], ebx
0x18000d242  xor     eax, eax
0x18000d244  jmp     short loc_18000D21A
```
