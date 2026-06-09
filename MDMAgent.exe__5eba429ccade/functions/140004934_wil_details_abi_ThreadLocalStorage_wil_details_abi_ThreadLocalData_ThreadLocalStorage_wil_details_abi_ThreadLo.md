# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140004934`
- end: `0x140004a0e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400048ac`

## callees

- `0x140004934`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049d0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004981`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049b2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000498f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000498f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049de`

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
0x140004934  push    rbx
0x140004936  push    rbp
0x140004937  push    rsi
0x140004938  push    rdi
0x140004939  push    r12
0x14000493b  push    r13
0x14000493d  push    r14
0x14000493f  push    r15
0x140004941  sub     rsp, 28h
0x140004945  lea     r15, [rcx+50h]
0x140004949  mov     rdi, rcx
0x14000494c  cmp     rcx, r15
0x14000494f  jz      loc_1400049FD
0x140004955  mov     rsi, [rdi]
0x140004958  jmp     loc_1400049E4
0x14000495d  mov     r13, rsi
0x140004960  mov     r12, rsi
0x140004963  mov     rsi, [rsi+8]
0x140004967  movzx   eax, word ptr [r13+30h]
0x14000496c  mov     rbp, [r13+28h]
0x140004970  lea     r14, [rax+rax*4]
0x140004974  shl     r14, 4
0x140004978  add     r14, rbp
0x14000497b  jmp     short loc_1400049A9
0x14000497d  mov     rbx, [rbp+40h]
0x140004981  call    cs:__imp_GetProcessHeap
0x140004987  mov     r8, rbx; lpMem
0x14000498a  xor     edx, edx; dwFlags
0x14000498c  mov     rcx, rax; hHeap
0x14000498f  call    cs:__imp_HeapFree
0x140004995  mov     qword ptr [rbp+40h], 0
0x14000499d  mov     qword ptr [rbp+48h], 0
0x1400049a5  add     rbp, 50h ; 'P'
0x1400049a9  cmp     rbp, r14
0x1400049ac  jnz     short loc_14000497D
0x1400049ae  mov     rbx, [r13+28h]
0x1400049b2  call    cs:__imp_GetProcessHeap
0x1400049b8  mov     r8, rbx; lpMem
0x1400049bb  xor     edx, edx; dwFlags
0x1400049bd  mov     rcx, rax; hHeap
0x1400049c0  call    cs:__imp_HeapFree
0x1400049c6  xor     eax, eax
0x1400049c8  mov     [r13+30h], eax
0x1400049cc  mov     [r13+28h], rax
0x1400049d0  call    cs:__imp_GetProcessHeap
0x1400049d6  mov     r8, r12; lpMem
0x1400049d9  xor     edx, edx; dwFlags
0x1400049db  mov     rcx, rax; hHeap
0x1400049de  call    cs:__imp_HeapFree
0x1400049e4  test    rsi, rsi
0x1400049e7  jnz     loc_14000495D
0x1400049ed  mov     [rdi], rsi
0x1400049f0  add     rdi, 8
0x1400049f4  cmp     rdi, r15
0x1400049f7  jnz     loc_140004955
0x1400049fd  add     rsp, 28h
0x140004a01  pop     r15
0x140004a03  pop     r14
0x140004a05  pop     r13
0x140004a07  pop     r12
0x140004a09  pop     rdi
0x140004a0a  pop     rsi
0x140004a0b  pop     rbp
0x140004a0c  pop     rbx
0x140004a0d  retn
```
