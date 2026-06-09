# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800050b8`
- end: `0x180005192`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180005030`

## callees

- `0x1800050b8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005105`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005154`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005105`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005136`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005154`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005144`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005162`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005113`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005144`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005162`

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
0x1800050b8  push    rbx
0x1800050ba  push    rbp
0x1800050bb  push    rsi
0x1800050bc  push    rdi
0x1800050bd  push    r12
0x1800050bf  push    r13
0x1800050c1  push    r14
0x1800050c3  push    r15
0x1800050c5  sub     rsp, 28h
0x1800050c9  lea     r15, [rcx+50h]
0x1800050cd  mov     rdi, rcx
0x1800050d0  cmp     rcx, r15
0x1800050d3  jz      loc_180005181
0x1800050d9  mov     rsi, [rdi]
0x1800050dc  jmp     loc_180005168
0x1800050e1  mov     r13, rsi
0x1800050e4  mov     r12, rsi
0x1800050e7  mov     rsi, [rsi+8]
0x1800050eb  movzx   eax, word ptr [r13+30h]
0x1800050f0  mov     rbp, [r13+28h]
0x1800050f4  lea     r14, [rax+rax*4]
0x1800050f8  shl     r14, 4
0x1800050fc  add     r14, rbp
0x1800050ff  jmp     short loc_18000512D
0x180005101  mov     rbx, [rbp+40h]
0x180005105  call    cs:__imp_GetProcessHeap
0x18000510b  mov     r8, rbx; lpMem
0x18000510e  xor     edx, edx; dwFlags
0x180005110  mov     rcx, rax; hHeap
0x180005113  call    cs:__imp_HeapFree
0x180005119  mov     qword ptr [rbp+40h], 0
0x180005121  mov     qword ptr [rbp+48h], 0
0x180005129  add     rbp, 50h ; 'P'
0x18000512d  cmp     rbp, r14
0x180005130  jnz     short loc_180005101
0x180005132  mov     rbx, [r13+28h]
0x180005136  call    cs:__imp_GetProcessHeap
0x18000513c  mov     r8, rbx; lpMem
0x18000513f  xor     edx, edx; dwFlags
0x180005141  mov     rcx, rax; hHeap
0x180005144  call    cs:__imp_HeapFree
0x18000514a  xor     eax, eax
0x18000514c  mov     [r13+30h], eax
0x180005150  mov     [r13+28h], rax
0x180005154  call    cs:__imp_GetProcessHeap
0x18000515a  mov     r8, r12; lpMem
0x18000515d  xor     edx, edx; dwFlags
0x18000515f  mov     rcx, rax; hHeap
0x180005162  call    cs:__imp_HeapFree
0x180005168  test    rsi, rsi
0x18000516b  jnz     loc_1800050E1
0x180005171  mov     [rdi], rsi
0x180005174  add     rdi, 8
0x180005178  cmp     rdi, r15
0x18000517b  jnz     loc_1800050D9
0x180005181  add     rsp, 28h
0x180005185  pop     r15
0x180005187  pop     r14
0x180005189  pop     r13
0x18000518b  pop     r12
0x18000518d  pop     rdi
0x18000518e  pop     rsi
0x18000518f  pop     rbp
0x180005190  pop     rbx
0x180005191  retn
```
