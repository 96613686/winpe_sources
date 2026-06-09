# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180015f10`
- end: `0x180015fea`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015eb0`

## callees

- `0x180015f10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015f9c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015fba`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fac`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015f8e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015fac`

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
0x180015f10  push    rbx
0x180015f12  push    rbp
0x180015f13  push    rsi
0x180015f14  push    rdi
0x180015f15  push    r12
0x180015f17  push    r13
0x180015f19  push    r14
0x180015f1b  push    r15
0x180015f1d  sub     rsp, 28h
0x180015f21  lea     r15, [rcx+50h]
0x180015f25  mov     rdi, rcx
0x180015f28  cmp     rcx, r15
0x180015f2b  jz      loc_180015FD9
0x180015f31  mov     rsi, [rdi]
0x180015f34  jmp     loc_180015FC0
0x180015f39  mov     r13, rsi
0x180015f3c  mov     r12, rsi
0x180015f3f  mov     rsi, [rsi+8]
0x180015f43  movzx   eax, word ptr [r13+30h]
0x180015f48  mov     rbp, [r13+28h]
0x180015f4c  lea     r14, [rax+rax*4]
0x180015f50  shl     r14, 4
0x180015f54  add     r14, rbp
0x180015f57  jmp     short loc_180015F85
0x180015f59  mov     rbx, [rbp+40h]
0x180015f5d  call    cs:__imp_GetProcessHeap
0x180015f63  mov     r8, rbx; lpMem
0x180015f66  xor     edx, edx; dwFlags
0x180015f68  mov     rcx, rax; hHeap
0x180015f6b  call    cs:__imp_HeapFree
0x180015f71  mov     qword ptr [rbp+40h], 0
0x180015f79  mov     qword ptr [rbp+48h], 0
0x180015f81  add     rbp, 50h ; 'P'
0x180015f85  cmp     rbp, r14
0x180015f88  jnz     short loc_180015F59
0x180015f8a  mov     rbx, [r13+28h]
0x180015f8e  call    cs:__imp_GetProcessHeap
0x180015f94  mov     r8, rbx; lpMem
0x180015f97  xor     edx, edx; dwFlags
0x180015f99  mov     rcx, rax; hHeap
0x180015f9c  call    cs:__imp_HeapFree
0x180015fa2  xor     eax, eax
0x180015fa4  mov     [r13+30h], eax
0x180015fa8  mov     [r13+28h], rax
0x180015fac  call    cs:__imp_GetProcessHeap
0x180015fb2  mov     r8, r12; lpMem
0x180015fb5  xor     edx, edx; dwFlags
0x180015fb7  mov     rcx, rax; hHeap
0x180015fba  call    cs:__imp_HeapFree
0x180015fc0  test    rsi, rsi
0x180015fc3  jnz     loc_180015F39
0x180015fc9  mov     [rdi], rsi
0x180015fcc  add     rdi, 8
0x180015fd0  cmp     rdi, r15
0x180015fd3  jnz     loc_180015F31
0x180015fd9  add     rsp, 28h
0x180015fdd  pop     r15
0x180015fdf  pop     r14
0x180015fe1  pop     r13
0x180015fe3  pop     r12
0x180015fe5  pop     rdi
0x180015fe6  pop     rsi
0x180015fe7  pop     rbp
0x180015fe8  pop     rbx
0x180015fe9  retn
```
