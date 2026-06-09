# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140005e1c`
- end: `0x140005e8b`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `111`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1400053d8`

## callees

- `0x1400036b4`
- `0x140005e1c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140005e5f`
- `KERNEL32!HeapFree` at `0x140005e5f`
- `KERNEL32!GetProcessHeap` at `0x140005e51`
- `KERNEL32!GetProcessHeap` at `0x140005e51`

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
0x140005e1c  mov     [rsp+arg_0], rbx
0x140005e21  mov     [rsp+arg_8], rbp
0x140005e26  mov     [rsp+arg_10], rsi
0x140005e2b  push    rdi
0x140005e2c  sub     rsp, 20h
0x140005e30  lea     rbp, [rcx+50h]
0x140005e34  mov     rdi, rcx
0x140005e37  cmp     rcx, rbp
0x140005e3a  jz      short loc_140005E76
0x140005e3c  mov     rsi, [rdi]
0x140005e3f  jmp     short loc_140005E65
0x140005e41  mov     rbx, rsi
0x140005e44  mov     rsi, [rsi+8]
0x140005e48  lea     rcx, [rbx+10h]; this
0x140005e4c  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x140005e51  call    cs:__imp_GetProcessHeap
0x140005e57  mov     r8, rbx; lpMem
0x140005e5a  xor     edx, edx; dwFlags
0x140005e5c  mov     rcx, rax; hHeap
0x140005e5f  call    cs:__imp_HeapFree
0x140005e65  test    rsi, rsi
0x140005e68  jnz     short loc_140005E41
0x140005e6a  mov     [rdi], rsi
0x140005e6d  add     rdi, 8
0x140005e71  cmp     rdi, rbp
0x140005e74  jnz     short loc_140005E3C
0x140005e76  mov     rbx, [rsp+28h+arg_0]
0x140005e7b  mov     rbp, [rsp+28h+arg_8]
0x140005e80  mov     rsi, [rsp+28h+arg_10]
0x140005e85  add     rsp, 20h
0x140005e89  pop     rdi
0x140005e8a  retn
```
