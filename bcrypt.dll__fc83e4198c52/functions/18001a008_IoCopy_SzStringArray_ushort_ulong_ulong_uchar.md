# IoCopy_SzStringArray(ushort * *,ulong,ulong *,uchar *)

- ea: `0x18001a008`
- end: `0x18001a142`
- name: `?IoCopy_SzStringArray@@YAKPEAPEAGKPEAKPEAE@Z`
- size: `314`
- prototype: `unsigned int __fastcall(unsigned __int16 **, unsigned int, unsigned int *, unsigned __int8 *)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x18001253c`
- `0x180019e84`

## callees

- `0x180004120`
- `0x18001a008`
- `0x18001b79d`

## pseudocode

```c
unsigned int __fastcall IoCopy_SzStringArray(
        unsigned __int16 **a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned __int8 *a4)
{
  unsigned __int8 *v4; // r15
  unsigned int *v5; // rsi
  int v8; // r14d
  unsigned __int8 *v9; // rbp
  __int64 i; // rbx
  const unsigned __int16 *v11; // rcx
  unsigned int result; // eax
  unsigned int v13; // esi
  size_t v14; // rbx
  int v15; // [rsp+20h] [rbp-48h]
  unsigned int v16; // [rsp+70h] [rbp+8h] BYREF
  unsigned int *v17; // [rsp+80h] [rbp+18h]
  unsigned int v18; // [rsp+88h] [rbp+20h]

  v17 = a3;
  v16 = 0;
  v4 = a4;
  v5 = a3;
  if ( a3 )
    *a3 = 0;
  if ( !a1 )
    return 87;
  v8 = 0;
  v15 = 8 * a2;
  v9 = a4 ? &a4[8 * a2] : 0LL;
  for ( i = 0; (unsigned int)i < a2; i = (unsigned int)(i + 1) )
  {
    v11 = a1[i];
    if ( !v11 )
      return 87;
    result = SzString_CchLength(v11, &v16, 0);
    if ( result )
      return result;
    if ( !v16 )
      return 87;
    v8 += v16 + 1;
  }
  if ( !v8 )
    return 87;
  if ( v4 )
  {
    v18 = 0;
    if ( a2 )
    {
      v13 = v18;
      do
      {
        SzString_CchLength(a1[v13], &v16, 0);
        v14 = 2LL * (v16 + 1);
        memcpy_0(v9, a1[v13], v14);
        *(_QWORD *)v4 = v9;
        ++v13;
        v9 += v14;
        v4 += 8;
      }
      while ( v13 < a2 );
      v5 = v17;
    }
  }
  if ( v5 )
    *v5 = v15 + ((2 * v8 + 7) & 0xFFFFFFF8);
  return 0;
}

```

## disassembly

```asm
0x18001a008  mov     [rsp+arg_8], rbx
0x18001a00d  mov     [rsp+arg_10], r8
0x18001a012  push    rbp
0x18001a013  push    rsi
0x18001a014  push    rdi
0x18001a015  push    r12
0x18001a017  push    r13
0x18001a019  push    r14
0x18001a01b  push    r15
0x18001a01d  sub     rsp, 30h
0x18001a021  mov     [rsp+68h+arg_0], 0
0x18001a029  mov     r15, r9
0x18001a02c  mov     rsi, r8
0x18001a02f  mov     r12d, edx
0x18001a032  mov     r13, rcx
0x18001a035  test    r8, r8
0x18001a038  jz      short loc_18001A041
0x18001a03a  mov     dword ptr [r8], 0
0x18001a041  test    r13, r13
0x18001a044  jz      loc_18001A127
0x18001a04a  xor     r14d, r14d
0x18001a04d  lea     ecx, ds:0[rdx*8]
0x18001a054  mov     [rsp+68h+var_48], ecx
0x18001a058  test    r15, r15
0x18001a05b  jz      short loc_18001A064
0x18001a05d  mov     ebp, ecx
0x18001a05f  add     rbp, r15
0x18001a062  jmp     short loc_18001A066
0x18001a064  xor     ebp, ebp
0x18001a066  xor     ebx, ebx
0x18001a068  cmp     ebx, r12d
0x18001a06b  jnb     short loc_18001A0A6
0x18001a06d  mov     rcx, [r13+rbx*8+0]; unsigned __int16 *
0x18001a072  test    rcx, rcx
0x18001a075  jz      loc_18001A127
0x18001a07b  xor     r8d, r8d; unsigned int
0x18001a07e  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x18001a083  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x18001a088  test    eax, eax
0x18001a08a  jnz     loc_18001A12C
0x18001a090  mov     eax, [rsp+68h+arg_0]
0x18001a094  test    eax, eax
0x18001a096  jz      loc_18001A127
0x18001a09c  inc     r14d
0x18001a09f  add     r14d, eax
0x18001a0a2  inc     ebx
0x18001a0a4  jmp     short loc_18001A068
0x18001a0a6  test    r14d, r14d
0x18001a0a9  jz      short loc_18001A127
0x18001a0ab  test    r15, r15
0x18001a0ae  jz      short loc_18001A10D
0x18001a0b0  mov     [rsp+68h+arg_18], 0
0x18001a0bb  test    r12d, r12d
0x18001a0be  jz      short loc_18001A10D
0x18001a0c0  mov     esi, [rsp+68h+arg_18]
0x18001a0c7  mov     edi, esi
0x18001a0c9  lea     rdx, [rsp+68h+arg_0]; unsigned int *
0x18001a0ce  xor     r8d, r8d; unsigned int
0x18001a0d1  mov     rcx, [r13+rdi*8+0]; unsigned __int16 *
0x18001a0d6  call    ?SzString_CchLength@@YAKPEBGPEAKK@Z; SzString_CchLength(ushort const *,ulong *,ulong)
0x18001a0db  mov     ebx, [rsp+68h+arg_0]
0x18001a0df  mov     rcx, rbp; void *
0x18001a0e2  mov     rdx, [r13+rdi*8+0]; Src
0x18001a0e7  inc     ebx
0x18001a0e9  add     rbx, rbx
0x18001a0ec  mov     r8, rbx; Size
0x18001a0ef  call    memcpy_0
0x18001a0f4  mov     [r15], rbp
0x18001a0f7  inc     esi
0x18001a0f9  add     rbp, rbx
0x18001a0fc  lea     r15, [r15+8]
0x18001a100  cmp     esi, r12d
0x18001a103  jb      short loc_18001A0C7
0x18001a105  mov     rsi, [rsp+68h+arg_10]
0x18001a10d  test    rsi, rsi
0x18001a110  jz      short loc_18001A123
0x18001a112  lea     eax, ds:7[r14*2]
0x18001a11a  and     eax, 0FFFFFFF8h
0x18001a11d  add     eax, [rsp+68h+var_48]
0x18001a121  mov     [rsi], eax
0x18001a123  xor     eax, eax
0x18001a125  jmp     short loc_18001A12C
0x18001a127  mov     eax, 57h ; 'W'
0x18001a12c  mov     rbx, [rsp+68h+arg_8]
0x18001a131  add     rsp, 30h
0x18001a135  pop     r15
0x18001a137  pop     r14
0x18001a139  pop     r13
0x18001a13b  pop     r12
0x18001a13d  pop     rdi
0x18001a13e  pop     rsi
0x18001a13f  pop     rbp
0x18001a140  retn
```
