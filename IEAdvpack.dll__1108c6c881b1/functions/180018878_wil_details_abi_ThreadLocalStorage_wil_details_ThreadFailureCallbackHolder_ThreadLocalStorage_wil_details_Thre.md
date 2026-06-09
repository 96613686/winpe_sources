# wil::details_abi::ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>::~ThreadLocalStorage<wil::details::ThreadFailureCallbackHolder *>(void)

- ea: `0x180018878`
- end: `0x1800188c7`
- name: `??1?$ThreadLocalStorage@PEAVThreadFailureCallbackHolder@details@wil@@@details_abi@wil@@QEAA@XZ`
- size: `79`
- prototype: `void __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bd90`

## callees

- `0x180018878`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800188a7`
- `KERNEL32!HeapFree` at `0x1800188a7`
- `KERNEL32!GetProcessHeap` at `0x180018899`
- `KERNEL32!GetProcessHeap` at `0x180018899`

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
0x180018878  push    rbx
0x18001887a  push    rbp
0x18001887b  push    rsi
0x18001887c  push    rdi
0x18001887d  sub     rsp, 28h
0x180018881  lea     rbp, [rcx+50h]
0x180018885  mov     rdi, rcx
0x180018888  cmp     rcx, rbp
0x18001888b  jz      short loc_1800188BE
0x18001888d  mov     rsi, [rdi]
0x180018890  jmp     short loc_1800188AD
0x180018892  mov     rbx, rsi
0x180018895  mov     rsi, [rsi+8]
0x180018899  call    cs:__imp_GetProcessHeap
0x18001889f  mov     r8, rbx; lpMem
0x1800188a2  xor     edx, edx; dwFlags
0x1800188a4  mov     rcx, rax; hHeap
0x1800188a7  call    cs:__imp_HeapFree
0x1800188ad  test    rsi, rsi
0x1800188b0  jnz     short loc_180018892
0x1800188b2  mov     [rdi], rsi
0x1800188b5  add     rdi, 8
0x1800188b9  cmp     rdi, rbp
0x1800188bc  jnz     short loc_18001888D
0x1800188be  add     rsp, 28h
0x1800188c2  pop     rdi
0x1800188c3  pop     rsi
0x1800188c4  pop     rbp
0x1800188c5  pop     rbx
0x1800188c6  retn
```
