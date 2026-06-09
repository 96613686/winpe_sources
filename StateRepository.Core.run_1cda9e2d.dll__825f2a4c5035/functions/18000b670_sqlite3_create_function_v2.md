# sqlite3_create_function_v2

- ea: `0x18000b670`
- end: `0x18000b83c`
- name: `sqlite3_create_function_v2`
- size: `460`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: ``

## callees

- `0x18000aac0`
- `0x18000b670`
- `0x18000ba34`
- `0x18000bd90`
- `0x1800275f0`
- `0x18004d3f8`
- `0x180060134`
- `0x180064ef0`
- `0x18006779c`
- `0x18009a010`

## string_xrefs

- `0x18000b809`: `unopened`

## pseudocode

```c
__int64 __fastcall sqlite3_create_function_v2(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        void (__fastcall *a9)(__int64))
{
  _DWORD *v13; // rsi
  unsigned int Func; // r14d
  unsigned int v15; // edi
  __int64 v17; // rax
  const char *v18; // r8

  if ( !a1 )
  {
    v18 = "NULL";
    goto LABEL_22;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
      return sqlite3ReportError(21, 183135, "misuse");
    v18 = "unopened";
LABEL_22:
    sqlite3_log(21, "API call with %s database connection pointer", v18);
    return sqlite3ReportError(21, 183135, "misuse");
  }
  v13 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1800B56B0)();
  if ( !a9 )
    goto LABEL_6;
  v17 = sqlite3Malloc(24);
  v13 = (_DWORD *)v17;
  if ( v17 )
  {
    *(_DWORD *)v17 = 0;
    *(_QWORD *)(v17 + 8) = a9;
    *(_QWORD *)(v17 + 16) = a5;
LABEL_6:
    Func = sqlite3CreateFunc(a1, a2, a3, a4, a5, a6, a7, a8, 0, 0, v13);
    if ( v13 && !*v13 )
    {
      a9(a5);
      sqlite3_free(v13);
    }
    goto LABEL_7;
  }
  Func = 1;
  sqlite3OomFault(a1);
  a9(a5);
LABEL_7:
  if ( *(_BYTE *)(a1 + 103) || Func )
    v15 = apiHandleError(a1, Func);
  else
    v15 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1800B56C0)();
  return v15;
}

```

## disassembly

```asm
0x18000b670  mov     rax, rsp
0x18000b673  push    rbx
0x18000b674  push    r12
0x18000b676  push    r14
0x18000b678  push    r15
0x18000b67a  sub     rsp, 68h
0x18000b67e  mov     r14d, r9d
0x18000b681  mov     r15d, r8d
0x18000b684  mov     r12, rdx
0x18000b687  mov     rbx, rcx
0x18000b68a  test    rcx, rcx
0x18000b68d  jz      loc_18000B7F7
0x18000b693  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18000b697  jnz     loc_18000B800
0x18000b69d  mov     rcx, [rcx+18h]
0x18000b6a1  mov     [rax+8], rbp
0x18000b6a5  mov     [rax+10h], rsi
0x18000b6a9  mov     [rax+18h], rdi
0x18000b6ad  mov     [rax-28h], r13
0x18000b6b1  xor     r13d, r13d
0x18000b6b4  mov     esi, r13d
0x18000b6b7  test    rcx, rcx
0x18000b6ba  jz      short loc_18000B6C8
0x18000b6bc  mov     rax, qword ptr cs:xmmword_1800B56B0
0x18000b6c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6c8  mov     rdi, [rsp+88h+arg_40]
0x18000b6d0  mov     rbp, [rsp+88h+arg_20]
0x18000b6d8  test    rdi, rdi
0x18000b6db  jnz     loc_18000B796
0x18000b6e1  mov     rax, [rsp+88h+arg_38]
0x18000b6e9  mov     r9d, r14d
0x18000b6ec  mov     [rsp+88h+var_38], rsi
0x18000b6f1  mov     r8d, r15d
0x18000b6f4  mov     [rsp+88h+var_40], r13
0x18000b6f9  mov     rdx, r12
0x18000b6fc  mov     [rsp+88h+var_48], r13
0x18000b701  mov     rcx, rbx
0x18000b704  mov     [rsp+88h+var_50], rax
0x18000b709  mov     rax, [rsp+88h+arg_30]
0x18000b711  mov     [rsp+88h+var_58], rax
0x18000b716  mov     rax, [rsp+88h+arg_28]
0x18000b71e  mov     [rsp+88h+var_60], rax
0x18000b723  mov     [rsp+88h+var_68], rbp
0x18000b728  call    sqlite3CreateFunc
0x18000b72d  mov     r14d, eax
0x18000b730  test    rsi, rsi
0x18000b733  jnz     loc_18000B7C6
0x18000b739  mov     rsi, [rsp+88h+arg_8]
0x18000b741  mov     rbp, [rsp+88h+arg_0]
0x18000b749  cmp     [rbx+67h], r13b
0x18000b74d  jnz     short loc_18000B787
0x18000b74f  test    r14d, r14d
0x18000b752  jnz     short loc_18000B787
0x18000b754  mov     edi, r13d
0x18000b757  mov     rcx, [rbx+18h]
0x18000b75b  mov     r13, [rsp+88h+var_28]
0x18000b760  test    rcx, rcx
0x18000b763  jz      short loc_18000B771
0x18000b765  mov     rax, qword ptr cs:xmmword_1800B56C0
0x18000b76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b771  mov     eax, edi
0x18000b773  mov     rdi, [rsp+88h+arg_10]
0x18000b77b  add     rsp, 68h
0x18000b77f  pop     r15
0x18000b781  pop     r14
0x18000b783  pop     r12
0x18000b785  pop     rbx
0x18000b786  retn
0x18000b787  mov     edx, r14d
0x18000b78a  mov     rcx, rbx
0x18000b78d  call    apiHandleError
0x18000b792  mov     edi, eax
0x18000b794  jmp     short loc_18000B757
0x18000b796  mov     ecx, 18h
0x18000b79b  call    sqlite3Malloc
0x18000b7a0  mov     rsi, rax
0x18000b7a3  test    rax, rax
0x18000b7a6  jnz     short loc_18000B7E7
0x18000b7a8  mov     rcx, rbx
0x18000b7ab  mov     r14d, 1
0x18000b7b1  call    sqlite3OomFault
0x18000b7b6  mov     rcx, rbp
0x18000b7b9  mov     rax, rdi
0x18000b7bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7c1  jmp     loc_18000B739
0x18000b7c6  cmp     [rsi], r13d
0x18000b7c9  jnz     loc_18000B739
0x18000b7cf  mov     rcx, rbp
0x18000b7d2  mov     rax, rdi
0x18000b7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7da  mov     rcx, rsi
0x18000b7dd  call    sqlite3_free
0x18000b7e2  jmp     loc_18000B739
0x18000b7e7  mov     [rax], r13d
0x18000b7ea  mov     [rax+8], rdi
0x18000b7ee  mov     [rax+10h], rbp
0x18000b7f2  jmp     loc_18000B6E1
0x18000b7f7  lea     r8, aNull_1; "NULL"
0x18000b7fe  jmp     short loc_18000B810
0x18000b800  call    sqlite3SafetyCheckSickOrOk
0x18000b805  test    eax, eax
0x18000b807  jz      short loc_18000B821
0x18000b809  lea     r8, aUnopened; "unopened"
0x18000b810  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x18000b817  mov     ecx, 15h
0x18000b81c  call    sqlite3_log
0x18000b821  lea     r8, aMisuse; "misuse"
0x18000b828  mov     edx, 2CB5Fh
0x18000b82d  mov     ecx, 15h
0x18000b832  call    sqlite3ReportError
0x18000b837  jmp     loc_18000B77B
```
