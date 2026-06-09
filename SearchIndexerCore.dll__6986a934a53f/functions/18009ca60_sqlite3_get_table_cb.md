# sqlite3_get_table_cb

- ea: `0x18009ca60`
- end: `0x18009cb9e`
- name: `sqlite3_get_table_cb`
- size: `318`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x18001eb90`
- `0x1800310a0`
- `0x180041eb0`
- `0x180046dd0`
- `0x180047da0`
- `0x18009ca60`
- `0x1800af620`

## string_xrefs

- `0x18009cb0d`: `sqlite3_get_table() called with two or more incompatible queries`

## pseudocode

```c
__int64 __fastcall sqlite3_get_table_cb(__int64 *a1, int a2, __int64 a3, __int64 a4)
{
  int v6; // edi
  unsigned int v8; // r8d
  __int64 v9; // rcx
  __int64 v10; // rax
  int i; // esi
  __int64 v12; // rdx
  int j; // esi
  __int64 v15; // rcx
  void *v16; // rbp
  size_t v17; // r12
  void *v18; // rax

  v6 = a2;
  if ( !*((_DWORD *)a1 + 5) )
  {
    if ( a3 )
      a2 *= 2;
  }
  v8 = *((_DWORD *)a1 + 4);
  if ( a2 + *((_DWORD *)a1 + 7) > v8 )
  {
    v9 = *a1;
    *((_DWORD *)a1 + 4) = a2 + 2 * v8;
    v10 = sqlite3Realloc(v9, 8LL * (a2 + 2 * v8));
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
      v12 = sqlite3_mprintf("%s", *(const char **)(a4 + 8LL * i));
      if ( !v12 )
        goto LABEL_23;
      *(_QWORD *)(*a1 + 8LL * (unsigned int)(*((_DWORD *)a1 + 7))++) = v12;
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
      v15 = *(_QWORD *)(a3 + 8LL * j);
      if ( v15 )
      {
        v17 = (int)(sqlite3Strlen30(v15) + 1);
        v18 = (void *)sqlite3_malloc64(v17);
        v16 = v18;
        if ( !v18 )
          goto LABEL_23;
        memcpy_0(v18, *(const void **)(a3 + 8LL * j), v17);
      }
      else
      {
        v16 = 0;
      }
      *(_QWORD *)(*a1 + 8LL * (unsigned int)(*((_DWORD *)a1 + 7))++) = v16;
    }
    ++*((_DWORD *)a1 + 5);
  }
  return 0;
}

```

## disassembly

```asm
0x18009ca60  push    rbx
0x18009ca62  push    rbp
0x18009ca63  push    rsi
0x18009ca64  push    rdi
0x18009ca65  push    r12
0x18009ca67  push    r13
0x18009ca69  push    r14
0x18009ca6b  push    r15
0x18009ca6d  sub     rsp, 28h
0x18009ca71  cmp     dword ptr [rcx+14h], 0
0x18009ca75  mov     r15, r9
0x18009ca78  mov     r14, r8
0x18009ca7b  mov     edi, edx
0x18009ca7d  mov     rbx, rcx
0x18009ca80  jnz     short loc_18009CA89
0x18009ca82  test    r8, r8
0x18009ca85  jz      short loc_18009CA89
0x18009ca87  add     edx, edx
0x18009ca89  mov     r8d, [rcx+10h]
0x18009ca8d  mov     r13d, 1
0x18009ca93  mov     ecx, [rcx+1Ch]
0x18009ca96  add     ecx, edx
0x18009ca98  cmp     ecx, r8d
0x18009ca9b  jbe     short loc_18009CABE
0x18009ca9d  mov     rcx, [rbx]
0x18009caa0  lea     eax, [rdx+r8*2]
0x18009caa4  mov     edx, eax
0x18009caa6  shl     rdx, 3
0x18009caaa  mov     [rbx+10h], eax
0x18009caad  call    sqlite3Realloc
0x18009cab2  test    rax, rax
0x18009cab5  jz      loc_18009CB7E
0x18009cabb  mov     [rbx], rax
0x18009cabe  cmp     dword ptr [rbx+14h], 0
0x18009cac2  jnz     short loc_18009CAFF
0x18009cac4  mov     [rbx+18h], edi
0x18009cac7  xor     esi, esi
0x18009cac9  cmp     esi, edi
0x18009cacb  jge     short loc_18009CB26
0x18009cacd  movsxd  rdx, esi
0x18009cad0  lea     rcx, aS_7; "%s"
0x18009cad7  mov     rdx, [r15+rdx*8]
0x18009cadb  call    sqlite3_mprintf
0x18009cae0  mov     rdx, rax
0x18009cae3  test    rax, rax
0x18009cae6  jz      loc_18009CB7E
0x18009caec  mov     ecx, [rbx+1Ch]
0x18009caef  mov     rax, [rbx]
0x18009caf2  mov     [rax+rcx*8], rdx
0x18009caf6  add     [rbx+1Ch], r13d
0x18009cafa  add     esi, r13d
0x18009cafd  jmp     short loc_18009CAC9
0x18009caff  cmp     [rbx+18h], edi
0x18009cb02  jz      short loc_18009CB26
0x18009cb04  mov     rcx, [rbx+8]
0x18009cb08  call    sqlite3_free
0x18009cb0d  lea     rcx, aSqlite3GetTabl_0; "sqlite3_get_table() called with two or "...
0x18009cb14  call    sqlite3_mprintf
0x18009cb19  mov     [rbx+8], rax
0x18009cb1d  mov     [rbx+20h], r13d
0x18009cb21  mov     eax, r13d
0x18009cb24  jmp     short loc_18009CB8D
0x18009cb26  test    r14, r14
0x18009cb29  jz      short loc_18009CB8B
0x18009cb2b  xor     esi, esi
0x18009cb2d  cmp     esi, edi
0x18009cb2f  jge     short loc_18009CB87
0x18009cb31  movsxd  r15, esi
0x18009cb34  mov     rcx, [r14+r15*8]
0x18009cb38  test    rcx, rcx
0x18009cb3b  jnz     short loc_18009CB41
0x18009cb3d  xor     ebp, ebp
0x18009cb3f  jmp     short loc_18009CB6B
0x18009cb41  call    sqlite3Strlen30
0x18009cb46  add     eax, r13d
0x18009cb49  movsxd  r12, eax
0x18009cb4c  mov     rcx, r12
0x18009cb4f  call    sqlite3_malloc64
0x18009cb54  mov     rbp, rax
0x18009cb57  test    rax, rax
0x18009cb5a  jz      short loc_18009CB7E
0x18009cb5c  mov     rdx, [r14+r15*8]; Src
0x18009cb60  mov     r8, r12; Size
0x18009cb63  mov     rcx, rax; void *
0x18009cb66  call    memcpy_0
0x18009cb6b  mov     edx, [rbx+1Ch]
0x18009cb6e  mov     rcx, [rbx]
0x18009cb71  mov     [rcx+rdx*8], rbp
0x18009cb75  add     [rbx+1Ch], r13d
0x18009cb79  add     esi, r13d
0x18009cb7c  jmp     short loc_18009CB2D
0x18009cb7e  mov     dword ptr [rbx+20h], 7
0x18009cb85  jmp     short loc_18009CB21
0x18009cb87  add     [rbx+14h], r13d
0x18009cb8b  xor     eax, eax
0x18009cb8d  add     rsp, 28h
0x18009cb91  pop     r15
0x18009cb93  pop     r14
0x18009cb95  pop     r13
0x18009cb97  pop     r12
0x18009cb99  pop     rdi
0x18009cb9a  pop     rsi
0x18009cb9b  pop     rbp
0x18009cb9c  pop     rbx
0x18009cb9d  retn
```
