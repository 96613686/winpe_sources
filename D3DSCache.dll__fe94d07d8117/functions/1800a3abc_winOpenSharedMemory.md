# winOpenSharedMemory

- ea: `0x1800a3abc`
- end: `0x1800a3cd6`
- name: `winOpenSharedMemory`
- size: `538`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180034620`

## callees

- `0x180012470`
- `0x1800293d4`
- `0x180029560`
- `0x18002b81c`
- `0x18002e290`
- `0x180034900`
- `0x180035b00`
- `0x18003f650`
- `0x180041688`
- `0x180042500`
- `0x1800965d0`
- `0x1800a3640`
- `0x1800a3abc`
- `0x1800a4028`
- `0x1800a4128`
- `0x1800a8010`

## string_xrefs

- `0x1800a3c01`: `readonly_shm`
- `0x1800a3c60`: `winOpenShm`

## pseudocode

```c
__int64 __fastcall winOpenSharedMemory(__int64 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 *v4; // r14
  __int64 v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdi
  __int64 i; // rsi
  __int64 v10; // rax
  unsigned int v11; // ebx
  __int64 *v12; // r15
  __int64 v13; // rcx
  __int64 v14; // rcx
  int v15; // eax
  __int16 v16; // r9
  int v17; // esi
  __int64 v18; // rbx
  DWORD v19; // eax
  unsigned int v20; // eax
  int v21; // [rsp+78h] [rbp+10h] BYREF

  v4 = (__int64 *)sqlite3MallocZero(0x18u);
  if ( !v4 )
    return 3082;
  v6 = (int)sqlite3Strlen30(a1[6], v2, v3);
  v7 = sqlite3MallocZero(v6 + 177);
  v8 = v7;
  if ( !v7 )
  {
    sqlite3_free(v4);
    return 3082;
  }
  *(_QWORD *)(v7 + 8) = v7 + 160;
  sqlite3_snprintf((unsigned int)(v6 + 15), v7 + 160, "%s-shm", (const char *)a1[6]);
  sqlite3_mutex_enter(qword_1800C78E0);
  for ( i = qword_1800C79B8; i; i = *(_QWORD *)(i + 152) )
  {
    if ( !(unsigned int)sqlite3StrICmp(*(_QWORD *)(i + 8), *(_QWORD *)(v8 + 8)) )
    {
      v11 = 0;
      sqlite3_free(v8);
LABEL_13:
      v13 = qword_1800C78E0;
      *v4 = i;
      ++*(_DWORD *)(i + 140);
      a1[5] = (__int64)v4;
      sqlite3_mutex_leave(v13);
      sqlite3_mutex_enter(*(_QWORD *)i);
      v4[1] = *(_QWORD *)(i + 144);
      v14 = *(_QWORD *)i;
      *(_QWORD *)(i + 144) = v4;
      goto LABEL_14;
    }
  }
  *(_QWORD *)(v8 + 32) = -1;
  *(_QWORD *)(v8 + 152) = qword_1800C79B8;
  v21 = 0;
  qword_1800C79B8 = v8;
  if ( !(_BYTE)word_1800C6974 || (v10 = sqlite3_mutex_alloc(0), (*(_QWORD *)v8 = v10) != 0) )
  {
    v15 = sqlite3_uri_boolean(a1[6], "readonly_shm", 0);
    v12 = a1 + 1;
    v16 = 6;
    if ( v15 )
      v16 = 1;
    v17 = winOpen(*v12, *(_QWORD *)(v8 + 8), v8 + 16, v16, &v21);
    if ( v17 )
    {
      v18 = *(_QWORD *)(v8 + 8);
      v19 = off_1800C40C8();
      v11 = winLogErrorAtLine(v17, v19, (unsigned int)"winOpenShm", v18, 50636);
    }
    else
    {
      i = v8;
      if ( v21 == 1 )
        *(_BYTE *)(v8 + 120) = 1;
      v20 = winLockSharedMemory(v8);
      v11 = v20;
      if ( !v20 || v20 == 1288 )
        goto LABEL_13;
    }
  }
  else
  {
    v11 = 3082;
    v12 = a1 + 1;
  }
  winShmSystemLock(v8, 1, 128, 1);
  winShmPurge(*v12, 0);
  sqlite3_free(v4);
  sqlite3_free(0);
  v14 = qword_1800C78E0;
LABEL_14:
  sqlite3_mutex_leave(v14);
  return v11;
}

```

## disassembly

```asm
0x1800a3abc  push    rbx
0x1800a3abe  push    rbp
0x1800a3abf  push    rsi
0x1800a3ac0  push    rdi
0x1800a3ac1  push    r14
0x1800a3ac3  push    r15
0x1800a3ac5  sub     rsp, 38h
0x1800a3ac9  mov     rbp, rcx
0x1800a3acc  mov     ecx, 18h; Size
0x1800a3ad1  call    sqlite3MallocZero
0x1800a3ad6  mov     r14, rax
0x1800a3ad9  test    rax, rax
0x1800a3adc  jnz     short loc_1800A3AE8
0x1800a3ade  mov     eax, 0C0Ah
0x1800a3ae3  jmp     loc_1800A3BF0
0x1800a3ae8  mov     rcx, [rbp+30h]
0x1800a3aec  call    sqlite3Strlen30
0x1800a3af1  movsxd  rbx, eax
0x1800a3af4  lea     rcx, [rbx+0B1h]; Size
0x1800a3afb  call    sqlite3MallocZero
0x1800a3b00  mov     rdi, rax
0x1800a3b03  test    rax, rax
0x1800a3b06  jnz     short loc_1800A3B12
0x1800a3b08  mov     rcx, r14
0x1800a3b0b  call    sqlite3_free
0x1800a3b10  jmp     short loc_1800A3ADE
0x1800a3b12  lea     rdx, [rax+0A0h]
0x1800a3b19  mov     [rax+8], rdx
0x1800a3b1d  lea     ecx, [rbx+0Fh]
0x1800a3b20  mov     r9, [rbp+30h]
0x1800a3b24  lea     r8, aSShm; "%s-shm"
0x1800a3b2b  call    sqlite3_snprintf
0x1800a3b30  mov     rcx, cs:qword_1800C78E0
0x1800a3b37  call    sqlite3_mutex_enter
0x1800a3b3c  mov     rsi, cs:qword_1800C79B8
0x1800a3b43  jmp     short loc_1800A3B5D
0x1800a3b45  mov     rdx, [rdi+8]
0x1800a3b49  mov     rcx, [rsi+8]
0x1800a3b4d  call    sqlite3StrICmp
0x1800a3b52  test    eax, eax
0x1800a3b54  jz      short loc_1800A3BA9
0x1800a3b56  mov     rsi, [rsi+98h]
0x1800a3b5d  test    rsi, rsi
0x1800a3b60  jnz     short loc_1800A3B45
0x1800a3b62  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x1800a3b6a  mov     rax, cs:qword_1800C79B8
0x1800a3b71  mov     [rdi+98h], rax
0x1800a3b78  cmp     byte ptr cs:word_1800C6974, sil
0x1800a3b7f  mov     [rsp+68h+arg_8], esi
0x1800a3b83  mov     cs:qword_1800C79B8, rdi
0x1800a3b8a  jz      short loc_1800A3BFD
0x1800a3b8c  xor     ecx, ecx
0x1800a3b8e  call    sqlite3_mutex_alloc
0x1800a3b93  mov     [rdi], rax
0x1800a3b96  test    rax, rax
0x1800a3b99  jnz     short loc_1800A3BFD
0x1800a3b9b  mov     ebx, 0C0Ah
0x1800a3ba0  lea     r15, [rbp+8]
0x1800a3ba4  jmp     loc_1800A3C9D
0x1800a3ba9  xor     ebx, ebx
0x1800a3bab  mov     rcx, rdi
0x1800a3bae  call    sqlite3_free
0x1800a3bb3  mov     rcx, cs:qword_1800C78E0
0x1800a3bba  mov     [r14], rsi
0x1800a3bbd  inc     dword ptr [rsi+8Ch]
0x1800a3bc3  mov     [rbp+28h], r14
0x1800a3bc7  call    sqlite3_mutex_leave
0x1800a3bcc  mov     rcx, [rsi]
0x1800a3bcf  call    sqlite3_mutex_enter
0x1800a3bd4  mov     rax, [rsi+90h]
0x1800a3bdb  mov     [r14+8], rax
0x1800a3bdf  mov     rcx, [rsi]
0x1800a3be2  mov     [rsi+90h], r14
0x1800a3be9  call    sqlite3_mutex_leave
0x1800a3bee  mov     eax, ebx
0x1800a3bf0  add     rsp, 38h
0x1800a3bf4  pop     r15
0x1800a3bf6  pop     r14
0x1800a3bf8  pop     rdi
0x1800a3bf9  pop     rsi
0x1800a3bfa  pop     rbp
0x1800a3bfb  pop     rbx
0x1800a3bfc  retn
0x1800a3bfd  mov     rcx, [rbp+30h]
0x1800a3c01  lea     rdx, aReadonlyShm; "readonly_shm"
0x1800a3c08  xor     r8d, r8d
0x1800a3c0b  call    sqlite3_uri_boolean
0x1800a3c10  mov     rdx, [rdi+8]
0x1800a3c14  lea     r15, [rbp+8]
0x1800a3c18  mov     ecx, 80001h
0x1800a3c1d  lea     r8, [rdi+10h]
0x1800a3c21  test    eax, eax
0x1800a3c23  lea     rax, [rsp+68h+arg_8]
0x1800a3c28  mov     [rsp+68h+var_48], rax
0x1800a3c2d  lea     r9d, [rcx+5]
0x1800a3c31  cmovnz  r9d, ecx
0x1800a3c35  mov     rcx, [r15]
0x1800a3c38  call    winOpen
0x1800a3c3d  mov     esi, eax
0x1800a3c3f  test    eax, eax
0x1800a3c41  jz      short loc_1800A3C72
0x1800a3c43  mov     rax, cs:off_1800C40C8
0x1800a3c4a  mov     rbx, [rdi+8]
0x1800a3c4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c53  mov     edx, eax
0x1800a3c55  mov     dword ptr [rsp+68h+var_48], 0C5CCh
0x1800a3c5d  mov     r9, rbx
0x1800a3c60  lea     r8, aWinopenshm; "winOpenShm"
0x1800a3c67  mov     ecx, esi
0x1800a3c69  call    winLogErrorAtLine
0x1800a3c6e  mov     ebx, eax
0x1800a3c70  jmp     short loc_1800A3C9D
0x1800a3c72  cmp     [rsp+68h+arg_8], 1
0x1800a3c77  mov     rsi, rdi
0x1800a3c7a  jnz     short loc_1800A3C80
0x1800a3c7c  mov     byte ptr [rdi+78h], 1
0x1800a3c80  mov     rcx, rdi
0x1800a3c83  call    winLockSharedMemory
0x1800a3c88  mov     ebx, eax
0x1800a3c8a  test    eax, eax
0x1800a3c8c  jz      loc_1800A3BB3
0x1800a3c92  cmp     eax, 508h
0x1800a3c97  jz      loc_1800A3BB3
0x1800a3c9d  mov     edx, 1
0x1800a3ca2  mov     rcx, rdi
0x1800a3ca5  mov     r9d, edx
0x1800a3ca8  lea     r8d, [rdx+7Fh]
0x1800a3cac  call    winShmSystemLock
0x1800a3cb1  mov     rcx, [r15]
0x1800a3cb4  xor     edx, edx
0x1800a3cb6  call    winShmPurge
0x1800a3cbb  mov     rcx, r14
0x1800a3cbe  call    sqlite3_free
0x1800a3cc3  xor     ecx, ecx
0x1800a3cc5  call    sqlite3_free
0x1800a3cca  mov     rcx, cs:qword_1800C78E0
0x1800a3cd1  jmp     loc_1800A3BE9
```
