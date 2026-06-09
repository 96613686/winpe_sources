# AppReadiness::User::IsVDI(void)

- ea: `0x18005a948`
- end: `0x18005aa3e`
- name: `?IsVDI@User@AppReadiness@@QEAA_NXZ`
- size: `246`
- prototype: `bool __fastcall(AppReadiness::User *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18002b08c`

## callees

- `0x180027a4c`
- `0x18003ecb4`
- `0x1800473d8`
- `0x18005a948`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005a987`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18005a987`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreePropertyValue` at `0x18005aa22`
- `ext-ms-win-session-winsta-l1-1-0!WinStationFreePropertyValue` at `0x18005aa22`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetConnectionProperty` at `0x18005a9fe`
- `ext-ms-win-session-winsta-l1-1-0!WinStationGetConnectionProperty` at `0x18005a9fe`

## string_xrefs

- `0x18005a99a`: `onecoreuap\shell\appreadiness\src\core\user.cpp`
- `0x18005a9bc`: `GetTokenInformation(GetToken().Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &userSessionIdLen)`
- `0x18005a9ae`: `AppReadiness::User::IsVDI`

## pseudocode

```c
bool __fastcall AppReadiness::User::IsVDI(AppReadiness::User *this)
{
  int v1; // eax
  void *v3; // rcx
  int Error; // eax
  BOOL v5; // ebx
  _BYTE pExceptionObject[72]; // [rsp+30h] [rbp-48h] BYREF
  unsigned int v8; // [rsp+80h] [rbp+8h] BYREF
  DWORD v9; // [rsp+88h] [rbp+10h] BYREF
  __int64 v10; // [rsp+90h] [rbp+18h] BYREF

  v1 = *((_DWORD *)this + 74);
  if ( !v1 )
  {
    v3 = (void *)*((_QWORD *)this + 14);
    v9 = 0;
    v8 = 0;
    if ( !GetTokenInformation(v3, TokenSessionId, &v8, 4u, &v9) )
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
      {
        Windows::HResultException::HResultException(
          (Windows::HResultException *)pExceptionObject,
          Error,
          "GetTokenInformation(GetToken().Get(), TokenSessionId, &userSessionId, sizeof(userSessionId), &userSessionIdLen)",
          "AppReadiness::User::IsVDI",
          "onecoreuap\\shell\\appreadiness\\src\\core\\user.cpp",
          234);
        throw (Windows::HResultException *)pExceptionObject;
      }
    }
    v10 = 0;
    v5 = 1;
    if ( (unsigned __int8)WinStationGetConnectionProperty(v8, PROPERTY_TYPE_IS_VDI_GUEST, &v10) && *(_WORD *)v10 == 1 )
      v5 = *(_DWORD *)(v10 + 8) == 0;
    if ( v10 )
      WinStationFreePropertyValue(v10);
    v1 = v5 + 1;
    *((_DWORD *)this + 74) = v5 + 1;
  }
  return v1 == 1;
}

```

## disassembly

```asm
0x18005a948  mov     r11, rsp
0x18005a94b  push    rbx
0x18005a94c  push    rbp
0x18005a94d  push    rdi
0x18005a94e  sub     rsp, 60h
0x18005a952  mov     eax, [rcx+128h]
0x18005a958  mov     rdi, rcx
0x18005a95b  mov     ebp, 1
0x18005a960  test    eax, eax
0x18005a962  jnz     loc_18005AA31
0x18005a968  mov     rcx, [rcx+70h]; TokenHandle
0x18005a96c  lea     r9d, [rbp+3]; TokenInformationLength
0x18005a970  mov     [r11+10h], eax
0x18005a974  lea     r8, [r11+8]; TokenInformation
0x18005a978  mov     [r11+8], eax
0x18005a97c  lea     edx, [rbp+0Bh]; TokenInformationClass
0x18005a97f  lea     rax, [r11+10h]
0x18005a983  mov     [r11-58h], rax
0x18005a987  call    cs:__imp_GetTokenInformation
0x18005a98d  test    eax, eax
0x18005a98f  jnz     short loc_18005A9DA
0x18005a991  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18005a996  test    eax, eax
0x18005a998  jns     short loc_18005A9DA
0x18005a99a  lea     rcx, aOnecoreuapShel_34; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18005a9a1  mov     [rsp+78h+var_50], 0EAh; int
0x18005a9a9  mov     [rsp+78h+var_58], rcx; char *
0x18005a9ae  lea     r9, aAppreadinessUs_1; "AppReadiness::User::IsVDI"
0x18005a9b5  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18005a9ba  mov     edx, eax; int
0x18005a9bc  lea     r8, aGettokeninform; "GetTokenInformation(GetToken().Get(), T"...
0x18005a9c3  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x18005a9c8  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18005a9cf  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18005a9d4  call    _CxxThrowException_0
0x18005a9da  mov     ecx, [rsp+78h+arg_0]
0x18005a9e1  lea     r8, [rsp+78h+arg_10]
0x18005a9e9  lea     rdx, PROPERTY_TYPE_IS_VDI_GUEST
0x18005a9f0  mov     [rsp+78h+arg_10], 0
0x18005a9fc  mov     ebx, ebp
0x18005a9fe  call    cs:__imp_WinStationGetConnectionProperty
0x18005aa04  mov     rcx, [rsp+78h+arg_10]
0x18005aa0c  test    al, al
0x18005aa0e  jz      short loc_18005AA1D
0x18005aa10  cmp     bp, [rcx]
0x18005aa13  jnz     short loc_18005AA1D
0x18005aa15  xor     eax, eax
0x18005aa17  cmp     [rcx+8], eax
0x18005aa1a  cmovnz  ebx, eax
0x18005aa1d  test    rcx, rcx
0x18005aa20  jz      short loc_18005AA28
0x18005aa22  call    cs:__imp_WinStationFreePropertyValue
0x18005aa28  lea     eax, [rbx+1]
0x18005aa2b  mov     [rdi+128h], eax
0x18005aa31  cmp     eax, ebp
0x18005aa33  setz    al
0x18005aa36  add     rsp, 60h
0x18005aa3a  pop     rdi
0x18005aa3b  pop     rbp
0x18005aa3c  pop     rbx
0x18005aa3d  retn
```
