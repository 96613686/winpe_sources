# _ProcessBufferDescParameters

- ea: `0x18000b680`
- end: `0x18000b81b`
- name: `_ProcessBufferDescParameters`
- size: `411`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180004390`

## callees

- `0x180004200`
- `0x180004648`
- `0x180005060`
- `0x180007a7c`
- `0x180009430`
- `0x18000b680`

## string_xrefs

- `0x18000b70d`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`
- `0x18000b7e1`: `onecore\ds\security\cryptoapi\ncrypt\crypt\base.c`

## pseudocode

```c
__int64 __fastcall ProcessBufferDescParameters(__int64 a1, __int64 *a2)
{
  __int64 v2; // r9
  __int64 v4; // rbx
  BOOL v5; // r8d
  unsigned int v6; // r10d
  int v7; // edx
  __int64 v8; // rdi
  unsigned int v9; // ebx
  unsigned int i; // r8d
  __int64 v11; // rdx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rax

  v2 = *(unsigned int *)(a1 + 4);
  v4 = a1;
  if ( !(_DWORD)v2 )
  {
LABEL_24:
    *a2 = a1;
    return 0;
  }
  v5 = 0;
  v6 = 0;
  while ( !v5 )
  {
    v5 = *(_DWORD *)(*(_QWORD *)(a1 + 8) + 16LL * v6++ + 4) == 6;
    if ( v6 >= (unsigned int)v2 )
    {
      if ( !v5 )
        goto LABEL_24;
      break;
    }
  }
  v8 = SafeAllocaAllocateFromHeap(16 * v2);
  if ( v8 )
  {
    for ( i = 0; i < *(_DWORD *)(v4 + 4); ++i )
    {
      v11 = 2LL * i;
      *(_DWORD *)(v8 + 8 * v11 + 4) = *(_DWORD *)(*(_QWORD *)(v4 + 8) + 16LL * i + 4);
      *(_DWORD *)(v8 + 8 * v11) = *(_DWORD *)(*(_QWORD *)(v4 + 8) + 16LL * i);
      v12 = *(_QWORD *)(v4 + 8);
      if ( *(_DWORD *)(v12 + 16LL * i + 4) == 6 )
      {
        if ( *(_DWORD *)(v12 + 16LL * i) != 8 )
        {
          v9 = -1073741811;
          v15 = 3221225485LL;
          goto LABEL_22;
        }
        v14 = ValidateBaseSecretHandle(*(_QWORD *)(v12 + 16LL * i + 8));
        if ( !v14 )
        {
          v9 = -1073741816;
          v15 = 3221225480LL;
LABEL_22:
          DebugTraceError(v15, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c");
          MSCryptFree(v8);
          return v9;
        }
        v13 = *(_QWORD *)(v14 + 16);
      }
      else
      {
        v13 = *(_QWORD *)(v12 + 16LL * i + 8);
      }
      *(_QWORD *)(v8 + 8 * v11 + 8) = v13;
    }
    v16 = SafeAllocaAllocateFromHeap(16);
    a1 = v16;
    if ( !v16 )
    {
      v9 = -1073741801;
      v15 = 3221225495LL;
      goto LABEL_22;
    }
    *(_DWORD *)v16 = *(_DWORD *)v4;
    *(_DWORD *)(v16 + 4) = *(_DWORD *)(v4 + 4);
    *(_QWORD *)(v16 + 8) = v8;
    goto LABEL_24;
  }
  v9 = -1073741801;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v7,
      (unsigned int)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      (unsigned int)"Status",
      23,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\crypt\\base.c",
      88);
  return v9;
}

```

## disassembly

```asm
0x18000b680  push    rbx
0x18000b682  push    rbp
0x18000b683  push    rsi
0x18000b684  push    rdi
0x18000b685  sub     rsp, 48h
0x18000b689  mov     r9d, [rcx+4]
0x18000b68d  mov     rsi, rdx
0x18000b690  mov     rbx, rcx
0x18000b693  test    r9d, r9d
0x18000b696  jz      loc_18000B807
0x18000b69c  xor     r8d, r8d
0x18000b69f  xor     r10d, r10d
0x18000b6a2  lea     ebp, [r8+1]
0x18000b6a6  test    r8d, r8d
0x18000b6a9  jnz     short loc_18000B6CF
0x18000b6ab  mov     rcx, [rbx+8]
0x18000b6af  mov     eax, r10d
0x18000b6b2  add     rax, rax
0x18000b6b5  cmp     dword ptr [rcx+rax*8+4], 6
0x18000b6ba  cmovz   r8d, ebp
0x18000b6be  add     r10d, ebp
0x18000b6c1  cmp     r10d, r9d
0x18000b6c4  jb      short loc_18000B6A6
0x18000b6c6  test    r8d, r8d
0x18000b6c9  jz      loc_18000B807
0x18000b6cf  mov     rcx, r9
0x18000b6d2  shl     rcx, 4
0x18000b6d6  call    SafeAllocaAllocateFromHeap
0x18000b6db  mov     rdi, rax
0x18000b6de  test    rax, rax
0x18000b6e1  jnz     short loc_18000B73A
0x18000b6e3  mov     ebx, 0C0000017h
0x18000b6e8  mov     rax, cs:WPP_GLOBAL_Control
0x18000b6ef  lea     rcx, WPP_GLOBAL_Control
0x18000b6f6  cmp     rax, rcx
0x18000b6f9  jz      loc_18000B80F
0x18000b6ff  test    [rax+1Ch], bpl
0x18000b703  jz      loc_18000B80F
0x18000b709  mov     rcx, [rax+10h]
0x18000b70d  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b714  mov     [rsp+68h+var_38], 458h
0x18000b71c  lea     r9, aStatus; "Status"
0x18000b723  mov     [rsp+68h+var_40], r8
0x18000b728  mov     [rsp+68h+var_48], 0C0000017h
0x18000b730  call    WPP_SF_sDsd
0x18000b735  jmp     loc_18000B80F
0x18000b73a  xor     r8d, r8d
0x18000b73d  cmp     r8d, [rbx+4]
0x18000b741  jnb     short loc_18000B7B8
0x18000b743  mov     rax, [rbx+8]
0x18000b747  mov     edx, r8d
0x18000b74a  add     rdx, rdx
0x18000b74d  mov     ecx, [rax+rdx*8+4]
0x18000b751  mov     [rdi+rdx*8+4], ecx
0x18000b755  mov     rax, [rbx+8]
0x18000b759  mov     ecx, [rax+rdx*8]
0x18000b75c  mov     [rdi+rdx*8], ecx
0x18000b75f  mov     rcx, [rbx+8]
0x18000b763  cmp     dword ptr [rcx+rdx*8+4], 6
0x18000b768  jz      short loc_18000B771
0x18000b76a  mov     rax, [rcx+rdx*8+8]
0x18000b76f  jmp     short loc_18000B78A
0x18000b771  cmp     dword ptr [rcx+rdx*8], 8
0x18000b775  jnz     short loc_18000B7A6
0x18000b777  mov     rcx, [rcx+rdx*8+8]
0x18000b77c  call    ValidateBaseSecretHandle
0x18000b781  test    rax, rax
0x18000b784  jz      short loc_18000B794
0x18000b786  mov     rax, [rax+10h]
0x18000b78a  mov     [rdi+rdx*8+8], rax
0x18000b78f  add     r8d, ebp
0x18000b792  jmp     short loc_18000B73D
0x18000b794  mov     ebx, 0C0000008h
0x18000b799  mov     ecx, 0C0000008h
0x18000b79e  mov     r9d, 47Dh
0x18000b7a4  jmp     short loc_18000B7DA
0x18000b7a6  mov     ebx, 0C000000Dh
0x18000b7ab  mov     ecx, 0C000000Dh
0x18000b7b0  mov     r9d, 46Fh
0x18000b7b6  jmp     short loc_18000B7DA
0x18000b7b8  mov     ecx, 10h
0x18000b7bd  call    SafeAllocaAllocateFromHeap
0x18000b7c2  mov     rcx, rax
0x18000b7c5  test    rax, rax
0x18000b7c8  jnz     short loc_18000B7F7
0x18000b7ca  mov     ebx, 0C0000017h
0x18000b7cf  mov     ecx, 0C0000017h
0x18000b7d4  mov     r9d, 48Eh
0x18000b7da  lea     rdx, aStatus; "Status"
0x18000b7e1  lea     r8, aOnecoreDsSecur_0; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18000b7e8  call    DebugTraceError
0x18000b7ed  mov     rcx, rdi
0x18000b7f0  call    MSCryptFree
0x18000b7f5  jmp     short loc_18000B80F
0x18000b7f7  mov     eax, [rbx]
0x18000b7f9  mov     [rcx], eax
0x18000b7fb  mov     eax, [rbx+4]
0x18000b7fe  mov     [rcx+4], eax
0x18000b801  mov     [rcx+8], rdi
0x18000b805  jmp     short loc_18000B80A
0x18000b807  mov     rcx, rbx
0x18000b80a  mov     [rsi], rcx
0x18000b80d  xor     ebx, ebx
0x18000b80f  mov     eax, ebx
0x18000b811  add     rsp, 48h
0x18000b815  pop     rdi
0x18000b816  pop     rsi
0x18000b817  pop     rbp
0x18000b818  pop     rbx
0x18000b819  retn
```
