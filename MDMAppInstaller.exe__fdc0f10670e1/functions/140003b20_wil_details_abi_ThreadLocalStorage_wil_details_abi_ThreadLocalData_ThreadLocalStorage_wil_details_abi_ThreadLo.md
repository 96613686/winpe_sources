# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003b20`
- end: `0x140003bfa`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003a98`

## callees

- `0x140003b20`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003b7b`
- `KERNEL32!HeapFree` at `0x140003bac`
- `KERNEL32!HeapFree` at `0x140003bca`
- `KERNEL32!HeapFree` at `0x140003b7b`
- `KERNEL32!HeapFree` at `0x140003bac`
- `KERNEL32!HeapFree` at `0x140003bca`
- `KERNEL32!GetProcessHeap` at `0x140003b6d`
- `KERNEL32!GetProcessHeap` at `0x140003b9e`
- `KERNEL32!GetProcessHeap` at `0x140003bbc`
- `KERNEL32!GetProcessHeap` at `0x140003b6d`
- `KERNEL32!GetProcessHeap` at `0x140003b9e`
- `KERNEL32!GetProcessHeap` at `0x140003bbc`

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
0x140003b20  push    rbx
0x140003b22  push    rbp
0x140003b23  push    rsi
0x140003b24  push    rdi
0x140003b25  push    r12
0x140003b27  push    r13
0x140003b29  push    r14
0x140003b2b  push    r15
0x140003b2d  sub     rsp, 28h
0x140003b31  lea     r15, [rcx+50h]
0x140003b35  mov     rdi, rcx
0x140003b38  cmp     rcx, r15
0x140003b3b  jz      loc_140003BE9
0x140003b41  mov     rsi, [rdi]
0x140003b44  jmp     loc_140003BD0
0x140003b49  mov     r13, rsi
0x140003b4c  mov     r12, rsi
0x140003b4f  mov     rsi, [rsi+8]
0x140003b53  movzx   eax, word ptr [r13+30h]
0x140003b58  mov     rbp, [r13+28h]
0x140003b5c  lea     r14, [rax+rax*4]
0x140003b60  shl     r14, 4
0x140003b64  add     r14, rbp
0x140003b67  jmp     short loc_140003B95
0x140003b69  mov     rbx, [rbp+40h]
0x140003b6d  call    cs:__imp_GetProcessHeap
0x140003b73  mov     r8, rbx; lpMem
0x140003b76  xor     edx, edx; dwFlags
0x140003b78  mov     rcx, rax; hHeap
0x140003b7b  call    cs:__imp_HeapFree
0x140003b81  mov     qword ptr [rbp+40h], 0
0x140003b89  mov     qword ptr [rbp+48h], 0
0x140003b91  add     rbp, 50h ; 'P'
0x140003b95  cmp     rbp, r14
0x140003b98  jnz     short loc_140003B69
0x140003b9a  mov     rbx, [r13+28h]
0x140003b9e  call    cs:__imp_GetProcessHeap
0x140003ba4  mov     r8, rbx; lpMem
0x140003ba7  xor     edx, edx; dwFlags
0x140003ba9  mov     rcx, rax; hHeap
0x140003bac  call    cs:__imp_HeapFree
0x140003bb2  xor     eax, eax
0x140003bb4  mov     [r13+30h], eax
0x140003bb8  mov     [r13+28h], rax
0x140003bbc  call    cs:__imp_GetProcessHeap
0x140003bc2  mov     r8, r12; lpMem
0x140003bc5  xor     edx, edx; dwFlags
0x140003bc7  mov     rcx, rax; hHeap
0x140003bca  call    cs:__imp_HeapFree
0x140003bd0  test    rsi, rsi
0x140003bd3  jnz     loc_140003B49
0x140003bd9  mov     [rdi], rsi
0x140003bdc  add     rdi, 8
0x140003be0  cmp     rdi, r15
0x140003be3  jnz     loc_140003B41
0x140003be9  add     rsp, 28h
0x140003bed  pop     r15
0x140003bef  pop     r14
0x140003bf1  pop     r13
0x140003bf3  pop     r12
0x140003bf5  pop     rdi
0x140003bf6  pop     rsi
0x140003bf7  pop     rbp
0x140003bf8  pop     rbx
0x140003bf9  retn
```
