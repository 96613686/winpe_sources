# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x140003868`
- end: `0x1400038e4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400036b8`

## callees

- `0x140003868`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000389b`
- `KERNEL32!HeapFree` at `0x1400038cc`
- `KERNEL32!HeapFree` at `0x14000389b`
- `KERNEL32!HeapFree` at `0x1400038cc`
- `KERNEL32!GetProcessHeap` at `0x14000388d`
- `KERNEL32!GetProcessHeap` at `0x1400038be`
- `KERNEL32!GetProcessHeap` at `0x14000388d`
- `KERNEL32!GetProcessHeap` at `0x1400038be`

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
0x140003868  push    rbx
0x14000386a  push    rbp
0x14000386b  push    rsi
0x14000386c  push    rdi
0x14000386d  sub     rsp, 28h
0x140003871  movzx   eax, word ptr [rcx+20h]
0x140003875  mov     rsi, rcx
0x140003878  mov     rdi, [rcx+18h]
0x14000387c  lea     rbp, [rax+rax*4]
0x140003880  shl     rbp, 4
0x140003884  add     rbp, rdi
0x140003887  jmp     short loc_1400038B5
0x140003889  mov     rbx, [rdi+40h]
0x14000388d  call    cs:__imp_GetProcessHeap
0x140003893  mov     r8, rbx; lpMem
0x140003896  xor     edx, edx; dwFlags
0x140003898  mov     rcx, rax; hHeap
0x14000389b  call    cs:__imp_HeapFree
0x1400038a1  mov     qword ptr [rdi+40h], 0
0x1400038a9  mov     qword ptr [rdi+48h], 0
0x1400038b1  add     rdi, 50h ; 'P'
0x1400038b5  cmp     rdi, rbp
0x1400038b8  jnz     short loc_140003889
0x1400038ba  mov     rbx, [rsi+18h]
0x1400038be  call    cs:__imp_GetProcessHeap
0x1400038c4  mov     r8, rbx; lpMem
0x1400038c7  xor     edx, edx; dwFlags
0x1400038c9  mov     rcx, rax; hHeap
0x1400038cc  call    cs:__imp_HeapFree
0x1400038d2  xor     eax, eax
0x1400038d4  mov     [rsi+20h], eax
0x1400038d7  mov     [rsi+18h], rax
0x1400038db  add     rsp, 28h
0x1400038df  pop     rdi
0x1400038e0  pop     rsi
0x1400038e1  pop     rbp
0x1400038e2  pop     rbx
0x1400038e3  retn
```
