# _anonymous_namespace_::SetFileIntegrityLevel

- ea: `0x180029ce8`
- end: `0x180029d98`
- name: `_anonymous_namespace_::SetFileIntegrityLevel`
- size: `176`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `2`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180029a80`
- `0x180029da0`

## callees

- `0x180020b50`
- `0x1800211f4`
- `0x180029ce8`

## import_xrefs

- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180029d00`
- `iertutil!__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z` at `0x180029d00`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029d7b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d73`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029d73`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029d55`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180029d55`

## pseudocode

```c
__int64 __fastcall anonymous_namespace_::SetFileIntegrityLevel(HANDLE Handle, char a2)
{
  unsigned int v3; // ebx
  const WCHAR *v4; // rcx
  enum _SE_OBJECT_TYPE v5; // edx
  bool *v6; // r9
  signed int LastError; // eax
  PSID Sid; // [rsp+30h] [rbp-18h] BYREF
  bool v10; // [rsp+58h] [rbp+10h] BYREF
  bool v11; // [rsp+60h] [rbp+18h] BYREF
  bool v12; // [rsp+68h] [rbp+20h] BYREF

  if ( a2 )
  {
    return (unsigned int)SetWindowsHandleAccess(Handle, 0x1240u, 0xE0010000);
  }
  else
  {
    v10 = 0;
    v12 = 0;
    v11 = 0;
    GetCurrentProcessIntegrityLevel(&v10, &v12, &v11);
    v4 = L"HI";
    Sid = 0;
    if ( !v10 )
      v4 = L"ME";
    if ( ConvertStringSidToSidW(v4, &Sid) )
    {
      v3 = SetHandleIntegrityLevel(Handle, v5, Sid, v6);
      LocalFree(Sid);
    }
    else
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        return (unsigned __int16)LastError | 0x80070000;
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180029ce8  push    rbx
0x180029cea  sub     rsp, 40h
0x180029cee  mov     rbx, rcx
0x180029cf1  test    dl, dl
0x180029cf3  jz      short loc_180029D0D
0x180029cf5  mov     edx, 1240h
0x180029cfa  mov     r8d, 0E0010000h
0x180029d00  call    cs:__imp_?SetWindowsHandleAccess@@YAJPEAXKK@Z; SetWindowsHandleAccess(void *,ulong,ulong)
0x180029d06  mov     ebx, eax
0x180029d08  jmp     loc_180029D90
0x180029d0d  lea     r8, [rsp+48h+arg_10]; bool *
0x180029d12  mov     [rsp+48h+arg_8], 0
0x180029d17  lea     rdx, [rsp+48h+arg_18]; bool *
0x180029d1c  mov     [rsp+48h+arg_18], 0
0x180029d21  lea     rcx, [rsp+48h+arg_8]; bool *
0x180029d26  mov     [rsp+48h+arg_10], 0
0x180029d2b  call    ?GetCurrentProcessIntegrityLevel@@YAXPEA_N00@Z; GetCurrentProcessIntegrityLevel(bool *,bool *,bool *)
0x180029d30  cmp     [rsp+48h+arg_8], 0
0x180029d35  lea     rax, aMe; "ME"
0x180029d3c  lea     rcx, aHi; "HI"
0x180029d43  mov     [rsp+48h+Sid], 0
0x180029d4c  cmovz   rcx, rax; StringSid
0x180029d50  lea     rdx, [rsp+48h+Sid]; Sid
0x180029d55  call    cs:__imp_ConvertStringSidToSidW
0x180029d5b  test    eax, eax
0x180029d5d  jz      short loc_180029D7B
0x180029d5f  mov     r8, [rsp+48h+Sid]; void *
0x180029d64  mov     rcx, rbx; Handle
0x180029d67  call    ?SetHandleIntegrityLevel@@YAJPEAXW4_SE_OBJECT_TYPE@@0PEA_NK@Z; SetHandleIntegrityLevel(void *,_SE_OBJECT_TYPE,void *,bool *,ulong)
0x180029d6c  mov     rcx, [rsp+48h+Sid]; hMem
0x180029d71  mov     ebx, eax
0x180029d73  call    cs:__imp_LocalFree
0x180029d79  jmp     short loc_180029D90
0x180029d7b  call    cs:__imp_GetLastError
0x180029d81  mov     ebx, eax
0x180029d83  test    eax, eax
0x180029d85  jle     short loc_180029D90
0x180029d87  movzx   ebx, ax
0x180029d8a  or      ebx, 80070000h
0x180029d90  mov     eax, ebx
0x180029d92  add     rsp, 40h
0x180029d96  pop     rbx
0x180029d97  retn
```
