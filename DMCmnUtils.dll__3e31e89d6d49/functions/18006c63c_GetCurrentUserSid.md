# GetCurrentUserSid

- ea: `0x18006c63c`
- end: `0x18006c709`
- name: `GetCurrentUserSid`
- size: `205`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180069ef0`
- `0x18006a150`
- `0x18006a660`
- `0x18006a730`
- `0x18006a860`

## callees

- `0x18006c63c`
- `0x18006c710`
- `0x18006c7c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c699`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006c699`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c6ce`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c6ce`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6dd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006c6ed`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c689`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18006c689`

## pseudocode

```c
__int64 __fastcall GetCurrentUserSid(LPWSTR *a1)
{
  PSID v1; // rdi
  signed int CurrentUserToken; // ebx
  int UserSidFromToken; // eax
  signed int LastError; // eax
  LPWSTR StringSid; // [rsp+48h] [rbp+28h] BYREF
  PSID Sid; // [rsp+50h] [rbp+30h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp+38h] BYREF

  v1 = 0;
  Sid = 0;
  StringSid = 0;
  hObject = 0;
  CurrentUserToken = GetCurrentUserToken(&hObject);
  if ( CurrentUserToken >= 0 )
  {
    UserSidFromToken = GetUserSidFromToken(hObject, &Sid);
    v1 = Sid;
    CurrentUserToken = UserSidFromToken;
    if ( UserSidFromToken >= 0 )
    {
      if ( ConvertSidToStringSidW(Sid, &StringSid) )
      {
        *a1 = StringSid;
        StringSid = 0;
      }
      else
      {
        LastError = GetLastError();
        CurrentUserToken = LastError;
        if ( LastError > 0 )
          CurrentUserToken = (unsigned __int16)LastError | 0x80070000;
      }
    }
  }
  if ( hObject )
    CloseHandle(hObject);
  LocalFree(v1);
  LocalFree(StringSid);
  return (unsigned int)CurrentUserToken;
}

```

## disassembly

```asm
0x18006c63c  mov     [rsp-18h+arg_0], rbx
0x18006c641  push    rbp
0x18006c642  push    rsi
0x18006c643  push    rdi
0x18006c644  mov     rbp, rsp
0x18006c647  sub     rsp, 20h
0x18006c64b  xor     edi, edi
0x18006c64d  mov     rsi, rcx
0x18006c650  lea     rcx, [rbp+hObject]; TokenHandle
0x18006c654  mov     [rbp+Sid], rdi
0x18006c658  mov     [rbp+StringSid], rdi
0x18006c65c  mov     [rbp+hObject], rdi
0x18006c660  call    GetCurrentUserToken
0x18006c665  mov     ebx, eax
0x18006c667  test    eax, eax
0x18006c669  js      short loc_18006C6C5
0x18006c66b  mov     rcx, [rbp+hObject]; TokenHandle
0x18006c66f  lea     rdx, [rbp+Sid]
0x18006c673  call    GetUserSidFromToken
0x18006c678  mov     rdi, [rbp+Sid]
0x18006c67c  mov     ebx, eax
0x18006c67e  test    eax, eax
0x18006c680  js      short loc_18006C6C5
0x18006c682  lea     rdx, [rbp+StringSid]; StringSid
0x18006c686  mov     rcx, rdi; Sid
0x18006c689  call    cs:__imp_ConvertSidToStringSidW
0x18006c690  nop     dword ptr [rax+rax+00h]
0x18006c695  test    eax, eax
0x18006c697  jnz     short loc_18006C6B6
0x18006c699  call    cs:__imp_GetLastError
0x18006c6a0  nop     dword ptr [rax+rax+00h]
0x18006c6a5  mov     ebx, eax
0x18006c6a7  test    eax, eax
0x18006c6a9  jle     short loc_18006C6C5
0x18006c6ab  movzx   ebx, ax
0x18006c6ae  or      ebx, 80070000h
0x18006c6b4  jmp     short loc_18006C6C5
0x18006c6b6  mov     rax, [rbp+StringSid]
0x18006c6ba  mov     [rsi], rax
0x18006c6bd  mov     [rbp+StringSid], 0
0x18006c6c5  mov     rcx, [rbp+hObject]; hObject
0x18006c6c9  test    rcx, rcx
0x18006c6cc  jz      short loc_18006C6DA
0x18006c6ce  call    cs:__imp_CloseHandle
0x18006c6d5  nop     dword ptr [rax+rax+00h]
0x18006c6da  mov     rcx, rdi; hMem
0x18006c6dd  call    cs:__imp_LocalFree
0x18006c6e4  nop     dword ptr [rax+rax+00h]
0x18006c6e9  mov     rcx, [rbp+StringSid]; hMem
0x18006c6ed  call    cs:__imp_LocalFree
0x18006c6f4  nop     dword ptr [rax+rax+00h]
0x18006c6f9  mov     eax, ebx
0x18006c6fb  mov     rbx, [rsp+20h+arg_0]
0x18006c700  add     rsp, 20h
0x18006c704  pop     rdi
0x18006c705  pop     rsi
0x18006c706  pop     rbp
0x18006c707  retn
```
