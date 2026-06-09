# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180012080`
- end: `0x1800120fc`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011bf4`

## callees

- `0x180012080`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800120b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800120e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800120b3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800120e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800120a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800120d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800120a5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800120d6`

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
0x180012080  push    rbx
0x180012082  push    rbp
0x180012083  push    rsi
0x180012084  push    rdi
0x180012085  sub     rsp, 28h
0x180012089  movzx   eax, word ptr [rcx+20h]
0x18001208d  mov     rsi, rcx
0x180012090  mov     rdi, [rcx+18h]
0x180012094  lea     rbp, [rax+rax*4]
0x180012098  shl     rbp, 4
0x18001209c  add     rbp, rdi
0x18001209f  jmp     short loc_1800120CD
0x1800120a1  mov     rbx, [rdi+40h]
0x1800120a5  call    cs:__imp_GetProcessHeap
0x1800120ab  mov     r8, rbx; lpMem
0x1800120ae  xor     edx, edx; dwFlags
0x1800120b0  mov     rcx, rax; hHeap
0x1800120b3  call    cs:__imp_HeapFree
0x1800120b9  mov     qword ptr [rdi+40h], 0
0x1800120c1  mov     qword ptr [rdi+48h], 0
0x1800120c9  add     rdi, 50h ; 'P'
0x1800120cd  cmp     rdi, rbp
0x1800120d0  jnz     short loc_1800120A1
0x1800120d2  mov     rbx, [rsi+18h]
0x1800120d6  call    cs:__imp_GetProcessHeap
0x1800120dc  mov     r8, rbx; lpMem
0x1800120df  xor     edx, edx; dwFlags
0x1800120e1  mov     rcx, rax; hHeap
0x1800120e4  call    cs:__imp_HeapFree
0x1800120ea  xor     eax, eax
0x1800120ec  mov     [rsi+20h], eax
0x1800120ef  mov     [rsi+18h], rax
0x1800120f3  add     rsp, 28h
0x1800120f7  pop     rdi
0x1800120f8  pop     rsi
0x1800120f9  pop     rbp
0x1800120fa  pop     rbx
0x1800120fb  retn
```
