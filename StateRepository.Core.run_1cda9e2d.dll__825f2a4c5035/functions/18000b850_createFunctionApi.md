# createFunctionApi

- ea: `0x18000b850`
- end: `0x18000ba2b`
- name: `createFunctionApi`
- size: `475`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180001010`
- `0x18008da60`
- `0x18008dc30`

## callees

- `0x18000aac0`
- `0x18000b850`
- `0x18000ba34`
- `0x18000bd90`
- `0x1800275f0`
- `0x18004d3f8`
- `0x180060134`
- `0x180064ef0`
- `0x18006779c`
- `0x18009a010`

## string_xrefs

- `0x18000b9f8`: `unopened`

## pseudocode

```c
__int64 __fastcall createFunctionApi(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        void (__fastcall *a11)(__int64))
{
  _DWORD *v15; // rsi
  unsigned int Func; // r14d
  unsigned int v17; // edi
  __int64 v19; // rax
  const char *v20; // r8

  if ( !a1 )
  {
    v20 = "NULL";
    goto LABEL_22;
  }
  if ( *(_BYTE *)(a1 + 113) != 118 )
  {
    if ( !(unsigned int)sqlite3SafetyCheckSickOrOk() )
      return sqlite3ReportError(21, 183135, "misuse");
    v20 = "unopened";
LABEL_22:
    sqlite3_log(21, "API call with %s database connection pointer", v20);
    return sqlite3ReportError(21, 183135, "misuse");
  }
  v15 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1800B56B0)();
  if ( !a11 )
    goto LABEL_6;
  v19 = sqlite3Malloc(24);
  v15 = (_DWORD *)v19;
  if ( v19 )
  {
    *(_DWORD *)v19 = 0;
    *(_QWORD *)(v19 + 8) = a11;
    *(_QWORD *)(v19 + 16) = a5;
LABEL_6:
    Func = sqlite3CreateFunc(a1, a2, a3, a4, a5, a6, a7, a8, a9, a10, v15);
    if ( v15 && !*v15 )
    {
      a11(a5);
      sqlite3_free(v15);
    }
    goto LABEL_7;
  }
  Func = 1;
  sqlite3OomFault(a1);
  a11(a5);
LABEL_7:
  if ( *(_BYTE *)(a1 + 103) || Func )
    v17 = apiHandleError(a1, Func);
  else
    v17 = 0;
  if ( *(_QWORD *)(a1 + 24) )
    ((void (*)(void))xmmword_1800B56C0)();
  return v17;
}

```

## disassembly

```asm
0x18000b850  mov     rax, rsp
0x18000b853  mov     [rax+20h], rbx
0x18000b857  push    r12
0x18000b859  push    r14
0x18000b85b  push    r15
0x18000b85d  sub     rsp, 60h
0x18000b861  mov     r14d, r9d
0x18000b864  mov     r15d, r8d
0x18000b867  mov     r12, rdx
0x18000b86a  mov     rbx, rcx
0x18000b86d  test    rcx, rcx
0x18000b870  jz      loc_18000B9E6
0x18000b876  cmp     byte ptr [rcx+71h], 76h ; 'v'
0x18000b87a  jnz     loc_18000B9EF
0x18000b880  mov     rcx, [rcx+18h]
0x18000b884  mov     [rax+8], rbp
0x18000b888  mov     [rax+10h], rsi
0x18000b88c  xor     esi, esi
0x18000b88e  mov     [rax+18h], rdi
0x18000b892  test    rcx, rcx
0x18000b895  jz      short loc_18000B8A3
0x18000b897  mov     rax, qword ptr cs:xmmword_1800B56B0
0x18000b89e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8a3  mov     rdi, [rsp+78h+arg_50]
0x18000b8ab  mov     rbp, [rsp+78h+arg_20]
0x18000b8b3  test    rdi, rdi
0x18000b8b6  jnz     loc_18000B982
0x18000b8bc  mov     rax, [rsp+78h+arg_48]
0x18000b8c4  mov     r9d, r14d
0x18000b8c7  mov     [rsp+78h+var_28], rsi
0x18000b8cc  mov     r8d, r15d
0x18000b8cf  mov     [rsp+78h+var_30], rax
0x18000b8d4  mov     rdx, r12
0x18000b8d7  mov     rax, [rsp+78h+arg_40]
0x18000b8df  mov     rcx, rbx
0x18000b8e2  mov     [rsp+78h+var_38], rax
0x18000b8e7  mov     rax, [rsp+78h+arg_38]
0x18000b8ef  mov     [rsp+78h+var_40], rax
0x18000b8f4  mov     rax, [rsp+78h+arg_30]
0x18000b8fc  mov     [rsp+78h+var_48], rax
0x18000b901  mov     rax, [rsp+78h+arg_28]
0x18000b909  mov     [rsp+78h+var_50], rax
0x18000b90e  mov     [rsp+78h+var_58], rbp
0x18000b913  call    sqlite3CreateFunc
0x18000b918  mov     r14d, eax
0x18000b91b  test    rsi, rsi
0x18000b91e  jnz     loc_18000B9B2
0x18000b924  cmp     byte ptr [rbx+67h], 0
0x18000b928  mov     rsi, [rsp+78h+arg_8]
0x18000b930  mov     rbp, [rsp+78h+arg_0]
0x18000b938  jnz     short loc_18000B973
0x18000b93a  test    r14d, r14d
0x18000b93d  jnz     short loc_18000B973
0x18000b93f  xor     edi, edi
0x18000b941  mov     rcx, [rbx+18h]
0x18000b945  test    rcx, rcx
0x18000b948  jz      short loc_18000B956
0x18000b94a  mov     rax, qword ptr cs:xmmword_1800B56C0
0x18000b951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b956  mov     eax, edi
0x18000b958  mov     rdi, [rsp+78h+arg_10]
0x18000b960  mov     rbx, [rsp+78h+arg_18]
0x18000b968  add     rsp, 60h
0x18000b96c  pop     r15
0x18000b96e  pop     r14
0x18000b970  pop     r12
0x18000b972  retn
0x18000b973  mov     edx, r14d
0x18000b976  mov     rcx, rbx
0x18000b979  call    apiHandleError
0x18000b97e  mov     edi, eax
0x18000b980  jmp     short loc_18000B941
0x18000b982  mov     ecx, 18h
0x18000b987  call    sqlite3Malloc
0x18000b98c  mov     rsi, rax
0x18000b98f  test    rax, rax
0x18000b992  jnz     short loc_18000B9D3
0x18000b994  mov     rcx, rbx
0x18000b997  mov     r14d, 1
0x18000b99d  call    sqlite3OomFault
0x18000b9a2  mov     rcx, rbp
0x18000b9a5  mov     rax, rdi
0x18000b9a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9ad  jmp     loc_18000B924
0x18000b9b2  cmp     dword ptr [rsi], 0
0x18000b9b5  jnz     loc_18000B924
0x18000b9bb  mov     rcx, rbp
0x18000b9be  mov     rax, rdi
0x18000b9c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9c6  mov     rcx, rsi
0x18000b9c9  call    sqlite3_free
0x18000b9ce  jmp     loc_18000B924
0x18000b9d3  mov     dword ptr [rax], 0
0x18000b9d9  mov     [rax+8], rdi
0x18000b9dd  mov     [rax+10h], rbp
0x18000b9e1  jmp     loc_18000B8BC
0x18000b9e6  lea     r8, aNull_1; "NULL"
0x18000b9ed  jmp     short loc_18000B9FF
0x18000b9ef  call    sqlite3SafetyCheckSickOrOk
0x18000b9f4  test    eax, eax
0x18000b9f6  jz      short loc_18000BA10
0x18000b9f8  lea     r8, aUnopened; "unopened"
0x18000b9ff  lea     rdx, aApiCallWithSDa; "API call with %s database connection po"...
0x18000ba06  mov     ecx, 15h
0x18000ba0b  call    sqlite3_log
0x18000ba10  lea     r8, aMisuse; "misuse"
0x18000ba17  mov     edx, 2CB5Fh
0x18000ba1c  mov     ecx, 15h
0x18000ba21  call    sqlite3ReportError
0x18000ba26  jmp     loc_18000B960
```
