# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180010d24`
- end: `0x180010d89`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180014bc0`

## callees

- `0x180010d24`
- `0x180011418`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010d62`
- `KERNEL32!HeapFree` at `0x180010d62`
- `KERNEL32!GetProcessHeap` at `0x180010d4e`
- `KERNEL32!GetProcessHeap` at `0x180010d4e`

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
0x180010d24  push    rbx
0x180010d26  push    rbp
0x180010d27  push    rsi
0x180010d28  push    rdi
0x180010d29  sub     rsp, 28h
0x180010d2d  lea     rbp, [rcx+50h]
0x180010d31  mov     rdi, rcx
0x180010d34  cmp     rcx, rbp
0x180010d37  jz      short loc_180010D7F
0x180010d39  mov     rsi, [rdi]
0x180010d3c  jmp     short loc_180010D6E
0x180010d3e  mov     rbx, rsi
0x180010d41  mov     rsi, [rsi+8]
0x180010d45  lea     rcx, [rbx+10h]; this
0x180010d49  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180010d4e  call    cs:__imp_GetProcessHeap
0x180010d55  nop     dword ptr [rax+rax+00h]
0x180010d5a  mov     r8, rbx; lpMem
0x180010d5d  xor     edx, edx; dwFlags
0x180010d5f  mov     rcx, rax; hHeap
0x180010d62  call    cs:__imp_HeapFree
0x180010d69  nop     dword ptr [rax+rax+00h]
0x180010d6e  test    rsi, rsi
0x180010d71  jnz     short loc_180010D3E
0x180010d73  mov     [rdi], rsi
0x180010d76  add     rdi, 8
0x180010d7a  cmp     rdi, rbp
0x180010d7d  jnz     short loc_180010D39
0x180010d7f  add     rsp, 28h
0x180010d83  pop     rdi
0x180010d84  pop     rsi
0x180010d85  pop     rbp
0x180010d86  pop     rbx
0x180010d87  retn
```
