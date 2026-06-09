# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180004a84`
- end: `0x180004ad3`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000bb40`

## callees

- `0x180004a84`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aa5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004aa5`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ab3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004ab3`

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
0x180004a84  push    rbx
0x180004a86  push    rbp
0x180004a87  push    rsi
0x180004a88  push    rdi
0x180004a89  sub     rsp, 28h
0x180004a8d  lea     rbp, [rcx+50h]
0x180004a91  mov     rdi, rcx
0x180004a94  cmp     rcx, rbp
0x180004a97  jz      short loc_180004ACA
0x180004a99  mov     rsi, [rdi]
0x180004a9c  jmp     short loc_180004AB9
0x180004a9e  mov     rbx, rsi
0x180004aa1  mov     rsi, [rsi+8]
0x180004aa5  call    cs:__imp_GetProcessHeap
0x180004aab  mov     r8, rbx; lpMem
0x180004aae  xor     edx, edx; dwFlags
0x180004ab0  mov     rcx, rax; hHeap
0x180004ab3  call    cs:__imp_HeapFree
0x180004ab9  test    rsi, rsi
0x180004abc  jnz     short loc_180004A9E
0x180004abe  mov     [rdi], rsi
0x180004ac1  add     rdi, 8
0x180004ac5  cmp     rdi, rbp
0x180004ac8  jnz     short loc_180004A99
0x180004aca  add     rsp, 28h
0x180004ace  pop     rdi
0x180004acf  pop     rsi
0x180004ad0  pop     rbp
0x180004ad1  pop     rbx
0x180004ad2  retn
```
