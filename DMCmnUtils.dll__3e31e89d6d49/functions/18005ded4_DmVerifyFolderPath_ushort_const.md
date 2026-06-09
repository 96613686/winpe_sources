# DmVerifyFolderPath(ushort const *)

- ea: `0x18005ded4`
- end: `0x18005e10c`
- name: `?DmVerifyFolderPath@@YAPEAXPEBG@Z`
- size: `568`
- prototype: `void *__fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005dab0`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x18005b73c`
- `0x18005bb6c`
- `0x18005bbf0`
- `0x18005d780`
- `0x18005d7b8`
- `0x18005dcf8`
- `0x18005ded4`
- `0x18005e19c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005df2a`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x18005df2a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e0ae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e036`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e0ae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e074`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18005e074`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005e01f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x18005e01f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18005df5e`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindNextComponentW` at `0x18005df5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1 #try_helpers=1
__int64 __fastcall DmVerifyFolderPath(const unsigned __int16 *a1)
{
  int v2; // ebx
  WCHAR *NextComponentW; // rsi
  __int64 FileW; // rdi
  __int64 v6; // rax
  const WCHAR *v7; // rax
  const WCHAR *v8; // rax
  const unsigned __int16 *v9; // rax
  _BYTE v10[32]; // [rsp+48h] [rbp-2A0h] BYREF
  _BYTE v11[32]; // [rsp+68h] [rbp-280h] BYREF
  _BYTE v12[40]; // [rsp+88h] [rbp-260h] BYREF
  wchar_t pszPath[264]; // [rsp+B0h] [rbp-238h] BYREF

  v2 = 0;
  memset_0(pszPath, 0, 0x20Au);
  _o_wcscpy_s(pszPath, 261, a1);
  NextComponentW = pszPath;
  FileW = -1;
  if ( !a1 )
    return -1;
  while ( NextComponentW )
  {
    NextComponentW = PathFindNextComponentW(NextComponentW);
    if ( NextComponentW )
    {
      if ( NextComponentW >= &pszPath[wcsnlen_s(pszPath, 0x104u)] )
      {
        v6 = std::wstring::wstring(v11, a1);
        v2 |= 2u;
      }
      else
      {
        v6 = std::wstring::wstring(v12, pszPath, NextComponentW - pszPath);
        v2 |= 1u;
      }
      std::wstring::wstring(v10, v6);
      if ( (v2 & 2) != 0 )
      {
        v2 &= ~2u;
        std::wstring::_Tidy_deallocate(v11);
      }
      if ( (v2 & 1) != 0 )
      {
        v2 &= ~1u;
        std::wstring::_Tidy_deallocate(v12);
      }
      v7 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
      if ( PathFileExistsW(v7) )
      {
        CloseHandle((HANDLE)FileW);
        v8 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
        FileW = (__int64)CreateFileW(v8, 0x80000000, 3u, 0, 3u, 0x2000000u, 0);
        if ( FileW == -1 )
        {
          std::wstring::_Tidy_deallocate(v10);
          return -1;
        }
        v9 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v10);
        if ( (int)DmVerifyFilePath(v9, (HANDLE)FileW) < 0 )
        {
          CloseHandle((HANDLE)FileW);
          std::wstring::_Tidy_deallocate(v10);
          return -1;
        }
      }
      std::wstring::_Tidy_deallocate(v10);
    }
  }
  return FileW;
}

```

## disassembly

```asm
0x18005ded4  mov     [rsp+arg_8], rbx
0x18005ded9  mov     [rsp+arg_10], rsi
0x18005dede  push    rdi
0x18005dedf  push    r14
0x18005dee1  push    r15
0x18005dee3  sub     rsp, 2D0h
0x18005deea  mov     rax, cs:__security_cookie
0x18005def1  xor     rax, rsp
0x18005def4  mov     [rsp+2E8h+var_28], rax
0x18005defc  mov     r14, rcx
0x18005deff  xor     ebx, ebx
0x18005df01  mov     dword ptr [rsp+2E8h+var_2A8], ebx
0x18005df05  xor     edx, edx; Val
0x18005df07  mov     r8d, 20Ah; Size
0x18005df0d  lea     rcx, [rsp+2E8h+pszPath]; void *
0x18005df15  call    memset_0
0x18005df1a  mov     r8, r14
0x18005df1d  mov     edx, 105h
0x18005df22  lea     rcx, [rsp+2E8h+pszPath]
0x18005df2a  call    cs:__imp__o_wcscpy_s
0x18005df31  nop     dword ptr [rax+rax+00h]
0x18005df36  lea     rsi, [rsp+2E8h+pszPath]
0x18005df3e  or      r15, 0FFFFFFFFFFFFFFFFh
0x18005df42  mov     rdi, r15
0x18005df45  test    r14, r14
0x18005df48  jnz     short loc_18005DF52
0x18005df4a  mov     rax, r15
0x18005df4d  jmp     loc_18005E0E2
0x18005df52  test    rsi, rsi
0x18005df55  jz      loc_18005E0D8
0x18005df5b  mov     rcx, rsi; pszPath
0x18005df5e  call    cs:__imp_PathFindNextComponentW
0x18005df65  nop     dword ptr [rax+rax+00h]
0x18005df6a  mov     rsi, rax
0x18005df6d  test    rax, rax
0x18005df70  jz      short loc_18005DF52
0x18005df72  mov     edx, 104h; MaxCount
0x18005df77  lea     rcx, [rsp+2E8h+pszPath]; Source
0x18005df7f  call    wcsnlen_s
0x18005df84  lea     rcx, [rsp+2E8h+pszPath]
0x18005df8c  lea     rcx, [rcx+rax*2]
0x18005df90  cmp     rsi, rcx
0x18005df93  jnb     short loc_18005DFC1
0x18005df95  lea     rax, [rsp+2E8h+pszPath]
0x18005df9d  mov     r8, rsi
0x18005dfa0  sub     r8, rax
0x18005dfa3  sar     r8, 1
0x18005dfa6  lea     rdx, [rsp+2E8h+pszPath]
0x18005dfae  lea     rcx, [rsp+2E8h+var_260]
0x18005dfb6  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG_K@Z; std::wstring::wstring(ushort const * const,unsigned __int64)
0x18005dfbb  nop
0x18005dfbc  or      ebx, 1
0x18005dfbf  jmp     short loc_18005DFD1
0x18005dfc1  mov     rdx, r14
0x18005dfc4  lea     rcx, [rsp+2E8h+var_280]
0x18005dfc9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18005dfce  or      ebx, 2
0x18005dfd1  mov     dword ptr [rsp+2E8h+var_2A8], ebx
0x18005dfd5  mov     rdx, rax
0x18005dfd8  lea     rcx, [rsp+2E8h+var_2A0]
0x18005dfdd  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x18005dfe2  test    bl, 2
0x18005dfe5  jz      short loc_18005DFF9
0x18005dfe7  and     ebx, 0FFFFFFFDh
0x18005dfea  mov     dword ptr [rsp+2E8h+var_2A8], ebx
0x18005dfee  lea     rcx, [rsp+2E8h+var_280]
0x18005dff3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005dff8  nop
0x18005dff9  test    bl, 1
0x18005dffc  jz      short loc_18005E012
0x18005dffe  and     ebx, 0FFFFFFFEh
0x18005e001  mov     dword ptr [rsp+2E8h+var_2A8], ebx
0x18005e005  lea     rcx, [rsp+2E8h+var_260]
0x18005e00d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e012  lea     rcx, [rsp+2E8h+var_2A0]
0x18005e017  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005e01c  mov     rcx, rax; pszPath
0x18005e01f  call    cs:__imp_PathFileExistsW
0x18005e026  nop     dword ptr [rax+rax+00h]
0x18005e02b  test    eax, eax
0x18005e02d  jz      loc_18005E0C9
0x18005e033  mov     rcx, rdi; hObject
0x18005e036  call    cs:__imp_CloseHandle
0x18005e03d  nop     dword ptr [rax+rax+00h]
0x18005e042  lea     rcx, [rsp+2E8h+var_2A0]
0x18005e047  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005e04c  mov     rcx, rax; lpFileName
0x18005e04f  mov     [rsp+2E8h+hTemplateFile], 0; hTemplateFile
0x18005e058  mov     [rsp+2E8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18005e060  mov     [rsp+2E8h+dwCreationDisposition], 3; dwCreationDisposition
0x18005e068  xor     r9d, r9d; lpSecurityAttributes
0x18005e06b  mov     edx, 80000000h; dwDesiredAccess
0x18005e070  lea     r8d, [r9+3]; dwShareMode
0x18005e074  call    cs:__imp_CreateFileW
0x18005e07b  nop     dword ptr [rax+rax+00h]
0x18005e080  mov     rdi, rax
0x18005e083  lea     rcx, [rsp+2E8h+var_2A0]
0x18005e088  cmp     rax, r15
0x18005e08b  jnz     short loc_18005E097
0x18005e08d  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e092  mov     rax, r15
0x18005e095  jmp     short loc_18005E0E2
0x18005e097  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18005e09c  mov     rcx, rax; unsigned __int16 *
0x18005e09f  mov     rdx, rdi; hFile
0x18005e0a2  call    ?DmVerifyFilePath@@YAJPEBGPEAX@Z; DmVerifyFilePath(ushort const *,void *)
0x18005e0a7  test    eax, eax
0x18005e0a9  jns     short loc_18005E0C9
0x18005e0ab  mov     rcx, rdi; hObject
0x18005e0ae  call    cs:__imp_CloseHandle
0x18005e0b5  nop     dword ptr [rax+rax+00h]
0x18005e0ba  lea     rcx, [rsp+2E8h+var_2A0]
0x18005e0bf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e0c4  mov     rax, r15
0x18005e0c7  jmp     short loc_18005E0E2
0x18005e0c9  lea     rcx, [rsp+2E8h+var_2A0]
0x18005e0ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18005e0d3  jmp     loc_18005DF52
0x18005e0d8  jmp     short loc_18005E0DF
0x18005e0da  mov     rdi, [rsp+2E8h+var_2A8]
0x18005e0df  mov     rax, rdi
0x18005e0e2  mov     rcx, [rsp+2E8h+var_28]
0x18005e0ea  xor     rcx, rsp; StackCookie
0x18005e0ed  call    __security_check_cookie
0x18005e0f2  lea     r11, [rsp+2E8h+var_18]
0x18005e0fa  mov     rbx, [r11+28h]
0x18005e0fe  mov     rsi, [r11+30h]
0x18005e102  mov     rsp, r11
0x18005e105  pop     r15
0x18005e107  pop     r14
0x18005e109  pop     rdi
0x18005e10a  retn
```
