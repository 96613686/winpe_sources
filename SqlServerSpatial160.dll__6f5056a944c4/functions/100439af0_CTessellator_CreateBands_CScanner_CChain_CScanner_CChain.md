# CTessellator::CreateBands(CScanner::CChain *,CScanner::CChain *)

- ea: `0x100439af0`
- end: `0x100439c3c`
- name: `?CreateBands@CTessellator@@QEAAJPEAVCChain@CScanner@@0@Z`
- size: `332`
- prototype: `__int64 __fastcall(CTessellator *__hidden this, struct CScanner::CChain *, struct CScanner::CChain *)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x100439750`
- `0x100439c50`

## callees

- `0x100439af0`
- `0x10043a330`

## pseudocode

```c
__int64 __fastcall CTessellator::CreateBands(
        CTessellator *this,
        struct CScanner::CChain *a2,
        struct CScanner::CChain *a3)
{
  struct CScanner::CChain *i; // rbx
  __int64 v6; // rdi
  unsigned int v7; // ecx
  __int64 v9; // rsi
  int v10; // eax
  _QWORD *v11; // rcx
  __int64 v12; // rcx
  _QWORD *v13; // [rsp+58h] [rbp+10h] BYREF

  i = a2;
  if ( a2 != a3 )
  {
    while ( (((unsigned __int8)~HIBYTE(*((unsigned __int16 *)i + 36))
            ^ (unsigned __int8)~(*((unsigned __int16 *)i + 36) >> 12))
           & 1) == 0 )
    {
      v6 = *((_QWORD *)i + 3);
      if ( !v6 )
        break;
      while ( 1 )
      {
        v7 = *(unsigned __int16 *)(v6 + 72);
        if ( (v7 & 0x2600) == 0 )
          break;
        v6 = *(_QWORD *)(v6 + 24);
        if ( !v6 )
          return 2148734217LL;
      }
      if ( (((unsigned __int8)~(v7 >> 8) ^ (unsigned __int8)~(v7 >> 12)) & 1) == 0 )
        break;
      v9 = *(_QWORD *)i;
      v13 = 0;
      v10 = SQL_Memblock<CTessellator::CVertexRef>::Allocate((char *)this + 536, &v13);
      v11 = v13;
      if ( v10 >= 0 )
      {
        *v13 = v9;
        v11[2] = 0;
        v11[1] = 0;
      }
      if ( !v11 )
        return 2147942414LL;
      *((_QWORD *)i + 7) = v11;
      *(_QWORD *)(v6 + 56) = v11;
      if ( (struct CScanner::CChain *)v6 == a3 )
        return 0;
      for ( i = *(struct CScanner::CChain **)(v6 + 24); i; i = (struct CScanner::CChain *)*((_QWORD *)i + 3) )
      {
        if ( (*((_WORD *)i + 36) & 0x2600) == 0 )
          break;
      }
      if ( i == a3 )
        goto LABEL_16;
    }
    return 2148734217LL;
  }
LABEL_16:
  v12 = *((_QWORD *)this + 39);
  if ( !v12 )
    return 2148734217LL;
  while ( (*(_WORD *)(v12 + 72) & 0x2600) != 0 )
  {
    v12 = *(_QWORD *)(v12 + 32);
    if ( !v12 )
      return 2148734217LL;
  }
  *((_QWORD *)i + 7) = *(_QWORD *)(v12 + 56);
  *(_QWORD *)(v12 + 56) = 0;
  return 0;
}

```

## disassembly

```asm
0x100439af0  mov     [rsp+arg_0], rbx
0x100439af5  mov     [rsp+arg_10], rbp
0x100439afa  push    rsi
0x100439afb  push    rdi
0x100439afc  push    r12
0x100439afe  push    r14
0x100439b00  push    r15
0x100439b02  sub     rsp, 20h
0x100439b06  xor     r15d, r15d
0x100439b09  mov     rbp, r8
0x100439b0c  mov     rbx, rdx
0x100439b0f  mov     r14, rcx
0x100439b12  mov     r12d, 2600h
0x100439b18  cmp     rdx, r8
0x100439b1b  jz      loc_100439BF2
0x100439b21  movzx   eax, word ptr [rbx+48h]
0x100439b25  mov     edx, eax
0x100439b27  shr     eax, 8
0x100439b2a  shr     edx, 0Ch
0x100439b2d  not     eax
0x100439b2f  not     edx
0x100439b31  xor     edx, eax
0x100439b33  test    dl, 1
0x100439b36  jnz     short loc_100439B5B
0x100439b38  mov     rdi, [rbx+18h]
0x100439b3c  test    rdi, rdi
0x100439b3f  jz      short loc_100439B5B
0x100439b41  movzx   ecx, word ptr [rdi+48h]
0x100439b45  movzx   eax, cx
0x100439b48  and     ax, r12w
0x100439b4c  cmp     r15w, ax
0x100439b50  jz      short loc_100439B77
0x100439b52  mov     rdi, [rdi+18h]
0x100439b56  test    rdi, rdi
0x100439b59  jnz     short loc_100439B41
0x100439b5b  mov     eax, 80131509h
0x100439b60  mov     rbx, [rsp+48h+arg_0]
0x100439b65  mov     rbp, [rsp+48h+arg_10]
0x100439b6a  add     rsp, 20h
0x100439b6e  pop     r15
0x100439b70  pop     r14
0x100439b72  pop     r12
0x100439b74  pop     rdi
0x100439b75  pop     rsi
0x100439b76  retn
0x100439b77  mov     eax, ecx
0x100439b79  shr     ecx, 0Ch
0x100439b7c  shr     eax, 8
0x100439b7f  not     ecx
0x100439b81  not     eax
0x100439b83  xor     ecx, eax
0x100439b85  test    cl, 1
0x100439b88  jz      short loc_100439B5B
0x100439b8a  mov     rsi, [rbx]
0x100439b8d  lea     rcx, [r14+218h]
0x100439b94  lea     rdx, [rsp+48h+arg_8]
0x100439b99  mov     [rsp+48h+arg_8], r15
0x100439b9e  call    ?Allocate@?$SQL_Memblock@VCVertexRef@CTessellator@@@@QEAAJPEAPEAVCVertexRef@CTessellator@@@Z; SQL_Memblock<CTessellator::CVertexRef>::Allocate(CTessellator::CVertexRef * *)
0x100439ba3  mov     rcx, [rsp+48h+arg_8]
0x100439ba8  test    eax, eax
0x100439baa  js      short loc_100439BB7
0x100439bac  mov     [rcx], rsi
0x100439baf  mov     [rcx+10h], r15
0x100439bb3  mov     [rcx+8], r15
0x100439bb7  test    rcx, rcx
0x100439bba  jz      short loc_100439C1E
0x100439bbc  mov     [rbx+38h], rcx
0x100439bc0  mov     [rdi+38h], rcx
0x100439bc4  cmp     rdi, rbp
0x100439bc7  jz      short loc_100439C34
0x100439bc9  mov     rbx, [rdi+18h]
0x100439bcd  test    rbx, rbx
0x100439bd0  jz      short loc_100439BE9
0x100439bd2  movzx   eax, word ptr [rbx+48h]
0x100439bd6  and     ax, r12w
0x100439bda  cmp     r15w, ax
0x100439bde  jz      short loc_100439BE9
0x100439be0  mov     rbx, [rbx+18h]
0x100439be4  test    rbx, rbx
0x100439be7  jnz     short loc_100439BD2
0x100439be9  cmp     rbx, rbp
0x100439bec  jnz     loc_100439B21
0x100439bf2  mov     rcx, [r14+138h]
0x100439bf9  test    rcx, rcx
0x100439bfc  jz      loc_100439B5B
0x100439c02  movzx   eax, word ptr [rcx+48h]
0x100439c06  and     ax, r12w
0x100439c0a  cmp     r15w, ax
0x100439c0e  jz      short loc_100439C28
0x100439c10  mov     rcx, [rcx+20h]
0x100439c14  test    rcx, rcx
0x100439c17  jnz     short loc_100439C02
0x100439c19  jmp     loc_100439B5B
0x100439c1e  mov     eax, 8007000Eh
0x100439c23  jmp     loc_100439B60
0x100439c28  mov     rax, [rcx+38h]
0x100439c2c  mov     [rbx+38h], rax
0x100439c30  mov     [rcx+38h], r15
0x100439c34  mov     eax, r15d
0x100439c37  jmp     loc_100439B60
```
