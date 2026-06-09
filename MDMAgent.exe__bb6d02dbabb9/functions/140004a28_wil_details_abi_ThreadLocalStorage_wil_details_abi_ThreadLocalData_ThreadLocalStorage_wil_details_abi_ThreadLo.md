# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140004a28`
- end: `0x140004a8d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140004994`

## callees

- `0x140004a28`
- `0x140005078`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a52`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140004a52`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a66`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140004a66`

## pseudocode

```c
void __fastcall wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rbp
  __int64 *v2; // rdi
  __int64 v3; // rsi
  __int64 v4; // rbx
  HANDLE ProcessHeap; // rax

  v1 = a1 + 10;
  v2 = a1;
  do
  {
    v3 = *v2;
    while ( v3 )
    {
      v4 = v3;
      v3 = *(_QWORD *)(v3 + 8);
      wil::details_abi::ThreadLocalData::Clear((wil::details_abi::ThreadLocalData *)(v4 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v4);
    }
    *v2++ = 0;
  }
  while ( v2 != v1 );
}

```

## disassembly

```asm
0x140004a28  push    rbx
0x140004a2a  push    rbp
0x140004a2b  push    rsi
0x140004a2c  push    rdi
0x140004a2d  sub     rsp, 28h
0x140004a31  lea     rbp, [rcx+50h]
0x140004a35  mov     rdi, rcx
0x140004a38  cmp     rcx, rbp
0x140004a3b  jz      short loc_140004A83
0x140004a3d  mov     rsi, [rdi]
0x140004a40  jmp     short loc_140004A72
0x140004a42  mov     rbx, rsi
0x140004a45  mov     rsi, [rsi+8]
0x140004a49  lea     rcx, [rbx+10h]; this
0x140004a4d  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x140004a52  call    cs:__imp_GetProcessHeap
0x140004a59  nop     dword ptr [rax+rax+00h]
0x140004a5e  mov     r8, rbx; lpMem
0x140004a61  xor     edx, edx; dwFlags
0x140004a63  mov     rcx, rax; hHeap
0x140004a66  call    cs:__imp_HeapFree
0x140004a6d  nop     dword ptr [rax+rax+00h]
0x140004a72  test    rsi, rsi
0x140004a75  jnz     short loc_140004A42
0x140004a77  mov     [rdi], rsi
0x140004a7a  add     rdi, 8
0x140004a7e  cmp     rdi, rbp
0x140004a81  jnz     short loc_140004A3D
0x140004a83  add     rsp, 28h
0x140004a87  pop     rdi
0x140004a88  pop     rsi
0x140004a89  pop     rbp
0x140004a8a  pop     rbx
0x140004a8b  retn
```
