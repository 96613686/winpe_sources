# BuildPath

- ea: `0x18002d79c`
- end: `0x18002d96b`
- name: `BuildPath`
- size: `463`
- prototype: `__int64 __fastcall(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18002dbac`
- `0x18002ec30`
- `0x18002ec90`

## callees

- `0x18002d79c`
- `0x18002d974`
- `0x18002da5c`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x18002d92a`
- `ntdll!RtlFreeHeap` at `0x18002d92a`
- `ntdll!RtlAllocateHeap` at `0x18002d84a`
- `ntdll!RtlAllocateHeap` at `0x18002d84a`

## pseudocode

```c
wchar_t *__fastcall BuildPath(STRSAFE_PCNZWCH pszSrc, STRSAFE_PCNZWCH a2)
{
  const wchar_t *v2; // rsi
  __int64 v4; // rbx
  int v5; // r14d
  __int64 v6; // rdi
  int v7; // eax
  STRSAFE_PCNZWCH v8; // rax
  __int64 v9; // rcx
  size_t v10; // r12
  wchar_t *Heap; // r15
  HRESULT v12; // eax
  unsigned __int16 v13; // di
  HRESULT v14; // eax
  HRESULT v15; // eax
  DWORD v17; // [rsp+30h] [rbp-48h]
  DWORD v18; // [rsp+30h] [rbp-48h]
  size_t cchDest; // [rsp+80h] [rbp+8h] BYREF
  STRSAFE_LPWSTR pszDest; // [rsp+90h] [rbp+18h] BYREF

  v2 = a2;
  pszDest = 0;
  cchDest = 0;
  if ( pszSrc && a2 )
  {
    v4 = -1;
    v5 = 0;
    v6 = -1;
    do
      ++v6;
    while ( pszSrc[v6] );
    do
      ++v4;
    while ( a2[v4] );
    if ( (_DWORD)v6 )
    {
      if ( pszSrc[(unsigned int)(v6 - 1)] == 92 )
      {
        v7 = v4 - 1;
        if ( *a2 != 92 )
          v7 = v4;
        LODWORD(v4) = v7;
        v8 = a2 + 1;
        if ( *a2 != 92 )
          v8 = a2;
        v2 = v8;
      }
      else if ( *a2 != 92 )
      {
        v5 = 1;
      }
    }
    v9 = (unsigned int)(v6 + v5 + v4 + 1);
    v10 = (unsigned int)v9;
    Heap = (wchar_t *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v9);
    if ( Heap )
    {
      v12 = StringCchCopyNExW(Heap, v10, pszSrc, (unsigned int)v6, &pszDest, &cchDest, v17);
      v13 = v12;
      if ( v12 >= 0 )
      {
        if ( !v5 || (v14 = StringCchCopyNExW(pszDest, cchDest, L"\\", 1u, &pszDest, &cchDest, v18), v13 = v14, v14 >= 0) )
        {
          v15 = StringCchCopyNW(pszDest, cchDest, v2, (unsigned int)v4);
          v13 = v15;
          if ( v15 >= 0 )
          {
            NtCurrentTeb()->LastErrorValue = 0;
            return Heap;
          }
        }
      }
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, Heap);
      NtCurrentTeb()->LastErrorValue = v13;
    }
    else
    {
      NtCurrentTeb()->LastErrorValue = 8;
    }
  }
  else
  {
    NtCurrentTeb()->LastErrorValue = 87;
  }
  return 0;
}

```

## disassembly

```asm
0x18002d79c  mov     rax, rsp
0x18002d79f  mov     [rax+10h], rbx
0x18002d7a3  push    rbp
0x18002d7a4  push    rsi
0x18002d7a5  push    rdi
0x18002d7a6  push    r12
0x18002d7a8  push    r13
0x18002d7aa  push    r14
0x18002d7ac  push    r15
0x18002d7ae  sub     rsp, 40h
0x18002d7b2  xor     r13d, r13d
0x18002d7b5  mov     rsi, rdx
0x18002d7b8  mov     [rax+18h], r13
0x18002d7bc  mov     rbp, rcx
0x18002d7bf  mov     [rax+8], r13
0x18002d7c3  test    rcx, rcx
0x18002d7c6  jz      loc_18002D941
0x18002d7cc  test    rdx, rdx
0x18002d7cf  jz      loc_18002D941
0x18002d7d5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18002d7d9  mov     r14d, r13d
0x18002d7dc  mov     rdi, rbx
0x18002d7df  inc     rdi
0x18002d7e2  cmp     [rcx+rdi*2], r13w
0x18002d7e7  jnz     short loc_18002D7DF
0x18002d7e9  inc     rbx
0x18002d7ec  cmp     [rdx+rbx*2], r13w
0x18002d7f1  jnz     short loc_18002D7E9
0x18002d7f3  mov     r8d, 1
0x18002d7f9  test    edi, edi
0x18002d7fb  jz      short loc_18002D829
0x18002d7fd  lea     eax, [rdi-1]
0x18002d800  lea     edx, [r8+5Bh]
0x18002d804  cmp     dx, [rcx+rax*2]
0x18002d808  jnz     short loc_18002D822
0x18002d80a  cmp     dx, [rsi]
0x18002d80d  lea     eax, [rbx-1]
0x18002d810  cmovnz  eax, ebx
0x18002d813  mov     ebx, eax
0x18002d815  lea     rax, [rsi+2]
0x18002d819  cmovnz  rax, rsi
0x18002d81d  mov     rsi, rax
0x18002d820  jmp     short loc_18002D829
0x18002d822  cmp     dx, [rsi]
0x18002d825  cmovnz  r14d, r8d
0x18002d829  lea     ecx, [rbx+1]
0x18002d82c  mov     edx, 8; Flags
0x18002d831  add     ecx, r14d
0x18002d834  add     ecx, edi
0x18002d836  mov     r12d, ecx
0x18002d839  lea     r8, [rcx+rcx]; Size
0x18002d83d  mov     rcx, gs:60h
0x18002d846  mov     rcx, [rcx+30h]; HeapHandle
0x18002d84a  call    cs:__imp_RtlAllocateHeap
0x18002d850  mov     r15, rax
0x18002d853  test    rax, rax
0x18002d856  jnz     short loc_18002D86D
0x18002d858  mov     rax, gs:30h
0x18002d861  mov     dword ptr [rax+68h], 8
0x18002d868  jmp     loc_18002D951
0x18002d86d  lea     rax, [rsp+78h+cchDest]
0x18002d875  mov     r9d, edi; cchToCopy
0x18002d878  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x18002d87d  mov     r8, rbp; pszSrc
0x18002d880  lea     rax, [rsp+78h+pszDest]
0x18002d888  mov     rdx, r12; cchDest
0x18002d88b  mov     rcx, r15; pszDest
0x18002d88e  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x18002d893  call    StringCchCopyNExW
0x18002d898  mov     edi, eax
0x18002d89a  test    eax, eax
0x18002d89c  js      short loc_18002D918
0x18002d89e  test    r14d, r14d
0x18002d8a1  jz      short loc_18002D8E5
0x18002d8a3  mov     rdx, [rsp+78h+cchDest]; cchDest
0x18002d8ab  lea     rax, [rsp+78h+cchDest]
0x18002d8b3  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18002d8bb  lea     r8, pszSrc; "\\"
0x18002d8c2  mov     [rsp+78h+pcchRemaining], rax; pcchRemaining
0x18002d8c7  mov     r9d, 1; cchToCopy
0x18002d8cd  lea     rax, [rsp+78h+pszDest]
0x18002d8d5  mov     [rsp+78h+ppszDestEnd], rax; ppszDestEnd
0x18002d8da  call    StringCchCopyNExW
0x18002d8df  mov     edi, eax
0x18002d8e1  test    eax, eax
0x18002d8e3  js      short loc_18002D918
0x18002d8e5  mov     rdx, [rsp+78h+cchDest]; cchDest
0x18002d8ed  mov     r8, rsi; pszSrc
0x18002d8f0  mov     rcx, [rsp+78h+pszDest]; pszDest
0x18002d8f8  mov     r9d, ebx; cchToCopy
0x18002d8fb  call    StringCchCopyNW
0x18002d900  mov     edi, eax
0x18002d902  test    eax, eax
0x18002d904  js      short loc_18002D918
0x18002d906  mov     rax, gs:30h
0x18002d90f  mov     [rax+68h], r13d
0x18002d913  mov     rax, r15
0x18002d916  jmp     short loc_18002D953
0x18002d918  mov     rcx, gs:60h
0x18002d921  mov     r8, r15; P
0x18002d924  xor     edx, edx; Flags
0x18002d926  mov     rcx, [rcx+30h]; HeapHandle
0x18002d92a  call    cs:__imp_RtlFreeHeap
0x18002d930  mov     rax, gs:30h
0x18002d939  movzx   ecx, di
0x18002d93c  mov     [rax+68h], ecx
0x18002d93f  jmp     short loc_18002D951
0x18002d941  mov     rax, gs:30h
0x18002d94a  mov     dword ptr [rax+68h], 57h ; 'W'
0x18002d951  xor     eax, eax
0x18002d953  mov     rbx, [rsp+78h+arg_8]
0x18002d95b  add     rsp, 40h
0x18002d95f  pop     r15
0x18002d961  pop     r14
0x18002d963  pop     r13
0x18002d965  pop     r12
0x18002d967  pop     rdi
0x18002d968  pop     rsi
0x18002d969  pop     rbp
0x18002d96a  retn
```
