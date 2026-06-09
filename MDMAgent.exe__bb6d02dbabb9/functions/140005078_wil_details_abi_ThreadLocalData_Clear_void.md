# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x140005078`
- end: `0x14000510d`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140004a28`

## callees

- `0x140005078`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000509d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400050da`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000509d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400050da`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400050b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400050ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400050b1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400050ee`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalData::Clear(wil::details_abi::ThreadLocalData *this)
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
0x140005078  push    rbx
0x14000507a  push    rbp
0x14000507b  push    rsi
0x14000507c  push    rdi
0x14000507d  sub     rsp, 28h
0x140005081  movzx   eax, word ptr [rcx+20h]
0x140005085  mov     rsi, rcx
0x140005088  mov     rdi, [rcx+18h]
0x14000508c  lea     rbp, [rax+rax*4]
0x140005090  shl     rbp, 4
0x140005094  add     rbp, rdi
0x140005097  jmp     short loc_1400050D1
0x140005099  mov     rbx, [rdi+40h]
0x14000509d  call    cs:__imp_GetProcessHeap
0x1400050a4  nop     dword ptr [rax+rax+00h]
0x1400050a9  mov     r8, rbx; lpMem
0x1400050ac  xor     edx, edx; dwFlags
0x1400050ae  mov     rcx, rax; hHeap
0x1400050b1  call    cs:__imp_HeapFree
0x1400050b8  nop     dword ptr [rax+rax+00h]
0x1400050bd  mov     qword ptr [rdi+40h], 0
0x1400050c5  mov     qword ptr [rdi+48h], 0
0x1400050cd  add     rdi, 50h ; 'P'
0x1400050d1  cmp     rdi, rbp
0x1400050d4  jnz     short loc_140005099
0x1400050d6  mov     rbx, [rsi+18h]
0x1400050da  call    cs:__imp_GetProcessHeap
0x1400050e1  nop     dword ptr [rax+rax+00h]
0x1400050e6  mov     r8, rbx; lpMem
0x1400050e9  xor     edx, edx; dwFlags
0x1400050eb  mov     rcx, rax; hHeap
0x1400050ee  call    cs:__imp_HeapFree
0x1400050f5  nop     dword ptr [rax+rax+00h]
0x1400050fa  xor     eax, eax
0x1400050fc  mov     [rsi+20h], eax
0x1400050ff  mov     [rsi+18h], rax
0x140005103  add     rsp, 28h
0x140005107  pop     rdi
0x140005108  pop     rsi
0x140005109  pop     rbp
0x14000510a  pop     rbx
0x14000510b  retn
```
