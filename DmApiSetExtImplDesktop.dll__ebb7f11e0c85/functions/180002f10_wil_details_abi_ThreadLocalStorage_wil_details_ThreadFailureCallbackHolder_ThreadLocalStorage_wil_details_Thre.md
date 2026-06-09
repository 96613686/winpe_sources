# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180002f10`
- end: `0x180002f6c`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a8a0`

## callees

- `0x180002f10`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f31`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f31`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f45`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002f45`

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
0x180002f10  push    rbx
0x180002f12  push    rbp
0x180002f13  push    rsi
0x180002f14  push    rdi
0x180002f15  sub     rsp, 28h
0x180002f19  lea     rbp, [rcx+50h]
0x180002f1d  mov     rdi, rcx
0x180002f20  cmp     rcx, rbp
0x180002f23  jz      short loc_180002F62
0x180002f25  mov     rsi, [rdi]
0x180002f28  jmp     short loc_180002F51
0x180002f2a  mov     rbx, rsi
0x180002f2d  mov     rsi, [rsi+8]
0x180002f31  call    cs:__imp_GetProcessHeap
0x180002f38  nop     dword ptr [rax+rax+00h]
0x180002f3d  mov     r8, rbx; lpMem
0x180002f40  xor     edx, edx; dwFlags
0x180002f42  mov     rcx, rax; hHeap
0x180002f45  call    cs:__imp_HeapFree
0x180002f4c  nop     dword ptr [rax+rax+00h]
0x180002f51  test    rsi, rsi
0x180002f54  jnz     short loc_180002F2A
0x180002f56  mov     [rdi], rsi
0x180002f59  add     rdi, 8
0x180002f5d  cmp     rdi, rbp
0x180002f60  jnz     short loc_180002F25
0x180002f62  add     rsp, 28h
0x180002f66  pop     rdi
0x180002f67  pop     rsi
0x180002f68  pop     rbp
0x180002f69  pop     rbx
0x180002f6a  retn
```
