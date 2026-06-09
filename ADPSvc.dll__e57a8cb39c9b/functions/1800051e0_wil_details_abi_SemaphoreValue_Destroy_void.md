# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x1800051e0`
- end: `0x18000528a`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000651c`
- `0x18000a898`

## callees

- `0x1800051e0`
- `0x18000771c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000523e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005211`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000523e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005227`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800051fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005227`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005232`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005205`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180005232`

## string_xrefs

- `0x180005261`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180005278`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800051e0  mov     [rsp+arg_0], rbx
0x1800051e5  mov     [rsp+arg_8], rsi
0x1800051ea  push    rdi
0x1800051eb  sub     rsp, 20h
0x1800051ef  mov     rdi, [rcx]
0x1800051f2  mov     rbx, rcx
0x1800051f5  test    rdi, rdi
0x1800051f8  jz      short loc_180005217
0x1800051fa  call    cs:__imp_GetLastError
0x180005200  mov     rcx, rdi; hObject
0x180005203  mov     esi, eax
0x180005205  call    cs:__imp_CloseHandle
0x18000520b  test    eax, eax
0x18000520d  jz      short loc_180005273
0x18000520f  mov     ecx, esi; dwErrCode
0x180005211  call    cs:__imp_SetLastError
0x180005217  mov     qword ptr [rbx], 0
0x18000521e  mov     rdi, [rbx+8]
0x180005222  test    rdi, rdi
0x180005225  jz      short loc_180005244
0x180005227  call    cs:__imp_GetLastError
0x18000522d  mov     rcx, rdi; hObject
0x180005230  mov     esi, eax
0x180005232  call    cs:__imp_CloseHandle
0x180005238  test    eax, eax
0x18000523a  jz      short loc_18000525C
0x18000523c  mov     ecx, esi; dwErrCode
0x18000523e  call    cs:__imp_SetLastError
0x180005244  mov     rsi, [rsp+28h+arg_8]
0x180005249  mov     qword ptr [rbx+8], 0
0x180005251  mov     rbx, [rsp+28h+arg_0]
0x180005256  add     rsp, 20h
0x18000525a  pop     rdi
0x18000525b  retn
0x18000525c  mov     rcx, [rsp+28h]; this
0x180005261  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005268  mov     edx, 0A0Bh; void *
0x18000526d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180005273  mov     rcx, [rsp+28h]; this
0x180005278  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000527f  mov     edx, 0A0Bh; void *
0x180005284  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
