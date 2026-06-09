# BfspCompareObjects

- ea: `0x18004e384`
- end: `0x18004e53b`
- name: `BfspCompareObjects`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180050554`

## callees

- `0x18004e384`
- `0x18004f888`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e47f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18004e47f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18004e435`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18004e43e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18004e435`
- `api-ms-win-crt-private-l1-1-0!_o__wcsupr` at `0x18004e43e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e4b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e517`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e49c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e4b5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e4f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18004e517`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e4a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e509`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e48e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e4a7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e4ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18004e509`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18004e44d`
- `api-ms-win-core-rtlsupport-l1-1-0!RtlCompareMemory` at `0x18004e44d`

## pseudocode

```c
__int64 __fastcall BfspCompareObjects(__int64 a1, __int64 a2, __int64 a3, __int64 a4, char *a5)
{
  char v5; // r12
  __int64 v6; // r15
  unsigned int v8; // r14d
  SIZE_T v9; // rbx
  _DWORD *v10; // rdi
  int v11; // r14d
  _DWORD *v12; // rsi
  HANDLE ProcessHeap; // rax
  HANDLE v14; // rax
  HANDLE v15; // rax
  HANDLE v16; // rax
  void *Source1; // [rsp+20h] [rbp-10h] BYREF
  void *Source2; // [rsp+28h] [rbp-8h] BYREF
  __int64 v20; // [rsp+70h] [rbp+40h]
  int v21; // [rsp+80h] [rbp+50h] BYREF
  int v22; // [rsp+84h] [rbp+54h]
  SIZE_T Length; // [rsp+88h] [rbp+58h] BYREF

  v22 = HIDWORD(a3);
  v20 = a1;
  v5 = 0;
  v21 = 0;
  v6 = 0;
  LODWORD(Length) = 0;
  Source1 = 0;
  Source2 = 0;
  while ( 1 )
  {
    v8 = *((_DWORD *)CompareElementListOsLoader + v6);
    if ( (int)BfspGetBcdElementData(a1, v8, &Source1, &v21) < 0 )
    {
      v10 = Source1;
      goto LABEL_23;
    }
    if ( (int)BfspGetBcdElementData(a2, v8, &Source2, &Length) < 0 )
      break;
    v9 = (unsigned int)Length;
    if ( (_DWORD)Length != v21 )
      break;
    v10 = Source1;
    v11 = v8 & 0xF000000;
    v12 = Source2;
    if ( v11 == 0x2000000 )
    {
      _o__wcsupr(Source2);
      _o__wcsupr(v10);
    }
    if ( RtlCompareMemory(v10, v12, v9) != v9
      && (v11 != 0x1000000 || *v10 != 4 || *v12 != 4 || v10[5] != v12[5] || (unsigned int)_o__wcsicmp(v10 + 6, v12 + 6)) )
    {
      goto LABEL_20;
    }
    if ( v12 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v12);
    }
    if ( v10 )
    {
      v14 = GetProcessHeap();
      HeapFree(v14, 0, v10);
    }
    a1 = v20;
    v12 = 0;
    v10 = 0;
    Source2 = 0;
    v6 = (unsigned int)(v6 + 1);
    Source1 = 0;
    if ( (unsigned int)v6 >= 4 )
    {
      v5 = 1;
      goto LABEL_20;
    }
  }
  v10 = Source1;
  v12 = Source2;
LABEL_20:
  if ( v12 )
  {
    v15 = GetProcessHeap();
    HeapFree(v15, 0, v12);
  }
LABEL_23:
  if ( v10 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, v10);
  }
  *a5 = v5;
  return 0;
}

```

## disassembly

```asm
0x18004e384  mov     rax, rsp
0x18004e387  mov     [rax+10h], rbx
0x18004e38b  mov     [rax+20h], r9d
0x18004e38f  mov     [rax+18h], r8
0x18004e393  mov     [rax+8], rcx
0x18004e397  push    rbp
0x18004e398  push    rsi
0x18004e399  push    rdi
0x18004e39a  push    r12
0x18004e39c  push    r13
0x18004e39e  push    r14
0x18004e3a0  push    r15
0x18004e3a2  mov     rbp, rsp
0x18004e3a5  sub     rsp, 30h
0x18004e3a9  xor     r12b, r12b
0x18004e3ac  mov     [rbp+arg_10], 0
0x18004e3b3  xor     r15d, r15d
0x18004e3b6  mov     dword ptr [rbp+Length], 0
0x18004e3bd  mov     r13, rdx
0x18004e3c0  mov     [rbp+Source1], 0
0x18004e3c8  mov     [rbp+Source2], 0
0x18004e3d0  lea     r14, CompareElementListOsLoader
0x18004e3d7  mov     r14d, [r14+r15*4]
0x18004e3db  lea     r9, [rbp+arg_10]
0x18004e3df  mov     edx, r14d
0x18004e3e2  lea     r8, [rbp+Source1]
0x18004e3e6  call    BfspGetBcdElementData
0x18004e3eb  test    eax, eax
0x18004e3ed  js      loc_18004E500
0x18004e3f3  lea     r9, [rbp+Length]
0x18004e3f7  mov     edx, r14d
0x18004e3fa  lea     r8, [rbp+Source2]
0x18004e3fe  mov     rcx, r13
0x18004e401  call    BfspGetBcdElementData
0x18004e406  test    eax, eax
0x18004e408  js      loc_18004E4DD
0x18004e40e  mov     ebx, dword ptr [rbp+Length]
0x18004e411  cmp     ebx, [rbp+arg_10]
0x18004e414  jnz     loc_18004E4DD
0x18004e41a  mov     rdi, [rbp+Source1]
0x18004e41e  and     r14d, 0F000000h
0x18004e425  mov     rsi, [rbp+Source2]
0x18004e429  cmp     r14d, 2000000h
0x18004e430  jnz     short loc_18004E444
0x18004e432  mov     rcx, rsi
0x18004e435  call    cs:__imp__o__wcsupr
0x18004e43b  mov     rcx, rdi
0x18004e43e  call    cs:__imp__o__wcsupr
0x18004e444  mov     r8, rbx; Length
0x18004e447  mov     rdx, rsi; Source2
0x18004e44a  mov     rcx, rdi; Source1
0x18004e44d  call    cs:__imp_RtlCompareMemory
0x18004e453  cmp     rax, rbx
0x18004e456  jz      short loc_18004E489
0x18004e458  cmp     r14d, 1000000h
0x18004e45f  jnz     loc_18004E4E5
0x18004e465  cmp     dword ptr [rdi], 4
0x18004e468  jnz     short loc_18004E4E5
0x18004e46a  cmp     dword ptr [rsi], 4
0x18004e46d  jnz     short loc_18004E4E5
0x18004e46f  mov     eax, [rsi+14h]
0x18004e472  cmp     [rdi+14h], eax
0x18004e475  jnz     short loc_18004E4E5
0x18004e477  lea     rdx, [rsi+18h]
0x18004e47b  lea     rcx, [rdi+18h]
0x18004e47f  call    cs:__imp__o__wcsicmp
0x18004e485  test    eax, eax
0x18004e487  jnz     short loc_18004E4E5
0x18004e489  test    rsi, rsi
0x18004e48c  jz      short loc_18004E4A2
0x18004e48e  call    cs:__imp_GetProcessHeap
0x18004e494  mov     r8, rsi; lpMem
0x18004e497  xor     edx, edx; dwFlags
0x18004e499  mov     rcx, rax; hHeap
0x18004e49c  call    cs:__imp_HeapFree
0x18004e4a2  test    rdi, rdi
0x18004e4a5  jz      short loc_18004E4BB
0x18004e4a7  call    cs:__imp_GetProcessHeap
0x18004e4ad  mov     r8, rdi; lpMem
0x18004e4b0  xor     edx, edx; dwFlags
0x18004e4b2  mov     rcx, rax; hHeap
0x18004e4b5  call    cs:__imp_HeapFree
0x18004e4bb  mov     rcx, [rbp+arg_0]
0x18004e4bf  xor     esi, esi
0x18004e4c1  xor     edi, edi
0x18004e4c3  mov     [rbp+Source2], rsi
0x18004e4c7  inc     r15d
0x18004e4ca  mov     [rbp+Source1], rdi
0x18004e4ce  cmp     r15d, 4
0x18004e4d2  jb      loc_18004E3D0
0x18004e4d8  mov     r12b, 1
0x18004e4db  jmp     short loc_18004E4E5
0x18004e4dd  mov     rdi, [rbp+Source1]
0x18004e4e1  mov     rsi, [rbp+Source2]
0x18004e4e5  test    rsi, rsi
0x18004e4e8  jz      short loc_18004E504
0x18004e4ea  call    cs:__imp_GetProcessHeap
0x18004e4f0  mov     r8, rsi; lpMem
0x18004e4f3  xor     edx, edx; dwFlags
0x18004e4f5  mov     rcx, rax; hHeap
0x18004e4f8  call    cs:__imp_HeapFree
0x18004e4fe  jmp     short loc_18004E504
0x18004e500  mov     rdi, [rbp+Source1]
0x18004e504  test    rdi, rdi
0x18004e507  jz      short loc_18004E51D
0x18004e509  call    cs:__imp_GetProcessHeap
0x18004e50f  mov     r8, rdi; lpMem
0x18004e512  xor     edx, edx; dwFlags
0x18004e514  mov     rcx, rax; hHeap
0x18004e517  call    cs:__imp_HeapFree
0x18004e51d  mov     rax, [rbp+arg_20]
0x18004e521  mov     rbx, [rsp+30h+arg_8]
0x18004e526  mov     [rax], r12b
0x18004e529  xor     eax, eax
0x18004e52b  add     rsp, 30h
0x18004e52f  pop     r15
0x18004e531  pop     r14
0x18004e533  pop     r13
0x18004e535  pop     r12
0x18004e537  pop     rdi
0x18004e538  pop     rsi
0x18004e539  pop     rbp
0x18004e53a  retn
```
