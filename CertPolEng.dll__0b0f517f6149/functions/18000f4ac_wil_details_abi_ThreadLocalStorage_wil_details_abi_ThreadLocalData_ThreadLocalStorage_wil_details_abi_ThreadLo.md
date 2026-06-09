# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000f4ac`
- end: `0x18000f586`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f44c`

## callees

- `0x18000f4ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f4f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f52a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f548`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f4f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f52a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000f548`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f507`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f556`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f507`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f538`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000f556`

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
0x18000f4ac  push    rbx
0x18000f4ae  push    rbp
0x18000f4af  push    rsi
0x18000f4b0  push    rdi
0x18000f4b1  push    r12
0x18000f4b3  push    r13
0x18000f4b5  push    r14
0x18000f4b7  push    r15
0x18000f4b9  sub     rsp, 28h
0x18000f4bd  lea     r15, [rcx+50h]
0x18000f4c1  mov     rdi, rcx
0x18000f4c4  cmp     rcx, r15
0x18000f4c7  jz      loc_18000F575
0x18000f4cd  mov     rsi, [rdi]
0x18000f4d0  jmp     loc_18000F55C
0x18000f4d5  mov     r13, rsi
0x18000f4d8  mov     r12, rsi
0x18000f4db  mov     rsi, [rsi+8]
0x18000f4df  movzx   eax, word ptr [r13+30h]
0x18000f4e4  mov     rbp, [r13+28h]
0x18000f4e8  lea     r14, [rax+rax*4]
0x18000f4ec  shl     r14, 4
0x18000f4f0  add     r14, rbp
0x18000f4f3  jmp     short loc_18000F521
0x18000f4f5  mov     rbx, [rbp+40h]
0x18000f4f9  call    cs:__imp_GetProcessHeap
0x18000f4ff  mov     r8, rbx; lpMem
0x18000f502  xor     edx, edx; dwFlags
0x18000f504  mov     rcx, rax; hHeap
0x18000f507  call    cs:__imp_HeapFree
0x18000f50d  mov     qword ptr [rbp+40h], 0
0x18000f515  mov     qword ptr [rbp+48h], 0
0x18000f51d  add     rbp, 50h ; 'P'
0x18000f521  cmp     rbp, r14
0x18000f524  jnz     short loc_18000F4F5
0x18000f526  mov     rbx, [r13+28h]
0x18000f52a  call    cs:__imp_GetProcessHeap
0x18000f530  mov     r8, rbx; lpMem
0x18000f533  xor     edx, edx; dwFlags
0x18000f535  mov     rcx, rax; hHeap
0x18000f538  call    cs:__imp_HeapFree
0x18000f53e  xor     eax, eax
0x18000f540  mov     [r13+30h], eax
0x18000f544  mov     [r13+28h], rax
0x18000f548  call    cs:__imp_GetProcessHeap
0x18000f54e  mov     r8, r12; lpMem
0x18000f551  xor     edx, edx; dwFlags
0x18000f553  mov     rcx, rax; hHeap
0x18000f556  call    cs:__imp_HeapFree
0x18000f55c  test    rsi, rsi
0x18000f55f  jnz     loc_18000F4D5
0x18000f565  mov     [rdi], rsi
0x18000f568  add     rdi, 8
0x18000f56c  cmp     rdi, r15
0x18000f56f  jnz     loc_18000F4CD
0x18000f575  add     rsp, 28h
0x18000f579  pop     r15
0x18000f57b  pop     r14
0x18000f57d  pop     r13
0x18000f57f  pop     r12
0x18000f581  pop     rdi
0x18000f582  pop     rsi
0x18000f583  pop     rbp
0x18000f584  pop     rbx
0x18000f585  retn
```
