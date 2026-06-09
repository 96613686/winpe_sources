# GetCurrentUserSidString(ushort * *)

- ea: `0x18002027c`
- end: `0x1800202de`
- name: `?GetCurrentUserSidString@@YAJPEAPEAG@Z`
- size: `98`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18001fcc0`
- `0x18001fed4`
- `0x180020c58`

## callees

- `0x18001e7b4`
- `0x180020100`
- `0x18002027c`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800202cb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800202cb`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800202b1`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800202b1`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSidString(LPWSTR *StringSid)
{
  int CurrentUserSid; // ebx
  PSID Sid; // [rsp+30h] [rbp+8h] BYREF

  *StringSid = 0;
  Sid = 0;
  CurrentUserSid = GetCurrentUserSid(&Sid);
  if ( CurrentUserSid >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, StringSid) )
      CurrentUserSid = 0;
    else
      CurrentUserSid = ResultFromKnownLastError();
    LocalFree(Sid);
  }
  return (unsigned int)CurrentUserSid;
}

```

## disassembly

```asm
0x18002027c  mov     [rsp+arg_8], rbx
0x180020281  push    rdi
0x180020282  sub     rsp, 20h
0x180020286  mov     rdi, rcx
0x180020289  mov     qword ptr [rcx], 0
0x180020290  lea     rcx, [rsp+28h+Sid]; void **
0x180020295  mov     [rsp+28h+Sid], 0
0x18002029e  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800202a3  mov     ebx, eax
0x1800202a5  test    eax, eax
0x1800202a7  js      short loc_1800202D1
0x1800202a9  mov     rcx, [rsp+28h+Sid]; Sid
0x1800202ae  mov     rdx, rdi; StringSid
0x1800202b1  call    cs:__imp_ConvertSidToStringSidW
0x1800202b7  test    eax, eax
0x1800202b9  jz      short loc_1800202BF
0x1800202bb  xor     ebx, ebx
0x1800202bd  jmp     short loc_1800202C6
0x1800202bf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800202c4  mov     ebx, eax
0x1800202c6  mov     rcx, [rsp+28h+Sid]; hMem
0x1800202cb  call    cs:__imp_LocalFree
0x1800202d1  mov     eax, ebx
0x1800202d3  mov     rbx, [rsp+28h+arg_8]
0x1800202d8  add     rsp, 20h
0x1800202dc  pop     rdi
0x1800202dd  retn
```
