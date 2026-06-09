# CDynamicArray<CReaderReference>::Set(int,CReaderReference *)

- ea: `0x180003860`
- end: `0x1800039d1`
- name: `?Set@?$CDynamicArray@VCReaderReference@@@@QEAAPEAVCReaderReference@@HPEAV2@@Z`
- size: `369`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180004af8`
- `0x180006030`
- `0x18000a310`

## callees

- `0x180003860`
- `0x180023168`
- `0x180023174`
- `0x180023282`
- `0x18003261b`

## pseudocode

```c
__int64 __fastcall CDynamicArray<CReaderReference>::Set(__int64 a1, unsigned int a2, __int64 a3)
{
  int v3; // esi
  __int64 v5; // rbx
  char *v7; // r15
  __int64 v8; // r8
  void **i; // r14
  __int64 v10; // rdx
  __int64 v12; // rcx
  void **v13; // r10
  unsigned int v14; // eax
  unsigned int v15; // esi
  __int64 v16; // rdx
  ulong pExceptionObject; // [rsp+68h] [rbp+10h] BYREF

  v3 = *(_DWORD *)(a1 + 8);
  v5 = a2;
  if ( a2 < v3 )
  {
    i = (void **)(a1 + 16);
  }
  else
  {
    if ( !v3 )
      v3 = 4;
    for ( ; (int)a2 >= v3; v3 *= 2 )
      ;
    v7 = (char *)operator new[](saturated_mul(v3, 8u));
    if ( !v7 )
    {
      pExceptionObject = 14;
      throw &pExceptionObject;
    }
    v8 = 0;
    for ( i = (void **)(a1 + 16);
          (unsigned int)v8 < *(_DWORD *)(a1 + 12);
          *(_QWORD *)&v7[v16] = *(_QWORD *)((char *)*i + v16) )
    {
      v16 = 8 * v8;
      v8 = (unsigned int)(v8 + 1);
    }
    if ( *i )
      operator delete[](*i);
    *i = v7;
    *(_DWORD *)(a1 + 8) = v3;
  }
  v10 = *(unsigned int *)(a1 + 12);
  if ( (unsigned int)v5 >= (unsigned int)v10 )
  {
    if ( (unsigned int)v5 > (unsigned int)v10 )
    {
      if ( (unsigned int)(v5 - v10) < 2 )
        goto LABEL_31;
      v13 = (void **)((char *)*i + 8 * v10);
      if ( v13 <= i && (char *)*i + 8 * (unsigned int)(v5 - 1) >= (char *)i )
        goto LABEL_31;
      v14 = v5 - (((_BYTE)v5 - (_BYTE)v10) & 1);
      do
      {
        LODWORD(v10) = v10 + 2;
        v15 = v10;
      }
      while ( (unsigned int)v10 < v14 );
      memset_0(v13, 0, 16 * ((unsigned __int64)(v14 - *(_DWORD *)(a1 + 12) + 1) >> 1));
      LODWORD(v10) = v15;
      if ( v15 < (unsigned int)v5 )
      {
LABEL_31:
        do
        {
          v12 = (unsigned int)v10;
          LODWORD(v10) = v10 + 1;
          *((_QWORD *)*i + v12) = 0;
        }
        while ( (unsigned int)v10 < (unsigned int)v5 );
      }
    }
    *(_DWORD *)(a1 + 12) = v5 + 1;
  }
  *((_QWORD *)*i + v5) = a3;
  return a3;
}

```

## disassembly

```asm
0x180003860  push    rbx
0x180003862  push    rbp
0x180003863  push    rsi
0x180003864  push    rdi
0x180003865  push    r14
0x180003867  push    r15
0x180003869  sub     rsp, 28h
0x18000386d  mov     esi, [rcx+8]
0x180003870  mov     rbp, r8
0x180003873  mov     ebx, edx
0x180003875  mov     rdi, rcx
0x180003878  cmp     edx, esi
0x18000387a  jb      loc_180003907
0x180003880  test    esi, esi
0x180003882  mov     eax, 4
0x180003887  cmovz   esi, eax
0x18000388a  cmp     ebx, esi
0x18000388c  jge     loc_1800039A2
0x180003892  movsxd  rcx, esi
0x180003895  mov     eax, 8
0x18000389a  mul     rcx
0x18000389d  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800038a4  cmovb   rax, rcx
0x1800038a8  mov     rcx, rax; unsigned __int64
0x1800038ab  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800038b0  mov     r15, rax
0x1800038b3  test    rax, rax
0x1800038b6  jz      loc_1800039AD
0x1800038bc  xor     r8d, r8d
0x1800038bf  lea     r14, [rdi+10h]
0x1800038c3  cmp     [rdi+0Ch], r8d
0x1800038c7  ja      loc_180003980
0x1800038cd  mov     rcx, [r14]; Block
0x1800038d0  test    rcx, rcx
0x1800038d3  jnz     loc_1800039C7
0x1800038d9  mov     [r14], r15
0x1800038dc  mov     [rdi+8], esi
0x1800038df  mov     edx, [rdi+0Ch]
0x1800038e2  cmp     ebx, edx
0x1800038e4  jnb     short loc_1800038FD
0x1800038e6  mov     rax, [r14]
0x1800038e9  mov     [rax+rbx*8], rbp
0x1800038ed  mov     rax, rbp
0x1800038f0  add     rsp, 28h
0x1800038f4  pop     r15
0x1800038f6  pop     r14
0x1800038f8  pop     rdi
0x1800038f9  pop     rsi
0x1800038fa  pop     rbp
0x1800038fb  pop     rbx
0x1800038fc  retn
0x1800038fd  ja      short loc_18000390D
0x1800038ff  lea     eax, [rbx+1]
0x180003902  mov     [rdi+0Ch], eax
0x180003905  jmp     short loc_1800038E6
0x180003907  lea     r14, [rcx+10h]
0x18000390b  jmp     short loc_1800038DF
0x18000390d  mov     r8d, ebx
0x180003910  sub     r8d, edx
0x180003913  cmp     r8d, 2
0x180003917  jnb     short loc_18000392E
0x180003919  mov     rax, [r14]
0x18000391c  mov     ecx, edx
0x18000391e  inc     edx
0x180003920  mov     qword ptr [rax+rcx*8], 0
0x180003928  cmp     edx, ebx
0x18000392a  jnb     short loc_1800038FF
0x18000392c  jmp     short loc_180003919
0x18000392e  mov     r9, [r14]
0x180003931  lea     r10, [r9+rdx*8]
0x180003935  cmp     r10, r14
0x180003938  ja      short loc_180003946
0x18000393a  lea     eax, [rbx-1]
0x18000393d  lea     rax, [r9+rax*8]
0x180003941  cmp     rax, r14
0x180003944  jnb     short loc_180003919
0x180003946  and     r8d, 1
0x18000394a  mov     eax, ebx
0x18000394c  sub     eax, r8d
0x18000394f  mov     ecx, edx
0x180003951  add     edx, 2
0x180003954  mov     esi, edx
0x180003956  cmp     edx, eax
0x180003958  jb      short loc_180003951
0x18000395a  sub     eax, ecx
0x18000395c  xor     edx, edx; Val
0x18000395e  mov     rcx, r10; void *
0x180003961  lea     r8d, [rax+1]
0x180003965  shr     r8, 1
0x180003968  shl     r8, 4
0x18000396c  and     r8, 0FFFFFFFFFFFFFFF8h; Size
0x180003970  call    memset_0
0x180003975  mov     edx, esi
0x180003977  cmp     esi, ebx
0x180003979  jb      short loc_180003919
0x18000397b  jmp     short loc_1800038FF
0x180003980  mov     rax, [r14]
0x180003983  lea     rdx, ds:0[r8*8]
0x18000398b  inc     r8d
0x18000398e  mov     rcx, [rdx+rax]
0x180003992  mov     [rdx+r15], rcx
0x180003996  cmp     r8d, [rdi+0Ch]
0x18000399a  jnb     loc_1800038CD
0x1800039a0  jmp     short loc_180003980
0x1800039a2  add     esi, esi
0x1800039a4  cmp     ebx, esi
0x1800039a6  jge     short loc_1800039A2
0x1800039a8  jmp     loc_180003892
0x1800039ad  lea     rdx, _TI1K; pThrowInfo
0x1800039b4  mov     [rsp+58h+pExceptionObject], 0Eh
0x1800039bc  lea     rcx, [rsp+58h+pExceptionObject]; pExceptionObject
0x1800039c1  call    _CxxThrowException_0
0x1800039c7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1800039cc  jmp     loc_1800038D9
```
