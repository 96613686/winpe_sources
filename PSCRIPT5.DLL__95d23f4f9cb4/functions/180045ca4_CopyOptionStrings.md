# CopyOptionStrings

- ea: `0x180045ca4`
- end: `0x180045db2`
- name: `CopyOptionStrings`
- size: `270`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800484d4`

## callees

- `0x180045ca4`
- `0x18004e048`
- `0x18005d010`

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
    XCF_FatalErrorHandler(a1, 7);
  (*(void (**)(__int64, _QWORD, const char *, ...))(a1 + 360))(v17, v16, "%s", *(_QWORD *)(a2 + 48));
  *(_QWORD *)(a1 + 8008) = v17;
}

```

## disassembly

```asm
0x180045ca4  push    rbx
0x180045ca6  push    rbp
0x180045ca7  push    rsi
0x180045ca8  push    rdi
0x180045ca9  push    r14
0x180045cab  push    r15
0x180045cad  sub     rsp, 38h
0x180045cb1  mov     rbx, rcx
0x180045cb4  mov     [rsp+68h+arg_8], 0
0x180045cbd  mov     rcx, [rdx+28h]
0x180045cc1  mov     rdi, rdx
0x180045cc4  lea     rsi, [rbx+150h]
0x180045ccb  lea     r14, [rbx+130h]
0x180045cd2  lea     r15, [rbx+138h]
0x180045cd9  test    rcx, rcx
0x180045cdc  jz      short loc_180045D38
0x180045cde  mov     rax, [rsi]
0x180045ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045ce6  mov     r8, [r15]
0x180045ce9  lea     rcx, [rsp+68h+arg_8]
0x180045cee  movzx   ebp, ax
0x180045cf1  mov     rax, [r14]
0x180045cf4  inc     ebp
0x180045cf6  mov     edx, ebp
0x180045cf8  mov     [rsp+68h+arg_8], 0
0x180045d01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d06  test    eax, eax
0x180045d08  jz      loc_180045DA4
0x180045d0e  mov     r9, [rdi+28h]
0x180045d12  lea     r8, aS_11; "%s"
0x180045d19  mov     rcx, [rsp+68h+arg_8]
0x180045d1e  mov     rax, [rbx+168h]
0x180045d25  mov     edx, ebp
0x180045d27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d2c  mov     rax, [rsp+68h+arg_8]
0x180045d31  mov     [rbx+1F40h], rax
0x180045d38  mov     rcx, [rdi+30h]
0x180045d3c  test    rcx, rcx
0x180045d3f  jz      short loc_180045D97
0x180045d41  mov     rax, [rsi]
0x180045d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d49  mov     r8, [r15]
0x180045d4c  lea     rcx, [rsp+68h+arg_8]
0x180045d51  movzx   esi, ax
0x180045d54  mov     rax, [r14]
0x180045d57  inc     esi
0x180045d59  mov     edx, esi
0x180045d5b  mov     [rsp+68h+arg_8], 0
0x180045d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d69  test    eax, eax
0x180045d6b  jz      short loc_180045DA4
0x180045d6d  mov     r9, [rdi+30h]
0x180045d71  lea     r8, aS_11; "%s"
0x180045d78  mov     rcx, [rsp+68h+arg_8]
0x180045d7d  mov     rax, [rbx+168h]
0x180045d84  mov     edx, esi
0x180045d86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045d8b  mov     rax, [rsp+68h+arg_8]
0x180045d90  mov     [rbx+1F48h], rax
0x180045d97  add     rsp, 38h
0x180045d9b  pop     r15
0x180045d9d  pop     r14
0x180045d9f  pop     rdi
0x180045da0  pop     rsi
0x180045da1  pop     rbp
0x180045da2  pop     rbx
0x180045da3  retn
0x180045da4  mov     edx, 7
0x180045da9  mov     rcx, rbx
0x180045dac  call    XCF_FatalErrorHandler
```
