# DmImpersonate(ushort const *)

- ea: `0x180012a58`
- end: `0x180012b79`
- name: `?DmImpersonate@@YAJPEBG@Z`
- size: `289`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x18000620c`

## callees

- `0x180011eb4`
- `0x180012a58`
- `0x1800147e8`
- `0x180014abc`
- `0x180014fe8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012ab4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012af0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012ab4`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180012af0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b2b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012b2b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180012b5d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180012b49`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012b1b`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012b1b`

## pseudocode

```c
__int64 __fastcall DmImpersonate(const unsigned __int16 *a1)
{
  HANDLE v2; // rdi
  void *v3; // rsi
  signed int v4; // ebx
  int CurrentUserSid; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  __int64 v8; // r8
  int UserTokenFromSid; // eax
  signed int LastError; // eax
  WINBOOL v12; // [rsp+48h] [rbp+10h] BYREF
  void *v13; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp+20h] BYREF

  v12 = 0;
  v2 = 0;
  v3 = 0;
  hToken = 0;
  v13 = 0;
  v4 = IsRunningInSystemContext(&v12);
  if ( v4 >= 0 )
  {
    if ( v12 )
    {
      if ( (unsigned int)_o__wcsicmp(a1, L"S-1-5-18") )
      {
        UserTokenFromSid = GetUserTokenFromSid((__int64)a1, &hToken, v8);
        v2 = hToken;
        v4 = UserTokenFromSid;
        if ( UserTokenFromSid >= 0 && !ImpersonateLoggedOnUser(hToken) )
        {
          LastError = GetLastError();
          v4 = LastError;
          if ( LastError > 0 )
            v4 = (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
    else
    {
      CurrentUserSid = GetCurrentUserSid(&v13);
      v3 = v13;
      v4 = CurrentUserSid;
      if ( CurrentUserSid >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v13, a1) )
        {
          if ( (byte_180029B01 & 0x40) != 0 )
            McTemplateU0zz_EventWriteTransfer(v7, v6, v3, a1);
          v4 = -2147024891;
        }
        else
        {
          v4 = 1;
        }
      }
    }
  }
  LocalFree(v3);
  if ( v2 )
    CloseHandle(v2);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180012a58  mov     rax, rsp
0x180012a5b  mov     [rax+8], rbx
0x180012a5f  push    rbp
0x180012a60  push    rsi
0x180012a61  push    rdi
0x180012a62  sub     rsp, 20h
0x180012a66  mov     rbp, rcx
0x180012a69  mov     dword ptr [rax+10h], 0
0x180012a70  xor     edi, edi
0x180012a72  lea     rcx, [rax+10h]; IsMember
0x180012a76  xor     esi, esi
0x180012a78  mov     [rax+20h], rdi
0x180012a7c  mov     [rax+18h], rsi
0x180012a80  call    IsRunningInSystemContext
0x180012a85  mov     ebx, eax
0x180012a87  test    eax, eax
0x180012a89  js      loc_180012B46
0x180012a8f  cmp     [rsp+38h+arg_8], esi
0x180012a93  jnz     short loc_180012AE6
0x180012a95  lea     rcx, [rsp+38h+arg_10]
0x180012a9a  call    GetCurrentUserSid
0x180012a9f  mov     rsi, [rsp+38h+arg_10]
0x180012aa4  mov     ebx, eax
0x180012aa6  test    eax, eax
0x180012aa8  js      loc_180012B46
0x180012aae  mov     rdx, rbp
0x180012ab1  mov     rcx, rsi
0x180012ab4  call    cs:__imp__o__wcsicmp
0x180012abb  nop     dword ptr [rax+rax+00h]
0x180012ac0  test    eax, eax
0x180012ac2  jz      short loc_180012ADF
0x180012ac4  test    cs:byte_180029B01, 40h
0x180012acb  jz      short loc_180012AD8
0x180012acd  mov     r9, rbp
0x180012ad0  mov     r8, rsi
0x180012ad3  call    McTemplateU0zz_EventWriteTransfer
0x180012ad8  mov     ebx, 80070005h
0x180012add  jmp     short loc_180012B46
0x180012adf  mov     ebx, 1
0x180012ae4  jmp     short loc_180012B46
0x180012ae6  lea     rdx, aS1518; "S-1-5-18"
0x180012aed  mov     rcx, rbp
0x180012af0  call    cs:__imp__o__wcsicmp
0x180012af7  nop     dword ptr [rax+rax+00h]
0x180012afc  test    eax, eax
0x180012afe  jz      short loc_180012B46
0x180012b00  lea     rdx, [rsp+38h+hToken]
0x180012b05  mov     rcx, rbp
0x180012b08  call    GetUserTokenFromSid
0x180012b0d  mov     rdi, [rsp+38h+hToken]
0x180012b12  mov     ebx, eax
0x180012b14  test    eax, eax
0x180012b16  js      short loc_180012B46
0x180012b18  mov     rcx, rdi; hToken
0x180012b1b  call    cs:__imp_ImpersonateLoggedOnUser
0x180012b22  nop     dword ptr [rax+rax+00h]
0x180012b27  test    eax, eax
0x180012b29  jnz     short loc_180012B46
0x180012b2b  call    cs:__imp_GetLastError
0x180012b32  nop     dword ptr [rax+rax+00h]
0x180012b37  mov     ebx, eax
0x180012b39  test    eax, eax
0x180012b3b  jle     short loc_180012B46
0x180012b3d  movzx   ebx, ax
0x180012b40  or      ebx, 80070000h
0x180012b46  mov     rcx, rsi; hMem
0x180012b49  call    cs:__imp_LocalFree
0x180012b50  nop     dword ptr [rax+rax+00h]
0x180012b55  test    rdi, rdi
0x180012b58  jz      short loc_180012B69
0x180012b5a  mov     rcx, rdi; hObject
0x180012b5d  call    cs:__imp_CloseHandle
0x180012b64  nop     dword ptr [rax+rax+00h]
0x180012b69  mov     eax, ebx
0x180012b6b  mov     rbx, [rsp+38h+arg_0]
0x180012b70  add     rsp, 20h
0x180012b74  pop     rdi
0x180012b75  pop     rsi
0x180012b76  pop     rbp
0x180012b77  retn
```
