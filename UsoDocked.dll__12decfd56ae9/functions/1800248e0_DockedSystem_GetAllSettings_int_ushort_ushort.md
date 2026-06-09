# DockedSystem::GetAllSettings(int,ushort * *,ushort * *)

- ea: `0x1800248e0`
- end: `0x180024b6a`
- name: `?GetAllSettings@DockedSystem@@UEAAJHPEAPEAG0@Z`
- size: `650`
- prototype: `__int64 __fastcall(DockedSystem *this, __int64, unsigned __int16 **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180007660`
- `0x180007dc0`
- `0x1800183f4`
- `0x18001ba70`
- `0x18001ee04`
- `0x1800209fc`
- `0x180023a34`
- `0x180023a58`
- `0x1800248e0`
- `0x18003e98c`
- `0x18003e9e0`
- `0x180071010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18002499c`
- `OLEAUT32!__imp_SysAllocString` at `0x180024a5c`
- `OLEAUT32!__imp_SysAllocString` at `0x18002499c`
- `OLEAUT32!__imp_SysAllocString` at `0x180024a5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180024a44`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024a07`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180024a07`

## string_xrefs

- `0x180024b10`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x180024b3d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18002491c`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024946`: `onecore\enduser\windowsupdate\muse\orchestrator\system\windows\docked\dll\dockedsystem.cpp`
- `0x180024b2b`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`
- `0x180024b57`: `onecore\enduser\windowsupdate\muse\common\lib\woscsettings.cpp`

## pseudocode

```c
__int64 __fastcall DockedSystem::GetAllSettings(
        DockedSystem *this,
        __int64 a2,
        unsigned __int16 **a3,
        unsigned __int16 **a4)
{
  __int64 result; // rax
  const char *v7; // r9
  __int64 UniqueId; // rax
  unsigned __int16 *v9; // rax
  const char *v10; // r9
  int v11; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v13; // r8
  const OLECHAR *v14; // rcx
  unsigned __int16 *v15; // rax
  const char *v16; // r9
  int v17; // eax
  void *v18; // rbx
  HSTRING string; // [rsp+20h] [rbp-58h] BYREF
  OLECHAR *psz[2]; // [rsp+28h] [rbp-50h] BYREF
  __int128 v21; // [rsp+38h] [rbp-40h]
  unsigned __int16 *v22; // [rsp+48h] [rbp-30h]
  void *Block; // [rsp+50h] [rbp-28h] BYREF
  char v24; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  LODWORD(string) = 0;
  if ( a3 )
  {
    if ( a4 )
    {
      try
      {
        WOSCSettings::GetSettings(&Block);
        if ( v24 )
        {
          UniqueId = WOSCSettings::GetUniqueId(Block, psz);
          if ( *(_QWORD *)(UniqueId + 24) > 7u )
            UniqueId = *(_QWORD *)UniqueId;
          v9 = SysAllocString((const OLECHAR *)UniqueId);
          v22 = v9;
          LODWORD(string) = 1;
          if ( !v9 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x15F3,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v10);
          *a4 = v9;
          std::wstring::_Tidy_deallocate(psz);
          if ( !v24 )
            std::_Throw_bad_optional_access();
          string = 0;
          v11 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(**(_QWORD **)Block + 104LL))(*(_QWORD *)Block, &string);
          if ( v11 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x96,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
              (const char *)(unsigned int)v11,
              (int)string);
          StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
          *(_OWORD *)psz = 0;
          v21 = 0;
          v13 = -1;
          do
            ++v13;
          while ( StringRawBuffer[v13] );
          std::wstring::_Construct<1,unsigned short const *>(psz, StringRawBuffer, v13);
          if ( string )
            WindowsDeleteString(string);
          v14 = (const OLECHAR *)psz;
          if ( *((_QWORD *)&v21 + 1) > 7u )
            v14 = psz[0];
          v15 = SysAllocString(v14);
          v22 = v15;
          LODWORD(string) = 6;
          if ( !v15 )
            wil::details::in1diag3::_Throw_NullAlloc(
              retaddr,
              (void *)0x15F3,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
              v16);
          *a3 = v15;
          std::wstring::_Tidy_deallocate(psz);
          if ( !v24 )
            std::_Throw_bad_optional_access();
          v17 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)Block + 112LL))(*(_QWORD *)Block);
          if ( v17 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x4D,
              (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\common\\lib\\woscsettings.cpp",
              (const char *)(unsigned int)v17,
              (int)string);
          if ( v24 )
          {
            v18 = Block;
            if ( Block )
            {
              if ( *(_QWORD *)Block )
                (*(void (__fastcall **)(_QWORD))(**(_QWORD **)Block + 16LL))(*(_QWORD *)Block);
              operator delete(v18);
            }
          }
          result = 0;
        }
        else
        {
          result = 2147943568LL;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x16E,
                               (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docke"
                                             "d\\dll\\dockedsystem.cpp",
                               v7);
      }
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x15E,
        (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
        (const char *)0x80004003LL,
        (int)string);
      return 2147500035LL;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x15D,
      (unsigned int)"onecore\\enduser\\windowsupdate\\muse\\orchestrator\\system\\windows\\docked\\dll\\dockedsystem.cpp",
      (const char *)0x80004003LL,
      (int)string);
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800248e0  mov     [rsp+arg_0], rbx
0x1800248e5  mov     [rsp+arg_8], rsi
0x1800248ea  push    rdi
0x1800248eb  sub     rsp, 70h
0x1800248ef  mov     rax, cs:__security_cookie
0x1800248f6  xor     rax, rsp
0x1800248f9  mov     [rsp+78h+var_18], rax
0x1800248fe  mov     rbx, r9
0x180024901  mov     rdi, r8
0x180024904  xor     esi, esi
0x180024906  mov     dword ptr [rsp+78h+string], esi; int
0x18002490a  test    r8, r8
0x18002490d  jnz     short loc_180024934
0x18002490f  mov     rcx, [rsp+78h]; this
0x180024914  mov     ebx, 80004003h
0x180024919  mov     r9d, ebx; char *
0x18002491c  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024923  mov     edx, 15Dh; void *
0x180024928  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002492d  mov     eax, ebx
0x18002492f  jmp     loc_180024AF1
0x180024934  test    rbx, rbx
0x180024937  jnz     short loc_18002495E
0x180024939  mov     rcx, [rsp+78h]; this
0x18002493e  mov     ebx, 80004003h
0x180024943  mov     r9d, ebx; char *
0x180024946  lea     r8, aOnecoreEnduser_12; "onecore\\enduser\\windowsupdate\\muse\\"...
0x18002494d  mov     edx, 15Eh; void *
0x180024952  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024957  mov     eax, ebx
0x180024959  jmp     loc_180024AF1
0x18002495e  test    edx, edx
0x180024960  setnz   dl
0x180024963  lea     rcx, [rsp+78h+Block]
0x180024968  call    ?GetSettings@WOSCSettings@@SA?AV?$optional@V?$unique_ptr@VWOSCSettings@@U?$default_delete@VWOSCSettings@@@std@@@std@@@std@@_N@Z; WOSCSettings::GetSettings(bool)
0x18002496d  nop
0x18002496e  cmp     [rsp+78h+var_20], sil
0x180024973  jnz     short loc_18002497F
0x180024975  mov     eax, 80070490h
0x18002497a  jmp     loc_180024AF1
0x18002497f  lea     rdx, [rsp+78h+psz]
0x180024984  mov     rcx, [rsp+78h+Block]
0x180024989  call    ?GetUniqueId@WOSCSettings@@QEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; WOSCSettings::GetUniqueId(void)
0x18002498e  nop
0x18002498f  cmp     qword ptr [rax+18h], 7
0x180024994  jbe     short loc_180024999
0x180024996  mov     rax, [rax]
0x180024999  mov     rcx, rax; psz
0x18002499c  call    cs:__imp_SysAllocString
0x1800249a2  mov     [rsp+78h+var_30], rax
0x1800249a7  mov     dword ptr [rsp+78h+string], 1
0x1800249af  mov     rcx, [rsp+78h]; this
0x1800249b4  test    rax, rax
0x1800249b7  jz      loc_180024B10
0x1800249bd  mov     [rbx], rax
0x1800249c0  lea     rcx, [rsp+78h+psz]
0x1800249c5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800249ca  cmp     [rsp+78h+var_20], sil
0x1800249cf  jz      loc_180024B22
0x1800249d5  mov     rax, [rsp+78h+Block]
0x1800249da  mov     [rsp+78h+string], rsi; int
0x1800249df  mov     rcx, [rax]
0x1800249e2  mov     rax, [rcx]
0x1800249e5  lea     rdx, [rsp+78h+string]
0x1800249ea  mov     rax, [rax+68h]
0x1800249ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249f3  mov     rcx, [rsp+78h]; this
0x1800249f8  test    eax, eax
0x1800249fa  js      loc_180024B28
0x180024a00  xor     edx, edx; length
0x180024a02  mov     rcx, [rsp+78h+string]; string
0x180024a07  call    cs:__imp_WindowsGetStringRawBuffer
0x180024a0d  xorps   xmm0, xmm0
0x180024a10  movups  xmmword ptr [rsp+78h+psz], xmm0
0x180024a15  xorps   xmm1, xmm1
0x180024a18  movdqu  [rsp+78h+var_40], xmm1
0x180024a1e  or      r8, 0FFFFFFFFFFFFFFFFh
0x180024a22  inc     r8
0x180024a25  cmp     [rax+r8*2], si
0x180024a2a  jnz     short loc_180024A22
0x180024a2c  mov     rdx, rax
0x180024a2f  lea     rcx, [rsp+78h+psz]
0x180024a34  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180024a39  nop
0x180024a3a  mov     rcx, [rsp+78h+string]; string
0x180024a3f  test    rcx, rcx
0x180024a42  jz      short loc_180024A4B
0x180024a44  call    cs:__imp_WindowsDeleteString
0x180024a4a  nop
0x180024a4b  lea     rcx, [rsp+78h+psz]
0x180024a50  cmp     qword ptr [rsp+78h+var_40+8], 7
0x180024a56  cmova   rcx, [rsp+78h+psz]; psz
0x180024a5c  call    cs:__imp_SysAllocString
0x180024a62  mov     [rsp+78h+var_30], rax
0x180024a67  mov     dword ptr [rsp+78h+string], 6; int
0x180024a6f  mov     rcx, [rsp+78h]; this
0x180024a74  test    rax, rax
0x180024a77  jz      loc_180024B3D
0x180024a7d  mov     [rdi], rax
0x180024a80  lea     rcx, [rsp+78h+psz]
0x180024a85  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180024a8a  cmp     [rsp+78h+var_20], sil
0x180024a8f  jz      loc_180024B4F
0x180024a95  mov     rax, [rsp+78h+Block]
0x180024a9a  mov     rcx, [rax]
0x180024a9d  mov     rax, [rcx]
0x180024aa0  mov     rax, [rax+70h]
0x180024aa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024aa9  mov     rcx, [rsp+78h]; this
0x180024aae  test    eax, eax
0x180024ab0  js      loc_180024B54
0x180024ab6  cmp     [rsp+78h+var_20], sil
0x180024abb  jz      short loc_180024AE9
0x180024abd  mov     rbx, [rsp+78h+Block]
0x180024ac2  test    rbx, rbx
0x180024ac5  jz      short loc_180024AE9
0x180024ac7  mov     rcx, [rbx]
0x180024aca  test    rcx, rcx
0x180024acd  jz      short loc_180024ADC
0x180024acf  mov     rax, [rcx]
0x180024ad2  mov     rax, [rax+10h]
0x180024ad6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024adb  nop
0x180024adc  mov     edx, 58h ; 'X'
0x180024ae1  mov     rcx, rbx; Block
0x180024ae4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180024ae9  xor     eax, eax
0x180024aeb  jmp     short loc_180024AF1
0x180024aed  mov     eax, dword ptr [rsp+78h+string]
0x180024af1  mov     rcx, [rsp+78h+var_18]
0x180024af6  xor     rcx, rsp; StackCookie
0x180024af9  call    __security_check_cookie
0x180024afe  lea     r11, [rsp+78h+var_8]
0x180024b03  mov     rbx, [r11+10h]
0x180024b07  mov     rsi, [r11+18h]
0x180024b0b  mov     rsp, r11
0x180024b0e  pop     rdi
0x180024b0f  retn
0x180024b10  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b17  mov     edx, 15F3h; void *
0x180024b1c  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180024b22  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180024b28  mov     r9d, eax; char *
0x180024b2b  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024b32  mov     edx, 96h; void *
0x180024b37  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180024b3d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024b44  mov     edx, 15F3h; void *
0x180024b49  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180024b4f  call    ?_Throw_bad_optional_access@std@@YAXXZ; std::_Throw_bad_optional_access(void)
0x180024b54  mov     r9d, eax; char *
0x180024b57  lea     r8, aOnecoreEnduser_3; "onecore\\enduser\\windowsupdate\\muse\\"...
0x180024b5e  mov     edx, 4Dh ; 'M'; void *
0x180024b63  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
