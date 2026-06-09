# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x18000ec44`
- end: `0x18000ecd4`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800108dc`

## callees

- `0x18000ec44`
- `0x18000ed60`
- `0x18000ee30`
- `0x180011afc`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec7f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000ec7f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec71`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000ec71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eca8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000eca8`

## string_xrefs

- `0x18000ecc2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000ec44  push    rbx
0x18000ec46  push    rbp
0x18000ec47  push    rsi
0x18000ec48  push    rdi
0x18000ec49  push    r14
0x18000ec4b  sub     rsp, 20h
0x18000ec4f  lea     rdi, [rcx+28h]
0x18000ec53  mov     rsi, rcx
0x18000ec56  lea     r14, [rdi+50h]
0x18000ec5a  jmp     short loc_18000EC91
0x18000ec5c  mov     rbp, [rdi]
0x18000ec5f  jmp     short loc_18000EC85
0x18000ec61  mov     rbx, rbp
0x18000ec64  mov     rbp, [rbp+8]
0x18000ec68  lea     rcx, [rbx+10h]; this
0x18000ec6c  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000ec71  call    cs:__imp_GetProcessHeap
0x18000ec77  mov     r8, rbx; lpMem
0x18000ec7a  xor     edx, edx; dwFlags
0x18000ec7c  mov     rcx, rax; hHeap
0x18000ec7f  call    cs:__imp_HeapFree
0x18000ec85  test    rbp, rbp
0x18000ec88  jnz     short loc_18000EC61
0x18000ec8a  mov     [rdi], rbp
0x18000ec8d  add     rdi, 8
0x18000ec91  cmp     rdi, r14
0x18000ec94  jnz     short loc_18000EC5C
0x18000ec96  lea     rcx, [rsi+10h]; this
0x18000ec9a  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000ec9f  mov     rcx, [rsi+8]; hObject
0x18000eca3  test    rcx, rcx
0x18000eca6  jz      short loc_18000ECB2
0x18000eca8  call    cs:__imp_CloseHandle
0x18000ecae  test    eax, eax
0x18000ecb0  jz      short loc_18000ECBD
0x18000ecb2  add     rsp, 20h
0x18000ecb6  pop     r14
0x18000ecb8  pop     rdi
0x18000ecb9  pop     rsi
0x18000ecba  pop     rbp
0x18000ecbb  pop     rbx
0x18000ecbc  retn
0x18000ecbd  mov     rcx, [rsp+48h]; this
0x18000ecc2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000ecc9  mov     edx, 0A0Bh; void *
0x18000ecce  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
