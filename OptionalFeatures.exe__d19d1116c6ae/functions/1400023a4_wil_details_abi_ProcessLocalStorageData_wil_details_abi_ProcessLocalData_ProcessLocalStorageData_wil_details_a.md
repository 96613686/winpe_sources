# wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(void)

- ea: `0x1400023a4`
- end: `0x14000246a`
- name: `??1?$ProcessLocalStorageData@UProcessLocalData@details_abi@wil@@@details_abi@wil@@QEAA@XZ`
- size: `198`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140003cec`

## callees

- `0x1400023a4`
- `0x140002470`
- `0x14000493c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1400023df`
- `KERNEL32!HeapFree` at `0x1400023df`
- `KERNEL32!CloseHandle` at `0x1400023ff`
- `KERNEL32!CloseHandle` at `0x140002412`
- `KERNEL32!CloseHandle` at `0x140002425`
- `KERNEL32!CloseHandle` at `0x1400023ff`
- `KERNEL32!CloseHandle` at `0x140002412`
- `KERNEL32!CloseHandle` at `0x140002425`
- `KERNEL32!GetProcessHeap` at `0x1400023d1`
- `KERNEL32!GetProcessHeap` at `0x1400023d1`

## pseudocode

```c
void __fastcall wil::details_abi::ProcessLocalStorageData<wil::details_abi::ProcessLocalData>::~ProcessLocalStorageData<wil::details_abi::ProcessLocalData>(
        _QWORD *a1)
{
  __int64 *v1; // rdi
  __int64 *v3; // r14
  __int64 v4; // rbp
  __int64 v5; // rbx
  HANDLE ProcessHeap; // rax
  void *v7; // rcx
  __int64 v8; // r8
  const char *v9; // r9
  void *v10; // rcx
  __int64 v11; // r8
  const char *v12; // r9
  void *v13; // rcx
  __int64 v14; // r8
  const char *v15; // r9
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
  v7 = (void *)a1[3];
  if ( v7 && !CloseHandle(v7) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
  v10 = (void *)a1[2];
  if ( v10 && !CloseHandle(v10) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v11, v12);
  v13 = (void *)a1[1];
  if ( v13 )
  {
    if ( !CloseHandle(v13) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v14, v15);
  }
}

```

## disassembly

```asm
0x1400023a4  push    rbx
0x1400023a6  push    rbp
0x1400023a7  push    rsi
0x1400023a8  push    rdi
0x1400023a9  push    r14
0x1400023ab  sub     rsp, 20h
0x1400023af  lea     rdi, [rcx+28h]
0x1400023b3  mov     rsi, rcx
0x1400023b6  lea     r14, [rdi+50h]
0x1400023ba  jmp     short loc_1400023F1
0x1400023bc  mov     rbp, [rdi]
0x1400023bf  jmp     short loc_1400023E5
0x1400023c1  mov     rbx, rbp
0x1400023c4  mov     rbp, [rbp+8]
0x1400023c8  lea     rcx, [rbx+10h]; this
0x1400023cc  call    ??1ThreadLocalData@details_abi@wil@@QEAA@XZ; wil::details_abi::ThreadLocalData::~ThreadLocalData(void)
0x1400023d1  call    cs:__imp_GetProcessHeap
0x1400023d7  mov     r8, rbx; lpMem
0x1400023da  xor     edx, edx; dwFlags
0x1400023dc  mov     rcx, rax; hHeap
0x1400023df  call    cs:__imp_HeapFree
0x1400023e5  test    rbp, rbp
0x1400023e8  jnz     short loc_1400023C1
0x1400023ea  mov     [rdi], rbp
0x1400023ed  add     rdi, 8
0x1400023f1  cmp     rdi, r14
0x1400023f4  jnz     short loc_1400023BC
0x1400023f6  mov     rcx, [rsi+18h]; hObject
0x1400023fa  test    rcx, rcx
0x1400023fd  jz      short loc_140002409
0x1400023ff  call    cs:__imp_CloseHandle
0x140002405  test    eax, eax
0x140002407  jz      short loc_14000244A
0x140002409  mov     rcx, [rsi+10h]; hObject
0x14000240d  test    rcx, rcx
0x140002410  jz      short loc_14000241C
0x140002412  call    cs:__imp_CloseHandle
0x140002418  test    eax, eax
0x14000241a  jz      short loc_14000245A
0x14000241c  mov     rcx, [rsi+8]; hObject
0x140002420  test    rcx, rcx
0x140002423  jz      short loc_14000242F
0x140002425  call    cs:__imp_CloseHandle
0x14000242b  test    eax, eax
0x14000242d  jz      short loc_14000243A
0x14000242f  add     rsp, 20h
0x140002433  pop     r14
0x140002435  pop     rdi
0x140002436  pop     rsi
0x140002437  pop     rbp
0x140002438  pop     rbx
0x140002439  retn
0x14000243a  mov     rcx, [rsp+48h]; this
0x14000243f  mov     edx, 0A0Bh; void *
0x140002444  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000244a  mov     rcx, [rsp+48h]; this
0x14000244f  mov     edx, 0A0Bh; void *
0x140002454  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x14000245a  mov     rcx, [rsp+48h]; this
0x14000245f  mov     edx, 0A0Bh; void *
0x140002464  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
