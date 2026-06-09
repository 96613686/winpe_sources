# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x18001133c`
- end: `0x18001139d`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x180011648`
- `0x180011a14`
- `0x180014bc0`
- `0x180014d30`
- `0x180018ded`

## callees

- `0x18001133c`
- `0x180016644`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x18001134e`
- `KERNEL32!CloseHandle` at `0x18001136b`
- `KERNEL32!CloseHandle` at `0x18001134e`
- `KERNEL32!CloseHandle` at `0x18001136b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  const char *v4; // r9
  __int64 v5; // r8
  const char *v6; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v3, v4);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v5, v6);
  }
}

```

## disassembly

```asm
0x18001133c  push    rbx
0x18001133e  sub     rsp, 20h
0x180011342  mov     rbx, rcx
0x180011345  mov     rcx, [rcx+8]; hObject
0x180011349  test    rcx, rcx
0x18001134c  jz      short loc_180011363
0x18001134e  call    cs:__imp_CloseHandle
0x180011355  nop     dword ptr [rax+rax+00h]
0x18001135a  mov     rcx, [rsp+28h]; this
0x18001135f  test    eax, eax
0x180011361  jz      short loc_180011392
0x180011363  mov     rcx, [rbx]; hObject
0x180011366  test    rcx, rcx
0x180011369  jz      short loc_180011380
0x18001136b  call    cs:__imp_CloseHandle
0x180011372  nop     dword ptr [rax+rax+00h]
0x180011377  mov     rcx, [rsp+28h]; this
0x18001137c  test    eax, eax
0x18001137e  jz      short loc_180011387
0x180011380  add     rsp, 20h
0x180011384  pop     rbx
0x180011385  retn
0x180011387  mov     edx, 0A0Bh; void *
0x18001138c  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180011392  mov     edx, 0A0Bh; void *
0x180011397  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
