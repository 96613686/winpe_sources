# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180014234`
- end: `0x18001430e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800141ac`

## callees

- `0x180014234`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800142d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001428f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001428f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800142de`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        _QWORD *a1)
{
  _QWORD *v1; // r15
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  _QWORD *v4; // r13
  void *v5; // r12
  __int64 v6; // rbp
  __int64 v7; // r14
  void *v8; // rbx
  HANDLE ProcessHeap; // rax
  void *v10; // rbx
  HANDLE v11; // rax
  HANDLE v12; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v5 = v3;
      v3 = (_QWORD *)v3[1];
      v6 = v4[5];
      v7 = v6 + 80LL * *((unsigned __int16 *)v4 + 24);
      while ( v6 != v7 )
      {
        v8 = *(void **)(v6 + 64);
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
        *(_QWORD *)(v6 + 64) = 0;
        *(_QWORD *)(v6 + 72) = 0;
        v6 += 80;
      }
      v10 = (void *)v4[5];
      v11 = GetProcessHeap();
      HeapFree(v11, 0, v10);
      *((_DWORD *)v4 + 12) = 0;
      v4[5] = 0;
      v12 = GetProcessHeap();
      HeapFree(v12, 0, v5);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180014234  push    rbx
0x180014236  push    rbp
0x180014237  push    rsi
0x180014238  push    rdi
0x180014239  push    r12
0x18001423b  push    r13
0x18001423d  push    r14
0x18001423f  push    r15
0x180014241  sub     rsp, 28h
0x180014245  lea     r15, [rcx+50h]
0x180014249  mov     rdi, rcx
0x18001424c  cmp     rcx, r15
0x18001424f  jz      loc_1800142FD
0x180014255  mov     rsi, [rdi]
0x180014258  jmp     loc_1800142E4
0x18001425d  mov     r13, rsi
0x180014260  mov     r12, rsi
0x180014263  mov     rsi, [rsi+8]
0x180014267  movzx   eax, word ptr [r13+30h]
0x18001426c  mov     rbp, [r13+28h]
0x180014270  lea     r14, [rax+rax*4]
0x180014274  shl     r14, 4
0x180014278  add     r14, rbp
0x18001427b  jmp     short loc_1800142A9
0x18001427d  mov     rbx, [rbp+40h]
0x180014281  call    cs:__imp_GetProcessHeap
0x180014287  mov     r8, rbx; lpMem
0x18001428a  xor     edx, edx; dwFlags
0x18001428c  mov     rcx, rax; hHeap
0x18001428f  call    cs:__imp_HeapFree
0x180014295  mov     qword ptr [rbp+40h], 0
0x18001429d  mov     qword ptr [rbp+48h], 0
0x1800142a5  add     rbp, 50h ; 'P'
0x1800142a9  cmp     rbp, r14
0x1800142ac  jnz     short loc_18001427D
0x1800142ae  mov     rbx, [r13+28h]
0x1800142b2  call    cs:__imp_GetProcessHeap
0x1800142b8  mov     r8, rbx; lpMem
0x1800142bb  xor     edx, edx; dwFlags
0x1800142bd  mov     rcx, rax; hHeap
0x1800142c0  call    cs:__imp_HeapFree
0x1800142c6  xor     eax, eax
0x1800142c8  mov     [r13+30h], eax
0x1800142cc  mov     [r13+28h], rax
0x1800142d0  call    cs:__imp_GetProcessHeap
0x1800142d6  mov     r8, r12; lpMem
0x1800142d9  xor     edx, edx; dwFlags
0x1800142db  mov     rcx, rax; hHeap
0x1800142de  call    cs:__imp_HeapFree
0x1800142e4  test    rsi, rsi
0x1800142e7  jnz     loc_18001425D
0x1800142ed  mov     [rdi], rsi
0x1800142f0  add     rdi, 8
0x1800142f4  cmp     rdi, r15
0x1800142f7  jnz     loc_180014255
0x1800142fd  add     rsp, 28h
0x180014301  pop     r15
0x180014303  pop     r14
0x180014305  pop     r13
0x180014307  pop     r12
0x180014309  pop     rdi
0x18001430a  pop     rsi
0x18001430b  pop     rbp
0x18001430c  pop     rbx
0x18001430d  retn
```
