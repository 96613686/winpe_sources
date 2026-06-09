# ExprComparison::generateCondition(tagTableInfo const &,StoragePool &,tagCondition &)

- ea: `0x180018a50`
- end: `0x180018d51`
- name: `?generateCondition@ExprComparison@@UEAAXAEBUtagTableInfo@@AEAVStoragePool@@AEAUtagCondition@@@Z`
- size: `769`
- prototype: `void __fastcall(ExprComparison *__hidden this, const struct tagTableInfo *, struct StoragePool *, struct tagCondition *)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180018a50`
- `0x1800434ba`

## import_xrefs

- `msvcrt!malloc` at `0x180018bca`
- `msvcrt!malloc` at `0x180018c6e`
- `msvcrt!malloc` at `0x180018bca`
- `msvcrt!malloc` at `0x180018c6e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018c53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180018c53`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018b69`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180018b69`

## string_xrefs

- `0x180018c26`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180018cbf`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180018cea`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180018d0f`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
void __fastcall ExprComparison::generateCondition(
        ExprComparison *this,
        const struct tagTableInfo *a2,
        struct StoragePool *a3,
        struct tagCondition *a4)
{
  __int64 v4; // rbp
  int v6; // edx
  int v8; // ecx
  __int64 v9; // rax
  __int64 v10; // rcx
  __int64 v11; // r15
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // r15
  char *v14; // rsi
  int v15; // ecx
  __int64 v16; // rcx
  unsigned __int64 v17; // rax
  GUID *v18; // rsi
  int v19; // ecx
  size_t v20; // r13
  _QWORD *v21; // r12
  __int64 v22; // rdi
  void *v23; // rax
  unsigned __int64 v24; // rax
  size_t v25; // r12
  _QWORD *v26; // r15
  __int64 v27; // rdi
  void *v28; // rax
  unsigned __int64 v29; // rax
  unsigned int v30; // edx
  unsigned int v31; // edx

  v4 = *((_QWORD *)this + 2);
  v6 = *((_DWORD *)this + 6);
  *(_DWORD *)a4 = *(_DWORD *)(*((_QWORD *)this + 1) + 16LL);
  *((_DWORD *)a4 + 8) = v6;
  *(_OWORD *)((char *)a4 + 8) = 0;
  *((_QWORD *)a4 + 3) = 0;
  v8 = *(_DWORD *)(v4 + 8);
  if ( !v8 )
  {
    *((_WORD *)a4 + 4) = 31;
    v9 = 2 * (*(_QWORD *)(v4 + 24) + 1LL);
    if ( !is_mul_ok(*(_QWORD *)(v4 + 24) + 1LL, 2u) )
      v9 = -1;
    v10 = *((_QWORD *)a3 + 1);
    v11 = v9 + 7;
    v12 = *(_QWORD *)(v10 + 16);
    v13 = v11 & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v13 <= v12 )
    {
      v14 = *(char **)(v10 + 8);
      *(_QWORD *)(v10 + 16) = v12 - v13;
      *(_QWORD *)(v10 + 8) = &v14[v13];
      if ( v14 )
        goto LABEL_6;
    }
    v20 = *(_QWORD *)a3;
    if ( v13 > *(_QWORD *)a3 )
      v20 = 2 * v13;
    v14 = 0;
    v21 = CoTaskMemAlloc(0x20u);
    if ( v21 )
    {
      v22 = *((_QWORD *)a3 + 1);
      v23 = malloc(v20);
      *v21 = v23;
      v21[1] = v23;
      v21[2] = v20;
      v21[3] = v22;
      if ( v23 )
      {
LABEL_19:
        *(_QWORD *)a3 = v20;
        *((_QWORD *)a3 + 1) = v21;
        v24 = v21[2];
        if ( v13 > v24 || (v14 = (char *)v21[1], v21[2] = v24 - v13, v21[1] = &v14[v13], !v14) )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
LABEL_6:
        *((_QWORD *)a4 + 2) = v14;
        memcpy_0(v14, *(const void **)(v4 + 16), 2LL * *(_QWORD *)(v4 + 24) + 2);
        return;
      }
      v30 = 34;
    }
    else
    {
      v21 = 0;
      v30 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v30, 0xC0001204, 0x10u);
    goto LABEL_19;
  }
  v15 = v8 - 1;
  if ( !v15 )
  {
    *((_WORD *)a4 + 4) = 72;
    v16 = *((_QWORD *)a3 + 1);
    v17 = *(_QWORD *)(v16 + 16);
    if ( v17 >= 0x10 )
    {
      v18 = *(GUID **)(v16 + 8);
      *(_QWORD *)(v16 + 16) = v17 - 16;
      *(_QWORD *)(v16 + 8) = v18 + 1;
      if ( v18 )
      {
LABEL_11:
        *((_QWORD *)a4 + 2) = v18;
        CLSIDFromString(*(LPCOLESTR *)(v4 + 16), v18);
        return;
      }
    }
    v25 = *(_QWORD *)a3;
    if ( *(_QWORD *)a3 < 0x10u )
      v25 = 32;
    v18 = 0;
    v26 = CoTaskMemAlloc(0x20u);
    if ( v26 )
    {
      v27 = *((_QWORD *)a3 + 1);
      v28 = malloc(v25);
      *v26 = v28;
      v26[1] = v28;
      v26[2] = v25;
      v26[3] = v27;
      if ( v28 )
      {
LABEL_26:
        *(_QWORD *)a3 = v25;
        *((_QWORD *)a3 + 1) = v26;
        v29 = v26[2];
        if ( v29 < 0x10 || (v18 = (GUID *)v26[1], v26[2] = v29 - 16, v26[1] = v18 + 1, !v18) )
          InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
        goto LABEL_11;
      }
      v31 = 34;
    }
    else
    {
      v26 = 0;
      v31 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v31, 0xC0001204, 0x10u);
    goto LABEL_26;
  }
  v19 = v15 - 1;
  if ( v19 )
  {
    if ( v19 == 1 )
    {
      *((_WORD *)a4 + 4) = 11;
      *((_WORD *)a4 + 8) = -(*(_BYTE *)(v4 + 16) != 0);
    }
  }
  else
  {
    *((_WORD *)a4 + 4) = 20;
    *((_QWORD *)a4 + 2) = *(_QWORD *)(v4 + 16);
  }
}

```

## disassembly

```asm
0x180018a50  mov     [rsp+arg_8], rbx
0x180018a55  mov     [rsp+arg_10], rbp
0x180018a5a  push    rsi
0x180018a5b  push    rdi
0x180018a5c  push    r12
0x180018a5e  push    r14
0x180018a60  push    r15
0x180018a62  sub     rsp, 20h
0x180018a66  mov     rax, [rcx+8]
0x180018a6a  xorps   xmm0, xmm0
0x180018a6d  mov     rbp, [rcx+10h]
0x180018a71  mov     rbx, r9
0x180018a74  mov     edx, [rcx+18h]
0x180018a77  mov     r14, r8
0x180018a7a  mov     ecx, [rax+10h]
0x180018a7d  xor     eax, eax
0x180018a7f  mov     [r9], ecx
0x180018a82  mov     [r9+20h], edx
0x180018a86  movups  xmmword ptr [r9+8], xmm0
0x180018a8b  mov     [r9+18h], rax
0x180018a8f  mov     ecx, [rbp+8]
0x180018a92  test    ecx, ecx
0x180018a94  jnz     loc_180018B23
0x180018a9a  mov     word ptr [r9+8], 1Fh
0x180018aa1  mov     eax, 2
0x180018aa6  mov     rcx, [rbp+18h]
0x180018aaa  inc     rcx
0x180018aad  mul     rcx
0x180018ab0  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180018ab7  cmovb   rax, rcx
0x180018abb  mov     rcx, [r8+8]
0x180018abf  lea     r15, [rax+7]
0x180018ac3  mov     rax, [rcx+10h]
0x180018ac7  and     r15, 0FFFFFFFFFFFFFFF8h
0x180018acb  cmp     r15, rax
0x180018ace  ja      loc_180018B99
0x180018ad4  mov     rsi, [rcx+8]
0x180018ad8  sub     rax, r15
0x180018adb  mov     [rcx+10h], rax
0x180018adf  lea     rax, [rsi+r15]
0x180018ae3  mov     [rcx+8], rax
0x180018ae7  test    rsi, rsi
0x180018aea  jz      loc_180018B99
0x180018af0  mov     [rbx+10h], rsi
0x180018af4  mov     rcx, rsi; void *
0x180018af7  mov     r8, [rbp+18h]
0x180018afb  mov     rdx, [rbp+10h]; Src
0x180018aff  lea     r8, ds:2[r8*2]; Size
0x180018b07  call    memcpy_0
0x180018b0c  mov     rbx, [rsp+48h+arg_8]
0x180018b11  mov     rbp, [rsp+48h+arg_10]
0x180018b16  add     rsp, 20h
0x180018b1a  pop     r15
0x180018b1c  pop     r14
0x180018b1e  pop     r12
0x180018b20  pop     rdi
0x180018b21  pop     rsi
0x180018b22  retn
0x180018b23  sub     ecx, 1
0x180018b26  jnz     short loc_180018B71
0x180018b28  mov     word ptr [r9+8], 48h ; 'H'
0x180018b2f  mov     rcx, [r8+8]
0x180018b33  mov     rax, [rcx+10h]
0x180018b37  cmp     rax, 10h
0x180018b3b  jb      loc_180018C43
0x180018b41  mov     rsi, [rcx+8]
0x180018b45  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018b49  mov     [rcx+10h], rax
0x180018b4d  lea     rax, [rsi+10h]
0x180018b51  mov     [rcx+8], rax
0x180018b55  test    rsi, rsi
0x180018b58  jz      loc_180018C43
0x180018b5e  mov     [rbx+10h], rsi
0x180018b62  mov     rdx, rsi; pclsid
0x180018b65  mov     rcx, [rbp+10h]; lpsz
0x180018b69  call    cs:__imp_CLSIDFromString
0x180018b6f  jmp     short loc_180018B0C
0x180018b71  sub     ecx, 1
0x180018b74  jz      loc_180018D34
0x180018b7a  cmp     ecx, 1
0x180018b7d  jnz     short loc_180018B0C
0x180018b7f  mov     word ptr [r9+8], 0Bh
0x180018b86  movzx   eax, byte ptr [rbp+10h]
0x180018b8a  neg     al
0x180018b8c  sbb     cx, cx
0x180018b8f  mov     [r9+10h], cx
0x180018b94  jmp     loc_180018B0C
0x180018b99  mov     [rsp+48h+arg_0], r13
0x180018b9e  mov     r13, [r8]
0x180018ba1  cmp     r15, r13
0x180018ba4  ja      loc_180018D48
0x180018baa  mov     ecx, 20h ; ' '; cb
0x180018baf  call    cs:__imp_CoTaskMemAlloc
0x180018bb5  xor     esi, esi
0x180018bb7  mov     r12, rax
0x180018bba  test    rax, rax
0x180018bbd  jz      loc_180018CDC
0x180018bc3  mov     rdi, [r14+8]
0x180018bc7  mov     rcx, r13; Size
0x180018bca  call    cs:__imp_malloc
0x180018bd0  mov     [r12], rax
0x180018bd4  mov     [r12+8], rax
0x180018bd9  mov     [r12+10h], r13
0x180018bde  mov     [r12+18h], rdi
0x180018be3  test    rax, rax
0x180018be6  jz      loc_180018D2D
0x180018bec  mov     [r14], r13
0x180018bef  mov     r13, [rsp+48h+arg_0]
0x180018bf4  mov     [r14+8], r12
0x180018bf8  mov     rax, [r12+10h]
0x180018bfd  cmp     r15, rax
0x180018c00  ja      short loc_180018C21
0x180018c02  mov     rsi, [r12+8]
0x180018c07  sub     rax, r15
0x180018c0a  mov     [r12+10h], rax
0x180018c0f  lea     rax, [rsi+r15]
0x180018c13  mov     [r12+8], rax
0x180018c18  test    rsi, rsi
0x180018c1b  jnz     loc_180018AF0
0x180018c21  mov     edx, 64h ; 'd'; unsigned int
0x180018c26  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018c2d  mov     r9d, 10h; unsigned __int16
0x180018c33  mov     r8d, 0C0001204h; unsigned int
0x180018c39  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018c3e  jmp     loc_180018AF0
0x180018c43  mov     r12, [r8]
0x180018c46  mov     ecx, 20h ; ' '; cb
0x180018c4b  cmp     r12, 10h
0x180018c4f  cmovb   r12, rcx
0x180018c53  call    cs:__imp_CoTaskMemAlloc
0x180018c59  xor     esi, esi
0x180018c5b  mov     r15, rax
0x180018c5e  test    rax, rax
0x180018c61  jz      loc_180018D01
0x180018c67  mov     rdi, [r14+8]
0x180018c6b  mov     rcx, r12; Size
0x180018c6e  call    cs:__imp_malloc
0x180018c74  mov     [r15], rax
0x180018c77  mov     [r15+8], rax
0x180018c7b  mov     [r15+10h], r12
0x180018c7f  mov     [r15+18h], rdi
0x180018c83  test    rax, rax
0x180018c86  jz      loc_180018D26
0x180018c8c  mov     [r14], r12
0x180018c8f  mov     [r14+8], r15
0x180018c93  mov     rax, [r15+10h]
0x180018c97  cmp     rax, 10h
0x180018c9b  jb      short loc_180018CBA
0x180018c9d  mov     rsi, [r15+8]
0x180018ca1  add     rax, 0FFFFFFFFFFFFFFF0h
0x180018ca5  mov     [r15+10h], rax
0x180018ca9  lea     rax, [rsi+10h]
0x180018cad  mov     [r15+8], rax
0x180018cb1  test    rsi, rsi
0x180018cb4  jnz     loc_180018B5E
0x180018cba  mov     edx, 64h ; 'd'; unsigned int
0x180018cbf  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018cc6  mov     r9d, 10h; unsigned __int16
0x180018ccc  mov     r8d, 0C0001204h; unsigned int
0x180018cd2  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018cd7  jmp     loc_180018B5E
0x180018cdc  mov     r12, rsi
0x180018cdf  mov     edx, 5Eh ; '^'; unsigned int
0x180018ce4  mov     r9d, 10h; unsigned __int16
0x180018cea  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018cf1  mov     r8d, 0C0001204h; unsigned int
0x180018cf7  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018cfc  jmp     loc_180018BEC
0x180018d01  mov     r15, rsi
0x180018d04  mov     edx, 5Eh ; '^'; unsigned int
0x180018d09  mov     r9d, 10h; unsigned __int16
0x180018d0f  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x180018d16  mov     r8d, 0C0001204h; unsigned int
0x180018d1c  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180018d21  jmp     loc_180018C8C
0x180018d26  mov     edx, 22h ; '"'
0x180018d2b  jmp     short loc_180018D09
0x180018d2d  mov     edx, 22h ; '"'
0x180018d32  jmp     short loc_180018CE4
0x180018d34  mov     word ptr [r9+8], 14h
0x180018d3b  mov     rax, [rbp+10h]
0x180018d3f  mov     [r9+10h], rax
0x180018d43  jmp     loc_180018B0C
0x180018d48  lea     r13, [r15+r15]
0x180018d4c  jmp     loc_180018BAA
```
