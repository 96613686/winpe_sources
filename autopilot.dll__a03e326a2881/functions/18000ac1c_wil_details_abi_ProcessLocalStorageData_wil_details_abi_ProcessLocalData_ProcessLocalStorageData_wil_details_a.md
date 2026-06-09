# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x18000ac1c`
- end: `0x18000acac`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000fda8`

## callees

- `0x18000ac1c`
- `0x18000b2a4`
- `0x18000b374`
- `0x180012114`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac49`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ac49`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac57`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ac57`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac80`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ac80`

## string_xrefs

- `0x18000ac9a`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18000ac1c  push    rbx
0x18000ac1e  push    rbp
0x18000ac1f  push    rsi
0x18000ac20  push    rdi
0x18000ac21  push    r14
0x18000ac23  sub     rsp, 20h
0x18000ac27  lea     rdi, [rcx+28h]
0x18000ac2b  mov     rsi, rcx
0x18000ac2e  lea     r14, [rdi+50h]
0x18000ac32  jmp     short loc_18000AC69
0x18000ac34  mov     rbp, [rdi]
0x18000ac37  jmp     short loc_18000AC5D
0x18000ac39  mov     rbx, rbp
0x18000ac3c  mov     rbp, [rbp+8]
0x18000ac40  lea     rcx, [rbx+10h]; this
0x18000ac44  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000ac49  call    cs:__imp_GetProcessHeap
0x18000ac4f  mov     r8, rbx; lpMem
0x18000ac52  xor     edx, edx; dwFlags
0x18000ac54  mov     rcx, rax; hHeap
0x18000ac57  call    cs:__imp_HeapFree
0x18000ac5d  test    rbp, rbp
0x18000ac60  jnz     short loc_18000AC39
0x18000ac62  mov     [rdi], rbp
0x18000ac65  add     rdi, 8
0x18000ac69  cmp     rdi, r14
0x18000ac6c  jnz     short loc_18000AC34
0x18000ac6e  lea     rcx, [rsi+10h]; this
0x18000ac72  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ac77  mov     rcx, [rsi+8]; hObject
0x18000ac7b  test    rcx, rcx
0x18000ac7e  jz      short loc_18000AC8A
0x18000ac80  call    cs:__imp_CloseHandle
0x18000ac86  test    eax, eax
0x18000ac88  jz      short loc_18000AC95
0x18000ac8a  add     rsp, 20h
0x18000ac8e  pop     r14
0x18000ac90  pop     rdi
0x18000ac91  pop     rsi
0x18000ac92  pop     rbp
0x18000ac93  pop     rbx
0x18000ac94  retn
0x18000ac95  mov     rcx, [rsp+48h]; this
0x18000ac9a  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000aca1  mov     edx, 0A0Bh; void *
0x18000aca6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
