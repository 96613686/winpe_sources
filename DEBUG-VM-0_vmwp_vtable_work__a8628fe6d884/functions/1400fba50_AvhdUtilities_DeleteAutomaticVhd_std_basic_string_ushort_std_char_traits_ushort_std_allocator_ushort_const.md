# AvhdUtilities::DeleteAutomaticVhd(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1400fba50`
- end: `0x1400fbb9d`
- name: `?DeleteAutomaticVhd@AvhdUtilities@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `333`
- prototype: `__int64 __fastcall(WCHAR *Src)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400fb9c0`

## callees

- `0x14002fb88`
- `0x140031c88`
- `0x14005b628`
- `0x14009d7ac`
- `0x1400fba50`
- `0x1401bbeac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbb2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbac1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400fbb2c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbaa5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb10`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb63`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbaa5`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb10`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400fbb63`

## string_xrefs

- `0x1400fba6f`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbada`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbb45`: `onecore\vm\common\avhd\avhdutilities.cpp`
- `0x1400fbb78`: `onecore\vm\common\avhd\avhdutilities.cpp`

## pseudocode

```c
__int64 __fastcall AvhdUtilities::DeleteAutomaticVhd(WCHAR *Src)
{
  int IsAutomaticVhd; // eax
  const WCHAR *v3; // rcx
  BOOL v4; // ebx
  DWORD LastError; // eax
  const WCHAR *v6; // rcx
  BOOL v7; // ebx
  DWORD v8; // eax
  const char *v9; // r9
  __int64 result; // rax
  LPCWSTR lpFileName[3]; // [rsp+20h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+38h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  IsAutomaticVhd = AvhdUtilities::IsAutomaticVhd();
  try
  {
    if ( !IsAutomaticVhd )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x24E,
        (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
        (const char *)0x57,
        (unsigned int)lpFileName[0]);
    std::operator+<unsigned short>((char *)lpFileName, Src, L".rct");
    v3 = (const WCHAR *)lpFileName;
    if ( v12 > 7 )
      v3 = lpFileName[0];
    v4 = DeleteFileW(v3);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( !v4 )
    {
      LastError = GetLastError();
      if ( LastError != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x260,
          (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
          (const char *)LastError,
          (unsigned int)lpFileName[0]);
    }
    std::operator+<unsigned short>((char *)lpFileName, Src, L".mrt");
    v6 = (const WCHAR *)lpFileName;
    if ( v12 > 7 )
      v6 = lpFileName[0];
    v7 = DeleteFileW(v6);
    std::wstring::_Tidy_deallocate(lpFileName);
    if ( !v7 )
    {
      v8 = GetLastError();
      if ( v8 != 2 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x26C,
          (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
          (const char *)v8,
          (unsigned int)lpFileName[0]);
    }
    if ( *((_QWORD *)Src + 3) > 7u )
      Src = *(WCHAR **)Src;
    if ( !DeleteFileW(Src) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x270,
        (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
        v9);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x273,
                           (unsigned int)"onecore\\vm\\common\\avhd\\avhdutilities.cpp",
                           v9);
  }
  return result;
}

```

## disassembly

```asm
0x1400fba50  mov     [rsp+arg_0], rbx
0x1400fba55  push    rdi
0x1400fba56  sub     rsp, 40h
0x1400fba5a  mov     rdi, rcx
0x1400fba5d  call    ?IsAutomaticVhd@AvhdUtilities@@SAHAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; AvhdUtilities::IsAutomaticVhd(std::wstring const &)
0x1400fba62  test    eax, eax
0x1400fba64  jnz     short loc_1400FBA80
0x1400fba66  mov     rcx, [rsp+48h]; this
0x1400fba6b  lea     r9d, [rax+57h]; char *
0x1400fba6f  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fba76  mov     edx, 24Eh; void *
0x1400fba7b  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fba80  lea     r8, aRct; ".rct"
0x1400fba87  mov     rdx, rdi; Src
0x1400fba8a  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400fba8f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400fba94  lea     rcx, [rsp+48h+lpFileName]
0x1400fba99  cmp     [rsp+48h+var_10], 7
0x1400fba9f  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400fbaa5  call    cs:__imp_DeleteFileW
0x1400fbaac  nop     dword ptr [rax+rax+00h]
0x1400fbab1  mov     ebx, eax
0x1400fbab3  lea     rcx, [rsp+48h+lpFileName]
0x1400fbab8  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400fbabd  test    ebx, ebx
0x1400fbabf  jnz     short loc_1400FBAEB
0x1400fbac1  call    cs:__imp_GetLastError
0x1400fbac8  nop     dword ptr [rax+rax+00h]
0x1400fbacd  cmp     eax, 2
0x1400fbad0  jz      short loc_1400FBAEB
0x1400fbad2  mov     rcx, [rsp+48h]; this
0x1400fbad7  mov     r9d, eax; char *
0x1400fbada  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbae1  mov     edx, 260h; void *
0x1400fbae6  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fbaeb  lea     r8, aMrt; ".mrt"
0x1400fbaf2  mov     rdx, rdi; Src
0x1400fbaf5  lea     rcx, [rsp+48h+lpFileName]; void *
0x1400fbafa  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x1400fbaff  lea     rcx, [rsp+48h+lpFileName]
0x1400fbb04  cmp     [rsp+48h+var_10], 7
0x1400fbb0a  cmova   rcx, [rsp+48h+lpFileName]; lpFileName
0x1400fbb10  call    cs:__imp_DeleteFileW
0x1400fbb17  nop     dword ptr [rax+rax+00h]
0x1400fbb1c  mov     ebx, eax
0x1400fbb1e  lea     rcx, [rsp+48h+lpFileName]
0x1400fbb23  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1400fbb28  test    ebx, ebx
0x1400fbb2a  jnz     short loc_1400FBB56
0x1400fbb2c  call    cs:__imp_GetLastError
0x1400fbb33  nop     dword ptr [rax+rax+00h]
0x1400fbb38  cmp     eax, 2
0x1400fbb3b  jz      short loc_1400FBB56
0x1400fbb3d  mov     rcx, [rsp+48h]; this
0x1400fbb42  mov     r9d, eax; char *
0x1400fbb45  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbb4c  mov     edx, 26Ch; void *
0x1400fbb51  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1400fbb56  cmp     qword ptr [rdi+18h], 7
0x1400fbb5b  jbe     short loc_1400FBB60
0x1400fbb5d  mov     rdi, [rdi]
0x1400fbb60  mov     rcx, rdi; lpFileName
0x1400fbb63  call    cs:__imp_DeleteFileW
0x1400fbb6a  nop     dword ptr [rax+rax+00h]
0x1400fbb6f  mov     rcx, [rsp+48h]; this
0x1400fbb74  test    eax, eax
0x1400fbb76  jnz     short loc_1400FBB89
0x1400fbb78  lea     r8, aOnecoreVmCommo_109; "onecore\\vm\\common\\avhd\\avhdutilitie"...
0x1400fbb7f  mov     edx, 270h; void *
0x1400fbb84  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400fbb89  xor     eax, eax
0x1400fbb8b  jmp     short loc_1400FBB91
0x1400fbb8d  mov     eax, [rsp+48h+arg_8]
0x1400fbb91  mov     rbx, [rsp+48h+arg_0]
0x1400fbb96  add     rsp, 40h
0x1400fbb9a  pop     rdi
0x1400fbb9b  retn
```
