# winOpenSharedMemory

- ea: `0x180004954`
- end: `0x180004bfd`
- name: `winOpenSharedMemory`
- size: `681`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180004660`

## callees

- `0x180003e50`
- `0x180004954`
- `0x180005810`
- `0x1800061e4`
- `0x180006958`
- `0x180006aa0`
- `0x180007e64`
- `0x180009f00`
- `0x18000aac0`
- `0x18000b220`
- `0x18000bd44`
- `0x18000c250`
- `0x1800654cc`
- `0x180065f7c`
- `0x180067b40`
- `0x1800846cc`
- `0x18009a010`

## string_xrefs

- `0x180004ad7`: `readonly_shm`
- `0x180004bdf`: `winOpenShm`

## pseudocode

```c
__int64 __fastcall winOpenSharedMemory(__int64 *a1)
{
  __int64 v2; // rdx
  __int64 v3; // r8
  __int64 *v4; // r14
  __int64 v5; // rbx
  __int64 v6; // rax
  __int64 v7; // rdi
  __int64 v8; // rsi
  _BYTE *v9; // rdx
  unsigned __int8 *i; // r8
  __int64 v11; // r9
  __int64 v12; // rax
  unsigned int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  int Boolean; // eax
  __int64 *v22; // r15
  __int16 v23; // r9
  int v24; // esi
  unsigned int v25; // eax
  __int64 v26; // rbx
  DWORD v27; // eax
  int v28; // [rsp+78h] [rbp+10h] BYREF

  v4 = (__int64 *)sqlite3MallocZero(0x18u);
  if ( !v4 )
    return 3082;
  v5 = (int)sqlite3Strlen30(a1[6], v2, v3);
  v6 = sqlite3MallocZero(v5 + 177);
  v7 = v6;
  if ( !v6 )
  {
    sqlite3_free(v4);
    return 3082;
  }
  *(_QWORD *)(v6 + 8) = v6 + 160;
  sqlite3_snprintf((unsigned int)(v5 + 15), v6 + 160, "%s-shm", (const char *)a1[6]);
  sqlite3_mutex_enter(qword_1800B5B10);
  v8 = qword_1800B5BE8;
  if ( !qword_1800B5BE8 )
    goto LABEL_14;
  do
  {
    v9 = *(_BYTE **)(v8 + 8);
    for ( i = *(unsigned __int8 **)(v7 + 8); ; ++i )
    {
      v11 = (unsigned __int8)*v9;
      v12 = *i;
      if ( (_DWORD)v11 != (_DWORD)v12 )
        break;
      if ( !*v9 )
        goto LABEL_10;
LABEL_7:
      ++v9;
    }
    if ( *((unsigned __int8 *)qword_18009E760 + v11) == *((unsigned __int8 *)qword_18009E760 + v12) )
      goto LABEL_7;
    v8 = *(_QWORD *)(v8 + 152);
  }
  while ( v8 );
LABEL_10:
  if ( v8 )
  {
    v13 = 0;
    sqlite3_free(v7);
    goto LABEL_12;
  }
LABEL_14:
  *(_QWORD *)(v7 + 32) = -1;
  *(_QWORD *)(v7 + 152) = qword_1800B5BE8;
  v28 = 0;
  qword_1800B5BE8 = v7;
  if ( (_BYTE)word_1800B5634 )
  {
    if ( (unsigned int)sqlite3_initialize() )
    {
      *(_QWORD *)v7 = 0;
    }
    else
    {
      v17 = ((__int64 (__fastcall *)(_QWORD))xmmword_1800B56A0)(0);
      *(_QWORD *)v7 = v17;
      if ( v17 )
        goto LABEL_17;
    }
    v13 = 3082;
    v22 = a1 + 1;
    goto LABEL_27;
  }
LABEL_17:
  v18 = a1[6];
  if ( v18 && (v19 = databaseName(v18), (v20 = uriParameter(v19, "readonly_shm")) != 0) )
    Boolean = (unsigned __int8)sqlite3GetBoolean(v20, 0);
  else
    Boolean = 0;
  v22 = a1 + 1;
  v23 = 6;
  if ( Boolean )
    v23 = 1;
  v24 = winOpen(*v22, *(_QWORD *)(v7 + 8), v7 + 16, v23, &v28);
  if ( v24 )
  {
    v26 = *(_QWORD *)(v7 + 8);
    v27 = off_1800B3078();
    v13 = winLogErrorAtLine(v24, v27, (unsigned int)"winOpenShm", v26, 50732);
    goto LABEL_27;
  }
  v8 = v7;
  if ( v28 == 1 )
    *(_BYTE *)(v7 + 120) = 1;
  v25 = winLockSharedMemory(v7);
  v13 = v25;
  if ( !v25 || v25 == 1288 )
  {
LABEL_12:
    v14 = qword_1800B5B10;
    *v4 = v8;
    ++*(_DWORD *)(v8 + 140);
    a1[5] = (__int64)v4;
    sqlite3_mutex_leave(v14);
    sqlite3_mutex_enter(*(_QWORD *)v8);
    v4[1] = *(_QWORD *)(v8 + 144);
    v15 = *(_QWORD *)v8;
    *(_QWORD *)(v8 + 144) = v4;
  }
  else
  {
LABEL_27:
    winShmSystemLock(v7, 1, 128, 1);
    winShmPurge(*v22, 0);
    sqlite3_free(v4);
    sqlite3_free(0);
    v15 = qword_1800B5B10;
  }
  sqlite3_mutex_leave(v15);
  return v13;
}

```

## disassembly

```asm
0x180004954  push    rbx
0x180004956  push    rbp
0x180004957  push    rsi
0x180004958  push    rdi
0x180004959  push    r14
0x18000495b  push    r15
0x18000495d  sub     rsp, 38h
0x180004961  mov     rbp, rcx
0x180004964  mov     ecx, 18h; Size
0x180004969  call    sqlite3MallocZero
0x18000496e  mov     r14, rax
0x180004971  test    rax, rax
0x180004974  jz      loc_180004B94
0x18000497a  mov     rcx, [rbp+30h]
0x18000497e  call    sqlite3Strlen30
0x180004983  movsxd  rbx, eax
0x180004986  lea     rcx, [rbx+0B1h]; Size
0x18000498d  call    sqlite3MallocZero
0x180004992  mov     rdi, rax
0x180004995  test    rax, rax
0x180004998  jz      loc_180004B8C
0x18000499e  lea     rdx, [rax+0A0h]
0x1800049a5  mov     [rax+8], rdx
0x1800049a9  lea     ecx, [rbx+0Fh]
0x1800049ac  mov     r9, [rbp+30h]
0x1800049b0  lea     r8, aSShm; "%s-shm"
0x1800049b7  call    sqlite3_snprintf
0x1800049bc  mov     rcx, cs:qword_1800B5B10
0x1800049c3  call    sqlite3_mutex_enter
0x1800049c8  mov     rsi, cs:qword_1800B5BE8
0x1800049cf  test    rsi, rsi
0x1800049d2  jz      loc_180004A74
0x1800049d8  lea     r10, qword_18009E760
0x1800049df  mov     rdx, [rsi+8]
0x1800049e3  mov     r8, [rdi+8]
0x1800049e7  movzx   r9d, byte ptr [rdx]
0x1800049eb  movzx   eax, byte ptr [r8]
0x1800049ef  cmp     r9d, eax
0x1800049f2  jnz     short loc_180004A01
0x1800049f4  test    r9d, r9d
0x1800049f7  jz      short loc_180004A1B
0x1800049f9  inc     rdx
0x1800049fc  inc     r8
0x1800049ff  jmp     short loc_1800049E7
0x180004a01  movzx   ecx, byte ptr [rax+r10]
0x180004a06  movzx   eax, byte ptr [r9+r10]
0x180004a0b  cmp     eax, ecx
0x180004a0d  jz      short loc_1800049F9
0x180004a0f  mov     rsi, [rsi+98h]
0x180004a16  test    rsi, rsi
0x180004a19  jnz     short loc_1800049DF
0x180004a1b  test    rsi, rsi
0x180004a1e  jz      short loc_180004A74
0x180004a20  xor     ebx, ebx
0x180004a22  mov     rcx, rdi
0x180004a25  call    sqlite3_free
0x180004a2a  mov     rcx, cs:qword_1800B5B10
0x180004a31  mov     [r14], rsi
0x180004a34  inc     dword ptr [rsi+8Ch]
0x180004a3a  mov     [rbp+28h], r14
0x180004a3e  call    sqlite3_mutex_leave
0x180004a43  mov     rcx, [rsi]
0x180004a46  call    sqlite3_mutex_enter
0x180004a4b  mov     rax, [rsi+90h]
0x180004a52  mov     [r14+8], rax
0x180004a56  mov     rcx, [rsi]
0x180004a59  mov     [rsi+90h], r14
0x180004a60  call    sqlite3_mutex_leave
0x180004a65  mov     eax, ebx
0x180004a67  add     rsp, 38h
0x180004a6b  pop     r15
0x180004a6d  pop     r14
0x180004a6f  pop     rdi
0x180004a70  pop     rsi
0x180004a71  pop     rbp
0x180004a72  pop     rbx
0x180004a73  retn
0x180004a74  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x180004a7c  mov     rax, cs:qword_1800B5BE8
0x180004a83  mov     [rdi+98h], rax
0x180004a8a  cmp     byte ptr cs:word_1800B5634, 0
0x180004a91  mov     [rsp+68h+arg_8], 0
0x180004a99  mov     cs:qword_1800B5BE8, rdi
0x180004aa0  jz      short loc_180004AC9
0x180004aa2  call    sqlite3_initialize
0x180004aa7  test    eax, eax
0x180004aa9  jnz     loc_180004B9E
0x180004aaf  mov     rax, qword ptr cs:xmmword_1800B56A0
0x180004ab6  xor     ecx, ecx
0x180004ab8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004abd  mov     [rdi], rax
0x180004ac0  test    rax, rax
0x180004ac3  jz      loc_180004BA5
0x180004ac9  mov     rcx, [rbp+30h]
0x180004acd  test    rcx, rcx
0x180004ad0  jz      short loc_180004AEF
0x180004ad2  call    databaseName
0x180004ad7  lea     rdx, aReadonlyShm; "readonly_shm"
0x180004ade  mov     rcx, rax
0x180004ae1  call    uriParameter
0x180004ae6  test    rax, rax
0x180004ae9  jnz     loc_180004BB0
0x180004aef  xor     eax, eax
0x180004af1  mov     rdx, [rdi+8]
0x180004af5  lea     r15, [rbp+8]
0x180004af9  mov     ecx, 80001h
0x180004afe  lea     r8, [rdi+10h]
0x180004b02  test    eax, eax
0x180004b04  lea     rax, [rsp+68h+arg_8]
0x180004b09  mov     [rsp+68h+var_48], rax
0x180004b0e  lea     r9d, [rcx+5]
0x180004b12  cmovnz  r9d, ecx
0x180004b16  mov     rcx, [r15]
0x180004b19  call    winOpen
0x180004b1e  mov     esi, eax
0x180004b20  test    eax, eax
0x180004b22  jnz     loc_180004BC2
0x180004b28  cmp     [rsp+68h+arg_8], 1
0x180004b2d  mov     rsi, rdi
0x180004b30  jz      loc_180004BF4
0x180004b36  mov     rcx, rdi
0x180004b39  call    winLockSharedMemory
0x180004b3e  mov     ebx, eax
0x180004b40  test    eax, eax
0x180004b42  jz      loc_180004A2A
0x180004b48  cmp     eax, 508h
0x180004b4d  jz      loc_180004A2A
0x180004b53  mov     edx, 1
0x180004b58  mov     rcx, rdi
0x180004b5b  mov     r9d, edx
0x180004b5e  lea     r8d, [rdx+7Fh]
0x180004b62  call    winShmSystemLock
0x180004b67  mov     rcx, [r15]
0x180004b6a  xor     edx, edx
0x180004b6c  call    winShmPurge
0x180004b71  mov     rcx, r14
0x180004b74  call    sqlite3_free
0x180004b79  xor     ecx, ecx
0x180004b7b  call    sqlite3_free
0x180004b80  mov     rcx, cs:qword_1800B5B10
0x180004b87  jmp     loc_180004A60
0x180004b8c  mov     rcx, r14
0x180004b8f  call    sqlite3_free
0x180004b94  mov     eax, 0C0Ah
0x180004b99  jmp     loc_180004A67
0x180004b9e  mov     qword ptr [rdi], 0
0x180004ba5  mov     ebx, 0C0Ah
0x180004baa  lea     r15, [rbp+8]
0x180004bae  jmp     short loc_180004B53
0x180004bb0  xor     edx, edx
0x180004bb2  mov     rcx, rax
0x180004bb5  call    sqlite3GetBoolean
0x180004bba  movzx   eax, al
0x180004bbd  jmp     loc_180004AF1
0x180004bc2  mov     rax, cs:off_1800B3078
0x180004bc9  mov     rbx, [rdi+8]
0x180004bcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bd2  mov     edx, eax
0x180004bd4  mov     dword ptr [rsp+68h+var_48], 0C62Ch
0x180004bdc  mov     r9, rbx
0x180004bdf  lea     r8, aWinopenshm; "winOpenShm"
0x180004be6  mov     ecx, esi
0x180004be8  call    winLogErrorAtLine
0x180004bed  mov     ebx, eax
0x180004bef  jmp     loc_180004B53
0x180004bf4  mov     byte ptr [rdi+78h], 1
0x180004bf8  jmp     loc_180004B36
```
