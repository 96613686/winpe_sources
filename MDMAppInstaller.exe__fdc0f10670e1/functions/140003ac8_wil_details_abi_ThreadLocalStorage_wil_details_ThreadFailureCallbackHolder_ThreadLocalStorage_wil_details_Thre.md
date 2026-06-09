# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140003ac8`
- end: `0x140003b17`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b350`

## callees

- `0x140003ac8`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003af7`
- `KERNEL32!HeapFree` at `0x140003af7`
- `KERNEL32!GetProcessHeap` at `0x140003ae9`
- `KERNEL32!GetProcessHeap` at `0x140003ae9`

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
0x140003ac8  push    rbx
0x140003aca  push    rbp
0x140003acb  push    rsi
0x140003acc  push    rdi
0x140003acd  sub     rsp, 28h
0x140003ad1  lea     rbp, [rcx+50h]
0x140003ad5  mov     rdi, rcx
0x140003ad8  cmp     rcx, rbp
0x140003adb  jz      short loc_140003B0E
0x140003add  mov     rsi, [rdi]
0x140003ae0  jmp     short loc_140003AFD
0x140003ae2  mov     rbx, rsi
0x140003ae5  mov     rsi, [rsi+8]
0x140003ae9  call    cs:__imp_GetProcessHeap
0x140003aef  mov     r8, rbx; lpMem
0x140003af2  xor     edx, edx; dwFlags
0x140003af4  mov     rcx, rax; hHeap
0x140003af7  call    cs:__imp_HeapFree
0x140003afd  test    rsi, rsi
0x140003b00  jnz     short loc_140003AE2
0x140003b02  mov     [rdi], rsi
0x140003b05  add     rdi, 8
0x140003b09  cmp     rdi, rbp
0x140003b0c  jnz     short loc_140003ADD
0x140003b0e  add     rsp, 28h
0x140003b12  pop     rdi
0x140003b13  pop     rsi
0x140003b14  pop     rbp
0x140003b15  pop     rbx
0x140003b16  retn
```
