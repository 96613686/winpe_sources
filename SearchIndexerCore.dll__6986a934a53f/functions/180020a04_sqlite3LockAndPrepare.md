# sqlite3LockAndPrepare

- ea: `0x180020a04`
- end: `0x180020be7`
- name: `sqlite3LockAndPrepare`
- size: `483`
- prototype: ``
- caller_count: `11`
- callee_count: `9`
- tags: ``

## callers

- `0x1800209d0`
- `0x1800324e4`
- `0x1800325b0`
- `0x180064574`
- `0x18008bc50`
- `0x180093bb0`
- `0x1800976d8`
- `0x18009c220`
- `0x18009d090`
- `0x18009d140`
- `0x18009da00`

## callees

- `0x18001fe30`
- `0x1800208d0`
- `0x180020a04`
- `0x180020bf0`
- `0x1800257e0`
- `0x1800272b4`
- `0x180031ee4`
- `0x18005a044`
- `0x1800b0010`

## string_xrefs

- `0x180020b79`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3LockAndPrepare(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        unsigned int a4,
        __int64 a5,
        _QWORD *a6,
        __int64 a7)
{
  unsigned int v9; // edi
  int v10; // ebp
  _BYTE *v11; // r14
  _BYTE *v12; // rdi
  unsigned int v13; // esi
  __int64 v14; // rcx
  int v16; // r9d
  const char *v17; // r8
  int v18; // ecx

  v9 = 21;
  if ( !a6 )
  {
    v16 = 143054;
LABEL_21:
    sqlite3_log(
      21,
      "%s at line %d of [%.10s]",
      "misuse",
      v16,
      "18a3cf29885901ce73120761875ccdd0e3704e39307ee4f79d503ddacc55c7af");
    return v9;
  }
  *a6 = 0;
  if ( !a1 )
  {
    v17 = "NULL";
LABEL_24:
    sqlite3_log(21, "API call with %s database connection pointer", v17);
    goto LABEL_25;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
      goto LABEL_25;
    v17 = "unopened";
    goto LABEL_24;
  }
  if ( !a2 )
  {
LABEL_25:
    v16 = 143058;
    goto LABEL_21;
  }
  v10 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1800D08F0)();
  if ( !*(_BYTE *)(a1 + 111) )
    btreeEnterAll(a1);
  v11 = (_BYTE *)(a1 + 103);
  v12 = (_BYTE *)(a1 + 103);
  while ( 1 )
  {
    v13 = sqlite3Prepare(a1, a2, a3, a4, a5, a6, a7);
    if ( !v13 )
      break;
    v12 = (_BYTE *)(a1 + 103);
    if ( *(_BYTE *)(a1 + 103) )
      break;
    if ( v13 == 513 )
    {
      v18 = v10++;
      if ( v18 < 25 )
        continue;
    }
    if ( v13 != 17 )
      break;
    sqlite3ResetOneSchema(a1);
    if ( v10 )
      break;
    v10 = 1;
  }
  if ( *(_BYTE *)(a1 + 111) )
    v11 = v12;
  else
    btreeLeaveAll(a1);
  if ( *v11 || v13 )
    v9 = apiHandleError(a1, v13);
  else
    v9 = 0;
  v14 = *(_QWORD *)(a1 + 24);
  *(_DWORD *)(a1 + 664) = 0;
  if ( v14 )
    ((void (*)(void))xmmword_1800D0900)();
  return v9;
}

```

## disassembly

```asm
0x180020a04  mov     [rsp+arg_0], rbx
0x180020a09  mov     [rsp+arg_18], r9d
0x180020a0e  mov     [rsp+arg_10], r8d
0x180020a13  push    rbp
0x180020a14  push    rsi
0x180020a15  push    rdi
0x180020a16  push    r12
0x180020a18  push    r13
0x180020a1a  push    r14
0x180020a1c  push    r15
0x180020a1e  sub     rsp, 40h
0x180020a22  mov     r15, [rsp+78h+arg_28]
0x180020a2a  mov     r12, rdx
0x180020a2d  mov     rbx, rcx
0x180020a30  mov     edi, 15h
0x180020a35  test    r15, r15
0x180020a38  jz      loc_180020B3A
0x180020a3e  mov     qword ptr [r15], 0
0x180020a45  test    rcx, rcx
0x180020a48  jz      loc_180020B70
0x180020a4e  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x180020a52  jnz     loc_180020B96
0x180020a58  test    rdx, rdx
0x180020a5b  jz      loc_180020B8E
0x180020a61  mov     rcx, [rcx+18h]
0x180020a65  xor     ebp, ebp
0x180020a67  test    rcx, rcx
0x180020a6a  jz      short loc_180020A78
0x180020a6c  mov     rax, qword ptr cs:xmmword_1800D08F0
0x180020a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020a78  cmp     [rbx+6Fh], bpl
0x180020a7c  jz      loc_180020B2D
0x180020a82  mov     r13, [rsp+78h+arg_30]
0x180020a8a  lea     r14, [rbx+67h]
0x180020a8e  mov     rdi, r14
0x180020a91  mov     rax, [rsp+78h+arg_20]
0x180020a99  mov     rdx, r12
0x180020a9c  mov     r9d, [rsp+78h+arg_18]
0x180020aa4  mov     rcx, rbx
0x180020aa7  mov     r8d, [rsp+78h+arg_10]
0x180020aaf  mov     [rsp+78h+var_48], r13
0x180020ab4  mov     [rsp+78h+var_50], r15
0x180020ab9  mov     [rsp+78h+var_58], rax
0x180020abe  call    sqlite3Prepare
0x180020ac3  mov     esi, eax
0x180020ac5  test    eax, eax
0x180020ac7  jnz     loc_180020BA1
0x180020acd  cmp     byte ptr [rbx+6Fh], 0
0x180020ad1  jz      loc_180020B63
0x180020ad7  mov     r14, rdi
0x180020ada  cmp     byte ptr [r14], 0
0x180020ade  jnz     short loc_180020B1F
0x180020ae0  test    esi, esi
0x180020ae2  jnz     short loc_180020B1F
0x180020ae4  xor     edi, edi
0x180020ae6  mov     rcx, [rbx+18h]
0x180020aea  mov     dword ptr [rbx+298h], 0
0x180020af4  test    rcx, rcx
0x180020af7  jz      short loc_180020B05
0x180020af9  mov     rax, qword ptr cs:xmmword_1800D0900
0x180020b00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b05  mov     rbx, [rsp+78h+arg_0]
0x180020b0d  mov     eax, edi
0x180020b0f  add     rsp, 40h
0x180020b13  pop     r15
0x180020b15  pop     r14
0x180020b17  pop     r13
0x180020b19  pop     r12
0x180020b1b  pop     rdi
0x180020b1c  pop     rsi
0x180020b1d  pop     rbp
0x180020b1e  retn
0x180020b1f  mov     edx, esi
0x180020b21  mov     rcx, rbx
0x180020b24  call    apiHandleError
0x180020b29  mov     edi, eax
0x180020b2b  jmp     short loc_180020AE6
0x180020b2d  mov     rcx, rbx
0x180020b30  call    btreeEnterAll
0x180020b35  jmp     loc_180020A82
0x180020b3a  mov     r9d, 22ECEh
0x180020b40  lea     rax, a20240523134606+14h; "18a3cf29885901ce73120761875ccdd0e3704e3"...
0x180020b47  mov     ecx, edi
0x180020b49  lea     r8, aMisuse; "misuse"
0x180020b50  mov     [rsp+78h+var_58], rax
0x180020b55  lea     rdx, aSAtLineDOf10s; "%s at line %d of [%.10s]"
0x180020b5c  call    sqlite3_log
0x180020b61  jmp     short loc_180020B05
0x180020b63  mov     rcx, rbx
0x180020b66  call    btreeLeaveAll
0x180020b6b  jmp     loc_180020ADA
0x180020b70  lea     r8, aNull_1; "NULL"
0x180020b77  jmp     short loc_180020B80
0x180020b79  lea     r8, aUnopened; "unopened"
0x180020b80  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x180020b87  mov     ecx, edi
0x180020b89  call    sqlite3_log
0x180020b8e  mov     r9d, 22ED2h
0x180020b94  jmp     short loc_180020B40
0x180020b96  call    sqlite3SafetyCheckSickOrOk
0x180020b9b  test    eax, eax
0x180020b9d  jz      short loc_180020B8E
0x180020b9f  jmp     short loc_180020B79
0x180020ba1  lea     rdi, [rbx+67h]
0x180020ba5  cmp     byte ptr [rdi], 0
0x180020ba8  jnz     loc_180020ACD
0x180020bae  cmp     esi, 201h
0x180020bb4  jnz     short loc_180020BC3
0x180020bb6  mov     ecx, ebp
0x180020bb8  inc     ebp
0x180020bba  cmp     ecx, 19h
0x180020bbd  jl      loc_180020A91
0x180020bc3  cmp     esi, 11h
0x180020bc6  jnz     loc_180020ACD
0x180020bcc  or      edx, 0FFFFFFFFh
0x180020bcf  mov     rcx, rbx
0x180020bd2  call    sqlite3ResetOneSchema
0x180020bd7  test    ebp, ebp
0x180020bd9  jnz     loc_180020ACD
0x180020bdf  lea     ebp, [rsi-10h]
0x180020be2  jmp     loc_180020A91
```
