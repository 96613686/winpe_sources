# GetCurrentUserSid

- ea: `0x1800147e8`
- end: `0x1800148b5`
- name: `GetCurrentUserSid`
- size: `205`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180012a58`

## callees

- `0x1800147e8`
- `0x1800148bc`
- `0x180014974`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014845`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180014845`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001487a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001487a`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014835`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180014835`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014899`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014889`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180014899`

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
0x1800147e8  mov     [rsp-18h+arg_0], rbx
0x1800147ed  push    rbp
0x1800147ee  push    rsi
0x1800147ef  push    rdi
0x1800147f0  mov     rbp, rsp
0x1800147f3  sub     rsp, 20h
0x1800147f7  xor     edi, edi
0x1800147f9  mov     rsi, rcx
0x1800147fc  lea     rcx, [rbp+hObject]; TokenHandle
0x180014800  mov     [rbp+Sid], rdi
0x180014804  mov     [rbp+StringSid], rdi
0x180014808  mov     [rbp+hObject], rdi
0x18001480c  call    GetCurrentUserToken
0x180014811  mov     ebx, eax
0x180014813  test    eax, eax
0x180014815  js      short loc_180014871
0x180014817  mov     rcx, [rbp+hObject]; TokenHandle
0x18001481b  lea     rdx, [rbp+Sid]
0x18001481f  call    GetUserSidFromToken
0x180014824  mov     rdi, [rbp+Sid]
0x180014828  mov     ebx, eax
0x18001482a  test    eax, eax
0x18001482c  js      short loc_180014871
0x18001482e  lea     rdx, [rbp+StringSid]; StringSid
0x180014832  mov     rcx, rdi; Sid
0x180014835  call    cs:__imp_ConvertSidToStringSidW
0x18001483c  nop     dword ptr [rax+rax+00h]
0x180014841  test    eax, eax
0x180014843  jnz     short loc_180014862
0x180014845  call    cs:__imp_GetLastError
0x18001484c  nop     dword ptr [rax+rax+00h]
0x180014851  mov     ebx, eax
0x180014853  test    eax, eax
0x180014855  jle     short loc_180014871
0x180014857  movzx   ebx, ax
0x18001485a  or      ebx, 80070000h
0x180014860  jmp     short loc_180014871
0x180014862  mov     rax, [rbp+StringSid]
0x180014866  mov     [rsi], rax
0x180014869  mov     [rbp+StringSid], 0
0x180014871  mov     rcx, [rbp+hObject]; hObject
0x180014875  test    rcx, rcx
0x180014878  jz      short loc_180014886
0x18001487a  call    cs:__imp_CloseHandle
0x180014881  nop     dword ptr [rax+rax+00h]
0x180014886  mov     rcx, rdi; hMem
0x180014889  call    cs:__imp_LocalFree
0x180014890  nop     dword ptr [rax+rax+00h]
0x180014895  mov     rcx, [rbp+StringSid]; hMem
0x180014899  call    cs:__imp_LocalFree
0x1800148a0  nop     dword ptr [rax+rax+00h]
0x1800148a5  mov     eax, ebx
0x1800148a7  mov     rbx, [rsp+20h+arg_0]
0x1800148ac  add     rsp, 20h
0x1800148b0  pop     rdi
0x1800148b1  pop     rsi
0x1800148b2  pop     rbp
0x1800148b3  retn
```
