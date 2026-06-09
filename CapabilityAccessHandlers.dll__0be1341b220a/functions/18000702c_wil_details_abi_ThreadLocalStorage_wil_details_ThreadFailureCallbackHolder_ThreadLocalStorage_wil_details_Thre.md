# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x18000702c`
- end: `0x18000707b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180013970`

## callees

- `0x18000702c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000705b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000705b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000704d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000704d`

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
0x18000702c  push    rbx
0x18000702e  push    rbp
0x18000702f  push    rsi
0x180007030  push    rdi
0x180007031  sub     rsp, 28h
0x180007035  lea     rbp, [rcx+50h]
0x180007039  mov     rdi, rcx
0x18000703c  cmp     rcx, rbp
0x18000703f  jz      short loc_180007072
0x180007041  mov     rsi, [rdi]
0x180007044  jmp     short loc_180007061
0x180007046  mov     rbx, rsi
0x180007049  mov     rsi, [rsi+8]
0x18000704d  call    cs:__imp_GetProcessHeap
0x180007053  mov     r8, rbx; lpMem
0x180007056  xor     edx, edx; dwFlags
0x180007058  mov     rcx, rax; hHeap
0x18000705b  call    cs:__imp_HeapFree
0x180007061  test    rsi, rsi
0x180007064  jnz     short loc_180007046
0x180007066  mov     [rdi], rsi
0x180007069  add     rdi, 8
0x18000706d  cmp     rdi, rbp
0x180007070  jnz     short loc_180007041
0x180007072  add     rsp, 28h
0x180007076  pop     rdi
0x180007077  pop     rsi
0x180007078  pop     rbp
0x180007079  pop     rbx
0x18000707a  retn
```
