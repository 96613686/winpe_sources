# CopyOptionStrings

- ea: `0x1800475c4`
- end: `0x1800476d3`
- name: `CopyOptionStrings`
- size: `271`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180049d44`

## callees

- `0x1800475c4`
- `0x18004f8e4`
- `0x18005f010`

## pseudocode

```c
void __fastcall CopyOptionStrings(__int64 a1, __int64 a2)
{
  __int64 (**v4)(void); // rsi
  unsigned int (__fastcall **v5)(__int64 *, _QWORD, __int64); // r14
  __int64 *v6; // r15
  unsigned __int16 v7; // ax
  __int64 v8; // r8
  int v9; // ebp
  unsigned int (__fastcall *v10)(__int64 *, _QWORD, __int64); // rax
  unsigned int v11; // ebp
  unsigned __int16 v12; // ax
  __int64 v13; // r8
  int v14; // esi
  unsigned int (__fastcall *v15)(__int64 *, _QWORD, __int64); // rax
  unsigned int v16; // esi
  __int64 v17; // [rsp+78h] [rbp+10h] BYREF

  v17 = 0;
  v4 = (__int64 (**)(void))(a1 + 336);
  v5 = (unsigned int (__fastcall **)(__int64 *, _QWORD, __int64))(a1 + 304);
  v6 = (__int64 *)(a1 + 312);
  if ( *(_QWORD *)(a2 + 40) )
  {
    v7 = (*v4)();
    v8 = *v6;
    v9 = v7;
    v10 = *v5;
    v11 = v9 + 1;
    v17 = 0;
    if ( !v10(&v17, v11, v8) )
      goto LABEL_8;
    (*(void (**)(__int64, _QWORD, const char *, ...))(a1 + 360))(v17, v11, "%s", *(_QWORD *)(a2 + 40));
    *(_QWORD *)(a1 + 8000) = v17;
  }
  if ( !*(_QWORD *)(a2 + 48) )
    return;
  v12 = (*v4)();
  v13 = *v6;
  v14 = v12;
  v15 = *v5;
  v16 = v14 + 1;
  v17 = 0;
  if ( !v15(&v17, v16, v13) )
LABEL_8:
    XCF_FatalErrorHandler((_JBTYPE *)a1, 7);
  (*(void (**)(__int64, _QWORD, const char *, ...))(a1 + 360))(v17, v16, "%s", *(_QWORD *)(a2 + 48));
  *(_QWORD *)(a1 + 8008) = v17;
}

```

## disassembly

```asm
0x1800475c4  push    rbx
0x1800475c6  push    rbp
0x1800475c7  push    rsi
0x1800475c8  push    rdi
0x1800475c9  push    r14
0x1800475cb  push    r15
0x1800475cd  sub     rsp, 38h
0x1800475d1  mov     rbx, rcx
0x1800475d4  mov     [rsp+68h+arg_8], 0
0x1800475dd  mov     rcx, [rdx+28h]
0x1800475e1  mov     rdi, rdx
0x1800475e4  lea     rsi, [rbx+150h]
0x1800475eb  lea     r14, [rbx+130h]
0x1800475f2  lea     r15, [rbx+138h]
0x1800475f9  test    rcx, rcx
0x1800475fc  jz      short loc_180047658
0x1800475fe  mov     rax, [rsi]
0x180047601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047606  mov     r8, [r15]
0x180047609  lea     rcx, [rsp+68h+arg_8]
0x18004760e  movzx   ebp, ax
0x180047611  mov     rax, [r14]
0x180047614  inc     ebp
0x180047616  mov     edx, ebp
0x180047618  mov     [rsp+68h+arg_8], 0
0x180047621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047626  test    eax, eax
0x180047628  jz      loc_1800476C5
0x18004762e  mov     r9, [rdi+28h]
0x180047632  lea     r8, aS_11; "%s"
0x180047639  mov     rcx, [rsp+68h+arg_8]
0x18004763e  mov     rax, [rbx+168h]
0x180047645  mov     edx, ebp
0x180047647  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004764c  mov     rax, [rsp+68h+arg_8]
0x180047651  mov     [rbx+1F40h], rax
0x180047658  mov     rcx, [rdi+30h]
0x18004765c  test    rcx, rcx
0x18004765f  jz      short loc_1800476B7
0x180047661  mov     rax, [rsi]
0x180047664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047669  mov     r8, [r15]
0x18004766c  lea     rcx, [rsp+68h+arg_8]
0x180047671  movzx   esi, ax
0x180047674  mov     rax, [r14]
0x180047677  inc     esi
0x180047679  mov     edx, esi
0x18004767b  mov     [rsp+68h+arg_8], 0
0x180047684  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047689  test    eax, eax
0x18004768b  jz      short loc_1800476C5
0x18004768d  mov     r9, [rdi+30h]
0x180047691  lea     r8, aS_11; "%s"
0x180047698  mov     rcx, [rsp+68h+arg_8]
0x18004769d  mov     rax, [rbx+168h]
0x1800476a4  mov     edx, esi
0x1800476a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476ab  mov     rax, [rsp+68h+arg_8]
0x1800476b0  mov     [rbx+1F48h], rax
0x1800476b7  add     rsp, 38h
0x1800476bb  pop     r15
0x1800476bd  pop     r14
0x1800476bf  pop     rdi
0x1800476c0  pop     rsi
0x1800476c1  pop     rbp
0x1800476c2  pop     rbx
0x1800476c3  retn
0x1800476c5  mov     edx, 7
0x1800476ca  mov     rcx, rbx
0x1800476cd  call    XCF_FatalErrorHandler
```
