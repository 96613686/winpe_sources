# ReallyDeleteProfile(wchar_t const *,wchar_t const *,wchar_t const *)

- ea: `0x180045918`
- end: `0x180045ac6`
- name: `?ReallyDeleteProfile@@YAJPEB_W00@Z`
- size: `430`
- prototype: `__int64 __fastcall(const wchar_t *, const wchar_t *, const wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180040d30`
- `0x1800414dc`

## callees

- `0x180002520`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x180045918`
- `0x1800463e4`
- `0x180047590`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004595b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004595b`
- `USERENV!DeleteProfileW` at `0x180045951`
- `USERENV!DeleteProfileW` at `0x180045951`

## string_xrefs

- `0x18004597b`: `DeleteProfile failed for %s (%s): %#x`
- `0x1800459bc`: `(SID for %s was unknown)`
- `0x1800459a0`: `DeleteProfileW succeeded for %s (%s)`
- `0x180045a43`: `Removing dir succeeded, but directory still exists.`
- `0x180045a76`: `Unable to fully delete profile directory %s for %s: %#x`
- `0x180045a8c`: `(profile directory confirmed gone: %s)`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ReallyDeleteProfile(const wchar_t *a1, const wchar_t *a2, const wchar_t *a3)
{
  DWORD LastError; // eax
  int v7; // ebx
  __int64 v9; // r8
  const struct std::filesystem::path *v10; // rdx
  const struct std::filesystem::path *v11; // rdx
  __int128 v12; // [rsp+38h] [rbp-50h] BYREF
  __int64 v13; // [rsp+48h] [rbp-40h]
  __int64 v14; // [rsp+50h] [rbp-38h]

  if ( a2 && *a2 )
  {
    if ( DeleteProfileW(a2, 0, 0) )
    {
      Log(4u, L"DeleteProfileW succeeded for %s (%s)", a1, a2);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError != 2 )
      {
        Log(3u, L"DeleteProfile failed for %s (%s): %#x", a1, a2, LastError);
        if ( v7 > 0 )
          return (unsigned __int16)v7 | 0x80070000;
        return (unsigned int)v7;
      }
      Log(4u, L"No profile found for %s (%s)", a1, a2);
    }
  }
  else
  {
    Log(4u, L"(SID for %s was unknown)", a1);
  }
  if ( a3 && *a3 )
  {
    v9 = -1;
    do
      ++v9;
    while ( a3[v9] );
    v12 = 0;
    v13 = 0;
    v14 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v12, a3);
    if ( std::filesystem::exists((std::filesystem *)&v12, v10)
      && (v7 = wil::RemoveDirectoryRecursiveNoThrow(a3, 2, -1), std::filesystem::exists((std::filesystem *)&v12, v11)) )
    {
      if ( v7 >= 0 )
      {
        Log(3u, L"Removing dir succeeded, but directory still exists.");
        v7 = -2147467259;
      }
    }
    else
    {
      v7 = 0;
    }
    std::wstring::~wstring(&v12);
    if ( v7 < 0 )
    {
      Log(3u, L"Unable to fully delete profile directory %s for %s: %#x", a3, a1, v7);
      return (unsigned int)v7;
    }
    Log(4u, L"(profile directory confirmed gone: %s)", a3);
  }
  else
  {
    Log(4u, L"(profile dir for %s was unknown)", a1);
  }
  return 0;
}

```

## disassembly

```asm
0x180045918  push    rbx
0x18004591a  push    rbp
0x18004591b  push    rsi
0x18004591c  push    rdi
0x18004591d  push    r14
0x18004591f  sub     rsp, 60h
0x180045923  mov     rax, cs:__security_cookie
0x18004592a  xor     rax, rsp
0x18004592d  mov     [rsp+88h+var_30], rax
0x180045932  mov     rdi, r8
0x180045935  mov     rsi, rdx
0x180045938  mov     rbp, rcx
0x18004593b  xor     r14d, r14d
0x18004593e  test    rdx, rdx
0x180045941  jz      short loc_1800459B9
0x180045943  cmp     [rdx], r14w
0x180045947  jz      short loc_1800459B9
0x180045949  xor     r8d, r8d; lpComputerName
0x18004594c  xor     edx, edx; lpProfilePath
0x18004594e  mov     rcx, rsi; lpSidString
0x180045951  call    cs:__imp_DeleteProfileW
0x180045957  test    eax, eax
0x180045959  jnz     short loc_1800459A0
0x18004595b  call    cs:__imp_GetLastError
0x180045961  mov     ebx, eax
0x180045963  cmp     eax, 2
0x180045966  jnz     short loc_180045971
0x180045968  lea     rdx, aNoProfileFound_0; "No profile found for %s (%s)"
0x18004596f  jmp     short loc_1800459A7
0x180045971  mov     [rsp+88h+var_68], ebx
0x180045975  mov     r9, rsi
0x180045978  mov     r8, rbp
0x18004597b  lea     rdx, aDeleteprofileF_0; "DeleteProfile failed for %s (%s): %#x"
0x180045982  mov     ecx, 3; unsigned __int8
0x180045987  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004598c  test    ebx, ebx
0x18004598e  jle     short loc_180045999
0x180045990  movzx   ebx, bx
0x180045993  or      ebx, 80070000h
0x180045999  mov     eax, ebx
0x18004599b  jmp     loc_180045AAE
0x1800459a0  lea     rdx, aDeleteprofilew_0; "DeleteProfileW succeeded for %s (%s)"
0x1800459a7  mov     r9, rsi
0x1800459aa  mov     r8, rbp
0x1800459ad  mov     ecx, 4; unsigned __int8
0x1800459b2  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800459b7  jmp     short loc_1800459CD
0x1800459b9  mov     r8, rbp
0x1800459bc  lea     rdx, aSidForSWasUnkn; "(SID for %s was unknown)"
0x1800459c3  mov     ecx, 4; unsigned __int8
0x1800459c8  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x1800459cd  test    rdi, rdi
0x1800459d0  jz      loc_180045A95
0x1800459d6  cmp     [rdi], r14w
0x1800459da  jz      loc_180045A95
0x1800459e0  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800459e4  mov     r8, rbx
0x1800459e7  inc     r8
0x1800459ea  cmp     [rdi+r8*2], r14w
0x1800459ef  jnz     short loc_1800459E7
0x1800459f1  xorps   xmm0, xmm0
0x1800459f4  movups  [rsp+88h+var_50], xmm0
0x1800459f9  mov     [rsp+88h+var_40], r14
0x1800459fe  mov     [rsp+88h+var_38], r14
0x180045a03  mov     rdx, rdi
0x180045a06  lea     rcx, [rsp+88h+var_50]
0x180045a0b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180045a10  nop
0x180045a11  lea     rcx, [rsp+88h+var_50]; this
0x180045a16  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x180045a1b  test    al, al
0x180045a1d  jz      short loc_180045A5B
0x180045a1f  mov     r8, rbx
0x180045a22  mov     edx, 2
0x180045a27  mov     rcx, rdi
0x180045a2a  call    ?RemoveDirectoryRecursiveNoThrow@wil@@YAJPEB_WW4RemoveDirectoryOptions@1@PEAX@Z; wil::RemoveDirectoryRecursiveNoThrow(wchar_t const *,wil::RemoveDirectoryOptions,void *)
0x180045a2f  mov     ebx, eax
0x180045a31  lea     rcx, [rsp+88h+var_50]; this
0x180045a36  call    ?exists@filesystem@std@@YA_NAEBVpath@12@@Z; std::filesystem::exists(std::filesystem::path const &)
0x180045a3b  test    al, al
0x180045a3d  jz      short loc_180045A5B
0x180045a3f  test    ebx, ebx
0x180045a41  js      short loc_180045A59
0x180045a43  lea     rdx, aRemovingDirSuc; "Removing dir succeeded, but directory s"...
0x180045a4a  mov     ecx, 3; unsigned __int8
0x180045a4f  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045a54  mov     ebx, 80004005h
0x180045a59  jmp     short loc_180045A5E
0x180045a5b  mov     ebx, r14d
0x180045a5e  lea     rcx, [rsp+88h+var_50]
0x180045a63  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180045a68  test    ebx, ebx
0x180045a6a  jns     short loc_180045A8C
0x180045a6c  mov     [rsp+88h+var_68], ebx
0x180045a70  mov     r9, rbp
0x180045a73  mov     r8, rdi
0x180045a76  lea     rdx, aUnableToFullyD; "Unable to fully delete profile director"...
0x180045a7d  mov     ecx, 3; unsigned __int8
0x180045a82  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045a87  jmp     loc_180045999
0x180045a8c  lea     rdx, aProfileDirecto; "(profile directory confirmed gone: %s)"
0x180045a93  jmp     short loc_180045A9F
0x180045a95  lea     rdx, aProfileDirForS; "(profile dir for %s was unknown)"
0x180045a9c  mov     rdi, rbp
0x180045a9f  mov     r8, rdi
0x180045aa2  mov     ecx, 4; unsigned __int8
0x180045aa7  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x180045aac  xor     eax, eax
0x180045aae  mov     rcx, [rsp+88h+var_30]
0x180045ab3  xor     rcx, rsp; StackCookie
0x180045ab6  call    __security_check_cookie
0x180045abb  add     rsp, 60h
0x180045abf  pop     r14
0x180045ac1  pop     rdi
0x180045ac2  pop     rsi
0x180045ac3  pop     rbp
0x180045ac4  pop     rbx
0x180045ac5  retn
```
