# BiStringFromGUID

- ea: `0x140020720`
- end: `0x1400207cc`
- name: `BiStringFromGUID`
- size: `172`
- prototype: `__int64 __fastcall(unsigned int *, __int64)`
- caller_count: `9`
- callee_count: `1`
- tags: ``

## callers

- `0x140013ee8`
- `0x140014130`
- `0x14001474c`
- `0x140018890`
- `0x140019038`
- `0x14001a264`
- `0x14001c794`
- `0x140024cf0`
- `0x140025368`

## callees

- `0x140020720`

## import_xrefs

- `msvcrt!swprintf_s` at `0x1400207b7`
- `msvcrt!swprintf_s` at `0x1400207b7`

## pseudocode

```c
__int64 __fastcall BiStringFromGUID(unsigned int *a1, __int64 a2)
{
  int v3; // [rsp+20h] [rbp-88h]
  int v4; // [rsp+28h] [rbp-80h]
  int v5; // [rsp+30h] [rbp-78h]
  int v6; // [rsp+38h] [rbp-70h]
  int v7; // [rsp+40h] [rbp-68h]
  int v8; // [rsp+48h] [rbp-60h]
  int v9; // [rsp+50h] [rbp-58h]
  int v10; // [rsp+58h] [rbp-50h]
  int v11; // [rsp+60h] [rbp-48h]
  int v12; // [rsp+68h] [rbp-40h]

  if ( *(_WORD *)(a2 + 2) < 0x4Eu )
    return 3221225507LL;
  *(_WORD *)a2 = 76;
  v12 = *((unsigned __int8 *)a1 + 15);
  v11 = *((unsigned __int8 *)a1 + 14);
  v10 = *((unsigned __int8 *)a1 + 13);
  v9 = *((unsigned __int8 *)a1 + 12);
  v8 = *((unsigned __int8 *)a1 + 11);
  v7 = *((unsigned __int8 *)a1 + 10);
  v6 = *((unsigned __int8 *)a1 + 9);
  v5 = *((unsigned __int8 *)a1 + 8);
  v4 = *((unsigned __int16 *)a1 + 3);
  v3 = *((unsigned __int16 *)a1 + 2);
  swprintf_s(
    *(wchar_t *const *)(a2 + 8),
    (unsigned __int64)*(unsigned __int16 *)(a2 + 2) >> 1,
    L"{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%02x%02x%02x}",
    *a1,
    v3,
    v4,
    v5,
    v6,
    v7,
    v8,
    v9,
    v10,
    v11,
    v12);
  return 0;
}

```

## disassembly

```asm
0x140020720  push    rbx
0x140020722  push    rbp
0x140020723  push    rsi
0x140020724  push    rdi
0x140020725  push    r14
0x140020727  push    r15
0x140020729  sub     rsp, 78h
0x14002072d  cmp     word ptr [rdx+2], 4Eh ; 'N'
0x140020732  mov     r15, rdx
0x140020735  mov     r14, rcx
0x140020738  jnb     short loc_140020741
0x14002073a  mov     eax, 0C0000023h
0x14002073f  jmp     short loc_1400207BF
0x140020741  mov     word ptr [rdx], 4Ch ; 'L'
0x140020746  movzx   eax, byte ptr [rcx+0Fh]
0x14002074a  movzx   ecx, byte ptr [rcx+0Eh]
0x14002074e  movzx   r8d, byte ptr [r14+0Dh]
0x140020753  movzx   r9d, byte ptr [r14+0Ch]
0x140020758  movzx   r10d, byte ptr [r14+0Bh]
0x14002075d  movzx   r11d, byte ptr [r14+0Ah]
0x140020762  movzx   ebx, byte ptr [r14+9]
0x140020767  movzx   edi, byte ptr [r14+8]
0x14002076c  movzx   esi, word ptr [r14+6]
0x140020771  movzx   edx, word ptr [rdx+2]
0x140020775  movzx   ebp, word ptr [r14+4]
0x14002077a  mov     [rsp+0A8h+var_40], eax
0x14002077e  mov     [rsp+0A8h+var_48], ecx
0x140020782  mov     rcx, [r15+8]; Buffer
0x140020786  mov     [rsp+0A8h+var_50], r8d
0x14002078b  lea     r8, a08lx04x04x02x0; "{%08lx-%04x-%04x-%02x%02x-%02x%02x%02x%"...
0x140020792  mov     [rsp+0A8h+var_58], r9d
0x140020797  mov     r9d, [r14]
0x14002079a  mov     [rsp+0A8h+var_60], r10d
0x14002079f  mov     [rsp+0A8h+var_68], r11d
0x1400207a4  mov     [rsp+0A8h+var_70], ebx
0x1400207a8  mov     [rsp+0A8h+var_78], edi
0x1400207ac  mov     [rsp+0A8h+var_80], esi
0x1400207b0  shr     rdx, 1; BufferCount
0x1400207b3  mov     [rsp+0A8h+var_88], ebp
0x1400207b7  call    cs:__imp_swprintf_s
0x1400207bd  xor     eax, eax
0x1400207bf  add     rsp, 78h
0x1400207c3  pop     r15
0x1400207c5  pop     r14
0x1400207c7  pop     rdi
0x1400207c8  pop     rsi
0x1400207c9  pop     rbp
0x1400207ca  pop     rbx
0x1400207cb  retn
```
