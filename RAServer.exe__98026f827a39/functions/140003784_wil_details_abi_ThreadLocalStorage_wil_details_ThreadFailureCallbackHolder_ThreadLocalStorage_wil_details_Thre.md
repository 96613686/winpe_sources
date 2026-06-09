# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140003784`
- end: `0x1400037d3`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400160f0`

## callees

- `0x140003784`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x1400037a5`
- `KERNEL32!GetProcessHeap` at `0x1400037a5`
- `KERNEL32!HeapFree` at `0x1400037b3`
- `KERNEL32!HeapFree` at `0x1400037b3`

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
0x140003784  push    rbx
0x140003786  push    rbp
0x140003787  push    rsi
0x140003788  push    rdi
0x140003789  sub     rsp, 28h
0x14000378d  lea     rbp, [rcx+50h]
0x140003791  mov     rdi, rcx
0x140003794  cmp     rcx, rbp
0x140003797  jz      short loc_1400037CA
0x140003799  mov     rsi, [rdi]
0x14000379c  jmp     short loc_1400037B9
0x14000379e  mov     rbx, rsi
0x1400037a1  mov     rsi, [rsi+8]
0x1400037a5  call    cs:__imp_GetProcessHeap
0x1400037ab  mov     r8, rbx; lpMem
0x1400037ae  xor     edx, edx; dwFlags
0x1400037b0  mov     rcx, rax; hHeap
0x1400037b3  call    cs:__imp_HeapFree
0x1400037b9  test    rsi, rsi
0x1400037bc  jnz     short loc_14000379E
0x1400037be  mov     [rdi], rsi
0x1400037c1  add     rdi, 8
0x1400037c5  cmp     rdi, rbp
0x1400037c8  jnz     short loc_140003799
0x1400037ca  add     rsp, 28h
0x1400037ce  pop     rdi
0x1400037cf  pop     rsi
0x1400037d0  pop     rbp
0x1400037d1  pop     rbx
0x1400037d2  retn
```
