# DmRevertToSelf(void)

- ea: `0x180012bac`
- end: `0x180012c06`
- name: `?DmRevertToSelf@@YAJXZ`
- size: `90`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180005bfc`

## callees

- `0x180012bac`
- `0x180015a28`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012bc4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012bb4`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012bb4`

## string_xrefs

- `0x180012be8`: `onecoreuap\admin\dm\dmcmnutils\securityutils\securityutils.cpp`

## pseudocode

```c
__int64 DmRevertToSelf(void)
{
  unsigned int v0; // ebx
  signed int LastError; // eax
  int v3; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v0 = 0;
  if ( !RevertToSelf() )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError > 0 )
      v0 = (unsigned __int16)LastError | 0x80070000;
    if ( (v0 & 0x80000000) != 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x32E,
        (unsigned int)"onecoreuap\\admin\\dm\\dmcmnutils\\securityutils\\securityutils.cpp",
        (const char *)v0,
        v3);
  }
  return v0;
}

```

## disassembly

```asm
0x180012bac  push    rbx; int
0x180012bae  sub     rsp, 20h
0x180012bb2  xor     ebx, ebx
0x180012bb4  call    cs:__imp_RevertToSelf
0x180012bbb  nop     dword ptr [rax+rax+00h]
0x180012bc0  test    eax, eax
0x180012bc2  jnz     short loc_180012BFD
0x180012bc4  call    cs:__imp_GetLastError
0x180012bcb  nop     dword ptr [rax+rax+00h]
0x180012bd0  mov     ebx, eax
0x180012bd2  test    eax, eax
0x180012bd4  jle     short loc_180012BDF
0x180012bd6  movzx   ebx, ax
0x180012bd9  or      ebx, 80070000h
0x180012bdf  test    ebx, ebx
0x180012be1  jns     short loc_180012BFD
0x180012be3  mov     rcx, [rsp+28h]; this
0x180012be8  lea     r8, aOnecoreuapAdmi; "onecoreuap\\admin\\dm\\dmcmnutils\\secu"...
0x180012bef  mov     r9d, ebx; char *
0x180012bf2  mov     edx, 32Eh; void *
0x180012bf7  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180012bfd  mov     eax, ebx
0x180012bff  add     rsp, 20h
0x180012c03  pop     rbx
0x180012c04  retn
```
