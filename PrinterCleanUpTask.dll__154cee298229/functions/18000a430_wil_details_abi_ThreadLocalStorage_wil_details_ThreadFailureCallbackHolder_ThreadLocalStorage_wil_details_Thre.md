# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000a430`
- end: `0x18000a47f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017780`

## callees

- `0x18000a430`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a45f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a45f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a451`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a451`

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
0x18000a430  push    rbx
0x18000a432  push    rbp
0x18000a433  push    rsi
0x18000a434  push    rdi
0x18000a435  sub     rsp, 28h
0x18000a439  lea     rbp, [rcx+50h]
0x18000a43d  mov     rdi, rcx
0x18000a440  cmp     rcx, rbp
0x18000a443  jz      short loc_18000A476
0x18000a445  mov     rsi, [rdi]
0x18000a448  jmp     short loc_18000A465
0x18000a44a  mov     rbx, rsi
0x18000a44d  mov     rsi, [rsi+8]
0x18000a451  call    cs:__imp_GetProcessHeap
0x18000a457  mov     r8, rbx; lpMem
0x18000a45a  xor     edx, edx; dwFlags
0x18000a45c  mov     rcx, rax; hHeap
0x18000a45f  call    cs:__imp_HeapFree
0x18000a465  test    rsi, rsi
0x18000a468  jnz     short loc_18000A44A
0x18000a46a  mov     [rdi], rsi
0x18000a46d  add     rdi, 8
0x18000a471  cmp     rdi, rbp
0x18000a474  jnz     short loc_18000A445
0x18000a476  add     rsp, 28h
0x18000a47a  pop     rdi
0x18000a47b  pop     rsi
0x18000a47c  pop     rbp
0x18000a47d  pop     rbx
0x18000a47e  retn
```
