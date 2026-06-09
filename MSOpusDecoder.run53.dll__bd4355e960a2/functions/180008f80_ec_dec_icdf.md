# ec_dec_icdf

- ea: `0x180008f80`
- end: `0x180008fd1`
- name: `ec_dec_icdf`
- size: `81`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x180005aa0`
- `0x180009400`
- `0x180010d80`
- `0x180013830`
- `0x180013860`
- `0x180013f70`
- `0x180014330`
- `0x180019300`
- `0x1800193d0`

## callees

- `0x180008f80`
- `0x180009040`

## pseudocode

```c
__int64 __fastcall ec_dec_icdf(__int64 a1, __int64 a2, char a3)
{
  unsigned int v3; // eax
  unsigned int v5; // r9d
  unsigned int v6; // ebx
  unsigned int v7; // r10d
  unsigned int v8; // ecx

  v3 = *(_DWORD *)(a1 + 32);
  v5 = *(_DWORD *)(a1 + 36);
  v6 = -1;
  v7 = v3 >> a3;
  do
  {
    v8 = v3;
    v3 = v7 * *(unsigned __int8 *)((int)++v6 + a2);
  }
  while ( v5 < v3 );
  *(_DWORD *)(a1 + 32) = v8 - v3;
  *(_DWORD *)(a1 + 36) = v5 - v3;
  ec_dec_normalize(a1);
  return v6;
}

```

## disassembly

```asm
0x180008f80  push    rbx
0x180008f82  sub     rsp, 20h
0x180008f86  mov     eax, [rcx+20h]
0x180008f89  mov     r11, rcx
0x180008f8c  mov     r9d, [rcx+24h]
0x180008f90  mov     r10d, eax
0x180008f93  mov     ecx, r8d
0x180008f96  mov     ebx, 0FFFFFFFFh
0x180008f9b  shr     r10d, cl
0x180008f9e  xchg    ax, ax
0x180008fa0  mov     ecx, eax
0x180008fa2  inc     ebx
0x180008fa4  movsxd  rax, ebx
0x180008fa7  movzx   eax, byte ptr [rax+rdx]
0x180008fab  imul    eax, r10d
0x180008faf  cmp     r9d, eax
0x180008fb2  jb      short loc_180008FA0
0x180008fb4  sub     ecx, eax
0x180008fb6  sub     r9d, eax
0x180008fb9  mov     [r11+20h], ecx
0x180008fbd  mov     rcx, r11
0x180008fc0  mov     [r11+24h], r9d
0x180008fc4  call    ec_dec_normalize
0x180008fc9  mov     eax, ebx
0x180008fcb  add     rsp, 20h
0x180008fcf  pop     rbx
0x180008fd0  retn
```
