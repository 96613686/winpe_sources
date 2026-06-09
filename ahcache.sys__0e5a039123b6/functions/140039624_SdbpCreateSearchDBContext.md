# SdbpCreateSearchDBContext

- ea: `0x140039624`
- end: `0x140039892`
- name: `SdbpCreateSearchDBContext`
- size: `622`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x14003a438`
- `0x14005a304`

## callees

- `0x1400012f0`
- `0x1400013d0`
- `0x140004553`
- `0x1400079f0`
- `0x140007e40`
- `0x140039624`
- `0x14003e364`
- `0x140045d44`
- `0x140053258`
- `0x14005498c`

## string_xrefs

- `0x1400396bc`: `Unable to allocate memory for directory path`
- `0x1400396c9`: `SdbpCreateSearchDBContext`
- `0x140039713`: `SdbpCreateSearchDBContext`
- `0x140039753`: `SdbpCreateSearchDBContext`
- `0x14003983b`: `SdbpCreateSearchDBContext`
- `0x140039701`: `Unable to parse executable path for "%ws"`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, const wchar_t **a2, __int64 a3, __int64 a4, __int64 a5)
{
  unsigned int v8; // r15d
  __int64 v9; // rcx
  const wchar_t *v10; // rdi
  __int64 v11; // rax
  unsigned int v12; // ebx
  wchar_t *Pool2_0; // rbp
  __int64 v14; // rcx
  wchar_t *v15; // rbx
  __int64 v16; // rcx
  wchar_t *v17; // rax
  unsigned int v18; // r10d
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rax
  _WORD *v22; // r11
  int v24; // [rsp+20h] [rbp-488h]
  wchar_t pszSrc[264]; // [rsp+40h] [rbp-468h] BYREF
  wchar_t v26[264]; // [rsp+250h] [rbp-258h] BYREF

  v8 = 0;
  memset(v26, 0, 0x208u);
  memset(pszSrc, 0, 0x208u);
  if ( !a2 )
  {
    Pool2_0 = (wchar_t *)AslAlloc(v9, 4, 1);
    v15 = (wchar_t *)AslAlloc(v19, 2, 1);
    v21 = AslAlloc(v20, 2, 1);
    if ( !Pool2_0 || !v15 || !v21 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 469, "Unable to allocate memory");
      if ( !Pool2_0 )
        goto LABEL_20;
      goto LABEL_19;
    }
    RtlStringCchCopyW(Pool2_0, 2u, L".");
    *v15 = 0;
    *v22 = 0;
    a1[3] = v22;
    goto LABEL_17;
  }
  v10 = *a2;
  v11 = -1;
  do
    ++v11;
  while ( v10[v11] );
  v12 = v11 + 1;
  Pool2_0 = (wchar_t *)ExAllocatePool2_0(256, 2LL * (unsigned int)(v11 + 1), 1953517633);
  if ( !Pool2_0 )
  {
    AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 437, "Unable to allocate memory for directory path");
    return v8;
  }
  if ( (int)AslPathSplit(v10, Pool2_0, v12, pszSrc, v24, v26) >= 0 )
  {
    v17 = (wchar_t *)AslAlloc(v14, 520, 1);
    v15 = v17;
    if ( !v17 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 454, "Unable to allocate memory for full name");
      goto LABEL_19;
    }
    if ( RtlStringCchCopyW(v17, 0x104u, pszSrc) < 0 || RtlStringCchCatW(v15, v18, v26) < 0 )
      goto LABEL_19;
LABEL_17:
    v8 = 1;
    a1[11] = a5;
    a1[1] = a2;
    a1[7] = a4;
    a1[4] = Pool2_0;
    a1[5] = v15;
    a1[6] = 0;
    a1[9] = 0;
    a1[8] = 0;
    a1[12] = 0;
    return v8;
  }
  v15 = 0;
  AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 448, "Unable to parse executable path for \"%ws\"", v10);
LABEL_19:
  AslFree(v16, Pool2_0);
LABEL_20:
  if ( v15 )
    AslFree(v16, v15);
  return v8;
}

```

## disassembly

```asm
0x140039624  mov     [rsp+arg_10], rbx
0x140039629  push    rbp
0x14003962a  push    rsi
0x14003962b  push    rdi
0x14003962c  push    r12
0x14003962e  push    r13
0x140039630  push    r14
0x140039632  push    r15
0x140039634  sub     rsp, 470h
0x14003963b  mov     rax, cs:__security_cookie
0x140039642  xor     rax, rsp
0x140039645  mov     [rsp+4A8h+var_48], rax
0x14003964d  mov     r14, rdx
0x140039650  mov     rsi, rcx
0x140039653  mov     ebx, 208h
0x140039658  lea     rcx, [rsp+4A8h+var_258]; void *
0x140039660  xor     r13d, r13d
0x140039663  mov     r8d, ebx; Size
0x140039666  xor     edx, edx; Val
0x140039668  mov     r12, r9
0x14003966b  mov     r15d, r13d
0x14003966e  call    memset
0x140039673  mov     r8d, ebx; Size
0x140039676  lea     rcx, [rsp+4A8h+pszSrc]; void *
0x14003967b  xor     edx, edx; Val
0x14003967d  call    memset
0x140039682  test    r14, r14
0x140039685  jz      loc_1400397A1
0x14003968b  mov     rdi, [r14]
0x14003968e  or      rax, 0FFFFFFFFFFFFFFFFh
0x140039692  inc     rax
0x140039695  cmp     [rdi+rax*2], r13w
0x14003969a  jnz     short loc_140039692
0x14003969c  lea     ebx, [rax+1]
0x14003969f  mov     ecx, 100h
0x1400396a4  mov     edx, ebx
0x1400396a6  mov     r8d, 74705041h
0x1400396ac  add     rdx, rdx
0x1400396af  call    ExAllocatePool2_0
0x1400396b4  mov     rbp, rax
0x1400396b7  test    rax, rax
0x1400396ba  jnz     short loc_1400396DD
0x1400396bc  lea     r9, aUnableToAlloca_2; "Unable to allocate memory for directory"...
0x1400396c3  mov     r8d, 1B5h
0x1400396c9  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x1400396d0  lea     ecx, [rax+1]
0x1400396d3  call    AslLogCallPrintf
0x1400396d8  jmp     loc_140039863
0x1400396dd  lea     rax, [rsp+4A8h+var_258]
0x1400396e5  mov     r8d, ebx; cchDest
0x1400396e8  lea     r9, [rsp+4A8h+pszSrc]; NTSTRSAFE_PWSTR
0x1400396ed  mov     [rsp+4A8h+var_480], rax; NTSTRSAFE_PWSTR
0x1400396f2  mov     rdx, rbp; pszDest
0x1400396f5  mov     rcx, rdi; pszSrc
0x1400396f8  call    AslPathSplit
0x1400396fd  test    eax, eax
0x1400396ff  jns     short loc_14003972C
0x140039701  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x140039708  mov     [rsp+4A8h+var_488], rdi
0x14003970d  mov     r8d, 1C0h
0x140039713  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x14003971a  mov     ecx, 1
0x14003971f  mov     rbx, r13
0x140039722  call    AslLogCallPrintf
0x140039727  jmp     loc_14003984E
0x14003972c  mov     edi, 1
0x140039731  mov     edx, 208h
0x140039736  mov     r8d, edi
0x140039739  call    AslAlloc
0x14003973e  mov     rbx, rax
0x140039741  test    rax, rax
0x140039744  jnz     short loc_140039766
0x140039746  lea     r9, aUnableToAlloca_1; "Unable to allocate memory for full name"
0x14003974d  mov     r8d, 1C6h
0x140039753  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x14003975a  mov     ecx, edi
0x14003975c  call    AslLogCallPrintf
0x140039761  jmp     loc_14003984E
0x140039766  mov     r10d, 104h
0x14003976c  lea     r8, [rsp+4A8h+pszSrc]; pszSrc
0x140039771  mov     edx, r10d; cchDest
0x140039774  mov     rcx, rbx; pszDest
0x140039777  call    RtlStringCchCopyW
0x14003977c  test    eax, eax
0x14003977e  js      loc_14003984E
0x140039784  lea     r8, [rsp+4A8h+var_258]; pszSrc
0x14003978c  mov     edx, r10d; cchDest
0x14003978f  mov     rcx, rbx; pszDest
0x140039792  call    RtlStringCchCatW
0x140039797  test    eax, eax
0x140039799  js      loc_14003984E
0x14003979f  jmp     short loc_1400397FD
0x1400397a1  mov     edi, 1
0x1400397a6  mov     r8d, edi
0x1400397a9  lea     edx, [rdi+3]
0x1400397ac  call    AslAlloc
0x1400397b1  mov     r8d, edi
0x1400397b4  lea     edx, [rdi+1]
0x1400397b7  mov     rbp, rax
0x1400397ba  call    AslAlloc
0x1400397bf  mov     r8d, edi
0x1400397c2  lea     edx, [rdi+1]
0x1400397c5  mov     rbx, rax
0x1400397c8  call    AslAlloc
0x1400397cd  mov     r11, rax
0x1400397d0  test    rbp, rbp
0x1400397d3  jz      short loc_14003982E
0x1400397d5  test    rbx, rbx
0x1400397d8  jz      short loc_14003982E
0x1400397da  test    rax, rax
0x1400397dd  jz      short loc_14003982E
0x1400397df  lea     r8, asc_14000D070; "."
0x1400397e6  mov     rcx, rbp; pszDest
0x1400397e9  lea     edx, [rdi+1]; cchDest
0x1400397ec  call    RtlStringCchCopyW
0x1400397f1  mov     [rbx], r13w
0x1400397f5  mov     [r11], r13w
0x1400397f9  mov     [rsi+18h], r11
0x1400397fd  mov     rax, [rsp+4A8h+arg_20]
0x140039805  mov     r15d, edi
0x140039808  mov     [rsi+58h], rax
0x14003980c  mov     [rsi+8], r14
0x140039810  mov     [rsi+38h], r12
0x140039814  mov     [rsi+20h], rbp
0x140039818  mov     [rsi+28h], rbx
0x14003981c  mov     [rsi+30h], r13
0x140039820  mov     [rsi+48h], r13
0x140039824  mov     [rsi+40h], r13
0x140039828  mov     [rsi+60h], r13
0x14003982c  jmp     short loc_140039863
0x14003982e  lea     r9, aUnableToAlloca_0; "Unable to allocate memory"
0x140039835  mov     r8d, 1D5h
0x14003983b  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140039842  mov     ecx, edi
0x140039844  call    AslLogCallPrintf
0x140039849  test    rbp, rbp
0x14003984c  jz      short loc_140039856
0x14003984e  mov     rdx, rbp
0x140039851  call    AslFree
0x140039856  test    rbx, rbx
0x140039859  jz      short loc_140039863
0x14003985b  mov     rdx, rbx
0x14003985e  call    AslFree
0x140039863  mov     eax, r15d
0x140039866  mov     rcx, [rsp+4A8h+var_48]
0x14003986e  xor     rcx, rsp; StackCookie
0x140039871  call    __security_check_cookie
0x140039876  mov     rbx, [rsp+4A8h+arg_10]
0x14003987e  add     rsp, 470h
0x140039885  pop     r15
0x140039887  pop     r14
0x140039889  pop     r13
0x14003988b  pop     r12
0x14003988d  pop     rdi
0x14003988e  pop     rsi
0x14003988f  pop     rbp
0x140039890  retn
```
