# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x180004830`
- end: `0x1800048c0`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `144`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000651c`

## callees

- `0x180004830`
- `0x18000494c`
- `0x180004a1c`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000485d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000486b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000486b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004894`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180004894`

## string_xrefs

- `0x1800048ae`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180004830  push    rbx
0x180004832  push    rbp
0x180004833  push    rsi
0x180004834  push    rdi
0x180004835  push    r14
0x180004837  sub     rsp, 20h
0x18000483b  lea     rdi, [rcx+28h]
0x18000483f  mov     rsi, rcx
0x180004842  lea     r14, [rdi+50h]
0x180004846  jmp     short loc_18000487D
0x180004848  mov     rbp, [rdi]
0x18000484b  jmp     short loc_180004871
0x18000484d  mov     rbx, rbp
0x180004850  mov     rbp, [rbp+8]
0x180004854  lea     rcx, [rbx+10h]; this
0x180004858  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x18000485d  call    cs:__imp_GetProcessHeap
0x180004863  mov     r8, rbx; lpMem
0x180004866  xor     edx, edx; dwFlags
0x180004868  mov     rcx, rax; hHeap
0x18000486b  call    cs:__imp_HeapFree
0x180004871  test    rbp, rbp
0x180004874  jnz     short loc_18000484D
0x180004876  mov     [rdi], rbp
0x180004879  add     rdi, 8
0x18000487d  cmp     rdi, r14
0x180004880  jnz     short loc_180004848
0x180004882  lea     rcx, [rsi+10h]; this
0x180004886  call    ??1SemaphoreValue@details_abi@wil@@QEAA@XZ; wil::details_abi::SemaphoreValue::~SemaphoreValue(void)
0x18000488b  mov     rcx, [rsi+8]; hObject
0x18000488f  test    rcx, rcx
0x180004892  jz      short loc_18000489E
0x180004894  call    cs:__imp_CloseHandle
0x18000489a  test    eax, eax
0x18000489c  jz      short loc_1800048A9
0x18000489e  add     rsp, 20h
0x1800048a2  pop     r14
0x1800048a4  pop     rdi
0x1800048a5  pop     rsi
0x1800048a6  pop     rbp
0x1800048a7  pop     rbx
0x1800048a8  retn
0x1800048a9  mov     rcx, [rsp+48h]; this
0x1800048ae  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800048b5  mov     edx, 0A0Bh; void *
0x1800048ba  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
