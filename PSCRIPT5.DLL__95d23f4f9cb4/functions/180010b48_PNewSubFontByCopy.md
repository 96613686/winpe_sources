# PNewSubFontByCopy

- ea: `0x180010b48`
- end: `0x180010c87`
- name: `PNewSubFontByCopy`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ee40`
- `0x18000f51c`

## callees

- `0x18000fe90`
- `0x180010984`
- `0x180010b48`
- `0x18001c7f0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180010c33`
- `KERNEL32!LocalFree` at `0x180010c33`
- `KERNEL32!LocalAlloc` at `0x180010bc9`
- `KERNEL32!LocalAlloc` at `0x180010bc9`

## pseudocode

```c
__int64 __fastcall PNewSubFontByCopy(__int64 a1, __int64 a2, __int16 a3, unsigned __int16 a4, __int64 a5)
{
  __int64 *v5; // rsi
  __int64 i; // rdi
  _WORD *j; // rbx
  _WORD *v11; // rax
  int v12; // r14d

  v5 = (__int64 *)(a2 + 200);
  if ( a3 )
  {
    for ( i = *v5; i && *(_WORD *)(i + 8) != a3; i = *(_QWORD *)i )
      ;
  }
  else
  {
    i = a2 + 200;
  }
  if ( i && *(_BYTE *)(i + 10) )
  {
    if ( a4 )
    {
      for ( j = (_WORD *)*v5; j && j[4] != a4; j = *(_WORD **)j )
        ;
    }
    else
    {
      j = (_WORD *)(a2 + 200);
    }
    if ( j )
    {
      v12 = 0;
    }
    else
    {
      v11 = LocalAlloc(0x40u, 0xA8u);
      j = v11;
      if ( !v11 )
        return PNewSubFont(a1, a2, a4, a5);
      v11[4] = a4;
      v12 = 1;
    }
    if ( *((_BYTE *)j + 10) )
      return (__int64)j;
    *((_QWORD *)j + 19) = a2;
    CreateSubFontPSName(a1, a2, j);
    if ( BCopyFont(a1, i, (__int64)j, *(_DWORD *)(a2 + 196)) )
    {
      if ( v12 )
      {
        *(_QWORD *)j = *v5;
        *v5 = (__int64)j;
      }
      return (__int64)j;
    }
    if ( !a4 )
      *((_BYTE *)j + 10) = 0;
    if ( v12 )
      LocalFree(j);
    return PNewSubFont(a1, a2, a4, a5);
  }
  return PNewSubFont(a1, a2, a4, a5);
}

```

## disassembly

```asm
0x180010b48  push    rbx
0x180010b4a  push    rbp
0x180010b4b  push    rsi
0x180010b4c  push    rdi
0x180010b4d  push    r12
0x180010b4f  push    r13
0x180010b51  push    r14
0x180010b53  push    r15
0x180010b55  sub     rsp, 28h
0x180010b59  xor     r13d, r13d
0x180010b5c  lea     rsi, [rdx+0C8h]
0x180010b63  movzx   ebp, r9w
0x180010b67  mov     r15, rdx
0x180010b6a  mov     r12, rcx
0x180010b6d  test    r8w, r8w
0x180010b71  jnz     short loc_180010B78
0x180010b73  mov     rdi, rsi
0x180010b76  jmp     short loc_180010B8C
0x180010b78  mov     rdi, [rsi]
0x180010b7b  jmp     short loc_180010B87
0x180010b7d  cmp     [rdi+8], r8w
0x180010b82  jz      short loc_180010B8C
0x180010b84  mov     rdi, [rdi]
0x180010b87  test    rdi, rdi
0x180010b8a  jnz     short loc_180010B7D
0x180010b8c  test    rdi, rdi
0x180010b8f  jz      loc_180010C65
0x180010b95  cmp     [rdi+0Ah], r13b
0x180010b99  jz      loc_180010C65
0x180010b9f  test    bp, bp
0x180010ba2  jnz     short loc_180010BA9
0x180010ba4  mov     rbx, rsi
0x180010ba7  jmp     short loc_180010BBC
0x180010ba9  mov     rbx, [rsi]
0x180010bac  jmp     short loc_180010BB7
0x180010bae  cmp     [rbx+8], bp
0x180010bb2  jz      short loc_180010BBC
0x180010bb4  mov     rbx, [rbx]
0x180010bb7  test    rbx, rbx
0x180010bba  jnz     short loc_180010BAE
0x180010bbc  test    rbx, rbx
0x180010bbf  jnz     short loc_180010BE3
0x180010bc1  mov     edx, 0A8h; uBytes
0x180010bc6  lea     ecx, [rbx+40h]; uFlags
0x180010bc9  call    cs:__imp_LocalAlloc
0x180010bcf  mov     rbx, rax
0x180010bd2  test    rax, rax
0x180010bd5  jz      short loc_180010C39
0x180010bd7  mov     [rax+8], bp
0x180010bdb  mov     r14d, 1
0x180010be1  jmp     short loc_180010BE6
0x180010be3  mov     r14d, r13d
0x180010be6  cmp     [rbx+0Ah], r13b
0x180010bea  jz      short loc_180010BF4
0x180010bec  mov     rax, rbx
0x180010bef  jmp     loc_180010C76
0x180010bf4  mov     r8, rbx
0x180010bf7  mov     [rbx+98h], r15
0x180010bfe  mov     rdx, r15
0x180010c01  mov     rcx, r12
0x180010c04  call    CreateSubFontPSName
0x180010c09  mov     r9d, [r15+0C4h]
0x180010c10  mov     r8, rbx
0x180010c13  mov     rdx, rdi
0x180010c16  mov     rcx, r12
0x180010c19  call    BCopyFont
0x180010c1e  test    eax, eax
0x180010c20  jnz     short loc_180010C55
0x180010c22  test    bp, bp
0x180010c25  jnz     short loc_180010C2B
0x180010c27  mov     [rbx+0Ah], r13b
0x180010c2b  test    r14d, r14d
0x180010c2e  jz      short loc_180010C39
0x180010c30  mov     rcx, rbx; hMem
0x180010c33  call    cs:__imp_LocalFree
0x180010c39  mov     r9, [rsp+68h+arg_20]
0x180010c41  movzx   r8d, bp
0x180010c45  mov     rdx, r15
0x180010c48  mov     rcx, r12
0x180010c4b  call    PNewSubFont
0x180010c50  mov     rbx, rax
0x180010c53  jmp     short loc_180010BEC
0x180010c55  test    r14d, r14d
0x180010c58  jz      short loc_180010BEC
0x180010c5a  mov     rax, [rsi]
0x180010c5d  mov     [rbx], rax
0x180010c60  mov     [rsi], rbx
0x180010c63  jmp     short loc_180010BEC
0x180010c65  mov     r9, [rsp+68h+arg_20]
0x180010c6d  movzx   r8d, bp
0x180010c71  call    PNewSubFont
0x180010c76  add     rsp, 28h
0x180010c7a  pop     r15
0x180010c7c  pop     r14
0x180010c7e  pop     r13
0x180010c80  pop     r12
0x180010c82  pop     rdi
0x180010c83  pop     rsi
0x180010c84  pop     rbp
0x180010c85  pop     rbx
0x180010c86  retn
```
