# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1800030e8`
- end: `0x180003149`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `97`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x180003354`
- `0x180003700`
- `0x1800064ec`
- `0x180006658`

## callees

- `0x1800030e8`
- `0x18000787c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x1800030fa`
- `KERNEL32!CloseHandle` at `0x180003112`
- `KERNEL32!CloseHandle` at `0x1800030fa`
- `KERNEL32!CloseHandle` at `0x180003112`

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
0x1800030e8  push    rbx
0x1800030ea  sub     rsp, 20h
0x1800030ee  mov     rbx, rcx
0x1800030f1  mov     rcx, [rcx+8]; hObject
0x1800030f5  test    rcx, rcx
0x1800030f8  jz      short loc_18000310A
0x1800030fa  call    cs:__imp_CloseHandle
0x180003101  nop     dword ptr [rax+rax+00h]
0x180003106  test    eax, eax
0x180003108  jz      short loc_180003139
0x18000310a  mov     rcx, [rbx]; hObject
0x18000310d  test    rcx, rcx
0x180003110  jz      short loc_180003122
0x180003112  call    cs:__imp_CloseHandle
0x180003119  nop     dword ptr [rax+rax+00h]
0x18000311e  test    eax, eax
0x180003120  jz      short loc_180003129
0x180003122  add     rsp, 20h
0x180003126  pop     rbx
0x180003127  retn
0x180003129  mov     rcx, [rsp+28h]; this
0x18000312e  mov     edx, 0A0Bh; void *
0x180003133  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003139  mov     rcx, [rsp+28h]; this
0x18000313e  mov     edx, 0A0Bh; void *
0x180003143  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
