# wil::details::RevertImpersonateToken(void *)

- ea: `0x1800191b0`
- end: `0x1800191e2`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180011c58`
- `0x18001aa8c`

## callees

- `0x18000f034`
- `0x1800191b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800191be`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x1800191be`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800191d6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800191d6`

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
0x1800191b0  push    rbx
0x1800191b2  sub     rsp, 20h
0x1800191b6  mov     rbx, rcx
0x1800191b9  mov     rdx, rcx; Token
0x1800191bc  xor     ecx, ecx; Thread
0x1800191be  call    cs:__imp_SetThreadToken
0x1800191c4  test    eax, eax
0x1800191c6  jnz     short loc_1800191CE
0x1800191c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800191ce  test    rbx, rbx
0x1800191d1  jz      short loc_1800191DC
0x1800191d3  mov     rcx, rbx; hObject
0x1800191d6  call    cs:__imp_CloseHandle
0x1800191dc  add     rsp, 20h
0x1800191e0  pop     rbx
0x1800191e1  retn
```
