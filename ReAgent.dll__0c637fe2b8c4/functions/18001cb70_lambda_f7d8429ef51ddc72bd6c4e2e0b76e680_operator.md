# _lambda_f7d8429ef51ddc72bd6c4e2e0b76e680_::operator()

- ea: `0x18001cb70`
- end: `0x18001cceb`
- name: `_lambda_f7d8429ef51ddc72bd6c4e2e0b76e680_::operator()`
- size: `379`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18001bcfc`

## callees

- `0x1800059fc`
- `0x18001c2bc`
- `0x18001c448`
- `0x18001cb70`
- `0x18001ee18`
- `0x18001f008`
- `0x18001f0c0`
- `0x18001f47c`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetFileSizeEx` at `0x18001cc6f`
- `KERNEL32!GetFileSizeEx` at `0x18001cc6f`
- `KERNEL32!CreateFileW` at `0x18001cc4f`
- `KERNEL32!CreateFileW` at `0x18001cc4f`
- `KERNEL32!CloseHandle` at `0x18001cc9f`
- `KERNEL32!CloseHandle` at `0x18001cc9f`

## string_xrefs

- `0x18001cc86`: ` (WinRE)winReCheckDirectorySize::<lambda_f7d8429ef51ddc72bd6c4e2e0b76e680>::operator ()() Get file size failed`
- `0x18001cca7`: ` (WinRE)winReCheckDirectorySize::<lambda_f7d8429ef51ddc72bd6c4e2e0b76e680>::operator ()() File open to check size failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall lambda_f7d8429ef51ddc72bd6c4e2e0b76e680_::operator()(__int64 a1, int a2, _QWORD *a3)
{
  unsigned int v5; // ebx
  _QWORD *v6; // rax
  _QWORD *v7; // rax
  const WCHAR *v8; // rcx
  unsigned __int64 v9; // r8
  __int64 v10; // rcx
  const WCHAR *v11; // rax
  HANDLE FileW; // rax
  void *v13; // rdi
  __int64 v14; // rdx
  union _LARGE_INTEGER FileSize; // [rsp+48h] [rbp-40h] BYREF
  _QWORD v17[4]; // [rsp+50h] [rbp-38h] BYREF

  v5 = 0;
  if ( a2 == 2 )
  {
    std::wstring::wstring(v17, *(_QWORD *)(a1 + 8));
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    if ( *((_WORD *)v6 + v17[2] - 1) == 92
      || !a3[2]
      || (v7 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a3), v8 = L"\\", *(_WORD *)v7 == 92) )
    {
      v8 = &cchOriginalDestLength;
    }
    v9 = std::char_traits<unsigned short>::length(v8);
    std::wstring::append(v17, v10, v9);
    std::wstring::append(v17, a3, 0, -1);
    v11 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v17);
    FileW = CreateFileW(v11, 0x80000000, 0, 0, 3u, 0x80u, 0);
    v13 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      UnattendLogW(
        2,
        L" (WinRE)winReCheckDirectorySize::<lambda_f7d8429ef51ddc72bd6c4e2e0b76e680>::operator ()() File open to check size failed");
      v5 = -2147467259;
    }
    else
    {
      FileSize.QuadPart = 0;
      if ( GetFileSizeEx(FileW, &FileSize) )
      {
        **(_QWORD **)a1 += FileSize.QuadPart;
      }
      else
      {
        UnattendLogW(
          2,
          L" (WinRE)winReCheckDirectorySize::<lambda_f7d8429ef51ddc72bd6c4e2e0b76e680>::operator ()() Get file size failed");
        v5 = -2147467259;
      }
      CloseHandle(v13);
    }
    std::wstring::~wstring((__int64)v17, v14);
  }
  return v5;
}

```

## disassembly

```asm
0x18001cb70  mov     r11, rsp
0x18001cb73  push    rdi
0x18001cb74  sub     rsp, 80h
0x18001cb7b  mov     qword ptr [r11-48h], 0FFFFFFFFFFFFFFFEh
0x18001cb83  mov     [r11+10h], rbx
0x18001cb87  mov     [r11+20h], rsi
0x18001cb8b  mov     rax, cs:__security_cookie
0x18001cb92  xor     rax, rsp
0x18001cb95  mov     [rsp+88h+var_18], rax
0x18001cb9a  mov     rdi, r8
0x18001cb9d  mov     rsi, rcx
0x18001cba0  xor     ebx, ebx
0x18001cba2  cmp     edx, 2
0x18001cba5  jnz     loc_18001CCC7
0x18001cbab  mov     rdx, [rcx+8]
0x18001cbaf  lea     rcx, [r11-38h]
0x18001cbb3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18001cbb8  nop
0x18001cbb9  lea     rcx, [rsp+88h+var_38]
0x18001cbbe  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cbc3  mov     rdx, rax
0x18001cbc6  mov     rax, [rsp+88h+var_28]
0x18001cbcb  cmp     word ptr [rdx+rax*2-2], 5Ch ; '\'
0x18001cbd1  jz      short loc_18001CBEE
0x18001cbd3  cmp     [rdi+10h], rbx
0x18001cbd7  jz      short loc_18001CBEE
0x18001cbd9  mov     rcx, rdi
0x18001cbdc  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cbe1  cmp     word ptr [rax], 5Ch ; '\'
0x18001cbe5  lea     rcx, pszSrc; "\\"
0x18001cbec  jnz     short loc_18001CBF5
0x18001cbee  lea     rcx, cchOriginalDestLength
0x18001cbf5  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x18001cbfa  mov     r8, rax
0x18001cbfd  mov     rdx, rcx
0x18001cc00  lea     rcx, [rsp+88h+var_38]
0x18001cc05  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x18001cc0a  or      r9, 0FFFFFFFFFFFFFFFFh
0x18001cc0e  xor     r8d, r8d
0x18001cc11  mov     rdx, rdi
0x18001cc14  lea     rcx, [rsp+88h+var_38]
0x18001cc19  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x18001cc1e  lea     rcx, [rsp+88h+var_38]
0x18001cc23  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001cc28  mov     rcx, rax; lpFileName
0x18001cc2b  mov     [rsp+88h+hTemplateFile], 0; hTemplateFile
0x18001cc34  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001cc3c  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x18001cc44  xor     r9d, r9d; lpSecurityAttributes
0x18001cc47  xor     r8d, r8d; dwShareMode
0x18001cc4a  mov     edx, 80000000h; dwDesiredAccess
0x18001cc4f  call    cs:__imp_CreateFileW
0x18001cc55  mov     rdi, rax
0x18001cc58  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001cc5c  jz      short loc_18001CCA7
0x18001cc5e  mov     qword ptr [rsp+88h+FileSize], 0
0x18001cc67  lea     rdx, [rsp+88h+FileSize]; lpFileSize
0x18001cc6c  mov     rcx, rax; hFile
0x18001cc6f  call    cs:__imp_GetFileSizeEx
0x18001cc75  test    eax, eax
0x18001cc77  jz      short loc_18001CC86
0x18001cc79  mov     rcx, [rsi]
0x18001cc7c  mov     rax, qword ptr [rsp+88h+FileSize]
0x18001cc81  add     [rcx], rax
0x18001cc84  jmp     short loc_18001CC9C
0x18001cc86  lea     rdx, aWinreWinrechec; " (WinRE)winReCheckDirectorySize::<lambd"...
0x18001cc8d  mov     ecx, 2
0x18001cc92  call    UnattendLogW
0x18001cc97  mov     ebx, 80004005h
0x18001cc9c  mov     rcx, rdi; hObject
0x18001cc9f  call    cs:__imp_CloseHandle
0x18001cca5  jmp     short loc_18001CCBD
0x18001cca7  lea     rdx, aWinreWinrechec_2; " (WinRE)winReCheckDirectorySize::<lambd"...
0x18001ccae  mov     ecx, 2
0x18001ccb3  call    UnattendLogW
0x18001ccb8  mov     ebx, 80004005h
0x18001ccbd  lea     rcx, [rsp+88h+var_38]
0x18001ccc2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18001ccc7  mov     eax, ebx
0x18001ccc9  mov     rcx, [rsp+88h+var_18]
0x18001ccce  xor     rcx, rsp; StackCookie
0x18001ccd1  call    __security_check_cookie
0x18001ccd6  lea     r11, [rsp+88h+var_8]
0x18001ccde  mov     rbx, [r11+18h]
0x18001cce2  mov     rsi, [r11+28h]
0x18001cce6  mov     rsp, r11
0x18001cce9  pop     rdi
0x18001ccea  retn
```
