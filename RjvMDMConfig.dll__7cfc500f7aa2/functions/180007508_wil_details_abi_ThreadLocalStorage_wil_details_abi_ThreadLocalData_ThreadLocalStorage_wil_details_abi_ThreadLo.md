# wil::details_abi::ThreadLocalStorage<wil::details_abi::ThreadLocalData>::~ThreadLocalStorage<wil::details_abi::ThreadLocalData>(void)

- ea: `0x180007508`
- end: `0x18000756d`
- name: `??1?$ThreadLocalStorage@UThreadLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180007444`

## callees

- `0x180007508`
- `0x1800084bc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007546`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007546`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007532`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007532`

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
0x180007508  push    rbx
0x18000750a  push    rbp
0x18000750b  push    rsi
0x18000750c  push    rdi
0x18000750d  sub     rsp, 28h
0x180007511  lea     rbp, [rcx+50h]
0x180007515  mov     rdi, rcx
0x180007518  cmp     rcx, rbp
0x18000751b  jz      short loc_180007563
0x18000751d  mov     rsi, [rdi]
0x180007520  jmp     short loc_180007552
0x180007522  mov     rbx, rsi
0x180007525  mov     rsi, [rsi+8]
0x180007529  lea     rcx, [rbx+10h]; this
0x18000752d  call    ?Clear@ThreadLocalData@details_abi@wil@@QEAAXXZ; wil::details_abi::ThreadLocalData::Clear(void)
0x180007532  call    cs:__imp_GetProcessHeap
0x180007539  nop     dword ptr [rax+rax+00h]
0x18000753e  mov     r8, rbx; lpMem
0x180007541  xor     edx, edx; dwFlags
0x180007543  mov     rcx, rax; hHeap
0x180007546  call    cs:__imp_HeapFree
0x18000754d  nop     dword ptr [rax+rax+00h]
0x180007552  test    rsi, rsi
0x180007555  jnz     short loc_180007522
0x180007557  mov     [rdi], rsi
0x18000755a  add     rdi, 8
0x18000755e  cmp     rdi, rbp
0x180007561  jnz     short loc_18000751D
0x180007563  add     rsp, 28h
0x180007567  pop     rdi
0x180007568  pop     rsi
0x180007569  pop     rbp
0x18000756a  pop     rbx
0x18000756b  retn
```
