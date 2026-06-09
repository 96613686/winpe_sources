# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180005060`
- end: `0x1800050af`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180017cc0`

## callees

- `0x180005060`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005081`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005081`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000508f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000508f`

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
0x180005060  push    rbx
0x180005062  push    rbp
0x180005063  push    rsi
0x180005064  push    rdi
0x180005065  sub     rsp, 28h
0x180005069  lea     rbp, [rcx+50h]
0x18000506d  mov     rdi, rcx
0x180005070  cmp     rcx, rbp
0x180005073  jz      short loc_1800050A6
0x180005075  mov     rsi, [rdi]
0x180005078  jmp     short loc_180005095
0x18000507a  mov     rbx, rsi
0x18000507d  mov     rsi, [rsi+8]
0x180005081  call    cs:__imp_GetProcessHeap
0x180005087  mov     r8, rbx; lpMem
0x18000508a  xor     edx, edx; dwFlags
0x18000508c  mov     rcx, rax; hHeap
0x18000508f  call    cs:__imp_HeapFree
0x180005095  test    rsi, rsi
0x180005098  jnz     short loc_18000507A
0x18000509a  mov     [rdi], rsi
0x18000509d  add     rdi, 8
0x1800050a1  cmp     rdi, rbp
0x1800050a4  jnz     short loc_180005075
0x1800050a6  add     rsp, 28h
0x1800050aa  pop     rdi
0x1800050ab  pop     rsi
0x1800050ac  pop     rbp
0x1800050ad  pop     rbx
0x1800050ae  retn
```
