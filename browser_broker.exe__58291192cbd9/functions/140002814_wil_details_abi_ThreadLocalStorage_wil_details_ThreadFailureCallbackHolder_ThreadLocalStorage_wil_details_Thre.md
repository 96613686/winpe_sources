# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140002814`
- end: `0x140002863`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140005b60`

## callees

- `0x140002814`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002843`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002843`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002835`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002835`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(
        _QWORD *a1)
{
  _QWORD *v1; // rbp
  _QWORD *v2; // rdi
  _QWORD *v3; // rsi
  void *v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = (_QWORD *)*v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = (_QWORD *)v3[1];
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x140002814  push    rbx
0x140002816  push    rbp
0x140002817  push    rsi
0x140002818  push    rdi
0x140002819  sub     rsp, 28h
0x14000281d  lea     rbp, [rcx+50h]
0x140002821  mov     rdi, rcx
0x140002824  cmp     rcx, rbp
0x140002827  jz      short loc_14000285A
0x140002829  mov     rsi, [rdi]
0x14000282c  jmp     short loc_140002849
0x14000282e  mov     rbx, rsi
0x140002831  mov     rsi, [rsi+8]
0x140002835  call    cs:__imp_GetProcessHeap
0x14000283b  mov     r8, rbx; lpMem
0x14000283e  xor     edx, edx; dwFlags
0x140002840  mov     rcx, rax; hHeap
0x140002843  call    cs:__imp_HeapFree
0x140002849  test    rsi, rsi
0x14000284c  jnz     short loc_14000282E
0x14000284e  mov     [rdi], rsi
0x140002851  add     rdi, 8
0x140002855  cmp     rdi, rbp
0x140002858  jnz     short loc_140002829
0x14000285a  add     rsp, 28h
0x14000285e  pop     rdi
0x14000285f  pop     rsi
0x140002860  pop     rbp
0x140002861  pop     rbx
0x140002862  retn
```
