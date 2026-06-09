# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180007098`
- end: `0x180007128`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000832c`

## callees

- `0x180007098`
- `0x1800071b4`
- `0x180007284`
- `0x180009260`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070d3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070d3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070c5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070fc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800070fc`

## string_xrefs

- `0x180007116`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(
        __int64 *a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // r14
  __int64 v4; // rbp
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  const char *v8; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = a1 + 5;
  v3 = a1 + 15;
  while ( v1 != v3 )
  {
    v4 = *v1;
    while ( v4 )
    {
      v5 = v4;
      v4 = *(_QWORD *)(v4 + 8);
      wil::details_abi::ThreadLocalData::~ThreadLocalData((wil::details_abi::ThreadLocalData *)(v5 + 16));
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)v5);
    }
    *v1++ = 0;
  }
  wil::details_abi::SemaphoreValue::~SemaphoreValue((wil::details_abi::SemaphoreValue *)(a1 + 2));
  v7 = (void *)a1[1];
  if ( v7 )
  {
    if ( !CloseHandle(v7) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v8);
  }
}

```

## disassembly

```asm
0x180007098  push    rbx
0x18000709a  push    rbp
0x18000709b  push    rsi
0x18000709c  push    rdi
0x18000709d  push    r14
0x18000709f  sub     rsp, 20h
0x1800070a3  lea     rdi, [rcx+28h]
0x1800070a7  mov     rsi, rcx
0x1800070aa  lea     r14, [rdi+50h]
0x1800070ae  jmp     short loc_1800070E5
0x1800070b0  mov     rbp, [rdi]
0x1800070b3  jmp     short loc_1800070D9
0x1800070b5  mov     rbx, rbp
0x1800070b8  mov     rbp, [rbp+8]
0x1800070bc  lea     rcx, [rbx+10h]; this
0x1800070c0  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1800070c5  call    cs:__imp_GetProcessHeap
0x1800070cb  mov     r8, rbx; lpMem
0x1800070ce  xor     edx, edx; dwFlags
0x1800070d0  mov     rcx, rax; hHeap
0x1800070d3  call    cs:__imp_HeapFree
0x1800070d9  test    rbp, rbp
0x1800070dc  jnz     short loc_1800070B5
0x1800070de  mov     [rdi], rbp
0x1800070e1  add     rdi, 8
0x1800070e5  cmp     rdi, r14
0x1800070e8  jnz     short loc_1800070B0
0x1800070ea  lea     rcx, [rsi+10h]; this
0x1800070ee  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800070f3  mov     rcx, [rsi+8]; hObject
0x1800070f7  test    rcx, rcx
0x1800070fa  jz      short loc_180007106
0x1800070fc  call    cs:__imp_CloseHandle
0x180007102  test    eax, eax
0x180007104  jz      short loc_180007111
0x180007106  add     rsp, 20h
0x18000710a  pop     r14
0x18000710c  pop     rdi
0x18000710d  pop     rsi
0x18000710e  pop     rbp
0x18000710f  pop     rbx
0x180007110  retn
0x180007111  mov     rcx, [rsp+48h]; this
0x180007116  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000711d  mov     edx, 0A0Bh; void *
0x180007122  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
