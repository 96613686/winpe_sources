# _anonymous_namespace_::TempCleanup::EnumStateRoot

- ea: `0x1800286e4`
- end: `0x18002891c`
- name: `_anonymous_namespace_::TempCleanup::EnumStateRoot`
- size: `568`
- prototype: `void __fastcall(const wchar_t *wzStateRoot, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800230dc`

## callees

- `0x1800026d0`
- `0x180017858`
- `0x1800186bc`
- `0x1800286e4`
- `0x1800415ee`
- `0x180041620`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180028786`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180028786`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800288e8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800288e8`

## string_xrefs

- `0x1800287f0`: `TempState`
- `0x180028868`: `AC\Temp`

## pseudocode

```c
void __fastcall anonymous_namespace_::TempCleanup::EnumStateRoot(const wchar_t *wzStateRoot, __int64 a2)
{
  HRESULT v4; // eax
  HANDLE FirstFileW; // rbx
  int v6; // edx
  int v7; // edx
  HRESULT v8; // eax
  HRESULT v9; // eax
  _WIN32_FIND_DATAW fd; // [rsp+40h] [rbp-C0h] BYREF
  wchar_t wzPathToClean[264]; // [rsp+290h] [rbp+190h] BYREF
  wchar_t wzFind[264]; // [rsp+4A0h] [rbp+3A0h] BYREF
  void *retaddr; // [rsp+6E8h] [rbp+5E8h]

  v4 = StringCchPrintfW(wzFind, 0x104u, L"%s\\*", a2);
  if ( wil::details::in1diag3::Log_IfFailedMsg(
         retaddr,
         0xBFu,
         "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
         v4,
         "StringCchPrintfW %ws",
         a2) >= 0 )
  {
    memset_0(&fd, 0, sizeof(fd));
    FirstFileW = FindFirstFileW(wzFind, &fd);
    if ( FirstFileW != (HANDLE)-1LL )
    {
      do
      {
        if ( (fd.dwFileAttributes & 0x10) != 0 )
        {
          v6 = fd.cFileName[0] - 46;
          if ( fd.cFileName[0] == 46 )
            v6 = fd.cFileName[1];
          if ( v6 )
          {
            v7 = fd.cFileName[0] - 46;
            if ( fd.cFileName[0] == 46 )
            {
              v7 = fd.cFileName[1] - 46;
              if ( fd.cFileName[1] == 46 )
                v7 = fd.cFileName[2];
            }
            if ( v7 )
            {
              v8 = StringCchPrintfW(wzPathToClean, 0x104u, L"%s\\%s\\%s", a2, fd.cFileName, L"TempState");
              if ( wil::details::in1diag3::Log_IfFailedMsg(
                     retaddr,
                     0xD6u,
                     "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
                     v8,
                     "StringCchPrintfW STATE %ws file %ws",
                     a2,
                     fd.cFileName) >= 0 )
                anonymous_namespace_::TempCleanup::CleanupTempRoot(wzStateRoot);
              v9 = StringCchPrintfW(wzPathToClean, 0x104u, L"%s\\%s\\%s", a2, fd.cFileName, L"AC\\Temp");
              if ( wil::details::in1diag3::Log_IfFailedMsg(
                     retaddr,
                     0xDDu,
                     "onecoreuap\\base\\appmodel\\statemanager\\winrt\\cleanup\\cleanup.cpp",
                     v9,
                     "StringCchPrintfW AC %ws file %ws",
                     a2,
                     fd.cFileName) >= 0 )
                anonymous_namespace_::TempCleanup::CleanupTempRoot(wzStateRoot);
            }
          }
        }
      }
      while ( FindNextFileW(FirstFileW, &fd) );
    }
  }
}

```

## disassembly

```asm
0x1800286e4  mov     [rsp-8+arg_10], rbx
0x1800286e9  push    rbp
0x1800286ea  push    rsi
0x1800286eb  push    rdi
0x1800286ec  push    r14
0x1800286ee  push    r15
0x1800286f0  lea     rbp, [rsp-5C0h]
0x1800286f8  sub     rsp, 6C0h
0x1800286ff  mov     rax, cs:__security_cookie
0x180028706  xor     rax, rsp
0x180028709  mov     [rbp+5E0h+var_30], rax
0x180028710  mov     rsi, wzStateRoot
0x180028713  lea     r8, aS; "%s\\*"
0x18002871a  mov     rdi, this
0x18002871d  mov     r9, wzStateRoot
0x180028720  mov     r15d, 104h
0x180028726  lea     this, [rbp+5E0h+wzFind]; pszDest
0x18002872d  mov     edx, r15d; cchDest
0x180028730  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028735  mov     this, [rbp+5E8h]; callerReturnAddress
0x18002873c  lea     wzStateRoot, aStringcchprint; "StringCchPrintfW %ws"
0x180028743  mov     [rsp+6E0h+var_6B8], rsi
0x180028748  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x18002874f  mov     [rsp+6E0h+formatString], wzStateRoot; formatString
0x180028754  mov     r9d, eax; hr
0x180028757  lea     edx, [r15-45h]; lineNumber
0x18002875b  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180028760  test    eax, eax
0x180028762  js      loc_1800288F6
0x180028768  xor     edx, edx; Val
0x18002876a  lea     this, [rsp+6E0h+fd]; void *
0x18002876f  mov     r8d, 250h; Size
0x180028775  call    memset_0
0x18002877a  lea     wzStateRoot, [rsp+6E0h+fd]; lpFindFileData
0x18002877f  lea     this, [rbp+5E0h+wzFind]; lpFileName
0x180028786  call    cs:__imp_FindFirstFileW
0x18002878c  mov     rbx, rax
0x18002878f  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180028793  jz      loc_1800288F6
0x180028799  mov     r14d, 2Eh ; '.'
0x18002879f  test    byte ptr [rsp+6E0h+fd.dwFileAttributes], 10h
0x1800287a4  jz      loc_1800288E0
0x1800287aa  movzx   edx, [rsp+6E0h+fd.cFileName]
0x1800287af  sub     edx, r14d
0x1800287b2  jnz     short loc_1800287C0
0x1800287b4  movzx   edx, [rsp+6E0h+fd.cFileName+2]
0x1800287b9  xor     eax, eax
0x1800287bb  movzx   ecx, ax
0x1800287be  sub     edx, ecx
0x1800287c0  test    edx, edx
0x1800287c2  jz      loc_1800288E0
0x1800287c8  movzx   edx, [rsp+6E0h+fd.cFileName]
0x1800287cd  sub     edx, r14d
0x1800287d0  jnz     short loc_1800287E8
0x1800287d2  movzx   edx, [rsp+6E0h+fd.cFileName+2]
0x1800287d7  sub     edx, r14d
0x1800287da  jnz     short loc_1800287E8
0x1800287dc  movzx   edx, [rsp+6E0h+fd.cFileName+4]
0x1800287e1  xor     eax, eax
0x1800287e3  movzx   ecx, ax
0x1800287e6  sub     edx, ecx
0x1800287e8  test    edx, edx
0x1800287ea  jz      loc_1800288E0
0x1800287f0  lea     rax, aTempstate; "TempState"
0x1800287f7  mov     r9, rsi
0x1800287fa  mov     [rsp+6E0h+var_6B8], rax
0x1800287ff  lea     r8, aSSS; "%s\\%s\\%s"
0x180028806  lea     rax, [rsp+6E0h+fd.cFileName]
0x18002880b  mov     wzStateRoot, r15; cchDest
0x18002880e  lea     this, [rbp+5E0h+wzPathToClean]; pszDest
0x180028815  mov     [rsp+6E0h+formatString], rax
0x18002881a  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002881f  mov     this, [rbp+5E8h]; callerReturnAddress
0x180028826  lea     wzStateRoot, [rsp+6E0h+fd.cFileName]
0x18002882b  mov     [rsp+6E0h+var_6B0], wzStateRoot
0x180028830  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x180028837  lea     wzStateRoot, aStringcchprint_1; "StringCchPrintfW STATE %ws file %ws"
0x18002883e  mov     [rsp+6E0h+var_6B8], rsi
0x180028843  mov     [rsp+6E0h+formatString], wzStateRoot; formatString
0x180028848  mov     r9d, eax; hr
0x18002884b  mov     edx, 0D6h; lineNumber
0x180028850  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180028855  test    eax, eax
0x180028857  js      short loc_180028868
0x180028859  lea     wzStateRoot, [rbp+5E0h+wzPathToClean]
0x180028860  mov     this, rdi; wzTempRoot
0x180028863  call    _anonymous_namespace___TempCleanup__CleanupTempRoot
0x180028868  lea     rax, aAcTemp; "AC\\Temp"
0x18002886f  mov     r9, rsi
0x180028872  mov     [rsp+6E0h+var_6B8], rax
0x180028877  lea     r8, aSSS; "%s\\%s\\%s"
0x18002887e  lea     rax, [rsp+6E0h+fd.cFileName]
0x180028883  mov     wzStateRoot, r15; cchDest
0x180028886  lea     this, [rbp+5E0h+wzPathToClean]; pszDest
0x18002888d  mov     [rsp+6E0h+formatString], rax
0x180028892  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180028897  mov     this, [rbp+5E8h]; callerReturnAddress
0x18002889e  lea     wzStateRoot, [rsp+6E0h+fd.cFileName]
0x1800288a3  mov     [rsp+6E0h+var_6B0], wzStateRoot
0x1800288a8  lea     r8, aOnecoreuapBase_13; "onecoreuap\\base\\appmodel\\statemanage"...
0x1800288af  lea     wzStateRoot, aStringcchprint_0; "StringCchPrintfW AC %ws file %ws"
0x1800288b6  mov     [rsp+6E0h+var_6B8], rsi
0x1800288bb  mov     [rsp+6E0h+formatString], wzStateRoot; formatString
0x1800288c0  mov     r9d, eax; hr
0x1800288c3  mov     edx, 0DDh; lineNumber
0x1800288c8  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800288cd  test    eax, eax
0x1800288cf  js      short loc_1800288E0
0x1800288d1  lea     wzStateRoot, [rbp+5E0h+wzPathToClean]
0x1800288d8  mov     this, rdi; wzTempRoot
0x1800288db  call    _anonymous_namespace___TempCleanup__CleanupTempRoot
0x1800288e0  lea     wzStateRoot, [rsp+6E0h+fd]; lpFindFileData
0x1800288e5  mov     this, rbx; hFindFile
0x1800288e8  call    cs:__imp_FindNextFileW
0x1800288ee  test    eax, eax
0x1800288f0  jnz     loc_18002879F
0x1800288f6  mov     this, [rbp+5E0h+var_30]
0x1800288fd  xor     this, rsp; StackCookie
0x180028900  call    __security_check_cookie
0x180028905  mov     rbx, [rsp+6E0h+arg_10]
0x18002890d  add     rsp, 6C0h
0x180028914  pop     r15
0x180028916  pop     r14
0x180028918  pop     rdi
0x180028919  pop     rsi
0x18002891a  pop     rbp
0x18002891b  retn
```
