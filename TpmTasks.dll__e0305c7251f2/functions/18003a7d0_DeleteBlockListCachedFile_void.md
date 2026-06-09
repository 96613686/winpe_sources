# DeleteBlockListCachedFile(void)

- ea: `0x18003a7d0`
- end: `0x18003a8a0`
- name: `?DeleteBlockListCachedFile@@YAXXZ`
- size: `208`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x18003a8a8`

## callees

- `0x1800078b0`
- `0x18000bc54`
- `0x18000bcc4`
- `0x180023634`
- `0x18002386c`
- `0x18003a7d0`
- `0x18003c0b8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a87c`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003a87c`
- `SHELL32!SHGetKnownFolderPath` at `0x18003a818`
- `SHELL32!SHGetKnownFolderPath` at `0x18003a818`

## string_xrefs

- `0x18003a845`: `\Microsoft\Windows\OneSettings\DBUpdateBL.json`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void DeleteBlockListCachedFile(void)
{
  __int64 v0; // r8
  __int64 v1; // rax
  const WCHAR *v2; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-38h] BYREF
  _OWORD v4[2]; // [rsp+28h] [rbp-30h] BYREF

  v4[0] = 0;
  v4[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v4[0]) = 0;
  ppszPath = 0;
  if ( SHGetKnownFolderPath(&FOLDERID_ProgramData, 0, 0, &ppszPath) >= 0 )
  {
    v0 = -1;
    do
      ++v0;
    while ( ppszPath[v0] );
    std::wstring::_Assign<unsigned short>(v4, ppszPath);
    std::wstring::_Append<unsigned short>(v4, L"\\Microsoft\\Windows\\OneSettings\\DBUpdateBL.json", 46);
    v1 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
    SBServicingLogMessage((wchar_t *)L"Deleting %s\n", v1);
    v2 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v4);
    DeleteFileW(v2);
  }
  std::wstring::_Tidy_deallocate(v4);
}

```

## disassembly

```asm
0x18003a7d0  push    rbx
0x18003a7d2  sub     rsp, 50h
0x18003a7d6  mov     rax, cs:__security_cookie
0x18003a7dd  xor     rax, rsp
0x18003a7e0  mov     [rsp+58h+var_10], rax
0x18003a7e5  xorps   xmm0, xmm0
0x18003a7e8  movups  [rsp+58h+var_30], xmm0
0x18003a7ed  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18003a7f5  movdqu  [rsp+58h+var_20], xmm1
0x18003a7fb  xor     ebx, ebx
0x18003a7fd  mov     word ptr [rsp+58h+var_30], bx
0x18003a802  mov     [rsp+58h+ppszPath], rbx
0x18003a807  lea     r9, [rsp+58h+ppszPath]; ppszPath
0x18003a80c  xor     r8d, r8d; hToken
0x18003a80f  xor     edx, edx; dwFlags
0x18003a811  lea     rcx, FOLDERID_ProgramData; rfid
0x18003a818  call    cs:__imp_SHGetKnownFolderPath
0x18003a81e  test    eax, eax
0x18003a820  js      short loc_18003A883
0x18003a822  mov     rdx, [rsp+58h+ppszPath]
0x18003a827  or      r8, 0FFFFFFFFFFFFFFFFh
0x18003a82b  inc     r8
0x18003a82e  cmp     [rdx+r8*2], bx
0x18003a833  jnz     short loc_18003A82B
0x18003a835  lea     rcx, [rsp+58h+var_30]
0x18003a83a  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x18003a83f  mov     r8d, 2Eh ; '.'
0x18003a845  lea     rdx, aMicrosoftWindo_0; "\\Microsoft\\Windows\\OneSettings\\DBUp"...
0x18003a84c  lea     rcx, [rsp+58h+var_30]
0x18003a851  call    ??$_Append@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Append<ushort>(ushort const * const,unsigned __int64)
0x18003a856  lea     rcx, [rsp+58h+var_30]
0x18003a85b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a860  mov     rdx, rax
0x18003a863  lea     rcx, aDeletingS; "Deleting %s\n"
0x18003a86a  call    ?SBServicingLogMessage@@YAXPEBGZZ; SBServicingLogMessage(ushort const *,...)
0x18003a86f  lea     rcx, [rsp+58h+var_30]
0x18003a874  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18003a879  mov     rcx, rax; lpFileName
0x18003a87c  call    cs:__imp_DeleteFileW
0x18003a882  nop
0x18003a883  lea     rcx, [rsp+58h+var_30]
0x18003a888  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18003a88d  mov     rcx, [rsp+58h+var_10]
0x18003a892  xor     rcx, rsp; StackCookie
0x18003a895  call    __security_check_cookie
0x18003a89a  add     rsp, 50h
0x18003a89e  pop     rbx
0x18003a89f  retn
```
