# AipLoadUserProfile(void *,void * *)

- ea: `0x18001158c`
- end: `0x1800116b5`
- name: `?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z`
- size: `297`
- prototype: `__int64 __fastcall(HANDLE hToken, void **)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180021968`
- `0x18002d8fc`
- `0x18002ed98`
- `0x18003d070`
- `0x1800436a8`

## callees

- `0x18001158c`
- `0x180046e1a`
- `0x180046e50`

## import_xrefs

- `msvcrt!wcschr` at `0x180011643`
- `msvcrt!wcschr` at `0x180011643`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011623`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800115fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011623`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800115f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800115f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001162b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011633`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001162b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180011633`
- `USERENV!LoadUserProfileW` at `0x180011677`
- `USERENV!LoadUserProfileW` at `0x180011677`
- `SspiCli!GetUserNameExW` at `0x180011619`
- `SspiCli!GetUserNameExW` at `0x180011619`

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
      LastError = 0;
      *a2 = ProfileInfo.hProfile;
      return LastError;
    }
  }
  return GetLastError();
}

```

## disassembly

```asm
0x18001158c  mov     [rsp-8+arg_10], rbx
0x180011591  mov     [rsp-8+arg_18], rdi
0x180011596  push    rbp
0x180011597  lea     rbp, [rsp-180h]
0x18001159f  sub     rsp, 280h
0x1800115a6  mov     rax, cs:__security_cookie
0x1800115ad  xor     rax, rsp
0x1800115b0  mov     [rbp+180h+var_10], rax
0x1800115b7  mov     rdi, rdx
0x1800115ba  mov     rbx, rcx
0x1800115bd  xor     edx, edx; Val
0x1800115bf  lea     rcx, [rsp+280h+NameBuffer]; void *
0x1800115c4  mov     r8d, 202h; Size
0x1800115ca  call    memset_0
0x1800115cf  xorps   xmm0, xmm0
0x1800115d2  mov     [rsp+280h+nSize], 101h
0x1800115da  xor     eax, eax
0x1800115dc  mov     rcx, rbx; hToken
0x1800115df  movups  xmmword ptr [rsp+280h+ProfileInfo.dwSize], xmm0
0x1800115e4  mov     [rsp+280h+ProfileInfo.hProfile], rax
0x1800115e9  movups  xmmword ptr [rsp+280h+ProfileInfo.lpProfilePath], xmm0
0x1800115ee  movups  xmmword ptr [rsp+280h+ProfileInfo.lpServerName], xmm0
0x1800115f3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800115f9  test    eax, eax
0x1800115fb  jnz     short loc_18001160A
0x1800115fd  call    cs:__imp_GetLastError
0x180011603  mov     ebx, eax
0x180011605  jmp     loc_18001168F
0x18001160a  lea     r8, [rsp+280h+nSize]; nSize
0x18001160f  mov     ecx, 2; NameFormat
0x180011614  lea     rdx, [rsp+280h+NameBuffer]; lpNameBuffer
0x180011619  call    cs:__imp_GetUserNameExW
0x18001161f  test    al, al
0x180011621  jnz     short loc_180011633
0x180011623  call    cs:__imp_GetLastError
0x180011629  mov     ebx, eax
0x18001162b  call    cs:__imp_RevertToSelf
0x180011631  jmp     short loc_18001168F
0x180011633  call    cs:__imp_RevertToSelf
0x180011639  mov     edx, 5Ch ; '\'; Ch
0x18001163e  lea     rcx, [rsp+280h+NameBuffer]; Str
0x180011643  call    cs:__imp_wcschr
0x180011649  test    rax, rax
0x18001164c  jnz     short loc_180011655
0x18001164e  lea     rax, [rsp+280h+NameBuffer]
0x180011653  jmp     short loc_180011659
0x180011655  add     rax, 2
0x180011659  lea     rdx, [rsp+280h+ProfileInfo]; lpProfileInfo
0x18001165e  mov     [rsp+280h+ProfileInfo.dwSize], 38h ; '8'
0x180011666  mov     rcx, rbx; hToken
0x180011669  mov     [rsp+280h+ProfileInfo.lpUserName], rax
0x18001166e  mov     [rsp+280h+ProfileInfo.lpProfilePath], 0
0x180011677  call    cs:__imp_LoadUserProfileW
0x18001167d  test    eax, eax
0x18001167f  jz      loc_1800115FD
0x180011685  mov     rax, [rsp+280h+ProfileInfo.hProfile]
0x18001168a  xor     ebx, ebx
0x18001168c  mov     [rdi], rax
0x18001168f  mov     eax, ebx
0x180011691  mov     rcx, [rbp+180h+var_10]
0x180011698  xor     rcx, rsp; StackCookie
0x18001169b  call    __security_check_cookie
0x1800116a0  lea     r11, [rsp+280h+var_s0]
0x1800116a8  mov     rbx, [r11+20h]
0x1800116ac  mov     rdi, [r11+28h]
0x1800116b0  mov     rsp, r11
0x1800116b3  pop     rbp
0x1800116b4  retn
```
