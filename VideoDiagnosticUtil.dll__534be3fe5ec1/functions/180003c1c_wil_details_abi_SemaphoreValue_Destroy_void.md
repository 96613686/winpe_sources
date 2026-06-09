# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x180003c1c`
- end: `0x180003cdd`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `193`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800064ec`
- `0x180006658`

## callees

- `0x180003c1c`
- `0x18000787c`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x180003c47`
- `KERNEL32!CloseHandle` at `0x180003c86`
- `KERNEL32!CloseHandle` at `0x180003c47`
- `KERNEL32!CloseHandle` at `0x180003c86`
- `KERNEL32!GetLastError` at `0x180003c36`
- `KERNEL32!GetLastError` at `0x180003c75`
- `KERNEL32!GetLastError` at `0x180003c36`
- `KERNEL32!GetLastError` at `0x180003c75`
- `KERNEL32!SetLastError` at `0x180003c59`
- `KERNEL32!SetLastError` at `0x180003c98`
- `KERNEL32!SetLastError` at `0x180003c59`
- `KERNEL32!SetLastError` at `0x180003c98`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  __int64 v4; // r8
  const char *v5; // r9
  void *v6; // rdi
  DWORD v7; // esi
  __int64 v8; // r8
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v4, v5);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v6 = (void *)*((_QWORD *)this + 1);
  if ( v6 )
  {
    v7 = GetLastError();
    if ( !CloseHandle(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v8, v9);
    SetLastError(v7);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x180003c1c  mov     [rsp+arg_0], rbx
0x180003c21  mov     [rsp+arg_8], rsi
0x180003c26  push    rdi
0x180003c27  sub     rsp, 20h
0x180003c2b  mov     rdi, [rcx]
0x180003c2e  mov     rbx, rcx
0x180003c31  test    rdi, rdi
0x180003c34  jz      short loc_180003C65
0x180003c36  call    cs:__imp_GetLastError
0x180003c3d  nop     dword ptr [rax+rax+00h]
0x180003c42  mov     rcx, rdi; hObject
0x180003c45  mov     esi, eax
0x180003c47  call    cs:__imp_CloseHandle
0x180003c4e  nop     dword ptr [rax+rax+00h]
0x180003c53  test    eax, eax
0x180003c55  jz      short loc_180003CCD
0x180003c57  mov     ecx, esi; dwErrCode
0x180003c59  call    cs:__imp_SetLastError
0x180003c60  nop     dword ptr [rax+rax+00h]
0x180003c65  mov     qword ptr [rbx], 0
0x180003c6c  mov     rdi, [rbx+8]
0x180003c70  test    rdi, rdi
0x180003c73  jz      short loc_180003CA4
0x180003c75  call    cs:__imp_GetLastError
0x180003c7c  nop     dword ptr [rax+rax+00h]
0x180003c81  mov     rcx, rdi; hObject
0x180003c84  mov     esi, eax
0x180003c86  call    cs:__imp_CloseHandle
0x180003c8d  nop     dword ptr [rax+rax+00h]
0x180003c92  test    eax, eax
0x180003c94  jz      short loc_180003CBD
0x180003c96  mov     ecx, esi; dwErrCode
0x180003c98  call    cs:__imp_SetLastError
0x180003c9f  nop     dword ptr [rax+rax+00h]
0x180003ca4  mov     rsi, [rsp+28h+arg_8]
0x180003ca9  mov     qword ptr [rbx+8], 0
0x180003cb1  mov     rbx, [rsp+28h+arg_0]
0x180003cb6  add     rsp, 20h
0x180003cba  pop     rdi
0x180003cbb  retn
0x180003cbd  mov     rcx, [rsp+28h]; this
0x180003cc2  mov     edx, 0A0Bh; void *
0x180003cc7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003ccd  mov     rcx, [rsp+28h]; this
0x180003cd2  mov     edx, 0A0Bh; void *
0x180003cd7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
