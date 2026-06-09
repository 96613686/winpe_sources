# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800103f8`
- end: `0x1800104d2`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180010340`

## callees

- `0x1800103f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010476`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010494`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010445`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010476`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180010494`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010484`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104a2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010453`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180010484`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800104a2`

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
0x1800103f8  push    rbx
0x1800103fa  push    rbp
0x1800103fb  push    rsi
0x1800103fc  push    rdi
0x1800103fd  push    r12
0x1800103ff  push    r13
0x180010401  push    r14
0x180010403  push    r15
0x180010405  sub     rsp, 28h
0x180010409  lea     r15, [rcx+50h]
0x18001040d  mov     rdi, rcx
0x180010410  cmp     rcx, r15
0x180010413  jz      loc_1800104C1
0x180010419  mov     rsi, [rdi]
0x18001041c  jmp     loc_1800104A8
0x180010421  mov     r13, rsi
0x180010424  mov     r12, rsi
0x180010427  mov     rsi, [rsi+8]
0x18001042b  movzx   eax, word ptr [r13+30h]
0x180010430  mov     rbp, [r13+28h]
0x180010434  lea     r14, [rax+rax*4]
0x180010438  shl     r14, 4
0x18001043c  add     r14, rbp
0x18001043f  jmp     short loc_18001046D
0x180010441  mov     rbx, [rbp+40h]
0x180010445  call    cs:__imp_GetProcessHeap
0x18001044b  mov     r8, rbx; lpMem
0x18001044e  xor     edx, edx; dwFlags
0x180010450  mov     rcx, rax; hHeap
0x180010453  call    cs:__imp_HeapFree
0x180010459  mov     qword ptr [rbp+40h], 0
0x180010461  mov     qword ptr [rbp+48h], 0
0x180010469  add     rbp, 50h ; 'P'
0x18001046d  cmp     rbp, r14
0x180010470  jnz     short loc_180010441
0x180010472  mov     rbx, [r13+28h]
0x180010476  call    cs:__imp_GetProcessHeap
0x18001047c  mov     r8, rbx; lpMem
0x18001047f  xor     edx, edx; dwFlags
0x180010481  mov     rcx, rax; hHeap
0x180010484  call    cs:__imp_HeapFree
0x18001048a  xor     eax, eax
0x18001048c  mov     [r13+30h], eax
0x180010490  mov     [r13+28h], rax
0x180010494  call    cs:__imp_GetProcessHeap
0x18001049a  mov     r8, r12; lpMem
0x18001049d  xor     edx, edx; dwFlags
0x18001049f  mov     rcx, rax; hHeap
0x1800104a2  call    cs:__imp_HeapFree
0x1800104a8  test    rsi, rsi
0x1800104ab  jnz     loc_180010421
0x1800104b1  mov     [rdi], rsi
0x1800104b4  add     rdi, 8
0x1800104b8  cmp     rdi, r15
0x1800104bb  jnz     loc_180010419
0x1800104c1  add     rsp, 28h
0x1800104c5  pop     r15
0x1800104c7  pop     r14
0x1800104c9  pop     r13
0x1800104cb  pop     r12
0x1800104cd  pop     rdi
0x1800104ce  pop     rsi
0x1800104cf  pop     rbp
0x1800104d0  pop     rbx
0x1800104d1  retn
```
