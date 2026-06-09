# sqlite3_serialize

- ea: `0x18009da00`
- end: `0x18009dc62`
- name: `sqlite3_serialize`
- size: `610`
- prototype: ``
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180020a04`
- `0x180023a80`
- `0x18002619c`
- `0x1800263c0`
- `0x180026990`
- `0x180026f00`
- `0x180027060`
- `0x180028360`
- `0x1800310a0`
- `0x1800325b0`
- `0x18003f840`
- `0x180041eb0`
- `0x180047da0`
- `0x1800531c0`
- `0x180053e08`
- `0x180078968`
- `0x180088dac`
- `0x18009da00`
- `0x1800af620`

## string_xrefs

- `0x18009db8b`: `BEGIN IMMEDIATE; COMMIT;`

## pseudocode

```c
__int64 __fastcall sqlite3_serialize(__int64 a1, __int64 a2, _QWORD *a3, char a4)
{
  __int64 v4; // rsi
  __int64 v10; // r15
  int DbName; // eax
  size_t *v12; // rbx
  void *v13; // rdi
  void *v14; // rax
  __int64 v15; // r15
  size_t v16; // r13
  __int64 v17; // rbx
  int v18; // eax
  int v19; // ebp
  size_t v20; // rbp
  __int64 v21; // rbx
  __int64 v22; // rbx
  int v23; // edi
  int v24; // r12d
  __int64 v25; // r13
  int v26; // eax
  __int64 v27; // r14
  void *v28; // rcx
  _QWORD v29[11]; // [rsp+40h] [rbp-58h] BYREF

  v4 = 0;
  v29[0] = 0;
  if ( !(unsigned int)sqlite3SafetyCheckOk(a1) )
  {
    sqlite3ReportError(21, 53728, "misuse");
    return 0;
  }
  if ( !a2 )
    a2 = **(_QWORD **)(a1 + 32);
  v10 = memdbFromDbSchema(a1, a2);
  DbName = sqlite3FindDbName(a1, a2);
  if ( a3 )
    *a3 = -1;
  if ( DbName < 0 )
    return 0;
  if ( v10 )
  {
    v12 = *(size_t **)(v10 + 8);
    if ( a3 )
      *a3 = *v12;
    if ( (a4 & 1) != 0 )
      return v12[3];
    v14 = (void *)sqlite3_malloc64(*v12);
    v13 = v14;
    if ( v14 )
      memcpy_0(v14, (const void *)v12[3], *v12);
    return (__int64)v13;
  }
  else
  {
    _mm_lfence();
    v15 = *(_QWORD *)(32LL * DbName + *(_QWORD *)(a1 + 32) + 8);
    if ( !v15 )
      return 0;
    v16 = *(int *)(*(_QWORD *)(v15 + 8) + 52LL);
    v17 = sqlite3_mprintf("PRAGMA \"%w\".page_count", a2);
    if ( v17 )
    {
      v18 = sqlite3LockAndPrepare(a1, v17, -1, 128, 0, (__int64)v29, 0);
      v4 = v29[0];
      v19 = v18;
    }
    else
    {
      v19 = 7;
    }
    sqlite3_free(v17);
    if ( v19 )
      return 0;
    if ( (unsigned int)sqlite3_step(v4) != 100 )
      goto LABEL_29;
    v20 = v16;
    v21 = v16 * sqlite3_column_int64(v4, 0);
    if ( !v21 )
    {
      sqlite3_reset(v4);
      sqlite3_exec(a1, (unsigned int)"BEGIN IMMEDIATE; COMMIT;", 0, 0, 0);
      if ( (unsigned int)sqlite3_step(v4) == 100 )
        v21 = v16 * sqlite3_column_int64(v4, 0);
    }
    if ( a3 )
      *a3 = v21;
    if ( (a4 & 1) == 0 )
    {
      v22 = sqlite3_malloc64(v21);
      if ( v22 )
      {
        v23 = 1;
        v24 = sqlite3_column_int(v4, 0);
        v25 = **(_QWORD **)(v15 + 8);
        if ( v24 >= 1 )
        {
          do
          {
            v29[0] = 0;
            v26 = sqlite3PagerGet(v25, (unsigned int)v23, v29, 0);
            v27 = v29[0];
            v28 = (void *)(v22 + v20 * (v23 - 1));
            if ( v26 )
              memset_0(v28, 0, v20);
            else
              memcpy_0(v28, *(const void **)(v29[0] + 8LL), v20);
            sqlite3PagerUnref(v27);
            ++v23;
          }
          while ( v23 <= v24 );
        }
      }
    }
    else
    {
LABEL_29:
      v22 = 0;
    }
    sqlite3_finalize(v4);
    return v22;
  }
}

```

## disassembly

```asm
0x18009da00  push    rbx
0x18009da02  push    rbp
0x18009da03  push    rsi
0x18009da04  push    rdi
0x18009da05  push    r12
0x18009da07  push    r13
0x18009da09  push    r14
0x18009da0b  push    r15
0x18009da0d  sub     rsp, 58h
0x18009da11  xor     esi, esi
0x18009da13  mov     r12d, r9d
0x18009da16  mov     [rsp+98h+var_58], rsi
0x18009da1b  mov     rdi, r8
0x18009da1e  mov     rbp, rdx
0x18009da21  mov     r14, rcx
0x18009da24  call    sqlite3SafetyCheckOk
0x18009da29  test    eax, eax
0x18009da2b  jnz     short loc_18009DA54
0x18009da2d  lea     r8, aMisuse; "misuse"
0x18009da34  mov     edx, 0D1E0h
0x18009da39  lea     ecx, [rsi+15h]
0x18009da3c  call    sqlite3ReportError
0x18009da41  xor     eax, eax
0x18009da43  add     rsp, 58h
0x18009da47  pop     r15
0x18009da49  pop     r14
0x18009da4b  pop     r13
0x18009da4d  pop     r12
0x18009da4f  pop     rdi
0x18009da50  pop     rsi
0x18009da51  pop     rbp
0x18009da52  pop     rbx
0x18009da53  retn
0x18009da54  test    rbp, rbp
0x18009da57  jnz     short loc_18009DA60
0x18009da59  mov     rax, [r14+20h]
0x18009da5d  mov     rbp, [rax]
0x18009da60  mov     rdx, rbp
0x18009da63  mov     rcx, r14
0x18009da66  call    memdbFromDbSchema
0x18009da6b  mov     rdx, rbp
0x18009da6e  mov     rcx, r14
0x18009da71  mov     r15, rax
0x18009da74  call    sqlite3FindDbName
0x18009da79  test    rdi, rdi
0x18009da7c  jz      short loc_18009DA85
0x18009da7e  mov     qword ptr [rdi], 0FFFFFFFFFFFFFFFFh
0x18009da85  test    eax, eax
0x18009da87  js      short loc_18009DA41
0x18009da89  test    r15, r15
0x18009da8c  jz      short loc_18009DAD0
0x18009da8e  mov     rbx, [r15+8]
0x18009da92  test    rdi, rdi
0x18009da95  jz      short loc_18009DA9D
0x18009da97  mov     rax, [rbx]
0x18009da9a  mov     [rdi], rax
0x18009da9d  test    r12b, 1
0x18009daa1  jz      short loc_18009DAA9
0x18009daa3  mov     rdi, [rbx+18h]
0x18009daa7  jmp     short loc_18009DAC8
0x18009daa9  mov     rcx, [rbx]
0x18009daac  call    sqlite3_malloc64
0x18009dab1  mov     rdi, rax
0x18009dab4  test    rax, rax
0x18009dab7  jz      short loc_18009DAC8
0x18009dab9  mov     r8, [rbx]; Size
0x18009dabc  mov     rcx, rax; void *
0x18009dabf  mov     rdx, [rbx+18h]; Src
0x18009dac3  call    memcpy_0
0x18009dac8  mov     rax, rdi
0x18009dacb  jmp     loc_18009DA43
0x18009dad0  lfence
0x18009dad3  movsxd  rcx, eax
0x18009dad6  mov     rax, [r14+20h]
0x18009dada  shl     rcx, 5
0x18009dade  mov     r15, [rcx+rax+8]
0x18009dae3  test    r15, r15
0x18009dae6  jz      loc_18009DA41
0x18009daec  mov     rax, [r15+8]
0x18009daf0  lea     rcx, aPragmaWPageCou; "PRAGMA \"%w\".page_count"
0x18009daf7  mov     rdx, rbp
0x18009dafa  movsxd  r13, dword ptr [rax+34h]
0x18009dafe  call    sqlite3_mprintf
0x18009db03  mov     rbx, rax
0x18009db06  test    rax, rax
0x18009db09  jz      short loc_18009DB3D
0x18009db0b  lea     rax, [rsp+98h+var_58]
0x18009db10  mov     [rsp+98h+var_68], rsi
0x18009db15  mov     [rsp+98h+var_70], rax
0x18009db1a  mov     r9d, 80h
0x18009db20  or      r8d, 0FFFFFFFFh
0x18009db24  mov     [rsp+98h+var_78], rsi
0x18009db29  mov     rdx, rbx
0x18009db2c  mov     rcx, r14
0x18009db2f  call    sqlite3LockAndPrepare
0x18009db34  mov     rsi, [rsp+98h+var_58]
0x18009db39  mov     ebp, eax
0x18009db3b  jmp     short loc_18009DB42
0x18009db3d  mov     ebp, 7
0x18009db42  mov     rcx, rbx
0x18009db45  call    sqlite3_free
0x18009db4a  test    ebp, ebp
0x18009db4c  jnz     loc_18009DA41
0x18009db52  mov     rcx, rsi
0x18009db55  call    sqlite3_step
0x18009db5a  cmp     eax, 64h ; 'd'
0x18009db5d  jnz     short loc_18009DBC6
0x18009db5f  xor     edx, edx
0x18009db61  mov     rcx, rsi
0x18009db64  mov     rbp, r13
0x18009db67  call    sqlite3_column_int64
0x18009db6c  mov     rbx, rax
0x18009db6f  imul    rbx, r13
0x18009db73  test    rbx, rbx
0x18009db76  jnz     short loc_18009DBB8
0x18009db78  mov     rcx, rsi
0x18009db7b  call    sqlite3_reset
0x18009db80  xor     r9d, r9d
0x18009db83  mov     [rsp+98h+var_78], rbx
0x18009db88  xor     r8d, r8d
0x18009db8b  lea     rdx, aBeginImmediate; "BEGIN IMMEDIATE; COMMIT;"
0x18009db92  mov     rcx, r14
0x18009db95  call    sqlite3_exec
0x18009db9a  mov     rcx, rsi
0x18009db9d  call    sqlite3_step
0x18009dba2  cmp     eax, 64h ; 'd'
0x18009dba5  jnz     short loc_18009DBB8
0x18009dba7  xor     edx, edx
0x18009dba9  mov     rcx, rsi
0x18009dbac  call    sqlite3_column_int64
0x18009dbb1  mov     rbx, rax
0x18009dbb4  imul    rbx, rbp
0x18009dbb8  test    rdi, rdi
0x18009dbbb  jz      short loc_18009DBC0
0x18009dbbd  mov     [rdi], rbx
0x18009dbc0  test    r12b, 1
0x18009dbc4  jz      short loc_18009DBCD
0x18009dbc6  xor     ebx, ebx
0x18009dbc8  jmp     loc_18009DC52
0x18009dbcd  mov     rcx, rbx
0x18009dbd0  call    sqlite3_malloc64
0x18009dbd5  mov     rbx, rax
0x18009dbd8  test    rax, rax
0x18009dbdb  jz      short loc_18009DC52
0x18009dbdd  xor     edx, edx
0x18009dbdf  mov     rcx, rsi
0x18009dbe2  call    sqlite3_column_int
0x18009dbe7  mov     rcx, [r15+8]
0x18009dbeb  mov     edi, 1
0x18009dbf0  mov     r12d, eax
0x18009dbf3  mov     r13, [rcx]
0x18009dbf6  cmp     eax, edi
0x18009dbf8  jl      short loc_18009DC52
0x18009dbfa  lea     ecx, [rdi-1]
0x18009dbfd  mov     [rsp+98h+var_58], 0
0x18009dc06  movsxd  r15, ecx
0x18009dc09  lea     r8, [rsp+98h+var_58]
0x18009dc0e  imul    r15, rbp
0x18009dc12  xor     r9d, r9d
0x18009dc15  mov     edx, edi
0x18009dc17  mov     rcx, r13
0x18009dc1a  add     r15, rbx
0x18009dc1d  call    sqlite3PagerGet
0x18009dc22  mov     r14, [rsp+98h+var_58]
0x18009dc27  mov     r8, rbp; Size
0x18009dc2a  mov     rcx, r15; void *
0x18009dc2d  test    eax, eax
0x18009dc2f  jnz     short loc_18009DC3C
0x18009dc31  mov     rdx, [r14+8]; Src
0x18009dc35  call    memcpy_0
0x18009dc3a  jmp     short loc_18009DC43
0x18009dc3c  xor     edx, edx; Val
0x18009dc3e  call    memset_0
0x18009dc43  mov     rcx, r14
0x18009dc46  call    sqlite3PagerUnref
0x18009dc4b  inc     edi
0x18009dc4d  cmp     edi, r12d
0x18009dc50  jle     short loc_18009DBFA
0x18009dc52  mov     rcx, rsi
0x18009dc55  call    sqlite3_finalize
0x18009dc5a  mov     rax, rbx
0x18009dc5d  jmp     loc_18009DA43
```
