# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180002ecc`
- end: `0x180002f1b`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f560`

## callees

- `0x180002ecc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002efb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002efb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002eed`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002eed`

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
0x180002ecc  push    rbx
0x180002ece  push    rbp
0x180002ecf  push    rsi
0x180002ed0  push    rdi
0x180002ed1  sub     rsp, 28h
0x180002ed5  lea     rbp, [rcx+50h]
0x180002ed9  mov     rdi, rcx
0x180002edc  cmp     rcx, rbp
0x180002edf  jz      short loc_180002F12
0x180002ee1  mov     rsi, [rdi]
0x180002ee4  jmp     short loc_180002F01
0x180002ee6  mov     rbx, rsi
0x180002ee9  mov     rsi, [rsi+8]
0x180002eed  call    cs:__imp_GetProcessHeap
0x180002ef3  mov     r8, rbx; lpMem
0x180002ef6  xor     edx, edx; dwFlags
0x180002ef8  mov     rcx, rax; hHeap
0x180002efb  call    cs:__imp_HeapFree
0x180002f01  test    rsi, rsi
0x180002f04  jnz     short loc_180002EE6
0x180002f06  mov     [rdi], rsi
0x180002f09  add     rdi, 8
0x180002f0d  cmp     rdi, rbp
0x180002f10  jnz     short loc_180002EE1
0x180002f12  add     rsp, 28h
0x180002f16  pop     rdi
0x180002f17  pop     rsi
0x180002f18  pop     rbp
0x180002f19  pop     rbx
0x180002f1a  retn
```
