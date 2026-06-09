# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000ad0c`
- end: `0x18000ade6`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ac54`

## callees

- `0x18000ad0c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ada8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ad8a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ada8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000adb6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad67`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ad98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000adb6`

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
0x18000ad0c  push    rbx
0x18000ad0e  push    rbp
0x18000ad0f  push    rsi
0x18000ad10  push    rdi
0x18000ad11  push    r12
0x18000ad13  push    r13
0x18000ad15  push    r14
0x18000ad17  push    r15
0x18000ad19  sub     rsp, 28h
0x18000ad1d  lea     r15, [rcx+50h]
0x18000ad21  mov     rdi, rcx
0x18000ad24  cmp     rcx, r15
0x18000ad27  jz      loc_18000ADD5
0x18000ad2d  mov     rsi, [rdi]
0x18000ad30  jmp     loc_18000ADBC
0x18000ad35  mov     r13, rsi
0x18000ad38  mov     r12, rsi
0x18000ad3b  mov     rsi, [rsi+8]
0x18000ad3f  movzx   eax, word ptr [r13+30h]
0x18000ad44  mov     rbp, [r13+28h]
0x18000ad48  lea     r14, [rax+rax*4]
0x18000ad4c  shl     r14, 4
0x18000ad50  add     r14, rbp
0x18000ad53  jmp     short loc_18000AD81
0x18000ad55  mov     rbx, [rbp+40h]
0x18000ad59  call    cs:__imp_GetProcessHeap
0x18000ad5f  mov     r8, rbx; lpMem
0x18000ad62  xor     edx, edx; dwFlags
0x18000ad64  mov     rcx, rax; hHeap
0x18000ad67  call    cs:__imp_HeapFree
0x18000ad6d  mov     qword ptr [rbp+40h], 0
0x18000ad75  mov     qword ptr [rbp+48h], 0
0x18000ad7d  add     rbp, 50h ; 'P'
0x18000ad81  cmp     rbp, r14
0x18000ad84  jnz     short loc_18000AD55
0x18000ad86  mov     rbx, [r13+28h]
0x18000ad8a  call    cs:__imp_GetProcessHeap
0x18000ad90  mov     r8, rbx; lpMem
0x18000ad93  xor     edx, edx; dwFlags
0x18000ad95  mov     rcx, rax; hHeap
0x18000ad98  call    cs:__imp_HeapFree
0x18000ad9e  xor     eax, eax
0x18000ada0  mov     [r13+30h], eax
0x18000ada4  mov     [r13+28h], rax
0x18000ada8  call    cs:__imp_GetProcessHeap
0x18000adae  mov     r8, r12; lpMem
0x18000adb1  xor     edx, edx; dwFlags
0x18000adb3  mov     rcx, rax; hHeap
0x18000adb6  call    cs:__imp_HeapFree
0x18000adbc  test    rsi, rsi
0x18000adbf  jnz     loc_18000AD35
0x18000adc5  mov     [rdi], rsi
0x18000adc8  add     rdi, 8
0x18000adcc  cmp     rdi, r15
0x18000adcf  jnz     loc_18000AD2D
0x18000add5  add     rsp, 28h
0x18000add9  pop     r15
0x18000addb  pop     r14
0x18000addd  pop     r13
0x18000addf  pop     r12
0x18000ade1  pop     rdi
0x18000ade2  pop     rsi
0x18000ade3  pop     rbp
0x18000ade4  pop     rbx
0x18000ade5  retn
```
