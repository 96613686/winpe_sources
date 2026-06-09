# D3D12PsoDatabase::DeserializeContext::AllocateMemory(unsigned __int64)

- ea: `0x1801832a4`
- end: `0x180183307`
- name: `?AllocateMemory@DeserializeContext@D3D12PsoDatabase@@AEAAPEAX_K@Z`
- size: `99`
- prototype: `void *(D3D12PsoDatabase::DeserializeContext *__hidden this, unsigned __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18017b330`
- `0x18017b6a0`

## callees

- `0x18004dc60`
- `0x1801832a4`
- `0x1801896a0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801832e6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1801832e6`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1801832d1`
- `api-ms-win-core-heap-l1-1-0!HeapCreate` at `0x1801832d1`

## pseudocode

```c
LPVOID __fastcall D3D12PsoDatabase::DeserializeContext::AllocateMemory(
        D3D12PsoDatabase::DeserializeContext *this,
        SIZE_T a2)
{
  HANDLE v4; // rax
  LPVOID v5; // rbx
  _BYTE v7[24]; // [rsp+20h] [rbp-18h] BYREF

  D3D12PsoDatabase::DeserializeContext::Lock(this, v7);
  v4 = (HANDLE)*((_QWORD *)this + 29);
  if ( !v4 )
  {
    v4 = HeapCreate(0, 0, 0);
    *((_QWORD *)this + 29) = v4;
  }
  v5 = HeapAlloc(v4, 0, a2);
  std::unique_lock<std::mutex>::~unique_lock<std::mutex>(v7);
  return v5;
}

```

## disassembly

```asm
0x1801832a4  mov     [rsp+arg_0], rbx
0x1801832a9  push    rdi
0x1801832aa  sub     rsp, 30h
0x1801832ae  mov     rdi, rdx
0x1801832b1  mov     rbx, rcx
0x1801832b4  lea     rdx, [rsp+38h+var_18]
0x1801832b9  call    ?Lock@DeserializeContext@D3D12PsoDatabase@@AEAA?AV?$unique_lock@Vmutex@std@@@std@@XZ; D3D12PsoDatabase::DeserializeContext::Lock(void)
0x1801832be  mov     rax, [rbx+0E8h]
0x1801832c5  test    rax, rax
0x1801832c8  jnz     short loc_1801832DE
0x1801832ca  xor     r8d, r8d; dwMaximumSize
0x1801832cd  xor     edx, edx; dwInitialSize
0x1801832cf  xor     ecx, ecx; flOptions
0x1801832d1  call    cs:__imp_HeapCreate
0x1801832d7  mov     [rbx+0E8h], rax
0x1801832de  mov     r8, rdi; dwBytes
0x1801832e1  xor     edx, edx; dwFlags
0x1801832e3  mov     rcx, rax; hHeap
0x1801832e6  call    cs:__imp_HeapAlloc
0x1801832ec  lea     rcx, [rsp+38h+var_18]
0x1801832f1  mov     rbx, rax
0x1801832f4  call    ??1?$unique_lock@Vmutex@std@@@std@@QEAA@XZ; std::unique_lock<std::mutex>::~unique_lock<std::mutex>(void)
0x1801832f9  mov     rax, rbx
0x1801832fc  mov     rbx, [rsp+38h+arg_0]
0x180183301  add     rsp, 30h
0x180183305  pop     rdi
0x180183306  retn
```
