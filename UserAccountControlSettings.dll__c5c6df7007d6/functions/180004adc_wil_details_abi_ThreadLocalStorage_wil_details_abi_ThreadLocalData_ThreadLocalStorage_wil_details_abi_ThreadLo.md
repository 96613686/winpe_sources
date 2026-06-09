# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180004adc`
- end: `0x180004bb6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180004a54`

## callees

- `0x180004adc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b78`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004b78`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b86`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004b86`

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
0x180004adc  push    rbx
0x180004ade  push    rbp
0x180004adf  push    rsi
0x180004ae0  push    rdi
0x180004ae1  push    r12
0x180004ae3  push    r13
0x180004ae5  push    r14
0x180004ae7  push    r15
0x180004ae9  sub     rsp, 28h
0x180004aed  lea     r15, [rcx+50h]
0x180004af1  mov     rdi, rcx
0x180004af4  cmp     rcx, r15
0x180004af7  jz      loc_180004BA5
0x180004afd  mov     rsi, [rdi]
0x180004b00  jmp     loc_180004B8C
0x180004b05  mov     r13, rsi
0x180004b08  mov     r12, rsi
0x180004b0b  mov     rsi, [rsi+8]
0x180004b0f  movzx   eax, word ptr [r13+30h]
0x180004b14  mov     rbp, [r13+28h]
0x180004b18  lea     r14, [rax+rax*4]
0x180004b1c  shl     r14, 4
0x180004b20  add     r14, rbp
0x180004b23  jmp     short loc_180004B51
0x180004b25  mov     rbx, [rbp+40h]
0x180004b29  call    cs:__imp_GetProcessHeap
0x180004b2f  mov     r8, rbx; lpMem
0x180004b32  xor     edx, edx; dwFlags
0x180004b34  mov     rcx, rax; hHeap
0x180004b37  call    cs:__imp_HeapFree
0x180004b3d  mov     qword ptr [rbp+40h], 0
0x180004b45  mov     qword ptr [rbp+48h], 0
0x180004b4d  add     rbp, 50h ; 'P'
0x180004b51  cmp     rbp, r14
0x180004b54  jnz     short loc_180004B25
0x180004b56  mov     rbx, [r13+28h]
0x180004b5a  call    cs:__imp_GetProcessHeap
0x180004b60  mov     r8, rbx; lpMem
0x180004b63  xor     edx, edx; dwFlags
0x180004b65  mov     rcx, rax; hHeap
0x180004b68  call    cs:__imp_HeapFree
0x180004b6e  xor     eax, eax
0x180004b70  mov     [r13+30h], eax
0x180004b74  mov     [r13+28h], rax
0x180004b78  call    cs:__imp_GetProcessHeap
0x180004b7e  mov     r8, r12; lpMem
0x180004b81  xor     edx, edx; dwFlags
0x180004b83  mov     rcx, rax; hHeap
0x180004b86  call    cs:__imp_HeapFree
0x180004b8c  test    rsi, rsi
0x180004b8f  jnz     loc_180004B05
0x180004b95  mov     [rdi], rsi
0x180004b98  add     rdi, 8
0x180004b9c  cmp     rdi, r15
0x180004b9f  jnz     loc_180004AFD
0x180004ba5  add     rsp, 28h
0x180004ba9  pop     r15
0x180004bab  pop     r14
0x180004bad  pop     r13
0x180004baf  pop     r12
0x180004bb1  pop     rdi
0x180004bb2  pop     rsi
0x180004bb3  pop     rbp
0x180004bb4  pop     rbx
0x180004bb5  retn
```
