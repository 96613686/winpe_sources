# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002f74`
- end: `0x180002fd9`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002eb8`

## callees

- `0x180002f74`
- `0x1800033a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fb2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002fb2`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x180002f74  push    rbx
0x180002f76  push    rbp
0x180002f77  push    rsi
0x180002f78  push    rdi
0x180002f79  sub     rsp, 28h
0x180002f7d  lea     rbp, [rcx+50h]
0x180002f81  mov     rdi, rcx
0x180002f84  cmp     rcx, rbp
0x180002f87  jz      short loc_180002FCF
0x180002f89  mov     rsi, [rdi]
0x180002f8c  jmp     short loc_180002FBE
0x180002f8e  mov     rbx, rsi
0x180002f91  mov     rsi, [rsi+8]
0x180002f95  lea     rcx, [rbx+10h]; this
0x180002f99  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180002f9e  call    cs:__imp_GetProcessHeap
0x180002fa5  nop     dword ptr [rax+rax+00h]
0x180002faa  mov     r8, rbx; lpMem
0x180002fad  xor     edx, edx; dwFlags
0x180002faf  mov     rcx, rax; hHeap
0x180002fb2  call    cs:__imp_HeapFree
0x180002fb9  nop     dword ptr [rax+rax+00h]
0x180002fbe  test    rsi, rsi
0x180002fc1  jnz     short loc_180002F8E
0x180002fc3  mov     [rdi], rsi
0x180002fc6  add     rdi, 8
0x180002fca  cmp     rdi, rbp
0x180002fcd  jnz     short loc_180002F89
0x180002fcf  add     rsp, 28h
0x180002fd3  pop     rdi
0x180002fd4  pop     rsi
0x180002fd5  pop     rbp
0x180002fd6  pop     rbx
0x180002fd7  retn
```
