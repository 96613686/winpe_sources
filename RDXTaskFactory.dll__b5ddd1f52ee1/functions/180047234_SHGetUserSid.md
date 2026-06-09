# SHGetUserSid

- ea: `0x180047234`
- end: `0x180047293`
- name: `SHGetUserSid`
- size: `95`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180023720`

## callees

- `0x180025cd8`
- `0x18004706c`
- `0x180047234`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047280`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047280`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004726c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004726c`

## pseudocode

```c
__int64 __fastcall SHGetUserSid(void *a1, LPWSTR *a2, DWORD a3)
{
  int Error; // ebx
  LPWSTR *v5; // rdx
  HLOCAL v6; // rdi
  HLOCAL hMem; // [rsp+38h] [rbp+10h] BYREF

  *a2 = 0;
  hMem = 0;
  Error = SHQueryToken<_TOKEN_USER>(a1, (unsigned int)a2, a3, &hMem);
  if ( Error >= 0 )
  {
    v5 = a2;
    v6 = hMem;
    if ( !ConvertSidToStringSidW(*(PSID *)hMem, v5) )
      Error = ResultFromKnownLastError();
    LocalFree(v6);
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180047234  mov     [rsp+arg_0], rbx
0x180047239  push    rdi
0x18004723a  sub     rsp, 20h
0x18004723e  lea     r9, [rsp+28h+hMem]
0x180047243  mov     qword ptr [rdx], 0
0x18004724a  mov     rdi, rdx
0x18004724d  mov     [rsp+28h+hMem], 0
0x180047256  call    ??$SHQueryToken@U_TOKEN_USER@@@@YAJPEAXW4_TOKEN_INFORMATION_CLASS@@HPEAPEAU_TOKEN_USER@@@Z; SHQueryToken<_TOKEN_USER>(void *,_TOKEN_INFORMATION_CLASS,int,_TOKEN_USER * *)
0x18004725b  mov     ebx, eax
0x18004725d  test    eax, eax
0x18004725f  js      short loc_180047286
0x180047261  mov     rdx, rdi; StringSid
0x180047264  mov     rdi, [rsp+28h+hMem]
0x180047269  mov     rcx, [rdi]; Sid
0x18004726c  call    cs:__imp_ConvertSidToStringSidW
0x180047272  test    eax, eax
0x180047274  jnz     short loc_18004727D
0x180047276  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004727b  mov     ebx, eax
0x18004727d  mov     rcx, rdi; hMem
0x180047280  call    cs:__imp_LocalFree
0x180047286  mov     eax, ebx
0x180047288  mov     rbx, [rsp+28h+arg_0]
0x18004728d  add     rsp, 20h
0x180047291  pop     rdi
0x180047292  retn
```
