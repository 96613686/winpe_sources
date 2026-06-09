# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180007704`
- end: `0x180007780`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000736c`

## callees

- `0x180007704`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000775a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007729`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000775a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007768`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007737`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007768`

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
0x180007704  push    rbx
0x180007706  push    rbp
0x180007707  push    rsi
0x180007708  push    rdi
0x180007709  sub     rsp, 28h
0x18000770d  movzx   eax, word ptr [rcx+20h]
0x180007711  mov     rsi, rcx
0x180007714  mov     rdi, [rcx+18h]
0x180007718  lea     rbp, [rax+rax*4]
0x18000771c  shl     rbp, 4
0x180007720  add     rbp, rdi
0x180007723  jmp     short loc_180007751
0x180007725  mov     rbx, [rdi+40h]
0x180007729  call    cs:__imp_GetProcessHeap
0x18000772f  mov     r8, rbx; lpMem
0x180007732  xor     edx, edx; dwFlags
0x180007734  mov     rcx, rax; hHeap
0x180007737  call    cs:__imp_HeapFree
0x18000773d  mov     qword ptr [rdi+40h], 0
0x180007745  mov     qword ptr [rdi+48h], 0
0x18000774d  add     rdi, 50h ; 'P'
0x180007751  cmp     rdi, rbp
0x180007754  jnz     short loc_180007725
0x180007756  mov     rbx, [rsi+18h]
0x18000775a  call    cs:__imp_GetProcessHeap
0x180007760  mov     r8, rbx; lpMem
0x180007763  xor     edx, edx; dwFlags
0x180007765  mov     rcx, rax; hHeap
0x180007768  call    cs:__imp_HeapFree
0x18000776e  xor     eax, eax
0x180007770  mov     [rsi+20h], eax
0x180007773  mov     [rsi+18h], rax
0x180007777  add     rsp, 28h
0x18000777b  pop     rdi
0x18000777c  pop     rsi
0x18000777d  pop     rbp
0x18000777e  pop     rbx
0x18000777f  retn
```
