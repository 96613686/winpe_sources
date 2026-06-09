# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180017368`
- end: `0x180017442`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800172b0`

## callees

- `0x180017368`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017412`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800173f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017412`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017404`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800173e6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017404`

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
0x180017368  push    rbx
0x18001736a  push    rbp
0x18001736b  push    rsi
0x18001736c  push    rdi
0x18001736d  push    r12
0x18001736f  push    r13
0x180017371  push    r14
0x180017373  push    r15
0x180017375  sub     rsp, 28h
0x180017379  lea     r15, [rcx+50h]
0x18001737d  mov     rdi, rcx
0x180017380  cmp     rcx, r15
0x180017383  jz      loc_180017431
0x180017389  mov     rsi, [rdi]
0x18001738c  jmp     loc_180017418
0x180017391  mov     r13, rsi
0x180017394  mov     r12, rsi
0x180017397  mov     rsi, [rsi+8]
0x18001739b  movzx   eax, word ptr [r13+30h]
0x1800173a0  mov     rbp, [r13+28h]
0x1800173a4  lea     r14, [rax+rax*4]
0x1800173a8  shl     r14, 4
0x1800173ac  add     r14, rbp
0x1800173af  jmp     short loc_1800173DD
0x1800173b1  mov     rbx, [rbp+40h]
0x1800173b5  call    cs:__imp_GetProcessHeap
0x1800173bb  mov     r8, rbx; lpMem
0x1800173be  xor     edx, edx; dwFlags
0x1800173c0  mov     rcx, rax; hHeap
0x1800173c3  call    cs:__imp_HeapFree
0x1800173c9  mov     qword ptr [rbp+40h], 0
0x1800173d1  mov     qword ptr [rbp+48h], 0
0x1800173d9  add     rbp, 50h ; 'P'
0x1800173dd  cmp     rbp, r14
0x1800173e0  jnz     short loc_1800173B1
0x1800173e2  mov     rbx, [r13+28h]
0x1800173e6  call    cs:__imp_GetProcessHeap
0x1800173ec  mov     r8, rbx; lpMem
0x1800173ef  xor     edx, edx; dwFlags
0x1800173f1  mov     rcx, rax; hHeap
0x1800173f4  call    cs:__imp_HeapFree
0x1800173fa  xor     eax, eax
0x1800173fc  mov     [r13+30h], eax
0x180017400  mov     [r13+28h], rax
0x180017404  call    cs:__imp_GetProcessHeap
0x18001740a  mov     r8, r12; lpMem
0x18001740d  xor     edx, edx; dwFlags
0x18001740f  mov     rcx, rax; hHeap
0x180017412  call    cs:__imp_HeapFree
0x180017418  test    rsi, rsi
0x18001741b  jnz     loc_180017391
0x180017421  mov     [rdi], rsi
0x180017424  add     rdi, 8
0x180017428  cmp     rdi, r15
0x18001742b  jnz     loc_180017389
0x180017431  add     rsp, 28h
0x180017435  pop     r15
0x180017437  pop     r14
0x180017439  pop     r13
0x18001743b  pop     r12
0x18001743d  pop     rdi
0x18001743e  pop     rsi
0x18001743f  pop     rbp
0x180017440  pop     rbx
0x180017441  retn
```
