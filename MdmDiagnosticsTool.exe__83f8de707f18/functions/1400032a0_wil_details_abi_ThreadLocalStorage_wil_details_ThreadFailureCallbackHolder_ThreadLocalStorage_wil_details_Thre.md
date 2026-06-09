# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1400032a0`
- end: `0x1400032fc`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000a4b0`

## callees

- `0x1400032a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400032d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400032c1`

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
0x1400032a0  push    rbx
0x1400032a2  push    rbp
0x1400032a3  push    rsi
0x1400032a4  push    rdi
0x1400032a5  sub     rsp, 28h
0x1400032a9  lea     rbp, [rcx+50h]
0x1400032ad  mov     rdi, rcx
0x1400032b0  cmp     rcx, rbp
0x1400032b3  jz      short loc_1400032F2
0x1400032b5  mov     rsi, [rdi]
0x1400032b8  jmp     short loc_1400032E1
0x1400032ba  mov     rbx, rsi
0x1400032bd  mov     rsi, [rsi+8]
0x1400032c1  call    cs:__imp_GetProcessHeap
0x1400032c8  nop     dword ptr [rax+rax+00h]
0x1400032cd  mov     r8, rbx; lpMem
0x1400032d0  xor     edx, edx; dwFlags
0x1400032d2  mov     rcx, rax; hHeap
0x1400032d5  call    cs:__imp_HeapFree
0x1400032dc  nop     dword ptr [rax+rax+00h]
0x1400032e1  test    rsi, rsi
0x1400032e4  jnz     short loc_1400032BA
0x1400032e6  mov     [rdi], rsi
0x1400032e9  add     rdi, 8
0x1400032ed  cmp     rdi, rbp
0x1400032f0  jnz     short loc_1400032B5
0x1400032f2  add     rsp, 28h
0x1400032f6  pop     rdi
0x1400032f7  pop     rsi
0x1400032f8  pop     rbp
0x1400032f9  pop     rbx
0x1400032fa  retn
```
