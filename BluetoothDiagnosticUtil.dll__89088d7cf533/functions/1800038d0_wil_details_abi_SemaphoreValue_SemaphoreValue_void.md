# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800038d0`
- end: `0x180003931`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800063e0`
- `0x180006d54`

## callees

- `0x1800038d0`
- `0x180008068`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800038e2`
- `KERNEL32!CloseHandle` at `0x1800038fa`
- `KERNEL32!CloseHandle` at `0x1800038e2`
- `KERNEL32!CloseHandle` at `0x1800038fa`

## pseudocode

```c
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
0x1800038d0  push    rbx
0x1800038d2  sub     rsp, 20h
0x1800038d6  mov     rbx, rcx
0x1800038d9  mov     rcx, [rcx+8]; hObject
0x1800038dd  test    rcx, rcx
0x1800038e0  jz      short loc_1800038F2
0x1800038e2  call    cs:__imp_CloseHandle
0x1800038e9  nop     dword ptr [rax+rax+00h]
0x1800038ee  test    eax, eax
0x1800038f0  jz      short loc_180003921
0x1800038f2  mov     rcx, [rbx]; hObject
0x1800038f5  test    rcx, rcx
0x1800038f8  jz      short loc_18000390A
0x1800038fa  call    cs:__imp_CloseHandle
0x180003901  nop     dword ptr [rax+rax+00h]
0x180003906  test    eax, eax
0x180003908  jz      short loc_180003911
0x18000390a  add     rsp, 20h
0x18000390e  pop     rbx
0x18000390f  retn
0x180003911  mov     rcx, [rsp+28h]; this
0x180003916  mov     edx, 0A0Bh; void *
0x18000391b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003921  mov     rcx, [rsp+28h]; this
0x180003926  mov     edx, 0A0Bh; void *
0x18000392b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
