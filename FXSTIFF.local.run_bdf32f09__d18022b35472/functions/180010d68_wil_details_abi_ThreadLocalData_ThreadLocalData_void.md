# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180010d68`
- end: `0x180010de4`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `124`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001053c`

## callees

- `0x180010d68`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180010d9b`
- `KERNEL32!HeapFree` at `0x180010dcc`
- `KERNEL32!HeapFree` at `0x180010d9b`
- `KERNEL32!HeapFree` at `0x180010dcc`
- `KERNEL32!GetProcessHeap` at `0x180010d8d`
- `KERNEL32!GetProcessHeap` at `0x180010dbe`
- `KERNEL32!GetProcessHeap` at `0x180010d8d`
- `KERNEL32!GetProcessHeap` at `0x180010dbe`

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
0x180010d68  push    rbx
0x180010d6a  push    rbp
0x180010d6b  push    rsi
0x180010d6c  push    rdi
0x180010d6d  sub     rsp, 28h
0x180010d71  movzx   eax, word ptr [rcx+20h]
0x180010d75  mov     rsi, rcx
0x180010d78  mov     rdi, [rcx+18h]
0x180010d7c  lea     rbp, [rax+rax*4]
0x180010d80  shl     rbp, 4
0x180010d84  add     rbp, rdi
0x180010d87  jmp     short loc_180010DB5
0x180010d89  mov     rbx, [rdi+40h]
0x180010d8d  call    cs:__imp_GetProcessHeap
0x180010d93  mov     r8, rbx; lpMem
0x180010d96  xor     edx, edx; dwFlags
0x180010d98  mov     rcx, rax; hHeap
0x180010d9b  call    cs:__imp_HeapFree
0x180010da1  mov     qword ptr [rdi+40h], 0
0x180010da9  mov     qword ptr [rdi+48h], 0
0x180010db1  add     rdi, 50h ; 'P'
0x180010db5  cmp     rdi, rbp
0x180010db8  jnz     short loc_180010D89
0x180010dba  mov     rbx, [rsi+18h]
0x180010dbe  call    cs:__imp_GetProcessHeap
0x180010dc4  mov     r8, rbx; lpMem
0x180010dc7  xor     edx, edx; dwFlags
0x180010dc9  mov     rcx, rax; hHeap
0x180010dcc  call    cs:__imp_HeapFree
0x180010dd2  xor     eax, eax
0x180010dd4  mov     [rsi+20h], eax
0x180010dd7  mov     [rsi+18h], rax
0x180010ddb  add     rsp, 28h
0x180010ddf  pop     rdi
0x180010de0  pop     rsi
0x180010de1  pop     rbp
0x180010de2  pop     rbx
0x180010de3  retn
```
