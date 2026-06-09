# ParseBCryptKDFParam(uchar *,ulong,ulong *,ulong * *,uchar *,ulong,uchar *,ulong,_BCryptBufferDesc * *)

- ea: `0x18000da88`
- end: `0x18000dc89`
- name: `?ParseBCryptKDFParam@@YAJPEAEKPEAKPEAPEAK0K0KPEAPEAU_BCryptBufferDesc@@@Z`
- size: `513`
- prototype: `__int64 __fastcall(unsigned __int8 *, unsigned int, unsigned int *, unsigned int **, unsigned __int8 *, unsigned int, unsigned __int8 *, unsigned int, struct _BCryptBufferDesc **)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000d6a0`

## callees

- `0x18000d63c`
- `0x18000da88`
- `0x180010920`
- `0x18001a450`
- `0x18001a6ac`

## string_xrefs

- `0x18000daed`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`
- `0x18000dc05`: `onecore\ds\security\keyman\sidkeyprov\common\sidkeykdf.cxx`
- `0x18000dbbe`: `KDS service`

## pseudocode

```c
__int64 __fastcall ParseBCryptKDFParam(
        unsigned __int8 *a1,
        unsigned int a2,
        unsigned int *a3,
        unsigned int **a4,
        unsigned __int8 *a5,
        unsigned int a6,
        unsigned __int8 *a7,
        unsigned int a8,
        struct _BCryptBufferDesc **a9)
{
  unsigned int v9; // r12d
  unsigned int v11; // ebx
  unsigned int v12; // ebx
  unsigned int v13; // r9d
  unsigned int v14; // ecx
  struct _BCryptBufferDesc *v15; // rsi
  struct _BCryptBuffer *v16; // rax
  struct _BCryptBuffer *v17; // rdi
  unsigned int v18; // r9d
  __int64 v19; // r14
  unsigned __int8 *v20; // r15
  __int64 v21; // rbx
  unsigned __int64 v22; // rcx
  void *v23; // rax
  const wchar_t *v24; // r15
  size_t v25; // rbp
  __int64 v26; // r14
  ULONG v27; // eax
  void *v28; // rax

  v9 = 0;
  v11 = 1;
  if ( a7 )
    v11 = *((_DWORD *)a7 + 1) + 1;
  if ( a4 )
  {
    if ( !a3 || (v9 = *a3, *a3 > a2) )
    {
      v12 = -2147024809;
      v13 = 80;
      v14 = -2147024809;
LABEL_7:
      SidKeyDebugTraceError(v14, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx", v13);
      return v12;
    }
  }
  v15 = (struct _BCryptBufferDesc *)SIDKeyProvAlloc(0x10u);
  if ( !v15 )
  {
    v12 = -2147024882;
    v13 = 92;
    v14 = -2147024882;
    goto LABEL_7;
  }
  v16 = (struct _BCryptBuffer *)SIDKeyProvAlloc(16LL * v11);
  v17 = v16;
  if ( !v16 )
  {
    v18 = 99;
LABEL_20:
    v12 = -2147024882;
    SidKeyDebugTraceError(0x8007000E, "hr", "onecore\\ds\\security\\keyman\\sidkeyprov\\common\\sidkeykdf.cxx", v18);
    FreeBCryptBuffers(v15);
    return v12;
  }
  v19 = 0;
  v15->cBuffers = v11;
  v15->ulVersion = 0;
  v15->pBuffers = v16;
  if ( a7 )
  {
    v20 = a7 + 8;
    if ( *((_DWORD *)a7 + 1) )
    {
      while ( 1 )
      {
        v21 = (unsigned int)v19;
        v17[v21].BufferType = *((_DWORD *)v20 + 1);
        v22 = *(unsigned int *)v20;
        v17[v21].cbBuffer = *(_DWORD *)v20;
        v23 = SIDKeyProvAlloc(v22);
        v17[(unsigned int)v19].pvBuffer = v23;
        if ( !v23 )
          break;
        memcpy_0(v23, v20 + 8, v17[(unsigned int)v19].cbBuffer);
        v20 += v17[(unsigned int)v19].cbBuffer + 8;
        v19 = (unsigned int)(v19 + 1);
        if ( (unsigned int)v19 >= *((_DWORD *)a7 + 1) )
          goto LABEL_16;
      }
      v18 = 118;
      goto LABEL_20;
    }
  }
LABEL_16:
  v24 = (const wchar_t *)a5;
  v25 = a6;
  if ( !a5 )
  {
    v25 = 24;
    v24 = L"KDS service";
  }
  v26 = v19;
  v27 = v25 + a2 + 1;
  v17[v26].cbBuffer = v27;
  v17[v26].BufferType = 17;
  v28 = SIDKeyProvAlloc(v27);
  v17[v26].pvBuffer = v28;
  if ( !v28 )
  {
    v18 = 137;
    goto LABEL_20;
  }
  v12 = 0;
  memcpy_0(v28, v24, v25);
  memcpy_0((char *)v17[v26].pvBuffer + v25 + 1, a1, a2);
  if ( a4 )
    *a4 = (unsigned int *)((char *)v17[v26].pvBuffer + v9 + v25 + 1);
  *a9 = v15;
  return v12;
}

```

## disassembly

```asm
0x18000da88  mov     [rsp+arg_10], rbx
0x18000da8d  mov     dword ptr [rsp+Size], edx
0x18000da91  mov     [rsp+Src], rcx
0x18000da96  push    rbp
0x18000da97  push    rsi
0x18000da98  push    rdi
0x18000da99  push    r12
0x18000da9b  push    r13
0x18000da9d  push    r14
0x18000da9f  push    r15
0x18000daa1  sub     rsp, 20h
0x18000daa5  mov     rbp, [rsp+58h+arg_30]
0x18000daad  xor     r12d, r12d
0x18000dab0  mov     r13, r9
0x18000dab3  mov     eax, edx
0x18000dab5  mov     ebx, 1
0x18000daba  test    rbp, rbp
0x18000dabd  jz      short loc_18000DAC4
0x18000dabf  mov     ebx, [rbp+4]
0x18000dac2  inc     ebx
0x18000dac4  test    r13, r13
0x18000dac7  jz      short loc_18000DAFE
0x18000dac9  test    r8, r8
0x18000dacc  jz      short loc_18000DAD6
0x18000dace  mov     r12d, [r8]
0x18000dad1  cmp     r12d, eax
0x18000dad4  jbe     short loc_18000DAFE
0x18000dad6  mov     ebx, 80070057h
0x18000dadb  mov     r9d, 50h ; 'P'; unsigned int
0x18000dae1  mov     ecx, 80070057h; unsigned int
0x18000dae6  lea     rdx, aHr; "hr"
0x18000daed  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000daf4  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000daf9  jmp     loc_18000DC72
0x18000dafe  mov     ecx, 10h; unsigned __int64
0x18000db03  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000db08  mov     rsi, rax
0x18000db0b  test    rax, rax
0x18000db0e  jnz     short loc_18000DB20
0x18000db10  mov     ebx, 8007000Eh
0x18000db15  lea     r9d, [rax+5Ch]
0x18000db19  mov     ecx, 8007000Eh
0x18000db1e  jmp     short loc_18000DAE6
0x18000db20  mov     ecx, ebx
0x18000db22  shl     rcx, 4; unsigned __int64
0x18000db26  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000db2b  mov     rdi, rax
0x18000db2e  test    rax, rax
0x18000db31  jnz     short loc_18000DB3C
0x18000db33  lea     r9d, [rax+63h]
0x18000db37  jmp     loc_18000DBF9
0x18000db3c  xor     r14d, r14d
0x18000db3f  mov     [rsi+4], ebx
0x18000db42  mov     [rsi], r14d
0x18000db45  mov     [rsi+8], rdi
0x18000db49  test    rbp, rbp
0x18000db4c  jz      short loc_18000DBA4
0x18000db4e  lea     r15, [rbp+8]
0x18000db52  cmp     [rbp+4], r14d
0x18000db56  jbe     short loc_18000DBA4
0x18000db58  mov     eax, [r15+4]
0x18000db5c  mov     ebx, r14d
0x18000db5f  add     rbx, rbx
0x18000db62  mov     [rdi+rbx*8+4], eax
0x18000db66  mov     eax, [r15]
0x18000db69  mov     ecx, eax; unsigned __int64
0x18000db6b  mov     [rdi+rbx*8], eax
0x18000db6e  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000db73  mov     [rdi+rbx*8+8], rax
0x18000db78  test    rax, rax
0x18000db7b  jz      loc_18000DC20
0x18000db81  mov     r8d, [rdi+rbx*8]; Size
0x18000db85  lea     rdx, [r15+8]; Src
0x18000db89  mov     rcx, rax; void *
0x18000db8c  call    memcpy_0
0x18000db91  mov     eax, [rdi+rbx*8]
0x18000db94  add     r15, 8
0x18000db98  add     r15, rax
0x18000db9b  inc     r14d
0x18000db9e  cmp     r14d, [rbp+4]
0x18000dba2  jb      short loc_18000DB58
0x18000dba4  mov     r15, [rsp+58h+arg_20]
0x18000dbac  mov     eax, 18h
0x18000dbb1  mov     ebp, [rsp+58h+arg_28]
0x18000dbb8  test    r15, r15
0x18000dbbb  cmovz   ebp, eax
0x18000dbbe  lea     rax, aKdsService; "KDS service"
0x18000dbc5  cmovz   r15, rax
0x18000dbc9  mov     eax, dword ptr [rsp+58h+Size]
0x18000dbcd  inc     eax
0x18000dbcf  shl     r14, 4
0x18000dbd3  add     eax, ebp
0x18000dbd5  mov     ecx, eax; unsigned __int64
0x18000dbd7  mov     [r14+rdi], eax
0x18000dbdb  mov     dword ptr [r14+rdi+4], 11h
0x18000dbe4  call    ?SIDKeyProvAlloc@@YAPEAX_K@Z; SIDKeyProvAlloc(unsigned __int64)
0x18000dbe9  mov     [r14+rdi+8], rax
0x18000dbee  test    rax, rax
0x18000dbf1  jnz     short loc_18000DC28
0x18000dbf3  mov     r9d, 89h; unsigned int
0x18000dbf9  mov     ecx, 8007000Eh; unsigned int
0x18000dbfe  lea     rdx, aHr; "hr"
0x18000dc05  lea     r8, aOnecoreDsSecur_6; "onecore\\ds\\security\\keyman\\sidkeypr"...
0x18000dc0c  mov     ebx, 8007000Eh
0x18000dc11  call    ?SidKeyDebugTraceError@@YAXKPEBD0K@Z; SidKeyDebugTraceError(ulong,char const *,char const *,ulong)
0x18000dc16  mov     rcx, rsi; lpMem
0x18000dc19  call    ?FreeBCryptBuffers@@YAXPEAU_BCryptBufferDesc@@@Z; FreeBCryptBuffers(_BCryptBufferDesc *)
0x18000dc1e  jmp     short loc_18000DC72
0x18000dc20  mov     r9d, 76h ; 'v'
0x18000dc26  jmp     short loc_18000DBF9
0x18000dc28  mov     r8, rbp; Size
0x18000dc2b  mov     rdx, r15; Src
0x18000dc2e  mov     rcx, rax; void *
0x18000dc31  xor     ebx, ebx
0x18000dc33  call    memcpy_0
0x18000dc38  mov     r8d, dword ptr [rsp+58h+Size]; Size
0x18000dc3d  lea     rcx, [rbp+1]
0x18000dc41  add     rcx, [r14+rdi+8]; void *
0x18000dc46  mov     rdx, [rsp+58h+Src]; Src
0x18000dc4b  call    memcpy_0
0x18000dc50  test    r13, r13
0x18000dc53  jz      short loc_18000DC67
0x18000dc55  mov     ecx, r12d
0x18000dc58  inc     rcx
0x18000dc5b  add     rcx, [r14+rdi+8]
0x18000dc60  add     rcx, rbp
0x18000dc63  mov     [r13+0], rcx
0x18000dc67  mov     rcx, [rsp+58h+arg_40]
0x18000dc6f  mov     [rcx], rsi
0x18000dc72  mov     eax, ebx
0x18000dc74  mov     rbx, [rsp+58h+arg_10]
0x18000dc79  add     rsp, 20h
0x18000dc7d  pop     r15
0x18000dc7f  pop     r14
0x18000dc81  pop     r13
0x18000dc83  pop     r12
0x18000dc85  pop     rdi
0x18000dc86  pop     rsi
0x18000dc87  pop     rbp
0x18000dc88  retn
```
