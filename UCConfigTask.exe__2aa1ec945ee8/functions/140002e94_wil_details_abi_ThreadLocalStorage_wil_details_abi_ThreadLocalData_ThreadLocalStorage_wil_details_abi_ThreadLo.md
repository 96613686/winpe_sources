# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140002e94`
- end: `0x140002f6e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140002ddc`

## callees

- `0x140002e94`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ee1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f30`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002ee1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f12`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002f30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002eef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f3e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002eef`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f20`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002f3e`

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
0x140002e94  push    rbx
0x140002e96  push    rbp
0x140002e97  push    rsi
0x140002e98  push    rdi
0x140002e99  push    r12
0x140002e9b  push    r13
0x140002e9d  push    r14
0x140002e9f  push    r15
0x140002ea1  sub     rsp, 28h
0x140002ea5  lea     r15, [rcx+50h]
0x140002ea9  mov     rdi, rcx
0x140002eac  cmp     rcx, r15
0x140002eaf  jz      loc_140002F5D
0x140002eb5  mov     rsi, [rdi]
0x140002eb8  jmp     loc_140002F44
0x140002ebd  mov     r13, rsi
0x140002ec0  mov     r12, rsi
0x140002ec3  mov     rsi, [rsi+8]
0x140002ec7  movzx   eax, word ptr [r13+30h]
0x140002ecc  mov     rbp, [r13+28h]
0x140002ed0  lea     r14, [rax+rax*4]
0x140002ed4  shl     r14, 4
0x140002ed8  add     r14, rbp
0x140002edb  jmp     short loc_140002F09
0x140002edd  mov     rbx, [rbp+40h]
0x140002ee1  call    cs:__imp_GetProcessHeap
0x140002ee7  mov     r8, rbx; lpMem
0x140002eea  xor     edx, edx; dwFlags
0x140002eec  mov     rcx, rax; hHeap
0x140002eef  call    cs:__imp_HeapFree
0x140002ef5  mov     qword ptr [rbp+40h], 0
0x140002efd  mov     qword ptr [rbp+48h], 0
0x140002f05  add     rbp, 50h ; 'P'
0x140002f09  cmp     rbp, r14
0x140002f0c  jnz     short loc_140002EDD
0x140002f0e  mov     rbx, [r13+28h]
0x140002f12  call    cs:__imp_GetProcessHeap
0x140002f18  mov     r8, rbx; lpMem
0x140002f1b  xor     edx, edx; dwFlags
0x140002f1d  mov     rcx, rax; hHeap
0x140002f20  call    cs:__imp_HeapFree
0x140002f26  xor     eax, eax
0x140002f28  mov     [r13+30h], eax
0x140002f2c  mov     [r13+28h], rax
0x140002f30  call    cs:__imp_GetProcessHeap
0x140002f36  mov     r8, r12; lpMem
0x140002f39  xor     edx, edx; dwFlags
0x140002f3b  mov     rcx, rax; hHeap
0x140002f3e  call    cs:__imp_HeapFree
0x140002f44  test    rsi, rsi
0x140002f47  jnz     loc_140002EBD
0x140002f4d  mov     [rdi], rsi
0x140002f50  add     rdi, 8
0x140002f54  cmp     rdi, r15
0x140002f57  jnz     loc_140002EB5
0x140002f5d  add     rsp, 28h
0x140002f61  pop     r15
0x140002f63  pop     r14
0x140002f65  pop     r13
0x140002f67  pop     r12
0x140002f69  pop     rdi
0x140002f6a  pop     rsi
0x140002f6b  pop     rbp
0x140002f6c  pop     rbx
0x140002f6d  retn
```
