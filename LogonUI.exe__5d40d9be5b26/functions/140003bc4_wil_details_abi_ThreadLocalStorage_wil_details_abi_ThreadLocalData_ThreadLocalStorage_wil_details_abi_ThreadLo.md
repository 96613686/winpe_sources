# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003bc4`
- end: `0x140003c9e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003b64`

## callees

- `0x140003bc4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c60`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c11`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c42`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003c60`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c6e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c1f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003c6e`

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
0x140003bc4  push    rbx
0x140003bc6  push    rbp
0x140003bc7  push    rsi
0x140003bc8  push    rdi
0x140003bc9  push    r12
0x140003bcb  push    r13
0x140003bcd  push    r14
0x140003bcf  push    r15
0x140003bd1  sub     rsp, 28h
0x140003bd5  lea     r15, [rcx+50h]
0x140003bd9  mov     rdi, rcx
0x140003bdc  cmp     rcx, r15
0x140003bdf  jz      loc_140003C8D
0x140003be5  mov     rsi, [rdi]
0x140003be8  jmp     loc_140003C74
0x140003bed  mov     r13, rsi
0x140003bf0  mov     r12, rsi
0x140003bf3  mov     rsi, [rsi+8]
0x140003bf7  movzx   eax, word ptr [r13+30h]
0x140003bfc  mov     rbp, [r13+28h]
0x140003c00  lea     r14, [rax+rax*4]
0x140003c04  shl     r14, 4
0x140003c08  add     r14, rbp
0x140003c0b  jmp     short loc_140003C39
0x140003c0d  mov     rbx, [rbp+40h]
0x140003c11  call    cs:__imp_GetProcessHeap
0x140003c17  mov     r8, rbx; lpMem
0x140003c1a  xor     edx, edx; dwFlags
0x140003c1c  mov     rcx, rax; hHeap
0x140003c1f  call    cs:__imp_HeapFree
0x140003c25  mov     qword ptr [rbp+40h], 0
0x140003c2d  mov     qword ptr [rbp+48h], 0
0x140003c35  add     rbp, 50h ; 'P'
0x140003c39  cmp     rbp, r14
0x140003c3c  jnz     short loc_140003C0D
0x140003c3e  mov     rbx, [r13+28h]
0x140003c42  call    cs:__imp_GetProcessHeap
0x140003c48  mov     r8, rbx; lpMem
0x140003c4b  xor     edx, edx; dwFlags
0x140003c4d  mov     rcx, rax; hHeap
0x140003c50  call    cs:__imp_HeapFree
0x140003c56  xor     eax, eax
0x140003c58  mov     [r13+30h], eax
0x140003c5c  mov     [r13+28h], rax
0x140003c60  call    cs:__imp_GetProcessHeap
0x140003c66  mov     r8, r12; lpMem
0x140003c69  xor     edx, edx; dwFlags
0x140003c6b  mov     rcx, rax; hHeap
0x140003c6e  call    cs:__imp_HeapFree
0x140003c74  test    rsi, rsi
0x140003c77  jnz     loc_140003BED
0x140003c7d  mov     [rdi], rsi
0x140003c80  add     rdi, 8
0x140003c84  cmp     rdi, r15
0x140003c87  jnz     loc_140003BE5
0x140003c8d  add     rsp, 28h
0x140003c91  pop     r15
0x140003c93  pop     r14
0x140003c95  pop     r13
0x140003c97  pop     r12
0x140003c99  pop     rdi
0x140003c9a  pop     rsi
0x140003c9b  pop     rbp
0x140003c9c  pop     rbx
0x140003c9d  retn
```
