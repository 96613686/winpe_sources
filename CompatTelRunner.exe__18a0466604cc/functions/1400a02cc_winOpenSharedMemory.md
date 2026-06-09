# winOpenSharedMemory

- ea: `0x1400a02cc`
- end: `0x1400a0533`
- name: `winOpenSharedMemory`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1400a0aa0`

## callees

- `0x140062d60`
- `0x1400702ec`
- `0x14008ac90`
- `0x14008b950`
- `0x14008ccd0`
- `0x14008f690`
- `0x14009f980`
- `0x14009fa4c`
- `0x14009ff30`
- `0x1400a02cc`
- `0x1400a0d90`
- `0x1400a0eac`
- `0x1400a8010`

## string_xrefs

- `0x1400a04bd`: `winOpenShm`
- `0x1400a045e`: `readonly_shm`

## pseudocode

```c
__int64 __fastcall winOpenSharedMemory(_QWORD *a1)
{
  __int64 *v2; // r14
  __int64 v4; // rax
  unsigned int v5; // ebx
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rsi
  __int64 i; // rdi
  __int64 v10; // rax
  unsigned int v11; // ebx
  _QWORD *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // r9
  int v17; // edi
  __int64 v18; // rbx
  DWORD v19; // eax
  unsigned int v20; // eax
  int v21; // [rsp+78h] [rbp+10h] BYREF

  v2 = (__int64 *)sqlite3MallocZero(0x18u);
  if ( !v2 )
    return 3082;
  v4 = a1[6];
  if ( v4 )
  {
    v6 = -1;
    do
      ++v6;
    while ( *(_BYTE *)(v4 + v6) );
    v5 = v6 & 0x3FFFFFFF;
  }
  else
  {
    v5 = 0;
  }
  v7 = sqlite3MallocZero(v5 + 177LL);
  v8 = v7;
  if ( !v7 )
  {
    sqlite3_free(v2);
    return 3082;
  }
  *(_QWORD *)(v7 + 8) = v7 + 160;
  sqlite3_snprintf(v5 + 15, v7 + 160, "%s-shm", (const char *)a1[6]);
  if ( qword_1400C9158 )
    ((void (*)(void))xmmword_1400C8530)();
  for ( i = qword_1400C9228; ; i = *(_QWORD *)(i + 152) )
  {
    if ( !i )
    {
      *(_QWORD *)(v8 + 32) = -1;
      *(_QWORD *)(v8 + 152) = qword_1400C9228;
      v21 = 0;
      qword_1400C9228 = v8;
      if ( !(_BYTE)word_1400C84B4 || (v10 = sqlite3_mutex_alloc(0), (*(_QWORD *)v8 = v10) != 0) )
      {
        v15 = sqlite3_uri_boolean(a1[6], "readonly_shm", 0);
        v12 = a1 + 1;
        v16 = 524294;
        if ( v15 )
          v16 = 524289;
        v17 = winOpen(*v12, *(_QWORD *)(v8 + 8), v8 + 16, v16, &v21);
        if ( v17 )
        {
          v18 = *(_QWORD *)(v8 + 8);
          v19 = off_1400C5C68();
          v11 = winLogErrorAtLine(v17, v19, (unsigned int)"winOpenShm", v18, 49778);
        }
        else
        {
          i = v8;
          if ( v21 == 1 )
            *(_BYTE *)(v8 + 120) = 1;
          v20 = winLockSharedMemory(v8);
          v11 = v20;
          if ( !v20 || v20 == 1288 )
            goto LABEL_20;
        }
      }
      else
      {
        v11 = 3082;
        v12 = a1 + 1;
      }
      winShmSystemLock(v8, 1, 128, 1);
      winShmPurge(*v12, 0);
      sqlite3_free(v2);
      sqlite3_free(0);
      v14 = qword_1400C9158;
      goto LABEL_25;
    }
    if ( !(unsigned int)sqlite3StrICmp(*(_QWORD *)(i + 8), *(_QWORD *)(v8 + 8)) )
      break;
  }
  v11 = 0;
  sqlite3_free(v8);
LABEL_20:
  v13 = qword_1400C9158;
  *v2 = i;
  ++*(_DWORD *)(i + 140);
  a1[5] = v2;
  if ( v13 )
    ((void (*)(void))xmmword_1400C8540)();
  if ( *(_QWORD *)i )
    ((void (*)(void))xmmword_1400C8530)();
  v2[1] = *(_QWORD *)(i + 144);
  v14 = *(_QWORD *)i;
  *(_QWORD *)(i + 144) = v2;
LABEL_25:
  if ( v14 )
    ((void (*)(void))xmmword_1400C8540)();
  return v11;
}

```

## disassembly

```asm
0x1400a02cc  push    rbx
0x1400a02ce  push    rbp
0x1400a02cf  push    rsi
0x1400a02d0  push    rdi
0x1400a02d1  push    r14
0x1400a02d3  push    r15
0x1400a02d5  sub     rsp, 38h
0x1400a02d9  mov     rbp, rcx
0x1400a02dc  mov     ecx, 18h; Size
0x1400a02e1  call    sqlite3MallocZero
0x1400a02e6  mov     r14, rax
0x1400a02e9  test    rax, rax
0x1400a02ec  jnz     short loc_1400A02F8
0x1400a02ee  mov     eax, 0C0Ah
0x1400a02f3  jmp     loc_1400A044D
0x1400a02f8  mov     rax, [rbp+30h]
0x1400a02fc  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400a0300  test    rax, rax
0x1400a0303  jnz     short loc_1400A0309
0x1400a0305  xor     ebx, ebx
0x1400a0307  jmp     short loc_1400A031B
0x1400a0309  mov     rbx, r15
0x1400a030c  inc     rbx
0x1400a030f  cmp     byte ptr [rax+rbx], 0
0x1400a0313  jnz     short loc_1400A030C
0x1400a0315  and     ebx, 3FFFFFFFh
0x1400a031b  mov     ecx, ebx
0x1400a031d  add     rcx, 0B1h; Size
0x1400a0324  call    sqlite3MallocZero
0x1400a0329  mov     rsi, rax
0x1400a032c  test    rax, rax
0x1400a032f  jnz     short loc_1400A033B
0x1400a0331  mov     rcx, r14
0x1400a0334  call    sqlite3_free
0x1400a0339  jmp     short loc_1400A02EE
0x1400a033b  lea     rdx, [rax+0A0h]
0x1400a0342  mov     [rax+8], rdx
0x1400a0346  lea     ecx, [rbx+0Fh]
0x1400a0349  mov     r9, [rbp+30h]
0x1400a034d  lea     r8, aSShm; "%s-shm"
0x1400a0354  call    sqlite3_snprintf
0x1400a0359  mov     rcx, cs:qword_1400C9158
0x1400a0360  test    rcx, rcx
0x1400a0363  jz      short loc_1400A0371
0x1400a0365  mov     rax, qword ptr cs:xmmword_1400C8530
0x1400a036c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0371  mov     rdi, cs:qword_1400C9228
0x1400a0378  jmp     short loc_1400A0392
0x1400a037a  mov     rdx, [rsi+8]
0x1400a037e  mov     rcx, [rdi+8]
0x1400a0382  call    sqlite3StrICmp
0x1400a0387  test    eax, eax
0x1400a0389  jz      short loc_1400A03E2
0x1400a038b  mov     rdi, [rdi+98h]
0x1400a0392  test    rdi, rdi
0x1400a0395  jnz     short loc_1400A037A
0x1400a0397  mov     [rsi+20h], r15
0x1400a039b  mov     rax, cs:qword_1400C9228
0x1400a03a2  mov     [rsi+98h], rax
0x1400a03a9  cmp     byte ptr cs:word_1400C84B4, dil
0x1400a03b0  mov     [rsp+68h+arg_8], edi
0x1400a03b4  mov     cs:qword_1400C9228, rsi
0x1400a03bb  jz      loc_1400A045A
0x1400a03c1  xor     ecx, ecx
0x1400a03c3  call    sqlite3_mutex_alloc
0x1400a03c8  mov     [rsi], rax
0x1400a03cb  test    rax, rax
0x1400a03ce  jnz     loc_1400A045A
0x1400a03d4  mov     ebx, 0C0Ah
0x1400a03d9  lea     r15, [rbp+8]
0x1400a03dd  jmp     loc_1400A04FA
0x1400a03e2  xor     ebx, ebx
0x1400a03e4  mov     rcx, rsi
0x1400a03e7  call    sqlite3_free
0x1400a03ec  mov     rcx, cs:qword_1400C9158
0x1400a03f3  mov     [r14], rdi
0x1400a03f6  inc     dword ptr [rdi+8Ch]
0x1400a03fc  mov     [rbp+28h], r14
0x1400a0400  test    rcx, rcx
0x1400a0403  jz      short loc_1400A0411
0x1400a0405  mov     rax, qword ptr cs:xmmword_1400C8540
0x1400a040c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0411  mov     rcx, [rdi]
0x1400a0414  test    rcx, rcx
0x1400a0417  jz      short loc_1400A0425
0x1400a0419  mov     rax, qword ptr cs:xmmword_1400C8530
0x1400a0420  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a0425  mov     rax, [rdi+90h]
0x1400a042c  mov     [r14+8], rax
0x1400a0430  mov     rcx, [rdi]
0x1400a0433  mov     [rdi+90h], r14
0x1400a043a  test    rcx, rcx
0x1400a043d  jz      short loc_1400A044B
0x1400a043f  mov     rax, qword ptr cs:xmmword_1400C8540
0x1400a0446  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a044b  mov     eax, ebx
0x1400a044d  add     rsp, 38h
0x1400a0451  pop     r15
0x1400a0453  pop     r14
0x1400a0455  pop     rdi
0x1400a0456  pop     rsi
0x1400a0457  pop     rbp
0x1400a0458  pop     rbx
0x1400a0459  retn
0x1400a045a  mov     rcx, [rbp+30h]
0x1400a045e  lea     rdx, aReadonlyShm; "readonly_shm"
0x1400a0465  xor     r8d, r8d
0x1400a0468  call    sqlite3_uri_boolean
0x1400a046d  mov     rdx, [rsi+8]
0x1400a0471  lea     r15, [rbp+8]
0x1400a0475  mov     ecx, 80001h
0x1400a047a  lea     r8, [rsi+10h]
0x1400a047e  test    eax, eax
0x1400a0480  lea     rax, [rsp+68h+arg_8]
0x1400a0485  mov     [rsp+68h+var_48], rax
0x1400a048a  lea     r9d, [rcx+5]
0x1400a048e  cmovnz  r9d, ecx
0x1400a0492  mov     rcx, [r15]
0x1400a0495  call    winOpen
0x1400a049a  mov     edi, eax
0x1400a049c  test    eax, eax
0x1400a049e  jz      short loc_1400A04CF
0x1400a04a0  mov     rax, cs:off_1400C5C68
0x1400a04a7  mov     rbx, [rsi+8]
0x1400a04ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400a04b0  mov     edx, eax
0x1400a04b2  mov     dword ptr [rsp+68h+var_48], 0C272h
0x1400a04ba  mov     r9, rbx
0x1400a04bd  lea     r8, aWinopenshm; "winOpenShm"
0x1400a04c4  mov     ecx, edi
0x1400a04c6  call    winLogErrorAtLine
0x1400a04cb  mov     ebx, eax
0x1400a04cd  jmp     short loc_1400A04FA
0x1400a04cf  cmp     [rsp+68h+arg_8], 1
0x1400a04d4  mov     rdi, rsi
0x1400a04d7  jnz     short loc_1400A04DD
0x1400a04d9  mov     byte ptr [rsi+78h], 1
0x1400a04dd  mov     rcx, rsi
0x1400a04e0  call    winLockSharedMemory
0x1400a04e5  mov     ebx, eax
0x1400a04e7  test    eax, eax
0x1400a04e9  jz      loc_1400A03EC
0x1400a04ef  cmp     eax, 508h
0x1400a04f4  jz      loc_1400A03EC
0x1400a04fa  mov     edx, 1
0x1400a04ff  mov     rcx, rsi
0x1400a0502  mov     r9d, edx
0x1400a0505  lea     r8d, [rdx+7Fh]
0x1400a0509  call    winShmSystemLock
0x1400a050e  mov     rcx, [r15]
0x1400a0511  xor     edx, edx
0x1400a0513  call    winShmPurge
0x1400a0518  mov     rcx, r14
0x1400a051b  call    sqlite3_free
0x1400a0520  xor     ecx, ecx
0x1400a0522  call    sqlite3_free
0x1400a0527  mov     rcx, cs:qword_1400C9158
0x1400a052e  jmp     loc_1400A043A
```
