# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x140003304`
- end: `0x140003369`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140003270`

## callees

- `0x140003304`
- `0x140003a34`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003342`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140003342`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000332e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000332e`

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
0x140003304  push    rbx
0x140003306  push    rbp
0x140003307  push    rsi
0x140003308  push    rdi
0x140003309  sub     rsp, 28h
0x14000330d  lea     rbp, [rcx+50h]
0x140003311  mov     rdi, rcx
0x140003314  cmp     rcx, rbp
0x140003317  jz      short loc_14000335F
0x140003319  mov     rsi, [rdi]
0x14000331c  jmp     short loc_14000334E
0x14000331e  mov     rbx, rsi
0x140003321  mov     rsi, [rsi+8]
0x140003325  lea     rcx, [rbx+10h]; this
0x140003329  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x14000332e  call    cs:__imp_GetProcessHeap
0x140003335  nop     dword ptr [rax+rax+00h]
0x14000333a  mov     r8, rbx; lpMem
0x14000333d  xor     edx, edx; dwFlags
0x14000333f  mov     rcx, rax; hHeap
0x140003342  call    cs:__imp_HeapFree
0x140003349  nop     dword ptr [rax+rax+00h]
0x14000334e  test    rsi, rsi
0x140003351  jnz     short loc_14000331E
0x140003353  mov     [rdi], rsi
0x140003356  add     rdi, 8
0x14000335a  cmp     rdi, rbp
0x14000335d  jnz     short loc_140003319
0x14000335f  add     rsp, 28h
0x140003363  pop     rdi
0x140003364  pop     rsi
0x140003365  pop     rbp
0x140003366  pop     rbx
0x140003367  retn
```
