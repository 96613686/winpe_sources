# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x1800067f4`
- end: `0x18000689e`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `170`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180009fe8`
- `0x18000a118`

## callees

- `0x1800067f4`
- `0x18000c5d4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006852`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006852`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000680e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000683b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000680e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000683b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006846`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006819`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006846`

## string_xrefs

- `0x180006875`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18000688c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800067f4  mov     [rsp+arg_0], rbx
0x1800067f9  mov     [rsp+arg_8], rsi
0x1800067fe  push    rdi
0x1800067ff  sub     rsp, 20h
0x180006803  mov     rdi, [rcx]
0x180006806  mov     rbx, rcx
0x180006809  test    rdi, rdi
0x18000680c  jz      short loc_18000682B
0x18000680e  call    cs:__imp_GetLastError
0x180006814  mov     rcx, rdi; hObject
0x180006817  mov     esi, eax
0x180006819  call    cs:__imp_CloseHandle
0x18000681f  test    eax, eax
0x180006821  jz      short loc_180006887
0x180006823  mov     ecx, esi; dwErrCode
0x180006825  call    cs:__imp_SetLastError
0x18000682b  mov     qword ptr [rbx], 0
0x180006832  mov     rdi, [rbx+8]
0x180006836  test    rdi, rdi
0x180006839  jz      short loc_180006858
0x18000683b  call    cs:__imp_GetLastError
0x180006841  mov     rcx, rdi; hObject
0x180006844  mov     esi, eax
0x180006846  call    cs:__imp_CloseHandle
0x18000684c  test    eax, eax
0x18000684e  jz      short loc_180006870
0x180006850  mov     ecx, esi; dwErrCode
0x180006852  call    cs:__imp_SetLastError
0x180006858  mov     rsi, [rsp+28h+arg_8]
0x18000685d  mov     qword ptr [rbx+8], 0
0x180006865  mov     rbx, [rsp+28h+arg_0]
0x18000686a  add     rsp, 20h
0x18000686e  pop     rdi
0x18000686f  retn
0x180006870  mov     rcx, [rsp+28h]; this
0x180006875  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000687c  mov     edx, 0A0Bh; void *
0x180006881  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180006887  mov     rcx, [rsp+28h]; this
0x18000688c  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006893  mov     edx, 0A0Bh; void *
0x180006898  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
