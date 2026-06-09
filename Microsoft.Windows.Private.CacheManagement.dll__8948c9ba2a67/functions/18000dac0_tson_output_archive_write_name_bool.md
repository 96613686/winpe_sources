# tson::output_archive::write_name(bool)

- ea: `0x18000dac0`
- end: `0x18000de07`
- name: `?write_name@output_archive@tson@@AEAA_N_N@Z`
- size: `839`
- prototype: `char __fastcall(tson::output_archive *this, char)`
- caller_count: `4`
- callee_count: `4`
- tags: ``

## callers

- `0x180009810`
- `0x18000aec0`
- `0x18000d6b0`
- `0x18000de10`

## callees

- `0x18000dac0`
- `0x18000de80`
- `0x18001cf40`
- `0x18001d600`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000dbe3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000ddd7`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000dbe3`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x18000ddd7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000db93`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dbc3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dbd7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dd92`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000ddcb`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000db93`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dbc3`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dbd7`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000dd92`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x18000ddcb`

## pseudocode

```c
char __fastcall tson::output_archive::write_name(tson::output_archive *this, char a2)
{
  char *v2; // rdi
  __int64 v4; // rax
  int v6; // eax
  __int64 v7; // rsi
  __int64 v8; // r14
  _WORD *v9; // rsi
  _WORD *v10; // rcx
  unsigned __int64 v11; // rbp
  __int64 v12; // rsi
  tson::write_buffer *v13; // rbx
  char *v15; // r14
  tson::write_buffer **v16; // rsi
  tson::write_buffer *v17; // rdi
  tson::write_buffer **v18; // rbp
  char *v19; // r15
  tson::write_buffer *v20; // rdi
  char v21; // al
  tson::write_buffer *v22; // rsi
  size_t v23; // rdi
  const void *v24; // r14
  void *v25; // rcx
  size_t v26; // rbp

  v2 = (char *)this + 24;
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    v2 = &v2[4 * v4 - 4];
  else
    *v2 = 1;
  v6 = *((_DWORD *)v2 + 1);
  if ( v6 == 2 )
  {
    *((_DWORD *)v2 + 1) = 3;
    v7 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v7 + 2072) < *(_QWORD *)(v7 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v7 + 2072))++ = 3;
    }
    v8 = *((_QWORD *)this + 18);
    v9 = (_WORD *)((char *)this + 10);
    if ( *(_QWORD *)(v8 + 2080) - *(_QWORD *)(v8 + 2072) < 2u
      && !tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 2u) )
    {
      goto LABEL_20;
    }
    v10 = *(_WORD **)(v8 + 2072);
    v11 = *(_QWORD *)(v8 + 2080) - (_QWORD)v10;
    if ( !v10 )
      goto LABEL_11;
    if ( this == (tson::output_archive *)-10LL || v11 < 2 )
    {
      memset(v10, 0, *(_QWORD *)(v8 + 2080) - (_QWORD)v10);
      if ( this == (tson::output_archive *)-10LL )
      {
LABEL_11:
        *_errno() = 22;
LABEL_18:
        _invalid_parameter_noinfo();
        goto LABEL_19;
      }
      if ( v11 < 2 )
      {
        *_errno() = 34;
        goto LABEL_18;
      }
    }
    else
    {
      *v10 = *v9;
    }
LABEL_19:
    *(_QWORD *)(v8 + 2072) += 2LL;
    v9 = (_WORD *)((char *)this + 10);
LABEL_20:
    *v9 = 0;
    goto LABEL_25;
  }
  if ( !v6 )
  {
    *((_DWORD *)v2 + 1) = 1;
    v12 = *((_QWORD *)this + 18);
    if ( *(_QWORD *)(v12 + 2072) < *(_QWORD *)(v12 + 2080)
      || tson::write_buffer::reserve(*((tson::write_buffer **)this + 18), 1u) )
    {
      *(_BYTE *)(*(_QWORD *)(v12 + 2072))++ = 1;
    }
  }
LABEL_25:
  *((_QWORD *)this + 2) = 0;
  if ( *((_DWORD *)v2 + 1) == 3 )
    return 1;
  if ( !a2 )
  {
    v15 = (char *)this + 8;
    if ( !*(_QWORD *)this )
    {
      *v15 = 1;
      *(_QWORD *)this = "-";
    }
    v16 = (tson::write_buffer **)((char *)this + 144);
    v17 = (tson::write_buffer *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 2) = *((_QWORD *)v17 + 259) - *((_QWORD *)v17 + 258);
    if ( *((_QWORD *)v17 + 259) < *((_QWORD *)v17 + 260)
      || (v18 = (tson::write_buffer **)((char *)this + 144), v19 = (char *)this + 8,
                                                             tson::write_buffer::reserve(v17, 1u)) )
    {
      v18 = (tson::write_buffer **)((char *)this + 144);
      v19 = (char *)this + 8;
      *(_BYTE *)(*((_QWORD *)v17 + 259))++ = 5;
    }
    v20 = *v16;
    if ( *((_QWORD *)*v16 + 259) < *((_QWORD *)*v16 + 260) || tson::write_buffer::reserve(*v16, 1u) )
    {
      v21 = *v15;
      v16 = v18;
      v15 = v19;
      *(_BYTE *)(*((_QWORD *)v20 + 259))++ = v21;
    }
    v22 = *v16;
    v23 = (unsigned __int8)*v15;
    v24 = *(const void **)this;
    if ( *((_QWORD *)v22 + 260) - *((_QWORD *)v22 + 259) < v23 )
    {
      _mm_lfence();
      if ( !tson::write_buffer::reserve(v22, (unsigned int)v23) )
        goto LABEL_52;
    }
    v25 = (void *)*((_QWORD *)v22 + 259);
    v26 = *((_QWORD *)v22 + 260) - (_QWORD)v25;
    if ( v23 )
    {
      if ( !v25 )
      {
LABEL_43:
        *_errno() = 22;
LABEL_50:
        _invalid_parameter_noinfo();
        goto LABEL_51;
      }
      if ( v24 && v26 >= v23 )
      {
        memmove(v25, v24, v23);
      }
      else
      {
        memset(v25, 0, *((_QWORD *)v22 + 260) - (_QWORD)v25);
        if ( !v24 )
          goto LABEL_43;
        if ( v26 < v23 )
        {
          *_errno() = 34;
          goto LABEL_50;
        }
      }
    }
LABEL_51:
    *((_QWORD *)v22 + 259) += v23;
LABEL_52:
    *(_QWORD *)this = 0;
    return 1;
  }
  *(_QWORD *)this = 0;
  v13 = (tson::write_buffer *)*((_QWORD *)this + 18);
  if ( *((_QWORD *)v13 + 259) < *((_QWORD *)v13 + 260) || tson::write_buffer::reserve(v13, 1u) )
    *(_BYTE *)(*((_QWORD *)v13 + 259))++ = 6;
  return 0;
}

```

## disassembly

```asm
0x18000dac0  mov     [rsp+arg_18], rbx
0x18000dac5  push    rdi
0x18000dac6  push    r12
0x18000dac8  push    r15
0x18000daca  sub     rsp, 20h
0x18000dace  lea     rdi, [rcx+18h]
0x18000dad2  movzx   r15d, dl
0x18000dad6  mov     rax, [rdi+68h]
0x18000dada  mov     rbx, rcx
0x18000dadd  test    rax, rax
0x18000dae0  jz      short loc_18000DAEC
0x18000dae2  lea     rdi, [rdi+rax*4]
0x18000dae6  add     rdi, 0FFFFFFFFFFFFFFFCh
0x18000daea  jmp     short loc_18000DAEF
0x18000daec  mov     byte ptr [rdi], 1
0x18000daef  mov     eax, [rdi+4]
0x18000daf2  xor     r12d, r12d
0x18000daf5  mov     [rsp+38h+arg_0], rbp
0x18000dafa  mov     [rsp+38h+arg_8], rsi
0x18000daff  mov     [rsp+38h+arg_10], r14
0x18000db04  cmp     eax, 2
0x18000db07  jnz     loc_18000DBFB
0x18000db0d  mov     dword ptr [rdi+4], 3
0x18000db14  mov     rsi, [rcx+90h]
0x18000db1b  mov     rax, [rsi+820h]
0x18000db22  cmp     [rsi+818h], rax
0x18000db29  jb      short loc_18000DB3C
0x18000db2b  mov     edx, 1; unsigned __int64
0x18000db30  mov     rcx, rsi; this
0x18000db33  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000db38  test    al, al
0x18000db3a  jz      short loc_18000DB4D
0x18000db3c  mov     rax, [rsi+818h]
0x18000db43  mov     byte ptr [rax], 3
0x18000db46  inc     qword ptr [rsi+818h]
0x18000db4d  mov     r14, [rbx+90h]
0x18000db54  lea     rsi, [rbx+0Ah]
0x18000db58  mov     rax, [r14+820h]
0x18000db5f  sub     rax, [r14+818h]
0x18000db66  cmp     rax, 2
0x18000db6a  jnb     short loc_18000DB7D
0x18000db6c  mov     edx, 2; unsigned __int64
0x18000db71  mov     rcx, r14; this
0x18000db74  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000db79  test    al, al
0x18000db7b  jz      short loc_18000DBF5
0x18000db7d  mov     rcx, [r14+818h]; void *
0x18000db84  mov     rbp, [r14+820h]
0x18000db8b  sub     rbp, rcx
0x18000db8e  test    rcx, rcx
0x18000db91  jnz     short loc_18000DBA1
0x18000db93  call    cs:__imp__errno
0x18000db99  mov     dword ptr [rax], 16h
0x18000db9f  jmp     short loc_18000DBE3
0x18000dba1  test    rsi, rsi
0x18000dba4  jz      short loc_18000DBB4
0x18000dba6  cmp     rbp, 2
0x18000dbaa  jb      short loc_18000DBB4
0x18000dbac  movzx   eax, word ptr [rsi]
0x18000dbaf  mov     [rcx], ax
0x18000dbb2  jmp     short loc_18000DBE9
0x18000dbb4  mov     r8, rbp; Size
0x18000dbb7  xor     edx, edx; Val
0x18000dbb9  call    memset
0x18000dbbe  test    rsi, rsi
0x18000dbc1  jnz     short loc_18000DBD1
0x18000dbc3  call    cs:__imp__errno
0x18000dbc9  mov     dword ptr [rax], 16h
0x18000dbcf  jmp     short loc_18000DBE3
0x18000dbd1  cmp     rbp, 2
0x18000dbd5  jnb     short loc_18000DBE9
0x18000dbd7  call    cs:__imp__errno
0x18000dbdd  mov     dword ptr [rax], 22h ; '"'
0x18000dbe3  call    cs:__imp__invalid_parameter_noinfo
0x18000dbe9  add     qword ptr [r14+818h], 2
0x18000dbf1  lea     rsi, [rbx+0Ah]
0x18000dbf5  mov     [rsi], r12w
0x18000dbf9  jmp     short loc_18000DC3F
0x18000dbfb  test    eax, eax
0x18000dbfd  jnz     short loc_18000DC3F
0x18000dbff  mov     dword ptr [rdi+4], 1
0x18000dc06  mov     rsi, [rcx+90h]
0x18000dc0d  mov     rax, [rsi+820h]
0x18000dc14  cmp     [rsi+818h], rax
0x18000dc1b  jb      short loc_18000DC2E
0x18000dc1d  mov     edx, 1; unsigned __int64
0x18000dc22  mov     rcx, rsi; this
0x18000dc25  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dc2a  test    al, al
0x18000dc2c  jz      short loc_18000DC3F
0x18000dc2e  mov     rax, [rsi+818h]
0x18000dc35  mov     byte ptr [rax], 1
0x18000dc38  inc     qword ptr [rsi+818h]
0x18000dc3f  mov     [rbx+10h], r12
0x18000dc43  cmp     dword ptr [rdi+4], 3
0x18000dc47  jz      loc_18000DDE7
0x18000dc4d  test    r15b, r15b
0x18000dc50  jz      short loc_18000DC95
0x18000dc52  mov     [rbx], r12
0x18000dc55  mov     rbx, [rbx+90h]
0x18000dc5c  mov     rax, [rbx+820h]
0x18000dc63  cmp     [rbx+818h], rax
0x18000dc6a  jb      short loc_18000DC7D
0x18000dc6c  mov     edx, 1; unsigned __int64
0x18000dc71  mov     rcx, rbx; this
0x18000dc74  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dc79  test    al, al
0x18000dc7b  jz      short loc_18000DC8E
0x18000dc7d  mov     rax, [rbx+818h]
0x18000dc84  mov     byte ptr [rax], 6
0x18000dc87  inc     qword ptr [rbx+818h]
0x18000dc8e  xor     al, al
0x18000dc90  jmp     loc_18000DDE9
0x18000dc95  lea     r14, [rbx+8]
0x18000dc99  cmp     [rbx], r12
0x18000dc9c  jnz     short loc_18000DCAC
0x18000dc9e  lea     rax, asc_180025848; "-"
0x18000dca5  mov     byte ptr [r14], 1
0x18000dca9  mov     [rbx], rax
0x18000dcac  lea     rsi, [rbx+90h]
0x18000dcb3  mov     rdi, [rsi]
0x18000dcb6  mov     rax, [rdi+818h]
0x18000dcbd  sub     rax, [rdi+810h]
0x18000dcc4  mov     [rbx+10h], rax
0x18000dcc8  mov     rax, [rdi+820h]
0x18000dccf  cmp     [rdi+818h], rax
0x18000dcd6  jb      short loc_18000DCEF
0x18000dcd8  mov     edx, 1; unsigned __int64
0x18000dcdd  mov     rcx, rdi; this
0x18000dce0  mov     rbp, rsi
0x18000dce3  mov     r15, r14
0x18000dce6  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dceb  test    al, al
0x18000dced  jz      short loc_18000DD0B
0x18000dcef  mov     rax, [rdi+818h]
0x18000dcf6  lea     rbp, [rbx+90h]
0x18000dcfd  lea     r15, [rbx+8]
0x18000dd01  mov     byte ptr [rax], 5
0x18000dd04  inc     qword ptr [rdi+818h]
0x18000dd0b  mov     rdi, [rsi]
0x18000dd0e  mov     rax, [rdi+820h]
0x18000dd15  cmp     [rdi+818h], rax
0x18000dd1c  jb      short loc_18000DD2F
0x18000dd1e  mov     edx, 1; unsigned __int64
0x18000dd23  mov     rcx, rdi; this
0x18000dd26  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dd2b  test    al, al
0x18000dd2d  jz      short loc_18000DD49
0x18000dd2f  movzx   eax, byte ptr [r14]
0x18000dd33  mov     rsi, rbp
0x18000dd36  mov     rcx, [rdi+818h]
0x18000dd3d  mov     r14, r15
0x18000dd40  mov     [rcx], al
0x18000dd42  inc     qword ptr [rdi+818h]
0x18000dd49  mov     rsi, [rsi]
0x18000dd4c  movzx   edi, byte ptr [r14]
0x18000dd50  mov     r14, [rbx]
0x18000dd53  mov     rax, [rsi+820h]
0x18000dd5a  sub     rax, [rsi+818h]
0x18000dd61  cmp     rax, rdi
0x18000dd64  jnb     short loc_18000DD77
0x18000dd66  lfence
0x18000dd69  mov     edx, edi; unsigned __int64
0x18000dd6b  mov     rcx, rsi; this
0x18000dd6e  call    ?reserve@write_buffer@tson@@AEAA_N_K@Z; tson::write_buffer::reserve(unsigned __int64)
0x18000dd73  test    al, al
0x18000dd75  jz      short loc_18000DDE4
0x18000dd77  mov     rcx, [rsi+818h]; void *
0x18000dd7e  mov     rbp, [rsi+820h]
0x18000dd85  sub     rbp, rcx
0x18000dd88  test    rdi, rdi
0x18000dd8b  jz      short loc_18000DDDD
0x18000dd8d  test    rcx, rcx
0x18000dd90  jnz     short loc_18000DDA0
0x18000dd92  call    cs:__imp__errno
0x18000dd98  mov     dword ptr [rax], 16h
0x18000dd9e  jmp     short loc_18000DDD7
0x18000dda0  test    r14, r14
0x18000dda3  jz      short loc_18000DDB7
0x18000dda5  cmp     rbp, rdi
0x18000dda8  jb      short loc_18000DDB7
0x18000ddaa  mov     r8, rdi; Size
0x18000ddad  mov     rdx, r14; Src
0x18000ddb0  call    memmove
0x18000ddb5  jmp     short loc_18000DDDD
0x18000ddb7  mov     r8, rbp; Size
0x18000ddba  xor     edx, edx; Val
0x18000ddbc  call    memset
0x18000ddc1  test    r14, r14
0x18000ddc4  jz      short loc_18000DD92
0x18000ddc6  cmp     rbp, rdi
0x18000ddc9  jnb     short loc_18000DDDD
0x18000ddcb  call    cs:__imp__errno
0x18000ddd1  mov     dword ptr [rax], 22h ; '"'
0x18000ddd7  call    cs:__imp__invalid_parameter_noinfo
0x18000dddd  add     [rsi+818h], rdi
0x18000dde4  mov     [rbx], r12
0x18000dde7  mov     al, 1
0x18000dde9  mov     r14, [rsp+38h+arg_10]
0x18000ddee  mov     rsi, [rsp+38h+arg_8]
0x18000ddf3  mov     rbp, [rsp+38h+arg_0]
0x18000ddf8  mov     rbx, [rsp+38h+arg_18]
0x18000ddfd  add     rsp, 20h
0x18000de01  pop     r15
0x18000de03  pop     r12
0x18000de05  pop     rdi
0x18000de06  retn
```
