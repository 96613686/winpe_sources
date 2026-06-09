# memdbOpen

- ea: `0x180079cf0`
- end: `0x180079eee`
- name: `memdbOpen`
- size: `510`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: ``

## callees

- `0x180005810`
- `0x180005d14`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18000bd90`
- `0x180047008`
- `0x180057a00`
- `0x18006910e`
- `0x180079cf0`
- `0x180099814`

## pseudocode

```c
__int64 __fastcall memdbOpen(__int64 a1, _BYTE *a2, __int64 a3, int a4, int *a5)
{
  int v8; // eax
  _BYTE *v9; // rdx
  __int64 v10; // r13
  __int64 v11; // rdi
  int i; // edx
  unsigned __int8 *v13; // rcx
  __int64 v14; // r9
  int v15; // r8d
  int v16; // eax
  __int64 v17; // rbx
  __int64 v19; // rax
  int v20; // ecx
  __int64 v21; // rax
  void *v22; // rax

  *(_OWORD *)a3 = 0;
  *(_QWORD *)(a3 + 16) = 0;
  v8 = sqlite3Strlen30(a2, a2, a3);
  v10 = v8;
  if ( v8 > 1 && (*v9 == 47 || *v9 == 92) )
  {
    v11 = sqlite3MutexAlloc(11);
    sqlite3_mutex_enter(v11);
    for ( i = 0; ; ++i )
    {
      if ( i >= dword_1800B5CF8 )
        goto LABEL_13;
      v13 = *(unsigned __int8 **)(*(_QWORD *)(qword_1800B5D00 + 8LL * i) + 64LL);
      v14 = a2 - v13;
      do
      {
        v15 = v13[v14];
        v16 = *v13 - v15;
        if ( v16 )
          break;
        ++v13;
      }
      while ( v15 );
      if ( !v16 )
        break;
    }
    _mm_lfence();
    v17 = *(_QWORD *)(qword_1800B5D00 + 8LL * i);
    if ( v17 )
    {
      sqlite3_mutex_enter(*(_QWORD *)(v17 + 32));
      ++*(_DWORD *)(v17 + 56);
LABEL_21:
      sqlite3_mutex_leave(v11);
      goto LABEL_24;
    }
LABEL_13:
    v17 = sqlite3Malloc(v10 + 75);
    if ( v17 )
    {
      v19 = sqlite3Realloc(qword_1800B5D00, 8LL * (dword_1800B5CF8 + 1));
      if ( v19 )
      {
        v20 = dword_1800B5CF8;
        qword_1800B5D00 = v19;
        *(_QWORD *)(v19 + 8LL * dword_1800B5CF8) = v17;
        dword_1800B5CF8 = v20 + 1;
        memset_0((void *)v17, 0, 0x48u);
        *(_DWORD *)(v17 + 44) = 3;
        *(_QWORD *)(v17 + 16) = qword_1800B57B8;
        *(_QWORD *)(v17 + 64) = v17 + 72;
        memcpy_0((void *)(v17 + 72), a2, (int)v10 + 1);
        v21 = sqlite3_mutex_alloc(0);
        *(_QWORD *)(v17 + 32) = v21;
        if ( v21 )
        {
          *(_DWORD *)(v17 + 56) = 1;
          sqlite3_mutex_enter(v21);
          goto LABEL_21;
        }
        --dword_1800B5CF8;
      }
      sqlite3_free(v17);
    }
    sqlite3_mutex_leave(v11);
    return 7;
  }
  v22 = (void *)sqlite3Malloc(72);
  v17 = (__int64)v22;
  if ( !v22 )
    return 7;
  memset_0(v22, 0, 0x48u);
  *(_DWORD *)(v17 + 44) = 3;
  *(_QWORD *)(v17 + 16) = qword_1800B57B8;
LABEL_24:
  *(_QWORD *)(a3 + 8) = v17;
  if ( a5 )
    *a5 = a4 | 0x80;
  *(_QWORD *)a3 = &qword_18009B5A0;
  sqlite3_mutex_leave(*(_QWORD *)(v17 + 32));
  return 0;
}

```

## disassembly

```asm
0x180079cf0  push    rbx
0x180079cf2  push    rbp
0x180079cf3  push    rdi
0x180079cf4  push    r13
0x180079cf6  push    r14
0x180079cf8  push    r15
0x180079cfa  sub     rsp, 28h
0x180079cfe  xor     eax, eax
0x180079d00  xorps   xmm0, xmm0
0x180079d03  movups  xmmword ptr [r8], xmm0
0x180079d07  mov     rcx, rdx
0x180079d0a  mov     [r8+10h], rax
0x180079d0e  mov     ebp, r9d
0x180079d11  mov     r14, r8
0x180079d14  mov     r15, rdx
0x180079d17  call    sqlite3Strlen30
0x180079d1c  movsxd  r13, eax
0x180079d1f  cmp     r13d, 1
0x180079d23  jle     loc_180079E7E
0x180079d29  cmp     byte ptr [rdx], 2Fh ; '/'
0x180079d2c  jz      short loc_180079D37
0x180079d2e  cmp     byte ptr [rdx], 5Ch ; '\'
0x180079d31  jnz     loc_180079E7E
0x180079d37  mov     ecx, 0Bh
0x180079d3c  call    sqlite3MutexAlloc
0x180079d41  mov     rcx, rax
0x180079d44  mov     rdi, rax
0x180079d47  call    sqlite3_mutex_enter
0x180079d4c  mov     r10, cs:qword_1800B5D00
0x180079d53  xor     edx, edx
0x180079d55  cmp     edx, cs:dword_1800B5CF8
0x180079d5b  jge     short loc_180079DAF
0x180079d5d  movsxd  rbx, edx
0x180079d60  mov     r9, r15
0x180079d63  mov     rax, [r10+rbx*8]
0x180079d67  mov     rcx, [rax+40h]
0x180079d6b  sub     r9, rcx
0x180079d6e  movzx   eax, byte ptr [rcx]
0x180079d71  movzx   r8d, byte ptr [rcx+r9]
0x180079d76  sub     eax, r8d
0x180079d79  jnz     short loc_180079D83
0x180079d7b  inc     rcx
0x180079d7e  test    r8d, r8d
0x180079d81  jnz     short loc_180079D6E
0x180079d83  test    eax, eax
0x180079d85  jz      short loc_180079D8B
0x180079d87  inc     edx
0x180079d89  jmp     short loc_180079D55
0x180079d8b  lfence
0x180079d8e  mov     rax, cs:qword_1800B5D00
0x180079d95  mov     rbx, [rax+rbx*8]
0x180079d99  test    rbx, rbx
0x180079d9c  jz      short loc_180079DAF
0x180079d9e  mov     rcx, [rbx+20h]
0x180079da2  call    sqlite3_mutex_enter
0x180079da7  inc     dword ptr [rbx+38h]
0x180079daa  jmp     loc_180079E74
0x180079daf  lea     rcx, [r13+4Bh]
0x180079db3  call    sqlite3Malloc
0x180079db8  mov     rbx, rax
0x180079dbb  test    rax, rax
0x180079dbe  jnz     short loc_180079DD2
0x180079dc0  mov     rcx, rdi
0x180079dc3  call    sqlite3_mutex_leave
0x180079dc8  mov     eax, 7
0x180079dcd  jmp     loc_180079EE0
0x180079dd2  mov     eax, cs:dword_1800B5CF8
0x180079dd8  mov     rcx, cs:qword_1800B5D00
0x180079ddf  inc     eax
0x180079de1  movsxd  rdx, eax
0x180079de4  shl     rdx, 3
0x180079de8  call    sqlite3Realloc
0x180079ded  test    rax, rax
0x180079df0  jnz     short loc_180079DFC
0x180079df2  mov     rcx, rbx
0x180079df5  call    sqlite3_free
0x180079dfa  jmp     short loc_180079DC0
0x180079dfc  movsxd  rcx, cs:dword_1800B5CF8
0x180079e03  xor     edx, edx; Val
0x180079e05  mov     cs:qword_1800B5D00, rax
0x180079e0c  mov     [rax+rcx*8], rbx
0x180079e10  lea     r8d, [rdx+48h]; Size
0x180079e14  inc     ecx
0x180079e16  mov     cs:dword_1800B5CF8, ecx
0x180079e1c  mov     rcx, rbx; void *
0x180079e1f  call    memset_0
0x180079e24  mov     dword ptr [rbx+2Ch], 3
0x180079e2b  lea     rcx, [rbx+48h]; void *
0x180079e2f  mov     rax, cs:qword_1800B57B8
0x180079e36  mov     rdx, r15; Src
0x180079e39  mov     [rbx+10h], rax
0x180079e3d  lea     eax, [r13+1]
0x180079e41  movsxd  r8, eax; Size
0x180079e44  mov     [rbx+40h], rcx
0x180079e48  call    memcpy_0
0x180079e4d  xor     ecx, ecx
0x180079e4f  call    sqlite3_mutex_alloc
0x180079e54  mov     [rbx+20h], rax
0x180079e58  test    rax, rax
0x180079e5b  jnz     short loc_180079E65
0x180079e5d  dec     cs:dword_1800B5CF8
0x180079e63  jmp     short loc_180079DF2
0x180079e65  mov     rcx, rax
0x180079e68  mov     dword ptr [rbx+38h], 1
0x180079e6f  call    sqlite3_mutex_enter
0x180079e74  mov     rcx, rdi
0x180079e77  call    sqlite3_mutex_leave
0x180079e7c  jmp     short loc_180079EB4
0x180079e7e  mov     ecx, 48h ; 'H'
0x180079e83  call    sqlite3Malloc
0x180079e88  mov     rbx, rax
0x180079e8b  test    rax, rax
0x180079e8e  jz      loc_180079DC8
0x180079e94  xor     edx, edx; Val
0x180079e96  mov     rcx, rax; void *
0x180079e99  lea     r8d, [rdx+48h]; Size
0x180079e9d  call    memset_0
0x180079ea2  mov     dword ptr [rbx+2Ch], 3
0x180079ea9  mov     rax, cs:qword_1800B57B8
0x180079eb0  mov     [rbx+10h], rax
0x180079eb4  mov     rax, [rsp+58h+arg_20]
0x180079ebc  mov     [r14+8], rbx
0x180079ec0  test    rax, rax
0x180079ec3  jz      short loc_180079ECB
0x180079ec5  bts     ebp, 7
0x180079ec9  mov     [rax], ebp
0x180079ecb  lea     rax, qword_18009B5A0
0x180079ed2  mov     [r14], rax
0x180079ed5  mov     rcx, [rbx+20h]
0x180079ed9  call    sqlite3_mutex_leave
0x180079ede  xor     eax, eax
0x180079ee0  add     rsp, 28h
0x180079ee4  pop     r15
0x180079ee6  pop     r14
0x180079ee8  pop     r13
0x180079eea  pop     rdi
0x180079eeb  pop     rbp
0x180079eec  pop     rbx
0x180079eed  retn
```
