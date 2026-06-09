# walTryBeginRead

- ea: `0x180007a7c`
- end: `0x180007ce5`
- name: `walTryBeginRead`
- size: `617`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x180007a20`
- `0x180049540`

## callees

- `0x180007a7c`
- `0x180007d74`
- `0x180049668`
- `0x1800496d0`
- `0x180049a40`
- `0x18004a1c8`
- `0x180059ad4`
- `0x180061cdc`
- `0x180095158`
- `0x180099808`
- `0x18009a010`

## pseudocode

```c
__int64 __fastcall walTryBeginRead(_QWORD *a1, _DWORD *a2, int a3, int *a4)
{
  int v5; // eax
  __int64 result; // rax
  __int64 v9; // rdx
  unsigned int v10; // edi
  __int64 v11; // rdx
  __int64 v12; // r13
  __int64 v13; // rcx
  unsigned int v14; // r12d
  unsigned int v15; // r15d
  int v16; // esi
  int i; // ebp
  unsigned int v18; // r14d
  int j; // ebp
  unsigned int v20; // eax
  unsigned int v21; // ecx
  __int64 v22; // rcx

  v5 = ++*a4;
  if ( *a4 > 5 )
  {
    if ( v5 > 100 )
      return 15;
    v9 = 1;
    if ( v5 >= 10 )
      v9 = (unsigned int)(39 * (v5 - 9) * (v5 - 9));
    (*(void (__fastcall **)(_QWORD, __int64))(*a1 + 112LL))(*a1, v9);
  }
  v10 = 0;
  if ( a3 )
    goto LABEL_18;
  if ( *((_BYTE *)a1 + 70) )
    return walBeginShmUnreliable(a1, a2);
  result = walIndexReadHdr((__int64)a1, a2);
  v10 = result;
  if ( (_DWORD)result != 5 )
  {
    if ( (_DWORD)result )
      return result;
    if ( *((_BYTE *)a1 + 70) )
      return walBeginShmUnreliable(a1, a2);
LABEL_18:
    ((void (*)(void))sehInjectFault)();
    v12 = *(_QWORD *)a1[6];
    ((void (*)(void))sehInjectFault)();
    if ( !a3 && *(_DWORD *)(v12 + 96) == *((_DWORD *)a1 + 22) )
    {
      v10 = walLockShared(a1, 3);
      walShmBarrier(a1);
      if ( !v10 )
      {
        sehInjectFault(v13);
        if ( memcmp_0(*(const void **)a1[6], a1 + 9, 0x30u) )
        {
          v11 = 3;
          goto LABEL_53;
        }
        *((_WORD *)a1 + 30) = 0;
        return 0;
      }
      if ( v10 != 5 )
        return v10;
    }
    v14 = *((_DWORD *)a1 + 22);
    v15 = 0;
    v16 = 0;
    for ( i = 1; i < 5; ++i )
    {
      v18 = *(_DWORD *)(v12 + 4LL * (unsigned int)i + 100);
      ((void (*)(void))sehInjectFault)();
      if ( v15 <= v18 && v18 <= v14 )
      {
        v15 = v18;
        v16 = i;
      }
    }
    if ( (*((_BYTE *)a1 + 66) & 2) == 0 )
    {
      if ( v15 >= v14 && v16 )
      {
LABEL_45:
        v20 = walLockShared(a1, (unsigned int)(v16 + 3));
        v21 = v20;
        if ( v20 )
        {
          if ( (_BYTE)v20 == 5 )
            return (unsigned int)-1;
          return v21;
        }
        *((_DWORD *)a1 + 30) = *(_DWORD *)(v12 + 96) + 1;
        sehInjectFault(0);
        walShmBarrier(a1);
        v22 = *(unsigned int *)(v12 + 4LL * v16 + 100);
        if ( (_DWORD)v22 != v15 || (sehInjectFault(v22), memcmp_0(*(const void **)a1[6], a1 + 9, 0x30u)) )
        {
          v11 = (unsigned int)(v16 + 3);
          goto LABEL_53;
        }
        *((_WORD *)a1 + 30) = v16;
        return 0;
      }
      for ( j = 1; j < 5; ++j )
      {
        result = walLockExclusive(a1, (unsigned int)(j + 3), 1);
        v10 = result;
        if ( !(_DWORD)result )
        {
          v15 = v14;
          v16 = j;
          *(_DWORD *)(v12 + 4LL * j + 100) = v14;
          walUnlockExclusive(a1, (unsigned int)(j + 3), 1);
          break;
        }
        if ( (_DWORD)result != 5 )
          return result;
      }
    }
    if ( !v16 )
    {
      result = 0xFFFFFFFFLL;
      if ( v10 != 5 )
        return 1288;
      return result;
    }
    goto LABEL_45;
  }
  if ( !*(_QWORD *)a1[6] )
    return 0xFFFFFFFFLL;
  result = walLockShared(a1, 2);
  if ( !(_DWORD)result )
  {
    v11 = 2;
LABEL_53:
    walUnlockShared(a1, v11);
    return 0xFFFFFFFFLL;
  }
  if ( (_DWORD)result == 5 )
    return 261;
  return result;
}

```

## disassembly

```asm
0x180007a7c  push    rbx
0x180007a7e  push    rbp
0x180007a7f  push    rsi
0x180007a80  push    rdi
0x180007a81  push    r12
0x180007a83  push    r13
0x180007a85  push    r14
0x180007a87  push    r15
0x180007a89  sub     rsp, 28h
0x180007a8d  inc     dword ptr [r9]
0x180007a90  mov     ebp, r8d
0x180007a93  mov     eax, [r9]
0x180007a96  mov     rsi, rdx
0x180007a99  mov     rbx, rcx
0x180007a9c  cmp     eax, 5
0x180007a9f  jle     short loc_180007ACF
0x180007aa1  cmp     eax, 64h ; 'd'
0x180007aa4  jle     short loc_180007AB0
0x180007aa6  mov     eax, 0Fh
0x180007aab  jmp     loc_180007CD4
0x180007ab0  mov     edx, 1
0x180007ab5  cmp     eax, 0Ah
0x180007ab8  jl      short loc_180007AC3
0x180007aba  add     eax, 0FFFFFFF7h
0x180007abd  imul    eax, eax
0x180007ac0  imul    edx, eax, 27h ; '''
0x180007ac3  mov     rcx, [rcx]
0x180007ac6  mov     rax, [rcx+70h]
0x180007aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007acf  xor     r14d, r14d
0x180007ad2  mov     edi, r14d
0x180007ad5  test    ebp, ebp
0x180007ad7  jnz     short loc_180007B46
0x180007ad9  cmp     [rbx+46h], r14b
0x180007add  jnz     short loc_180007B36
0x180007adf  mov     rdx, rsi
0x180007ae2  mov     rcx, rbx
0x180007ae5  call    walIndexReadHdr
0x180007aea  mov     edi, eax
0x180007aec  cmp     eax, 5
0x180007aef  jnz     short loc_180007B28
0x180007af1  mov     rax, [rbx+30h]
0x180007af5  cmp     [rax], r14
0x180007af8  jz      loc_180007CD1
0x180007afe  lea     edx, [rbp+2]
0x180007b01  mov     rcx, rbx
0x180007b04  call    walLockShared
0x180007b09  test    eax, eax
0x180007b0b  jnz     short loc_180007B15
0x180007b0d  lea     edx, [rbp+2]
0x180007b10  jmp     loc_180007CC9
0x180007b15  cmp     eax, 5
0x180007b18  jnz     loc_180007CD4
0x180007b1e  mov     eax, 105h
0x180007b23  jmp     loc_180007CD4
0x180007b28  test    eax, eax
0x180007b2a  jnz     loc_180007CD4
0x180007b30  cmp     [rbx+46h], r14b
0x180007b34  jz      short loc_180007B46
0x180007b36  mov     rdx, rsi
0x180007b39  mov     rcx, rbx
0x180007b3c  call    walBeginShmUnreliable
0x180007b41  jmp     loc_180007CD4
0x180007b46  call    sehInjectFault
0x180007b4b  mov     rax, [rbx+30h]
0x180007b4f  mov     r13, [rax]
0x180007b52  call    sehInjectFault
0x180007b57  test    ebp, ebp
0x180007b59  jnz     short loc_180007BBD
0x180007b5b  mov     ecx, [rbx+58h]
0x180007b5e  mov     eax, [r13+60h]
0x180007b62  cmp     eax, ecx
0x180007b64  jnz     short loc_180007BBD
0x180007b66  lea     esi, [rbp+3]
0x180007b69  mov     rcx, rbx
0x180007b6c  mov     edx, esi
0x180007b6e  call    walLockShared
0x180007b73  mov     rcx, rbx
0x180007b76  mov     edi, eax
0x180007b78  call    walShmBarrier
0x180007b7d  test    edi, edi
0x180007b7f  jnz     short loc_180007BB1
0x180007b81  call    sehInjectFault
0x180007b86  mov     rcx, [rbx+30h]
0x180007b8a  lea     rdx, [rbx+48h]; Buf2
0x180007b8e  lea     r8d, [rbp+30h]; Size
0x180007b92  mov     rcx, [rcx]; Buf1
0x180007b95  call    memcmp_0
0x180007b9a  test    eax, eax
0x180007b9c  jz      short loc_180007BA5
0x180007b9e  mov     edx, esi
0x180007ba0  jmp     loc_180007CC9
0x180007ba5  mov     [rbx+3Ch], r14w
0x180007baa  xor     eax, eax
0x180007bac  jmp     loc_180007CD4
0x180007bb1  cmp     edi, 5
0x180007bb4  jz      short loc_180007BBD
0x180007bb6  mov     eax, edi
0x180007bb8  jmp     loc_180007CD4
0x180007bbd  mov     r12d, [rbx+58h]
0x180007bc1  mov     r15d, r14d
0x180007bc4  mov     esi, r14d
0x180007bc7  mov     ebp, 1
0x180007bcc  mov     eax, ebp
0x180007bce  mov     r14d, [r13+rax*4+64h]
0x180007bd3  call    sehInjectFault
0x180007bd8  cmp     r15d, r14d
0x180007bdb  ja      short loc_180007BE7
0x180007bdd  cmp     r14d, r12d
0x180007be0  ja      short loc_180007BE7
0x180007be2  mov     r15d, r14d
0x180007be5  mov     esi, ebp
0x180007be7  inc     ebp
0x180007be9  cmp     ebp, 5
0x180007bec  jl      short loc_180007BCC
0x180007bee  test    byte ptr [rbx+42h], 2
0x180007bf2  jnz     short loc_180007C49
0x180007bf4  cmp     r15d, r12d
0x180007bf7  jb      short loc_180007BFD
0x180007bf9  test    esi, esi
0x180007bfb  jnz     short loc_180007C5D
0x180007bfd  mov     ebp, 1
0x180007c02  cmp     ebp, 5
0x180007c05  jge     short loc_180007C49
0x180007c07  mov     r8d, 1
0x180007c0d  lea     edx, [rbp+3]
0x180007c10  mov     rcx, rbx
0x180007c13  call    walLockExclusive
0x180007c18  mov     edi, eax
0x180007c1a  test    eax, eax
0x180007c1c  jz      short loc_180007C2B
0x180007c1e  cmp     eax, 5
0x180007c21  jnz     loc_180007CD4
0x180007c27  inc     ebp
0x180007c29  jmp     short loc_180007C02
0x180007c2b  movsxd  rax, ebp
0x180007c2e  lea     edx, [rbp+3]
0x180007c31  mov     r8d, 1
0x180007c37  mov     rcx, rbx
0x180007c3a  mov     r15d, r12d
0x180007c3d  mov     esi, ebp
0x180007c3f  mov     [r13+rax*4+64h], r12d
0x180007c44  call    walUnlockExclusive
0x180007c49  test    esi, esi
0x180007c4b  jnz     short loc_180007C5D
0x180007c4d  or      eax, 0FFFFFFFFh
0x180007c50  mov     ecx, 508h
0x180007c55  cmp     edi, 5
0x180007c58  cmovnz  eax, ecx
0x180007c5b  jmp     short loc_180007CD4
0x180007c5d  lea     edx, [rsi+3]
0x180007c60  mov     rcx, rbx
0x180007c63  call    walLockShared
0x180007c68  mov     ecx, eax
0x180007c6a  test    eax, eax
0x180007c6c  jz      short loc_180007C7B
0x180007c6e  or      eax, 0FFFFFFFFh
0x180007c71  cmp     cl, 5
0x180007c74  cmovz   ecx, eax
0x180007c77  mov     eax, ecx
0x180007c79  jmp     short loc_180007CD4
0x180007c7b  mov     eax, [r13+60h]
0x180007c7f  inc     eax
0x180007c81  mov     [rbx+78h], eax
0x180007c84  call    sehInjectFault
0x180007c89  mov     rcx, rbx
0x180007c8c  call    walShmBarrier
0x180007c91  movsxd  rax, esi
0x180007c94  mov     ecx, [r13+rax*4+64h]
0x180007c99  cmp     ecx, r15d
0x180007c9c  jnz     short loc_180007CC6
0x180007c9e  call    sehInjectFault
0x180007ca3  mov     rcx, [rbx+30h]
0x180007ca7  lea     rdx, [rbx+48h]; Buf2
0x180007cab  mov     r8d, 30h ; '0'; Size
0x180007cb1  mov     rcx, [rcx]; Buf1
0x180007cb4  call    memcmp_0
0x180007cb9  test    eax, eax
0x180007cbb  jnz     short loc_180007CC6
0x180007cbd  mov     [rbx+3Ch], si
0x180007cc1  jmp     loc_180007BAA
0x180007cc6  lea     edx, [rsi+3]
0x180007cc9  mov     rcx, rbx
0x180007ccc  call    walUnlockShared
0x180007cd1  or      eax, 0FFFFFFFFh
0x180007cd4  add     rsp, 28h
0x180007cd8  pop     r15
0x180007cda  pop     r14
0x180007cdc  pop     r13
0x180007cde  pop     r12
0x180007ce0  pop     rdi
0x180007ce1  pop     rsi
0x180007ce2  pop     rbp
0x180007ce3  pop     rbx
0x180007ce4  retn
```
