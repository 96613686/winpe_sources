# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800188d0`
- end: `0x1800189aa`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180018848`

## callees

- `0x1800188d0`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18001892b`
- `KERNEL32!HeapFree` at `0x18001895c`
- `KERNEL32!HeapFree` at `0x18001897a`
- `KERNEL32!HeapFree` at `0x18001892b`
- `KERNEL32!HeapFree` at `0x18001895c`
- `KERNEL32!HeapFree` at `0x18001897a`
- `KERNEL32!GetProcessHeap` at `0x18001891d`
- `KERNEL32!GetProcessHeap` at `0x18001894e`
- `KERNEL32!GetProcessHeap` at `0x18001896c`
- `KERNEL32!GetProcessHeap` at `0x18001891d`
- `KERNEL32!GetProcessHeap` at `0x18001894e`
- `KERNEL32!GetProcessHeap` at `0x18001896c`

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
0x1800188d0  push    rbx
0x1800188d2  push    rbp
0x1800188d3  push    rsi
0x1800188d4  push    rdi
0x1800188d5  push    r12
0x1800188d7  push    r13
0x1800188d9  push    r14
0x1800188db  push    r15
0x1800188dd  sub     rsp, 28h
0x1800188e1  lea     r15, [rcx+50h]
0x1800188e5  mov     rdi, rcx
0x1800188e8  cmp     rcx, r15
0x1800188eb  jz      loc_180018999
0x1800188f1  mov     rsi, [rdi]
0x1800188f4  jmp     loc_180018980
0x1800188f9  mov     r13, rsi
0x1800188fc  mov     r12, rsi
0x1800188ff  mov     rsi, [rsi+8]
0x180018903  movzx   eax, word ptr [r13+30h]
0x180018908  mov     rbp, [r13+28h]
0x18001890c  lea     r14, [rax+rax*4]
0x180018910  shl     r14, 4
0x180018914  add     r14, rbp
0x180018917  jmp     short loc_180018945
0x180018919  mov     rbx, [rbp+40h]
0x18001891d  call    cs:__imp_GetProcessHeap
0x180018923  mov     r8, rbx; lpMem
0x180018926  xor     edx, edx; dwFlags
0x180018928  mov     rcx, rax; hHeap
0x18001892b  call    cs:__imp_HeapFree
0x180018931  mov     qword ptr [rbp+40h], 0
0x180018939  mov     qword ptr [rbp+48h], 0
0x180018941  add     rbp, 50h ; 'P'
0x180018945  cmp     rbp, r14
0x180018948  jnz     short loc_180018919
0x18001894a  mov     rbx, [r13+28h]
0x18001894e  call    cs:__imp_GetProcessHeap
0x180018954  mov     r8, rbx; lpMem
0x180018957  xor     edx, edx; dwFlags
0x180018959  mov     rcx, rax; hHeap
0x18001895c  call    cs:__imp_HeapFree
0x180018962  xor     eax, eax
0x180018964  mov     [r13+30h], eax
0x180018968  mov     [r13+28h], rax
0x18001896c  call    cs:__imp_GetProcessHeap
0x180018972  mov     r8, r12; lpMem
0x180018975  xor     edx, edx; dwFlags
0x180018977  mov     rcx, rax; hHeap
0x18001897a  call    cs:__imp_HeapFree
0x180018980  test    rsi, rsi
0x180018983  jnz     loc_1800188F9
0x180018989  mov     [rdi], rsi
0x18001898c  add     rdi, 8
0x180018990  cmp     rdi, r15
0x180018993  jnz     loc_1800188F1
0x180018999  add     rsp, 28h
0x18001899d  pop     r15
0x18001899f  pop     r14
0x1800189a1  pop     r13
0x1800189a3  pop     r12
0x1800189a5  pop     rdi
0x1800189a6  pop     rsi
0x1800189a7  pop     rbp
0x1800189a8  pop     rbx
0x1800189a9  retn
```
