# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180013a04`
- end: `0x180013ade`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001397c`

## callees

- `0x180013a04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013aa0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a51`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013a82`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180013aa0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013a5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013aae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013a5f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013a90`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180013aae`

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
0x180013a04  push    rbx
0x180013a06  push    rbp
0x180013a07  push    rsi
0x180013a08  push    rdi
0x180013a09  push    r12
0x180013a0b  push    r13
0x180013a0d  push    r14
0x180013a0f  push    r15
0x180013a11  sub     rsp, 28h
0x180013a15  lea     r15, [rcx+50h]
0x180013a19  mov     rdi, rcx
0x180013a1c  cmp     rcx, r15
0x180013a1f  jz      loc_180013ACD
0x180013a25  mov     rsi, [rdi]
0x180013a28  jmp     loc_180013AB4
0x180013a2d  mov     r13, rsi
0x180013a30  mov     r12, rsi
0x180013a33  mov     rsi, [rsi+8]
0x180013a37  movzx   eax, word ptr [r13+30h]
0x180013a3c  mov     rbp, [r13+28h]
0x180013a40  lea     r14, [rax+rax*4]
0x180013a44  shl     r14, 4
0x180013a48  add     r14, rbp
0x180013a4b  jmp     short loc_180013A79
0x180013a4d  mov     rbx, [rbp+40h]
0x180013a51  call    cs:__imp_GetProcessHeap
0x180013a57  mov     r8, rbx; lpMem
0x180013a5a  xor     edx, edx; dwFlags
0x180013a5c  mov     rcx, rax; hHeap
0x180013a5f  call    cs:__imp_HeapFree
0x180013a65  mov     qword ptr [rbp+40h], 0
0x180013a6d  mov     qword ptr [rbp+48h], 0
0x180013a75  add     rbp, 50h ; 'P'
0x180013a79  cmp     rbp, r14
0x180013a7c  jnz     short loc_180013A4D
0x180013a7e  mov     rbx, [r13+28h]
0x180013a82  call    cs:__imp_GetProcessHeap
0x180013a88  mov     r8, rbx; lpMem
0x180013a8b  xor     edx, edx; dwFlags
0x180013a8d  mov     rcx, rax; hHeap
0x180013a90  call    cs:__imp_HeapFree
0x180013a96  xor     eax, eax
0x180013a98  mov     [r13+30h], eax
0x180013a9c  mov     [r13+28h], rax
0x180013aa0  call    cs:__imp_GetProcessHeap
0x180013aa6  mov     r8, r12; lpMem
0x180013aa9  xor     edx, edx; dwFlags
0x180013aab  mov     rcx, rax; hHeap
0x180013aae  call    cs:__imp_HeapFree
0x180013ab4  test    rsi, rsi
0x180013ab7  jnz     loc_180013A2D
0x180013abd  mov     [rdi], rsi
0x180013ac0  add     rdi, 8
0x180013ac4  cmp     rdi, r15
0x180013ac7  jnz     loc_180013A25
0x180013acd  add     rsp, 28h
0x180013ad1  pop     r15
0x180013ad3  pop     r14
0x180013ad5  pop     r13
0x180013ad7  pop     r12
0x180013ad9  pop     rdi
0x180013ada  pop     rsi
0x180013adb  pop     rbp
0x180013adc  pop     rbx
0x180013add  retn
```
