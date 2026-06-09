# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x1800031dc`
- end: `0x180003278`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180007368`
- `0x1800075e8`

## callees

- `0x180002e24`
- `0x1800031dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000320d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000323a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000320d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000323a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003223`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800031f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003223`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000322e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003201`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000322e`

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
0x1800031dc  mov     [rsp+arg_0], rbx
0x1800031e1  mov     [rsp+arg_8], rsi
0x1800031e6  push    rdi
0x1800031e7  sub     rsp, 20h
0x1800031eb  mov     rdi, [rcx]
0x1800031ee  mov     rbx, rcx
0x1800031f1  test    rdi, rdi
0x1800031f4  jz      short loc_180003213
0x1800031f6  call    cs:__imp_GetLastError
0x1800031fc  mov     rcx, rdi; hObject
0x1800031ff  mov     esi, eax
0x180003201  call    cs:__imp_CloseHandle
0x180003207  test    eax, eax
0x180003209  jz      short loc_180003268
0x18000320b  mov     ecx, esi; dwErrCode
0x18000320d  call    cs:__imp_SetLastError
0x180003213  mov     qword ptr [rbx], 0
0x18000321a  mov     rdi, [rbx+8]
0x18000321e  test    rdi, rdi
0x180003221  jz      short loc_180003240
0x180003223  call    cs:__imp_GetLastError
0x180003229  mov     rcx, rdi; hObject
0x18000322c  mov     esi, eax
0x18000322e  call    cs:__imp_CloseHandle
0x180003234  test    eax, eax
0x180003236  jz      short loc_180003258
0x180003238  mov     ecx, esi; dwErrCode
0x18000323a  call    cs:__imp_SetLastError
0x180003240  mov     rsi, [rsp+28h+arg_8]
0x180003245  mov     qword ptr [rbx+8], 0
0x18000324d  mov     rbx, [rsp+28h+arg_0]
0x180003252  add     rsp, 20h
0x180003256  pop     rdi
0x180003257  retn
0x180003258  mov     rcx, [rsp+28h]; this
0x18000325d  mov     edx, 0A0Bh; void *
0x180003262  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180003268  mov     rcx, [rsp+28h]; this
0x18000326d  mov     edx, 0A0Bh; void *
0x180003272  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
