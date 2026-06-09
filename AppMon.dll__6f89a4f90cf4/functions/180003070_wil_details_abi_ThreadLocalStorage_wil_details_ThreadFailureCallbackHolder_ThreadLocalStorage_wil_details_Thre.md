# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180003070`
- end: `0x1800030bf`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000fbf0`

## callees

- `0x180003070`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000309f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000309f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003091`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003091`

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
0x180003070  push    rbx
0x180003072  push    rbp
0x180003073  push    rsi
0x180003074  push    rdi
0x180003075  sub     rsp, 28h
0x180003079  lea     rbp, [rcx+50h]
0x18000307d  mov     rdi, rcx
0x180003080  cmp     rcx, rbp
0x180003083  jz      short loc_1800030B6
0x180003085  mov     rsi, [rdi]
0x180003088  jmp     short loc_1800030A5
0x18000308a  mov     rbx, rsi
0x18000308d  mov     rsi, [rsi+8]
0x180003091  call    cs:__imp_GetProcessHeap
0x180003097  mov     r8, rbx; lpMem
0x18000309a  xor     edx, edx; dwFlags
0x18000309c  mov     rcx, rax; hHeap
0x18000309f  call    cs:__imp_HeapFree
0x1800030a5  test    rsi, rsi
0x1800030a8  jnz     short loc_18000308A
0x1800030aa  mov     [rdi], rsi
0x1800030ad  add     rdi, 8
0x1800030b1  cmp     rdi, rbp
0x1800030b4  jnz     short loc_180003085
0x1800030b6  add     rsp, 28h
0x1800030ba  pop     rdi
0x1800030bb  pop     rsi
0x1800030bc  pop     rbp
0x1800030bd  pop     rbx
0x1800030be  retn
```
