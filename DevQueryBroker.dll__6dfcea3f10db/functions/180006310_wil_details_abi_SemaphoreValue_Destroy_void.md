# wil::details_abi::SemaphoreValue::Destroy(void)

- ea: `0x180006310`
- end: `0x1800063ac`
- name: `?Destroy@SemaphoreValue@details_abi@wil@@QEAAXXZ`
- size: `156`
- prototype: `void __fastcall(wil::details_abi::SemaphoreValue *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180008a1c`
- `0x180008b30`

## callees

- `0x180006310`
- `0x180009cac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000636e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006341`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000636e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000632a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006357`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000632a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006357`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006362`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006335`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006362`

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
0x180006310  mov     [rsp+arg_0], rbx
0x180006315  mov     [rsp+arg_8], rsi
0x18000631a  push    rdi
0x18000631b  sub     rsp, 20h
0x18000631f  mov     rdi, [rcx]
0x180006322  mov     rbx, rcx
0x180006325  test    rdi, rdi
0x180006328  jz      short loc_180006347
0x18000632a  call    cs:__imp_GetLastError
0x180006330  mov     rcx, rdi; hObject
0x180006333  mov     esi, eax
0x180006335  call    cs:__imp_CloseHandle
0x18000633b  test    eax, eax
0x18000633d  jz      short loc_18000639C
0x18000633f  mov     ecx, esi; dwErrCode
0x180006341  call    cs:__imp_SetLastError
0x180006347  mov     qword ptr [rbx], 0
0x18000634e  mov     rdi, [rbx+8]
0x180006352  test    rdi, rdi
0x180006355  jz      short loc_180006374
0x180006357  call    cs:__imp_GetLastError
0x18000635d  mov     rcx, rdi; hObject
0x180006360  mov     esi, eax
0x180006362  call    cs:__imp_CloseHandle
0x180006368  test    eax, eax
0x18000636a  jz      short loc_18000638C
0x18000636c  mov     ecx, esi; dwErrCode
0x18000636e  call    cs:__imp_SetLastError
0x180006374  mov     rsi, [rsp+28h+arg_8]
0x180006379  mov     qword ptr [rbx+8], 0
0x180006381  mov     rbx, [rsp+28h+arg_0]
0x180006386  add     rsp, 20h
0x18000638a  pop     rdi
0x18000638b  retn
0x18000638c  mov     rcx, [rsp+28h]; this
0x180006391  mov     edx, 0A0Bh; void *
0x180006396  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000639c  mov     rcx, [rsp+28h]; this
0x1800063a1  mov     edx, 0A0Bh; void *
0x1800063a6  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
