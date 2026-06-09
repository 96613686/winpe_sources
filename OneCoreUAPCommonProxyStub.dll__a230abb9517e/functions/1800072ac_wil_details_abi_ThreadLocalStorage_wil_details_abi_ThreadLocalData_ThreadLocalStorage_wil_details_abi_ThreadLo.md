# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800072ac`
- end: `0x180007386`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000727c`

## callees

- `0x1800072ac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007356`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007307`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007338`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007356`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000732a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007348`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800072f9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000732a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007348`

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
0x1800072ac  push    rbx
0x1800072ae  push    rbp
0x1800072af  push    rsi
0x1800072b0  push    rdi
0x1800072b1  push    r12
0x1800072b3  push    r13
0x1800072b5  push    r14
0x1800072b7  push    r15
0x1800072b9  sub     rsp, 28h
0x1800072bd  lea     r15, [rcx+50h]
0x1800072c1  mov     rdi, rcx
0x1800072c4  cmp     rcx, r15
0x1800072c7  jz      loc_180007375
0x1800072cd  mov     rsi, [rdi]
0x1800072d0  jmp     loc_18000735C
0x1800072d5  mov     r13, rsi
0x1800072d8  mov     r12, rsi
0x1800072db  mov     rsi, [rsi+8]
0x1800072df  movzx   eax, word ptr [r13+30h]
0x1800072e4  mov     rbp, [r13+28h]
0x1800072e8  lea     r14, [rax+rax*4]
0x1800072ec  shl     r14, 4
0x1800072f0  add     r14, rbp
0x1800072f3  jmp     short loc_180007321
0x1800072f5  mov     rbx, [rbp+40h]
0x1800072f9  call    cs:__imp_GetProcessHeap
0x1800072ff  mov     r8, rbx; lpMem
0x180007302  xor     edx, edx; dwFlags
0x180007304  mov     rcx, rax; hHeap
0x180007307  call    cs:__imp_HeapFree
0x18000730d  mov     qword ptr [rbp+40h], 0
0x180007315  mov     qword ptr [rbp+48h], 0
0x18000731d  add     rbp, 50h ; 'P'
0x180007321  cmp     rbp, r14
0x180007324  jnz     short loc_1800072F5
0x180007326  mov     rbx, [r13+28h]
0x18000732a  call    cs:__imp_GetProcessHeap
0x180007330  mov     r8, rbx; lpMem
0x180007333  xor     edx, edx; dwFlags
0x180007335  mov     rcx, rax; hHeap
0x180007338  call    cs:__imp_HeapFree
0x18000733e  xor     eax, eax
0x180007340  mov     [r13+30h], eax
0x180007344  mov     [r13+28h], rax
0x180007348  call    cs:__imp_GetProcessHeap
0x18000734e  mov     r8, r12; lpMem
0x180007351  xor     edx, edx; dwFlags
0x180007353  mov     rcx, rax; hHeap
0x180007356  call    cs:__imp_HeapFree
0x18000735c  test    rsi, rsi
0x18000735f  jnz     loc_1800072D5
0x180007365  mov     [rdi], rsi
0x180007368  add     rdi, 8
0x18000736c  cmp     rdi, r15
0x18000736f  jnz     loc_1800072CD
0x180007375  add     rsp, 28h
0x180007379  pop     r15
0x18000737b  pop     r14
0x18000737d  pop     r13
0x18000737f  pop     r12
0x180007381  pop     rdi
0x180007382  pop     rsi
0x180007383  pop     rbp
0x180007384  pop     rbx
0x180007385  retn
```
