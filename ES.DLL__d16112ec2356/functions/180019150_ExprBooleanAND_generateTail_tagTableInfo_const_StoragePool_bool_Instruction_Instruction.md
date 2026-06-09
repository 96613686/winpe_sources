# ExprBooleanAND::generateTail(tagTableInfo const &,StoragePool &,bool,Instruction *,Instruction *)

- ea: `0x180019150`
- end: `0x180019432`
- name: `?generateTail@ExprBooleanAND@@UEAAPEAVInstruction@@AEBUtagTableInfo@@AEAVStoragePool@@_NPEAV2@3@Z`
- size: `738`
- prototype: `struct Instruction *__fastcall(ExprBooleanAND *__hidden this, const struct tagTableInfo *, struct StoragePool *, bool, struct Instruction *, struct Instruction *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x180019150`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x1800192a4`
- `msvcrt!malloc` at `0x180019332`
- `msvcrt!malloc` at `0x1800192a4`
- `msvcrt!malloc` at `0x180019332`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001928b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019319`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001928b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180019319`

## string_xrefs

- `0x180019383`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800193b0`: `com\complus\src\events\queryengine\pool.cpp`
- `0x1800193d4`: `com\complus\src\events\queryengine\pool.cpp`
- `0x180019415`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
struct Instruction *__fastcall ExprBooleanAND::generateTail(
        ExprBooleanAND *this,
        const struct tagTableInfo *a2,
        struct StoragePool *a3,
        char a4,
        struct Instruction *a5,
        struct Instruction *a6)
{
  int v6; // r13d
  _QWORD *v8; // rdi
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // r15
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // r15
  __int64 v15; // rsi
  int i; // ebx
  __int64 v17; // rdx
  unsigned __int64 v18; // rax
  struct Instruction *result; // rax
  size_t v20; // rsi
  _QWORD *v21; // r12
  __int64 v22; // rbx
  void *v23; // rax
  unsigned __int64 v24; // rax
  size_t v25; // rbp
  _QWORD *v26; // rdi
  __int64 v27; // rbx
  void *v28; // rax
  unsigned __int64 v29; // rax
  unsigned int v30; // edx
  unsigned int v31; // edx

  v6 = *((_DWORD *)this + 4);
  v8 = (_QWORD *)*((_QWORD *)this + 1);
  if ( a4 )
  {
    v8 = (_QWORD *)v8[1];
    --v6;
  }
  v10 = 40LL * v6;
  if ( !is_mul_ok(v6, 0x28u) )
    v10 = -1;
  v11 = *((_QWORD *)a3 + 1);
  v12 = v10 + 7;
  v13 = *(_QWORD *)(v11 + 16);
  v14 = v12 & 0xFFFFFFFFFFFFFFF8uLL;
  if ( v14 > v13
    || (v15 = *(_QWORD *)(v11 + 8), *(_QWORD *)(v11 + 16) = v13 - v14, *(_QWORD *)(v11 + 8) = v15 + v14, !v15) )
  {
    v20 = *(_QWORD *)a3;
    if ( v14 > *(_QWORD *)a3 )
      v20 = 2 * v14;
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
        goto LABEL_17;
      v30 = 34;
    }
    else
    {
      v21 = 0;
      v30 = 94;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v30, 0xC0001204, 0x10u);
LABEL_17:
    *(_QWORD *)a3 = v20;
    *((_QWORD *)a3 + 1) = v21;
    v24 = v21[2];
    if ( v14 > v24 )
    {
      v15 = 0;
    }
    else
    {
      v15 = v21[1];
      v21[2] = v24 - v14;
      v21[1] = v15 + v14;
      if ( v15 )
        goto LABEL_7;
    }
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
  }
LABEL_7:
  for ( i = 0; v8; ++i )
  {
    (*(void (__fastcall **)(_QWORD, const struct tagTableInfo *, struct StoragePool *, __int64))(*(_QWORD *)*v8 + 56LL))(
      *v8,
      a2,
      a3,
      v15 + 40LL * i);
    v8 = (_QWORD *)v8[1];
  }
  v17 = *((_QWORD *)a3 + 1);
  v18 = *(_QWORD *)(v17 + 16);
  if ( v18 >= 0x28 )
  {
    *(_QWORD *)(v17 + 16) = v18 - 40;
    result = *(struct Instruction **)(v17 + 8);
    *(_QWORD *)(v17 + 8) = (char *)result + 40;
    if ( result )
      goto LABEL_11;
  }
  v25 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 < 0x28u )
    v25 = 80;
  v26 = CoTaskMemAlloc(0x20u);
  if ( !v26 )
  {
    v26 = 0;
    v31 = 94;
LABEL_30:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v31, 0xC0001204, 0x10u);
    goto LABEL_24;
  }
  v27 = *((_QWORD *)a3 + 1);
  v28 = malloc(v25);
  *v26 = v28;
  v26[1] = v28;
  v26[2] = v25;
  v26[3] = v27;
  if ( !v28 )
  {
    v31 = 34;
    goto LABEL_30;
  }
LABEL_24:
  *(_QWORD *)a3 = v25;
  *((_QWORD *)a3 + 1) = v26;
  v29 = v26[2];
  if ( v29 < 0x28 || (v26[2] = v29 - 40, result = (struct Instruction *)v26[1], v26[1] = (char *)result + 40, !result) )
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    return 0;
  }
LABEL_11:
  *((_QWORD *)result + 1) = a5;
  *((_QWORD *)result + 2) = a6;
  *(_QWORD *)result = &AcceptIf::`vftable';
  *((_DWORD *)result + 6) = v6;
  *((_QWORD *)result + 4) = v15;
  return result;
}

```

## disassembly

```asm
0x180019150  push    rbx
0x180019152  push    rbp
0x180019153  push    rdi
0x180019154  push    r13
0x180019156  push    r14
0x180019158  sub     rsp, 30h
0x18001915c  mov     r13d, [rcx+10h]
0x180019160  mov     r14, r8
0x180019163  mov     rdi, [rcx+8]
0x180019167  mov     rbp, rdx
0x18001916a  mov     [rsp+58h+arg_10], r15
0x18001916f  test    r9b, r9b
0x180019172  jnz     loc_1800193F9
0x180019178  movsxd  rcx, r13d
0x18001917b  mov     eax, 28h ; '('
0x180019180  mul     rcx
0x180019183  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18001918a  mov     [rsp+58h+arg_0], rsi
0x18001918f  cmovb   rax, rcx
0x180019193  mov     rcx, [r8+8]
0x180019197  lea     r15, [rax+7]
0x18001919b  mov     rax, [rcx+10h]
0x18001919f  and     r15, 0FFFFFFFFFFFFFFF8h
0x1800191a3  cmp     r15, rax
0x1800191a6  ja      loc_180019275
0x1800191ac  mov     rsi, [rcx+8]
0x1800191b0  sub     rax, r15
0x1800191b3  mov     [rcx+10h], rax
0x1800191b7  lea     rax, [rsi+r15]
0x1800191bb  mov     [rcx+8], rax
0x1800191bf  test    rsi, rsi
0x1800191c2  jz      loc_180019275
0x1800191c8  mov     r15, [rsp+58h+arg_10]
0x1800191cd  xor     ebx, ebx
0x1800191cf  test    rdi, rdi
0x1800191d2  jz      short loc_18001920B
0x1800191d4  nop     dword ptr [rax+00h]
0x1800191d8  nop     dword ptr [rax+rax+00000000h]
0x1800191e0  mov     rcx, [rdi]
0x1800191e3  movsxd  rax, ebx
0x1800191e6  mov     r8, [rcx]
0x1800191e9  lea     rdx, [rax+rax*4]
0x1800191ed  lea     r9, [rsi+rdx*8]
0x1800191f1  mov     rdx, rbp
0x1800191f4  mov     rax, [r8+38h]
0x1800191f8  mov     r8, r14
0x1800191fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019200  mov     rdi, [rdi+8]
0x180019204  inc     ebx
0x180019206  test    rdi, rdi
0x180019209  jnz     short loc_1800191E0
0x18001920b  mov     rdx, [r14+8]
0x18001920f  mov     rax, [rdx+10h]
0x180019213  cmp     rax, 28h ; '('
0x180019217  jb      loc_180019304
0x18001921d  add     rax, 0FFFFFFFFFFFFFFD8h
0x180019221  mov     [rdx+10h], rax
0x180019225  mov     rax, [rdx+8]
0x180019229  lea     rcx, [rax+28h]
0x18001922d  mov     [rdx+8], rcx
0x180019231  test    rax, rax
0x180019234  jz      loc_180019304
0x18001923a  mov     rcx, [rsp+58h+arg_20]
0x180019242  mov     [rax+8], rcx
0x180019246  mov     rcx, [rsp+58h+arg_28]
0x18001924e  mov     [rax+10h], rcx
0x180019252  lea     rcx, ??_7AcceptIf@@6B@; const AcceptIf::`vftable'
0x180019259  mov     [rax], rcx
0x18001925c  mov     [rax+18h], r13d
0x180019260  mov     [rax+20h], rsi
0x180019264  mov     rsi, [rsp+58h+arg_0]
0x180019269  add     rsp, 30h
0x18001926d  pop     r14
0x18001926f  pop     r13
0x180019271  pop     rdi
0x180019272  pop     rbp
0x180019273  pop     rbx
0x180019274  retn
0x180019275  mov     rsi, [r8]
0x180019278  mov     [rsp+58h+arg_8], r12
0x18001927d  cmp     r15, rsi
0x180019280  ja      loc_180019405
0x180019286  mov     ecx, 20h ; ' '; cb
0x18001928b  call    cs:__imp_CoTaskMemAlloc
0x180019291  mov     r12, rax
0x180019294  test    rax, rax
0x180019297  jz      loc_1800193A2
0x18001929d  mov     rbx, [r14+8]
0x1800192a1  mov     rcx, rsi; Size
0x1800192a4  call    cs:__imp_malloc
0x1800192aa  mov     [r12], rax
0x1800192ae  mov     [r12+8], rax
0x1800192b3  mov     [r12+10h], rsi
0x1800192b8  mov     [r12+18h], rbx
0x1800192bd  test    rax, rax
0x1800192c0  jz      loc_1800193EB
0x1800192c6  mov     [r14], rsi
0x1800192c9  mov     [r14+8], r12
0x1800192cd  mov     rax, [r12+10h]
0x1800192d2  cmp     r15, rax
0x1800192d5  ja      loc_18001940E
0x1800192db  mov     rsi, [r12+8]
0x1800192e0  sub     rax, r15
0x1800192e3  mov     [r12+10h], rax
0x1800192e8  lea     rax, [rsi+r15]
0x1800192ec  mov     [r12+8], rax
0x1800192f1  test    rsi, rsi
0x1800192f4  jz      loc_180019410
0x1800192fa  mov     r12, [rsp+58h+arg_8]
0x1800192ff  jmp     loc_1800191C8
0x180019304  mov     rbp, [r14]
0x180019307  mov     eax, 50h ; 'P'
0x18001930c  cmp     rbp, 28h ; '('
0x180019310  mov     ecx, 20h ; ' '; cb
0x180019315  cmovb   rbp, rax
0x180019319  call    cs:__imp_CoTaskMemAlloc
0x18001931f  mov     rdi, rax
0x180019322  test    rax, rax
0x180019325  jz      loc_1800193C7
0x18001932b  mov     rbx, [r14+8]
0x18001932f  mov     rcx, rbp; Size
0x180019332  call    cs:__imp_malloc
0x180019338  mov     [rdi], rax
0x18001933b  mov     [rdi+8], rax
0x18001933f  mov     [rdi+10h], rbp
0x180019343  mov     [rdi+18h], rbx
0x180019347  test    rax, rax
0x18001934a  jz      loc_1800193F2
0x180019350  mov     [r14], rbp
0x180019353  mov     [r14+8], rdi
0x180019357  mov     rax, [rdi+10h]
0x18001935b  cmp     rax, 28h ; '('
0x18001935f  jb      short loc_18001937E
0x180019361  add     rax, 0FFFFFFFFFFFFFFD8h
0x180019365  mov     [rdi+10h], rax
0x180019369  mov     rax, [rdi+8]
0x18001936d  lea     rcx, [rax+28h]
0x180019371  mov     [rdi+8], rcx
0x180019375  test    rax, rax
0x180019378  jnz     loc_18001923A
0x18001937e  mov     edx, 64h ; 'd'; unsigned int
0x180019383  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001938a  mov     r9d, 10h; unsigned __int16
0x180019390  mov     r8d, 0C0001204h; unsigned int
0x180019396  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001939b  xor     eax, eax
0x18001939d  jmp     loc_180019264
0x1800193a2  xor     r12d, r12d
0x1800193a5  mov     edx, 5Eh ; '^'; unsigned int
0x1800193aa  mov     r9d, 10h; unsigned __int16
0x1800193b0  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800193b7  mov     r8d, 0C0001204h; unsigned int
0x1800193bd  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800193c2  jmp     loc_1800192C6
0x1800193c7  xor     edi, edi
0x1800193c9  mov     edx, 5Eh ; '^'; unsigned int
0x1800193ce  mov     r9d, 10h; unsigned __int16
0x1800193d4  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x1800193db  mov     r8d, 0C0001204h; unsigned int
0x1800193e1  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x1800193e6  jmp     loc_180019350
0x1800193eb  mov     edx, 22h ; '"'
0x1800193f0  jmp     short loc_1800193AA
0x1800193f2  mov     edx, 22h ; '"'
0x1800193f7  jmp     short loc_1800193CE
0x1800193f9  mov     rdi, [rdi+8]
0x1800193fd  dec     r13d
0x180019400  jmp     loc_180019178
0x180019405  lea     rsi, [r15+r15]
0x180019409  jmp     loc_180019286
0x18001940e  xor     esi, esi
0x180019410  mov     edx, 64h ; 'd'; unsigned int
0x180019415  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001941c  mov     r9d, 10h; unsigned __int16
0x180019422  mov     r8d, 0C0001204h; unsigned int
0x180019428  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001942d  jmp     loc_1800192FA
```
