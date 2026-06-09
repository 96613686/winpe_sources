# std::vector<uint,std::allocator<uint>>::_Insert_n(std::_Vector_iterator<uint,std::allocator<uint>>,unsigned __int64,uint const &)

- ea: `0x18001b924`
- end: `0x18001bc08`
- name: `?_Insert_n@?$vector@IV?$allocator@I@std@@@std@@IEAAXV?$_Vector_iterator@IV?$allocator@I@std@@@2@_KAEBI@Z`
- size: `740`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18001b5c0`

## callees

- `0x18000252c`
- `0x18000f438`
- `0x18001b924`
- `0x18002687c`
- `0x1800268f4`
- `0x180026f66`

## import_xrefs

- `msvcrt!memmove_s` at `0x18001ba81`
- `msvcrt!memmove_s` at `0x18001bab5`
- `msvcrt!memmove_s` at `0x18001bb31`
- `msvcrt!memmove_s` at `0x18001bbad`
- `msvcrt!memmove_s` at `0x18001bbd6`
- `msvcrt!memmove_s` at `0x18001ba81`
- `msvcrt!memmove_s` at `0x18001bab5`
- `msvcrt!memmove_s` at `0x18001bb31`
- `msvcrt!memmove_s` at `0x18001bbad`
- `msvcrt!memmove_s` at `0x18001bbd6`

## pseudocode

```c
char *__fastcall std::vector<unsigned int>::_Insert_n(__int64 a1, char *a2, unsigned __int64 a3, unsigned int *a4)
{
  char *result; // rax
  char *v8; // r13
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 v12; // rax
  unsigned __int64 v13; // r15
  __int64 v14; // rax
  __int64 v15; // rax
  unsigned __int64 v16; // rcx
  char *v17; // rax
  char *v18; // r12
  _BYTE *v19; // r8
  __int64 j; // rcx
  char *v21; // rdi
  char *v22; // r10
  __int64 v23; // rdx
  void *v24; // rcx
  __int64 v25; // rax
  unsigned __int64 v26; // rsi
  __int64 v27; // rdi
  __int64 v28; // r15
  __int64 v29; // rdi
  char *v30; // rdi
  unsigned __int64 v31; // rsi
  unsigned __int64 i; // rcx
  unsigned __int64 v33; // rcx
  char *v34; // rdi
  rsize_t v35; // rdx
  rsize_t v36; // r12
  __int64 v37; // rsi
  _BYTE pExceptionObject[24]; // [rsp+28h] [rbp-40h] BYREF
  _UNKNOWN *retaddr; // [rsp+68h] [rbp+0h] BYREF
  char *v40; // [rsp+70h] [rbp+8h]

  result = (char *)&retaddr;
  v8 = (char *)*a4;
  v9 = *(_QWORD *)(a1 + 8);
  if ( v9 )
    v10 = (*(_QWORD *)(a1 + 24) - v9) >> 2;
  else
    v10 = 0;
  if ( a3 )
  {
    if ( v9 )
      v11 = (*(_QWORD *)(a1 + 16) - v9) >> 2;
    else
      v11 = 0;
    if ( 0x3FFFFFFFFFFFFFFFLL - v11 < a3 )
      std::vector<_GUID>::_Xlen(v9, v10, 0x3FFFFFFFFFFFFFFFLL);
    if ( v9 )
      v12 = (*(_QWORD *)(a1 + 16) - v9) >> 2;
    else
      v12 = 0;
    if ( v10 >= a3 + v12 )
    {
      v27 = *(_QWORD *)(a1 + 16);
      v28 = 4 * a3;
      if ( (v27 - (__int64)a2) >> 2 >= a3 )
      {
        v35 = 4 * (v28 >> 2);
        v36 = v35 + v27;
        if ( v28 >> 2 )
          memmove_s(*(void *const *)(a1 + 16), v35, (const void *const)(v27 - v28), 4 * (v28 >> 2));
        *(_QWORD *)(a1 + 16) = v36;
        v37 = (v27 - v28 - (__int64)a2) >> 2;
        if ( v37 > 0 )
          memmove_s((void *const)(v27 - 4 * v37), 4 * v37, a2, 4 * v37);
        result = &a2[v28];
        while ( a2 != result )
        {
          *(_DWORD *)a2 = (_DWORD)v8;
          a2 += 4;
        }
      }
      else
      {
        v29 = (v27 - (__int64)a2) >> 2;
        if ( v29 )
          memmove_s(&a2[v28], 4 * v29, a2, 4 * v29);
        try
        {
          v30 = *(char **)(a1 + 16);
          v31 = a3 - ((v30 - a2) >> 2);
          if ( v31 )
          {
            for ( i = v31; i; --i )
            {
              *(_DWORD *)v30 = (_DWORD)v8;
              v30 += 4;
            }
          }
        }
        catch ( ... )
        {
          throw;
        }
        *(_QWORD *)(a1 + 16) += v28;
        result = (char *)(*(_QWORD *)(a1 + 16) - v28);
        v33 = (unsigned __int64)(result - a2 + 3) >> 2;
        if ( a2 > result )
          v33 = 0;
        if ( v33 )
        {
          result = v8;
          v34 = a2;
          while ( v33 )
          {
            *(_DWORD *)v34 = (_DWORD)v8;
            v34 += 4;
            --v33;
          }
        }
      }
    }
    else
    {
      v13 = 0;
      if ( 0x3FFFFFFFFFFFFFFFLL - (v10 >> 1) >= v10 )
        v13 = v10 + (v10 >> 1);
      if ( v9 )
        v14 = (*(_QWORD *)(a1 + 16) - v9) >> 2;
      else
        v14 = 0;
      if ( v13 < a3 + v14 )
      {
        if ( v9 )
          v15 = (*(_QWORD *)(a1 + 16) - v9) >> 2;
        else
          v15 = 0;
        v13 = v15 + a3;
      }
      v16 = v13;
      if ( v13 )
      {
        if ( 0xFFFFFFFFFFFFFFFFuLL / v13 < 4 )
        {
          std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
          throw (std::bad_alloc *)pExceptionObject;
        }
      }
      else
      {
        v16 = 0;
      }
      v17 = (char *)operator new(4 * v16);
      v18 = v17;
      v40 = v17;
      try
      {
        v19 = *(_BYTE **)(a1 + 8);
        j = (a2 - v19) >> 2;
        v21 = &v17[4 * j];
        if ( j )
          memmove_s(v17, 4 * j, v19, 4 * ((a2 - v19) >> 2));
        v22 = &v21[4 * a3];
        if ( a3 )
        {
          for ( j = a3; j; --j )
          {
            *(_DWORD *)v21 = (_DWORD)v8;
            v21 += 4;
          }
        }
        v23 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 2;
        if ( v23 )
          memmove_s(v22, 4 * v23, a2, 4 * v23);
      }
      catch ( ... )
      {
        std::allocator<unsigned int>::deallocate(j, v40);
        throw;
      }
      v24 = *(void **)(a1 + 8);
      if ( v24 )
        v25 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)v24) >> 2;
      else
        v25 = 0;
      v26 = v25 + a3;
      if ( v24 )
        operator delete(v24);
      *(_QWORD *)(a1 + 24) = &v18[4 * v13];
      result = &v18[4 * v26];
      *(_QWORD *)(a1 + 16) = result;
      *(_QWORD *)(a1 + 8) = v18;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001b924  mov     rax, rsp
0x18001b927  push    rdi
0x18001b928  push    r12
0x18001b92a  push    r13
0x18001b92c  push    r14
0x18001b92e  push    r15
0x18001b930  sub     rsp, 40h
0x18001b934  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18001b93c  mov     [rax+10h], rbx
0x18001b940  mov     [rax+18h], rsi
0x18001b944  mov     rsi, r8
0x18001b947  mov     rbx, rdx
0x18001b94a  mov     r14, rcx
0x18001b94d  mov     r13d, [r9]
0x18001b950  mov     rcx, [rcx+8]
0x18001b954  xor     r9d, r9d
0x18001b957  test    rcx, rcx
0x18001b95a  jnz     short loc_18001B961
0x18001b95c  mov     edx, r9d
0x18001b95f  jmp     short loc_18001B96C
0x18001b961  mov     rdx, [r14+18h]
0x18001b965  sub     rdx, rcx
0x18001b968  sar     rdx, 2
0x18001b96c  test    rsi, rsi
0x18001b96f  jz      loc_18001BBEE
0x18001b975  test    rcx, rcx
0x18001b978  jnz     short loc_18001B97F
0x18001b97a  mov     rdi, r9
0x18001b97d  jmp     short loc_18001B98A
0x18001b97f  mov     rdi, [r14+10h]
0x18001b983  sub     rdi, rcx
0x18001b986  sar     rdi, 2
0x18001b98a  mov     r8, 3FFFFFFFFFFFFFFFh
0x18001b994  mov     rax, r8
0x18001b997  sub     rax, rdi
0x18001b99a  cmp     rax, rsi
0x18001b99d  jnb     short loc_18001B9A5
0x18001b99f  call    ?_Xlen@?$vector@U_GUID@@V?$allocator@U_GUID@@@std@@@std@@KAXXZ; std::vector<_GUID>::_Xlen(void)
0x18001b9a5  test    rcx, rcx
0x18001b9a8  jnz     short loc_18001B9AF
0x18001b9aa  mov     rax, r9
0x18001b9ad  jmp     short loc_18001B9BA
0x18001b9af  mov     rax, [r14+10h]
0x18001b9b3  sub     rax, rcx
0x18001b9b6  sar     rax, 2
0x18001b9ba  add     rax, rsi
0x18001b9bd  cmp     rdx, rax
0x18001b9c0  jnb     loc_18001BAFA
0x18001b9c6  mov     rax, rdx
0x18001b9c9  shr     rax, 1
0x18001b9cc  sub     r8, rax
0x18001b9cf  add     rax, rdx
0x18001b9d2  mov     r15, r9
0x18001b9d5  cmp     r8, rdx
0x18001b9d8  cmovnb  r15, rax
0x18001b9dc  test    rcx, rcx
0x18001b9df  jnz     short loc_18001B9E6
0x18001b9e1  mov     rax, r9
0x18001b9e4  jmp     short loc_18001B9F1
0x18001b9e6  mov     rax, [r14+10h]
0x18001b9ea  sub     rax, rcx
0x18001b9ed  sar     rax, 2
0x18001b9f1  add     rax, rsi
0x18001b9f4  cmp     r15, rax
0x18001b9f7  jnb     short loc_18001BA12
0x18001b9f9  test    rcx, rcx
0x18001b9fc  jnz     short loc_18001BA03
0x18001b9fe  mov     rax, r9
0x18001ba01  jmp     short loc_18001BA0E
0x18001ba03  mov     rax, [r14+10h]
0x18001ba07  sub     rax, rcx
0x18001ba0a  sar     rax, 2
0x18001ba0e  lea     r15, [rax+rsi]
0x18001ba12  mov     rcx, r15
0x18001ba15  test    r15, r15
0x18001ba18  jnz     short loc_18001BA1F
0x18001ba1a  mov     rcx, r9
0x18001ba1d  jmp     short loc_18001BA4C
0x18001ba1f  xor     edx, edx
0x18001ba21  or      rax, 0FFFFFFFFFFFFFFFFh
0x18001ba25  div     r15
0x18001ba28  cmp     rax, 4
0x18001ba2c  jnb     short loc_18001BA4C
0x18001ba2e  xor     edx, edx; char *
0x18001ba30  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18001ba35  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18001ba3a  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18001ba41  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18001ba46  call    _CxxThrowException_0
0x18001ba4c  shl     rcx, 2; Size
0x18001ba50  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001ba55  mov     r12, rax
0x18001ba58  mov     [rsp+68h+arg_0], rax
0x18001ba5d  mov     r8, [r14+8]; Source
0x18001ba61  mov     rcx, rbx
0x18001ba64  sub     rcx, r8
0x18001ba67  sar     rcx, 2
0x18001ba6b  mov     rdx, rcx
0x18001ba6e  shl     rdx, 2; DestinationSize
0x18001ba72  lea     rdi, [rdx+rax]
0x18001ba76  test    rcx, rcx
0x18001ba79  jz      short loc_18001BA87
0x18001ba7b  mov     r9, rdx; SourceSize
0x18001ba7e  mov     rcx, rax; Destination
0x18001ba81  call    cs:__imp_memmove_s
0x18001ba87  lea     r10, [rdi+rsi*4]
0x18001ba8b  test    rsi, rsi
0x18001ba8e  jz      short loc_18001BA98
0x18001ba90  mov     rax, r13
0x18001ba93  mov     rcx, rsi
0x18001ba96  rep stosd
0x18001ba98  mov     rdx, [r14+10h]
0x18001ba9c  sub     rdx, rbx
0x18001ba9f  sar     rdx, 2
0x18001baa3  test    rdx, rdx
0x18001baa6  jz      short loc_18001BABC
0x18001baa8  shl     rdx, 2; DestinationSize
0x18001baac  mov     r9, rdx; SourceSize
0x18001baaf  mov     r8, rbx; Source
0x18001bab2  mov     rcx, r10; Destination
0x18001bab5  call    cs:__imp_memmove_s
0x18001babb  nop
0x18001babc  mov     rcx, [r14+8]; Block
0x18001bac0  test    rcx, rcx
0x18001bac3  jnz     short loc_18001BAC9
0x18001bac5  xor     eax, eax
0x18001bac7  jmp     short loc_18001BAD4
0x18001bac9  mov     rax, [r14+10h]
0x18001bacd  sub     rax, rcx
0x18001bad0  sar     rax, 2
0x18001bad4  add     rsi, rax
0x18001bad7  test    rcx, rcx
0x18001bada  jz      short loc_18001BAE1
0x18001badc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001bae1  lea     rax, [r12+r15*4]
0x18001bae5  mov     [r14+18h], rax
0x18001bae9  lea     rax, [r12+rsi*4]
0x18001baed  mov     [r14+10h], rax
0x18001baf1  mov     [r14+8], r12
0x18001baf5  jmp     loc_18001BBEE
0x18001bafa  mov     rdi, [r14+10h]
0x18001bafe  mov     rax, rdi
0x18001bb01  sub     rax, rbx
0x18001bb04  sar     rax, 2
0x18001bb08  mov     r15, rsi
0x18001bb0b  shl     r15, 2
0x18001bb0f  cmp     rax, rsi
0x18001bb12  jnb     short loc_18001BB84
0x18001bb14  lea     rcx, [r15+rbx]; Destination
0x18001bb18  sub     rdi, rbx
0x18001bb1b  sar     rdi, 2
0x18001bb1f  test    rdi, rdi
0x18001bb22  jz      short loc_18001BB3A
0x18001bb24  mov     rdx, rdi
0x18001bb27  shl     rdx, 2; DestinationSize
0x18001bb2b  mov     r9, rdx; SourceSize
0x18001bb2e  mov     r8, rbx; Source
0x18001bb31  call    cs:__imp_memmove_s
0x18001bb37  xor     r9d, r9d
0x18001bb3a  mov     rdi, [r14+10h]
0x18001bb3e  mov     rax, rdi
0x18001bb41  sub     rax, rbx
0x18001bb44  sar     rax, 2
0x18001bb48  sub     rsi, rax
0x18001bb4b  jz      short loc_18001BB55
0x18001bb4d  mov     rax, r13
0x18001bb50  mov     rcx, rsi
0x18001bb53  rep stosd
0x18001bb55  add     [r14+10h], r15
0x18001bb59  mov     rax, [r14+10h]
0x18001bb5d  sub     rax, r15
0x18001bb60  mov     rcx, rax
0x18001bb63  sub     rcx, rbx
0x18001bb66  add     rcx, 3
0x18001bb6a  shr     rcx, 2
0x18001bb6e  cmp     rbx, rax
0x18001bb71  cmova   rcx, r9
0x18001bb75  test    rcx, rcx
0x18001bb78  jz      short loc_18001BBEE
0x18001bb7a  mov     rax, r13
0x18001bb7d  mov     rdi, rbx
0x18001bb80  rep stosd
0x18001bb82  jmp     short loc_18001BBEE
0x18001bb84  mov     rsi, rdi
0x18001bb87  sub     rsi, r15
0x18001bb8a  mov     rax, rdi
0x18001bb8d  sub     rax, rsi
0x18001bb90  sar     rax, 2
0x18001bb94  mov     rdx, rax
0x18001bb97  shl     rdx, 2; DestinationSize
0x18001bb9b  lea     r12, [rdx+rdi]
0x18001bb9f  test    rax, rax
0x18001bba2  jz      short loc_18001BBB3
0x18001bba4  mov     r9, rdx; SourceSize
0x18001bba7  mov     r8, rsi; Source
0x18001bbaa  mov     rcx, rdi; Destination
0x18001bbad  call    cs:__imp_memmove_s
0x18001bbb3  mov     [r14+10h], r12
0x18001bbb7  sub     rsi, rbx
0x18001bbba  sar     rsi, 2
0x18001bbbe  test    rsi, rsi
0x18001bbc1  jle     short loc_18001BBDC
0x18001bbc3  mov     rdx, rsi
0x18001bbc6  shl     rdx, 2; DestinationSize
0x18001bbca  sub     rdi, rdx
0x18001bbcd  mov     r9, rdx; SourceSize
0x18001bbd0  mov     r8, rbx; Source
0x18001bbd3  mov     rcx, rdi; Destination
0x18001bbd6  call    cs:__imp_memmove_s
0x18001bbdc  lea     rax, [r15+rbx]
0x18001bbe0  jmp     short loc_18001BBE9
0x18001bbe2  mov     [rbx], r13d
0x18001bbe5  add     rbx, 4
0x18001bbe9  cmp     rbx, rax
0x18001bbec  jnz     short loc_18001BBE2
0x18001bbee  lea     r11, [rsp+68h+var_28]
0x18001bbf3  mov     rbx, [r11+38h]
0x18001bbf7  mov     rsi, [r11+40h]
0x18001bbfb  mov     rsp, r11
0x18001bbfe  pop     r15
0x18001bc00  pop     r14
0x18001bc02  pop     r13
0x18001bc04  pop     r12
0x18001bc06  pop     rdi
0x18001bc07  retn
```
