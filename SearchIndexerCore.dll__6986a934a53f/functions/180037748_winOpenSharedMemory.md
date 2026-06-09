# winOpenSharedMemory

- ea: `0x180037748`
- end: `0x1800379bd`
- name: `winOpenSharedMemory`
- size: `629`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `broker_com_uri`

## callers

- `0x180047310`

## callees

- `0x18000a710`
- `0x18001eb90`
- `0x18001fda8`
- `0x180024640`
- `0x180035850`
- `0x180035c7c`
- `0x1800375e4`
- `0x180037748`
- `0x180037f5c`
- `0x180038d00`
- `0x180041eb0`
- `0x18004909c`
- `0x180049178`
- `0x1800496f0`
- `0x18004ae40`
- `0x180069d50`
- `0x1800766a4`
- `0x1800b0010`

## string_xrefs

- `0x180037822`: `readonly_shm`
- `0x180037935`: `winOpenShm`

## pseudocode

```c
__int64 __fastcall winOpenSharedMemory(__int64 *a1)
{
  __int64 *v2; // r14
  __int64 v3; // rbx
  __int64 v4; // rax
  __int64 v5; // rdi
  __int64 i; // rsi
  __int64 v7; // rcx
  __int64 v8; // rax
  __int64 v9; // rax
  int Boolean; // eax
  __int64 *v11; // r15
  __int16 v12; // r9
  int v13; // esi
  unsigned int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // rcx
  __int64 v17; // rcx
  __int64 v19; // rax
  __int64 v20; // rbx
  DWORD v21; // eax
  int v22; // [rsp+78h] [rbp+10h] BYREF

  v2 = (__int64 *)sqlite3MallocZero(0x18u);
  if ( !v2 )
    return 3082;
  v3 = (int)sqlite3Strlen30(a1[6]);
  v4 = sqlite3MallocZero(v3 + 177);
  v5 = v4;
  if ( !v4 )
  {
    sqlite3_free(v2);
    return 3082;
  }
  *(_QWORD *)(v4 + 8) = v4 + 160;
  sqlite3_snprintf((unsigned int)(v3 + 15), v4 + 160, "%s-shm", (const char *)a1[6]);
  sqlite3_mutex_enter(qword_1800D0DB8);
  for ( i = qword_1800D0E98; i; i = *(_QWORD *)(i + 152) )
  {
    if ( !(unsigned int)sqlite3StrICmp(*(_QWORD *)(i + 8), *(_QWORD *)(v5 + 8)) )
    {
      v15 = 0;
      sqlite3_free(v5);
LABEL_20:
      v16 = qword_1800D0DB8;
      *v2 = i;
      ++*(_DWORD *)(i + 140);
      a1[5] = (__int64)v2;
      sqlite3_mutex_leave(v16);
      sqlite3_mutex_enter(*(_QWORD *)i);
      v2[1] = *(_QWORD *)(i + 144);
      v17 = *(_QWORD *)i;
      *(_QWORD *)(i + 144) = v2;
      goto LABEL_21;
    }
  }
  *(_QWORD *)(v5 + 32) = -1;
  *(_QWORD *)(v5 + 152) = qword_1800D0E98;
  v22 = 0;
  qword_1800D0E98 = v5;
  if ( !(_BYTE)word_1800D0874 )
    goto LABEL_8;
  if ( (unsigned int)sqlite3_initialize() )
  {
    *(_QWORD *)v5 = 0;
  }
  else
  {
    v19 = ((__int64 (__fastcall *)(_QWORD))xmmword_1800D08E0)(0);
    *(_QWORD *)v5 = v19;
    if ( v19 )
    {
LABEL_8:
      v7 = a1[6];
      if ( v7 && (v8 = databaseName(v7), (v9 = uriParameter(v8, "readonly_shm")) != 0) )
        Boolean = (unsigned __int8)sqlite3GetBoolean(v9, 0);
      else
        Boolean = 0;
      v11 = a1 + 1;
      v12 = 6;
      if ( Boolean )
        v12 = 1;
      v13 = winOpen(*v11, *(_QWORD *)(v5 + 8), (__int64 **)(v5 + 16), v12, &v22);
      if ( v13 )
      {
        v20 = *(_QWORD *)(v5 + 8);
        v21 = off_1800CE078();
        v15 = winLogErrorAtLine(v13, v21, (unsigned int)"winOpenShm", v20, 50731);
      }
      else
      {
        i = v5;
        if ( v22 == 1 )
          *(_BYTE *)(v5 + 120) = 1;
        v14 = winLockSharedMemory(v5);
        v15 = v14;
        if ( !v14 || v14 == 1288 )
          goto LABEL_20;
      }
      goto LABEL_26;
    }
  }
  v15 = 3082;
  v11 = a1 + 1;
LABEL_26:
  winShmSystemLock(v5, 1, 128, 1);
  winShmPurge(*v11, 0);
  sqlite3_free(v2);
  sqlite3_free(0);
  v17 = qword_1800D0DB8;
LABEL_21:
  sqlite3_mutex_leave(v17);
  return v15;
}

```

## disassembly

```asm
0x180037748  push    rbx
0x18003774a  push    rbp
0x18003774b  push    rsi
0x18003774c  push    rdi
0x18003774d  push    r14
0x18003774f  push    r15
0x180037751  sub     rsp, 38h
0x180037755  mov     rbp, rcx
0x180037758  mov     ecx, 18h; Size
0x18003775d  call    sqlite3MallocZero
0x180037762  mov     r14, rax
0x180037765  test    rax, rax
0x180037768  jz      loc_180037986
0x18003776e  mov     rcx, [rbp+30h]
0x180037772  call    sqlite3Strlen30
0x180037777  movsxd  rbx, eax
0x18003777a  lea     rcx, [rbx+0B1h]; Size
0x180037781  call    sqlite3MallocZero
0x180037786  mov     rdi, rax
0x180037789  test    rax, rax
0x18003778c  jz      loc_18003797E
0x180037792  lea     rdx, [rax+0A0h]
0x180037799  mov     [rax+8], rdx
0x18003779d  lea     ecx, [rbx+0Fh]
0x1800377a0  mov     r9, [rbp+30h]
0x1800377a4  lea     r8, aSShm; "%s-shm"
0x1800377ab  call    sqlite3_snprintf
0x1800377b0  mov     rcx, cs:qword_1800D0DB8
0x1800377b7  call    sqlite3_mutex_enter
0x1800377bc  mov     rsi, cs:qword_1800D0E98
0x1800377c3  jmp     short loc_1800377E1
0x1800377c5  mov     rdx, [rdi+8]
0x1800377c9  mov     rcx, [rsi+8]
0x1800377cd  call    sqlite3StrICmp
0x1800377d2  test    eax, eax
0x1800377d4  jz      loc_18003789B
0x1800377da  mov     rsi, [rsi+98h]
0x1800377e1  test    rsi, rsi
0x1800377e4  jnz     short loc_1800377C5
0x1800377e6  mov     qword ptr [rdi+20h], 0FFFFFFFFFFFFFFFFh
0x1800377ee  mov     rax, cs:qword_1800D0E98
0x1800377f5  mov     [rdi+98h], rax
0x1800377fc  cmp     byte ptr cs:word_1800D0874, sil
0x180037803  mov     [rsp+68h+arg_8], esi
0x180037807  mov     cs:qword_1800D0E98, rdi
0x18003780e  jnz     loc_1800378EF
0x180037814  mov     rcx, [rbp+30h]
0x180037818  test    rcx, rcx
0x18003781b  jz      short loc_18003783A
0x18003781d  call    databaseName
0x180037822  lea     rdx, aReadonlyShm; "readonly_shm"
0x180037829  mov     rcx, rax
0x18003782c  call    uriParameter
0x180037831  test    rax, rax
0x180037834  jnz     loc_1800379A2
0x18003783a  xor     eax, eax
0x18003783c  mov     rdx, [rdi+8]
0x180037840  lea     r15, [rbp+8]
0x180037844  mov     ecx, 80001h
0x180037849  lea     r8, [rdi+10h]
0x18003784d  test    eax, eax
0x18003784f  lea     rax, [rsp+68h+arg_8]
0x180037854  mov     [rsp+68h+var_48], rax
0x180037859  lea     r9d, [rcx+5]
0x18003785d  cmovnz  r9d, ecx
0x180037861  mov     rcx, [r15]
0x180037864  call    winOpen
0x180037869  mov     esi, eax
0x18003786b  test    eax, eax
0x18003786d  jnz     loc_180037918
0x180037873  cmp     [rsp+68h+arg_8], 1
0x180037878  mov     rsi, rdi
0x18003787b  jz      loc_1800379B4
0x180037881  mov     rcx, rdi
0x180037884  call    winLockSharedMemory
0x180037889  mov     ebx, eax
0x18003788b  test    eax, eax
0x18003788d  jz      short loc_1800378A5
0x18003788f  cmp     eax, 508h
0x180037894  jz      short loc_1800378A5
0x180037896  jmp     loc_180037945
0x18003789b  xor     ebx, ebx
0x18003789d  mov     rcx, rdi
0x1800378a0  call    sqlite3_free
0x1800378a5  mov     rcx, cs:qword_1800D0DB8
0x1800378ac  mov     [r14], rsi
0x1800378af  inc     dword ptr [rsi+8Ch]
0x1800378b5  mov     [rbp+28h], r14
0x1800378b9  call    sqlite3_mutex_leave
0x1800378be  mov     rcx, [rsi]
0x1800378c1  call    sqlite3_mutex_enter
0x1800378c6  mov     rax, [rsi+90h]
0x1800378cd  mov     [r14+8], rax
0x1800378d1  mov     rcx, [rsi]
0x1800378d4  mov     [rsi+90h], r14
0x1800378db  call    sqlite3_mutex_leave
0x1800378e0  mov     eax, ebx
0x1800378e2  add     rsp, 38h
0x1800378e6  pop     r15
0x1800378e8  pop     r14
0x1800378ea  pop     rdi
0x1800378eb  pop     rsi
0x1800378ec  pop     rbp
0x1800378ed  pop     rbx
0x1800378ee  retn
0x1800378ef  call    sqlite3_initialize
0x1800378f4  test    eax, eax
0x1800378f6  jnz     loc_180037990
0x1800378fc  mov     rax, qword ptr cs:xmmword_1800D08E0
0x180037903  xor     ecx, ecx
0x180037905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003790a  mov     [rdi], rax
0x18003790d  test    rax, rax
0x180037910  jnz     loc_180037814
0x180037916  jmp     short loc_180037997
0x180037918  mov     rax, cs:off_1800CE078
0x18003791f  mov     rbx, [rdi+8]
0x180037923  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037928  mov     edx, eax
0x18003792a  mov     dword ptr [rsp+68h+var_48], 0C62Bh
0x180037932  mov     r9, rbx
0x180037935  lea     r8, aWinopenshm; "winOpenShm"
0x18003793c  mov     ecx, esi
0x18003793e  call    winLogErrorAtLine
0x180037943  mov     ebx, eax
0x180037945  mov     edx, 1
0x18003794a  mov     rcx, rdi
0x18003794d  mov     r9d, edx
0x180037950  lea     r8d, [rdx+7Fh]
0x180037954  call    winShmSystemLock
0x180037959  mov     rcx, [r15]
0x18003795c  xor     edx, edx
0x18003795e  call    winShmPurge
0x180037963  mov     rcx, r14
0x180037966  call    sqlite3_free
0x18003796b  xor     ecx, ecx
0x18003796d  call    sqlite3_free
0x180037972  mov     rcx, cs:qword_1800D0DB8
0x180037979  jmp     loc_1800378DB
0x18003797e  mov     rcx, r14
0x180037981  call    sqlite3_free
0x180037986  mov     eax, 0C0Ah
0x18003798b  jmp     loc_1800378E2
0x180037990  mov     qword ptr [rdi], 0
0x180037997  mov     ebx, 0C0Ah
0x18003799c  lea     r15, [rbp+8]
0x1800379a0  jmp     short loc_180037945
0x1800379a2  xor     edx, edx
0x1800379a4  mov     rcx, rax
0x1800379a7  call    sqlite3GetBoolean
0x1800379ac  movzx   eax, al
0x1800379af  jmp     loc_18003783C
0x1800379b4  mov     byte ptr [rdi+78h], 1
0x1800379b8  jmp     loc_180037881
```
