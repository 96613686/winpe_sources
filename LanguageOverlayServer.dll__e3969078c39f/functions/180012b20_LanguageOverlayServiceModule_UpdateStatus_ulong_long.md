# LanguageOverlayServiceModule::_UpdateStatus(ulong,long)

- ea: `0x180012b20`
- end: `0x180012c69`
- name: `?_UpdateStatus@LanguageOverlayServiceModule@@AEAAXKJ@Z`
- size: `329`
- prototype: `void __fastcall(LanguageOverlayServiceModule *__hidden this, unsigned int, int)`
- caller_count: `6`
- callee_count: `4`
- tags: `service_task, installer_update`

## callers

- `0x1800119a0`
- `0x1800120d0`
- `0x1800121a8`
- `0x18001242c`
- `0x18001244c`
- `0x1800128e0`

## callees

- `0x180003a00`
- `0x180011318`
- `0x180011334`
- `0x180012b20`

## import_xrefs

- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012bf8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x180012bf8`
- `msvcp_win!_Mtx_unlock` at `0x180012c17`
- `msvcp_win!_Mtx_unlock` at `0x180012c17`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012b5e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012b7a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012b5e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180012b7a`
- `msvcp_win!_Mtx_lock` at `0x180012b4f`
- `msvcp_win!_Mtx_lock` at `0x180012b4f`

## string_xrefs

- `0x180012c3a`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`
- `0x180012c57`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LanguageOverlayServiceModule::_UpdateStatus(LanguageOverlayServiceModule *this, DWORD a2, DWORD a3)
{
  char *v6; // rdi
  const char *v7; // r9
  unsigned int v8; // [rsp+20h] [rbp-48h]
  _SERVICE_STATUS ServiceStatus; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  v6 = (char *)this + 16;
  v8 = (_DWORD)this + 16;
  if ( _Mtx_lock((LanguageOverlayServiceModule *)((char *)this + 16)) )
  {
    std::_Throw_Cpp_error(5);
    __debugbreak();
  }
  if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
  {
    *((_DWORD *)v6 + 19) = 2147483646;
    std::_Throw_Cpp_error(6);
  }
  if ( *((_DWORD *)this + 31) == 3 && ((a2 - 1) & 0xFFFFFFFD) != 0 )
    wil::details::in1diag3::Throw_Win32(
      retaddr,
      (void *)0x191,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      (const char *)0x45B,
      v8);
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  ServiceStatus.dwCurrentState = a2;
  ServiceStatus.dwServiceType = 32;
  switch ( a2 )
  {
    case 1u:
      ServiceStatus.dwWin32ExitCode = a3;
      break;
    case 2u:
    case 3u:
      ServiceStatus.dwWaitHint = 3000;
      ServiceStatus.dwCheckPoint = *((_DWORD *)this + 32) + 1;
      break;
    case 4u:
      ServiceStatus.dwControlsAccepted = 1025;
      break;
  }
  if ( !SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 17), &ServiceStatus) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1A9,
      (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
      v7);
  *((_DWORD *)this + 31) = a2;
  *((_DWORD *)this + 32) = ServiceStatus.dwCheckPoint;
  _Mtx_unlock((_Mtx_t)v6);
}

```

## disassembly

```asm
0x180012b20  mov     [rsp+arg_18], rbx
0x180012b25  push    rbp
0x180012b26  push    rsi
0x180012b27  push    rdi
0x180012b28  sub     rsp, 50h
0x180012b2c  mov     rax, cs:__security_cookie
0x180012b33  xor     rax, rsp
0x180012b36  mov     [rsp+68h+var_20], rax
0x180012b3b  mov     ebp, r8d
0x180012b3e  mov     esi, edx
0x180012b40  mov     rbx, rcx
0x180012b43  lea     rdi, [rcx+10h]
0x180012b47  mov     qword ptr [rsp+68h+var_48], rdi; unsigned int
0x180012b4c  mov     rcx, rdi; _Mtx_t
0x180012b4f  call    cs:__imp__Mtx_lock
0x180012b55  test    eax, eax
0x180012b57  jz      short loc_180012B65
0x180012b59  mov     ecx, 5
0x180012b5e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012b64  int     3; Trap to Debugger
0x180012b65  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x180012b6c  jnz     short loc_180012B81
0x180012b6e  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180012b75  mov     ecx, 6
0x180012b7a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012b80  nop
0x180012b81  cmp     dword ptr [rbx+7Ch], 3
0x180012b85  jnz     short loc_180012B95
0x180012b87  lea     eax, [rsi-1]
0x180012b8a  test    eax, 0FFFFFFFDh
0x180012b8f  jnz     loc_180012C4C
0x180012b95  xorps   xmm0, xmm0
0x180012b98  movdqu  xmmword ptr [rsp+68h+ServiceStatus.dwControlsAccepted], xmm0
0x180012b9e  mov     [rsp+68h+ServiceStatus.dwWaitHint], 0
0x180012ba6  mov     [rsp+68h+ServiceStatus.dwCurrentState], esi
0x180012baa  mov     [rsp+68h+ServiceStatus.dwServiceType], 20h ; ' '
0x180012bb2  mov     eax, esi
0x180012bb4  sub     eax, 1
0x180012bb7  jz      short loc_180012BE8
0x180012bb9  sub     eax, 1
0x180012bbc  jz      short loc_180012BD2
0x180012bbe  sub     eax, 1
0x180012bc1  jz      short loc_180012BD2
0x180012bc3  cmp     eax, 1
0x180012bc6  jnz     short loc_180012BEC
0x180012bc8  mov     [rsp+68h+ServiceStatus.dwControlsAccepted], 401h
0x180012bd0  jmp     short loc_180012BEC
0x180012bd2  mov     [rsp+68h+ServiceStatus.dwWaitHint], 0BB8h
0x180012bda  mov     eax, [rbx+80h]
0x180012be0  inc     eax
0x180012be2  mov     [rsp+68h+ServiceStatus.dwCheckPoint], eax
0x180012be6  jmp     short loc_180012BEC
0x180012be8  mov     [rsp+68h+ServiceStatus.dwWin32ExitCode], ebp
0x180012bec  lea     rdx, [rsp+68h+ServiceStatus]; lpServiceStatus
0x180012bf1  mov     rcx, [rbx+88h]; hServiceStatus
0x180012bf8  call    cs:__imp_SetServiceStatus
0x180012bfe  mov     rcx, [rsp+68h]; this
0x180012c03  test    eax, eax
0x180012c05  jz      short loc_180012C3A
0x180012c07  mov     [rbx+7Ch], esi
0x180012c0a  mov     eax, [rsp+68h+ServiceStatus.dwCheckPoint]
0x180012c0e  mov     [rbx+80h], eax
0x180012c14  mov     rcx, rdi; _Mtx_t
0x180012c17  call    cs:__imp__Mtx_unlock
0x180012c1d  mov     rcx, [rsp+68h+var_20]
0x180012c22  xor     rcx, rsp; StackCookie
0x180012c25  call    __security_check_cookie
0x180012c2a  mov     rbx, [rsp+68h+arg_18]
0x180012c32  add     rsp, 50h
0x180012c36  pop     rdi
0x180012c37  pop     rsi
0x180012c38  pop     rbp
0x180012c39  retn
0x180012c3a  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x180012c41  mov     edx, 1A9h; void *
0x180012c46  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x180012c4c  mov     rcx, [rsp+68h]; this
0x180012c51  mov     r9d, 45Bh; char *
0x180012c57  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x180012c5e  mov     edx, 191h; void *
0x180012c63  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
```
