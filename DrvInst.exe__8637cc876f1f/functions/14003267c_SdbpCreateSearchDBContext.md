# SdbpCreateSearchDBContext

- ea: `0x14003267c`
- end: `0x140032949`
- name: `SdbpCreateSearchDBContext`
- size: `717`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x140030008`

## callees

- `0x14002fdc0`
- `0x14002fea8`
- `0x14003267c`
- `0x14003bf18`
- `0x14003c368`
- `0x14003def0`
- `0x140045eea`
- `0x140045f30`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x140032711`
- `ntdll!RtlAllocateHeap` at `0x1400327a5`
- `ntdll!RtlAllocateHeap` at `0x14003282c`
- `ntdll!RtlAllocateHeap` at `0x14003284c`
- `ntdll!RtlAllocateHeap` at `0x140032868`
- `ntdll!RtlAllocateHeap` at `0x140032711`
- `ntdll!RtlAllocateHeap` at `0x1400327a5`
- `ntdll!RtlAllocateHeap` at `0x14003282c`
- `ntdll!RtlAllocateHeap` at `0x14003284c`
- `ntdll!RtlAllocateHeap` at `0x140032868`

## string_xrefs

- `0x14003271f`: `Unable to allocate memory for directory path`
- `0x140032764`: `Unable to parse executable path for "%ws"`
- `0x14003272c`: `SdbpCreateSearchDBContext`
- `0x140032776`: `SdbpCreateSearchDBContext`
- `0x1400327c0`: `SdbpCreateSearchDBContext`
- `0x1400328d6`: `SdbpCreateSearchDBContext`

## pseudocode

```c
__int64 __fastcall SdbpCreateSearchDBContext(_QWORD *a1, const wchar_t **a2)
{
  unsigned int v4; // r12d
  const wchar_t *v5; // rbp
  __int64 v6; // rax
  unsigned int v7; // edi
  _WORD *Heap; // rsi
  _WORD *v9; // rdi
  _WORD *v10; // rax
  unsigned int v11; // r11d
  _WORD *v12; // rax
  _WORD *v13; // r14
  int v15; // [rsp+20h] [rbp-488h]
  _WORD v16[264]; // [rsp+40h] [rbp-468h] BYREF
  _WORD v17[264]; // [rsp+250h] [rbp-258h] BYREF

  v4 = 0;
  memset_0(v17, 0, 0x208u);
  memset_0(v16, 0, 0x208u);
  if ( !a2 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 4u);
    v9 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v12 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2u);
    v13 = v12;
    if ( !Heap || !v9 || !v12 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 469, "Unable to allocate memory");
      if ( !Heap )
        goto LABEL_20;
      goto LABEL_19;
    }
    RtlStringCchCopyW(Heap, 2, L".");
    *v9 = 0;
    *v13 = 0;
    a1[3] = v13;
    goto LABEL_17;
  }
  v5 = *a2;
  v6 = -1;
  do
    ++v6;
  while ( v5[v6] );
  v7 = v6 + 1;
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * (unsigned int)(v6 + 1));
  if ( !Heap )
  {
    AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 437, "Unable to allocate memory for directory path");
    return v4;
  }
  if ( (int)AslPathSplit(v5, Heap, v7, v16, v15, v17) >= 0 )
  {
    v10 = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x208u);
    v9 = v10;
    if ( !v10 )
    {
      AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 454, "Unable to allocate memory for full name");
      goto LABEL_19;
    }
    if ( (int)RtlStringCchCopyW(v10, 260, v16) < 0 || (int)RtlStringCchCatW(v9, v11, v17) < 0 )
      goto LABEL_19;
LABEL_17:
    a1[1] = a2;
    v4 = 1;
    a1[7] = 0;
    a1[4] = Heap;
    a1[5] = v9;
    a1[6] = 0;
    a1[9] = 0;
    a1[8] = 0;
    a1[11] = 0;
    a1[12] = 0;
    return v4;
  }
  v9 = 0;
  AslLogCallPrintf(1, "SdbpCreateSearchDBContext", 448, "Unable to parse executable path for \"%ws\"", v5);
LABEL_19:
  AslFree(NtCurrentPeb()->ProcessHeap, Heap);
LABEL_20:
  if ( v9 )
    AslFree(NtCurrentPeb()->ProcessHeap, v9);
  return v4;
}

```

## disassembly

```asm
0x14003267c  mov     [rsp+arg_10], rbx
0x140032681  push    rbp
0x140032682  push    rsi
0x140032683  push    rdi
0x140032684  push    r12
0x140032686  push    r13
0x140032688  push    r14
0x14003268a  push    r15
0x14003268c  sub     rsp, 470h
0x140032693  mov     rax, cs:__security_cookie
0x14003269a  xor     rax, rsp
0x14003269d  mov     [rsp+4A8h+var_48], rax
0x1400326a5  mov     r15, rdx
0x1400326a8  mov     rbx, rcx
0x1400326ab  mov     edi, 208h
0x1400326b0  lea     rcx, [rsp+4A8h+var_258]; void *
0x1400326b8  xor     r13d, r13d
0x1400326bb  mov     r8d, edi; Size
0x1400326be  xor     edx, edx; Val
0x1400326c0  mov     r12d, r13d
0x1400326c3  call    memset_0
0x1400326c8  mov     r8d, edi; Size
0x1400326cb  lea     rcx, [rsp+4A8h+var_468]; void *
0x1400326d0  xor     edx, edx; Val
0x1400326d2  call    memset_0
0x1400326d7  test    r15, r15
0x1400326da  jz      loc_140032812
0x1400326e0  mov     rbp, [r15]
0x1400326e3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1400326e7  inc     rax
0x1400326ea  cmp     [rbp+rax*2+0], r13w
0x1400326f0  jnz     short loc_1400326E7
0x1400326f2  mov     rcx, gs:60h
0x1400326fb  lea     edi, [rax+1]
0x1400326fe  mov     r8d, edi
0x140032701  mov     r14d, 8
0x140032707  add     r8, r8; Size
0x14003270a  mov     edx, r14d; Flags
0x14003270d  mov     rcx, [rcx+30h]; HeapHandle
0x140032711  call    cs:__imp_RtlAllocateHeap
0x140032717  mov     rsi, rax
0x14003271a  test    rax, rax
0x14003271d  jnz     short loc_140032740
0x14003271f  lea     r9, aUnableToAlloca_3; "Unable to allocate memory for directory"...
0x140032726  mov     r8d, 1B5h
0x14003272c  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x140032733  lea     ecx, [rax+1]
0x140032736  call    AslLogCallPrintf
0x14003273b  jmp     loc_14003291B
0x140032740  lea     rax, [rsp+4A8h+var_258]
0x140032748  mov     r8d, edi
0x14003274b  lea     r9, [rsp+4A8h+var_468]
0x140032750  mov     [rsp+4A8h+var_480], rax
0x140032755  mov     rdx, rsi
0x140032758  mov     rcx, rbp
0x14003275b  call    AslPathSplit
0x140032760  test    eax, eax
0x140032762  jns     short loc_14003278F
0x140032764  lea     r9, aUnableToParseE; "Unable to parse executable path for \"%"...
0x14003276b  mov     [rsp+4A8h+var_488], rbp
0x140032770  mov     r8d, 1C0h
0x140032776  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x14003277d  mov     ecx, 1
0x140032782  mov     rdi, r13
0x140032785  call    AslLogCallPrintf
0x14003278a  jmp     loc_1400328EC
0x14003278f  mov     rcx, gs:60h
0x140032798  mov     r8d, 208h; Size
0x14003279e  mov     edx, r14d; Flags
0x1400327a1  mov     rcx, [rcx+30h]; HeapHandle
0x1400327a5  call    cs:__imp_RtlAllocateHeap
0x1400327ab  mov     rdi, rax
0x1400327ae  test    rax, rax
0x1400327b1  jnz     short loc_1400327D4
0x1400327b3  lea     r9, aUnableToAlloca_2; "Unable to allocate memory for full name"
0x1400327ba  mov     r8d, 1C6h
0x1400327c0  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x1400327c7  lea     ecx, [rax+1]
0x1400327ca  call    AslLogCallPrintf
0x1400327cf  jmp     loc_1400328EC
0x1400327d4  mov     r11d, 104h
0x1400327da  lea     r8, [rsp+4A8h+var_468]
0x1400327df  mov     edx, r11d
0x1400327e2  mov     rcx, rdi
0x1400327e5  call    RtlStringCchCopyW
0x1400327ea  test    eax, eax
0x1400327ec  js      loc_1400328EC
0x1400327f2  lea     r8, [rsp+4A8h+var_258]
0x1400327fa  mov     edx, r11d
0x1400327fd  mov     rcx, rdi
0x140032800  call    RtlStringCchCatW
0x140032805  test    eax, eax
0x140032807  jns     loc_14003289D
0x14003280d  jmp     loc_1400328EC
0x140032812  mov     rcx, gs:60h
0x14003281b  mov     r8d, 4; Size
0x140032821  mov     rcx, [rcx+30h]; HeapHandle
0x140032825  lea     r14d, [r8+4]
0x140032829  mov     edx, r14d; Flags
0x14003282c  call    cs:__imp_RtlAllocateHeap
0x140032832  mov     rcx, gs:60h
0x14003283b  lea     ebp, [r14-6]
0x14003283f  mov     r8d, ebp; Size
0x140032842  mov     edx, r14d; Flags
0x140032845  mov     rsi, rax
0x140032848  mov     rcx, [rcx+30h]; HeapHandle
0x14003284c  call    cs:__imp_RtlAllocateHeap
0x140032852  mov     rcx, gs:60h
0x14003285b  mov     r8d, ebp; Size
0x14003285e  mov     edx, r14d; Flags
0x140032861  mov     rdi, rax
0x140032864  mov     rcx, [rcx+30h]; HeapHandle
0x140032868  call    cs:__imp_RtlAllocateHeap
0x14003286e  mov     r14, rax
0x140032871  test    rsi, rsi
0x140032874  jz      short loc_1400328C9
0x140032876  test    rdi, rdi
0x140032879  jz      short loc_1400328C9
0x14003287b  test    rax, rax
0x14003287e  jz      short loc_1400328C9
0x140032880  lea     r8, asc_1400525DC; "."
0x140032887  mov     edx, ebp
0x140032889  mov     rcx, rsi
0x14003288c  call    RtlStringCchCopyW
0x140032891  mov     [rdi], r13w
0x140032895  mov     [r14], r13w
0x140032899  mov     [rbx+18h], r14
0x14003289d  mov     [rbx+8], r15
0x1400328a1  mov     r12d, 1
0x1400328a7  mov     [rbx+38h], r13
0x1400328ab  mov     [rbx+20h], rsi
0x1400328af  mov     [rbx+28h], rdi
0x1400328b3  mov     [rbx+30h], r13
0x1400328b7  mov     [rbx+48h], r13
0x1400328bb  mov     [rbx+40h], r13
0x1400328bf  mov     [rbx+58h], r13
0x1400328c3  mov     [rbx+60h], r13
0x1400328c7  jmp     short loc_14003291B
0x1400328c9  lea     r9, aUnableToAlloca_1; "Unable to allocate memory"
0x1400328d0  mov     r8d, 1D5h
0x1400328d6  lea     rdx, aSdbpcreatesear_0; "SdbpCreateSearchDBContext"
0x1400328dd  mov     ecx, 1
0x1400328e2  call    AslLogCallPrintf
0x1400328e7  test    rsi, rsi
0x1400328ea  jz      short loc_140032901
0x1400328ec  mov     rcx, gs:60h
0x1400328f5  mov     rdx, rsi
0x1400328f8  mov     rcx, [rcx+30h]
0x1400328fc  call    AslFree
0x140032901  test    rdi, rdi
0x140032904  jz      short loc_14003291B
0x140032906  mov     rcx, gs:60h
0x14003290f  mov     rdx, rdi
0x140032912  mov     rcx, [rcx+30h]
0x140032916  call    AslFree
0x14003291b  mov     eax, r12d
0x14003291e  mov     rcx, [rsp+4A8h+var_48]
0x140032926  xor     rcx, rsp; StackCookie
0x140032929  call    __security_check_cookie
0x14003292e  mov     rbx, [rsp+4A8h+arg_10]
0x140032936  add     rsp, 470h
0x14003293d  pop     r15
0x14003293f  pop     r14
0x140032941  pop     r13
0x140032943  pop     r12
0x140032945  pop     rdi
0x140032946  pop     rsi
0x140032947  pop     rbp
0x140032948  retn
```
