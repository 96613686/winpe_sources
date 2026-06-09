# DeleteFileViaDisposition(ushort const *)

- ea: `0x140045c60`
- end: `0x140045e15`
- name: `?DeleteFileViaDisposition@@YAKPEBG@Z`
- size: `437`
- prototype: `__int64 __fastcall(PCNZWCH lpString1)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x140049910`

## callees

- `0x140003611`
- `0x140004170`
- `0x140004348`
- `0x1400085b4`
- `0x140017af0`
- `0x140045c60`
- `0x140113220`

## import_xrefs

- `KERNEL32!CreateFileW` at `0x140045cbf`
- `KERNEL32!CreateFileW` at `0x140045cbf`
- `KERNEL32!CloseHandle` at `0x140045de8`
- `KERNEL32!CloseHandle` at `0x140045de8`
- `KERNEL32!SetFileInformationByHandle` at `0x140045ddd`
- `KERNEL32!SetFileInformationByHandle` at `0x140045ddd`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140045ce3`
- `KERNEL32!GetFinalPathNameByHandleW` at `0x140045ce3`
- `KERNEL32!CompareStringW` at `0x140045d14`
- `KERNEL32!CompareStringW` at `0x140045d4a`
- `KERNEL32!CompareStringW` at `0x140045d78`
- `KERNEL32!CompareStringW` at `0x140045d14`
- `KERNEL32!CompareStringW` at `0x140045d4a`
- `KERNEL32!CompareStringW` at `0x140045d78`

## string_xrefs

- `0x140045db0`: `: found to have an unexpected reparse point`
- `0x140045d8f`: `Unable to delete `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall DeleteFileViaDisposition(PCNZWCH lpString1)
{
  unsigned int v2; // edi
  HANDLE FileW; // rax
  void *v4; // rbx
  __int64 v5; // rax
  __int64 v6; // rax
  __int64 v7; // rax
  __int64 v8; // rax
  char FileInformation[16]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR szFilePath; // [rsp+50h] [rbp-428h] BYREF
  WCHAR String2[516]; // [rsp+58h] [rbp-420h] BYREF

  v2 = 0;
  memset_0(&szFilePath, 0, 0x410u);
  FileW = CreateFileW(lpString1, 0x10000u, 5u, 0, 3u, 0x200080u, 0);
  v4 = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( !GetFinalPathNameByHandleW(FileW, &szFilePath, 0x208u, 0)
      || CompareStringW(0x400u, 0x1001u, lpString1, -1, &szFilePath, -1) == 2
      || CompareStringW(0x400u, 0x1001u, L"\\\\?\\", 4, &szFilePath, 4) == 2
      && CompareStringW(0x400u, 0x1001u, lpString1, -1, String2, -1) == 2 )
    {
      FileInformation[0] = 1;
      v2 = SetFileInformationByHandle(v4, FileDispositionInfo, FileInformation, 1u);
      CloseHandle(v4);
    }
    else
    {
      v5 = CSmartPtr<mlib::handle_ostreamT<unsigned short,std::char_traits<unsigned short>>>::operator->(&mlib::stdoutw);
      v6 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v5 + 240, L"Unable to delete ");
      v7 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(v6, lpString1);
      v8 = std::operator<<<unsigned short,std::char_traits<unsigned short>>(
             v7,
             ": found to have an unexpected reparse point");
      std::endl(v8);
    }
  }
  return v2;
}

```

## disassembly

```asm
0x140045c60  mov     [rsp+arg_8], rbx
0x140045c65  mov     [rsp+arg_10], rsi
0x140045c6a  push    rdi
0x140045c6b  sub     rsp, 470h
0x140045c72  mov     rax, cs:__security_cookie
0x140045c79  xor     rax, rsp
0x140045c7c  mov     [rsp+478h+var_18], rax
0x140045c84  mov     rsi, rcx
0x140045c87  xor     edx, edx; Val
0x140045c89  lea     rcx, [rsp+478h+szFilePath]; void *
0x140045c8e  mov     r8d, 410h; Size
0x140045c94  xor     edi, edi
0x140045c96  call    memset_0
0x140045c9b  mov     [rsp+478h+hTemplateFile], rdi; hTemplateFile
0x140045ca0  lea     r8d, [rdi+5]; dwShareMode
0x140045ca4  mov     [rsp+478h+dwFlagsAndAttributes], 200080h; dwFlagsAndAttributes
0x140045cac  xor     r9d, r9d; lpSecurityAttributes
0x140045caf  mov     edx, 10000h; dwDesiredAccess
0x140045cb4  mov     [rsp+478h+dwCreationDisposition], 3; dwCreationDisposition
0x140045cbc  mov     rcx, rsi; lpFileName
0x140045cbf  call    cs:__imp_CreateFileW
0x140045cc5  mov     rbx, rax
0x140045cc8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x140045ccc  jz      loc_140045DEE
0x140045cd2  xor     r9d, r9d; dwFlags
0x140045cd5  lea     rdx, [rsp+478h+szFilePath]; lpszFilePath
0x140045cda  mov     r8d, 208h; cchFilePath
0x140045ce0  mov     rcx, rax; hFile
0x140045ce3  call    cs:__imp_GetFinalPathNameByHandleW
0x140045ce9  test    eax, eax
0x140045ceb  jz      loc_140045DC6
0x140045cf1  lea     rax, [rsp+478h+szFilePath]
0x140045cf6  mov     [rsp+478h+dwFlagsAndAttributes], 0FFFFFFFFh; cchCount2
0x140045cfe  or      r9d, 0FFFFFFFFh; cchCount1
0x140045d02  mov     qword ptr [rsp+478h+dwCreationDisposition], rax; lpString2
0x140045d07  mov     r8, rsi; lpString1
0x140045d0a  mov     edx, 1001h; dwCmpFlags
0x140045d0f  mov     ecx, 400h; Locale
0x140045d14  call    cs:__imp_CompareStringW
0x140045d1a  cmp     eax, 2
0x140045d1d  jz      loc_140045DC6
0x140045d23  lea     rax, [rsp+478h+szFilePath]
0x140045d28  mov     [rsp+478h+dwFlagsAndAttributes], 4; cchCount2
0x140045d30  lea     r9d, [rdi+4]; cchCount1
0x140045d34  mov     qword ptr [rsp+478h+dwCreationDisposition], rax; lpString2
0x140045d39  lea     r8, String1; "\\\\?\\"
0x140045d40  mov     edx, 1001h; dwCmpFlags
0x140045d45  mov     ecx, 400h; Locale
0x140045d4a  call    cs:__imp_CompareStringW
0x140045d50  cmp     eax, 2
0x140045d53  jnz     short loc_140045D83
0x140045d55  lea     rax, [rsp+478h+String2]
0x140045d5a  mov     [rsp+478h+dwFlagsAndAttributes], 0FFFFFFFFh; cchCount2
0x140045d62  or      r9d, 0FFFFFFFFh; cchCount1
0x140045d66  mov     qword ptr [rsp+478h+dwCreationDisposition], rax; lpString2
0x140045d6b  mov     r8, rsi; lpString1
0x140045d6e  mov     edx, 1001h; dwCmpFlags
0x140045d73  mov     ecx, 400h; Locale
0x140045d78  call    cs:__imp_CompareStringW
0x140045d7e  cmp     eax, 2
0x140045d81  jz      short loc_140045DC6
0x140045d83  lea     rcx, ?stdoutw@mlib@@3V?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@A; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>> mlib::stdoutw
0x140045d8a  call    ??C?$CSmartPtr@V?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@@@QEBAPEAV?$handle_ostreamT@GU?$char_traits@G@std@@@mlib@@XZ; CSmartPtr<mlib::handle_ostreamT<ushort,std::char_traits<ushort>>>::operator->(void)
0x140045d8f  lea     rdx, aUnableToDelete; "Unable to delete "
0x140045d96  lea     rcx, [rax+0F0h]
0x140045d9d  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140045da2  mov     rcx, rax
0x140045da5  mov     rdx, rsi
0x140045da8  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBG@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,ushort const *)
0x140045dad  mov     rcx, rax
0x140045db0  lea     rdx, aFoundToHaveAnU; ": found to have an unexpected reparse p"...
0x140045db7  call    ??$?6GU?$char_traits@G@std@@@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@0@AEAV10@PEBD@Z; std::operator<<<ushort,std::char_traits<ushort>>(std::basic_ostream<ushort> &,char const *)
0x140045dbc  mov     rcx, rax
0x140045dbf  call    ?endl@std@@YAAEAV?$basic_ostream@GU?$char_traits@G@std@@@1@AEAV21@@Z; std::endl(std::basic_ostream<ushort> &)
0x140045dc4  jmp     short loc_140045DEE
0x140045dc6  mov     r9d, 1; dwBufferSize
0x140045dcc  mov     [rsp+478h+FileInformation], 1
0x140045dd1  lea     r8, [rsp+478h+FileInformation]; lpFileInformation
0x140045dd6  mov     rcx, rbx; hFile
0x140045dd9  lea     edx, [r9+3]; FileInformationClass
0x140045ddd  call    cs:__imp_SetFileInformationByHandle
0x140045de3  mov     rcx, rbx; hObject
0x140045de6  mov     edi, eax
0x140045de8  call    cs:__imp_CloseHandle
0x140045dee  mov     eax, edi
0x140045df0  mov     rcx, [rsp+478h+var_18]
0x140045df8  xor     rcx, rsp; StackCookie
0x140045dfb  call    __security_check_cookie
0x140045e00  lea     r11, [rsp+478h+var_8]
0x140045e08  mov     rbx, [r11+18h]
0x140045e0c  mov     rsi, [r11+20h]
0x140045e10  mov     rsp, r11
0x140045e13  pop     rdi
0x140045e14  retn
```
