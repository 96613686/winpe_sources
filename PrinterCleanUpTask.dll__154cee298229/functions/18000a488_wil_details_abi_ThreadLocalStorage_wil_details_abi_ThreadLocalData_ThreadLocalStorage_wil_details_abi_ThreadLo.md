# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x18000a488`
- end: `0x18000a562`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a400`

## callees

- `0x18000a488`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a4e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a532`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a4e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a514`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a524`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a4d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a506`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a524`

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
0x18000a488  push    rbx
0x18000a48a  push    rbp
0x18000a48b  push    rsi
0x18000a48c  push    rdi
0x18000a48d  push    r12
0x18000a48f  push    r13
0x18000a491  push    r14
0x18000a493  push    r15
0x18000a495  sub     rsp, 28h
0x18000a499  lea     r15, [rcx+50h]
0x18000a49d  mov     rdi, rcx
0x18000a4a0  cmp     rcx, r15
0x18000a4a3  jz      loc_18000A551
0x18000a4a9  mov     rsi, [rdi]
0x18000a4ac  jmp     loc_18000A538
0x18000a4b1  mov     r13, rsi
0x18000a4b4  mov     r12, rsi
0x18000a4b7  mov     rsi, [rsi+8]
0x18000a4bb  movzx   eax, word ptr [r13+30h]
0x18000a4c0  mov     rbp, [r13+28h]
0x18000a4c4  lea     r14, [rax+rax*4]
0x18000a4c8  shl     r14, 4
0x18000a4cc  add     r14, rbp
0x18000a4cf  jmp     short loc_18000A4FD
0x18000a4d1  mov     rbx, [rbp+40h]
0x18000a4d5  call    cs:__imp_GetProcessHeap
0x18000a4db  mov     r8, rbx; lpMem
0x18000a4de  xor     edx, edx; dwFlags
0x18000a4e0  mov     rcx, rax; hHeap
0x18000a4e3  call    cs:__imp_HeapFree
0x18000a4e9  mov     qword ptr [rbp+40h], 0
0x18000a4f1  mov     qword ptr [rbp+48h], 0
0x18000a4f9  add     rbp, 50h ; 'P'
0x18000a4fd  cmp     rbp, r14
0x18000a500  jnz     short loc_18000A4D1
0x18000a502  mov     rbx, [r13+28h]
0x18000a506  call    cs:__imp_GetProcessHeap
0x18000a50c  mov     r8, rbx; lpMem
0x18000a50f  xor     edx, edx; dwFlags
0x18000a511  mov     rcx, rax; hHeap
0x18000a514  call    cs:__imp_HeapFree
0x18000a51a  xor     eax, eax
0x18000a51c  mov     [r13+30h], eax
0x18000a520  mov     [r13+28h], rax
0x18000a524  call    cs:__imp_GetProcessHeap
0x18000a52a  mov     r8, r12; lpMem
0x18000a52d  xor     edx, edx; dwFlags
0x18000a52f  mov     rcx, rax; hHeap
0x18000a532  call    cs:__imp_HeapFree
0x18000a538  test    rsi, rsi
0x18000a53b  jnz     loc_18000A4B1
0x18000a541  mov     [rdi], rsi
0x18000a544  add     rdi, 8
0x18000a548  cmp     rdi, r15
0x18000a54b  jnz     loc_18000A4A9
0x18000a551  add     rsp, 28h
0x18000a555  pop     r15
0x18000a557  pop     r14
0x18000a559  pop     r13
0x18000a55b  pop     r12
0x18000a55d  pop     rdi
0x18000a55e  pop     rsi
0x18000a55f  pop     rbp
0x18000a560  pop     rbx
0x18000a561  retn
```
