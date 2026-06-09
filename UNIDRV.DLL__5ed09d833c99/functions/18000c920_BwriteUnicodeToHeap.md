# BwriteUnicodeToHeap

- ea: `0x18000c920`
- end: `0x18000ca14`
- name: `BwriteUnicodeToHeap`
- size: `244`
- prototype: `__int64 __fastcall(unsigned int *, int *, UINT, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000b518`

## callees

- `0x180007150`
- `0x18000af00`
- `0x18000c920`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x18000c994`
- `KERNEL32!MultiByteToWideChar` at `0x18000c994`

## string_xrefs

- `0x18000c9d5`: `BwriteUnicodeToHeap`

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
    WriteDbgTraceErrorGpd((__int64)"BwriteUnicodeToHeap", "Heap exhausted - restart.");
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
    BwriteToHeap(&v14, &qword_18007F1D0, 2u, 1u, a4);
    return 1;
  }
}

```

## disassembly

```asm
0x18000c920  push    rbx
0x18000c922  push    rbp
0x18000c923  push    rsi
0x18000c924  push    rdi
0x18000c925  sub     rsp, 38h
0x18000c929  mov     r10d, [r9+0Ch]
0x18000c92d  mov     rbx, r9
0x18000c930  mov     rsi, [r9]
0x18000c933  inc     r10d
0x18000c936  shr     r10d, 1
0x18000c939  mov     ebp, r8d
0x18000c93c  add     r10d, r10d
0x18000c93f  mov     rdi, rdx
0x18000c942  mov     [r9+0Ch], r10d
0x18000c946  mov     r11, rcx
0x18000c949  mov     r9d, [rcx]; cbMultiByte
0x18000c94c  mov     [rdx+4], r10d
0x18000c950  lea     eax, [r9+1]
0x18000c954  cmp     eax, r9d
0x18000c957  jb      short loc_18000C9CE
0x18000c959  mov     ecx, eax
0x18000c95b  mov     eax, 0FFFFFFFFh
0x18000c960  add     rcx, rcx
0x18000c963  cmp     rcx, rax
0x18000c966  ja      short loc_18000C9CE
0x18000c968  mov     eax, [rbx+0Ch]
0x18000c96b  lea     edx, [rcx+rax]
0x18000c96e  cmp     edx, eax
0x18000c970  jb      short loc_18000C9CE
0x18000c972  cmp     edx, [rbx+8]
0x18000c975  ja      short loc_18000C9CE
0x18000c977  mov     r8d, [r11+4]
0x18000c97b  mov     edx, 1; dwFlags
0x18000c980  mov     [rsp+58h+cchWideChar], ecx; cchWideChar
0x18000c984  add     r8, rsi; lpMultiByteStr
0x18000c987  mov     eax, r10d
0x18000c98a  mov     ecx, ebp; CodePage
0x18000c98c  add     rax, rsi
0x18000c98f  mov     [rsp+58h+lpWideCharStr], rax; lpWideCharStr
0x18000c994  call    cs:__imp_MultiByteToWideChar
0x18000c99b  nop     dword ptr [rax+rax+00h]
0x18000c9a0  mov     r9d, 1
0x18000c9a6  mov     [rsp+58h+lpWideCharStr], rbx
0x18000c9ab  add     eax, eax
0x18000c9ad  lea     rdx, qword_18007F1D0
0x18000c9b4  add     [rbx+0Ch], eax
0x18000c9b7  lea     rcx, [rsp+58h+arg_0]
0x18000c9bc  mov     [rdi], eax
0x18000c9be  lea     r8d, [r9+1]
0x18000c9c2  call    BwriteToHeap
0x18000c9c7  mov     eax, 1
0x18000c9cc  jmp     short loc_18000CA0A
0x18000c9ce  lea     rdx, aHeapExhaustedR; "Heap exhausted - restart."
0x18000c9d5  lea     rcx, aBwriteunicodet; "BwriteUnicodeToHeap"
0x18000c9dc  call    WriteDbgTraceErrorGpd
0x18000c9e1  cmp     dword ptr [rbx+8ACh], 2
0x18000c9e8  jge     short loc_18000CA08
0x18000c9ea  mov     dword ptr [rbx+8ACh], 2
0x18000c9f4  mov     dword ptr [rbx+8B0h], 2
0x18000c9fe  mov     dword ptr [rbx+8A8h], 0
0x18000ca08  xor     eax, eax
0x18000ca0a  add     rsp, 38h
0x18000ca0e  pop     rdi
0x18000ca0f  pop     rsi
0x18000ca10  pop     rbp
0x18000ca11  pop     rbx
0x18000ca12  retn
```
