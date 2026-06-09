# DmImpersonate(ushort const *)

- ea: `0x18006a860`
- end: `0x18006a984`
- name: `?DmImpersonate@@YAJPEBG@Z`
- size: `292`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800609dc`

## callees

- `0x18005ccbc`
- `0x18006a860`
- `0x18006c63c`
- `0x18006c910`
- `0x18006cea8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a8bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a8f8`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a8bc`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18006a8f8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a936`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a936`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a968`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006a968`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a954`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18006a954`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006a926`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18006a926`

## pseudocode

```c
__int64 __fastcall DmImpersonate(const unsigned __int16 *a1)
{
  HANDLE v2; // rdi
  LPWSTR v3; // rsi
  signed int v4; // ebx
  int CurrentUserSid; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  int UserTokenFromSid; // eax
  signed int LastError; // eax
  WINBOOL v11; // [rsp+48h] [rbp+10h] BYREF
  LPWSTR v12; // [rsp+50h] [rbp+18h] BYREF
  HANDLE hToken; // [rsp+58h] [rbp+20h] BYREF

  v11 = 0;
  v2 = 0;
  v3 = 0;
  hToken = 0;
  v12 = 0;
  v4 = IsRunningInSystemContext(&v11);
  if ( v4 >= 0 )
  {
    if ( v11 )
    {
      if ( (unsigned int)_o__wcsicmp(a1, L"S-1-5-18") )
      {
        UserTokenFromSid = GetUserTokenFromSid((__int64)a1, &hToken, 0);
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
      CurrentUserSid = GetCurrentUserSid(&v12);
      v3 = v12;
      v4 = CurrentUserSid;
      if ( CurrentUserSid >= 0 )
      {
        if ( (unsigned int)_o__wcsicmp(v12, a1) )
        {
          if ( (Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits & 0x4000) != 0 )
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
0x18006a860  mov     rax, rsp
0x18006a863  mov     [rax+8], rbx
0x18006a867  push    rbp
0x18006a868  push    rsi
0x18006a869  push    rdi
0x18006a86a  sub     rsp, 20h
0x18006a86e  mov     rbp, rcx
0x18006a871  mov     dword ptr [rax+10h], 0
0x18006a878  xor     edi, edi
0x18006a87a  lea     rcx, [rax+10h]; IsMember
0x18006a87e  xor     esi, esi
0x18006a880  mov     [rax+20h], rdi
0x18006a884  mov     [rax+18h], rsi
0x18006a888  call    IsRunningInSystemContext
0x18006a88d  mov     ebx, eax
0x18006a88f  test    eax, eax
0x18006a891  js      loc_18006A951
0x18006a897  cmp     [rsp+38h+arg_8], esi
0x18006a89b  jnz     short loc_18006A8EE
0x18006a89d  lea     rcx, [rsp+38h+arg_10]
0x18006a8a2  call    GetCurrentUserSid
0x18006a8a7  mov     rsi, [rsp+38h+arg_10]
0x18006a8ac  mov     ebx, eax
0x18006a8ae  test    eax, eax
0x18006a8b0  js      loc_18006A951
0x18006a8b6  mov     rdx, rbp
0x18006a8b9  mov     rcx, rsi
0x18006a8bc  call    cs:__imp__o__wcsicmp
0x18006a8c3  nop     dword ptr [rax+rax+00h]
0x18006a8c8  test    eax, eax
0x18006a8ca  jz      short loc_18006A8E7
0x18006a8cc  test    byte ptr cs:Microsoft_Windows_DeviceManagement_Enterprise_Diagnostics_ProviderEnableBits+1, 40h
0x18006a8d3  jz      short loc_18006A8E0
0x18006a8d5  mov     r9, rbp
0x18006a8d8  mov     r8, rsi
0x18006a8db  call    McTemplateU0zz_EventWriteTransfer
0x18006a8e0  mov     ebx, 80070005h
0x18006a8e5  jmp     short loc_18006A951
0x18006a8e7  mov     ebx, 1
0x18006a8ec  jmp     short loc_18006A951
0x18006a8ee  lea     rdx, aS1518; "S-1-5-18"
0x18006a8f5  mov     rcx, rbp
0x18006a8f8  call    cs:__imp__o__wcsicmp
0x18006a8ff  nop     dword ptr [rax+rax+00h]
0x18006a904  test    eax, eax
0x18006a906  jz      short loc_18006A951
0x18006a908  xor     r8d, r8d
0x18006a90b  lea     rdx, [rsp+38h+hToken]
0x18006a910  mov     rcx, rbp
0x18006a913  call    GetUserTokenFromSid
0x18006a918  mov     rdi, [rsp+38h+hToken]
0x18006a91d  mov     ebx, eax
0x18006a91f  test    eax, eax
0x18006a921  js      short loc_18006A951
0x18006a923  mov     rcx, rdi; hToken
0x18006a926  call    cs:__imp_ImpersonateLoggedOnUser
0x18006a92d  nop     dword ptr [rax+rax+00h]
0x18006a932  test    eax, eax
0x18006a934  jnz     short loc_18006A951
0x18006a936  call    cs:__imp_GetLastError
0x18006a93d  nop     dword ptr [rax+rax+00h]
0x18006a942  mov     ebx, eax
0x18006a944  test    eax, eax
0x18006a946  jle     short loc_18006A951
0x18006a948  movzx   ebx, ax
0x18006a94b  or      ebx, 80070000h
0x18006a951  mov     rcx, rsi; hMem
0x18006a954  call    cs:__imp_LocalFree
0x18006a95b  nop     dword ptr [rax+rax+00h]
0x18006a960  test    rdi, rdi
0x18006a963  jz      short loc_18006A974
0x18006a965  mov     rcx, rdi; hObject
0x18006a968  call    cs:__imp_CloseHandle
0x18006a96f  nop     dword ptr [rax+rax+00h]
0x18006a974  mov     eax, ebx
0x18006a976  mov     rbx, [rsp+38h+arg_0]
0x18006a97b  add     rsp, 20h
0x18006a97f  pop     rdi
0x18006a980  pop     rsi
0x18006a981  pop     rbp
0x18006a982  retn
```
