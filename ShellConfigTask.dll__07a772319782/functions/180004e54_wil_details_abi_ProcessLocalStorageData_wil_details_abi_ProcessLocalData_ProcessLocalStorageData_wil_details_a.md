# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180004e54`
- end: `0x180004ee4`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180009fe8`

## callees

- `0x180004e54`
- `0x1800054cc`
- `0x18000559c`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e8f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180004e8f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e81`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180004e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eb8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004eb8`

## string_xrefs

- `0x180004ed2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004e54  push    rbx
0x180004e56  push    rbp
0x180004e57  push    rsi
0x180004e58  push    rdi
0x180004e59  push    r14
0x180004e5b  sub     rsp, 20h
0x180004e5f  lea     rdi, [rcx+28h]
0x180004e63  mov     rsi, rcx
0x180004e66  lea     r14, [rdi+50h]
0x180004e6a  jmp     short loc_180004EA1
0x180004e6c  mov     rbp, [rdi]
0x180004e6f  jmp     short loc_180004E95
0x180004e71  mov     rbx, rbp
0x180004e74  mov     rbp, [rbp+8]
0x180004e78  lea     rcx, [rbx+10h]; this
0x180004e7c  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x180004e81  call    cs:__imp_GetProcessHeap
0x180004e87  mov     r8, rbx; lpMem
0x180004e8a  xor     edx, edx; dwFlags
0x180004e8c  mov     rcx, rax; hHeap
0x180004e8f  call    cs:__imp_HeapFree
0x180004e95  test    rbp, rbp
0x180004e98  jnz     short loc_180004E71
0x180004e9a  mov     [rdi], rbp
0x180004e9d  add     rdi, 8
0x180004ea1  cmp     rdi, r14
0x180004ea4  jnz     short loc_180004E6C
0x180004ea6  lea     rcx, [rsi+10h]; this
0x180004eaa  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x180004eaf  mov     rcx, [rsi+8]; hObject
0x180004eb3  test    rcx, rcx
0x180004eb6  jz      short loc_180004EC2
0x180004eb8  call    cs:__imp_CloseHandle
0x180004ebe  test    eax, eax
0x180004ec0  jz      short loc_180004ECD
0x180004ec2  add     rsp, 20h
0x180004ec6  pop     r14
0x180004ec8  pop     rdi
0x180004ec9  pop     rsi
0x180004eca  pop     rbp
0x180004ecb  pop     rbx
0x180004ecc  retn
0x180004ecd  mov     rcx, [rsp+48h]; this
0x180004ed2  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180004ed9  mov     edx, 0A0Bh; void *
0x180004ede  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
