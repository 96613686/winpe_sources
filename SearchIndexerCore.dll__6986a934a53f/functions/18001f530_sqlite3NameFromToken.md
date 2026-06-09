# sqlite3NameFromToken

- ea: `0x18001f530`
- end: `0x18001f6de`
- name: `sqlite3NameFromToken`
- size: `430`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `18`
- callee_count: `3`
- tags: ``

## callers

- `0x18000213c`
- `0x1800142d0`
- `0x18001d1c8`
- `0x18001ebb8`
- `0x18001f484`
- `0x180058a38`
- `0x180058b64`
- `0x1800656dc`
- `0x180072cf0`
- `0x180073c34`
- `0x180075d14`
- `0x180076344`
- `0x180076544`
- `0x18008f450`
- `0x18008fcd0`
- `0x180091ff0`
- `0x180093bb0`
- `0x180097b90`

## callees

- `0x1800163a0`
- `0x18001f530`
- `0x1800af620`

## pseudocode

```c
_QWORD *__fastcall sqlite3NameFromToken(__int64 a1, __int64 a2)
{
  int v2; // edi
  const void *v3; // rbp
  size_t v4; // rsi
  unsigned __int64 v5; // rdx
  _QWORD *v6; // rbx
  __int64 v7; // rax
  char v9; // r9
  int i; // ecx
  char v11; // dl
  __int64 v12; // rax

  v2 = 0;
  if ( !a2 )
    return 0;
  v3 = *(const void **)a2;
  if ( !*(_QWORD *)a2 )
    return 0;
  v4 = *(unsigned int *)(a2 + 8);
  v5 = v4 + 1;
  if ( v4 + 1 > *(unsigned __int16 *)(a1 + 420) )
  {
    if ( *(_DWORD *)(a1 + 416) )
    {
      if ( *(_BYTE *)(a1 + 103) )
      {
        v6 = 0;
        goto LABEL_7;
      }
      goto LABEL_26;
    }
    ++*(_DWORD *)(a1 + 436);
    v6 = (_QWORD *)dbMallocRawFinish(a1, v5);
  }
  else
  {
    if ( v5 > 0x80 )
      goto LABEL_11;
    v6 = *(_QWORD **)(a1 + 472);
    if ( v6 )
    {
      *(_QWORD *)(a1 + 472) = *v6;
      ++*(_DWORD *)(a1 + 432);
      goto LABEL_7;
    }
    v6 = *(_QWORD **)(a1 + 464);
    if ( v6 )
    {
      *(_QWORD *)(a1 + 464) = *v6;
      ++*(_DWORD *)(a1 + 432);
    }
    else
    {
LABEL_11:
      v6 = *(_QWORD **)(a1 + 456);
      if ( v6 )
      {
        *(_QWORD *)(a1 + 456) = *v6;
        ++*(_DWORD *)(a1 + 432);
        goto LABEL_7;
      }
      v6 = *(_QWORD **)(a1 + 448);
      if ( !v6 )
      {
        ++*(_DWORD *)(a1 + 440);
LABEL_26:
        v6 = (_QWORD *)dbMallocRawFinish(a1, v5);
        goto LABEL_7;
      }
      v12 = *v6;
      ++*(_DWORD *)(a1 + 432);
      *(_QWORD *)(a1 + 448) = v12;
    }
  }
LABEL_7:
  if ( v6 )
  {
    memcpy_0(v6, v3, v4);
    *((_BYTE *)v6 + v4) = 0;
    v7 = *(unsigned __int8 *)v6;
    if ( *((char *)&qword_1800B4FF0 + v7) < 0 )
    {
      v9 = *(_BYTE *)v6;
      if ( (_BYTE)v7 == 91 )
        v9 = 93;
      for ( i = 1; ; ++i )
      {
        v11 = *((_BYTE *)v6 + i);
        if ( v11 == v9 )
        {
          if ( *((_BYTE *)v6 + i + 1) != v9 )
          {
            *((_BYTE *)v6 + v2) = 0;
            return v6;
          }
          ++i;
          v11 = v9;
        }
        *((_BYTE *)v6 + v2++) = v11;
      }
    }
  }
  return v6;
}

```

## disassembly

```asm
0x18001f530  push    rdi
0x18001f532  sub     rsp, 20h
0x18001f536  xor     edi, edi
0x18001f538  test    rdx, rdx
0x18001f53b  jz      loc_18001F663
0x18001f541  mov     [rsp+28h+arg_8], rbp
0x18001f546  mov     rbp, [rdx]
0x18001f549  test    rbp, rbp
0x18001f54c  jz      loc_18001F6BB
0x18001f552  movzx   eax, word ptr [rcx+1A4h]
0x18001f559  mov     [rsp+28h+arg_0], rbx
0x18001f55e  mov     [rsp+28h+arg_10], rsi
0x18001f563  mov     esi, [rdx+8]
0x18001f566  lea     rdx, [rsi+1]
0x18001f56a  cmp     rdx, rax
0x18001f56d  ja      loc_18001F64D
0x18001f573  cmp     rdx, 80h
0x18001f57a  ja      short loc_18001F5E7
0x18001f57c  mov     rbx, [rcx+1D8h]
0x18001f583  test    rbx, rbx
0x18001f586  jz      short loc_18001F5D7
0x18001f588  mov     rax, [rbx]
0x18001f58b  mov     [rcx+1D8h], rax
0x18001f592  inc     dword ptr [rcx+1B0h]
0x18001f598  test    rbx, rbx
0x18001f59b  jz      short loc_18001F5BF
0x18001f59d  mov     r8, rsi; Size
0x18001f5a0  mov     rdx, rbp; Src
0x18001f5a3  mov     rcx, rbx; void *
0x18001f5a6  call    memcpy_0
0x18001f5ab  mov     [rsi+rbx], dil
0x18001f5af  lea     rcx, qword_1800B4FF0
0x18001f5b6  movzx   eax, byte ptr [rbx]
0x18001f5b9  cmp     [rax+rcx], dil
0x18001f5bd  jl      short loc_18001F605
0x18001f5bf  mov     rsi, [rsp+28h+arg_10]
0x18001f5c4  mov     rax, rbx
0x18001f5c7  mov     rbx, [rsp+28h+arg_0]
0x18001f5cc  mov     rbp, [rsp+28h+arg_8]
0x18001f5d1  add     rsp, 20h
0x18001f5d5  pop     rdi
0x18001f5d6  retn
0x18001f5d7  mov     rbx, [rcx+1D0h]
0x18001f5de  test    rbx, rbx
0x18001f5e1  jnz     loc_18001F6A6
0x18001f5e7  mov     rbx, [rcx+1C8h]
0x18001f5ee  test    rbx, rbx
0x18001f5f1  jz      short loc_18001F66C
0x18001f5f3  mov     rax, [rbx]
0x18001f5f6  mov     [rcx+1C8h], rax
0x18001f5fd  inc     dword ptr [rcx+1B0h]
0x18001f603  jmp     short loc_18001F598
0x18001f605  mov     ecx, 5Dh ; ']'
0x18001f60a  cmp     al, 5Bh ; '['
0x18001f60c  mov     r9d, eax
0x18001f60f  cmovz   r9d, ecx
0x18001f613  mov     ecx, 1
0x18001f618  nop     dword ptr [rax+rax+00000000h]
0x18001f620  movsxd  rax, ecx
0x18001f623  movsxd  r8, edi
0x18001f626  movzx   edx, byte ptr [rax+rbx]
0x18001f62a  cmp     dl, r9b
0x18001f62d  jz      short loc_18001F639
0x18001f62f  inc     ecx
0x18001f631  mov     [r8+rbx], dl
0x18001f635  inc     edi
0x18001f637  jmp     short loc_18001F620
0x18001f639  movsxd  rax, ecx
0x18001f63c  cmp     [rax+rbx+1], r9b
0x18001f641  jz      short loc_18001F69E
0x18001f643  mov     byte ptr [r8+rbx], 0
0x18001f648  jmp     loc_18001F5BF
0x18001f64d  cmp     [rcx+1A0h], edi
0x18001f653  jz      short loc_18001F68B
0x18001f655  cmp     [rcx+67h], dil
0x18001f659  jz      short loc_18001F67E
0x18001f65b  mov     rbx, rdi
0x18001f65e  jmp     loc_18001F598
0x18001f663  mov     rax, rdi
0x18001f666  add     rsp, 20h
0x18001f66a  pop     rdi
0x18001f66b  retn
0x18001f66c  mov     rbx, [rcx+1C0h]
0x18001f673  test    rbx, rbx
0x18001f676  jnz     short loc_18001F6C9
0x18001f678  inc     dword ptr [rcx+1B8h]
0x18001f67e  call    dbMallocRawFinish
0x18001f683  mov     rbx, rax
0x18001f686  jmp     loc_18001F598
0x18001f68b  inc     dword ptr [rcx+1B4h]
0x18001f691  call    dbMallocRawFinish
0x18001f696  mov     rbx, rax
0x18001f699  jmp     loc_18001F598
0x18001f69e  inc     ecx
0x18001f6a0  movzx   edx, r9b
0x18001f6a4  jmp     short loc_18001F62F
0x18001f6a6  mov     rax, [rbx]
0x18001f6a9  mov     [rcx+1D0h], rax
0x18001f6b0  inc     dword ptr [rcx+1B0h]
0x18001f6b6  jmp     loc_18001F598
0x18001f6bb  mov     rbp, [rsp+28h+arg_8]
0x18001f6c0  mov     rax, rdi
0x18001f6c3  add     rsp, 20h
0x18001f6c7  pop     rdi
0x18001f6c8  retn
0x18001f6c9  mov     rax, [rbx]
0x18001f6cc  inc     dword ptr [rcx+1B0h]
0x18001f6d2  mov     [rcx+1C0h], rax
0x18001f6d9  jmp     loc_18001F598
```
