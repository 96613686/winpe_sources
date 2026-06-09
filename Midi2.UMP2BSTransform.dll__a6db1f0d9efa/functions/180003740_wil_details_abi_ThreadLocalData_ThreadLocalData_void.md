# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003740`
- end: `0x1800037bc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800034d8`

## callees

- `0x180003740`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003796`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003765`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003796`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003773`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800037a4`

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
0x180003740  push    rbx
0x180003742  push    rbp
0x180003743  push    rsi
0x180003744  push    rdi
0x180003745  sub     rsp, 28h
0x180003749  movzx   eax, word ptr [rcx+20h]
0x18000374d  mov     rsi, rcx
0x180003750  mov     rdi, [rcx+18h]
0x180003754  lea     rbp, [rax+rax*4]
0x180003758  shl     rbp, 4
0x18000375c  add     rbp, rdi
0x18000375f  jmp     short loc_18000378D
0x180003761  mov     rbx, [rdi+40h]
0x180003765  call    cs:__imp_GetProcessHeap
0x18000376b  mov     r8, rbx; lpMem
0x18000376e  xor     edx, edx; dwFlags
0x180003770  mov     rcx, rax; hHeap
0x180003773  call    cs:__imp_HeapFree
0x180003779  mov     qword ptr [rdi+40h], 0
0x180003781  mov     qword ptr [rdi+48h], 0
0x180003789  add     rdi, 50h ; 'P'
0x18000378d  cmp     rdi, rbp
0x180003790  jnz     short loc_180003761
0x180003792  mov     rbx, [rsi+18h]
0x180003796  call    cs:__imp_GetProcessHeap
0x18000379c  mov     r8, rbx; lpMem
0x18000379f  xor     edx, edx; dwFlags
0x1800037a1  mov     rcx, rax; hHeap
0x1800037a4  call    cs:__imp_HeapFree
0x1800037aa  xor     eax, eax
0x1800037ac  mov     [rsi+20h], eax
0x1800037af  mov     [rsi+18h], rax
0x1800037b3  add     rsp, 28h
0x1800037b7  pop     rdi
0x1800037b8  pop     rsi
0x1800037b9  pop     rbp
0x1800037ba  pop     rbx
0x1800037bb  retn
```
