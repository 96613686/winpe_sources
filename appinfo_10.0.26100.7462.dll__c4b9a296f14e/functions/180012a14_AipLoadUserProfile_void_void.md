# AipLoadUserProfile(void *,void * *)

- ea: `0x180012a14`
- end: `0x180012b65`
- name: `?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z`
- size: `337`
- prototype: `unsigned int __fastcall(HANDLE hToken, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014da0`
- `0x18001e804`
- `0x18002a2a8`
- `0x18003ac30`
- `0x180041040`

## callees

- `0x180012a14`
- `0x1800449fa`
- `0x180044a20`

## import_xrefs

- `msvcrt!wcschr` at `0x180012aee`
- `msvcrt!wcschr` at `0x180012aee`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012a78`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012a78`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012aca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012ad8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012aca`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012ad8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012abc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012a8a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012abc`
- `USERENV!LoadUserProfileW` at `0x180012b24`
- `USERENV!LoadUserProfileW` at `0x180012b24`
- `SspiCli!GetUserNameExW` at `0x180012aac`
- `SspiCli!GetUserNameExW` at `0x180012aac`

## pseudocode

```c
__int64 __fastcall AipLoadUserProfile(HANDLE hToken, void **a2)
{
  DWORD LastError; // ebx
  wchar_t *v5; // rax
  WCHAR *v6; // rax
  ULONG nSize; // [rsp+20h] [rbp-E0h] BYREF
  _PROFILEINFOW ProfileInfo; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR NameBuffer[264]; // [rsp+60h] [rbp-A0h] BYREF

  memset_0(NameBuffer, 0, 0x202u);
  nSize = 257;
  memset(&ProfileInfo, 0, sizeof(ProfileInfo));
  LastError = 0;
  if ( ImpersonateLoggedOnUser(hToken) )
  {
    if ( !GetUserNameExW(NameSamCompatible, NameBuffer, &nSize) )
    {
      LastError = GetLastError();
      RevertToSelf();
      return LastError;
    }
    RevertToSelf();
    v5 = wcschr(NameBuffer, 0x5Cu);
    if ( v5 )
      v6 = v5 + 1;
    else
      v6 = NameBuffer;
    ProfileInfo.dwSize = 56;
    ProfileInfo.lpUserName = v6;
    ProfileInfo.lpProfilePath = 0;
    if ( LoadUserProfileW(hToken, &ProfileInfo) )
    {
      *a2 = ProfileInfo.hProfile;
      return LastError;
    }
  }
  return GetLastError();
}

```

## disassembly

```asm
0x180012a14  mov     [rsp-8+arg_10], rbx
0x180012a19  push    rbp
0x180012a1a  push    rsi
0x180012a1b  push    rdi
0x180012a1c  lea     rbp, [rsp-180h]
0x180012a24  sub     rsp, 280h
0x180012a2b  mov     rax, cs:__security_cookie
0x180012a32  xor     rax, rsp
0x180012a35  mov     [rbp+190h+var_20], rax
0x180012a3c  mov     rsi, rdx
0x180012a3f  mov     rdi, rcx
0x180012a42  xor     edx, edx; Val
0x180012a44  lea     rcx, [rsp+290h+NameBuffer]; void *
0x180012a49  mov     r8d, 202h; Size
0x180012a4f  call    memset_0
0x180012a54  xorps   xmm0, xmm0
0x180012a57  mov     [rsp+290h+nSize], 101h
0x180012a5f  xor     eax, eax
0x180012a61  mov     rcx, rdi; hToken
0x180012a64  movups  xmmword ptr [rsp+290h+ProfileInfo.dwSize], xmm0
0x180012a69  mov     [rsp+290h+ProfileInfo.hProfile], rax
0x180012a6e  movups  xmmword ptr [rsp+290h+ProfileInfo.lpProfilePath], xmm0
0x180012a73  movups  xmmword ptr [rsp+290h+ProfileInfo.lpServerName], xmm0
0x180012a78  call    cs:__imp_ImpersonateLoggedOnUser
0x180012a7f  nop     dword ptr [rax+rax+00h]
0x180012a84  xor     ebx, ebx
0x180012a86  test    eax, eax
0x180012a88  jnz     short loc_180012A9D
0x180012a8a  call    cs:__imp_GetLastError
0x180012a91  nop     dword ptr [rax+rax+00h]
0x180012a96  mov     ebx, eax
0x180012a98  jmp     loc_180012B40
0x180012a9d  lea     r8, [rsp+290h+nSize]; nSize
0x180012aa2  mov     ecx, 2; NameFormat
0x180012aa7  lea     rdx, [rsp+290h+NameBuffer]; lpNameBuffer
0x180012aac  call    cs:__imp_GetUserNameExW
0x180012ab3  nop     dword ptr [rax+rax+00h]
0x180012ab8  test    al, al
0x180012aba  jnz     short loc_180012AD8
0x180012abc  call    cs:__imp_GetLastError
0x180012ac3  nop     dword ptr [rax+rax+00h]
0x180012ac8  mov     ebx, eax
0x180012aca  call    cs:__imp_RevertToSelf
0x180012ad1  nop     dword ptr [rax+rax+00h]
0x180012ad6  jmp     short loc_180012B40
0x180012ad8  call    cs:__imp_RevertToSelf
0x180012adf  nop     dword ptr [rax+rax+00h]
0x180012ae4  mov     edx, 5Ch ; '\'; Ch
0x180012ae9  lea     rcx, [rsp+290h+NameBuffer]; Str
0x180012aee  call    cs:__imp_wcschr
0x180012af5  nop     dword ptr [rax+rax+00h]
0x180012afa  test    rax, rax
0x180012afd  jnz     short loc_180012B06
0x180012aff  lea     rax, [rsp+290h+NameBuffer]
0x180012b04  jmp     short loc_180012B0A
0x180012b06  add     rax, 2
0x180012b0a  lea     rdx, [rsp+290h+ProfileInfo]; lpProfileInfo
0x180012b0f  mov     [rsp+290h+ProfileInfo.dwSize], 38h ; '8'
0x180012b17  mov     rcx, rdi; hToken
0x180012b1a  mov     [rsp+290h+ProfileInfo.lpUserName], rax
0x180012b1f  mov     [rsp+290h+ProfileInfo.lpProfilePath], rbx
0x180012b24  call    cs:__imp_LoadUserProfileW
0x180012b2b  nop     dword ptr [rax+rax+00h]
0x180012b30  test    eax, eax
0x180012b32  jz      loc_180012A8A
0x180012b38  mov     rax, [rsp+290h+ProfileInfo.hProfile]
0x180012b3d  mov     [rsi], rax
0x180012b40  mov     eax, ebx
0x180012b42  mov     rcx, [rbp+190h+var_20]
0x180012b49  xor     rcx, rsp; StackCookie
0x180012b4c  call    __security_check_cookie
0x180012b51  mov     rbx, [rsp+290h+arg_10]
0x180012b59  add     rsp, 280h
0x180012b60  pop     rdi
0x180012b61  pop     rsi
0x180012b62  pop     rbp
0x180012b63  retn
```
