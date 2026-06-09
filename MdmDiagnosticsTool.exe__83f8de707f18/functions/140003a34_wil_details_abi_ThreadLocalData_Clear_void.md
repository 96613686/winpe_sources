# wil::details_abi::ThreadLocalData::Clear(void)

- ea: `0x140003a34`
- end: `0x140003ac9`
- name: `?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ`
- size: `149`
- prototype: `void __fastcall(wil::details_abi::ThreadLocalData *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140003304`

## callees

- `0x140003a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003aaa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003a6d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003aaa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a59`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140003a96`

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
0x140003a34  push    rbx
0x140003a36  push    rbp
0x140003a37  push    rsi
0x140003a38  push    rdi
0x140003a39  sub     rsp, 28h
0x140003a3d  movzx   eax, word ptr [rcx+20h]
0x140003a41  mov     rsi, rcx
0x140003a44  mov     rdi, [rcx+18h]
0x140003a48  lea     rbp, [rax+rax*4]
0x140003a4c  shl     rbp, 4
0x140003a50  add     rbp, rdi
0x140003a53  jmp     short loc_140003A8D
0x140003a55  mov     rbx, [rdi+40h]
0x140003a59  call    cs:__imp_GetProcessHeap
0x140003a60  nop     dword ptr [rax+rax+00h]
0x140003a65  mov     r8, rbx; lpMem
0x140003a68  xor     edx, edx; dwFlags
0x140003a6a  mov     rcx, rax; hHeap
0x140003a6d  call    cs:__imp_HeapFree
0x140003a74  nop     dword ptr [rax+rax+00h]
0x140003a79  mov     qword ptr [rdi+40h], 0
0x140003a81  mov     qword ptr [rdi+48h], 0
0x140003a89  add     rdi, 50h ; 'P'
0x140003a8d  cmp     rdi, rbp
0x140003a90  jnz     short loc_140003A55
0x140003a92  mov     rbx, [rsi+18h]
0x140003a96  call    cs:__imp_GetProcessHeap
0x140003a9d  nop     dword ptr [rax+rax+00h]
0x140003aa2  mov     r8, rbx; lpMem
0x140003aa5  xor     edx, edx; dwFlags
0x140003aa7  mov     rcx, rax; hHeap
0x140003aaa  call    cs:__imp_HeapFree
0x140003ab1  nop     dword ptr [rax+rax+00h]
0x140003ab6  xor     eax, eax
0x140003ab8  mov     [rsi+20h], eax
0x140003abb  mov     [rsi+18h], rax
0x140003abf  add     rsp, 28h
0x140003ac3  pop     rdi
0x140003ac4  pop     rsi
0x140003ac5  pop     rbp
0x140003ac6  pop     rbx
0x140003ac7  retn
```
