# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000c278`
- end: `0x18000c2c7`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001ac30`

## callees

- `0x18000c278`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c299`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000c299`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000c2a7`

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
0x18000c278  push    rbx
0x18000c27a  push    rbp
0x18000c27b  push    rsi
0x18000c27c  push    rdi
0x18000c27d  sub     rsp, 28h
0x18000c281  lea     rbp, [rcx+50h]
0x18000c285  mov     rdi, rcx
0x18000c288  cmp     rcx, rbp
0x18000c28b  jz      short loc_18000C2BE
0x18000c28d  mov     rsi, [rdi]
0x18000c290  jmp     short loc_18000C2AD
0x18000c292  mov     rbx, rsi
0x18000c295  mov     rsi, [rsi+8]
0x18000c299  call    cs:__imp_GetProcessHeap
0x18000c29f  mov     r8, rbx; lpMem
0x18000c2a2  xor     edx, edx; dwFlags
0x18000c2a4  mov     rcx, rax; hHeap
0x18000c2a7  call    cs:__imp_HeapFree
0x18000c2ad  test    rsi, rsi
0x18000c2b0  jnz     short loc_18000C292
0x18000c2b2  mov     [rdi], rsi
0x18000c2b5  add     rdi, 8
0x18000c2b9  cmp     rdi, rbp
0x18000c2bc  jnz     short loc_18000C28D
0x18000c2be  add     rsp, 28h
0x18000c2c2  pop     rdi
0x18000c2c3  pop     rsi
0x18000c2c4  pop     rbp
0x18000c2c5  pop     rbx
0x18000c2c6  retn
```
