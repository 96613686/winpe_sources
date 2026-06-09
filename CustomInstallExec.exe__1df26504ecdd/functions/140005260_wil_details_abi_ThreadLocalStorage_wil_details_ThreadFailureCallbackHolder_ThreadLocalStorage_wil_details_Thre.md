# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x140005260`
- end: `0x1400052af`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14000ee90`

## callees

- `0x140005260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000528f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000528f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005281`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140005281`

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
0x140005260  push    rbx
0x140005262  push    rbp
0x140005263  push    rsi
0x140005264  push    rdi
0x140005265  sub     rsp, 28h
0x140005269  lea     rbp, [rcx+50h]
0x14000526d  mov     rdi, rcx
0x140005270  cmp     rcx, rbp
0x140005273  jz      short loc_1400052A6
0x140005275  mov     rsi, [rdi]
0x140005278  jmp     short loc_140005295
0x14000527a  mov     rbx, rsi
0x14000527d  mov     rsi, [rsi+8]
0x140005281  call    cs:__imp_GetProcessHeap
0x140005287  mov     r8, rbx; lpMem
0x14000528a  xor     edx, edx; dwFlags
0x14000528c  mov     rcx, rax; hHeap
0x14000528f  call    cs:__imp_HeapFree
0x140005295  test    rsi, rsi
0x140005298  jnz     short loc_14000527A
0x14000529a  mov     [rdi], rsi
0x14000529d  add     rdi, 8
0x1400052a1  cmp     rdi, rbp
0x1400052a4  jnz     short loc_140005275
0x1400052a6  add     rsp, 28h
0x1400052aa  pop     rdi
0x1400052ab  pop     rsi
0x1400052ac  pop     rbp
0x1400052ad  pop     rbx
0x1400052ae  retn
```
