# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140002e3c`
- end: `0x140002e8b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140008a00`

## callees

- `0x140002e3c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002e5d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140002e5d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002e6b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140002e6b`

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
0x140002e3c  push    rbx
0x140002e3e  push    rbp
0x140002e3f  push    rsi
0x140002e40  push    rdi
0x140002e41  sub     rsp, 28h
0x140002e45  lea     rbp, [rcx+50h]
0x140002e49  mov     rdi, rcx
0x140002e4c  cmp     rcx, rbp
0x140002e4f  jz      short loc_140002E82
0x140002e51  mov     rsi, [rdi]
0x140002e54  jmp     short loc_140002E71
0x140002e56  mov     rbx, rsi
0x140002e59  mov     rsi, [rsi+8]
0x140002e5d  call    cs:__imp_GetProcessHeap
0x140002e63  mov     r8, rbx; lpMem
0x140002e66  xor     edx, edx; dwFlags
0x140002e68  mov     rcx, rax; hHeap
0x140002e6b  call    cs:__imp_HeapFree
0x140002e71  test    rsi, rsi
0x140002e74  jnz     short loc_140002E56
0x140002e76  mov     [rdi], rsi
0x140002e79  add     rdi, 8
0x140002e7d  cmp     rdi, rbp
0x140002e80  jnz     short loc_140002E51
0x140002e82  add     rsp, 28h
0x140002e86  pop     rdi
0x140002e87  pop     rsi
0x140002e88  pop     rbp
0x140002e89  pop     rbx
0x140002e8a  retn
```
