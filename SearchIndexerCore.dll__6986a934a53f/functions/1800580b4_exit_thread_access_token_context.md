# exit_thread_access_token_context

- ea: `0x1800580b4`
- end: `0x180058110`
- name: `exit_thread_access_token_context`
- size: `92`
- prototype: `DWORD __fastcall(__int64)`
- caller_count: `12`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180057f68`
- `0x1800686c0`
- `0x180068790`
- `0x180068880`
- `0x1800689a0`
- `0x180068af0`
- `0x180068c20`
- `0x180068e60`
- `0x180068f60`
- `0x1800690b0`
- `0x1800a7070`
- `0x1800a7180`

## callees

- `0x1800580b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058104`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800580f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180058104`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800580e6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800580e6`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800580c2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800580c2`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800580d8`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800580d8`

## pseudocode

```c
DWORD __fastcall exit_thread_access_token_context(__int64 a1)
{
  if ( *(_BYTE *)a1 )
  {
    if ( !RevertToSelf() )
      __fastfail(GetLastError());
    return 0;
  }
  if ( !ImpersonateLoggedOnUser(*(HANDLE *)(a1 + 8)) )
    __fastfail(GetLastError());
  if ( CloseHandle(*(HANDLE *)(a1 + 8)) )
    return 0;
  return GetLastError();
}

```

## disassembly

```asm
0x1800580b4  push    rbx
0x1800580b6  sub     rsp, 20h
0x1800580ba  cmp     byte ptr [rcx], 0
0x1800580bd  mov     rbx, rcx
0x1800580c0  jz      short loc_1800580D4
0x1800580c2  call    cs:__imp_RevertToSelf
0x1800580c8  test    eax, eax
0x1800580ca  jz      short loc_1800580F8
0x1800580cc  xor     eax, eax
0x1800580ce  add     rsp, 20h
0x1800580d2  pop     rbx
0x1800580d3  retn
0x1800580d4  mov     rcx, [rcx+8]; hToken
0x1800580d8  call    cs:__imp_ImpersonateLoggedOnUser
0x1800580de  test    eax, eax
0x1800580e0  jz      short loc_180058104
0x1800580e2  mov     rcx, [rbx+8]; hObject
0x1800580e6  call    cs:__imp_CloseHandle
0x1800580ec  test    eax, eax
0x1800580ee  jnz     short loc_1800580CC
0x1800580f0  call    cs:__imp_GetLastError
0x1800580f6  jmp     short loc_1800580CE
0x1800580f8  call    cs:__imp_GetLastError
0x1800580fe  mov     ecx, eax
0x180058100  int     29h; Win8: RtlFailFast(ecx)
0x180058102  jmp     short loc_1800580CC
0x180058104  call    cs:__imp_GetLastError
0x18005810a  mov     ecx, eax
0x18005810c  int     29h; Win8: RtlFailFast(ecx)
0x18005810e  jmp     short loc_1800580E2
```
