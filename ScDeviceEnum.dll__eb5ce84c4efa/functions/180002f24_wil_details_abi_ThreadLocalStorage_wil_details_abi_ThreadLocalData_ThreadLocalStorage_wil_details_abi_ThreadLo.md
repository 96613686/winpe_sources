# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002f24`
- end: `0x180002ffe`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002e9c`

## callees

- `0x180002f24`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fce`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fa2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002fc0`

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
0x180002f24  push    rbx
0x180002f26  push    rbp
0x180002f27  push    rsi
0x180002f28  push    rdi
0x180002f29  push    r12
0x180002f2b  push    r13
0x180002f2d  push    r14
0x180002f2f  push    r15
0x180002f31  sub     rsp, 28h
0x180002f35  lea     r15, [rcx+50h]
0x180002f39  mov     rdi, rcx
0x180002f3c  cmp     rcx, r15
0x180002f3f  jz      loc_180002FED
0x180002f45  mov     rsi, [rdi]
0x180002f48  jmp     loc_180002FD4
0x180002f4d  mov     r13, rsi
0x180002f50  mov     r12, rsi
0x180002f53  mov     rsi, [rsi+8]
0x180002f57  movzx   eax, word ptr [r13+30h]
0x180002f5c  mov     rbp, [r13+28h]
0x180002f60  lea     r14, [rax+rax*4]
0x180002f64  shl     r14, 4
0x180002f68  add     r14, rbp
0x180002f6b  jmp     short loc_180002F99
0x180002f6d  mov     rbx, [rbp+40h]
0x180002f71  call    cs:__imp_GetProcessHeap
0x180002f77  mov     r8, rbx; lpMem
0x180002f7a  xor     edx, edx; dwFlags
0x180002f7c  mov     rcx, rax; hHeap
0x180002f7f  call    cs:__imp_HeapFree
0x180002f85  mov     qword ptr [rbp+40h], 0
0x180002f8d  mov     qword ptr [rbp+48h], 0
0x180002f95  add     rbp, 50h ; 'P'
0x180002f99  cmp     rbp, r14
0x180002f9c  jnz     short loc_180002F6D
0x180002f9e  mov     rbx, [r13+28h]
0x180002fa2  call    cs:__imp_GetProcessHeap
0x180002fa8  mov     r8, rbx; lpMem
0x180002fab  xor     edx, edx; dwFlags
0x180002fad  mov     rcx, rax; hHeap
0x180002fb0  call    cs:__imp_HeapFree
0x180002fb6  xor     eax, eax
0x180002fb8  mov     [r13+30h], eax
0x180002fbc  mov     [r13+28h], rax
0x180002fc0  call    cs:__imp_GetProcessHeap
0x180002fc6  mov     r8, r12; lpMem
0x180002fc9  xor     edx, edx; dwFlags
0x180002fcb  mov     rcx, rax; hHeap
0x180002fce  call    cs:__imp_HeapFree
0x180002fd4  test    rsi, rsi
0x180002fd7  jnz     loc_180002F4D
0x180002fdd  mov     [rdi], rsi
0x180002fe0  add     rdi, 8
0x180002fe4  cmp     rdi, r15
0x180002fe7  jnz     loc_180002F45
0x180002fed  add     rsp, 28h
0x180002ff1  pop     r15
0x180002ff3  pop     r14
0x180002ff5  pop     r13
0x180002ff7  pop     r12
0x180002ff9  pop     rdi
0x180002ffa  pop     rsi
0x180002ffb  pop     rbp
0x180002ffc  pop     rbx
0x180002ffd  retn
```
