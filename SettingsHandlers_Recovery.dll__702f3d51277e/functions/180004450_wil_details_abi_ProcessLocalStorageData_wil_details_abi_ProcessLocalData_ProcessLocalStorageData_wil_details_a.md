# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180004450`
- end: `0x1800044e0`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000879c`

## callees

- `0x180004450`
- `0x180004ab8`
- `0x180004b88`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000447d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000447d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000448b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000448b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044b4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800044b4`

## string_xrefs

- `0x1800044ce`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004450  push    rbx
0x180004452  push    rbp
0x180004453  push    rsi
0x180004454  push    rdi
0x180004455  push    r14
0x180004457  sub     rsp, 20h
0x18000445b  lea     rdi, [rcx+28h]
0x18000445f  mov     rsi, rcx
0x180004462  lea     r14, [rdi+50h]
0x180004466  jmp     short loc_18000449D
0x180004468  mov     rbp, [rdi]
0x18000446b  jmp     short loc_180004491
0x18000446d  mov     rbx, rbp
0x180004470  mov     rbp, [rbp+8]
0x180004474  lea     rcx, [rbx+10h]; this
0x180004478  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000447d  call    cs:__imp_GetProcessHeap
0x180004483  mov     r8, rbx; lpMem
0x180004486  xor     edx, edx; dwFlags
0x180004488  mov     rcx, rax; hHeap
0x18000448b  call    cs:__imp_HeapFree
0x180004491  test    rbp, rbp
0x180004494  jnz     short loc_18000446D
0x180004496  mov     [rdi], rbp
0x180004499  add     rdi, 8
0x18000449d  cmp     rdi, r14
0x1800044a0  jnz     short loc_180004468
0x1800044a2  lea     rcx, [rsi+10h]; this
0x1800044a6  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x1800044ab  mov     rcx, [rsi+8]; hObject
0x1800044af  test    rcx, rcx
0x1800044b2  jz      short loc_1800044BE
0x1800044b4  call    cs:__imp_CloseHandle
0x1800044ba  test    eax, eax
0x1800044bc  jz      short loc_1800044C9
0x1800044be  add     rsp, 20h
0x1800044c2  pop     r14
0x1800044c4  pop     rdi
0x1800044c5  pop     rsi
0x1800044c6  pop     rbp
0x1800044c7  pop     rbx
0x1800044c8  retn
0x1800044c9  mov     rcx, [rsp+48h]; this
0x1800044ce  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800044d5  mov     edx, 0A0Bh; void *
0x1800044da  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
