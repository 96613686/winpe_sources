# wil::details_abi::ThreadLocalData::~ThreadLocalData(void)

- ea: `0x180003414`
- end: `0x1800034a9`
- name: `??1ThreadLocalData@details_abi@wil@@QEAA@XZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002dd4`

## callees

- `0x180003414`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180003439`
- `KERNEL32!GetProcessHeap` at `0x180003476`
- `KERNEL32!GetProcessHeap` at `0x180003439`
- `KERNEL32!GetProcessHeap` at `0x180003476`
- `KERNEL32!HeapFree` at `0x18000344d`
- `KERNEL32!HeapFree` at `0x18000348a`
- `KERNEL32!HeapFree` at `0x18000344d`
- `KERNEL32!HeapFree` at `0x18000348a`

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
0x180003414  push    rbx
0x180003416  push    rbp
0x180003417  push    rsi
0x180003418  push    rdi
0x180003419  sub     rsp, 28h
0x18000341d  movzx   eax, word ptr [rcx+20h]
0x180003421  mov     rsi, rcx
0x180003424  mov     rdi, [rcx+18h]
0x180003428  lea     rbp, [rax+rax*4]
0x18000342c  shl     rbp, 4
0x180003430  add     rbp, rdi
0x180003433  jmp     short loc_18000346D
0x180003435  mov     rbx, [rdi+40h]
0x180003439  call    cs:__imp_GetProcessHeap
0x180003440  nop     dword ptr [rax+rax+00h]
0x180003445  mov     r8, rbx; lpMem
0x180003448  xor     edx, edx; dwFlags
0x18000344a  mov     rcx, rax; hHeap
0x18000344d  call    cs:__imp_HeapFree
0x180003454  nop     dword ptr [rax+rax+00h]
0x180003459  mov     qword ptr [rdi+40h], 0
0x180003461  mov     qword ptr [rdi+48h], 0
0x180003469  add     rdi, 50h ; 'P'
0x18000346d  cmp     rdi, rbp
0x180003470  jnz     short loc_180003435
0x180003472  mov     rbx, [rsi+18h]
0x180003476  call    cs:__imp_GetProcessHeap
0x18000347d  nop     dword ptr [rax+rax+00h]
0x180003482  mov     r8, rbx; lpMem
0x180003485  xor     edx, edx; dwFlags
0x180003487  mov     rcx, rax; hHeap
0x18000348a  call    cs:__imp_HeapFree
0x180003491  nop     dword ptr [rax+rax+00h]
0x180003496  xor     eax, eax
0x180003498  mov     [rsi+20h], eax
0x18000349b  mov     [rsi+18h], rax
0x18000349f  add     rsp, 28h
0x1800034a3  pop     rdi
0x1800034a4  pop     rsi
0x1800034a5  pop     rbp
0x1800034a6  pop     rbx
0x1800034a7  retn
```
