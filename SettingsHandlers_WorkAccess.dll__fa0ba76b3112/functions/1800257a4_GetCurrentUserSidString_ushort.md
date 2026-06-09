# GetCurrentUserSidString(ushort * *)

- ea: `0x1800257a4`
- end: `0x180025813`
- name: `?GetCurrentUserSidString@@YAJPEAPEAG@Z`
- size: `111`
- prototype: `__int64 __fastcall(LPWSTR *StringSid)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180026be8`
- `0x1800426e0`
- `0x1800461f0`
- `0x1800462d8`
- `0x18004862c`

## callees

- `0x18001f164`
- `0x180025678`
- `0x1800257a4`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257f9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800257f9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800257d9`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800257d9`

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
0x1800257a4  mov     [rsp+arg_8], rbx
0x1800257a9  push    rdi
0x1800257aa  sub     rsp, 20h
0x1800257ae  mov     rdi, rcx
0x1800257b1  mov     qword ptr [rcx], 0
0x1800257b8  lea     rcx, [rsp+28h+Sid]; void **
0x1800257bd  mov     [rsp+28h+Sid], 0
0x1800257c6  call    ?GetCurrentUserSid@@YAJPEAPEAX@Z; GetCurrentUserSid(void * *)
0x1800257cb  mov     ebx, eax
0x1800257cd  test    eax, eax
0x1800257cf  js      short loc_180025805
0x1800257d1  mov     rcx, [rsp+28h+Sid]; Sid
0x1800257d6  mov     rdx, rdi; StringSid
0x1800257d9  call    cs:__imp_ConvertSidToStringSidW
0x1800257e0  nop     dword ptr [rax+rax+00h]
0x1800257e5  test    eax, eax
0x1800257e7  jz      short loc_1800257ED
0x1800257e9  xor     ebx, ebx
0x1800257eb  jmp     short loc_1800257F4
0x1800257ed  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800257f2  mov     ebx, eax
0x1800257f4  mov     rcx, [rsp+28h+Sid]; hMem
0x1800257f9  call    cs:__imp_LocalFree
0x180025800  nop     dword ptr [rax+rax+00h]
0x180025805  mov     eax, ebx
0x180025807  mov     rbx, [rsp+28h+arg_8]
0x18002580c  add     rsp, 20h
0x180025810  pop     rdi
0x180025811  retn
```
