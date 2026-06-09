# ExprComparison::InsertAsORChild(ExprBooleanOR &,StoragePool &)

- ea: `0x18001e150`
- end: `0x18001e31d`
- name: `?InsertAsORChild@ExprComparison@@UEAAXAEAVExprBooleanOR@@AEAVStoragePool@@@Z`
- size: `461`
- prototype: `void __fastcall(ExprComparison *__hidden this, struct ExprBooleanOR *, struct StoragePool *)`
- caller_count: `0`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callees

- `0x180003d54`
- `0x18001e150`
- `0x180046010`

## import_xrefs

- `msvcrt!malloc` at `0x18001e24e`
- `msvcrt!malloc` at `0x18001e24e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e239`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001e239`

## string_xrefs

- `0x18001e2a0`: `com\complus\src\events\queryengine\pool.cpp`
- `0x18001e2cd`: `com\complus\src\events\queryengine\pool.cpp`

## pseudocode

```c
void __fastcall ExprComparison::InsertAsORChild(ExprComparison *this, struct ExprBooleanOR *a2, struct StoragePool *a3)
{
  __int64 v5; // rcx
  int v7; // ebp
  unsigned __int64 v8; // rax
  __int64 v9; // rbx
  __int64 v10; // rax
  __int64 v11; // r15
  _QWORD *v12; // r14
  _QWORD *i; // rsi
  size_t v14; // r12
  _QWORD *v15; // r15
  __int64 v16; // rbx
  void *v17; // rax
  unsigned __int64 v18; // rax
  unsigned int v19; // edx

  v5 = *((_QWORD *)a3 + 1);
  v7 = 1;
  v8 = *(_QWORD *)(v5 + 16);
  if ( v8 >= 0x18 )
  {
    v9 = *(_QWORD *)(v5 + 8);
    *(_QWORD *)(v5 + 16) = v8 - 24;
    *(_QWORD *)(v5 + 8) = v9 + 24;
    if ( v9 )
      goto LABEL_3;
  }
  v14 = *(_QWORD *)a3;
  if ( *(_QWORD *)a3 < 0x18u )
    v14 = 48;
  v15 = CoTaskMemAlloc(0x20u);
  if ( !v15 )
  {
    v15 = 0;
    v19 = 94;
LABEL_23:
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", v19, 0xC0001204, 0x10u);
    goto LABEL_19;
  }
  v16 = *((_QWORD *)a3 + 1);
  v17 = malloc(v14);
  *v15 = v17;
  v15[1] = v17;
  v15[2] = v14;
  v15[3] = v16;
  if ( !v17 )
  {
    v19 = 34;
    goto LABEL_23;
  }
LABEL_19:
  *(_QWORD *)a3 = v14;
  *((_QWORD *)a3 + 1) = v15;
  v18 = v15[2];
  if ( v18 < 0x18 || (v9 = v15[1], v15[2] = v18 - 24, v15[1] = v9 + 24, !v9) )
  {
    InternalError(L"com\\complus\\src\\events\\queryengine\\pool.cpp", 0x64u, 0xC0001204, 0x10u);
    v9 = 0;
    goto LABEL_4;
  }
LABEL_3:
  *(_QWORD *)v9 = this;
  *(_DWORD *)(v9 + 8) = 1;
  *(_QWORD *)(v9 + 16) = 0;
LABEL_4:
  if ( *((_DWORD *)this + 6) != 1 || *(_DWORD *)(*((_QWORD *)this + 1) + 16LL) )
  {
    *(_QWORD *)(v9 + 16) = *((_QWORD *)a2 + 1);
    v10 = *((_QWORD *)a2 + 1);
    if ( v10 )
      v7 = *(_DWORD *)(v10 + 8) + 1;
    *(_DWORD *)(v9 + 8) = v7;
    *((_BYTE *)a2 + 16) = 0;
LABEL_9:
    *((_QWORD *)a2 + 1) = v9;
    return;
  }
  v11 = *((_QWORD *)this + 2);
  v12 = 0;
  for ( i = (_QWORD *)*((_QWORD *)a2 + 1); i; i = (_QWORD *)i[2] )
  {
    if ( (*(unsigned __int8 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*i + 64LL))(*i, v11) )
      break;
    v12 = i;
  }
  *(_QWORD *)(v9 + 16) = i;
  if ( i )
    v7 = *((_DWORD *)i + 2) + 1;
  *(_DWORD *)(v9 + 8) = v7;
  if ( !v12 )
    goto LABEL_9;
  v12[2] = v9;
}

```

## disassembly

```asm
0x18001e150  push    rbx
0x18001e152  push    rbp
0x18001e153  push    rsi
0x18001e154  push    rdi
0x18001e155  push    r14
0x18001e157  push    r15
0x18001e159  sub     rsp, 28h
0x18001e15d  mov     rsi, rcx
0x18001e160  mov     r14, r8
0x18001e163  mov     rcx, [r8+8]
0x18001e167  mov     rdi, rdx
0x18001e16a  mov     ebp, 1
0x18001e16f  mov     rax, [rcx+10h]
0x18001e173  cmp     rax, 18h
0x18001e177  jb      loc_18001E21F
0x18001e17d  mov     rbx, [rcx+8]
0x18001e181  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001e185  mov     [rcx+10h], rax
0x18001e189  lea     rax, [rbx+18h]
0x18001e18d  mov     [rcx+8], rax
0x18001e191  test    rbx, rbx
0x18001e194  jz      loc_18001E21F
0x18001e19a  mov     [rbx], rsi
0x18001e19d  mov     [rbx+8], ebp
0x18001e1a0  mov     qword ptr [rbx+10h], 0
0x18001e1a8  cmp     [rsi+18h], ebp
0x18001e1ab  jnz     short loc_18001E1B7
0x18001e1ad  mov     rax, [rsi+8]
0x18001e1b1  cmp     dword ptr [rax+10h], 0
0x18001e1b5  jz      short loc_18001E1E5
0x18001e1b7  mov     rax, [rdi+8]
0x18001e1bb  mov     [rbx+10h], rax
0x18001e1bf  mov     rax, [rdi+8]
0x18001e1c3  test    rax, rax
0x18001e1c6  jz      short loc_18001E1CD
0x18001e1c8  mov     ebp, [rax+8]
0x18001e1cb  inc     ebp
0x18001e1cd  mov     [rbx+8], ebp
0x18001e1d0  mov     byte ptr [rdi+10h], 0
0x18001e1d4  mov     [rdi+8], rbx
0x18001e1d8  add     rsp, 28h
0x18001e1dc  pop     r15
0x18001e1de  pop     r14
0x18001e1e0  pop     rdi
0x18001e1e1  pop     rsi
0x18001e1e2  pop     rbp
0x18001e1e3  pop     rbx
0x18001e1e4  retn
0x18001e1e5  mov     r15, [rsi+10h]
0x18001e1e9  xor     r14d, r14d
0x18001e1ec  mov     rsi, [rdi+8]
0x18001e1f0  test    rsi, rsi
0x18001e1f3  jnz     loc_18001E2E8
0x18001e1f9  mov     [rbx+10h], rsi
0x18001e1fd  test    rsi, rsi
0x18001e200  jnz     loc_18001E313
0x18001e206  mov     [rbx+8], ebp
0x18001e209  test    r14, r14
0x18001e20c  jz      short loc_18001E1D4
0x18001e20e  mov     [r14+10h], rbx
0x18001e212  add     rsp, 28h
0x18001e216  pop     r15
0x18001e218  pop     r14
0x18001e21a  pop     rdi
0x18001e21b  pop     rsi
0x18001e21c  pop     rbp
0x18001e21d  pop     rbx
0x18001e21e  retn
0x18001e21f  mov     [rsp+58h+arg_0], r12
0x18001e224  mov     eax, 30h ; '0'
0x18001e229  mov     r12, [r8]
0x18001e22c  mov     ecx, 20h ; ' '; cb
0x18001e231  cmp     r12, 18h
0x18001e235  cmovb   r12, rax
0x18001e239  call    cs:__imp_CoTaskMemAlloc
0x18001e23f  mov     r15, rax
0x18001e242  test    rax, rax
0x18001e245  jz      short loc_18001E2BF
0x18001e247  mov     rbx, [r14+8]
0x18001e24b  mov     rcx, r12; Size
0x18001e24e  call    cs:__imp_malloc
0x18001e254  mov     [r15], rax
0x18001e257  mov     [r15+8], rax
0x18001e25b  mov     [r15+10h], r12
0x18001e25f  mov     [r15+18h], rbx
0x18001e263  test    rax, rax
0x18001e266  jz      short loc_18001E2E1
0x18001e268  mov     [r14], r12
0x18001e26b  mov     r12, [rsp+58h+arg_0]
0x18001e270  mov     [r14+8], r15
0x18001e274  mov     rax, [r15+10h]
0x18001e278  cmp     rax, 18h
0x18001e27c  jb      short loc_18001E29B
0x18001e27e  mov     rbx, [r15+8]
0x18001e282  add     rax, 0FFFFFFFFFFFFFFE8h
0x18001e286  mov     [r15+10h], rax
0x18001e28a  lea     rax, [rbx+18h]
0x18001e28e  mov     [r15+8], rax
0x18001e292  test    rbx, rbx
0x18001e295  jnz     loc_18001E19A
0x18001e29b  mov     edx, 64h ; 'd'; unsigned int
0x18001e2a0  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001e2a7  mov     r9d, 10h; unsigned __int16
0x18001e2ad  mov     r8d, 0C0001204h; unsigned int
0x18001e2b3  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001e2b8  xor     ebx, ebx
0x18001e2ba  jmp     loc_18001E1A8
0x18001e2bf  xor     r15d, r15d
0x18001e2c2  mov     edx, 5Eh ; '^'; unsigned int
0x18001e2c7  mov     r9d, 10h; unsigned __int16
0x18001e2cd  lea     rcx, aComComplusSrcE_19; "com\\complus\\src\\events\\queryengine"...
0x18001e2d4  mov     r8d, 0C0001204h; unsigned int
0x18001e2da  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18001e2df  jmp     short loc_18001E268
0x18001e2e1  mov     edx, 22h ; '"'
0x18001e2e6  jmp     short loc_18001E2C7
0x18001e2e8  mov     rcx, [rsi]
0x18001e2eb  mov     rdx, r15
0x18001e2ee  mov     rax, [rcx]
0x18001e2f1  mov     rax, [rax+40h]
0x18001e2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e2fa  test    al, al
0x18001e2fc  jnz     loc_18001E1F9
0x18001e302  mov     r14, rsi
0x18001e305  mov     rsi, [rsi+10h]
0x18001e309  test    rsi, rsi
0x18001e30c  jnz     short loc_18001E2E8
0x18001e30e  jmp     loc_18001E1F9
0x18001e313  mov     ebp, [rsi+8]
0x18001e316  inc     ebp
0x18001e318  jmp     loc_18001E206
```
