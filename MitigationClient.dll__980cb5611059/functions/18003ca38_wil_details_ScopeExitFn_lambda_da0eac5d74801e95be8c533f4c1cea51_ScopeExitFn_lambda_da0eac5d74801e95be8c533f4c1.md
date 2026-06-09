# wil::details::ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___::_ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___

- ea: `0x18003ca38`
- end: `0x18003ca74`
- name: `wil::details::ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___::_ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___`
- size: `60`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x1800591fb`

## callees

- `0x18003ca38`
- `0x18003d304`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ca5a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ca50`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003ca50`

## pseudocode

```c
void __fastcall wil::details::ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___::_ScopeExitFn__lambda_da0eac5d74801e95be8c533f4c1cea51___(
        _BYTE *a1)
{
  void *v1; // rdx
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a1[8] )
  {
    a1[8] = 0;
    if ( !DeleteFileW(*(LPCWSTR *)(*(_QWORD *)a1 + 128LL)) && GetLastError() != 2 )
      wil::details::in1diag3::_Log_GetLastError(retaddr, v1, v2, v3);
  }
}

```

## disassembly

```asm
0x18003ca38  sub     rsp, 28h
0x18003ca3c  cmp     byte ptr [rcx+8], 0
0x18003ca40  jz      short loc_18003CA6F
0x18003ca42  mov     byte ptr [rcx+8], 0
0x18003ca46  mov     rcx, [rcx]
0x18003ca49  mov     rcx, [rcx+80h]; lpFileName
0x18003ca50  call    cs:__imp_DeleteFileW
0x18003ca56  test    eax, eax
0x18003ca58  jnz     short loc_18003CA6F
0x18003ca5a  call    cs:__imp_GetLastError
0x18003ca60  cmp     eax, 2
0x18003ca63  jz      short loc_18003CA6F
0x18003ca65  mov     rcx, [rsp+28h]; this
0x18003ca6a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18003ca6f  add     rsp, 28h
0x18003ca73  retn
```
