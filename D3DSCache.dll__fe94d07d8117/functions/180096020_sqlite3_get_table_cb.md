# sqlite3_get_table_cb

- ea: `0x180096020`
- end: `0x18009615e`
- name: `sqlite3_get_table_cb`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180012470`
- `0x1800201f4`
- `0x18002b81c`
- `0x180096020`
- `0x1800964a0`
- `0x180096550`
- `0x1800a6d08`

## string_xrefs

- `0x1800960cd`: `sqlite3_get_table() called with two or more incompatible queries`

## pseudocode

```c
__int64 __fastcall sqlite3_get_table_cb(__int64 *a1, __int64 a2, __int64 a3, __int64 a4)
{
  int v6; // edi
  __int64 v8; // r8
  __int64 v9; // rcx
  __int64 v10; // rax
  int i; // esi
  int j; // esi
  __int64 v14; // rcx
  void *v15; // rbp
  size_t v16; // r12
  __int64 v17; // rdx
  __int64 v18; // r8
  void *v19; // rax

  v6 = a2;
  if ( !*((_DWORD *)a1 + 5) )
  {
    if ( a3 )
      a2 = (unsigned int)(2 * a2);
  }
  v8 = *((unsigned int *)a1 + 4);
  if ( (int)a2 + *((_DWORD *)a1 + 7) > (unsigned int)v8 )
  {
    v9 = *a1;
    *((_DWORD *)a1 + 4) = a2 + 2 * v8;
    v10 = sqlite3Realloc(v9, 8LL * (unsigned int)(a2 + 2 * v8));
    if ( !v10 )
    {
LABEL_23:
      *((_DWORD *)a1 + 8) = 7;
      return 1;
    }
    *a1 = v10;
  }
  if ( !*((_DWORD *)a1 + 5) )
  {
    *((_DWORD *)a1 + 6) = v6;
    for ( i = 0; i < v6; ++i )
    {
      a2 = sqlite3_mprintf("%s", *(const char **)(a4 + 8LL * i));
      if ( !a2 )
        goto LABEL_23;
      *(_QWORD *)(*a1 + 8LL * (unsigned int)(*((_DWORD *)a1 + 7))++) = a2;
    }
    goto LABEL_15;
  }
  if ( *((_DWORD *)a1 + 6) != v6 )
  {
    sqlite3_free(a1[1]);
    a1[1] = sqlite3_mprintf("sqlite3_get_table() called with two or more incompatible queries");
    *((_DWORD *)a1 + 8) = 1;
    return 1;
  }
LABEL_15:
  if ( a3 )
  {
    for ( j = 0; j < v6; ++j )
    {
      v14 = *(_QWORD *)(a3 + 8LL * j);
      if ( v14 )
      {
        v16 = (int)(sqlite3Strlen30(v14, a2, v8) + 1);
        v19 = (void *)sqlite3_malloc64(v16, v17, v18);
        v15 = v19;
        if ( !v19 )
          goto LABEL_23;
        memcpy_0(v19, *(const void **)(a3 + 8LL * j), v16);
      }
      else
      {
        v15 = 0;
      }
      a2 = *((unsigned int *)a1 + 7);
      *(_QWORD *)(*a1 + 8 * a2) = v15;
      ++*((_DWORD *)a1 + 7);
    }
    ++*((_DWORD *)a1 + 5);
  }
  return 0;
}

```

## disassembly

```asm
0x180096020  push    rbx
0x180096022  push    rbp
0x180096023  push    rsi
0x180096024  push    rdi
0x180096025  push    r12
0x180096027  push    r13
0x180096029  push    r14
0x18009602b  push    r15
0x18009602d  sub     rsp, 28h
0x180096031  cmp     dword ptr [rcx+14h], 0
0x180096035  mov     r15, r9
0x180096038  mov     r14, r8
0x18009603b  mov     edi, edx
0x18009603d  mov     rbx, rcx
0x180096040  jnz     short loc_180096049
0x180096042  test    r8, r8
0x180096045  jz      short loc_180096049
0x180096047  add     edx, edx
0x180096049  mov     r8d, [rcx+10h]
0x18009604d  mov     r13d, 1
0x180096053  mov     ecx, [rcx+1Ch]
0x180096056  add     ecx, edx
0x180096058  cmp     ecx, r8d
0x18009605b  jbe     short loc_18009607E
0x18009605d  mov     rcx, [rbx]
0x180096060  lea     eax, [rdx+r8*2]
0x180096064  mov     edx, eax
0x180096066  shl     rdx, 3
0x18009606a  mov     [rbx+10h], eax
0x18009606d  call    sqlite3Realloc
0x180096072  test    rax, rax
0x180096075  jz      loc_18009613E
0x18009607b  mov     [rbx], rax
0x18009607e  cmp     dword ptr [rbx+14h], 0
0x180096082  jnz     short loc_1800960BF
0x180096084  mov     [rbx+18h], edi
0x180096087  xor     esi, esi
0x180096089  cmp     esi, edi
0x18009608b  jge     short loc_1800960E6
0x18009608d  movsxd  rdx, esi
0x180096090  lea     rcx, aS_10; "%s"
0x180096097  mov     rdx, [r15+rdx*8]
0x18009609b  call    sqlite3_mprintf
0x1800960a0  mov     rdx, rax
0x1800960a3  test    rax, rax
0x1800960a6  jz      loc_18009613E
0x1800960ac  mov     ecx, [rbx+1Ch]
0x1800960af  mov     rax, [rbx]
0x1800960b2  mov     [rax+rcx*8], rdx
0x1800960b6  add     [rbx+1Ch], r13d
0x1800960ba  add     esi, r13d
0x1800960bd  jmp     short loc_180096089
0x1800960bf  cmp     [rbx+18h], edi
0x1800960c2  jz      short loc_1800960E6
0x1800960c4  mov     rcx, [rbx+8]
0x1800960c8  call    sqlite3_free
0x1800960cd  lea     rcx, aSqlite3GetTabl; "sqlite3_get_table() called with two or "...
0x1800960d4  call    sqlite3_mprintf
0x1800960d9  mov     [rbx+8], rax
0x1800960dd  mov     [rbx+20h], r13d
0x1800960e1  mov     eax, r13d
0x1800960e4  jmp     short loc_18009614D
0x1800960e6  test    r14, r14
0x1800960e9  jz      short loc_18009614B
0x1800960eb  xor     esi, esi
0x1800960ed  cmp     esi, edi
0x1800960ef  jge     short loc_180096147
0x1800960f1  movsxd  r15, esi
0x1800960f4  mov     rcx, [r14+r15*8]
0x1800960f8  test    rcx, rcx
0x1800960fb  jnz     short loc_180096101
0x1800960fd  xor     ebp, ebp
0x1800960ff  jmp     short loc_18009612B
0x180096101  call    sqlite3Strlen30
0x180096106  add     eax, r13d
0x180096109  movsxd  r12, eax
0x18009610c  mov     rcx, r12
0x18009610f  call    sqlite3_malloc64
0x180096114  mov     rbp, rax
0x180096117  test    rax, rax
0x18009611a  jz      short loc_18009613E
0x18009611c  mov     rdx, [r14+r15*8]; Src
0x180096120  mov     r8, r12; Size
0x180096123  mov     rcx, rax; void *
0x180096126  call    memcpy_0
0x18009612b  mov     edx, [rbx+1Ch]
0x18009612e  mov     rcx, [rbx]
0x180096131  mov     [rcx+rdx*8], rbp
0x180096135  add     [rbx+1Ch], r13d
0x180096139  add     esi, r13d
0x18009613c  jmp     short loc_1800960ED
0x18009613e  mov     dword ptr [rbx+20h], 7
0x180096145  jmp     short loc_1800960E1
0x180096147  add     [rbx+14h], r13d
0x18009614b  xor     eax, eax
0x18009614d  add     rsp, 28h
0x180096151  pop     r15
0x180096153  pop     r14
0x180096155  pop     r13
0x180096157  pop     r12
0x180096159  pop     rdi
0x18009615a  pop     rsi
0x18009615b  pop     rbp
0x18009615c  pop     rbx
0x18009615d  retn
```
