# BiGetSystemStorePathComponents

- ea: `0x14001c508`
- end: `0x14001c6dc`
- name: `BiGetSystemStorePathComponents`
- size: `468`
- prototype: `__int64 __fastcall(wchar_t **, wchar_t **)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400200a0`

## callees

- `0x14001c3a8`
- `0x14001c458`
- `0x14001c508`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x14001c5d2`
- `msvcrt!wcscpy_s` at `0x14001c5d2`
- `msvcrt!wcsncpy_s` at `0x14001c654`
- `msvcrt!wcsncpy_s` at `0x14001c654`
- `msvcrt!wcsrchr` at `0x14001c5f3`
- `msvcrt!wcsrchr` at `0x14001c5f3`
- `msvcrt!wcscat_s` at `0x14001c5e5`
- `msvcrt!wcscat_s` at `0x14001c5e5`
- `ntdll!RtlAllocateHeap` at `0x14001c5af`
- `ntdll!RtlAllocateHeap` at `0x14001c631`
- `ntdll!RtlAllocateHeap` at `0x14001c5af`
- `ntdll!RtlAllocateHeap` at `0x14001c631`
- `ntdll!RtlFreeHeap` at `0x14001c685`
- `ntdll!RtlFreeHeap` at `0x14001c6a6`
- `ntdll!RtlFreeHeap` at `0x14001c6c3`
- `ntdll!RtlFreeHeap` at `0x14001c685`
- `ntdll!RtlFreeHeap` at `0x14001c6a6`
- `ntdll!RtlFreeHeap` at `0x14001c6c3`

## pseudocode

```c
__int64 __fastcall BiGetSystemStorePathComponents(wchar_t **a1, wchar_t **a2)
{
  int v4; // eax
  int v5; // ebx
  const wchar_t *v6; // r14
  wchar_t *v7; // rsi
  wchar_t *v8; // rdi
  int SystemPartition; // eax
  wchar_t *v10; // r15
  __int64 v11; // rax
  __int64 v12; // rax
  rsize_t v13; // rbp
  wchar_t *Heap; // rax
  wchar_t *v15; // rax
  __int64 v16; // rbp
  PVOID ProcessHeap; // rcx
  wchar_t *v18; // rax
  wchar_t *Source; // [rsp+80h] [rbp+18h] BYREF

  Source = 0;
  v4 = BiGetFirmwareType(0) - 1;
  if ( v4 )
  {
    if ( (unsigned int)(v4 - 1) >= 2 )
      return (unsigned int)-1073741637;
    v6 = L"EFI\\Microsoft\\Boot\\BCD";
  }
  else
  {
    v6 = L"Boot\\BCD";
  }
  v7 = 0;
  v8 = 0;
  SystemPartition = BiGetSystemPartition(&Source);
  v10 = Source;
  v5 = SystemPartition;
  if ( SystemPartition >= 0 )
  {
    if ( a1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( Source[v11] );
      v12 = (unsigned int)(v11 + 2);
      v13 = (unsigned int)v12;
      Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, 2 * v12);
      v8 = Heap;
      if ( !Heap )
        goto LABEL_11;
      wcscpy_s(Heap, v13, v10);
      wcscat_s(v8, v13, L"\\");
    }
    v15 = wcsrchr(v6, 0x5Cu);
    if ( !v15 )
    {
      v5 = -1073741811;
      goto LABEL_22;
    }
    if ( a2 )
    {
      v16 = v15 - v6;
      ProcessHeap = NtCurrentPeb()->ProcessHeap;
      Source = (wchar_t *)(unsigned int)(v16 + 1);
      v18 = (wchar_t *)RtlAllocateHeap(ProcessHeap, 0, 2LL * (_QWORD)Source);
      v7 = v18;
      if ( !v8 )
      {
LABEL_11:
        v5 = -1073741670;
        goto LABEL_22;
      }
      wcsncpy_s(v18, (rsize_t)Source, v6, (unsigned int)v16);
    }
    if ( a1 )
      *a1 = v8;
    if ( a2 )
      *a2 = v7;
  }
LABEL_22:
  if ( v10 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v10);
  if ( v5 < 0 )
  {
    if ( v8 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v8);
    if ( v7 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v7);
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x14001c508  mov     rax, rsp
0x14001c50b  mov     [rax+18h], r8
0x14001c50f  push    rbx
0x14001c510  push    rbp
0x14001c511  push    rsi
0x14001c512  push    rdi
0x14001c513  push    r12
0x14001c515  push    r13
0x14001c517  push    r14
0x14001c519  push    r15
0x14001c51b  sub     rsp, 28h
0x14001c51f  mov     r12, rcx
0x14001c522  xor     ebp, ebp
0x14001c524  xor     ecx, ecx
0x14001c526  mov     [rax+18h], rbp
0x14001c52a  mov     r13, rdx
0x14001c52d  call    BiGetFirmwareType
0x14001c532  sub     eax, 1
0x14001c535  jz      short loc_14001C554
0x14001c537  sub     eax, 1
0x14001c53a  jz      short loc_14001C54B
0x14001c53c  cmp     eax, 1
0x14001c53f  jz      short loc_14001C54B
0x14001c541  mov     ebx, 0C00000BBh
0x14001c546  jmp     loc_14001C6C9
0x14001c54b  lea     r14, aEfiMicrosoftBo_2+2; "EFI\\Microsoft\\Boot\\BCD"
0x14001c552  jmp     short loc_14001C55B
0x14001c554  lea     r14, aBootBcd_0+2; "Boot\\BCD"
0x14001c55b  lea     rcx, [rsp+68h+Source]
0x14001c563  mov     rsi, rbp
0x14001c566  mov     rdi, rbp
0x14001c569  call    BiGetSystemPartition
0x14001c56e  mov     r15, [rsp+68h+Source]
0x14001c576  mov     ebx, eax
0x14001c578  test    eax, eax
0x14001c57a  js      loc_14001C66E
0x14001c580  test    r12, r12
0x14001c583  jz      short loc_14001C5EB
0x14001c585  or      rax, 0FFFFFFFFFFFFFFFFh
0x14001c589  inc     rax
0x14001c58c  cmp     [r15+rax*2], bp
0x14001c591  jnz     short loc_14001C589
0x14001c593  mov     rcx, gs:60h
0x14001c59c  add     eax, 2
0x14001c59f  xor     edx, edx; Flags
0x14001c5a1  mov     ebp, eax
0x14001c5a3  mov     rcx, [rcx+30h]; HeapHandle
0x14001c5a7  lea     r8, ds:0[rax*2]; Size
0x14001c5af  call    cs:__imp_RtlAllocateHeap
0x14001c5b5  mov     rdi, rax
0x14001c5b8  test    rax, rax
0x14001c5bb  jnz     short loc_14001C5C9
0x14001c5bd  mov     ebx, 0C000009Ah
0x14001c5c2  xor     ebp, ebp
0x14001c5c4  jmp     loc_14001C66E
0x14001c5c9  mov     r8, r15; Source
0x14001c5cc  mov     rdx, rbp; SizeInWords
0x14001c5cf  mov     rcx, rdi; Destination
0x14001c5d2  call    cs:__imp_wcscpy_s
0x14001c5d8  lea     r8, pszSrc; "\\"
0x14001c5df  mov     rdx, rbp; SizeInWords
0x14001c5e2  mov     rcx, rdi; Destination
0x14001c5e5  call    cs:__imp_wcscat_s
0x14001c5eb  mov     edx, 5Ch ; '\'; Ch
0x14001c5f0  mov     rcx, r14; Str
0x14001c5f3  call    cs:__imp_wcsrchr
0x14001c5f9  mov     rbp, rax
0x14001c5fc  test    rax, rax
0x14001c5ff  jnz     short loc_14001C608
0x14001c601  mov     ebx, 0C000000Dh
0x14001c606  jmp     short loc_14001C5C2
0x14001c608  test    r13, r13
0x14001c60b  jz      short loc_14001C65A
0x14001c60d  mov     rcx, gs:60h
0x14001c616  sub     rbp, r14
0x14001c619  sar     rbp, 1
0x14001c61c  xor     edx, edx; Flags
0x14001c61e  mov     rcx, [rcx+30h]; HeapHandle
0x14001c622  lea     eax, [rbp+1]
0x14001c625  lea     r8, [rax+rax]; Size
0x14001c629  mov     [rsp+68h+Source], rax
0x14001c631  call    cs:__imp_RtlAllocateHeap
0x14001c637  mov     rsi, rax
0x14001c63a  test    rdi, rdi
0x14001c63d  jz      loc_14001C5BD
0x14001c643  mov     rdx, [rsp+68h+Source]; SizeInWords
0x14001c64b  mov     r8, r14; Source
0x14001c64e  mov     r9d, ebp; MaxCount
0x14001c651  mov     rcx, rax; Destination
0x14001c654  call    cs:__imp_wcsncpy_s
0x14001c65a  xor     ebp, ebp
0x14001c65c  test    r12, r12
0x14001c65f  jz      short loc_14001C665
0x14001c661  mov     [r12], rdi
0x14001c665  test    r13, r13
0x14001c668  jz      short loc_14001C66E
0x14001c66a  mov     [r13+0], rsi
0x14001c66e  test    r15, r15
0x14001c671  jz      short loc_14001C68B
0x14001c673  mov     rcx, gs:60h
0x14001c67c  mov     r8, r15; P
0x14001c67f  xor     edx, edx; Flags
0x14001c681  mov     rcx, [rcx+30h]; HeapHandle
0x14001c685  call    cs:__imp_RtlFreeHeap
0x14001c68b  test    ebx, ebx
0x14001c68d  jns     short loc_14001C6C9
0x14001c68f  test    rdi, rdi
0x14001c692  jz      short loc_14001C6AC
0x14001c694  mov     rcx, gs:60h
0x14001c69d  mov     r8, rdi; P
0x14001c6a0  xor     edx, edx; Flags
0x14001c6a2  mov     rcx, [rcx+30h]; HeapHandle
0x14001c6a6  call    cs:__imp_RtlFreeHeap
0x14001c6ac  test    rsi, rsi
0x14001c6af  jz      short loc_14001C6C9
0x14001c6b1  mov     rcx, gs:60h
0x14001c6ba  mov     r8, rsi; P
0x14001c6bd  xor     edx, edx; Flags
0x14001c6bf  mov     rcx, [rcx+30h]; HeapHandle
0x14001c6c3  call    cs:__imp_RtlFreeHeap
0x14001c6c9  mov     eax, ebx
0x14001c6cb  add     rsp, 28h
0x14001c6cf  pop     r15
0x14001c6d1  pop     r14
0x14001c6d3  pop     r13
0x14001c6d5  pop     r12
0x14001c6d7  pop     rdi
0x14001c6d8  pop     rsi
0x14001c6d9  pop     rbp
0x14001c6da  pop     rbx
0x14001c6db  retn
```
