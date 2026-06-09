# updatewindow

- ea: `0x180004920`
- end: `0x180004a30`
- name: `updatewindow`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180002d40`

## callees

- `0x180004920`
- `0x18000a766`
- `0x18002e010`

## pseudocode

```c
__int64 __fastcall updatewindow(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v3; // rbx
  __int64 v5; // rbp
  char *v6; // r9
  __int64 v7; // rax
  unsigned int v9; // edi
  unsigned int v10; // eax
  __int64 v11; // rcx
  unsigned int v12; // edi
  unsigned int v13; // ebp
  unsigned int v14; // ecx
  unsigned int v15; // eax

  v3 = *(_QWORD *)(a1 + 40);
  v5 = a3;
  v6 = *(char **)(v3 + 64);
  if ( !v6 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 48))(
           *(_QWORD *)(a1 + 64),
           (unsigned int)(1 << *(_DWORD *)(v3 + 48)),
           1);
    *(_QWORD *)(v3 + 64) = v7;
    v6 = (char *)v7;
    if ( !v7 )
      return 1;
  }
  v9 = *(_DWORD *)(v3 + 52);
  if ( !v9 )
  {
    v9 = 1 << *(_DWORD *)(v3 + 48);
    *(_DWORD *)(v3 + 52) = v9;
    *(_QWORD *)(v3 + 56) = 0;
  }
  if ( (unsigned int)v5 < v9 )
  {
    v11 = *(unsigned int *)(v3 + 60);
    v12 = v9 - v11;
    if ( v12 > (unsigned int)v5 )
      v12 = v5;
    memcpy_0(&v6[v11], (const void *)(a2 - v5), v12);
    v13 = v5 - v12;
    if ( v13 )
    {
      memcpy_0(*(void **)(v3 + 64), (const void *)(a2 - v13), v13);
      v10 = *(_DWORD *)(v3 + 52);
      *(_DWORD *)(v3 + 60) = v13;
    }
    else
    {
      *(_DWORD *)(v3 + 60) += v12;
      v14 = *(_DWORD *)(v3 + 52);
      if ( *(_DWORD *)(v3 + 60) == v14 )
        *(_DWORD *)(v3 + 60) = 0;
      v15 = *(_DWORD *)(v3 + 56);
      if ( v15 >= v14 )
        return 0;
      v10 = v12 + v15;
    }
  }
  else
  {
    memcpy_0(v6, (const void *)(a2 - v9), v9);
    v10 = *(_DWORD *)(v3 + 52);
    *(_DWORD *)(v3 + 60) = 0;
  }
  *(_DWORD *)(v3 + 56) = v10;
  return 0;
}

```

## disassembly

```asm
0x180004920  mov     [rsp+arg_10], rbx
0x180004925  push    rbp
0x180004926  push    rsi
0x180004927  push    r14
0x180004929  sub     rsp, 20h
0x18000492d  mov     rbx, [rcx+28h]
0x180004931  mov     rsi, rdx
0x180004934  mov     ebp, r8d
0x180004937  mov     rax, rcx
0x18000493a  mov     r9, [rbx+40h]
0x18000493e  test    r9, r9
0x180004941  jnz     short loc_18000497F
0x180004943  mov     ecx, [rbx+30h]
0x180004946  mov     edx, 1
0x18000494b  shl     edx, cl
0x18000494d  mov     r8d, 1
0x180004953  mov     rcx, [rax+40h]
0x180004957  mov     rax, [rax+30h]
0x18000495b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004960  mov     [rbx+40h], rax
0x180004964  mov     r9, rax
0x180004967  test    rax, rax
0x18000496a  jnz     short loc_18000497F
0x18000496c  mov     eax, 1
0x180004971  mov     rbx, [rsp+38h+arg_10]
0x180004976  add     rsp, 20h
0x18000497a  pop     r14
0x18000497c  pop     rsi
0x18000497d  pop     rbp
0x18000497e  retn
0x18000497f  mov     [rsp+38h+arg_0], rdi
0x180004984  mov     edi, [rbx+34h]
0x180004987  mov     [rsp+38h+arg_8], r15
0x18000498c  xor     r15d, r15d
0x18000498f  test    edi, edi
0x180004991  jnz     short loc_1800049A4
0x180004993  mov     ecx, [rbx+30h]
0x180004996  mov     edi, 1
0x18000499b  shl     edi, cl
0x18000499d  mov     [rbx+34h], edi
0x1800049a0  mov     [rbx+38h], r15
0x1800049a4  cmp     ebp, edi
0x1800049a6  jb      short loc_1800049C2
0x1800049a8  mov     r8d, edi; Size
0x1800049ab  mov     rcx, r9; void *
0x1800049ae  sub     rsi, r8
0x1800049b1  mov     rdx, rsi; Src
0x1800049b4  call    memcpy_0
0x1800049b9  mov     eax, [rbx+34h]
0x1800049bc  mov     [rbx+3Ch], r15d
0x1800049c0  jmp     short loc_180004A13
0x1800049c2  mov     ecx, [rbx+3Ch]
0x1800049c5  mov     rdx, rsi
0x1800049c8  sub     edi, ecx
0x1800049ca  cmp     edi, ebp
0x1800049cc  cmova   edi, ebp
0x1800049cf  sub     rdx, rbp; Src
0x1800049d2  mov     r8d, edi; Size
0x1800049d5  add     rcx, r9; void *
0x1800049d8  call    memcpy_0
0x1800049dd  sub     ebp, edi
0x1800049df  jz      short loc_1800049FB
0x1800049e1  mov     rcx, [rbx+40h]; void *
0x1800049e5  mov     r8d, ebp; Size
0x1800049e8  sub     rsi, r8
0x1800049eb  mov     rdx, rsi; Src
0x1800049ee  call    memcpy_0
0x1800049f3  mov     eax, [rbx+34h]
0x1800049f6  mov     [rbx+3Ch], ebp
0x1800049f9  jmp     short loc_180004A13
0x1800049fb  add     [rbx+3Ch], edi
0x1800049fe  mov     ecx, [rbx+34h]
0x180004a01  cmp     [rbx+3Ch], ecx
0x180004a04  jnz     short loc_180004A0A
0x180004a06  mov     [rbx+3Ch], r15d
0x180004a0a  mov     eax, [rbx+38h]
0x180004a0d  cmp     eax, ecx
0x180004a0f  jnb     short loc_180004A16
0x180004a11  add     eax, edi
0x180004a13  mov     [rbx+38h], eax
0x180004a16  mov     r15, [rsp+38h+arg_8]
0x180004a1b  xor     eax, eax
0x180004a1d  mov     rdi, [rsp+38h+arg_0]
0x180004a22  mov     rbx, [rsp+38h+arg_10]
0x180004a27  add     rsp, 20h
0x180004a2b  pop     r14
0x180004a2d  pop     rsi
0x180004a2e  pop     rbp
0x180004a2f  retn
```
