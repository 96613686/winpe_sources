# wil::details::RevertImpersonateToken(void *)

- ea: `0x1400103e8`
- end: `0x14001041a`
- name: `?RevertImpersonateToken@details@wil@@YAXPEAX@Z`
- size: `50`
- prototype: `void __fastcall(HANDLE hObject, void *)`
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x14000934c`
- `0x140012944`

## callees

- `0x140006340`
- `0x1400103e8`

## import_xrefs

- `ADVAPI32!SetThreadToken` at `0x1400103f6`
- `ADVAPI32!SetThreadToken` at `0x1400103f6`
- `KERNEL32!CloseHandle` at `0x14001040e`
- `KERNEL32!CloseHandle` at `0x14001040e`

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
0x1400103e8  push    rbx
0x1400103ea  sub     rsp, 20h
0x1400103ee  mov     rbx, rcx
0x1400103f1  mov     rdx, rcx; Token
0x1400103f4  xor     ecx, ecx; Thread
0x1400103f6  call    cs:__imp_SetThreadToken
0x1400103fc  test    eax, eax
0x1400103fe  jnz     short loc_140010406
0x140010400  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140010406  test    rbx, rbx
0x140010409  jz      short loc_140010414
0x14001040b  mov     rcx, rbx; hObject
0x14001040e  call    cs:__imp_CloseHandle
0x140010414  add     rsp, 20h
0x140010418  pop     rbx
0x140010419  retn
```
