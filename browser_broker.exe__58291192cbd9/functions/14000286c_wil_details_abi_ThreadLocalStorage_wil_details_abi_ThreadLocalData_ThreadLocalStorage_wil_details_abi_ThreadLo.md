# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000286c`
- end: `0x140002946`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400027e4`

## callees

- `0x14000286c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400028c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400028f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002916`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400028c7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400028f8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002916`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400028b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400028ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002908`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400028b9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400028ea`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002908`

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
0x14000286c  push    rbx
0x14000286e  push    rbp
0x14000286f  push    rsi
0x140002870  push    rdi
0x140002871  push    r12
0x140002873  push    r13
0x140002875  push    r14
0x140002877  push    r15
0x140002879  sub     rsp, 28h
0x14000287d  lea     r15, [rcx+50h]
0x140002881  mov     rdi, rcx
0x140002884  cmp     rcx, r15
0x140002887  jz      loc_140002935
0x14000288d  mov     rsi, [rdi]
0x140002890  jmp     loc_14000291C
0x140002895  mov     r13, rsi
0x140002898  mov     r12, rsi
0x14000289b  mov     rsi, [rsi+8]
0x14000289f  movzx   eax, word ptr [r13+30h]
0x1400028a4  mov     rbp, [r13+28h]
0x1400028a8  lea     r14, [rax+rax*4]
0x1400028ac  shl     r14, 4
0x1400028b0  add     r14, rbp
0x1400028b3  jmp     short loc_1400028E1
0x1400028b5  mov     rbx, [rbp+40h]
0x1400028b9  call    cs:__imp_GetProcessHeap
0x1400028bf  mov     r8, rbx; lpMem
0x1400028c2  xor     edx, edx; dwFlags
0x1400028c4  mov     rcx, rax; hHeap
0x1400028c7  call    cs:__imp_HeapFree
0x1400028cd  mov     qword ptr [rbp+40h], 0
0x1400028d5  mov     qword ptr [rbp+48h], 0
0x1400028dd  add     rbp, 50h ; 'P'
0x1400028e1  cmp     rbp, r14
0x1400028e4  jnz     short loc_1400028B5
0x1400028e6  mov     rbx, [r13+28h]
0x1400028ea  call    cs:__imp_GetProcessHeap
0x1400028f0  mov     r8, rbx; lpMem
0x1400028f3  xor     edx, edx; dwFlags
0x1400028f5  mov     rcx, rax; hHeap
0x1400028f8  call    cs:__imp_HeapFree
0x1400028fe  xor     eax, eax
0x140002900  mov     [r13+30h], eax
0x140002904  mov     [r13+28h], rax
0x140002908  call    cs:__imp_GetProcessHeap
0x14000290e  mov     r8, r12; lpMem
0x140002911  xor     edx, edx; dwFlags
0x140002913  mov     rcx, rax; hHeap
0x140002916  call    cs:__imp_HeapFree
0x14000291c  test    rsi, rsi
0x14000291f  jnz     loc_140002895
0x140002925  mov     [rdi], rsi
0x140002928  add     rdi, 8
0x14000292c  cmp     rdi, r15
0x14000292f  jnz     loc_14000288D
0x140002935  add     rsp, 28h
0x140002939  pop     r15
0x14000293b  pop     r14
0x14000293d  pop     r13
0x14000293f  pop     r12
0x140002941  pop     rdi
0x140002942  pop     rsi
0x140002943  pop     rbp
0x140002944  pop     rbx
0x140002945  retn
```
