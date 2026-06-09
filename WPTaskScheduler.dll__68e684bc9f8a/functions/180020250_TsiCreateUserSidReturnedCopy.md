# TsiCreateUserSidReturnedCopy

- ea: `0x180020250`
- end: `0x1800202e6`
- name: `TsiCreateUserSidReturnedCopy`
- size: `150`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001fdfc`

## callees

- `0x18000be70`
- `0x180020250`

## import_xrefs

- `msvcrt!free` at `0x1800202c7`
- `msvcrt!free` at `0x1800202d0`
- `msvcrt!free` at `0x1800202c7`
- `msvcrt!free` at `0x1800202d0`
- `msvcrt!malloc` at `0x18002027e`
- `msvcrt!malloc` at `0x180020294`
- `msvcrt!malloc` at `0x18002027e`
- `msvcrt!malloc` at `0x180020294`

## pseudocode

```c
__int64 __fastcall TsiCreateUserSidReturnedCopy(_QWORD *a1, __int64 a2)
{
  _DWORD *v4; // rbx
  int v5; // edi
  unsigned __int16 *v6; // rax

  if ( !a2 || !*(_DWORD *)(a2 + 8) )
    return 0;
  if ( !a1 )
  {
    v4 = 0;
    v5 = -2147467261;
LABEL_10:
    free(v4);
    return (unsigned int)v5;
  }
  v4 = malloc(0x10u);
  v5 = -2147024882;
  if ( !v4 )
    goto LABEL_10;
  v6 = (unsigned __int16 *)malloc(*(unsigned int *)(a2 + 8));
  *(_QWORD *)v4 = v6;
  if ( !v6
    || (v4[2] = *(_DWORD *)(a2 + 8),
        v5 = StringCchCopyW(v6, (unsigned __int64)*(unsigned int *)(a2 + 8) >> 1, *(const unsigned __int16 **)a2),
        v5 < 0) )
  {
    free(*(void **)v4);
    goto LABEL_10;
  }
  *a1 = v4;
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180020250  push    rbx
0x180020252  push    rsi
0x180020253  push    rdi
0x180020254  push    r14
0x180020256  sub     rsp, 28h
0x18002025a  mov     rsi, rdx
0x18002025d  mov     r14, rcx
0x180020260  test    rdx, rdx
0x180020263  jz      short loc_1800202D8
0x180020265  cmp     dword ptr [rdx+8], 0
0x180020269  jz      short loc_1800202D8
0x18002026b  test    rcx, rcx
0x18002026e  jnz     short loc_180020279
0x180020270  xor     ebx, ebx
0x180020272  mov     edi, 80004003h
0x180020277  jmp     short loc_1800202CD
0x180020279  mov     ecx, 10h; Size
0x18002027e  call    cs:__imp_malloc
0x180020284  mov     rbx, rax
0x180020287  mov     edi, 8007000Eh
0x18002028c  test    rax, rax
0x18002028f  jz      short loc_1800202CD
0x180020291  mov     ecx, [rsi+8]; Size
0x180020294  call    cs:__imp_malloc
0x18002029a  mov     [rbx], rax
0x18002029d  mov     rcx, rax; unsigned __int16 *
0x1800202a0  test    rax, rax
0x1800202a3  jz      short loc_1800202C4
0x1800202a5  mov     eax, [rsi+8]
0x1800202a8  mov     [rbx+8], eax
0x1800202ab  mov     edx, [rsi+8]
0x1800202ae  mov     r8, [rsi]; unsigned __int16 *
0x1800202b1  shr     rdx, 1; unsigned __int64
0x1800202b4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800202b9  mov     edi, eax
0x1800202bb  test    eax, eax
0x1800202bd  js      short loc_1800202C4
0x1800202bf  mov     [r14], rbx
0x1800202c2  jmp     short loc_1800202DA
0x1800202c4  mov     rcx, [rbx]; Block
0x1800202c7  call    cs:__imp_free
0x1800202cd  mov     rcx, rbx; Block
0x1800202d0  call    cs:__imp_free
0x1800202d6  jmp     short loc_1800202DA
0x1800202d8  xor     edi, edi
0x1800202da  mov     eax, edi
0x1800202dc  add     rsp, 28h
0x1800202e0  pop     r14
0x1800202e2  pop     rdi
0x1800202e3  pop     rsi
0x1800202e4  pop     rbx
0x1800202e5  retn
```
