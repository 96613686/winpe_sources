# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x18001ba98`
- end: `0x18001bb14`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b2dc`

## callees

- `0x18001ba98`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bacb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bafc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bacb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001bafc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001babd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001baee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001babd`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001baee`

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
0x18001ba98  push    rbx
0x18001ba9a  push    rbp
0x18001ba9b  push    rsi
0x18001ba9c  push    rdi
0x18001ba9d  sub     rsp, 28h
0x18001baa1  movzx   eax, word ptr [rcx+20h]
0x18001baa5  mov     rsi, rcx
0x18001baa8  mov     rdi, [rcx+18h]
0x18001baac  lea     rbp, [rax+rax*4]
0x18001bab0  shl     rbp, 4
0x18001bab4  add     rbp, rdi
0x18001bab7  jmp     short loc_18001BAE5
0x18001bab9  mov     rbx, [rdi+40h]
0x18001babd  call    cs:__imp_GetProcessHeap
0x18001bac3  mov     r8, rbx; lpMem
0x18001bac6  xor     edx, edx; dwFlags
0x18001bac8  mov     rcx, rax; hHeap
0x18001bacb  call    cs:__imp_HeapFree
0x18001bad1  mov     qword ptr [rdi+40h], 0
0x18001bad9  mov     qword ptr [rdi+48h], 0
0x18001bae1  add     rdi, 50h ; 'P'
0x18001bae5  cmp     rdi, rbp
0x18001bae8  jnz     short loc_18001BAB9
0x18001baea  mov     rbx, [rsi+18h]
0x18001baee  call    cs:__imp_GetProcessHeap
0x18001baf4  mov     r8, rbx; lpMem
0x18001baf7  xor     edx, edx; dwFlags
0x18001baf9  mov     rcx, rax; hHeap
0x18001bafc  call    cs:__imp_HeapFree
0x18001bb02  xor     eax, eax
0x18001bb04  mov     [rsi+20h], eax
0x18001bb07  mov     [rsi+18h], rax
0x18001bb0b  add     rsp, 28h
0x18001bb0f  pop     rdi
0x18001bb10  pop     rsi
0x18001bb11  pop     rbp
0x18001bb12  pop     rbx
0x18001bb13  retn
```
