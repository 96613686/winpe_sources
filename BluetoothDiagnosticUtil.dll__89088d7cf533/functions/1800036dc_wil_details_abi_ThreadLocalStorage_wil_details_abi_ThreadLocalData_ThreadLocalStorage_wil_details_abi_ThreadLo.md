# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x1800036dc`
- end: `0x180003741`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180006d54`

## callees

- `0x1800036dc`
- `0x1800039ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x18000371a`
- `KERNEL32!HeapFree` at `0x18000371a`
- `KERNEL32!GetProcessHeap` at `0x180003706`
- `KERNEL32!GetProcessHeap` at `0x180003706`

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
0x1800036dc  push    rbx
0x1800036de  push    rbp
0x1800036df  push    rsi
0x1800036e0  push    rdi
0x1800036e1  sub     rsp, 28h
0x1800036e5  lea     rbp, [rcx+50h]
0x1800036e9  mov     rdi, rcx
0x1800036ec  cmp     rcx, rbp
0x1800036ef  jz      short loc_180003737
0x1800036f1  mov     rsi, [rdi]
0x1800036f4  jmp     short loc_180003726
0x1800036f6  mov     rbx, rsi
0x1800036f9  mov     rsi, [rsi+8]
0x1800036fd  lea     rcx, [rbx+10h]; this
0x180003701  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180003706  call    cs:__imp_GetProcessHeap
0x18000370d  nop     dword ptr [rax+rax+00h]
0x180003712  mov     r8, rbx; lpMem
0x180003715  xor     edx, edx; dwFlags
0x180003717  mov     rcx, rax; hHeap
0x18000371a  call    cs:__imp_HeapFree
0x180003721  nop     dword ptr [rax+rax+00h]
0x180003726  test    rsi, rsi
0x180003729  jnz     short loc_1800036F6
0x18000372b  mov     [rdi], rsi
0x18000372e  add     rdi, 8
0x180003732  cmp     rdi, rbp
0x180003735  jnz     short loc_1800036F1
0x180003737  add     rsp, 28h
0x18000373b  pop     rdi
0x18000373c  pop     rsi
0x18000373d  pop     rbp
0x18000373e  pop     rbx
0x18000373f  retn
```
