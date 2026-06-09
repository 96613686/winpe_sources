# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140004da4`
- end: `0x140004e7e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004d44`

## callees

- `0x140004da4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004dff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e4e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004dff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e30`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004e4e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e40`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004df1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e22`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004e40`

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
0x140004da4  push    rbx
0x140004da6  push    rbp
0x140004da7  push    rsi
0x140004da8  push    rdi
0x140004da9  push    r12
0x140004dab  push    r13
0x140004dad  push    r14
0x140004daf  push    r15
0x140004db1  sub     rsp, 28h
0x140004db5  lea     r15, [rcx+50h]
0x140004db9  mov     rdi, rcx
0x140004dbc  cmp     rcx, r15
0x140004dbf  jz      loc_140004E6D
0x140004dc5  mov     rsi, [rdi]
0x140004dc8  jmp     loc_140004E54
0x140004dcd  mov     r13, rsi
0x140004dd0  mov     r12, rsi
0x140004dd3  mov     rsi, [rsi+8]
0x140004dd7  movzx   eax, word ptr [r13+30h]
0x140004ddc  mov     rbp, [r13+28h]
0x140004de0  lea     r14, [rax+rax*4]
0x140004de4  shl     r14, 4
0x140004de8  add     r14, rbp
0x140004deb  jmp     short loc_140004E19
0x140004ded  mov     rbx, [rbp+40h]
0x140004df1  call    cs:__imp_GetProcessHeap
0x140004df7  mov     r8, rbx; lpMem
0x140004dfa  xor     edx, edx; dwFlags
0x140004dfc  mov     rcx, rax; hHeap
0x140004dff  call    cs:__imp_HeapFree
0x140004e05  mov     qword ptr [rbp+40h], 0
0x140004e0d  mov     qword ptr [rbp+48h], 0
0x140004e15  add     rbp, 50h ; 'P'
0x140004e19  cmp     rbp, r14
0x140004e1c  jnz     short loc_140004DED
0x140004e1e  mov     rbx, [r13+28h]
0x140004e22  call    cs:__imp_GetProcessHeap
0x140004e28  mov     r8, rbx; lpMem
0x140004e2b  xor     edx, edx; dwFlags
0x140004e2d  mov     rcx, rax; hHeap
0x140004e30  call    cs:__imp_HeapFree
0x140004e36  xor     eax, eax
0x140004e38  mov     [r13+30h], eax
0x140004e3c  mov     [r13+28h], rax
0x140004e40  call    cs:__imp_GetProcessHeap
0x140004e46  mov     r8, r12; lpMem
0x140004e49  xor     edx, edx; dwFlags
0x140004e4b  mov     rcx, rax; hHeap
0x140004e4e  call    cs:__imp_HeapFree
0x140004e54  test    rsi, rsi
0x140004e57  jnz     loc_140004DCD
0x140004e5d  mov     [rdi], rsi
0x140004e60  add     rdi, 8
0x140004e64  cmp     rdi, r15
0x140004e67  jnz     loc_140004DC5
0x140004e6d  add     rsp, 28h
0x140004e71  pop     r15
0x140004e73  pop     r14
0x140004e75  pop     r13
0x140004e77  pop     r12
0x140004e79  pop     rdi
0x140004e7a  pop     rsi
0x140004e7b  pop     rbp
0x140004e7c  pop     rbx
0x140004e7d  retn
```
