# UddpGetFullPathFromImagePath

- ea: `0x180033024`
- end: `0x180033250`
- name: `UddpGetFullPathFromImagePath`
- size: `556`
- prototype: `__int64 __fastcall(LPCWCH lpString1)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004d604`

## callees

- `0x180012920`
- `0x180033024`

## import_xrefs

- `msvcrt!memcpy_s` at `0x1800331ff`
- `msvcrt!memcpy_s` at `0x1800331ff`
- `ntdll!RtlFreeHeap` at `0x180033242`
- `ntdll!RtlFreeHeap` at `0x180033242`
- `ntdll!RtlAllocateHeap` at `0x180033092`
- `ntdll!RtlAllocateHeap` at `0x18003319a`
- `ntdll!RtlAllocateHeap` at `0x180033092`
- `ntdll!RtlAllocateHeap` at `0x18003319a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003320a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180033161`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003320a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003306c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033105`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003313b`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003306c`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180033105`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18003313b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033152`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800331b8`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x180033152`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800331b8`

## string_xrefs

- `0x1800330b2`: `UddpGetFullPathFromImagePath`
- `0x18003321d`: `UddpGetFullPathFromImagePath`
- `0x18003316b`: `Failed to GetSystemWindowsDirectory [%d]`
- `0x180033210`: `Failed to GetSystemWindowsDirectory [%d]`

## pseudocode

```c
WCHAR *__fastcall UddpGetFullPathFromImagePath(LPCWCH lpString1)
{
  unsigned __int64 v1; // rbx
  SIZE_T v3; // rbx
  WCHAR *v4; // rax
  WCHAR *v5; // rsi
  int v6; // r8d
  LPCWCH v8; // r8
  rsize_t v9; // r9
  rsize_t v10; // rdx
  WCHAR *v11; // rcx
  LPCWCH v12; // r15
  UINT SystemWindowsDirectoryW; // eax
  UINT v14; // ebp
  unsigned __int64 v15; // r14
  WCHAR *Heap; // rax
  UINT v17; // eax
  UINT v18; // edx
  BOOL bIgnoreCase[2]; // [rsp+20h] [rbp-58h]

  v1 = -1;
  do
    ++v1;
  while ( lpString1[v1] );
  if ( v1 <= 4 || CompareStringOrdinal(lpString1, 4, L"\\??\\", 4, 1) != 2 )
  {
    if ( v1 > 0xC && CompareStringOrdinal(lpString1, 12, L"\\SystemRoot\\", 12, 1) == 2 )
    {
      v12 = lpString1 + 12;
      v1 -= 12LL;
    }
    else
    {
      v12 = lpString1;
      if ( v1 > 0xD && CompareStringOrdinal(lpString1, 13, L"%SystemRoot%\\", 13, 1) == 2 )
      {
        v12 = lpString1 + 13;
        v1 -= 13LL;
      }
    }
    SystemWindowsDirectoryW = GetSystemWindowsDirectoryW(0, 0);
    v14 = SystemWindowsDirectoryW;
    if ( !SystemWindowsDirectoryW )
    {
      v5 = 0;
      bIgnoreCase[0] = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"UddpGetFullPathFromImagePath",
        1852,
        (unsigned int)"Failed to GetSystemWindowsDirectory [%d]",
        *(_QWORD *)bIgnoreCase);
      return v5;
    }
    v15 = v1 + SystemWindowsDirectoryW + 1LL;
    Heap = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v15);
    v5 = Heap;
    if ( !Heap )
    {
      v6 = 1861;
      goto LABEL_7;
    }
    v17 = GetSystemWindowsDirectoryW(Heap, v14);
    v18 = v17;
    if ( !v17 || v17 > v14 - 1 )
    {
      bIgnoreCase[0] = GetLastError();
      AslLogCallPrintf(
        1,
        (unsigned int)"UddpGetFullPathFromImagePath",
        1869,
        (unsigned int)"Failed to GetSystemWindowsDirectory [%d]",
        *(_QWORD *)bIgnoreCase);
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v5);
      return 0;
    }
    if ( v5[v17 - 1] == 92 )
      v18 = v17 - 1;
    else
      v5[v17] = 92;
    v8 = v12;
    v9 = 2 * v1 + 2;
    v11 = &v5[v18 + 1];
    v10 = 2 * (v15 - (v18 + 1));
LABEL_26:
    memcpy_s(v11, v10, v8, v9);
    return v5;
  }
  v3 = 2 * v1 - 6;
  v4 = (WCHAR *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, v3);
  v5 = v4;
  if ( v4 )
  {
    v8 = lpString1 + 4;
    v9 = v3;
    v10 = v3;
    v11 = v4;
    goto LABEL_26;
  }
  v6 = 1810;
LABEL_7:
  AslLogCallPrintf(
    1,
    (unsigned int)"UddpGetFullPathFromImagePath",
    v6,
    (unsigned int)"Failed to allocate memory for '%ls'",
    lpString1);
  return v5;
}

```

## disassembly

```asm
0x180033024  push    rbx
0x180033026  push    rbp
0x180033027  push    rsi
0x180033028  push    rdi
0x180033029  push    r12
0x18003302b  push    r13
0x18003302d  push    r14
0x18003302f  push    r15
0x180033031  sub     rsp, 38h
0x180033035  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180033039  mov     rdi, rcx
0x18003303c  xor     r12d, r12d
0x18003303f  inc     rbx
0x180033042  cmp     [rcx+rbx*2], r12w
0x180033047  jnz     short loc_18003303F
0x180033049  mov     r13d, 1
0x18003304f  cmp     rbx, 4
0x180033053  jbe     loc_1800330E7
0x180033059  lea     r9d, [r13+3]; cchCount2
0x18003305d  mov     [rsp+78h+bIgnoreCase], r13d; bIgnoreCase
0x180033062  mov     edx, r9d; cchCount1
0x180033065  lea     r8, asc_1801034A0; "\\??\\"
0x18003306c  call    cs:__imp_CompareStringOrdinal
0x180033072  cmp     eax, 2
0x180033075  jnz     short loc_1800330E7
0x180033077  mov     rcx, gs:60h
0x180033080  lea     rbx, ds:0FFFFFFFFFFFFFFFAh[rbx*2]
0x180033088  mov     r8, rbx; Size
0x18003308b  lea     edx, [rax+6]; Flags
0x18003308e  mov     rcx, [rcx+30h]; HeapHandle
0x180033092  call    cs:__imp_RtlAllocateHeap
0x180033098  mov     rsi, rax
0x18003309b  test    rax, rax
0x18003309e  jnz     short loc_1800330D5
0x1800330a0  mov     r8d, 712h
0x1800330a6  lea     r9, aFailedToAlloca_1; "Failed to allocate memory for '%ls'"
0x1800330ad  mov     qword ptr [rsp+78h+bIgnoreCase], rdi
0x1800330b2  lea     rdx, aUddpgetfullpat; "UddpGetFullPathFromImagePath"
0x1800330b9  mov     ecx, r13d
0x1800330bc  call    AslLogCallPrintf
0x1800330c1  mov     rax, rsi
0x1800330c4  add     rsp, 38h
0x1800330c8  pop     r15
0x1800330ca  pop     r14
0x1800330cc  pop     r13
0x1800330ce  pop     r12
0x1800330d0  pop     rdi
0x1800330d1  pop     rsi
0x1800330d2  pop     rbp
0x1800330d3  pop     rbx
0x1800330d4  retn
0x1800330d5  lea     r8, [rdi+8]
0x1800330d9  mov     r9, rbx
0x1800330dc  mov     rdx, rbx
0x1800330df  mov     rcx, rax
0x1800330e2  jmp     loc_1800331FF
0x1800330e7  cmp     rbx, 0Ch
0x1800330eb  jbe     short loc_18003311A
0x1800330ed  mov     r9d, 0Ch; cchCount2
0x1800330f3  mov     [rsp+78h+bIgnoreCase], r13d; bIgnoreCase
0x1800330f8  mov     edx, r9d; cchCount1
0x1800330fb  lea     r8, aSystemroot_1; "\\SystemRoot\\"
0x180033102  mov     rcx, rdi; lpString1
0x180033105  call    cs:__imp_CompareStringOrdinal
0x18003310b  cmp     eax, 2
0x18003310e  jnz     short loc_18003311A
0x180033110  lea     r15, [rdi+18h]
0x180033114  add     rbx, 0FFFFFFFFFFFFFFF4h
0x180033118  jmp     short loc_18003314E
0x18003311a  mov     r15, rdi
0x18003311d  cmp     rbx, 0Dh
0x180033121  jbe     short loc_18003314E
0x180033123  mov     r9d, 0Dh; cchCount2
0x180033129  mov     [rsp+78h+bIgnoreCase], r13d; bIgnoreCase
0x18003312e  mov     edx, r9d; cchCount1
0x180033131  lea     r8, aSystemroot_2; "%SystemRoot%\\"
0x180033138  mov     rcx, rdi; lpString1
0x18003313b  call    cs:__imp_CompareStringOrdinal
0x180033141  cmp     eax, 2
0x180033144  jnz     short loc_18003314E
0x180033146  lea     r15, [rdi+1Ah]
0x18003314a  add     rbx, 0FFFFFFFFFFFFFFF3h
0x18003314e  xor     edx, edx; uSize
0x180033150  xor     ecx, ecx; lpBuffer
0x180033152  call    cs:__imp_GetSystemWindowsDirectoryW
0x180033158  mov     ebp, eax
0x18003315a  test    eax, eax
0x18003315c  jnz     short loc_18003317D
0x18003315e  mov     rsi, r12
0x180033161  call    cs:__imp_GetLastError
0x180033167  mov     [rsp+78h+bIgnoreCase], eax
0x18003316b  lea     r9, aFailedToGetsys; "Failed to GetSystemWindowsDirectory [%d"...
0x180033172  mov     r8d, 73Ch
0x180033178  jmp     loc_1800330B2
0x18003317d  mov     rcx, gs:60h
0x180033186  lea     r14, [rbp+1]
0x18003318a  add     r14, rbx
0x18003318d  mov     edx, 8; Flags
0x180033192  mov     rcx, [rcx+30h]; HeapHandle
0x180033196  lea     r8, [r14+r14]; Size
0x18003319a  call    cs:__imp_RtlAllocateHeap
0x1800331a0  mov     rsi, rax
0x1800331a3  test    rax, rax
0x1800331a6  jnz     short loc_1800331B3
0x1800331a8  mov     r8d, 745h
0x1800331ae  jmp     loc_1800330A6
0x1800331b3  mov     edx, ebp; uSize
0x1800331b5  mov     rcx, rsi; lpBuffer
0x1800331b8  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800331be  mov     edx, eax
0x1800331c0  test    eax, eax
0x1800331c2  jz      short loc_18003320A
0x1800331c4  lea     ecx, [rbp-1]
0x1800331c7  cmp     edx, ecx
0x1800331c9  ja      short loc_18003320A
0x1800331cb  lea     eax, [rdx-1]
0x1800331ce  mov     r8d, 5Ch ; '\'
0x1800331d4  cmp     r8w, [rsi+rax*2]
0x1800331d9  jnz     short loc_1800331DF
0x1800331db  mov     edx, eax
0x1800331dd  jmp     short loc_1800331E4
0x1800331df  mov     [rsi+rdx*2], r8w
0x1800331e4  lea     eax, [rdx+1]
0x1800331e7  mov     r8, r15; Source
0x1800331ea  mov     ecx, eax
0x1800331ec  lea     r9, ds:2[rbx*2]; SourceSize
0x1800331f4  sub     r14, rcx
0x1800331f7  lea     rcx, [rsi+rax*2]; Destination
0x1800331fb  lea     rdx, [r14+r14]; DestinationSize
0x1800331ff  call    cs:__imp_memcpy_s
0x180033205  jmp     loc_1800330C1
0x18003320a  call    cs:__imp_GetLastError
0x180033210  lea     r9, aFailedToGetsys; "Failed to GetSystemWindowsDirectory [%d"...
0x180033217  mov     r8d, 74Dh
0x18003321d  lea     rdx, aUddpgetfullpat; "UddpGetFullPathFromImagePath"
0x180033224  mov     [rsp+78h+bIgnoreCase], eax
0x180033228  mov     ecx, r13d
0x18003322b  call    AslLogCallPrintf
0x180033230  mov     rcx, gs:60h
0x180033239  mov     r8, rsi; P
0x18003323c  xor     edx, edx; Flags
0x18003323e  mov     rcx, [rcx+30h]; HeapHandle
0x180033242  call    cs:__imp_RtlFreeHeap
0x180033248  mov     rsi, r12
0x18003324b  jmp     loc_1800330C1
```
