# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x1800076a0`
- end: `0x18000774a`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000a388`
- `0x18000a4b8`

## callees

- `0x1800076a0`
- `0x18000c268`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800076e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076fe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076d1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800076fe`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076c5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076f2`

## string_xrefs

- `0x180007721`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180007738`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800076a0  mov     [rsp+arg_0], rbx
0x1800076a5  mov     [rsp+arg_8], rsi
0x1800076aa  push    rdi
0x1800076ab  sub     rsp, 20h
0x1800076af  mov     rdi, [rcx]
0x1800076b2  mov     rbx, rcx
0x1800076b5  test    rdi, rdi
0x1800076b8  jz      short loc_1800076D7
0x1800076ba  call    cs:__imp_GetLastError
0x1800076c0  mov     rcx, rdi; hObject
0x1800076c3  mov     esi, eax
0x1800076c5  call    cs:__imp_CloseHandle
0x1800076cb  test    eax, eax
0x1800076cd  jz      short loc_180007733
0x1800076cf  mov     ecx, esi; dwErrCode
0x1800076d1  call    cs:__imp_SetLastError
0x1800076d7  mov     qword ptr [rbx], 0
0x1800076de  mov     rdi, [rbx+8]
0x1800076e2  test    rdi, rdi
0x1800076e5  jz      short loc_180007704
0x1800076e7  call    cs:__imp_GetLastError
0x1800076ed  mov     rcx, rdi; hObject
0x1800076f0  mov     esi, eax
0x1800076f2  call    cs:__imp_CloseHandle
0x1800076f8  test    eax, eax
0x1800076fa  jz      short loc_18000771C
0x1800076fc  mov     ecx, esi; dwErrCode
0x1800076fe  call    cs:__imp_SetLastError
0x180007704  mov     rsi, [rsp+28h+arg_8]
0x180007709  mov     qword ptr [rbx+8], 0
0x180007711  mov     rbx, [rsp+28h+arg_0]
0x180007716  add     rsp, 20h
0x18000771a  pop     rdi
0x18000771b  retn
0x18000771c  mov     rcx, [rsp+28h]; this
0x180007721  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180007728  mov     edx, 0A0Bh; void *
0x18000772d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180007733  mov     rcx, [rsp+28h]; this
0x180007738  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000773f  mov     edx, 0A0Bh; void *
0x180007744  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
