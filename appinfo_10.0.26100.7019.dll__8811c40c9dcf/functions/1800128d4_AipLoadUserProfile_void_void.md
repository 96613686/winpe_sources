# AipLoadUserProfile(void *,void * *)

- ea: `0x1800128d4`
- end: `0x180012a25`
- name: `?AipLoadUserProfile@@YAKPEAXPEAPEAX@Z`
- size: `337`
- prototype: `unsigned int __fastcall(HANDLE hToken, void **)`
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180014d40`
- `0x18002b828`
- `0x180039cb0`
- `0x18003ef30`

## callees

- `0x1800128d4`
- `0x18004292a`
- `0x180042950`

## import_xrefs

- `msvcrt!wcschr` at `0x1800129ae`
- `msvcrt!wcschr` at `0x1800129ae`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012938`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180012938`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001298a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012998`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001298a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180012998`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001294a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001297c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001294a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001297c`
- `SspiCli!GetUserNameExW` at `0x18001296c`
- `SspiCli!GetUserNameExW` at `0x18001296c`
- `USERENV!LoadUserProfileW` at `0x1800129e4`
- `USERENV!LoadUserProfileW` at `0x1800129e4`

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
0x1800128d4  mov     [rsp-8+arg_10], rbx
0x1800128d9  push    rbp
0x1800128da  push    rsi
0x1800128db  push    rdi
0x1800128dc  lea     rbp, [rsp-180h]
0x1800128e4  sub     rsp, 280h
0x1800128eb  mov     rax, cs:__security_cookie
0x1800128f2  xor     rax, rsp
0x1800128f5  mov     [rbp+190h+var_20], rax
0x1800128fc  mov     rsi, rdx
0x1800128ff  mov     rdi, rcx
0x180012902  xor     edx, edx; Val
0x180012904  lea     rcx, [rsp+290h+NameBuffer]; void *
0x180012909  mov     r8d, 202h; Size
0x18001290f  call    memset_0
0x180012914  xorps   xmm0, xmm0
0x180012917  mov     [rsp+290h+nSize], 101h
0x18001291f  xor     eax, eax
0x180012921  mov     rcx, rdi; hToken
0x180012924  movups  xmmword ptr [rsp+290h+ProfileInfo.dwSize], xmm0
0x180012929  mov     [rsp+290h+ProfileInfo.hProfile], rax
0x18001292e  movups  xmmword ptr [rsp+290h+ProfileInfo.lpProfilePath], xmm0
0x180012933  movups  xmmword ptr [rsp+290h+ProfileInfo.lpServerName], xmm0
0x180012938  call    cs:__imp_ImpersonateLoggedOnUser
0x18001293f  nop     dword ptr [rax+rax+00h]
0x180012944  xor     ebx, ebx
0x180012946  test    eax, eax
0x180012948  jnz     short loc_18001295D
0x18001294a  call    cs:__imp_GetLastError
0x180012951  nop     dword ptr [rax+rax+00h]
0x180012956  mov     ebx, eax
0x180012958  jmp     loc_180012A00
0x18001295d  lea     r8, [rsp+290h+nSize]; nSize
0x180012962  mov     ecx, 2; NameFormat
0x180012967  lea     rdx, [rsp+290h+NameBuffer]; lpNameBuffer
0x18001296c  call    cs:__imp_GetUserNameExW
0x180012973  nop     dword ptr [rax+rax+00h]
0x180012978  test    al, al
0x18001297a  jnz     short loc_180012998
0x18001297c  call    cs:__imp_GetLastError
0x180012983  nop     dword ptr [rax+rax+00h]
0x180012988  mov     ebx, eax
0x18001298a  call    cs:__imp_RevertToSelf
0x180012991  nop     dword ptr [rax+rax+00h]
0x180012996  jmp     short loc_180012A00
0x180012998  call    cs:__imp_RevertToSelf
0x18001299f  nop     dword ptr [rax+rax+00h]
0x1800129a4  mov     edx, 5Ch ; '\'; Ch
0x1800129a9  lea     rcx, [rsp+290h+NameBuffer]; Str
0x1800129ae  call    cs:__imp_wcschr
0x1800129b5  nop     dword ptr [rax+rax+00h]
0x1800129ba  test    rax, rax
0x1800129bd  jnz     short loc_1800129C6
0x1800129bf  lea     rax, [rsp+290h+NameBuffer]
0x1800129c4  jmp     short loc_1800129CA
0x1800129c6  add     rax, 2
0x1800129ca  lea     rdx, [rsp+290h+ProfileInfo]; lpProfileInfo
0x1800129cf  mov     [rsp+290h+ProfileInfo.dwSize], 38h ; '8'
0x1800129d7  mov     rcx, rdi; hToken
0x1800129da  mov     [rsp+290h+ProfileInfo.lpUserName], rax
0x1800129df  mov     [rsp+290h+ProfileInfo.lpProfilePath], rbx
0x1800129e4  call    cs:__imp_LoadUserProfileW
0x1800129eb  nop     dword ptr [rax+rax+00h]
0x1800129f0  test    eax, eax
0x1800129f2  jz      loc_18001294A
0x1800129f8  mov     rax, [rsp+290h+ProfileInfo.hProfile]
0x1800129fd  mov     [rsi], rax
0x180012a00  mov     eax, ebx
0x180012a02  mov     rcx, [rbp+190h+var_20]
0x180012a09  xor     rcx, rsp; StackCookie
0x180012a0c  call    __security_check_cookie
0x180012a11  mov     rbx, [rsp+290h+arg_10]
0x180012a19  add     rsp, 280h
0x180012a20  pop     rdi
0x180012a21  pop     rsi
0x180012a22  pop     rbp
0x180012a23  retn
```
