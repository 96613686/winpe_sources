# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800046f8`
- end: `0x180004774`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180003fc4`

## callees

- `0x1800046f8`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000472b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000475c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000472b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000475c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000471d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000474e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000471d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000474e`

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
0x1800046f8  push    rbx
0x1800046fa  push    rbp
0x1800046fb  push    rsi
0x1800046fc  push    rdi
0x1800046fd  sub     rsp, 28h
0x180004701  movzx   eax, word ptr [rcx+20h]
0x180004705  mov     rsi, rcx
0x180004708  mov     rdi, [rcx+18h]
0x18000470c  lea     rbp, [rax+rax*4]
0x180004710  shl     rbp, 4
0x180004714  add     rbp, rdi
0x180004717  jmp     short loc_180004745
0x180004719  mov     rbx, [rdi+40h]
0x18000471d  call    cs:__imp_GetProcessHeap
0x180004723  mov     r8, rbx; lpMem
0x180004726  xor     edx, edx; dwFlags
0x180004728  mov     rcx, rax; hHeap
0x18000472b  call    cs:__imp_HeapFree
0x180004731  mov     qword ptr [rdi+40h], 0
0x180004739  mov     qword ptr [rdi+48h], 0
0x180004741  add     rdi, 50h ; 'P'
0x180004745  cmp     rdi, rbp
0x180004748  jnz     short loc_180004719
0x18000474a  mov     rbx, [rsi+18h]
0x18000474e  call    cs:__imp_GetProcessHeap
0x180004754  mov     r8, rbx; lpMem
0x180004757  xor     edx, edx; dwFlags
0x180004759  mov     rcx, rax; hHeap
0x18000475c  call    cs:__imp_HeapFree
0x180004762  xor     eax, eax
0x180004764  mov     [rsi+20h], eax
0x180004767  mov     [rsi+18h], rax
0x18000476b  add     rsp, 28h
0x18000476f  pop     rdi
0x180004770  pop     rsi
0x180004771  pop     rbp
0x180004772  pop     rbx
0x180004773  retn
```
