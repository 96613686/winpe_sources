# CNgscbScopedPrivilege::ReleasePrivilege(void)

- ea: `0x18000f0e4`
- end: `0x18000f12a`
- name: `?ReleasePrivilege@CNgscbScopedPrivilege@@QEAAXXZ`
- size: `70`
- prototype: `void __fastcall(CNgscbScopedPrivilege *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x18000dde0`
- `0x180031318`
- `0x180040fac`

## callees

- `0x18000f0e4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f0f8`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18000f0f8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f110`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000f110`

## pseudocode

```c
void __fastcall CNgscbScopedPrivilege::ReleasePrivilege(HANDLE *this)
{
  if ( *((_BYTE *)this + 8) )
  {
    SetThreadToken(0, *this);
    *((_BYTE *)this + 8) = 0;
  }
  if ( *this )
  {
    CloseHandle(*this);
    *this = 0;
  }
}

```

## disassembly

```asm
0x18000f0e4  push    rbx
0x18000f0e6  sub     rsp, 20h
0x18000f0ea  cmp     byte ptr [rcx+8], 0
0x18000f0ee  mov     rbx, rcx
0x18000f0f1  jz      short loc_18000F108
0x18000f0f3  mov     rdx, [rcx]; Token
0x18000f0f6  xor     ecx, ecx; Thread
0x18000f0f8  call    cs:__imp_SetThreadToken
0x18000f0ff  nop     dword ptr [rax+rax+00h]
0x18000f104  mov     byte ptr [rbx+8], 0
0x18000f108  mov     rcx, [rbx]; hObject
0x18000f10b  test    rcx, rcx
0x18000f10e  jz      short loc_18000F123
0x18000f110  call    cs:__imp_CloseHandle
0x18000f117  nop     dword ptr [rax+rax+00h]
0x18000f11c  mov     qword ptr [rbx], 0
0x18000f123  add     rsp, 20h
0x18000f127  pop     rbx
0x18000f128  retn
```
