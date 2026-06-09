# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x140003330`
- end: `0x1400033cc`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x14000461c`
- `0x140007910`

## callees

- `0x140003330`
- `0x1400055ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000334a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000334a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003377`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003361`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000338e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140003361`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000338e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003382`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003355`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140003382`

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
0x140003330  mov     [rsp+arg_0], rbx
0x140003335  mov     [rsp+arg_8], rsi
0x14000333a  push    rdi
0x14000333b  sub     rsp, 20h
0x14000333f  mov     rdi, [rcx]
0x140003342  mov     rbx, rcx
0x140003345  test    rdi, rdi
0x140003348  jz      short loc_140003367
0x14000334a  call    cs:__imp_GetLastError
0x140003350  mov     rcx, rdi; hObject
0x140003353  mov     esi, eax
0x140003355  call    cs:__imp_CloseHandle
0x14000335b  test    eax, eax
0x14000335d  jz      short loc_1400033BC
0x14000335f  mov     ecx, esi; dwErrCode
0x140003361  call    cs:__imp_SetLastError
0x140003367  mov     qword ptr [rbx], 0
0x14000336e  mov     rdi, [rbx+8]
0x140003372  test    rdi, rdi
0x140003375  jz      short loc_140003394
0x140003377  call    cs:__imp_GetLastError
0x14000337d  mov     rcx, rdi; hObject
0x140003380  mov     esi, eax
0x140003382  call    cs:__imp_CloseHandle
0x140003388  test    eax, eax
0x14000338a  jz      short loc_1400033AC
0x14000338c  mov     ecx, esi; dwErrCode
0x14000338e  call    cs:__imp_SetLastError
0x140003394  mov     rsi, [rsp+28h+arg_8]
0x140003399  mov     qword ptr [rbx+8], 0
0x1400033a1  mov     rbx, [rsp+28h+arg_0]
0x1400033a6  add     rsp, 20h
0x1400033aa  pop     rdi
0x1400033ab  retn
0x1400033ac  mov     rcx, [rsp+28h]; this
0x1400033b1  mov     edx, 0A0Bh; void *
0x1400033b6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1400033bc  mov     rcx, [rsp+28h]; this
0x1400033c1  mov     edx, 0A0Bh; void *
0x1400033c6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
