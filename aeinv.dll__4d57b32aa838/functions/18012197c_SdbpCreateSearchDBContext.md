# SdbpCreateSearchDBContext

- ea: `0x18012197c`
- end: `0x180121c4f`
- name: `SdbpCreateSearchDBContext`
- size: `723`
- prototype: `__int64 __fastcall(_QWORD *, __int64 *, __int64, __int64)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18011b4e8`

## callees

- `0x1800197d4`
- `0x18001cce4`
- `0x18002256c`
- `0x1800250cc`
- `0x180059920`
- `0x18005a8bc`
- `0x18006bc7c`
- `0x18012197c`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180121a14`
- `ntdll!RtlAllocateHeap` at `0x180121aa9`
- `ntdll!RtlAllocateHeap` at `0x180121b32`
- `ntdll!RtlAllocateHeap` at `0x180121b4f`
- `ntdll!RtlAllocateHeap` at `0x180121b6c`
- `ntdll!RtlAllocateHeap` at `0x180121a14`
- `ntdll!RtlAllocateHeap` at `0x180121aa9`
- `ntdll!RtlAllocateHeap` at `0x180121b32`
- `ntdll!RtlAllocateHeap` at `0x180121b4f`
- `ntdll!RtlAllocateHeap` at `0x180121b6c`

## string_xrefs

- `0x180121a2f`: `SdbpCreateSearchDBContext`
- `0x180121a7d`: `SdbpCreateSearchDBContext`
- `0x180121ac6`: `SdbpCreateSearchDBContext`
- `0x180121bdc`: `SdbpCreateSearchDBContext`
- `0x180121a22`: `Unable to allocate memory for directory path`
- `0x180121a70`: `Unable to parse executable path for "%ws"`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, __int64 *a2, __int64 a3, __int64 a4)
{
  unsigned int v7; // r12d
  __int64 v8; // rbp
  __int64 v9; // rax
  int v10; // edi
  PVOID Heap; // rsi
  _WORD *v12; // rdi
  _WORD *v13; // rax
  unsigned int v14; // r11d
  _WORD *v15; // rax
  _WORD *v16; // r14
  _BYTE v18[528]; // [rsp+40h] [rbp-468h] BYREF
  _BYTE v19[528]; // [rsp+250h] [rbp-258h] BYREF

  v7 = 0;
  memset_0(v19, 0, 0x208u);
  memset_0(v18, 0, 0x208u);
  if ( !a2 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4u);
    v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v15 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v16 = v15;
    if ( !Heap || !v12 || !v15 )
    {
      AslLogCallPrintf(1, (unsigned int)"SdbpCreateSearchDBContext", 469, (unsigned int)"Unable to allocate memory");
      if ( !Heap )
        goto LABEL_20;
      goto LABEL_19;
    }
    RtlStringCchCopyW(Heap, 2, L".");
    *v12 = 0;
    *v16 = 0;
    a1[3] = v16;
    goto LABEL_17;
  }
  v8 = *a2;
  v9 = -1;
  do
    ++v9;
  while ( *(_WORD *)(v8 + 2 * v9) );
  v10 = v9 + 1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v9 + 1));
  if ( !Heap )
  {
    AslLogCallPrintf(
      1,
      (unsigned int)"SdbpCreateSearchDBContext",
      437,
      (unsigned int)"Unable to allocate memory for directory path");
    return v7;
  }
  if ( (int)AslPathSplit(v8, (_DWORD)Heap, v10, (unsigned int)v18) >= 0 )
  {
    v13 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    v12 = v13;
    if ( !v13 )
    {
      AslLogCallPrintf(
        1,
        (unsigned int)"SdbpCreateSearchDBContext",
        454,
        (unsigned int)"Unable to allocate memory for full name");
      goto LABEL_19;
    }
    if ( (int)RtlStringCchCopyW(v13, 260, v18) < 0 || (int)RtlStringCchCatW(v12, v14, v19) < 0 )
      goto LABEL_19;
LABEL_17:
    a1[1] = a2;
    v7 = 1;
    a1[7] = a4;
    a1[4] = Heap;
    a1[5] = v12;
    a1[6] = 0;
    a1[9] = 0;
    a1[8] = 0;
    a1[11] = 0;
    a1[12] = 0;
    return v7;
  }
  v12 = 0;
  AslLogCallPrintf(
    1,
    (unsigned int)"SdbpCreateSearchDBContext",
    448,
    (unsigned int)"Unable to parse executable path for \"%ws\"");
LABEL_19:
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
LABEL_20:
  if ( v12 )
    AslFree(NtCurrentPeb()->ProcessHeap, v12);
  return v7;
}

```

## disassembly

```asm
0x18012197c  mov     [rsp+arg_10], rbx
0x180121981  push    rbp
0x180121982  push    rsi
0x180121983  push    rdi
0x180121984  push    r12
0x180121986  push    r13
0x180121988  push    r14
0x18012198a  push    r15
0x18012198c  sub     rsp, 470h
0x180121993  mov     rax, cs:__security_cookie
0x18012199a  xor     rax, rsp
0x18012199d  mov     [rsp+4A8h+var_48], rax
0x1801219a5  mov     r15, rdx
0x1801219a8  mov     rbx, rcx
0x1801219ab  mov     edi, 208h
0x1801219b0  lea     rcx, [rsp+4A8h+var_258]; void *
0x1801219b8  xor     ebp, ebp
0x1801219ba  mov     r8d, edi; Size
0x1801219bd  xor     edx, edx; Val
0x1801219bf  mov     r13, r9
0x1801219c2  mov     r12d, ebp
0x1801219c5  call    memset_0
0x1801219ca  mov     r8d, edi; Size
0x1801219cd  lea     rcx, [rsp+4A8h+var_468]; void *
0x1801219d2  xor     edx, edx; Val
0x1801219d4  call    memset_0
0x1801219d9  test    r15, r15
0x1801219dc  jz      loc_180121B18
0x1801219e2  mov     rbp, [r15]
0x1801219e5  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801219e9  xor     ecx, ecx
0x1801219eb  inc     rax
0x1801219ee  cmp     [rbp+rax*2+0], cx
0x1801219f3  jnz     short loc_1801219EB
0x1801219f5  mov     rcx, gs:60h
0x1801219fe  lea     edi, [rax+1]
0x180121a01  mov     r8d, edi
0x180121a04  mov     r14d, 8
0x180121a0a  add     r8, r8; Size
0x180121a0d  mov     edx, r14d; Flags
0x180121a10  mov     rcx, [rcx+30h]; HeapHandle
0x180121a14  call    cs:__imp_RtlAllocateHeap
0x180121a1a  mov     rsi, rax
0x180121a1d  test    rax, rax
0x180121a20  jnz     short loc_180121A43
0x180121a22  lea     r9, aUnableToAlloca_2; "Unable to allocate memory for directory"...
0x180121a29  mov     r8d, 1B5h
0x180121a2f  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x180121a36  lea     ecx, [rax+1]
0x180121a39  call    AslLogCallPrintf
0x180121a3e  jmp     loc_180121C21
0x180121a43  lea     rax, [rsp+4A8h+var_258]
0x180121a4b  mov     r8d, edi
0x180121a4e  lea     r9, [rsp+4A8h+var_468]
0x180121a53  mov     [rsp+4A8h+var_480], rax
0x180121a58  mov     rdx, rsi
0x180121a5b  mov     rcx, rbp
0x180121a5e  call    AslPathSplit
0x180121a63  xor     ecx, ecx
0x180121a65  test    eax, eax
0x180121a67  jns     short loc_180121A93
0x180121a69  mov     edi, ecx
0x180121a6b  mov     [rsp+4A8h+var_488], rbp
0x180121a70  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x180121a77  mov     r8d, 1C0h
0x180121a7d  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x180121a84  lea     ecx, [rdi+1]
0x180121a87  call    AslLogCallPrintf
0x180121a8c  xor     ebp, ebp
0x180121a8e  jmp     loc_180121BF2
0x180121a93  mov     rcx, gs:60h
0x180121a9c  mov     r8d, 208h; Size
0x180121aa2  mov     edx, r14d; Flags
0x180121aa5  mov     rcx, [rcx+30h]; HeapHandle
0x180121aa9  call    cs:__imp_RtlAllocateHeap
0x180121aaf  xor     ebp, ebp
0x180121ab1  mov     rdi, rax
0x180121ab4  test    rax, rax
0x180121ab7  jnz     short loc_180121ADA
0x180121ab9  lea     r9, aUnableToAlloca_1; "Unable to allocate memory for full name"
0x180121ac0  mov     r8d, 1C6h
0x180121ac6  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x180121acd  lea     ecx, [rax+1]
0x180121ad0  call    AslLogCallPrintf
0x180121ad5  jmp     loc_180121BF2
0x180121ada  mov     r11d, 104h
0x180121ae0  lea     r8, [rsp+4A8h+var_468]
0x180121ae5  mov     edx, r11d
0x180121ae8  mov     rcx, rdi
0x180121aeb  call    RtlStringCchCopyW
0x180121af0  test    eax, eax
0x180121af2  js      loc_180121BF2
0x180121af8  lea     r8, [rsp+4A8h+var_258]
0x180121b00  mov     edx, r11d
0x180121b03  mov     rcx, rdi
0x180121b06  call    RtlStringCchCatW
0x180121b0b  test    eax, eax
0x180121b0d  jns     loc_180121BA3
0x180121b13  jmp     loc_180121BF2
0x180121b18  mov     rcx, gs:60h
0x180121b21  mov     r8d, 4; Size
0x180121b27  mov     rcx, [rcx+30h]; HeapHandle
0x180121b2b  lea     r14d, [r8+4]
0x180121b2f  mov     edx, r14d; Flags
0x180121b32  call    cs:__imp_RtlAllocateHeap
0x180121b38  mov     rcx, gs:60h
0x180121b41  lea     r8d, [r14-6]; Size
0x180121b45  mov     edx, r14d; Flags
0x180121b48  mov     rsi, rax
0x180121b4b  mov     rcx, [rcx+30h]; HeapHandle
0x180121b4f  call    cs:__imp_RtlAllocateHeap
0x180121b55  mov     rcx, gs:60h
0x180121b5e  lea     r8d, [r14-6]; Size
0x180121b62  mov     edx, r14d; Flags
0x180121b65  mov     rdi, rax
0x180121b68  mov     rcx, [rcx+30h]; HeapHandle
0x180121b6c  call    cs:__imp_RtlAllocateHeap
0x180121b72  mov     r14, rax
0x180121b75  test    rsi, rsi
0x180121b78  jz      short loc_180121BCF
0x180121b7a  test    rdi, rdi
0x180121b7d  jz      short loc_180121BCF
0x180121b7f  test    rax, rax
0x180121b82  jz      short loc_180121BCF
0x180121b84  lea     r8, asc_180139934; "."
0x180121b8b  mov     edx, 2
0x180121b90  mov     rcx, rsi
0x180121b93  call    RtlStringCchCopyW
0x180121b98  mov     [rdi], bp
0x180121b9b  mov     [r14], bp
0x180121b9f  mov     [rbx+18h], r14
0x180121ba3  mov     [rbx+8], r15
0x180121ba7  mov     r12d, 1
0x180121bad  mov     [rbx+38h], r13
0x180121bb1  mov     [rbx+20h], rsi
0x180121bb5  mov     [rbx+28h], rdi
0x180121bb9  mov     [rbx+30h], rbp
0x180121bbd  mov     [rbx+48h], rbp
0x180121bc1  mov     [rbx+40h], rbp
0x180121bc5  mov     [rbx+58h], rbp
0x180121bc9  mov     [rbx+60h], rbp
0x180121bcd  jmp     short loc_180121C21
0x180121bcf  lea     r9, aUnableToAlloca_0; "Unable to allocate memory"
0x180121bd6  mov     r8d, 1D5h
0x180121bdc  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x180121be3  mov     ecx, 1
0x180121be8  call    AslLogCallPrintf
0x180121bed  test    rsi, rsi
0x180121bf0  jz      short loc_180121C07
0x180121bf2  mov     rcx, gs:60h
0x180121bfb  mov     rdx, rsi
0x180121bfe  mov     rcx, [rcx+30h]
0x180121c02  call    AslFree
0x180121c07  test    rdi, rdi
0x180121c0a  jz      short loc_180121C21
0x180121c0c  mov     rcx, gs:60h
0x180121c15  mov     rdx, rdi
0x180121c18  mov     rcx, [rcx+30h]
0x180121c1c  call    AslFree
0x180121c21  mov     eax, r12d
0x180121c24  mov     rcx, [rsp+4A8h+var_48]
0x180121c2c  xor     rcx, rsp; StackCookie
0x180121c2f  call    __security_check_cookie
0x180121c34  mov     rbx, [rsp+4A8h+arg_10]
0x180121c3c  add     rsp, 470h
0x180121c43  pop     r15
0x180121c45  pop     r14
0x180121c47  pop     r13
0x180121c49  pop     r12
0x180121c4b  pop     rdi
0x180121c4c  pop     rsi
0x180121c4d  pop     rbp
0x180121c4e  retn
```
