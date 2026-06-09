# ConnectedStorage::File::CreateParentDirectories(ushort const *,ushort const *,ConnectedStorage::VerifyFilePathHandler &)

- ea: `0x18004f554`
- end: `0x18004f6bd`
- name: `?CreateParentDirectories@File@ConnectedStorage@@CAXPEBG0AEAVVerifyFilePathHandler@2@@Z`
- size: `361`
- prototype: `static void(const unsigned __int16 *, const unsigned __int16 *, struct ConnectedStorage::VerifyFilePathHandler *)`
- caller_count: `2`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x18004ee1c`
- `0x18004ef4c`

## callees

- `0x180003c70`
- `0x180004754`
- `0x18000aae4`
- `0x180010e30`
- `0x18001c090`
- `0x18004deec`
- `0x18004f1d0`
- `0x18004f554`
- `0x18004f790`
- `0x18004f7c8`
- `0x1800500a4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004f5ea`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18004f5ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f69c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f69c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004f65c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004f65c`

## string_xrefs

- `0x18004f6ae`: `File::CreateParentDirectories`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ConnectedStorage::File::CreateParentDirectories(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct ConnectedStorage::VerifyFilePathHandler *a3)
{
  const unsigned __int16 *i; // rax
  char IsDirectory; // bl
  const unsigned __int16 *v8; // rdi
  signed int LastError; // eax
  const unsigned __int16 *v10; // r8
  _BYTE v11[32]; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR PathName[264]; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v13[528]; // [rsp+250h] [rbp+150h] BYREF

  std::wstring::wstring((__int64)v11, (__int64)a1);
  ConnectedStorage::VerifyFilePathHandler::VerifyPath(a3, (__int64)v11);
  std::wstring::_Tidy_deallocate(v11);
  for ( i = ConnectedStorage::File::FindNextSlash(a2); ; i = ConnectedStorage::File::FindNextSlash(v8) )
  {
    v8 = i;
    if ( !*i )
      break;
    memset_0(v13, 0, 0x208u);
    _o_wcsncpy_s(v13, 260, a2, v8 - a2);
    ConnectedStorage::GenerateAbsolutePath<260>((__int64)a1, (__int64)v13, PathName);
    std::wstring::wstring((__int64)v11, (__int64)PathName);
    IsDirectory = ConnectedStorage::VerifyFilePathHandler::IsDirectory(v11);
    std::wstring::_Tidy_deallocate(v11);
    if ( !IsDirectory )
    {
      std::wstring::wstring((__int64)v11, (__int64)PathName);
      ConnectedStorage::VerifyFilePathHandler::AddPath(a3, (__int64)v11);
      std::wstring::_Tidy_deallocate(v11);
      if ( !CreateDirectoryW(PathName, 0) )
      {
        LastError = GetLastError();
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)LastError,
          (int)L"File::CreateParentDirectories",
          v10);
      }
    }
  }
}

```

## disassembly

```asm
0x18004f554  push    rbp
0x18004f556  push    rbx
0x18004f557  push    rsi
0x18004f558  push    rdi
0x18004f559  push    r12
0x18004f55b  push    r14
0x18004f55d  push    r15
0x18004f55f  lea     rbp, [rsp-370h]
0x18004f567  sub     rsp, 470h
0x18004f56e  mov     rax, cs:__security_cookie
0x18004f575  xor     rax, rsp
0x18004f578  mov     [rbp+3A0h+var_40], rax
0x18004f57f  mov     rsi, r8
0x18004f582  mov     r14, rdx
0x18004f585  mov     r15, rcx
0x18004f588  mov     rdx, rcx
0x18004f58b  lea     rcx, [rsp+4A0h+var_480]
0x18004f590  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f595  nop
0x18004f596  lea     rdx, [rsp+4A0h+var_480]
0x18004f59b  mov     rcx, rsi
0x18004f59e  call    ?VerifyPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::VerifyPath(std::wstring const &)
0x18004f5a3  nop
0x18004f5a4  lea     rcx, [rsp+4A0h+var_480]
0x18004f5a9  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f5ae  mov     rcx, r14; unsigned __int16 *
0x18004f5b1  call    ?FindNextSlash@File@ConnectedStorage@@CAPEBGPEBG@Z; ConnectedStorage::File::FindNextSlash(ushort const *)
0x18004f5b6  xor     r12d, r12d
0x18004f5b9  jmp     loc_18004F66E
0x18004f5be  xor     edx, edx; Val
0x18004f5c0  mov     r8d, 208h; Size
0x18004f5c6  lea     rcx, [rbp+3A0h+var_250]; void *
0x18004f5cd  call    memset_0
0x18004f5d2  mov     r9, rdi
0x18004f5d5  sub     r9, r14
0x18004f5d8  sar     r9, 1
0x18004f5db  mov     r8, r14
0x18004f5de  mov     edx, 104h
0x18004f5e3  lea     rcx, [rbp+3A0h+var_250]
0x18004f5ea  call    cs:__imp__o_wcsncpy_s
0x18004f5f0  lea     r8, [rsp+4A0h+PathName]
0x18004f5f5  lea     rdx, [rbp+3A0h+var_250]
0x18004f5fc  mov     rcx, r15
0x18004f5ff  call    ??$GenerateAbsolutePath@$0BAE@@ConnectedStorage@@YAXPEBG0AEAY0BAE@G@Z; ConnectedStorage::GenerateAbsolutePath<260>(ushort const *,ushort const *,ushort (&)[260])
0x18004f604  lea     rdx, [rsp+4A0h+PathName]
0x18004f609  lea     rcx, [rsp+4A0h+var_480]
0x18004f60e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f613  lea     rcx, [rsp+4A0h+var_480]
0x18004f618  call    ?IsDirectory@VerifyFilePathHandler@ConnectedStorage@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::IsDirectory(std::wstring const &)
0x18004f61d  mov     bl, al
0x18004f61f  lea     rcx, [rsp+4A0h+var_480]
0x18004f624  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f629  test    bl, bl
0x18004f62b  jnz     short loc_18004F666
0x18004f62d  lea     rdx, [rsp+4A0h+PathName]
0x18004f632  lea     rcx, [rsp+4A0h+var_480]
0x18004f637  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004f63c  nop
0x18004f63d  lea     rdx, [rsp+4A0h+var_480]
0x18004f642  mov     rcx, rsi
0x18004f645  call    ?AddPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::AddPath(std::wstring const &)
0x18004f64a  nop
0x18004f64b  lea     rcx, [rsp+4A0h+var_480]
0x18004f650  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f655  xor     edx, edx; lpSecurityAttributes
0x18004f657  lea     rcx, [rsp+4A0h+PathName]; lpPathName
0x18004f65c  call    cs:__imp_CreateDirectoryW
0x18004f662  test    eax, eax
0x18004f664  jz      short loc_18004F69C
0x18004f666  mov     rcx, rdi; unsigned __int16 *
0x18004f669  call    ?FindNextSlash@File@ConnectedStorage@@CAPEBGPEBG@Z; ConnectedStorage::File::FindNextSlash(ushort const *)
0x18004f66e  cmp     [rax], r12w
0x18004f672  mov     rdi, rax
0x18004f675  jnz     loc_18004F5BE
0x18004f67b  mov     rcx, [rbp+3A0h+var_40]
0x18004f682  xor     rcx, rsp; StackCookie
0x18004f685  call    __security_check_cookie
0x18004f68a  add     rsp, 470h
0x18004f691  pop     r15
0x18004f693  pop     r14
0x18004f695  pop     r12
0x18004f697  pop     rdi
0x18004f698  pop     rsi
0x18004f699  pop     rbx
0x18004f69a  pop     rbp
0x18004f69b  retn
0x18004f69c  call    cs:__imp_GetLastError
0x18004f6a2  test    eax, eax
0x18004f6a4  jle     short loc_18004F6AE
0x18004f6a6  movzx   eax, ax
0x18004f6a9  or      eax, 80070000h
0x18004f6ae  lea     rdx, aFileCreatepare; "File::CreateParentDirectories"
0x18004f6b5  mov     ecx, eax; this
0x18004f6b7  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
