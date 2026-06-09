# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x1800033a4`
- end: `0x180003439`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002f74`

## callees

- `0x1800033a4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003406`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800033c9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003406`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000341a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800033dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000341a`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
{
  __int64 v2; // rdi
  __int64 v3; // rbp
  void *v4; // rbx
  HANDLE ProcessHeap; // rax
  void *v6; // rbx
  HANDLE v7; // rax

  v2 = *((_QWORD *)this + 3);
  v3 = v2 + 80LL * *((unsigned __int16 *)this + 16);
  while ( v2 != v3 )
  {
    v4 = *(void **)(v2 + 64);
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v4);
    *(_QWORD *)(v2 + 64) = 0;
    *(_QWORD *)(v2 + 72) = 0;
    v2 += 80;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  v7 = GetProcessHeap();
  HeapFree(v7, 0, v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x1800033a4  push    rbx
0x1800033a6  push    rbp
0x1800033a7  push    rsi
0x1800033a8  push    rdi
0x1800033a9  sub     rsp, 28h
0x1800033ad  movzx   eax, word ptr [rcx+20h]
0x1800033b1  mov     rsi, rcx
0x1800033b4  mov     rdi, [rcx+18h]
0x1800033b8  lea     rbp, [rax+rax*4]
0x1800033bc  shl     rbp, 4
0x1800033c0  add     rbp, rdi
0x1800033c3  jmp     short loc_1800033FD
0x1800033c5  mov     rbx, [rdi+40h]
0x1800033c9  call    cs:__imp_GetProcessHeap
0x1800033d0  nop     dword ptr [rax+rax+00h]
0x1800033d5  mov     r8, rbx; lpMem
0x1800033d8  xor     edx, edx; dwFlags
0x1800033da  mov     rcx, rax; hHeap
0x1800033dd  call    cs:__imp_HeapFree
0x1800033e4  nop     dword ptr [rax+rax+00h]
0x1800033e9  mov     qword ptr [rdi+40h], 0
0x1800033f1  mov     qword ptr [rdi+48h], 0
0x1800033f9  add     rdi, 50h ; 'P'
0x1800033fd  cmp     rdi, rbp
0x180003400  jnz     short loc_1800033C5
0x180003402  mov     rbx, [rsi+18h]
0x180003406  call    cs:__imp_GetProcessHeap
0x18000340d  nop     dword ptr [rax+rax+00h]
0x180003412  mov     r8, rbx; lpMem
0x180003415  xor     edx, edx; dwFlags
0x180003417  mov     rcx, rax; hHeap
0x18000341a  call    cs:__imp_HeapFree
0x180003421  nop     dword ptr [rax+rax+00h]
0x180003426  xor     eax, eax
0x180003428  mov     [rsi+20h], eax
0x18000342b  mov     [rsi+18h], rax
0x18000342f  add     rsp, 28h
0x180003433  pop     rdi
0x180003434  pop     rsi
0x180003435  pop     rbp
0x180003436  pop     rbx
0x180003437  retn
```
