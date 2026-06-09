# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180017e2c`
- end: `0x180017e91`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180018fc0`

## callees

- `0x180017e2c`
- `0x180018004`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e56`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180017e56`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e6a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180017e6a`

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
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v4 + 16));
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
0x180017e2c  push    rbx
0x180017e2e  push    rbp
0x180017e2f  push    rsi
0x180017e30  push    rdi
0x180017e31  sub     rsp, 28h
0x180017e35  lea     rbp, [rcx+50h]
0x180017e39  mov     rdi, rcx
0x180017e3c  cmp     rcx, rbp
0x180017e3f  jz      short loc_180017E87
0x180017e41  mov     rsi, [rdi]
0x180017e44  jmp     short loc_180017E76
0x180017e46  mov     rbx, rsi
0x180017e49  mov     rsi, [rsi+8]
0x180017e4d  lea     rcx, [rbx+10h]; this
0x180017e51  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180017e56  call    cs:__imp_GetProcessHeap
0x180017e5d  nop     dword ptr [rax+rax+00h]
0x180017e62  mov     r8, rbx; lpMem
0x180017e65  xor     edx, edx; dwFlags
0x180017e67  mov     rcx, rax; hHeap
0x180017e6a  call    cs:__imp_HeapFree
0x180017e71  nop     dword ptr [rax+rax+00h]
0x180017e76  test    rsi, rsi
0x180017e79  jnz     short loc_180017E46
0x180017e7b  mov     [rdi], rsi
0x180017e7e  add     rdi, 8
0x180017e82  cmp     rdi, rbp
0x180017e85  jnz     short loc_180017E41
0x180017e87  add     rsp, 28h
0x180017e8b  pop     rdi
0x180017e8c  pop     rsi
0x180017e8d  pop     rbp
0x180017e8e  pop     rbx
0x180017e8f  retn
```
