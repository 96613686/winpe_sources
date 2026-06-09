# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1400049c4`
- end: `0x140004a20`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `92`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140019c50`

## callees

- `0x1400049c4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049e5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400049e5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049f9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400049f9`

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
0x1400049c4  push    rbx
0x1400049c6  push    rbp
0x1400049c7  push    rsi
0x1400049c8  push    rdi
0x1400049c9  sub     rsp, 28h
0x1400049cd  lea     rbp, [rcx+50h]
0x1400049d1  mov     rdi, rcx
0x1400049d4  cmp     rcx, rbp
0x1400049d7  jz      short loc_140004A16
0x1400049d9  mov     rsi, [rdi]
0x1400049dc  jmp     short loc_140004A05
0x1400049de  mov     rbx, rsi
0x1400049e1  mov     rsi, [rsi+8]
0x1400049e5  call    cs:__imp_GetProcessHeap
0x1400049ec  nop     dword ptr [rax+rax+00h]
0x1400049f1  mov     r8, rbx; lpMem
0x1400049f4  xor     edx, edx; dwFlags
0x1400049f6  mov     rcx, rax; hHeap
0x1400049f9  call    cs:__imp_HeapFree
0x140004a00  nop     dword ptr [rax+rax+00h]
0x140004a05  test    rsi, rsi
0x140004a08  jnz     short loc_1400049DE
0x140004a0a  mov     [rdi], rsi
0x140004a0d  add     rdi, 8
0x140004a11  cmp     rdi, rbp
0x140004a14  jnz     short loc_1400049D9
0x140004a16  add     rsp, 28h
0x140004a1a  pop     rdi
0x140004a1b  pop     rsi
0x140004a1c  pop     rbp
0x140004a1d  pop     rbx
0x140004a1e  retn
```
