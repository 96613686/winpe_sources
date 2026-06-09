# wil::details::RevertImpersonateToken(void *)

- ea: `0x180017694`
- end: `0x1800176c6`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800157a4`
- `0x180017c84`

## callees

- `0x18000ad74`
- `0x180017694`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800176a2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800176a2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800176ba`

## pseudocode

```c
void __fastcall wil::details::RevertImpersonateToken(HANDLE hObject, void *a2)
{
  wil::details::in1diag3 *v3; // rcx

  if ( !SetThreadToken(0, hObject) )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v3);
  if ( hObject )
    CloseHandle(hObject);
}

```

## disassembly

```asm
0x180017694  push    rbx
0x180017696  sub     rsp, 20h
0x18001769a  mov     rbx, rcx
0x18001769d  mov     rdx, rcx; Token
0x1800176a0  xor     ecx, ecx; Thread
0x1800176a2  call    cs:__imp_SetThreadToken
0x1800176a8  test    eax, eax
0x1800176aa  jnz     short loc_1800176B2
0x1800176ac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800176b2  test    rbx, rbx
0x1800176b5  jz      short loc_1800176C0
0x1800176b7  mov     rcx, rbx; hObject
0x1800176ba  call    cs:__imp_CloseHandle
0x1800176c0  add     rsp, 20h
0x1800176c4  pop     rbx
0x1800176c5  retn
```
