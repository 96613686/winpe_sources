# DmGetUserSidFromToken(void *,ushort * *)

- ea: `0x18006a680`
- end: `0x18006a726`
- name: `?DmGetUserSidFromToken@@YAJPEAXPEAPEAG@Z`
- size: `166`
- prototype: `__int64 __fastcall(void *, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18006a680`
- `0x18006c7c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a6c8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a6c8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a6fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a70c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a6fb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a70c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a6b8`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006a6b8`

## pseudocode

```c
__int64 __fastcall DmGetUserSidFromToken(void *a1, unsigned __int16 **a2)
{
  int UserSidFromToken; // ebx
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+40h] [rbp+18h] BYREF
  PSID Sid; // [rsp+48h] [rbp+20h] BYREF

  Sid = 0;
  StringSid = 0;
  UserSidFromToken = GetUserSidFromToken(a1, &Sid);
  if ( UserSidFromToken >= 0 )
  {
    if ( ConvertSidToStringSidW(Sid, &StringSid) )
    {
      *a2 = StringSid;
      StringSid = 0;
    }
    else
    {
      LastError = GetLastError();
      UserSidFromToken = LastError;
      if ( LastError > 0 )
        UserSidFromToken = (unsigned __int16)LastError | 0x80070000;
    }
  }
  LocalFree(Sid);
  LocalFree(StringSid);
  return (unsigned int)UserSidFromToken;
}

```

## disassembly

```asm
0x18006a680  mov     rax, rsp
0x18006a683  mov     [rax+8], rbx
0x18006a687  push    rdi
0x18006a688  sub     rsp, 20h
0x18006a68c  mov     rdi, rdx
0x18006a68f  mov     qword ptr [rax+20h], 0
0x18006a697  lea     rdx, [rax+20h]
0x18006a69b  mov     qword ptr [rax+18h], 0
0x18006a6a3  call    GetUserSidFromToken
0x18006a6a8  mov     ebx, eax
0x18006a6aa  test    eax, eax
0x18006a6ac  js      short loc_18006A6F6
0x18006a6ae  mov     rcx, [rsp+28h+Sid]; Sid
0x18006a6b3  lea     rdx, [rsp+28h+StringSid]; StringSid
0x18006a6b8  call    cs:__imp_ConvertSidToStringSidW
0x18006a6bf  nop     dword ptr [rax+rax+00h]
0x18006a6c4  test    eax, eax
0x18006a6c6  jnz     short loc_18006A6E5
0x18006a6c8  call    cs:__imp_GetLastError
0x18006a6cf  nop     dword ptr [rax+rax+00h]
0x18006a6d4  mov     ebx, eax
0x18006a6d6  test    eax, eax
0x18006a6d8  jle     short loc_18006A6F6
0x18006a6da  movzx   ebx, ax
0x18006a6dd  or      ebx, 80070000h
0x18006a6e3  jmp     short loc_18006A6F6
0x18006a6e5  mov     rax, [rsp+28h+StringSid]
0x18006a6ea  mov     [rdi], rax
0x18006a6ed  mov     [rsp+28h+StringSid], 0
0x18006a6f6  mov     rcx, [rsp+28h+Sid]; hMem
0x18006a6fb  call    cs:__imp_LocalFree
0x18006a702  nop     dword ptr [rax+rax+00h]
0x18006a707  mov     rcx, [rsp+28h+StringSid]; hMem
0x18006a70c  call    cs:__imp_LocalFree
0x18006a713  nop     dword ptr [rax+rax+00h]
0x18006a718  mov     eax, ebx
0x18006a71a  mov     rbx, [rsp+28h+arg_0]
0x18006a71f  add     rsp, 20h
0x18006a723  pop     rdi
0x18006a724  retn
```
