# CStorageProviderInfo::SetFullProviderAndUserAndAccountIdentifier(ushort const *)

- ea: `0x180011360`
- end: `0x18001155b`
- name: `?SetFullProviderAndUserAndAccountIdentifier@CStorageProviderInfo@@UEAAJPEBG@Z`
- size: `507`
- prototype: `__int64 __fastcall(CStorageProviderInfo *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011360`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800113d9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011490`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011490`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800114e5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemRealloc` at `0x1800114e5`

## pseudocode

```c
__int64 __fastcall CStorageProviderInfo::SetFullProviderAndUserAndAccountIdentifier(
        CStorageProviderInfo *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rbx
  __int64 v4; // rax
  unsigned __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  unsigned __int64 v7; // rcx
  _WORD *v8; // rax
  int v9; // r8d
  _WORD *v10; // rdx
  unsigned __int64 v11; // rcx
  _WORD *v12; // rax
  __int64 result; // rax
  void *v14; // rcx
  unsigned __int64 v15; // rsi
  LPVOID v16; // rax
  __int64 v17; // rcx

  v2 = a2;
  if ( a2 )
  {
    v4 = -1;
    v5 = -1;
    do
      ++v5;
    while ( a2[v5] );
    v6 = v5 + 1;
    if ( v5 + 1 < v5 )
      return 2147942934LL;
    v7 = *((_QWORD *)this + 14);
    if ( v7 == -1 )
    {
      if ( *((_QWORD *)this + 13) == -1 )
      {
        v17 = *((_QWORD *)this + 12);
        if ( v17 )
        {
          do
            ++v4;
          while ( *(_WORD *)(v17 + 2 * v4) );
        }
        else
        {
          v4 = 0;
        }
        *((_QWORD *)this + 13) = v4;
      }
      else
      {
        v4 = *((_QWORD *)this + 13);
      }
      v7 = v4 + 1;
      if ( !*((_QWORD *)this + 12) )
        v7 = 0;
      *((_QWORD *)this + 14) = v7;
    }
    if ( v7 )
    {
      v9 = 0;
      if ( v6 <= v7 )
        goto LABEL_11;
      v15 = 2 * v7;
      if ( is_mul_ok(v7, 2u) )
      {
        if ( v7 > 0x800 )
          v15 = v7 + 2048;
        if ( v6 > v15 )
          v15 = v5 + 1;
        v16 = CoTaskMemRealloc(*((LPVOID *)this + 12), 2 * v15);
        if ( !v16 )
          return 2147942414LL;
        *((_QWORD *)this + 14) = v15;
        v9 = 0;
        *((_QWORD *)this + 12) = v16;
        goto LABEL_12;
      }
    }
    else if ( is_mul_ok(v6, 2u) )
    {
      v8 = CoTaskMemAlloc(2 * v6);
      if ( v8 )
      {
        *((_QWORD *)this + 14) = v6;
        v9 = 0;
        *((_QWORD *)this + 12) = v8;
        *v8 = 0;
        goto LABEL_12;
      }
      v9 = -2147024882;
LABEL_11:
      if ( v9 < 0 )
        return (unsigned int)v9;
LABEL_12:
      if ( v5 != -1 )
      {
        v10 = (_WORD *)*((_QWORD *)this + 12);
        if ( v6 > 0x7FFFFFFF || v5 > 0x7FFFFFFE )
        {
          *v10 = 0;
        }
        else
        {
          v11 = v5;
          do
          {
            if ( !v11 )
              break;
            if ( !*v2 )
              break;
            *v10++ = *v2++;
            --v11;
            --v6;
          }
          while ( v6 );
          v12 = v10 - 1;
          if ( v6 )
            v12 = v10;
          *v12 = 0;
        }
      }
      *((_QWORD *)this + 13) = v5;
      return (unsigned int)v9;
    }
    return 2147942934LL;
  }
  v14 = (void *)*((_QWORD *)this + 12);
  if ( v14 )
  {
    CoTaskMemFree(v14);
    *((_QWORD *)this + 12) = 0;
  }
  *((_QWORD *)this + 13) = 0;
  result = 0;
  *((_QWORD *)this + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x180011360  push    rbx
0x180011362  push    r14
0x180011364  push    r15
0x180011366  sub     rsp, 20h
0x18001136a  mov     rbx, rdx
0x18001136d  mov     r14, rcx
0x180011370  test    rdx, rdx
0x180011373  jz      loc_180011484
0x180011379  mov     [rsp+38h+arg_8], rbp
0x18001137e  mov     rax, 0FFFFFFFFFFFFFFFFh
0x180011385  mov     rbp, rax
0x180011388  mov     [rsp+38h+arg_18], rdi
0x18001138d  nop     dword ptr [rax]
0x180011390  inc     rbp
0x180011393  cmp     word ptr [rdx+rbp*2], 0
0x180011398  jnz     short loc_180011390
0x18001139a  lea     rdi, [rbp+1]
0x18001139e  cmp     rdi, rbp
0x1800113a1  jb      loc_180011476
0x1800113a7  mov     rcx, [rcx+70h]
0x1800113ab  xor     r15d, r15d
0x1800113ae  cmp     rcx, rax
0x1800113b1  jz      loc_180011513
0x1800113b7  mov     [rsp+38h+arg_10], rsi
0x1800113bc  test    rcx, rcx
0x1800113bf  jnz     loc_1800114AF
0x1800113c5  mov     eax, 2
0x1800113ca  mul     rdi
0x1800113cd  test    rdx, rdx
0x1800113d0  jnz     loc_18001147D
0x1800113d6  mov     rcx, rax; cb
0x1800113d9  call    cs:__imp_CoTaskMemAlloc
0x1800113df  test    rax, rax
0x1800113e2  jz      short loc_1800113F5
0x1800113e4  mov     [r14+70h], rdi
0x1800113e8  mov     r8d, r15d
0x1800113eb  mov     [r14+60h], rax
0x1800113ef  mov     [rax], r15w
0x1800113f3  jmp     short loc_180011400
0x1800113f5  mov     r8d, 8007000Eh
0x1800113fb  test    r8d, r8d
0x1800113fe  js      short loc_18001145A
0x180011400  test    rdi, rdi
0x180011403  jz      short loc_180011456
0x180011405  mov     rdx, [r14+60h]
0x180011409  cmp     rdi, 7FFFFFFFh
0x180011410  ja      loc_180011552
0x180011416  cmp     rbp, 7FFFFFFEh
0x18001141d  ja      loc_180011552
0x180011423  mov     rcx, rbp
0x180011426  test    rcx, rcx
0x180011429  jz      short loc_180011447
0x18001142b  movzx   eax, word ptr [rbx]
0x18001142e  test    ax, ax
0x180011431  jz      short loc_180011447
0x180011433  mov     [rdx], ax
0x180011436  add     rbx, 2
0x18001143a  add     rdx, 2
0x18001143e  dec     rcx
0x180011441  sub     rdi, 1
0x180011445  jnz     short loc_180011426
0x180011447  test    rdi, rdi
0x18001144a  lea     rax, [rdx-2]
0x18001144e  cmovnz  rax, rdx
0x180011452  mov     [rax], r15w
0x180011456  mov     [r14+68h], rbp
0x18001145a  mov     eax, r8d
0x18001145d  mov     rsi, [rsp+38h+arg_10]
0x180011462  mov     rbp, [rsp+38h+arg_8]
0x180011467  mov     rdi, [rsp+38h+arg_18]
0x18001146c  add     rsp, 20h
0x180011470  pop     r15
0x180011472  pop     r14
0x180011474  pop     rbx
0x180011475  retn
0x180011476  mov     eax, 80070216h
0x18001147b  jmp     short loc_180011462
0x18001147d  mov     eax, 80070216h
0x180011482  jmp     short loc_18001145D
0x180011484  mov     rcx, [rcx+60h]; pv
0x180011488  xor     r15d, r15d
0x18001148b  test    rcx, rcx
0x18001148e  jz      short loc_18001149A
0x180011490  call    cs:__imp_CoTaskMemFree
0x180011496  mov     [r14+60h], r15
0x18001149a  mov     [r14+68h], r15
0x18001149e  mov     eax, r15d
0x1800114a1  mov     [r14+70h], r15
0x1800114a5  add     rsp, 20h
0x1800114a9  pop     r15
0x1800114ab  pop     r14
0x1800114ad  pop     rbx
0x1800114ae  retn
0x1800114af  mov     r8d, r15d
0x1800114b2  cmp     rdi, rcx
0x1800114b5  jbe     loc_1800113FB
0x1800114bb  mov     eax, 2
0x1800114c0  mul     rcx
0x1800114c3  mov     rsi, rax
0x1800114c6  test    rdx, rdx
0x1800114c9  jnz     short loc_18001147D
0x1800114cb  sub     rax, rcx
0x1800114ce  cmp     rax, 800h
0x1800114d4  ja      short loc_1800114FA
0x1800114d6  mov     rcx, [r14+60h]; pv
0x1800114da  cmp     rdi, rsi
0x1800114dd  cmova   rsi, rdi
0x1800114e1  lea     rdx, [rsi+rsi]; cb
0x1800114e5  call    cs:__imp_CoTaskMemRealloc
0x1800114eb  test    rax, rax
0x1800114ee  jnz     short loc_180011503
0x1800114f0  mov     eax, 8007000Eh
0x1800114f5  jmp     loc_18001145D
0x1800114fa  lea     rsi, [rcx+800h]
0x180011501  jmp     short loc_1800114D6
0x180011503  mov     [r14+70h], rsi
0x180011507  mov     r8d, r15d
0x18001150a  mov     [r14+60h], rax
0x18001150e  jmp     loc_180011400
0x180011513  mov     rcx, [r14+68h]
0x180011517  cmp     rcx, rax
0x18001151a  jnz     short loc_18001153A
0x18001151c  mov     rcx, [r14+60h]
0x180011520  test    rcx, rcx
0x180011523  jnz     short loc_18001152A
0x180011525  mov     rax, r15
0x180011528  jmp     short loc_180011534
0x18001152a  inc     rax
0x18001152d  cmp     [rcx+rax*2], r15w
0x180011532  jnz     short loc_18001152A
0x180011534  mov     [r14+68h], rax
0x180011538  jmp     short loc_18001153D
0x18001153a  mov     rax, rcx
0x18001153d  cmp     [r14+60h], r15
0x180011541  lea     rcx, [rax+1]
0x180011545  cmovz   rcx, r15
0x180011549  mov     [r14+70h], rcx
0x18001154d  jmp     loc_1800113B7
0x180011552  mov     [rdx], r15w
0x180011556  jmp     loc_180011456
```
