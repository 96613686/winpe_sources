# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x14000442c`
- end: `0x140004506`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004374`

## callees

- `0x14000442c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004487`
- `KERNEL32!HeapFree` at `0x1400044b8`
- `KERNEL32!HeapFree` at `0x1400044d6`
- `KERNEL32!HeapFree` at `0x140004487`
- `KERNEL32!HeapFree` at `0x1400044b8`
- `KERNEL32!HeapFree` at `0x1400044d6`
- `KERNEL32!GetProcessHeap` at `0x140004479`
- `KERNEL32!GetProcessHeap` at `0x1400044aa`
- `KERNEL32!GetProcessHeap` at `0x1400044c8`
- `KERNEL32!GetProcessHeap` at `0x140004479`
- `KERNEL32!GetProcessHeap` at `0x1400044aa`
- `KERNEL32!GetProcessHeap` at `0x1400044c8`

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
0x14000442c  push    rbx
0x14000442e  push    rbp
0x14000442f  push    rsi
0x140004430  push    rdi
0x140004431  push    r12
0x140004433  push    r13
0x140004435  push    r14
0x140004437  push    r15
0x140004439  sub     rsp, 28h
0x14000443d  lea     r15, [rcx+50h]
0x140004441  mov     rdi, rcx
0x140004444  cmp     rcx, r15
0x140004447  jz      loc_1400044F5
0x14000444d  mov     rsi, [rdi]
0x140004450  jmp     loc_1400044DC
0x140004455  mov     r13, rsi
0x140004458  mov     r12, rsi
0x14000445b  mov     rsi, [rsi+8]
0x14000445f  movzx   eax, word ptr [r13+30h]
0x140004464  mov     rbp, [r13+28h]
0x140004468  lea     r14, [rax+rax*4]
0x14000446c  shl     r14, 4
0x140004470  add     r14, rbp
0x140004473  jmp     short loc_1400044A1
0x140004475  mov     rbx, [rbp+40h]
0x140004479  call    cs:__imp_GetProcessHeap
0x14000447f  mov     r8, rbx; lpMem
0x140004482  xor     edx, edx; dwFlags
0x140004484  mov     rcx, rax; hHeap
0x140004487  call    cs:__imp_HeapFree
0x14000448d  mov     qword ptr [rbp+40h], 0
0x140004495  mov     qword ptr [rbp+48h], 0
0x14000449d  add     rbp, 50h ; 'P'
0x1400044a1  cmp     rbp, r14
0x1400044a4  jnz     short loc_140004475
0x1400044a6  mov     rbx, [r13+28h]
0x1400044aa  call    cs:__imp_GetProcessHeap
0x1400044b0  mov     r8, rbx; lpMem
0x1400044b3  xor     edx, edx; dwFlags
0x1400044b5  mov     rcx, rax; hHeap
0x1400044b8  call    cs:__imp_HeapFree
0x1400044be  xor     eax, eax
0x1400044c0  mov     [r13+30h], eax
0x1400044c4  mov     [r13+28h], rax
0x1400044c8  call    cs:__imp_GetProcessHeap
0x1400044ce  mov     r8, r12; lpMem
0x1400044d1  xor     edx, edx; dwFlags
0x1400044d3  mov     rcx, rax; hHeap
0x1400044d6  call    cs:__imp_HeapFree
0x1400044dc  test    rsi, rsi
0x1400044df  jnz     loc_140004455
0x1400044e5  mov     [rdi], rsi
0x1400044e8  add     rdi, 8
0x1400044ec  cmp     rdi, r15
0x1400044ef  jnz     loc_14000444D
0x1400044f5  add     rsp, 28h
0x1400044f9  pop     r15
0x1400044fb  pop     r14
0x1400044fd  pop     r13
0x1400044ff  pop     r12
0x140004501  pop     rdi
0x140004502  pop     rsi
0x140004503  pop     rbp
0x140004504  pop     rbx
0x140004505  retn
```
