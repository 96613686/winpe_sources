# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002dac`
- end: `0x180002e28`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002bf4`

## callees

- `0x180002dac`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e10`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002ddf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002e10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e02`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002dd1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002e02`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
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
0x180002dac  push    rbx
0x180002dae  push    rbp
0x180002daf  push    rsi
0x180002db0  push    rdi
0x180002db1  sub     rsp, 28h
0x180002db5  movzx   eax, word ptr [rcx+20h]
0x180002db9  mov     rsi, rcx
0x180002dbc  mov     rdi, [rcx+18h]
0x180002dc0  lea     rbp, [rax+rax*4]
0x180002dc4  shl     rbp, 4
0x180002dc8  add     rbp, rdi
0x180002dcb  jmp     short loc_180002DF9
0x180002dcd  mov     rbx, [rdi+40h]
0x180002dd1  call    cs:__imp_GetProcessHeap
0x180002dd7  mov     r8, rbx; lpMem
0x180002dda  xor     edx, edx; dwFlags
0x180002ddc  mov     rcx, rax; hHeap
0x180002ddf  call    cs:__imp_HeapFree
0x180002de5  mov     qword ptr [rdi+40h], 0
0x180002ded  mov     qword ptr [rdi+48h], 0
0x180002df5  add     rdi, 50h ; 'P'
0x180002df9  cmp     rdi, rbp
0x180002dfc  jnz     short loc_180002DCD
0x180002dfe  mov     rbx, [rsi+18h]
0x180002e02  call    cs:__imp_GetProcessHeap
0x180002e08  mov     r8, rbx; lpMem
0x180002e0b  xor     edx, edx; dwFlags
0x180002e0d  mov     rcx, rax; hHeap
0x180002e10  call    cs:__imp_HeapFree
0x180002e16  xor     eax, eax
0x180002e18  mov     [rsi+20h], eax
0x180002e1b  mov     [rsi+18h], rax
0x180002e1f  add     rsp, 28h
0x180002e23  pop     rdi
0x180002e24  pop     rsi
0x180002e25  pop     rbp
0x180002e26  pop     rbx
0x180002e27  retn
```
