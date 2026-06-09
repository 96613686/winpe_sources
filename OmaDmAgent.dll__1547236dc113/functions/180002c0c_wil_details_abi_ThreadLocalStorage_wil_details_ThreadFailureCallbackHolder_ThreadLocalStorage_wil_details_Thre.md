# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180002c0c`
- end: `0x180002c68`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020d80`

## callees

- `0x180002c0c`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002c2d`
- `KERNEL32!GetProcessHeap` at `0x180002c2d`
- `KERNEL32!HeapFree` at `0x180002c41`
- `KERNEL32!HeapFree` at `0x180002c41`

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
0x180002c0c  push    rbx
0x180002c0e  push    rbp
0x180002c0f  push    rsi
0x180002c10  push    rdi
0x180002c11  sub     rsp, 28h
0x180002c15  lea     rbp, [rcx+50h]
0x180002c19  mov     rdi, rcx
0x180002c1c  cmp     rcx, rbp
0x180002c1f  jz      short loc_180002C5E
0x180002c21  mov     rsi, [rdi]
0x180002c24  jmp     short loc_180002C4D
0x180002c26  mov     rbx, rsi
0x180002c29  mov     rsi, [rsi+8]
0x180002c2d  call    cs:__imp_GetProcessHeap
0x180002c34  nop     dword ptr [rax+rax+00h]
0x180002c39  mov     r8, rbx; lpMem
0x180002c3c  xor     edx, edx; dwFlags
0x180002c3e  mov     rcx, rax; hHeap
0x180002c41  call    cs:__imp_HeapFree
0x180002c48  nop     dword ptr [rax+rax+00h]
0x180002c4d  test    rsi, rsi
0x180002c50  jnz     short loc_180002C26
0x180002c52  mov     [rdi], rsi
0x180002c55  add     rdi, 8
0x180002c59  cmp     rdi, rbp
0x180002c5c  jnz     short loc_180002C21
0x180002c5e  add     rsp, 28h
0x180002c62  pop     rdi
0x180002c63  pop     rsi
0x180002c64  pop     rbp
0x180002c65  pop     rbx
0x180002c66  retn
```
