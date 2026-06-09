# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x1800039ac`
- end: `0x180003a41`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800036dc`

## callees

- `0x1800039ac`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800039e5`
- `KERNEL32!HeapFree` at `0x180003a22`
- `KERNEL32!HeapFree` at `0x1800039e5`
- `KERNEL32!HeapFree` at `0x180003a22`
- `KERNEL32!GetProcessHeap` at `0x1800039d1`
- `KERNEL32!GetProcessHeap` at `0x180003a0e`
- `KERNEL32!GetProcessHeap` at `0x1800039d1`
- `KERNEL32!GetProcessHeap` at `0x180003a0e`

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
0x1800039ac  push    rbx
0x1800039ae  push    rbp
0x1800039af  push    rsi
0x1800039b0  push    rdi
0x1800039b1  sub     rsp, 28h
0x1800039b5  movzx   eax, word ptr [rcx+20h]
0x1800039b9  mov     rsi, rcx
0x1800039bc  mov     rdi, [rcx+18h]
0x1800039c0  lea     rbp, [rax+rax*4]
0x1800039c4  shl     rbp, 4
0x1800039c8  add     rbp, rdi
0x1800039cb  jmp     short loc_180003A05
0x1800039cd  mov     rbx, [rdi+40h]
0x1800039d1  call    cs:__imp_GetProcessHeap
0x1800039d8  nop     dword ptr [rax+rax+00h]
0x1800039dd  mov     r8, rbx; lpMem
0x1800039e0  xor     edx, edx; dwFlags
0x1800039e2  mov     rcx, rax; hHeap
0x1800039e5  call    cs:__imp_HeapFree
0x1800039ec  nop     dword ptr [rax+rax+00h]
0x1800039f1  mov     qword ptr [rdi+40h], 0
0x1800039f9  mov     qword ptr [rdi+48h], 0
0x180003a01  add     rdi, 50h ; 'P'
0x180003a05  cmp     rdi, rbp
0x180003a08  jnz     short loc_1800039CD
0x180003a0a  mov     rbx, [rsi+18h]
0x180003a0e  call    cs:__imp_GetProcessHeap
0x180003a15  nop     dword ptr [rax+rax+00h]
0x180003a1a  mov     r8, rbx; lpMem
0x180003a1d  xor     edx, edx; dwFlags
0x180003a1f  mov     rcx, rax; hHeap
0x180003a22  call    cs:__imp_HeapFree
0x180003a29  nop     dword ptr [rax+rax+00h]
0x180003a2e  xor     eax, eax
0x180003a30  mov     [rsi+20h], eax
0x180003a33  mov     [rsi+18h], rax
0x180003a37  add     rsp, 28h
0x180003a3b  pop     rdi
0x180003a3c  pop     rsi
0x180003a3d  pop     rbp
0x180003a3e  pop     rbx
0x180003a3f  retn
```
