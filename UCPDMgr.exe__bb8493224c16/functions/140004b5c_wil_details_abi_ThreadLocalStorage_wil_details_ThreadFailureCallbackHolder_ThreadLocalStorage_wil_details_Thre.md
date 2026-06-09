# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140004b5c`
- end: `0x140004bc2`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `102`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400102a0`

## callees

- `0x140004b5c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140004b96`
- `KERNEL32!HeapFree` at `0x140004b96`
- `KERNEL32!GetProcessHeap` at `0x140004b88`
- `KERNEL32!GetProcessHeap` at `0x140004b88`

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
0x140004b5c  mov     [rsp+arg_0], rbx
0x140004b61  mov     [rsp+arg_8], rbp
0x140004b66  mov     [rsp+arg_10], rsi
0x140004b6b  push    rdi
0x140004b6c  sub     rsp, 20h
0x140004b70  lea     rbp, [rcx+50h]
0x140004b74  mov     rdi, rcx
0x140004b77  cmp     rcx, rbp
0x140004b7a  jz      short loc_140004BAD
0x140004b7c  mov     rsi, [rdi]
0x140004b7f  jmp     short loc_140004B9C
0x140004b81  mov     rbx, rsi
0x140004b84  mov     rsi, [rsi+8]
0x140004b88  call    cs:__imp_GetProcessHeap
0x140004b8e  mov     r8, rbx; lpMem
0x140004b91  xor     edx, edx; dwFlags
0x140004b93  mov     rcx, rax; hHeap
0x140004b96  call    cs:__imp_HeapFree
0x140004b9c  test    rsi, rsi
0x140004b9f  jnz     short loc_140004B81
0x140004ba1  mov     [rdi], rsi
0x140004ba4  add     rdi, 8
0x140004ba8  cmp     rdi, rbp
0x140004bab  jnz     short loc_140004B7C
0x140004bad  mov     rbx, [rsp+28h+arg_0]
0x140004bb2  mov     rbp, [rsp+28h+arg_8]
0x140004bb7  mov     rsi, [rsp+28h+arg_10]
0x140004bbc  add     rsp, 20h
0x140004bc0  pop     rdi
0x140004bc1  retn
```
