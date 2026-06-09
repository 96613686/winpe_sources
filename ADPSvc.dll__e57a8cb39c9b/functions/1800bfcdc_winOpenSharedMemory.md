# winOpenSharedMemory

- ea: `0x1800bfcdc`
- end: `0x1800bff43`
- name: `winOpenSharedMemory`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x1800c04b0`

## callees

- `0x180080cc8`
- `0x18008ed60`
- `0x1800a98a0`
- `0x1800aa5c0`
- `0x1800abbf0`
- `0x1800ae540`
- `0x1800bf3b0`
- `0x1800bf47c`
- `0x1800bf940`
- `0x1800bfcdc`
- `0x1800c07a0`
- `0x1800c08bc`
- `0x1800ca010`

## string_xrefs

- `0x1800bfe6e`: `readonly_shm`
- `0x1800bfecd`: `winOpenShm`

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
  if ( qword_18010F878 )
    ((void (*)(void))xmmword_18010EED0)();
  for ( i = qword_18010F958; ; i = *(_QWORD *)(i + 152) )
  {
    if ( !i )
    {
      *(_QWORD *)(v8 + 32) = -1;
      *(_QWORD *)(v8 + 152) = qword_18010F958;
      v21 = 0;
      qword_18010F958 = v8;
      if ( !(_BYTE)word_18010EE54 || (v10 = sqlite3_mutex_alloc(0), (*(_QWORD *)v8 = v10) != 0) )
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
          v19 = off_18010C078();
          v11 = winLogErrorAtLine(v17, v19, (unsigned int)"winOpenShm", v18, 50732);
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
      v14 = qword_18010F878;
      goto LABEL_25;
    }
    if ( !(unsigned int)sqlite3StrICmp(*(_QWORD *)(i + 8), *(_QWORD *)(v8 + 8)) )
      break;
  }
  v11 = 0;
  sqlite3_free(v8);
LABEL_20:
  v13 = qword_18010F878;
  *v2 = i;
  ++*(_DWORD *)(i + 140);
  a1[5] = v2;
  if ( v13 )
    ((void (*)(void))xmmword_18010EEE0)();
  if ( *(_QWORD *)i )
    ((void (*)(void))xmmword_18010EED0)();
  v2[1] = *(_QWORD *)(i + 144);
  v14 = *(_QWORD *)i;
  *(_QWORD *)(i + 144) = v2;
LABEL_25:
  if ( v14 )
    ((void (*)(void))xmmword_18010EEE0)();
  return v11;
}

```

## disassembly

```asm
0x1800bfcdc  push    rbx
0x1800bfcde  push    rbp
0x1800bfcdf  push    rsi
0x1800bfce0  push    rdi
0x1800bfce1  push    r14
0x1800bfce3  push    r15
0x1800bfce5  sub     rsp, 38h
0x1800bfce9  mov     rbp, rcx
0x1800bfcec  mov     ecx, 18h; Size
0x1800bfcf1  call    sqlite3MallocZero
0x1800bfcf6  mov     r14, rax
0x1800bfcf9  test    rax, rax
0x1800bfcfc  jnz     short loc_1800BFD08
0x1800bfcfe  mov     eax, 0C0Ah
0x1800bfd03  jmp     loc_1800BFE5D
0x1800bfd08  mov     rax, [rbp+30h]
0x1800bfd0c  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800bfd10  test    rax, rax
0x1800bfd13  jnz     short loc_1800BFD19
0x1800bfd15  xor     ebx, ebx
0x1800bfd17  jmp     short loc_1800BFD2B
0x1800bfd19  mov     rbx, r15
0x1800bfd1c  inc     rbx
0x1800bfd1f  cmp     byte ptr [rax+rbx], 0
0x1800bfd23  jnz     short loc_1800BFD1C
0x1800bfd25  and     ebx, 3FFFFFFFh
0x1800bfd2b  mov     ecx, ebx
0x1800bfd2d  add     rcx, 0B1h; Size
0x1800bfd34  call    sqlite3MallocZero
0x1800bfd39  mov     rsi, rax
0x1800bfd3c  test    rax, rax
0x1800bfd3f  jnz     short loc_1800BFD4B
0x1800bfd41  mov     rcx, r14
0x1800bfd44  call    sqlite3_free
0x1800bfd49  jmp     short loc_1800BFCFE
0x1800bfd4b  lea     rdx, [rax+0A0h]
0x1800bfd52  mov     [rax+8], rdx
0x1800bfd56  lea     ecx, [rbx+0Fh]
0x1800bfd59  mov     r9, [rbp+30h]
0x1800bfd5d  lea     r8, aSShm; "%s-shm"
0x1800bfd64  call    sqlite3_snprintf
0x1800bfd69  mov     rcx, cs:qword_18010F878
0x1800bfd70  test    rcx, rcx
0x1800bfd73  jz      short loc_1800BFD81
0x1800bfd75  mov     rax, qword ptr cs:xmmword_18010EED0
0x1800bfd7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfd81  mov     rdi, cs:qword_18010F958
0x1800bfd88  jmp     short loc_1800BFDA2
0x1800bfd8a  mov     rdx, [rsi+8]
0x1800bfd8e  mov     rcx, [rdi+8]
0x1800bfd92  call    sqlite3StrICmp
0x1800bfd97  test    eax, eax
0x1800bfd99  jz      short loc_1800BFDF2
0x1800bfd9b  mov     rdi, [rdi+98h]
0x1800bfda2  test    rdi, rdi
0x1800bfda5  jnz     short loc_1800BFD8A
0x1800bfda7  mov     [rsi+20h], r15
0x1800bfdab  mov     rax, cs:qword_18010F958
0x1800bfdb2  mov     [rsi+98h], rax
0x1800bfdb9  cmp     byte ptr cs:word_18010EE54, dil
0x1800bfdc0  mov     [rsp+68h+arg_8], edi
0x1800bfdc4  mov     cs:qword_18010F958, rsi
0x1800bfdcb  jz      loc_1800BFE6A
0x1800bfdd1  xor     ecx, ecx
0x1800bfdd3  call    sqlite3_mutex_alloc
0x1800bfdd8  mov     [rsi], rax
0x1800bfddb  test    rax, rax
0x1800bfdde  jnz     loc_1800BFE6A
0x1800bfde4  mov     ebx, 0C0Ah
0x1800bfde9  lea     r15, [rbp+8]
0x1800bfded  jmp     loc_1800BFF0A
0x1800bfdf2  xor     ebx, ebx
0x1800bfdf4  mov     rcx, rsi
0x1800bfdf7  call    sqlite3_free
0x1800bfdfc  mov     rcx, cs:qword_18010F878
0x1800bfe03  mov     [r14], rdi
0x1800bfe06  inc     dword ptr [rdi+8Ch]
0x1800bfe0c  mov     [rbp+28h], r14
0x1800bfe10  test    rcx, rcx
0x1800bfe13  jz      short loc_1800BFE21
0x1800bfe15  mov     rax, qword ptr cs:xmmword_18010EEE0
0x1800bfe1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe21  mov     rcx, [rdi]
0x1800bfe24  test    rcx, rcx
0x1800bfe27  jz      short loc_1800BFE35
0x1800bfe29  mov     rax, qword ptr cs:xmmword_18010EED0
0x1800bfe30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe35  mov     rax, [rdi+90h]
0x1800bfe3c  mov     [r14+8], rax
0x1800bfe40  mov     rcx, [rdi]
0x1800bfe43  mov     [rdi+90h], r14
0x1800bfe4a  test    rcx, rcx
0x1800bfe4d  jz      short loc_1800BFE5B
0x1800bfe4f  mov     rax, qword ptr cs:xmmword_18010EEE0
0x1800bfe56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfe5b  mov     eax, ebx
0x1800bfe5d  add     rsp, 38h
0x1800bfe61  pop     r15
0x1800bfe63  pop     r14
0x1800bfe65  pop     rdi
0x1800bfe66  pop     rsi
0x1800bfe67  pop     rbp
0x1800bfe68  pop     rbx
0x1800bfe69  retn
0x1800bfe6a  mov     rcx, [rbp+30h]
0x1800bfe6e  lea     rdx, aReadonlyShm; "readonly_shm"
0x1800bfe75  xor     r8d, r8d
0x1800bfe78  call    sqlite3_uri_boolean
0x1800bfe7d  mov     rdx, [rsi+8]
0x1800bfe81  lea     r15, [rbp+8]
0x1800bfe85  mov     ecx, 80001h
0x1800bfe8a  lea     r8, [rsi+10h]
0x1800bfe8e  test    eax, eax
0x1800bfe90  lea     rax, [rsp+68h+arg_8]
0x1800bfe95  mov     [rsp+68h+var_48], rax
0x1800bfe9a  lea     r9d, [rcx+5]
0x1800bfe9e  cmovnz  r9d, ecx
0x1800bfea2  mov     rcx, [r15]
0x1800bfea5  call    winOpen
0x1800bfeaa  mov     edi, eax
0x1800bfeac  test    eax, eax
0x1800bfeae  jz      short loc_1800BFEDF
0x1800bfeb0  mov     rax, cs:off_18010C078
0x1800bfeb7  mov     rbx, [rsi+8]
0x1800bfebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bfec0  mov     edx, eax
0x1800bfec2  mov     dword ptr [rsp+68h+var_48], 0C62Ch
0x1800bfeca  mov     r9, rbx
0x1800bfecd  lea     r8, aWinopenshm; "winOpenShm"
0x1800bfed4  mov     ecx, edi
0x1800bfed6  call    winLogErrorAtLine
0x1800bfedb  mov     ebx, eax
0x1800bfedd  jmp     short loc_1800BFF0A
0x1800bfedf  cmp     [rsp+68h+arg_8], 1
0x1800bfee4  mov     rdi, rsi
0x1800bfee7  jnz     short loc_1800BFEED
0x1800bfee9  mov     byte ptr [rsi+78h], 1
0x1800bfeed  mov     rcx, rsi
0x1800bfef0  call    winLockSharedMemory
0x1800bfef5  mov     ebx, eax
0x1800bfef7  test    eax, eax
0x1800bfef9  jz      loc_1800BFDFC
0x1800bfeff  cmp     eax, 508h
0x1800bff04  jz      loc_1800BFDFC
0x1800bff0a  mov     edx, 1
0x1800bff0f  mov     rcx, rsi
0x1800bff12  mov     r9d, edx
0x1800bff15  lea     r8d, [rdx+7Fh]
0x1800bff19  call    winShmSystemLock
0x1800bff1e  mov     rcx, [r15]
0x1800bff21  xor     edx, edx
0x1800bff23  call    winShmPurge
0x1800bff28  mov     rcx, r14
0x1800bff2b  call    sqlite3_free
0x1800bff30  xor     ecx, ecx
0x1800bff32  call    sqlite3_free
0x1800bff37  mov     rcx, cs:qword_18010F878
0x1800bff3e  jmp     loc_1800BFE4A
```
