# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180009428`
- end: `0x1800094ba`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `146`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a0d8`

## callees

- `0x180009428`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000945f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000948b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000945f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000948b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000946d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009499`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000946d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009499`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::~ThreadLocalData(wil::details_abi::ThreadLocalData *this)
{
  __int64 v1; // rdi
  __int64 v3; // rbp
  __int64 v4; // rdi
  void *v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rbx
  HANDLE v8; // rax

  v1 = *((_QWORD *)this + 3);
  v3 = v1 + 80LL * *((unsigned __int16 *)this + 16);
  if ( v1 != v3 )
  {
    v4 = v1 + 64;
    do
    {
      v5 = *(void **)v4;
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v5);
      *(_QWORD *)v4 = 0;
      *(_QWORD *)(v4 + 8) = 0;
      v4 += 80;
    }
    while ( v4 - 64 != v3 );
  }
  v7 = (void *)*((_QWORD *)this + 3);
  v8 = GetProcessHeap();
  HeapFree(v8, 0, v7);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 3) = 0;
}

```

## disassembly

```asm
0x180009428  mov     [rsp+arg_8], rbx
0x18000942d  mov     [rsp+arg_10], rbp
0x180009432  push    rsi
0x180009433  push    rdi
0x180009434  push    r14
0x180009436  sub     rsp, 20h
0x18000943a  mov     rdi, [rcx+18h]
0x18000943e  xor     r14d, r14d
0x180009441  movzx   eax, word ptr [rcx+20h]
0x180009445  mov     rsi, rcx
0x180009448  lea     rbp, [rax+rax*4]
0x18000944c  shl     rbp, 4
0x180009450  add     rbp, rdi
0x180009453  cmp     rdi, rbp
0x180009456  jz      short loc_180009487
0x180009458  add     rdi, 40h ; '@'
0x18000945c  mov     rbx, [rdi]
0x18000945f  call    cs:__imp_GetProcessHeap
0x180009465  mov     r8, rbx; lpMem
0x180009468  xor     edx, edx; dwFlags
0x18000946a  mov     rcx, rax; hHeap
0x18000946d  call    cs:__imp_HeapFree
0x180009473  mov     [rdi], r14
0x180009476  mov     [rdi+8], r14
0x18000947a  lea     rdi, [rdi+50h]
0x18000947e  lea     rax, [rdi-40h]
0x180009482  cmp     rax, rbp
0x180009485  jnz     short loc_18000945C
0x180009487  mov     rbx, [rsi+18h]
0x18000948b  call    cs:__imp_GetProcessHeap
0x180009491  mov     r8, rbx; lpMem
0x180009494  xor     edx, edx; dwFlags
0x180009496  mov     rcx, rax; hHeap
0x180009499  call    cs:__imp_HeapFree
0x18000949f  mov     rbx, [rsp+38h+arg_8]
0x1800094a4  mov     rbp, [rsp+38h+arg_10]
0x1800094a9  mov     [rsi+20h], r14d
0x1800094ad  mov     [rsi+18h], r14
0x1800094b1  add     rsp, 20h
0x1800094b5  pop     r14
0x1800094b7  pop     rdi
0x1800094b8  pop     rsi
0x1800094b9  retn
```
