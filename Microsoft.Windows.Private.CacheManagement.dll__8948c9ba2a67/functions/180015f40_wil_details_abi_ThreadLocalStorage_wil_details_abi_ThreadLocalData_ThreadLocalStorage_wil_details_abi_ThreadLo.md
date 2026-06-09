# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180015f40`
- end: `0x180015fbf`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180015b90`

## callees

- `0x180014ed0`
- `0x180015f40`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180015f8e`
- `KERNEL32!HeapFree` at `0x180015f8e`
- `KERNEL32!GetProcessHeap` at `0x180015f80`
- `KERNEL32!GetProcessHeap` at `0x180015f80`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rsi
  __int64 v3; // rbx
  __int64 v4; // rdi
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
0x180015f40  mov     [rsp+arg_18], rbp
0x180015f45  push    rsi
0x180015f46  sub     rsp, 20h
0x180015f4a  lea     rbp, [rcx+50h]
0x180015f4e  mov     rsi, rcx
0x180015f51  cmp     rcx, rbp
0x180015f54  jz      short loc_180015FB4
0x180015f56  mov     [rsp+28h+arg_0], rbx
0x180015f5b  mov     [rsp+28h+arg_8], rdi
0x180015f60  mov     [rsp+28h+arg_10], r14
0x180015f65  xor     r14d, r14d
0x180015f68  mov     rbx, [rsi]
0x180015f6b  test    rbx, rbx
0x180015f6e  jz      short loc_180015F99
0x180015f70  mov     rdi, rbx
0x180015f73  mov     rbx, [rbx+8]
0x180015f77  lea     rcx, [rdi+10h]; this
0x180015f7b  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180015f80  call    cs:__imp_GetProcessHeap
0x180015f86  mov     r8, rdi; lpMem
0x180015f89  xor     edx, edx; dwFlags
0x180015f8b  mov     rcx, rax; hHeap
0x180015f8e  call    cs:__imp_HeapFree
0x180015f94  test    rbx, rbx
0x180015f97  jnz     short loc_180015F70
0x180015f99  mov     [rsi], r14
0x180015f9c  add     rsi, 8
0x180015fa0  cmp     rsi, rbp
0x180015fa3  jnz     short loc_180015F68
0x180015fa5  mov     r14, [rsp+28h+arg_10]
0x180015faa  mov     rdi, [rsp+28h+arg_8]
0x180015faf  mov     rbx, [rsp+28h+arg_0]
0x180015fb4  mov     rbp, [rsp+28h+arg_18]
0x180015fb9  add     rsp, 20h
0x180015fbd  pop     rsi
0x180015fbe  retn
```
