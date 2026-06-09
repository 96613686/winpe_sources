# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003d88`
- end: `0x140003e04`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003784`

## callees

- `0x140003d88`

## import_xrefs

- `KERNEL32!HeapFree` at `0x140003dbb`
- `KERNEL32!HeapFree` at `0x140003dec`
- `KERNEL32!HeapFree` at `0x140003dbb`
- `KERNEL32!HeapFree` at `0x140003dec`
- `KERNEL32!GetProcessHeap` at `0x140003dad`
- `KERNEL32!GetProcessHeap` at `0x140003dde`
- `KERNEL32!GetProcessHeap` at `0x140003dad`
- `KERNEL32!GetProcessHeap` at `0x140003dde`

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
0x140003d88  push    rbx
0x140003d8a  push    rbp
0x140003d8b  push    rsi
0x140003d8c  push    rdi
0x140003d8d  sub     rsp, 28h
0x140003d91  movzx   eax, word ptr [rcx+20h]
0x140003d95  mov     rsi, rcx
0x140003d98  mov     rdi, [rcx+18h]
0x140003d9c  lea     rbp, [rax+rax*4]
0x140003da0  shl     rbp, 4
0x140003da4  add     rbp, rdi
0x140003da7  jmp     short loc_140003DD5
0x140003da9  mov     rbx, [rdi+40h]
0x140003dad  call    cs:__imp_GetProcessHeap
0x140003db3  mov     r8, rbx; lpMem
0x140003db6  xor     edx, edx; dwFlags
0x140003db8  mov     rcx, rax; hHeap
0x140003dbb  call    cs:__imp_HeapFree
0x140003dc1  mov     qword ptr [rdi+40h], 0
0x140003dc9  mov     qword ptr [rdi+48h], 0
0x140003dd1  add     rdi, 50h ; 'P'
0x140003dd5  cmp     rdi, rbp
0x140003dd8  jnz     short loc_140003DA9
0x140003dda  mov     rbx, [rsi+18h]
0x140003dde  call    cs:__imp_GetProcessHeap
0x140003de4  mov     r8, rbx; lpMem
0x140003de7  xor     edx, edx; dwFlags
0x140003de9  mov     rcx, rax; hHeap
0x140003dec  call    cs:__imp_HeapFree
0x140003df2  xor     eax, eax
0x140003df4  mov     [rsi+20h], eax
0x140003df7  mov     [rsi+18h], rax
0x140003dfb  add     rsp, 28h
0x140003dff  pop     rdi
0x140003e00  pop     rsi
0x140003e01  pop     rbp
0x140003e02  pop     rbx
0x140003e03  retn
```
