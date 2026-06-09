# _lambda_38c5608bc4c03dfbfb86470b211a07e1_::operator()

- ea: `0x18001c6cc`
- end: `0x18001c8e9`
- name: `_lambda_38c5608bc4c03dfbfb86470b211a07e1_::operator()`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001b330`

## callees

- `0x1800059fc`
- `0x18001c2bc`
- `0x18001c448`
- `0x18001c6cc`
- `0x18001ee18`
- `0x18001f008`
- `0x18001f0c0`
- `0x18001f47c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001c789`
- `KERNEL32!GetLastError` at `0x18001c862`
- `KERNEL32!GetLastError` at `0x18001c897`
- `KERNEL32!GetLastError` at `0x18001c789`
- `KERNEL32!GetLastError` at `0x18001c862`
- `KERNEL32!GetLastError` at `0x18001c897`
- `KERNEL32!RemoveDirectoryW` at `0x18001c77a`
- `KERNEL32!RemoveDirectoryW` at `0x18001c77a`
- `KERNEL32!GetFileAttributesW` at `0x18001c837`
- `KERNEL32!GetFileAttributesW` at `0x18001c837`
- `KERNEL32!SetFileAttributesW` at `0x18001c858`
- `KERNEL32!SetFileAttributesW` at `0x18001c858`
- `KERNEL32!DeleteFileW` at `0x18001c888`
- `KERNEL32!DeleteFileW` at `0x18001c888`

## string_xrefs

- `0x18001c79e`: ` (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() delete directory failed %s %x`
- `0x18001c86b`: ` (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() SetFileAttributes failed. Error: 0x%X`
- `0x18001c8ac`: ` (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() delete file failed %s %x`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall lambda_38c5608bc4c03dfbfb86470b211a07e1_::operator()(_QWORD *a1, int a2, _QWORD *a3)
{
  _QWORD *v4; // rax
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  const WCHAR *v7; // rcx
  unsigned __int64 v8; // r8
  __int64 v9; // rcx
  const WCHAR *v10; // rax
  __int64 v11; // rdx
  _QWORD *v12; // rax
  _QWORD *v13; // rax
  _QWORD *v14; // rax
  const WCHAR *v15; // rcx
  unsigned __int64 v16; // rax
  __int64 v17; // rcx
  const WCHAR *v18; // rax
  DWORD FileAttributesW; // eax
  const WCHAR *v20; // rax
  DWORD v21; // edx
  DWORD LastError; // eax
  const WCHAR *v23; // rax
  _QWORD *v24; // rax
  _QWORD v26[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v27; // [rsp+38h] [rbp-18h]

  if ( a2 == 1 )
  {
    std::wstring::wstring(v26, *a1);
    v4 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    v5 = 0;
    if ( *((_WORD *)v4 + v27 - 1) == 92
      || !a3[2]
      || (v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3), v7 = L"\\", *(_WORD *)v6 == 92) )
    {
      v7 = &cchOriginalDestLength;
    }
    v8 = std::char_traits<unsigned short>::length(v7);
    std::wstring::append(v26, v9, v8);
    std::wstring::append(v26, a3, 0, -1);
    v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    if ( !RemoveDirectoryW(v10) )
    {
      v5 = -2147467259;
      GetLastError();
      v12 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      UnattendLogW(
        2,
        L" (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() delete directory failed %s %x",
        v12);
    }
  }
  else
  {
    if ( a2 != 2 )
      return 0;
    std::wstring::wstring(v26, *a1);
    v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    v5 = 0;
    if ( *((_WORD *)v13 + v27 - 1) == 92
      || !a3[2]
      || (v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3), v15 = L"\\", *(_WORD *)v14 == 92) )
    {
      v15 = &cchOriginalDestLength;
    }
    v16 = std::char_traits<unsigned short>::length(v15);
    std::wstring::append(v26, v17, v16);
    std::wstring::append(v26, a3, 0, -1);
    v18 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    FileAttributesW = GetFileAttributesW(v18);
    if ( FileAttributesW != -1 && (FileAttributesW & 1) != 0 )
    {
      v20 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      if ( !SetFileAttributesW(v20, v21) )
      {
        LastError = GetLastError();
        UnattendLogW(
          2,
          L" (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() SetFileAttributes failed. Error: 0x%X",
          LastError);
      }
    }
    v23 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
    if ( !DeleteFileW(v23) )
    {
      v5 = -2147467259;
      GetLastError();
      v24 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v26);
      UnattendLogW(
        2,
        L" (WinRE)winREMoveDirectory::<lambda_38c5608bc4c03dfbfb86470b211a07e1>::operator ()() delete file failed %s %x",
        v24);
    }
  }
  std::wstring::~wstring((__int64)v26, v11);
  return v5;
}

```

## disassembly

```asm
0x18001c6cc  push    rbp
0x18001c6ce  mov     rbp, rsp
0x18001c6d1  sub     rsp, 50h
0x18001c6d5  mov     [rbp+var_30], 0FFFFFFFFFFFFFFFEh
0x18001c6dd  mov     [rsp+50h+arg_8], rbx
0x18001c6e2  mov     [rsp+50h+arg_18], rdi
0x18001c6e7  mov     rax, cs:__security_cookie
0x18001c6ee  xor     rax, rsp
0x18001c6f1  mov     [rbp+var_8], rax
0x18001c6f5  mov     rdi, r8
0x18001c6f8  cmp     edx, 1
0x18001c6fb  jnz     loc_18001C7B5
0x18001c701  mov     rdx, [rcx]
0x18001c704  lea     rcx, [rbp+var_28]
0x18001c708  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c70d  nop
0x18001c70e  lea     rcx, [rbp+var_28]
0x18001c712  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c717  xor     ebx, ebx
0x18001c719  mov     rcx, [rbp+var_18]
0x18001c71d  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18001c723  jz      short loc_18001C740
0x18001c725  cmp     [rdi+10h], rbx
0x18001c729  jz      short loc_18001C740
0x18001c72b  mov     rcx, rdi
0x18001c72e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c733  cmp     word ptr [rax], 5Ch ; '\'
0x18001c737  lea     rcx, pszSrc; "\\"
0x18001c73e  jnz     short loc_18001C747
0x18001c740  lea     rcx, cchOriginalDestLength
0x18001c747  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001c74c  mov     r8, rax
0x18001c74f  mov     rdx, rcx
0x18001c752  lea     rcx, [rbp+var_28]
0x18001c756  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001c75b  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c75f  xor     r8d, r8d
0x18001c762  mov     rdx, rdi
0x18001c765  lea     rcx, [rbp+var_28]
0x18001c769  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c76e  lea     rcx, [rbp+var_28]
0x18001c772  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c777  mov     rcx, rax; lpPathName
0x18001c77a  call    cs:__imp_RemoveDirectoryW
0x18001c780  test    eax, eax
0x18001c782  jnz     short loc_18001C7B0
0x18001c784  mov     ebx, 80004005h
0x18001c789  call    cs:__imp_GetLastError
0x18001c78f  mov     r9d, eax
0x18001c792  lea     rcx, [rbp+var_28]
0x18001c796  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c79b  mov     r8, rax
0x18001c79e  lea     rdx, aWinreWinremove_3; " (WinRE)winREMoveDirectory::<lambda_38c"...
0x18001c7a5  mov     ecx, 2
0x18001c7aa  call    UnattendLogW
0x18001c7af  nop
0x18001c7b0  jmp     loc_18001C8BE
0x18001c7b5  cmp     edx, 2
0x18001c7b8  jnz     loc_18001C8C9
0x18001c7be  mov     rdx, [rcx]
0x18001c7c1  lea     rcx, [rbp+var_28]
0x18001c7c5  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001c7ca  nop
0x18001c7cb  lea     rcx, [rbp+var_28]
0x18001c7cf  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c7d4  xor     ebx, ebx
0x18001c7d6  mov     rcx, [rbp+var_18]
0x18001c7da  cmp     word ptr [rax+rcx*2-2], 5Ch ; '\'
0x18001c7e0  jz      short loc_18001C7FD
0x18001c7e2  cmp     [rdi+10h], rbx
0x18001c7e6  jz      short loc_18001C7FD
0x18001c7e8  mov     rcx, rdi
0x18001c7eb  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c7f0  cmp     word ptr [rax], 5Ch ; '\'
0x18001c7f4  lea     rcx, pszSrc; "\\"
0x18001c7fb  jnz     short loc_18001C804
0x18001c7fd  lea     rcx, cchOriginalDestLength
0x18001c804  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001c809  mov     r8, rax
0x18001c80c  mov     rdx, rcx
0x18001c80f  lea     rcx, [rbp+var_28]
0x18001c813  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001c818  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001c81c  xor     r8d, r8d
0x18001c81f  mov     rdx, rdi
0x18001c822  lea     rcx, [rbp+var_28]
0x18001c826  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001c82b  lea     rcx, [rbp+var_28]
0x18001c82f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c834  mov     rcx, rax; lpFileName
0x18001c837  call    cs:__imp_GetFileAttributesW
0x18001c83d  mov     edx, eax
0x18001c83f  cmp     eax, 0FFFFFFFFh
0x18001c842  jz      short loc_18001C87C
0x18001c844  test    dl, 1
0x18001c847  jz      short loc_18001C87C
0x18001c849  and     edx, 0FFFFFFFEh
0x18001c84c  lea     rcx, [rbp+var_28]
0x18001c850  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c855  mov     rcx, rax; lpFileName
0x18001c858  call    cs:__imp_SetFileAttributesW
0x18001c85e  test    eax, eax
0x18001c860  jnz     short loc_18001C87C
0x18001c862  call    cs:__imp_GetLastError
0x18001c868  mov     r8d, eax
0x18001c86b  lea     rdx, aWinreWinremove_1; " (WinRE)winREMoveDirectory::<lambda_38c"...
0x18001c872  mov     ecx, 2
0x18001c877  call    UnattendLogW
0x18001c87c  lea     rcx, [rbp+var_28]
0x18001c880  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c885  mov     rcx, rax; lpFileName
0x18001c888  call    cs:__imp_DeleteFileW
0x18001c88e  test    eax, eax
0x18001c890  jnz     short loc_18001C8BE
0x18001c892  mov     ebx, 80004005h
0x18001c897  call    cs:__imp_GetLastError
0x18001c89d  mov     r9d, eax
0x18001c8a0  lea     rcx, [rbp+var_28]
0x18001c8a4  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001c8a9  mov     r8, rax
0x18001c8ac  lea     rdx, aWinreWinremove_6; " (WinRE)winREMoveDirectory::<lambda_38c"...
0x18001c8b3  mov     ecx, 2
0x18001c8b8  call    UnattendLogW
0x18001c8bd  nop
0x18001c8be  lea     rcx, [rbp+var_28]
0x18001c8c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001c8c7  jmp     short loc_18001C8CB
0x18001c8c9  xor     ebx, ebx
0x18001c8cb  mov     eax, ebx
0x18001c8cd  mov     rcx, [rbp+var_8]
0x18001c8d1  xor     rcx, rsp; StackCookie
0x18001c8d4  call    __security_check_cookie
0x18001c8d9  mov     rbx, [rsp+50h+arg_8]
0x18001c8de  mov     rdi, [rsp+50h+arg_18]
0x18001c8e3  add     rsp, 50h
0x18001c8e7  pop     rbp
0x18001c8e8  retn
```
