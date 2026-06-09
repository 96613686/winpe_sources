# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x1800059e0`
- end: `0x180005a8a`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000879c`
- `0x1800088c0`

## callees

- `0x1800059e0`
- `0x18000a49c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a3e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a11`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005a3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a27`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800059fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005a27`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a05`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005a32`

## string_xrefs

- `0x180005a61`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005a78`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall wil::details_abi::SemaphoreValue::Destroy(wil::details_abi::SemaphoreValue *this)
{
  void *v1; // rdi
  DWORD LastError; // esi
  const char *v4; // r9
  void *v5; // rdi
  DWORD v6; // esi
  const char *v7; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    LastError = GetLastError();
    if ( !CloseHandle(v1) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v4);
    SetLastError(LastError);
  }
  *(_QWORD *)this = 0;
  v5 = (void *)*((_QWORD *)this + 1);
  if ( v5 )
  {
    v6 = GetLastError();
    if ( !CloseHandle(v5) )
      wil::details::in1diag3::_FailFast_GetLastError(
        retaddr,
        (void *)0xA0B,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        v7);
    SetLastError(v6);
  }
  *((_QWORD *)this + 1) = 0;
}

```

## disassembly

```asm
0x1800059e0  mov     [rsp+arg_0], rbx
0x1800059e5  mov     [rsp+arg_8], rsi
0x1800059ea  push    rdi
0x1800059eb  sub     rsp, 20h
0x1800059ef  mov     rdi, [rcx]
0x1800059f2  mov     rbx, rcx
0x1800059f5  test    rdi, rdi
0x1800059f8  jz      short loc_180005A17
0x1800059fa  call    cs:__imp_GetLastError
0x180005a00  mov     rcx, rdi; hObject
0x180005a03  mov     esi, eax
0x180005a05  call    cs:__imp_CloseHandle
0x180005a0b  test    eax, eax
0x180005a0d  jz      short loc_180005A73
0x180005a0f  mov     ecx, esi; dwErrCode
0x180005a11  call    cs:__imp_SetLastError
0x180005a17  mov     qword ptr [rbx], 0
0x180005a1e  mov     rdi, [rbx+8]
0x180005a22  test    rdi, rdi
0x180005a25  jz      short loc_180005A44
0x180005a27  call    cs:__imp_GetLastError
0x180005a2d  mov     rcx, rdi; hObject
0x180005a30  mov     esi, eax
0x180005a32  call    cs:__imp_CloseHandle
0x180005a38  test    eax, eax
0x180005a3a  jz      short loc_180005A5C
0x180005a3c  mov     ecx, esi; dwErrCode
0x180005a3e  call    cs:__imp_SetLastError
0x180005a44  mov     rsi, [rsp+28h+arg_8]
0x180005a49  mov     qword ptr [rbx+8], 0
0x180005a51  mov     rbx, [rsp+28h+arg_0]
0x180005a56  add     rsp, 20h
0x180005a5a  pop     rdi
0x180005a5b  retn
0x180005a5c  mov     rcx, [rsp+28h]; this
0x180005a61  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005a68  mov     edx, 0A0Bh; void *
0x180005a6d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005a73  mov     rcx, [rsp+28h]; this
0x180005a78  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005a7f  mov     edx, 0A0Bh; void *
0x180005a84  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
