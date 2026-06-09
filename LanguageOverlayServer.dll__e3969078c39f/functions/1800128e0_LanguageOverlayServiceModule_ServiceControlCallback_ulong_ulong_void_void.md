# LanguageOverlayServiceModule::_ServiceControlCallback(ulong,ulong,void *,void *)

- ea: `0x1800128e0`
- end: `0x1800129e9`
- name: `?_ServiceControlCallback@LanguageOverlayServiceModule@@CAKKKPEAX0@Z`
- size: `265`
- prototype: `DWORD __stdcall(DWORD dwControl, DWORD dwEventType, LPVOID lpEventData, LPVOID lpContext)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, installer_update`

## callees

- `0x18000a008`
- `0x180011334`
- `0x1800128e0`
- `0x180012b20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001296e`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001296e`
- `msvcp_win!_Mtx_unlock` at `0x180012980`
- `msvcp_win!_Mtx_unlock` at `0x180012980`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001290f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001292a`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001290f`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18001292a`
- `msvcp_win!_Mtx_lock` at `0x180012900`
- `msvcp_win!_Mtx_lock` at `0x180012900`

## string_xrefs

- `0x1800129d6`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x1800129a9`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`
- `0x1800129c5`: `onecore\base\languageoverlay\services\languageoverlayservice\lib\languageoverlayservicemodule.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall LanguageOverlayServiceModule::_ServiceControlCallback(
        DWORD dwControl,
        DWORD dwEventType,
        LPVOID lpEventData,
        char *lpContext)
{
  char *v6; // rdi
  int v7; // eax
  DWORD v8; // ebx
  DWORD v9; // ebx
  DWORD v10; // ebx
  int v11; // ebx
  const char *v12; // r9
  const char *v13; // r9
  __int64 result; // rax
  unsigned int v15; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v6 = lpContext + 16;
  v7 = _Mtx_lock((_Mtx_t)(lpContext + 16));
  try
  {
    if ( v7 )
      std::_Throw_Cpp_error(5);
    if ( *((_DWORD *)v6 + 19) == 0x7FFFFFFF )
    {
      *((_DWORD *)v6 + 19) = 2147483646;
      std::_Throw_Cpp_error(6);
    }
    v8 = dwControl - 1;
    if ( v8 )
    {
      v9 = v8 - 3;
      if ( !v9 )
      {
LABEL_15:
        _Mtx_unlock((_Mtx_t)v6);
        return 0;
      }
      v10 = v9 - 1;
      if ( v10 )
      {
        v11 = v10 - 10;
        if ( v11 )
        {
          if ( v11 != 17 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x17B,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
              (const char *)0x78,
              v15);
          if ( *((_DWORD *)lpContext + 31) == 3 )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x176,
              (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\languageoverlayservicemodule.cpp",
              (const char *)0x45B,
              v15);
          goto LABEL_15;
        }
      }
    }
    if ( *((_DWORD *)lpContext + 31) != 3 )
    {
      LanguageOverlayServiceModule::_UpdateStatus((LanguageOverlayServiceModule *)lpContext, 3u, 0);
      if ( !SetEvent(*((HANDLE *)lpContext + 18)) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
          v12);
    }
    goto LABEL_15;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x1F4,
                           (unsigned int)"onecore\\base\\languageoverlay\\services\\languageoverlayservice\\lib\\language"
                                         "overlayservicemodule.cpp",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x1800128e0  mov     [rsp+arg_0], rbx
0x1800128e5  mov     [rsp+arg_8], rsi
0x1800128ea  push    rdi; unsigned int
0x1800128eb  sub     rsp, 20h
0x1800128ef  mov     rsi, r9
0x1800128f2  mov     ebx, ecx
0x1800128f4  lea     rdi, [r9+10h]
0x1800128f8  mov     [rsp+28h+arg_18], rdi
0x1800128fd  mov     rcx, rdi; _Mtx_t
0x180012900  call    cs:__imp__Mtx_lock
0x180012906  test    eax, eax
0x180012908  jz      short loc_180012915
0x18001290a  mov     ecx, 5
0x18001290f  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012915  cmp     dword ptr [rdi+4Ch], 7FFFFFFFh
0x18001291c  jnz     short loc_180012931
0x18001291e  mov     dword ptr [rdi+4Ch], 7FFFFFFEh
0x180012925  mov     ecx, 6
0x18001292a  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180012930  nop
0x180012931  sub     ebx, 1
0x180012934  jz      short loc_180012952
0x180012936  sub     ebx, 3
0x180012939  jz      short loc_18001297D
0x18001293b  sub     ebx, 1
0x18001293e  jz      short loc_180012952
0x180012940  sub     ebx, 0Ah
0x180012943  jz      short loc_180012952
0x180012945  cmp     ebx, 11h
0x180012948  jnz     short loc_18001299E
0x18001294a  cmp     dword ptr [rsi+7Ch], 3
0x18001294e  jz      short loc_1800129BA
0x180012950  jmp     short loc_18001297D
0x180012952  cmp     dword ptr [rsi+7Ch], 3
0x180012956  jz      short loc_18001297D
0x180012958  xor     r8d, r8d; int
0x18001295b  lea     edx, [r8+3]; unsigned int
0x18001295f  mov     rcx, rsi; this
0x180012962  call    ?_UpdateStatus@LanguageOverlayServiceModule@@AEAAXKJ@Z; LanguageOverlayServiceModule::_UpdateStatus(ulong,long)
0x180012967  mov     rcx, [rsi+90h]; hEvent
0x18001296e  call    cs:__imp_SetEvent
0x180012974  mov     rcx, [rsp+28h]; this
0x180012979  test    eax, eax
0x18001297b  jz      short loc_1800129D6
0x18001297d  mov     rcx, rdi; _Mtx_t
0x180012980  call    cs:__imp__Mtx_unlock
0x180012986  xor     eax, eax
0x180012988  jmp     short loc_18001298E
0x18001298a  mov     eax, dword ptr [rsp+28h+arg_18]
0x18001298e  mov     rbx, [rsp+28h+arg_0]
0x180012993  mov     rsi, [rsp+28h+arg_8]
0x180012998  add     rsp, 20h
0x18001299c  pop     rdi
0x18001299d  retn
0x18001299e  mov     rcx, [rsp+28h]; this
0x1800129a3  mov     r9d, 78h ; 'x'; char *
0x1800129a9  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x1800129b0  mov     edx, 17Bh; void *
0x1800129b5  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800129ba  mov     rcx, [rsp+28h]; this
0x1800129bf  mov     r9d, 45Bh; char *
0x1800129c5  lea     r8, aOnecoreBaseLan_5; "onecore\\base\\languageoverlay\\service"...
0x1800129cc  mov     edx, 176h; void *
0x1800129d1  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1800129d6  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800129dd  mov     edx, 0A01h; void *
0x1800129e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
