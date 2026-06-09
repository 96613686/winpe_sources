# wil::details_abi::SemaphoreValue::~SemaphoreValue(void)

- ea: `0x1400036f0`
- end: `0x14000376a`
- name: `??1SemaphoreValue@details_abi@wil@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400031f4`
- `0x140003c20`

## callees

- `0x1400036f0`
- `0x1400076ec`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140003702`
- `KERNEL32!CloseHandle` at `0x140003714`
- `KERNEL32!CloseHandle` at `0x140003702`
- `KERNEL32!CloseHandle` at `0x140003714`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::~SemaphoreValue(wil::details_abi::SemaphoreValue *this)
{
  void *v2; // rcx
  __int64 v3; // r8
  __int64 v4; // r8
  const char *v5; // [rsp+28h] [rbp-10h]
  wil::details::in1diag5 *retaddr; // [rsp+38h] [rbp+0h]

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 && !CloseHandle(v2) )
    wil::details::in1diag5::_FailFast_GetLastError(
      retaddr,
      (void *)0xA0B,
      v3,
      "wil::details::CloseHandle",
      "::CloseHandle(handle)",
      v5);
  if ( *(_QWORD *)this )
  {
    if ( !CloseHandle(*(HANDLE *)this) )
      wil::details::in1diag5::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        v4,
        "wil::details::CloseHandle",
        "::CloseHandle(handle)",
        v5);
  }
}

```

## disassembly

```asm
0x1400036f0  push    rbx
0x1400036f2  sub     rsp, 30h
0x1400036f6  mov     rbx, rcx
0x1400036f9  mov     rcx, [rcx+8]; hObject
0x1400036fd  test    rcx, rcx
0x140003700  jz      short loc_14000370C
0x140003702  call    cs:__imp_CloseHandle
0x140003708  test    eax, eax
0x14000370a  jz      short loc_140003747
0x14000370c  mov     rcx, [rbx]; hObject
0x14000370f  test    rcx, rcx
0x140003712  jz      short loc_14000371E
0x140003714  call    cs:__imp_CloseHandle
0x14000371a  test    eax, eax
0x14000371c  jz      short loc_140003724
0x14000371e  add     rsp, 30h
0x140003722  pop     rbx
0x140003723  retn
0x140003724  mov     rcx, [rsp+38h]; this
0x140003729  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140003730  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x140003737  mov     [rsp+38h+var_18], rax; char *
0x14000373c  mov     edx, 0A0Bh; void *
0x140003741  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
0x140003747  mov     rcx, [rsp+38h]; this
0x14000374c  lea     rax, aClosehandleHan; "::CloseHandle(handle)"
0x140003753  lea     r9, aWilDetailsClos; "wil::details::CloseHandle"
0x14000375a  mov     [rsp+38h+var_18], rax; char *
0x14000375f  mov     edx, 0A0Bh; void *
0x140003764  call    ?_FailFast_GetLastError@in1diag5@details@wil@@YAXPEAXIPEBD11@Z; wil::details::in1diag5::_FailFast_GetLastError(void *,uint,char const *,char const *,char const *)
```
