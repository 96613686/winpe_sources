# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180002c04`
- end: `0x180002c80`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002a4c`

## callees

- `0x180002c04`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180002c5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180002c68`

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
0x180002c04  push    rbx
0x180002c06  push    rbp
0x180002c07  push    rsi
0x180002c08  push    rdi
0x180002c09  sub     rsp, 28h
0x180002c0d  movzx   eax, word ptr [rcx+20h]
0x180002c11  mov     rsi, rcx
0x180002c14  mov     rdi, [rcx+18h]
0x180002c18  lea     rbp, [rax+rax*4]
0x180002c1c  shl     rbp, 4
0x180002c20  add     rbp, rdi
0x180002c23  jmp     short loc_180002C51
0x180002c25  mov     rbx, [rdi+40h]
0x180002c29  call    cs:__imp_GetProcessHeap
0x180002c2f  mov     r8, rbx; lpMem
0x180002c32  xor     edx, edx; dwFlags
0x180002c34  mov     rcx, rax; hHeap
0x180002c37  call    cs:__imp_HeapFree
0x180002c3d  mov     qword ptr [rdi+40h], 0
0x180002c45  mov     qword ptr [rdi+48h], 0
0x180002c4d  add     rdi, 50h ; 'P'
0x180002c51  cmp     rdi, rbp
0x180002c54  jnz     short loc_180002C25
0x180002c56  mov     rbx, [rsi+18h]
0x180002c5a  call    cs:__imp_GetProcessHeap
0x180002c60  mov     r8, rbx; lpMem
0x180002c63  xor     edx, edx; dwFlags
0x180002c65  mov     rcx, rax; hHeap
0x180002c68  call    cs:__imp_HeapFree
0x180002c6e  xor     eax, eax
0x180002c70  mov     [rsi+20h], eax
0x180002c73  mov     [rsi+18h], rax
0x180002c77  add     rsp, 28h
0x180002c7b  pop     rdi
0x180002c7c  pop     rsi
0x180002c7d  pop     rbp
0x180002c7e  pop     rbx
0x180002c7f  retn
```
