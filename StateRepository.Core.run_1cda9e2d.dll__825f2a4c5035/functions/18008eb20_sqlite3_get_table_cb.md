# sqlite3_get_table_cb

- ea: `0x18008eb20`
- end: `0x18008ec5e`
- name: `sqlite3_get_table_cb`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x180001110`
- `0x180005810`
- `0x180005b90`
- `0x18000aac0`
- `0x180047008`
- `0x18008eb20`
- `0x180099814`

## string_xrefs

- `0x18008ebcd`: `sqlite3_get_table() called with two or more incompatible queries`

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
  __int64 v19; // r9
  void *v20; // rax

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
        v20 = (void *)sqlite3_malloc64(v16, v17, v18, v19);
        v15 = v20;
        if ( !v20 )
          goto LABEL_23;
        memcpy_0(v20, *(const void **)(a3 + 8LL * j), v16);
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
0x18008eb20  push    rbx
0x18008eb22  push    rbp
0x18008eb23  push    rsi
0x18008eb24  push    rdi
0x18008eb25  push    r12
0x18008eb27  push    r13
0x18008eb29  push    r14
0x18008eb2b  push    r15
0x18008eb2d  sub     rsp, 28h
0x18008eb31  cmp     dword ptr [rcx+14h], 0
0x18008eb35  mov     r15, r9
0x18008eb38  mov     r14, r8
0x18008eb3b  mov     edi, edx
0x18008eb3d  mov     rbx, rcx
0x18008eb40  jnz     short loc_18008EB49
0x18008eb42  test    r8, r8
0x18008eb45  jz      short loc_18008EB49
0x18008eb47  add     edx, edx
0x18008eb49  mov     r8d, [rcx+10h]
0x18008eb4d  mov     r13d, 1
0x18008eb53  mov     ecx, [rcx+1Ch]
0x18008eb56  add     ecx, edx
0x18008eb58  cmp     ecx, r8d
0x18008eb5b  jbe     short loc_18008EB7E
0x18008eb5d  mov     rcx, [rbx]
0x18008eb60  lea     eax, [rdx+r8*2]
0x18008eb64  mov     edx, eax
0x18008eb66  shl     rdx, 3
0x18008eb6a  mov     [rbx+10h], eax
0x18008eb6d  call    sqlite3Realloc
0x18008eb72  test    rax, rax
0x18008eb75  jz      loc_18008EC3E
0x18008eb7b  mov     [rbx], rax
0x18008eb7e  cmp     dword ptr [rbx+14h], 0
0x18008eb82  jnz     short loc_18008EBBF
0x18008eb84  mov     [rbx+18h], edi
0x18008eb87  xor     esi, esi
0x18008eb89  cmp     esi, edi
0x18008eb8b  jge     short loc_18008EBE6
0x18008eb8d  movsxd  rdx, esi
0x18008eb90  lea     rcx, aS_7; "%s"
0x18008eb97  mov     rdx, [r15+rdx*8]
0x18008eb9b  call    sqlite3_mprintf
0x18008eba0  mov     rdx, rax
0x18008eba3  test    rax, rax
0x18008eba6  jz      loc_18008EC3E
0x18008ebac  mov     ecx, [rbx+1Ch]
0x18008ebaf  mov     rax, [rbx]
0x18008ebb2  mov     [rax+rcx*8], rdx
0x18008ebb6  add     [rbx+1Ch], r13d
0x18008ebba  add     esi, r13d
0x18008ebbd  jmp     short loc_18008EB89
0x18008ebbf  cmp     [rbx+18h], edi
0x18008ebc2  jz      short loc_18008EBE6
0x18008ebc4  mov     rcx, [rbx+8]
0x18008ebc8  call    sqlite3_free
0x18008ebcd  lea     rcx, aSqlite3GetTabl_0; "sqlite3_get_table() called with two or "...
0x18008ebd4  call    sqlite3_mprintf
0x18008ebd9  mov     [rbx+8], rax
0x18008ebdd  mov     [rbx+20h], r13d
0x18008ebe1  mov     eax, r13d
0x18008ebe4  jmp     short loc_18008EC4D
0x18008ebe6  test    r14, r14
0x18008ebe9  jz      short loc_18008EC4B
0x18008ebeb  xor     esi, esi
0x18008ebed  cmp     esi, edi
0x18008ebef  jge     short loc_18008EC47
0x18008ebf1  movsxd  r15, esi
0x18008ebf4  mov     rcx, [r14+r15*8]
0x18008ebf8  test    rcx, rcx
0x18008ebfb  jnz     short loc_18008EC01
0x18008ebfd  xor     ebp, ebp
0x18008ebff  jmp     short loc_18008EC2B
0x18008ec01  call    sqlite3Strlen30
0x18008ec06  add     eax, r13d
0x18008ec09  movsxd  r12, eax
0x18008ec0c  mov     rcx, r12
0x18008ec0f  call    sqlite3_malloc64
0x18008ec14  mov     rbp, rax
0x18008ec17  test    rax, rax
0x18008ec1a  jz      short loc_18008EC3E
0x18008ec1c  mov     rdx, [r14+r15*8]; Src
0x18008ec20  mov     r8, r12; Size
0x18008ec23  mov     rcx, rax; void *
0x18008ec26  call    memcpy_0
0x18008ec2b  mov     edx, [rbx+1Ch]
0x18008ec2e  mov     rcx, [rbx]
0x18008ec31  mov     [rcx+rdx*8], rbp
0x18008ec35  add     [rbx+1Ch], r13d
0x18008ec39  add     esi, r13d
0x18008ec3c  jmp     short loc_18008EBED
0x18008ec3e  mov     dword ptr [rbx+20h], 7
0x18008ec45  jmp     short loc_18008EBE1
0x18008ec47  add     [rbx+14h], r13d
0x18008ec4b  xor     eax, eax
0x18008ec4d  add     rsp, 28h
0x18008ec51  pop     r15
0x18008ec53  pop     r14
0x18008ec55  pop     r13
0x18008ec57  pop     r12
0x18008ec59  pop     rdi
0x18008ec5a  pop     rsi
0x18008ec5b  pop     rbp
0x18008ec5c  pop     rbx
0x18008ec5d  retn
```
