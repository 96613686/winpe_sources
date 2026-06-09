# ec_dec_bit_logp

- ea: `0x180008eb0`
- end: `0x180008ef9`
- name: `ec_dec_bit_logp`
- size: `73`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `reparse_path`

## callers

- `0x1800022f0`
- `0x180005aa0`
- `0x180009400`
- `0x18000bf50`
- `0x18000d040`
- `0x180010d80`

## callees

- `0x180008eb0`
- `0x180009040`

## pseudocode

```c
_BOOL8 __fastcall ec_dec_bit_logp(__int64 a1, char a2)
{
  unsigned int v2; // r10d
  unsigned int v3; // r9d
  unsigned int v4; // edx
  BOOL v5; // ebx
  unsigned int v6; // r10d

  v2 = *(_DWORD *)(a1 + 32);
  v3 = *(_DWORD *)(a1 + 36);
  v4 = v2 >> a2;
  v5 = v3 < v4;
  if ( v3 >= v4 )
    *(_DWORD *)(a1 + 36) = v3 - v4;
  v6 = v2 - v4;
  if ( v3 >= v4 )
    v4 = v6;
  *(_DWORD *)(a1 + 32) = v4;
  ec_dec_normalize(a1);
  return v5;
}

```

## disassembly

```asm
0x180008eb0  push    rbx
0x180008eb2  sub     rsp, 20h
0x180008eb6  mov     r10d, [rcx+20h]
0x180008eba  xor     ebx, ebx
0x180008ebc  mov     r9d, [rcx+24h]
0x180008ec0  mov     r8, rcx
0x180008ec3  mov     ecx, edx
0x180008ec5  mov     edx, r10d
0x180008ec8  shr     edx, cl
0x180008eca  cmp     r9d, edx
0x180008ecd  setb    bl
0x180008ed0  jb      short loc_180008EDB
0x180008ed2  mov     ecx, r9d
0x180008ed5  sub     ecx, edx
0x180008ed7  mov     [r8+24h], ecx
0x180008edb  sub     r10d, edx
0x180008ede  mov     rcx, r8
0x180008ee1  cmp     r9d, edx
0x180008ee4  cmovnb  edx, r10d
0x180008ee8  mov     [r8+20h], edx
0x180008eec  call    ec_dec_normalize
0x180008ef1  mov     eax, ebx
0x180008ef3  add     rsp, 20h
0x180008ef7  pop     rbx
0x180008ef8  retn
```
