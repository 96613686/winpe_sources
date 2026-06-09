# Dns_CheckedStringLength

- ea: `0x18000e2d4`
- end: `0x18000e33b`
- name: `Dns_CheckedStringLength`
- size: `103`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x1800077b0`
- `0x18000be78`
- `0x18000bfac`
- `0x18000d82c`
- `0x18000e344`

## callees

- `0x18000e2d4`
- `0x180015e84`

## pseudocode

```c
__int64 __fastcall Dns_CheckedStringLength(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  unsigned __int64 v5; // rbp
  __int64 v8; // rax
  unsigned __int64 v9; // rcx
  __int64 result; // rax

  v5 = a2;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
    WPP_SF_SDl(a1, 12, a3, a1, a2, a3);
  *a4 = 0;
  v8 = -1;
  do
    ++v8;
  while ( *(_WORD *)(a1 + 2 * v8) );
  v9 = v8 + 1;
  if ( !a3 )
    v9 = v8;
  if ( v9 >= v5 )
    return 122;
  result = 0;
  *a4 = v9;
  return result;
}

```

## disassembly

```asm
0x18000e2d4  push    rbx
0x18000e2d6  push    rbp
0x18000e2d7  push    rsi
0x18000e2d8  push    rdi
0x18000e2d9  sub     rsp, 38h
0x18000e2dd  mov     rdi, r9
0x18000e2e0  mov     ebp, edx
0x18000e2e2  mov     esi, r8d
0x18000e2e5  mov     rbx, rcx
0x18000e2e8  test    byte ptr cs:xmmword_18001F260+1, 8
0x18000e2ef  jz      short loc_18000E307
0x18000e2f1  mov     [rsp+58h+var_30], r8d
0x18000e2f6  mov     edx, 0Ch
0x18000e2fb  mov     r9, rcx
0x18000e2fe  mov     [rsp+58h+var_38], ebp
0x18000e302  call    WPP_SF_SDl
0x18000e307  xor     edx, edx
0x18000e309  mov     [rdi], edx
0x18000e30b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000e30f  inc     rax
0x18000e312  cmp     [rbx+rax*2], dx
0x18000e316  jnz     short loc_18000E30F
0x18000e318  test    esi, esi
0x18000e31a  lea     rcx, [rax+1]
0x18000e31e  cmovz   rcx, rax
0x18000e322  cmp     rcx, rbp
0x18000e325  jb      short loc_18000E32E
0x18000e327  mov     eax, 7Ah ; 'z'
0x18000e32c  jmp     short loc_18000E332
0x18000e32e  mov     eax, edx
0x18000e330  mov     [rdi], ecx
0x18000e332  add     rsp, 38h
0x18000e336  pop     rdi
0x18000e337  pop     rsi
0x18000e338  pop     rbp
0x18000e339  pop     rbx
0x18000e33a  retn
```
