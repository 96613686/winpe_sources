# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180005c30`
- end: `0x180005caf`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `127`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180005880`

## callees

- `0x1800049b0`
- `0x180005c30`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180005c7e`
- `KERNEL32!HeapFree` at `0x180005c7e`
- `KERNEL32!GetProcessHeap` at `0x180005c70`
- `KERNEL32!GetProcessHeap` at `0x180005c70`

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
0x180005c30  mov     [rsp+arg_18], rbp
0x180005c35  push    rsi
0x180005c36  sub     rsp, 20h
0x180005c3a  lea     rbp, [rcx+50h]
0x180005c3e  mov     rsi, rcx
0x180005c41  cmp     rcx, rbp
0x180005c44  jz      short loc_180005CA4
0x180005c46  mov     [rsp+28h+arg_0], rbx
0x180005c4b  mov     [rsp+28h+arg_8], rdi
0x180005c50  mov     [rsp+28h+arg_10], r14
0x180005c55  xor     r14d, r14d
0x180005c58  mov     rbx, [rsi]
0x180005c5b  test    rbx, rbx
0x180005c5e  jz      short loc_180005C89
0x180005c60  mov     rdi, rbx
0x180005c63  mov     rbx, [rbx+8]
0x180005c67  lea     rcx, [rdi+10h]; this
0x180005c6b  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180005c70  call    cs:__imp_GetProcessHeap
0x180005c76  mov     r8, rdi; lpMem
0x180005c79  xor     edx, edx; dwFlags
0x180005c7b  mov     rcx, rax; hHeap
0x180005c7e  call    cs:__imp_HeapFree
0x180005c84  test    rbx, rbx
0x180005c87  jnz     short loc_180005C60
0x180005c89  mov     [rsi], r14
0x180005c8c  add     rsi, 8
0x180005c90  cmp     rsi, rbp
0x180005c93  jnz     short loc_180005C58
0x180005c95  mov     r14, [rsp+28h+arg_10]
0x180005c9a  mov     rdi, [rsp+28h+arg_8]
0x180005c9f  mov     rbx, [rsp+28h+arg_0]
0x180005ca4  mov     rbp, [rsp+28h+arg_18]
0x180005ca9  add     rsp, 20h
0x180005cad  pop     rsi
0x180005cae  retn
```
