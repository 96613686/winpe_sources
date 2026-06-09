# ConnectedStorage::LocalStorage::GetUserContextRoot(unsigned __int64,ConnectedStorage::SimpleHStringWrapper const &)

- ea: `0x1800270e8`
- end: `0x1800271a5`
- name: `?GetUserContextRoot@LocalStorage@ConnectedStorage@@SA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@_KAEBVSimpleHStringWrapper@2@@Z`
- size: `189`
- prototype: `__int64 __fastcall(__int64, __int64, _QWORD *)`
- caller_count: `7`
- callee_count: `7`
- tags: ``

## callers

- `0x180014280`
- `0x180026e8c`
- `0x18002f6b8`
- `0x1800318bc`
- `0x180031efc`
- `0x180032f64`
- `0x180033414`

## callees

- `0x18000aae4`
- `0x180010e6c`
- `0x1800136e8`
- `0x18001b9c8`
- `0x180022dec`
- `0x1800270e8`
- `0x18004f508`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002718b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002718b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027155`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180027155`
- `ext-ms-win-gaming-xblgamesave-l1-1-0!XblGameSave_GetUserStorageRoot` at `0x180027135`
- `ext-ms-win-gaming-xblgamesave-l1-1-0!XblGameSave_GetUserStorageRoot` at `0x180027135`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConnectedStorage::LocalStorage::GetUserContextRoot(__int64 a1, __int64 a2, _QWORD *a3)
{
  HSTRING *AddressOf; // rax
  int UserStorageRoot; // eax
  const unsigned __int16 *v8; // r8
  PCWSTR StringRawBuffer; // rax
  const unsigned __int16 *v10; // rax
  HSTRING string; // [rsp+50h] [rbp+18h] BYREF

  std::wstring::wstring(a1);
  string = 0;
  AddressOf = ConnectedStorage::SimpleHStringWrapper::GetAddressOf((ConnectedStorage::SimpleHStringWrapper *)&string);
  UserStorageRoot = XblGameSave_GetUserStorageRoot(a2, *a3, AddressOf);
  if ( UserStorageRoot < 0 )
    ConnectedStorage::ReportErrorAndThrow(
      (ConnectedStorage *)(unsigned int)UserStorageRoot,
      (int)L"XblGameSave_GetUserStorageRoot(userContext, packageFamilyName.Get(), storageRoot.GetAddressOf())",
      v8);
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  std::wstring::append(a1, StringRawBuffer);
  std::wstring::append(a1, L"\\wgs");
  v10 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1);
  ConnectedStorage::File::CreateDirectoryW(v10);
  WindowsDeleteString(string);
  return a1;
}

```

## disassembly

```asm
0x1800270e8  mov     rax, rsp
0x1800270eb  mov     [rax+10h], rbx
0x1800270ef  mov     [rax+20h], rsi
0x1800270f3  mov     [rax+8], rcx
0x1800270f7  push    rdi
0x1800270f8  sub     rsp, 30h
0x1800270fc  mov     rbx, r8
0x1800270ff  mov     rdi, rdx
0x180027102  mov     rsi, rcx
0x180027105  mov     dword ptr [rax-18h], 0
0x18002710c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x180027111  mov     [rsp+38h+var_18], 1
0x180027119  mov     [rsp+38h+string], 0
0x180027122  lea     rcx, [rsp+38h+string]; this
0x180027127  call    ?GetAddressOf@SimpleHStringWrapper@ConnectedStorage@@QEAAPEAPEAUHSTRING__@@XZ; ConnectedStorage::SimpleHStringWrapper::GetAddressOf(void)
0x18002712c  mov     r8, rax
0x18002712f  mov     rdx, [rbx]
0x180027132  mov     rcx, rdi
0x180027135  call    cs:__imp_XblGameSave_GetUserStorageRoot
0x18002713b  test    eax, eax
0x18002713d  jns     short loc_18002714E
0x18002713f  lea     rdx, aXblgamesaveGet_0; "XblGameSave_GetUserStorageRoot(userCont"...
0x180027146  mov     ecx, eax; this
0x180027148  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18002714e  xor     edx, edx; length
0x180027150  mov     rcx, [rsp+38h+string]; string
0x180027155  call    cs:__imp_WindowsGetStringRawBuffer
0x18002715b  mov     rdx, rax
0x18002715e  mov     rcx, rsi
0x180027161  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180027166  lea     rdx, aWgs; "\\wgs"
0x18002716d  mov     rcx, rsi
0x180027170  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@QEBG@Z; std::wstring::append(ushort const * const)
0x180027175  mov     rcx, rsi
0x180027178  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002717d  mov     rcx, rax; unsigned __int16 *
0x180027180  call    ?CreateDirectoryW@File@ConnectedStorage@@SAJPEBG@Z; ConnectedStorage::File::CreateDirectoryW(ushort const *)
0x180027185  nop
0x180027186  mov     rcx, [rsp+38h+string]; string
0x18002718b  call    cs:__imp_WindowsDeleteString
0x180027191  mov     rax, rsi
0x180027194  mov     rbx, [rsp+38h+arg_8]
0x180027199  mov     rsi, [rsp+38h+arg_18]
0x18002719e  add     rsp, 30h
0x1800271a2  pop     rdi
0x1800271a3  retn
```
