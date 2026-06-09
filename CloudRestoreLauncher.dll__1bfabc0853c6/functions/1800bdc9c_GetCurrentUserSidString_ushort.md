# GetCurrentUserSidString(ushort * *)

- ea: `0x1800bdc9c`
- end: `0x1800bdcfe`
- name: `?GetCurrentUserSidString@@YAJPEAPEAG@Z`
- size: `98`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800bc5ac`
- `0x1800bd330`

## callees

- `0x1800bdb98`
- `0x1800bdc9c`
- `0x1800beb8c`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800bdceb`
- `KERNEL32!LocalFree` at `0x1800bdceb`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800bdcd1`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800bdcd1`

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
0x1800bdc9c  mov     [rsp+arg_8], rbx
0x1800bdca1  push    rdi
0x1800bdca2  sub     rsp, 20h
0x1800bdca6  mov     rdi, rcx
0x1800bdca9  mov     qword ptr [rcx], 0
0x1800bdcb0  lea     rcx, [rsp+28h+Sid]; void **
0x1800bdcb5  mov     [rsp+28h+Sid], 0
0x1800bdcbe  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800bdcc3  mov     ebx, eax
0x1800bdcc5  test    eax, eax
0x1800bdcc7  js      short loc_1800BDCF1
0x1800bdcc9  mov     rcx, [rsp+28h+Sid]; Sid
0x1800bdcce  mov     rdx, rdi; StringSid
0x1800bdcd1  call    cs:__imp_ConvertSidToStringSidW
0x1800bdcd7  test    eax, eax
0x1800bdcd9  jz      short loc_1800BDCDF
0x1800bdcdb  xor     ebx, ebx
0x1800bdcdd  jmp     short loc_1800BDCE6
0x1800bdcdf  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800bdce4  mov     ebx, eax
0x1800bdce6  mov     rcx, [rsp+28h+Sid]; hMem
0x1800bdceb  call    cs:__imp_LocalFree
0x1800bdcf1  mov     eax, ebx
0x1800bdcf3  mov     rbx, [rsp+28h+arg_8]
0x1800bdcf8  add     rsp, 20h
0x1800bdcfc  pop     rdi
0x1800bdcfd  retn
```
