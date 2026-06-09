# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180004e6c`
- end: `0x180004f46`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004de4`

## callees

- `0x180004e6c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ef8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f16`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ec7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ef8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004f16`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f08`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eb9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004eea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004f08`

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
0x180004e6c  push    rbx
0x180004e6e  push    rbp
0x180004e6f  push    rsi
0x180004e70  push    rdi
0x180004e71  push    r12
0x180004e73  push    r13
0x180004e75  push    r14
0x180004e77  push    r15
0x180004e79  sub     rsp, 28h
0x180004e7d  lea     r15, [rcx+50h]
0x180004e81  mov     rdi, rcx
0x180004e84  cmp     rcx, r15
0x180004e87  jz      loc_180004F35
0x180004e8d  mov     rsi, [rdi]
0x180004e90  jmp     loc_180004F1C
0x180004e95  mov     r13, rsi
0x180004e98  mov     r12, rsi
0x180004e9b  mov     rsi, [rsi+8]
0x180004e9f  movzx   eax, word ptr [r13+30h]
0x180004ea4  mov     rbp, [r13+28h]
0x180004ea8  lea     r14, [rax+rax*4]
0x180004eac  shl     r14, 4
0x180004eb0  add     r14, rbp
0x180004eb3  jmp     short loc_180004EE1
0x180004eb5  mov     rbx, [rbp+40h]
0x180004eb9  call    cs:__imp_GetProcessHeap
0x180004ebf  mov     r8, rbx; lpMem
0x180004ec2  xor     edx, edx; dwFlags
0x180004ec4  mov     rcx, rax; hHeap
0x180004ec7  call    cs:__imp_HeapFree
0x180004ecd  mov     qword ptr [rbp+40h], 0
0x180004ed5  mov     qword ptr [rbp+48h], 0
0x180004edd  add     rbp, 50h ; 'P'
0x180004ee1  cmp     rbp, r14
0x180004ee4  jnz     short loc_180004EB5
0x180004ee6  mov     rbx, [r13+28h]
0x180004eea  call    cs:__imp_GetProcessHeap
0x180004ef0  mov     r8, rbx; lpMem
0x180004ef3  xor     edx, edx; dwFlags
0x180004ef5  mov     rcx, rax; hHeap
0x180004ef8  call    cs:__imp_HeapFree
0x180004efe  xor     eax, eax
0x180004f00  mov     [r13+30h], eax
0x180004f04  mov     [r13+28h], rax
0x180004f08  call    cs:__imp_GetProcessHeap
0x180004f0e  mov     r8, r12; lpMem
0x180004f11  xor     edx, edx; dwFlags
0x180004f13  mov     rcx, rax; hHeap
0x180004f16  call    cs:__imp_HeapFree
0x180004f1c  test    rsi, rsi
0x180004f1f  jnz     loc_180004E95
0x180004f25  mov     [rdi], rsi
0x180004f28  add     rdi, 8
0x180004f2c  cmp     rdi, r15
0x180004f2f  jnz     loc_180004E8D
0x180004f35  add     rsp, 28h
0x180004f39  pop     r15
0x180004f3b  pop     r14
0x180004f3d  pop     r13
0x180004f3f  pop     r12
0x180004f41  pop     rdi
0x180004f42  pop     rsi
0x180004f43  pop     rbp
0x180004f44  pop     rbx
0x180004f45  retn
```
