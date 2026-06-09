# ConnectedStorage::_ExecuteWithVerifyFilePath__lambda_766f01c331b105c560f318e401dc925d___

- ea: `0x18004e4b4`
- end: `0x18004e5a4`
- name: `ConnectedStorage::_ExecuteWithVerifyFilePath__lambda_766f01c331b105c560f318e401dc925d___`
- size: `240`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x18004f508`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x180010e30`
- `0x18001c090`
- `0x18004e4b4`
- `0x18004ebdc`
- `0x18004ed0c`
- `0x18004f1d0`
- `0x18004f7f4`
- `0x1800500a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e55c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e55c`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004e552`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18004e552`

## string_xrefs

- `0x18004e56e`: `CreateDirectory`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall ConnectedStorage::_ExecuteWithVerifyFilePath__lambda_766f01c331b105c560f318e401dc925d___(
        LPCWSTR lpPathName)
{
  char IsFile; // bl
  signed int LastError; // eax
  const unsigned __int16 *v4; // r8
  _QWORD v6[2]; // [rsp+20h] [rbp-40h] BYREF
  _BYTE v7[32]; // [rsp+30h] [rbp-30h] BYREF

  std::map<std::wstring,ConnectedStorage::Handle>::map<std::wstring,ConnectedStorage::Handle>(v6);
  std::wstring::wstring(v7);
  IsFile = ConnectedStorage::VerifyFilePathHandler::IsFile(v7);
  std::wstring::_Tidy_deallocate(v7);
  if ( !IsFile )
  {
    std::wstring::wstring(v7);
    ConnectedStorage::VerifyFilePathHandler::VerifyPath(v6, (__int64)v7);
    std::wstring::_Tidy_deallocate(v7);
  }
  std::wstring::wstring(v7);
  ConnectedStorage::VerifyFilePathHandler::AddPath(v6, (__int64)v7);
  std::wstring::_Tidy_deallocate(v7);
  if ( !CreateDirectoryW(lpPathName, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)(unsigned int)LastError, (int)L"CreateDirectory", v4);
  }
  return std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>(v6);
}

```

## disassembly

```asm
0x18004e4b4  mov     [rsp-8+arg_8], rbx
0x18004e4b9  mov     [rsp-8+arg_10], rdi
0x18004e4be  push    rbp
0x18004e4bf  mov     rbp, rsp
0x18004e4c2  sub     rsp, 60h
0x18004e4c6  mov     rax, cs:__security_cookie
0x18004e4cd  xor     rax, rsp
0x18004e4d0  mov     [rbp+var_10], rax
0x18004e4d4  mov     rdi, rcx
0x18004e4d7  lea     rcx, [rbp+var_40]
0x18004e4db  call    ??0?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@@std@@QEAA@XZ; std::map<std::wstring,ConnectedStorage::Handle>::map<std::wstring,ConnectedStorage::Handle>(void)
0x18004e4e0  nop
0x18004e4e1  mov     rdx, rdi
0x18004e4e4  lea     rcx, [rbp+var_30]
0x18004e4e8  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e4ed  lea     rcx, [rbp+var_30]
0x18004e4f1  call    ?IsFile@VerifyFilePathHandler@ConnectedStorage@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::IsFile(std::wstring const &)
0x18004e4f6  mov     bl, al
0x18004e4f8  lea     rcx, [rbp+var_30]
0x18004e4fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e501  test    bl, bl
0x18004e503  jnz     short loc_18004E529
0x18004e505  mov     rdx, rdi
0x18004e508  lea     rcx, [rbp+var_30]
0x18004e50c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e511  nop
0x18004e512  lea     rdx, [rbp+var_30]
0x18004e516  lea     rcx, [rbp+var_40]
0x18004e51a  call    ?VerifyPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::VerifyPath(std::wstring const &)
0x18004e51f  nop
0x18004e520  lea     rcx, [rbp+var_30]
0x18004e524  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e529  mov     rdx, rdi
0x18004e52c  lea     rcx, [rbp+var_30]
0x18004e530  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18004e535  nop
0x18004e536  lea     rdx, [rbp+var_30]
0x18004e53a  lea     rcx, [rbp+var_40]
0x18004e53e  call    ?AddPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::AddPath(std::wstring const &)
0x18004e543  nop
0x18004e544  lea     rcx, [rbp+var_30]
0x18004e548  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004e54d  xor     edx, edx; lpSecurityAttributes
0x18004e54f  mov     rcx, rdi; lpPathName
0x18004e552  call    cs:__imp_CreateDirectoryW
0x18004e558  test    eax, eax
0x18004e55a  jnz     short loc_18004E57D
0x18004e55c  call    cs:__imp_GetLastError
0x18004e562  test    eax, eax
0x18004e564  jle     short loc_18004E56E
0x18004e566  movzx   eax, ax
0x18004e569  or      eax, 80070000h
0x18004e56e  lea     rdx, aCreatedirector; "CreateDirectory"
0x18004e575  mov     ecx, eax; this
0x18004e577  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004e57d  lea     rcx, [rbp+var_40]
0x18004e581  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>(void)
0x18004e586  mov     rcx, [rbp+var_10]
0x18004e58a  xor     rcx, rsp; StackCookie
0x18004e58d  call    __security_check_cookie
0x18004e592  lea     r11, [rsp+60h+var_s0]
0x18004e597  mov     rbx, [r11+18h]
0x18004e59b  mov     rdi, [r11+20h]
0x18004e59f  mov     rsp, r11
0x18004e5a2  pop     rbp
0x18004e5a3  retn
```
