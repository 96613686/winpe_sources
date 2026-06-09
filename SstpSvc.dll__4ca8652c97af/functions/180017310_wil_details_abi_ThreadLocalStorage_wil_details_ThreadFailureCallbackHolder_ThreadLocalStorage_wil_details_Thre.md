# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180017310`
- end: `0x18001735f`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001c600`

## callees

- `0x180017310`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001733f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001733f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017331`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017331`

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
0x180017310  push    rbx
0x180017312  push    rbp
0x180017313  push    rsi
0x180017314  push    rdi
0x180017315  sub     rsp, 28h
0x180017319  lea     rbp, [rcx+50h]
0x18001731d  mov     rdi, rcx
0x180017320  cmp     rcx, rbp
0x180017323  jz      short loc_180017356
0x180017325  mov     rsi, [rdi]
0x180017328  jmp     short loc_180017345
0x18001732a  mov     rbx, rsi
0x18001732d  mov     rsi, [rsi+8]
0x180017331  call    cs:__imp_GetProcessHeap
0x180017337  mov     r8, rbx; lpMem
0x18001733a  xor     edx, edx; dwFlags
0x18001733c  mov     rcx, rax; hHeap
0x18001733f  call    cs:__imp_HeapFree
0x180017345  test    rsi, rsi
0x180017348  jnz     short loc_18001732A
0x18001734a  mov     [rdi], rsi
0x18001734d  add     rdi, 8
0x180017351  cmp     rdi, rbp
0x180017354  jnz     short loc_180017325
0x180017356  add     rsp, 28h
0x18001735a  pop     rdi
0x18001735b  pop     rsi
0x18001735c  pop     rbp
0x18001735d  pop     rbx
0x18001735e  retn
```
