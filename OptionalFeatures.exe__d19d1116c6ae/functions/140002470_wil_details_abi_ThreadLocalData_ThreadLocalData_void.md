# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140002470`
- end: `0x1400024ec`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400023a4`

## callees

- `0x140002470`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400024a3`
- `KERNEL32!HeapFree` at `0x1400024d4`
- `KERNEL32!HeapFree` at `0x1400024a3`
- `KERNEL32!HeapFree` at `0x1400024d4`
- `KERNEL32!GetProcessHeap` at `0x140002495`
- `KERNEL32!GetProcessHeap` at `0x1400024c6`
- `KERNEL32!GetProcessHeap` at `0x140002495`
- `KERNEL32!GetProcessHeap` at `0x1400024c6`

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
0x140002470  push    rbx
0x140002472  push    rbp
0x140002473  push    rsi
0x140002474  push    rdi
0x140002475  sub     rsp, 28h
0x140002479  movzx   eax, word ptr [rcx+20h]
0x14000247d  mov     rsi, rcx
0x140002480  mov     rdi, [rcx+18h]
0x140002484  lea     rbp, [rax+rax*4]
0x140002488  shl     rbp, 4
0x14000248c  add     rbp, rdi
0x14000248f  jmp     short loc_1400024BD
0x140002491  mov     rbx, [rdi+40h]
0x140002495  call    cs:__imp_GetProcessHeap
0x14000249b  mov     r8, rbx; lpMem
0x14000249e  xor     edx, edx; dwFlags
0x1400024a0  mov     rcx, rax; hHeap
0x1400024a3  call    cs:__imp_HeapFree
0x1400024a9  mov     qword ptr [rdi+40h], 0
0x1400024b1  mov     qword ptr [rdi+48h], 0
0x1400024b9  add     rdi, 50h ; 'P'
0x1400024bd  cmp     rdi, rbp
0x1400024c0  jnz     short loc_140002491
0x1400024c2  mov     rbx, [rsi+18h]
0x1400024c6  call    cs:__imp_GetProcessHeap
0x1400024cc  mov     r8, rbx; lpMem
0x1400024cf  xor     edx, edx; dwFlags
0x1400024d1  mov     rcx, rax; hHeap
0x1400024d4  call    cs:__imp_HeapFree
0x1400024da  xor     eax, eax
0x1400024dc  mov     [rsi+20h], eax
0x1400024df  mov     [rsi+18h], rax
0x1400024e3  add     rsp, 28h
0x1400024e7  pop     rdi
0x1400024e8  pop     rsi
0x1400024e9  pop     rbp
0x1400024ea  pop     rbx
0x1400024eb  retn
```
