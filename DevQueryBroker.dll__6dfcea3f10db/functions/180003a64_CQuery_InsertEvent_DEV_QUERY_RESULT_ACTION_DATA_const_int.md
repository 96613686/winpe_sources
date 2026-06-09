# CQuery::InsertEvent(_DEV_QUERY_RESULT_ACTION_DATA const *,int)

- ea: `0x180003a64`
- end: `0x180003d0b`
- name: `?InsertEvent@CQuery@@QEAAJPEBU_DEV_QUERY_RESULT_ACTION_DATA@@H@Z`
- size: `679`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *this, const struct _DEV_QUERY_RESULT_ACTION_DATA *, int)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x180001bfc`
- `0x180003330`

## callees

- `0x1800039a0`
- `0x180003a64`
- `0x18000a192`

## import_xrefs

- `msvcrt!time` at `0x180003aac`
- `msvcrt!time` at `0x180003aac`
- `msvcrt!malloc` at `0x180003a83`
- `msvcrt!malloc` at `0x180003ab7`
- `msvcrt!malloc` at `0x180003b16`
- `msvcrt!malloc` at `0x180003b4c`
- `msvcrt!malloc` at `0x180003bdd`
- `msvcrt!malloc` at `0x180003c3b`
- `msvcrt!malloc` at `0x180003a83`
- `msvcrt!malloc` at `0x180003ab7`
- `msvcrt!malloc` at `0x180003b16`
- `msvcrt!malloc` at `0x180003b4c`
- `msvcrt!malloc` at `0x180003bdd`
- `msvcrt!malloc` at `0x180003c3b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ce6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180003ce6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c7d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180003c7d`

## pseudocode

```c
__int64 __fastcall CQuery::InsertEvent(
        struct _RTL_CRITICAL_SECTION *this,
        const struct _DEV_QUERY_RESULT_ACTION_DATA *a2,
        int a3)
{
  void *v6; // rax
  void **v7; // rdi
  unsigned int v8; // ebx
  _OWORD *v9; // rax
  int v10; // edx
  __int64 v11; // rax
  size_t v12; // rsi
  void *v13; // rcx
  size_t v14; // rsi
  void *v15; // rcx
  unsigned int v16; // ecx
  unsigned int i; // r8d
  __int64 v18; // rax
  __int64 v19; // rdx
  __int64 v20; // rcx
  unsigned int v21; // r14d
  __int64 v22; // r15
  size_t v23; // rcx
  void *v24; // rax
  __int64 v25; // rcx
  __int64 v26; // rax
  size_t v27; // r12
  void *v28; // rax
  int v29; // esi
  char *v30; // rcx
  char *v31; // rax
  __int64 v32; // rdx
  char **v33; // rdx

  v6 = malloc(0x20u);
  v7 = (void **)v6;
  if ( v6 )
  {
    *(_OWORD *)v6 = 0;
    *((_OWORD *)v6 + 1) = 0;
    time((time_t *const)v6 + 1);
    v9 = malloc(0x28u);
    *v7 = v9;
    if ( !v9 )
    {
LABEL_4:
      v8 = -2147024882;
      goto LABEL_31;
    }
    *v9 = 0;
    v9[1] = 0;
    *((_QWORD *)v9 + 4) = 0;
    *(_DWORD *)*v7 = *(_DWORD *)a2;
    v10 = *(_DWORD *)a2;
    *((_DWORD *)*v7 + 2) = *((_DWORD *)a2 + 2);
    if ( v10 )
    {
      v11 = -1;
      do
        ++v11;
      while ( *(_WORD *)(*((_QWORD *)a2 + 2) + 2 * v11) );
      v12 = 2 * v11 + 2;
      *((_QWORD *)*v7 + 2) = malloc(v12);
      v13 = (void *)*((_QWORD *)*v7 + 2);
      if ( !v13 )
        goto LABEL_4;
      memcpy_0(v13, *((const void **)a2 + 2), v12);
      v14 = 48LL * *((unsigned int *)a2 + 6);
      *((_QWORD *)*v7 + 4) = malloc(v14);
      v15 = (void *)*((_QWORD *)*v7 + 4);
      if ( !v15 )
        goto LABEL_4;
      memcpy_0(v15, *((const void **)a2 + 4), v14);
      v16 = *((_DWORD *)a2 + 6);
      for ( i = 0; i < v16; v16 = *((_DWORD *)a2 + 6) )
      {
        v18 = i++;
        v19 = 6 * v18;
        v20 = *((_QWORD *)*v7 + 4);
        *(_DWORD *)(v20 + 8 * v19 + 36) = 0;
        *(_QWORD *)(v20 + 8 * v19 + 40) = 0;
        *(_QWORD *)(v20 + 8 * v19 + 24) = 0;
      }
      v21 = 0;
      for ( *((_DWORD *)*v7 + 6) = v16; v21 < *((_DWORD *)a2 + 6); ++v21 )
      {
        v22 = *((_QWORD *)*v7 + 4);
        v23 = *(unsigned int *)(*((_QWORD *)a2 + 4) + 48LL * v21 + 36);
        if ( (_DWORD)v23 )
        {
          v24 = malloc(v23);
          *(_QWORD *)(v22 + 48LL * v21 + 40) = v24;
          if ( !v24 )
            goto LABEL_4;
          memcpy_0(
            v24,
            *(const void **)(*((_QWORD *)a2 + 4) + 48LL * v21 + 40),
            *(unsigned int *)(*((_QWORD *)a2 + 4) + 48LL * v21 + 36));
          *(_DWORD *)(v22 + 48LL * v21 + 36) = *(_DWORD *)(*((_QWORD *)a2 + 4) + 48LL * v21 + 36);
        }
        v25 = *(_QWORD *)(*((_QWORD *)a2 + 4) + 48LL * v21 + 24);
        if ( v25 )
        {
          v26 = -1;
          do
            ++v26;
          while ( *(_WORD *)(v25 + 2 * v26) );
          v27 = 2 * v26 + 2;
          v28 = malloc(v27);
          *(_QWORD *)(v22 + 48LL * v21 + 24) = v28;
          if ( !v28 )
            goto LABEL_4;
          memcpy_0(v28, *(const void **)(*((_QWORD *)a2 + 4) + 48LL * v21 + 24), v27);
        }
      }
    }
    EnterCriticalSection(this + 4);
    if ( LODWORD(this[5].DebugInfo) )
    {
      v29 = 1;
      goto LABEL_30;
    }
    ++HIDWORD(this[5].DebugInfo);
    v30 = (char *)(v7 + 2);
    v31 = (char *)&this[3];
    v29 = 0;
    if ( a3 )
    {
      v32 = *(_QWORD *)v31;
      if ( *(char **)(*(_QWORD *)v31 + 8LL) == v31 )
      {
        *(_QWORD *)v30 = v32;
        v7[3] = v31;
        *(_QWORD *)(v32 + 8) = v30;
        *(_QWORD *)v31 = v30;
        goto LABEL_30;
      }
    }
    else
    {
      v33 = *(char ***)&this[3].LockCount;
      if ( *v33 == v31 )
      {
        *(_QWORD *)v30 = v31;
        v7[3] = v33;
        *v33 = v30;
        *(_QWORD *)&this[3].LockCount = v30;
LABEL_30:
        v8 = 0;
        LeaveCriticalSection(this + 4);
        if ( !v29 )
          return v8;
LABEL_31:
        CQuery::FreeQueryEvent(v7);
        return v8;
      }
    }
    __fastfail(3u);
  }
  return (unsigned int)-2147024882;
}

```

## disassembly

```asm
0x180003a64  push    rbx
0x180003a66  push    rbp
0x180003a67  push    rsi
0x180003a68  push    rdi
0x180003a69  push    r12
0x180003a6b  push    r13
0x180003a6d  push    r14
0x180003a6f  push    r15
0x180003a71  sub     rsp, 28h
0x180003a75  mov     rbp, rcx
0x180003a78  mov     r13d, r8d
0x180003a7b  mov     ecx, 20h ; ' '; Size
0x180003a80  mov     rbx, rdx
0x180003a83  call    cs:__imp_malloc
0x180003a89  xor     r12d, r12d
0x180003a8c  mov     rdi, rax
0x180003a8f  test    rax, rax
0x180003a92  jnz     short loc_180003A9E
0x180003a94  mov     ebx, 8007000Eh
0x180003a99  jmp     loc_180003CF8
0x180003a9e  xorps   xmm0, xmm0
0x180003aa1  lea     rcx, [rax+8]; Time
0x180003aa5  movups  xmmword ptr [rax], xmm0
0x180003aa8  movups  xmmword ptr [rax+10h], xmm0
0x180003aac  call    cs:__imp_time
0x180003ab2  mov     ecx, 28h ; '('; Size
0x180003ab7  call    cs:__imp_malloc
0x180003abd  mov     [rdi], rax
0x180003ac0  test    rax, rax
0x180003ac3  jnz     short loc_180003ACF
0x180003ac5  mov     ebx, 8007000Eh
0x180003aca  jmp     loc_180003CF0
0x180003acf  xor     ecx, ecx
0x180003ad1  xorps   xmm0, xmm0
0x180003ad4  movups  xmmword ptr [rax], xmm0
0x180003ad7  movups  xmmword ptr [rax+10h], xmm0
0x180003adb  mov     [rax+20h], rcx
0x180003adf  mov     rcx, [rdi]
0x180003ae2  mov     eax, [rbx]
0x180003ae4  mov     [rcx], eax
0x180003ae6  mov     edx, [rbx]
0x180003ae8  mov     rcx, [rdi]
0x180003aeb  mov     eax, [rbx+8]
0x180003aee  mov     [rcx+8], eax
0x180003af1  test    edx, edx
0x180003af3  jz      loc_180003C73
0x180003af9  mov     rcx, [rbx+10h]
0x180003afd  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003b01  inc     rax
0x180003b04  cmp     [rcx+rax*2], r12w
0x180003b09  jnz     short loc_180003B01
0x180003b0b  lea     rsi, ds:2[rax*2]
0x180003b13  mov     rcx, rsi; Size
0x180003b16  call    cs:__imp_malloc
0x180003b1c  mov     rcx, rax
0x180003b1f  mov     rax, [rdi]
0x180003b22  mov     [rax+10h], rcx
0x180003b26  mov     rax, [rdi]
0x180003b29  mov     rcx, [rax+10h]; void *
0x180003b2d  test    rcx, rcx
0x180003b30  jz      short loc_180003AC5
0x180003b32  mov     rdx, [rbx+10h]; Src
0x180003b36  mov     r8, rsi; Size
0x180003b39  call    memcpy_0
0x180003b3e  mov     eax, [rbx+18h]
0x180003b41  lea     rsi, [rax+rax*2]
0x180003b45  shl     rsi, 4
0x180003b49  mov     rcx, rsi; Size
0x180003b4c  call    cs:__imp_malloc
0x180003b52  mov     rcx, rax
0x180003b55  mov     rax, [rdi]
0x180003b58  mov     [rax+20h], rcx
0x180003b5c  mov     rax, [rdi]
0x180003b5f  mov     rcx, [rax+20h]; void *
0x180003b63  test    rcx, rcx
0x180003b66  jz      loc_180003AC5
0x180003b6c  mov     rdx, [rbx+20h]; Src
0x180003b70  mov     r8, rsi; Size
0x180003b73  call    memcpy_0
0x180003b78  mov     ecx, [rbx+18h]
0x180003b7b  mov     r8d, r12d
0x180003b7e  test    ecx, ecx
0x180003b80  jz      short loc_180003BAD
0x180003b82  mov     eax, r8d
0x180003b85  inc     r8d
0x180003b88  lea     rdx, [rax+rax*2]
0x180003b8c  mov     rax, [rdi]
0x180003b8f  add     rdx, rdx
0x180003b92  mov     rcx, [rax+20h]
0x180003b96  mov     [rcx+rdx*8+24h], r12d
0x180003b9b  mov     [rcx+rdx*8+28h], r12
0x180003ba0  mov     [rcx+rdx*8+18h], r12
0x180003ba5  mov     ecx, [rbx+18h]
0x180003ba8  cmp     r8d, ecx
0x180003bab  jb      short loc_180003B82
0x180003bad  mov     rax, [rdi]
0x180003bb0  mov     r14d, r12d
0x180003bb3  mov     [rax+18h], ecx
0x180003bb6  cmp     [rbx+18h], r12d
0x180003bba  jbe     loc_180003C73
0x180003bc0  mov     eax, r14d
0x180003bc3  lea     rsi, [rax+rax*2]
0x180003bc7  mov     rax, [rdi]
0x180003bca  add     rsi, rsi
0x180003bcd  mov     r15, [rax+20h]
0x180003bd1  mov     rax, [rbx+20h]
0x180003bd5  mov     ecx, [rax+rsi*8+24h]; Size
0x180003bd9  test    ecx, ecx
0x180003bdb  jz      short loc_180003C14
0x180003bdd  call    cs:__imp_malloc
0x180003be3  mov     [r15+rsi*8+28h], rax
0x180003be8  test    rax, rax
0x180003beb  jz      loc_180003AC5
0x180003bf1  mov     rdx, [rbx+20h]
0x180003bf5  mov     rcx, rax; void *
0x180003bf8  mov     r8d, [rdx+rsi*8+24h]; Size
0x180003bfd  mov     rdx, [rdx+rsi*8+28h]; Src
0x180003c02  call    memcpy_0
0x180003c07  mov     rax, [rbx+20h]
0x180003c0b  mov     ecx, [rax+rsi*8+24h]
0x180003c0f  mov     [r15+rsi*8+24h], ecx
0x180003c14  mov     rax, [rbx+20h]
0x180003c18  mov     rcx, [rax+rsi*8+18h]
0x180003c1d  test    rcx, rcx
0x180003c20  jz      short loc_180003C66
0x180003c22  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003c26  inc     rax
0x180003c29  cmp     [rcx+rax*2], r12w
0x180003c2e  jnz     short loc_180003C26
0x180003c30  lea     r12, ds:2[rax*2]
0x180003c38  mov     rcx, r12; Size
0x180003c3b  call    cs:__imp_malloc
0x180003c41  mov     [r15+rsi*8+18h], rax
0x180003c46  test    rax, rax
0x180003c49  jz      loc_180003AC5
0x180003c4f  mov     rdx, [rbx+20h]
0x180003c53  mov     r8, r12; Size
0x180003c56  mov     rcx, rax; void *
0x180003c59  mov     rdx, [rdx+rsi*8+18h]; Src
0x180003c5e  call    memcpy_0
0x180003c63  xor     r12d, r12d
0x180003c66  inc     r14d
0x180003c69  cmp     r14d, [rbx+18h]
0x180003c6d  jb      loc_180003BC0
0x180003c73  lea     r14, [rbp+0A0h]
0x180003c7a  mov     rcx, r14; lpCriticalSection
0x180003c7d  call    cs:__imp_EnterCriticalSection
0x180003c83  cmp     [rbp+0C8h], r12d
0x180003c8a  jz      short loc_180003C93
0x180003c8c  mov     esi, 1
0x180003c91  jmp     short loc_180003CE0
0x180003c93  inc     dword ptr [rbp+0CCh]
0x180003c99  lea     rcx, [rdi+10h]
0x180003c9d  lea     rax, [rbp+78h]
0x180003ca1  mov     esi, r12d
0x180003ca4  test    r13d, r13d
0x180003ca7  jz      short loc_180003CC2
0x180003ca9  mov     rdx, [rax]
0x180003cac  cmp     [rdx+8], rax
0x180003cb0  jnz     short loc_180003CCB
0x180003cb2  mov     [rcx], rdx
0x180003cb5  mov     [rcx+8], rax
0x180003cb9  mov     [rdx+8], rcx
0x180003cbd  mov     [rax], rcx
0x180003cc0  jmp     short loc_180003CE0
0x180003cc2  mov     rdx, [rax+8]
0x180003cc6  cmp     [rdx], rax
0x180003cc9  jz      short loc_180003CD2
0x180003ccb  mov     ecx, 3
0x180003cd0  int     29h; Win8: RtlFailFast(ecx)
0x180003cd2  mov     [rcx], rax
0x180003cd5  mov     [rcx+8], rdx
0x180003cd9  mov     [rdx], rcx
0x180003cdc  mov     [rax+8], rcx
0x180003ce0  mov     rcx, r14; lpCriticalSection
0x180003ce3  mov     ebx, r12d
0x180003ce6  call    cs:__imp_LeaveCriticalSection
0x180003cec  test    esi, esi
0x180003cee  jz      short loc_180003CF8
0x180003cf0  mov     rcx, rdi; Block
0x180003cf3  call    ?FreeQueryEvent@CQuery@@SAXPEAU_QUERY_EVENT@@@Z; CQuery::FreeQueryEvent(_QUERY_EVENT *)
0x180003cf8  mov     eax, ebx
0x180003cfa  add     rsp, 28h
0x180003cfe  pop     r15
0x180003d00  pop     r14
0x180003d02  pop     r13
0x180003d04  pop     r12
0x180003d06  pop     rdi
0x180003d07  pop     rsi
0x180003d08  pop     rbp
0x180003d09  pop     rbx
0x180003d0a  retn
```
