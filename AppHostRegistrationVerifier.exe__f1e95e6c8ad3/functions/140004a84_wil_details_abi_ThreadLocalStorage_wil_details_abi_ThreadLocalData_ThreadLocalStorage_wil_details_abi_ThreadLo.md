# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140004a84`
- end: `0x140004b5e`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `218`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400049dc`

## callees

- `0x140004a84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b2e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004adf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004b2e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b20`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004ad1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004b20`

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
0x140004a84  push    rbx
0x140004a86  push    rbp
0x140004a87  push    rsi
0x140004a88  push    rdi
0x140004a89  push    r12
0x140004a8b  push    r13
0x140004a8d  push    r14
0x140004a8f  push    r15
0x140004a91  sub     rsp, 28h
0x140004a95  lea     r15, [rcx+50h]
0x140004a99  mov     rdi, rcx
0x140004a9c  cmp     rcx, r15
0x140004a9f  jz      loc_140004B4D
0x140004aa5  mov     rsi, [rdi]
0x140004aa8  jmp     loc_140004B34
0x140004aad  mov     r13, rsi
0x140004ab0  mov     r12, rsi
0x140004ab3  mov     rsi, [rsi+8]
0x140004ab7  movzx   eax, word ptr [r13+30h]
0x140004abc  mov     rbp, [r13+28h]
0x140004ac0  lea     r14, [rax+rax*4]
0x140004ac4  shl     r14, 4
0x140004ac8  add     r14, rbp
0x140004acb  jmp     short loc_140004AF9
0x140004acd  mov     rbx, [rbp+40h]
0x140004ad1  call    cs:__imp_GetProcessHeap
0x140004ad7  mov     r8, rbx; lpMem
0x140004ada  xor     edx, edx; dwFlags
0x140004adc  mov     rcx, rax; hHeap
0x140004adf  call    cs:__imp_HeapFree
0x140004ae5  mov     qword ptr [rbp+40h], 0
0x140004aed  mov     qword ptr [rbp+48h], 0
0x140004af5  add     rbp, 50h ; 'P'
0x140004af9  cmp     rbp, r14
0x140004afc  jnz     short loc_140004ACD
0x140004afe  mov     rbx, [r13+28h]
0x140004b02  call    cs:__imp_GetProcessHeap
0x140004b08  mov     r8, rbx; lpMem
0x140004b0b  xor     edx, edx; dwFlags
0x140004b0d  mov     rcx, rax; hHeap
0x140004b10  call    cs:__imp_HeapFree
0x140004b16  xor     eax, eax
0x140004b18  mov     [r13+30h], eax
0x140004b1c  mov     [r13+28h], rax
0x140004b20  call    cs:__imp_GetProcessHeap
0x140004b26  mov     r8, r12; lpMem
0x140004b29  xor     edx, edx; dwFlags
0x140004b2b  mov     rcx, rax; hHeap
0x140004b2e  call    cs:__imp_HeapFree
0x140004b34  test    rsi, rsi
0x140004b37  jnz     loc_140004AAD
0x140004b3d  mov     [rdi], rsi
0x140004b40  add     rdi, 8
0x140004b44  cmp     rdi, r15
0x140004b47  jnz     loc_140004AA5
0x140004b4d  add     rsp, 28h
0x140004b51  pop     r15
0x140004b53  pop     r14
0x140004b55  pop     r13
0x140004b57  pop     r12
0x140004b59  pop     rdi
0x140004b5a  pop     rsi
0x140004b5b  pop     rbp
0x140004b5c  pop     rbx
0x140004b5d  retn
```
