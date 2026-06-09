# BwriteUnicodeToHeap

- ea: `0x18000c924`
- end: `0x18000ca11`
- name: `BwriteUnicodeToHeap`
- size: `237`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b504`

## callees

- `0x180007220`
- `0x18000aef4`
- `0x18000c924`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000c998`
- `KERNEL32!MultiByteToWideChar` at `0x18000c998`

## string_xrefs

- `0x18000c9d3`: `BwriteUnicodeToHeap`

## pseudocode

```c
__int64 __fastcall BwriteUnicodeToHeap(unsigned int *a1, int *a2, UINT a3, __int64 a4)
{
  __int64 v5; // rsi
  unsigned int v6; // r10d
  unsigned int v9; // r9d
  unsigned __int64 cchWideChar; // rcx
  unsigned int v11; // eax
  int v12; // eax
  int v14; // [rsp+60h] [rbp+8h] BYREF

  v5 = *(_QWORD *)a4;
  v6 = 2 * ((unsigned int)(*(_DWORD *)(a4 + 12) + 1) >> 1);
  *(_DWORD *)(a4 + 12) = v6;
  v9 = *a1;
  a2[1] = v6;
  if ( v9 + 1 < v9
    || (cchWideChar = 2LL * (v9 + 1), cchWideChar > 0xFFFFFFFF)
    || (v11 = *(_DWORD *)(a4 + 12), (unsigned int)cchWideChar + v11 < v11)
    || (unsigned int)cchWideChar + v11 > *(_DWORD *)(a4 + 8) )
  {
    WriteDbgTraceErrorGpd("BwriteUnicodeToHeap", "Heap exhausted - restart.");
    if ( *(int *)(a4 + 2220) < 2 )
    {
      *(_DWORD *)(a4 + 2220) = 2;
      *(_DWORD *)(a4 + 2224) = 2;
      *(_DWORD *)(a4 + 2216) = 0;
    }
    return 0;
  }
  else
  {
    v12 = 2 * MultiByteToWideChar(a3, 1u, (LPCCH)(v5 + a1[1]), v9, (LPWSTR)(v5 + v6), cchWideChar);
    *(_DWORD *)(a4 + 12) += v12;
    *a2 = v12;
    BwriteToHeap(&v14, &qword_18007D1D0, 2u, 1u, a4);
    return 1;
  }
}

```

## disassembly

```asm
0x18000c924  push    rbx
0x18000c926  push    rbp
0x18000c927  push    rsi
0x18000c928  push    rdi
0x18000c929  sub     rsp, 38h
0x18000c92d  mov     r10d, [r9+0Ch]
0x18000c931  mov     rbx, r9
0x18000c934  mov     rsi, [r9]
0x18000c937  inc     r10d
0x18000c93a  shr     r10d, 1
0x18000c93d  mov     ebp, r8d
0x18000c940  add     r10d, r10d
0x18000c943  mov     rdi, rdx
0x18000c946  mov     [r9+0Ch], r10d
0x18000c94a  mov     r11, rcx
0x18000c94d  mov     r9d, [rcx]; cbMultiByte
0x18000c950  mov     [rdx+4], r10d
0x18000c954  lea     eax, [r9+1]
0x18000c958  cmp     eax, r9d
0x18000c95b  jb      short loc_18000C9CC
0x18000c95d  mov     ecx, eax
0x18000c95f  mov     eax, 0FFFFFFFFh
0x18000c964  add     rcx, rcx
0x18000c967  cmp     rcx, rax
0x18000c96a  ja      short loc_18000C9CC
0x18000c96c  mov     eax, [rbx+0Ch]
0x18000c96f  lea     edx, [rcx+rax]
0x18000c972  cmp     edx, eax
0x18000c974  jb      short loc_18000C9CC
0x18000c976  cmp     edx, [rbx+8]
0x18000c979  ja      short loc_18000C9CC
0x18000c97b  mov     r8d, [r11+4]
0x18000c97f  mov     edx, 1; dwFlags
0x18000c984  mov     [rsp+58h+cchWideChar], ecx; cchWideChar
0x18000c988  add     r8, rsi; lpMultiByteStr
0x18000c98b  mov     eax, r10d
0x18000c98e  mov     ecx, ebp; CodePage
0x18000c990  add     rax, rsi
0x18000c993  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18000c998  call    cs:__imp_MultiByteToWideChar
0x18000c99e  mov     r9d, 1
0x18000c9a4  mov     [rsp+58h+lpWideCharStr], rbx
0x18000c9a9  add     eax, eax
0x18000c9ab  lea     rdx, qword_18007D1D0
0x18000c9b2  add     [rbx+0Ch], eax
0x18000c9b5  lea     rcx, [rsp+58h+arg_0]
0x18000c9ba  mov     [rdi], eax
0x18000c9bc  lea     r8d, [r9+1]
0x18000c9c0  call    BwriteToHeap
0x18000c9c5  mov     eax, 1
0x18000c9ca  jmp     short loc_18000CA08
0x18000c9cc  lea     rdx, aHeapExhaustedR; "Heap exhausted - restart."
0x18000c9d3  lea     rcx, aBwriteunicodet; "BwriteUnicodeToHeap"
0x18000c9da  call    WriteDbgTraceErrorGpd
0x18000c9df  cmp     dword ptr [rbx+8ACh], 2
0x18000c9e6  jge     short loc_18000CA06
0x18000c9e8  mov     dword ptr [rbx+8ACh], 2
0x18000c9f2  mov     dword ptr [rbx+8B0h], 2
0x18000c9fc  mov     dword ptr [rbx+8A8h], 0
0x18000ca06  xor     eax, eax
0x18000ca08  add     rsp, 38h
0x18000ca0c  pop     rdi
0x18000ca0d  pop     rsi
0x18000ca0e  pop     rbp
0x18000ca0f  pop     rbx
0x18000ca10  retn
```
