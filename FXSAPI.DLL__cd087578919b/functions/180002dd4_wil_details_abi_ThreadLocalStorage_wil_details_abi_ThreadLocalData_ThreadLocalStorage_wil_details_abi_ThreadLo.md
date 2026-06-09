# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180002dd4`
- end: `0x180002e39`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x1800076f0`

## callees

- `0x180002dd4`
- `0x180003414`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180002dfe`
- `KERNEL32!GetProcessHeap` at `0x180002dfe`
- `KERNEL32!HeapFree` at `0x180002e12`
- `KERNEL32!HeapFree` at `0x180002e12`

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
0x180002dd4  push    rbx
0x180002dd6  push    rbp
0x180002dd7  push    rsi
0x180002dd8  push    rdi
0x180002dd9  sub     rsp, 28h
0x180002ddd  lea     rbp, [rcx+50h]
0x180002de1  mov     rdi, rcx
0x180002de4  cmp     rcx, rbp
0x180002de7  jz      short loc_180002E2F
0x180002de9  mov     rsi, [rdi]
0x180002dec  jmp     short loc_180002E1E
0x180002dee  mov     rbx, rsi
0x180002df1  mov     rsi, [rsi+8]
0x180002df5  lea     rcx, [rbx+10h]; this
0x180002df9  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180002dfe  call    cs:__imp_GetProcessHeap
0x180002e05  nop     dword ptr [rax+rax+00h]
0x180002e0a  mov     r8, rbx; lpMem
0x180002e0d  xor     edx, edx; dwFlags
0x180002e0f  mov     rcx, rax; hHeap
0x180002e12  call    cs:__imp_HeapFree
0x180002e19  nop     dword ptr [rax+rax+00h]
0x180002e1e  test    rsi, rsi
0x180002e21  jnz     short loc_180002DEE
0x180002e23  mov     [rdi], rsi
0x180002e26  add     rdi, 8
0x180002e2a  cmp     rdi, rbp
0x180002e2d  jnz     short loc_180002DE9
0x180002e2f  add     rsp, 28h
0x180002e33  pop     rdi
0x180002e34  pop     rsi
0x180002e35  pop     rbp
0x180002e36  pop     rbx
0x180002e37  retn
```
