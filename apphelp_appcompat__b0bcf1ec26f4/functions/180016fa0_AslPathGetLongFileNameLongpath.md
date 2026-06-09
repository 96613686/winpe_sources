# AslPathGetLongFileNameLongpath

- ea: `0x180016fa0`
- end: `0x18001712b`
- name: `AslPathGetLongFileNameLongpath`
- size: `395`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180016dc0`

## callees

- `0x18000f114`
- `0x18001577c`
- `0x180016fa0`
- `0x180018f20`
- `0x180039a4e`
- `0x180039aba`

## import_xrefs

- `ntdll!wcschr` at `0x180016fd4`
- `ntdll!wcschr` at `0x180016fd4`
- `ntdll!RtlAllocateHeap` at `0x18001705c`
- `ntdll!RtlAllocateHeap` at `0x18001705c`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180017077`
- `api-ms-win-core-file-l1-1-0!GetLongPathNameW` at `0x180017077`

## string_xrefs

- `0x180017029`: `AslPathGetLongFileNameLongpath`
- `0x1800170c1`: `AslPathGetLongFileNameLongpath`
- `0x1800170f7`: `AslPathGetLongFileNameLongpath`
- `0x1800170ec`: `Long path conversion failed %d [%x]`

## pseudocode

```c
__int64 __fastcall AslPathGetLongFileNameLongpath(WCHAR **a1, const wchar_t *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  __int64 v7; // r8
  char v8; // r15
  DWORD v9; // ebx
  WCHAR *Heap; // rax
  WCHAR *v11; // rsi
  DWORD LongPathNameW; // eax
  DWORD v13; // ebp
  DWORD LastError_0; // eax

  *a1 = 0;
  if ( wcsstr_0(a2, L"SIGN.MEDIA=") )
  {
    v4 = AslStringDuplicate(a1, a2);
    v5 = v4;
    if ( v4 >= 0 )
      return v5;
    v7 = 75;
    goto LABEL_8;
  }
  if ( !wcschr(a2, 0x7Eu) )
  {
    v4 = AslStringDuplicate(a1, a2);
    v5 = v4;
    if ( v4 >= 0 )
      return v5;
    v7 = 94;
LABEL_8:
    AslLogCallPrintf(1, "AslPathGetLongFileNameLongpath", v7, "AslStringDuplicate failed [%x]", v4);
    return v5;
  }
  v8 = 0;
  v9 = 260;
  while ( 1 )
  {
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2LL * v9);
    v11 = Heap;
    if ( !Heap )
      return (unsigned int)-1073741801;
    LongPathNameW = GetLongPathNameW(a2, Heap, v9);
    v13 = LongPathNameW;
    if ( !LongPathNameW )
    {
      v5 = -1073741823;
      LastError_0 = GetLastError_0();
      AslLogCallPrintf(
        1,
        "AslPathGetLongFileNameLongpath",
        110,
        "Long path conversion failed %d [%x]",
        LastError_0,
        -1073741823);
      goto LABEL_20;
    }
    if ( LongPathNameW <= v9 )
    {
      if ( LongPathNameW < v9 )
      {
        *a1 = v11;
        return 0;
      }
    }
    else
    {
      if ( v8 )
      {
        v5 = -1073741789;
        AslLogCallPrintf(1, "AslPathGetLongFileNameLongpath", 119, "Buffer allocated was not large enough");
LABEL_20:
        AslFree(NtCurrentPeb()->ProcessHeap, v11);
        return v5;
      }
      AslFree(NtCurrentPeb()->ProcessHeap, v11);
      v9 = v13;
    }
    v8 = 1;
  }
}

```

## disassembly

```asm
0x180016fa0  push    rbx
0x180016fa2  push    rbp
0x180016fa3  push    rsi
0x180016fa4  push    rdi
0x180016fa5  push    r14
0x180016fa7  push    r15
0x180016fa9  sub     rsp, 38h
0x180016fad  mov     rdi, rdx
0x180016fb0  mov     qword ptr [rcx], 0
0x180016fb7  mov     r14, rcx
0x180016fba  lea     rdx, aSignMedia; "SIGN.MEDIA="
0x180016fc1  mov     rcx, rdi; Str
0x180016fc4  call    wcsstr_0
0x180016fc9  test    rax, rax
0x180016fcc  jnz     short loc_180016FFF
0x180016fce  lea     edx, [rax+7Eh]; Ch
0x180016fd1  mov     rcx, rdi; Str
0x180016fd4  call    cs:__imp_wcschr
0x180016fda  test    rax, rax
0x180016fdd  jnz     short loc_18001703C
0x180016fdf  mov     rdx, rdi
0x180016fe2  mov     rcx, r14
0x180016fe5  call    AslStringDuplicate
0x180016fea  mov     ebx, eax
0x180016fec  test    eax, eax
0x180016fee  js      short loc_180017018
0x180016ff0  mov     eax, ebx
0x180016ff2  add     rsp, 38h
0x180016ff6  pop     r15
0x180016ff8  pop     r14
0x180016ffa  pop     rdi
0x180016ffb  pop     rsi
0x180016ffc  pop     rbp
0x180016ffd  pop     rbx
0x180016ffe  retn
0x180016fff  mov     rdx, rdi
0x180017002  mov     rcx, r14
0x180017005  call    AslStringDuplicate
0x18001700a  mov     ebx, eax
0x18001700c  test    eax, eax
0x18001700e  jns     short loc_180016FF0
0x180017010  mov     r8d, 4Bh ; 'K'
0x180017016  jmp     short loc_18001701E
0x180017018  mov     r8d, 5Eh ; '^'
0x18001701e  lea     r9, aAslstringdupli_2; "AslStringDuplicate failed [%x]"
0x180017025  mov     [rsp+68h+var_48], eax
0x180017029  lea     rdx, aAslpathgetlong_0; "AslPathGetLongFileNameLongpath"
0x180017030  mov     ecx, 1
0x180017035  call    AslLogCallPrintf
0x18001703a  jmp     short loc_180016FF0
0x18001703c  xor     r15b, r15b
0x18001703f  mov     ebx, 104h
0x180017044  mov     rcx, gs:60h
0x18001704d  mov     edx, 8; Flags
0x180017052  mov     r8d, ebx
0x180017055  add     r8, r8; Size
0x180017058  mov     rcx, [rcx+30h]; HeapHandle
0x18001705c  call    cs:__imp_RtlAllocateHeap
0x180017062  mov     rsi, rax
0x180017065  test    rax, rax
0x180017068  jz      loc_180017121
0x18001706e  mov     r8d, ebx; cchBuffer
0x180017071  mov     rdx, rax; lpszLongPath
0x180017074  mov     rcx, rdi; lpszShortPath
0x180017077  call    cs:__imp_GetLongPathNameW
0x18001707d  mov     ebp, eax
0x18001707f  test    eax, eax
0x180017081  jz      short loc_1800170D8
0x180017083  cmp     eax, ebx
0x180017085  jbe     short loc_1800170A8
0x180017087  test    r15b, r15b
0x18001708a  jnz     short loc_1800170B4
0x18001708c  mov     rcx, gs:60h
0x180017095  mov     rdx, rsi
0x180017098  mov     rcx, [rcx+30h]
0x18001709c  call    AslFree
0x1800170a1  mov     ebx, ebp
0x1800170a3  mov     r15b, 1
0x1800170a6  jmp     short loc_180017044
0x1800170a8  jnb     short loc_1800170A3
0x1800170aa  mov     [r14], rsi
0x1800170ad  xor     ebx, ebx
0x1800170af  jmp     loc_180016FF0
0x1800170b4  mov     r8d, 77h ; 'w'
0x1800170ba  lea     r9, aBufferAllocate; "Buffer allocated was not large enough"
0x1800170c1  lea     rdx, aAslpathgetlong_0; "AslPathGetLongFileNameLongpath"
0x1800170c8  mov     ebx, 0C0000023h
0x1800170cd  lea     ecx, [r8-76h]
0x1800170d1  call    AslLogCallPrintf
0x1800170d6  jmp     short loc_180017107
0x1800170d8  mov     ebx, 0C0000001h
0x1800170dd  call    GetLastError_0
0x1800170e2  mov     r8d, 6Eh ; 'n'
0x1800170e8  mov     [rsp+68h+var_40], ebx
0x1800170ec  lea     r9, aLongPathConver; "Long path conversion failed %d [%x]"
0x1800170f3  mov     [rsp+68h+var_48], eax
0x1800170f7  lea     rdx, aAslpathgetlong_0; "AslPathGetLongFileNameLongpath"
0x1800170fe  lea     ecx, [r8-6Dh]
0x180017102  call    AslLogCallPrintf
0x180017107  mov     rcx, gs:60h
0x180017110  mov     rdx, rsi
0x180017113  mov     rcx, [rcx+30h]
0x180017117  call    AslFree
0x18001711c  jmp     loc_180016FF0
0x180017121  mov     ebx, 0C0000017h
0x180017126  jmp     loc_180016FF0
```
