# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003800`
- end: `0x18000387c`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000322c`

## callees

- `0x180003800`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003864`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003833`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003864`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003825`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003856`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003825`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003856`

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
0x180003800  push    rbx
0x180003802  push    rbp
0x180003803  push    rsi
0x180003804  push    rdi
0x180003805  sub     rsp, 28h
0x180003809  movzx   eax, word ptr [rcx+20h]
0x18000380d  mov     rsi, rcx
0x180003810  mov     rdi, [rcx+18h]
0x180003814  lea     rbp, [rax+rax*4]
0x180003818  shl     rbp, 4
0x18000381c  add     rbp, rdi
0x18000381f  jmp     short loc_18000384D
0x180003821  mov     rbx, [rdi+40h]
0x180003825  call    cs:__imp_GetProcessHeap
0x18000382b  mov     r8, rbx; lpMem
0x18000382e  xor     edx, edx; dwFlags
0x180003830  mov     rcx, rax; hHeap
0x180003833  call    cs:__imp_HeapFree
0x180003839  mov     qword ptr [rdi+40h], 0
0x180003841  mov     qword ptr [rdi+48h], 0
0x180003849  add     rdi, 50h ; 'P'
0x18000384d  cmp     rdi, rbp
0x180003850  jnz     short loc_180003821
0x180003852  mov     rbx, [rsi+18h]
0x180003856  call    cs:__imp_GetProcessHeap
0x18000385c  mov     r8, rbx; lpMem
0x18000385f  xor     edx, edx; dwFlags
0x180003861  mov     rcx, rax; hHeap
0x180003864  call    cs:__imp_HeapFree
0x18000386a  xor     eax, eax
0x18000386c  mov     [rsi+20h], eax
0x18000386f  mov     [rsi+18h], rax
0x180003873  add     rsp, 28h
0x180003877  pop     rdi
0x180003878  pop     rsi
0x180003879  pop     rbp
0x18000387a  pop     rbx
0x18000387b  retn
```
