# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x1800141dc`
- end: `0x18001422b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c3d0`

## callees

- `0x1800141dc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800141fd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800141fd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001420b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001420b`

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
0x1800141dc  push    rbx
0x1800141de  push    rbp
0x1800141df  push    rsi
0x1800141e0  push    rdi
0x1800141e1  sub     rsp, 28h
0x1800141e5  lea     rbp, [rcx+50h]
0x1800141e9  mov     rdi, rcx
0x1800141ec  cmp     rcx, rbp
0x1800141ef  jz      short loc_180014222
0x1800141f1  mov     rsi, [rdi]
0x1800141f4  jmp     short loc_180014211
0x1800141f6  mov     rbx, rsi
0x1800141f9  mov     rsi, [rsi+8]
0x1800141fd  call    cs:__imp_GetProcessHeap
0x180014203  mov     r8, rbx; lpMem
0x180014206  xor     edx, edx; dwFlags
0x180014208  mov     rcx, rax; hHeap
0x18001420b  call    cs:__imp_HeapFree
0x180014211  test    rsi, rsi
0x180014214  jnz     short loc_1800141F6
0x180014216  mov     [rdi], rsi
0x180014219  add     rdi, 8
0x18001421d  cmp     rdi, rbp
0x180014220  jnz     short loc_1800141F1
0x180014222  add     rsp, 28h
0x180014226  pop     rdi
0x180014227  pop     rsi
0x180014228  pop     rbp
0x180014229  pop     rbx
0x18001422a  retn
```
