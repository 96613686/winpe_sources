# Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)

- ea: `0x18002bbd8`
- end: `0x18002bd4d`
- name: `?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18002b428`

## callees

- `0x18000d090`
- `0x18000dce0`
- `0x180011d90`
- `0x180019f3c`
- `0x180021da8`
- `0x180024a34`
- `0x180025360`
- `0x18002baf0`
- `0x18002bbd8`
- `0x18002d9d8`
- `0x180098010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002bc9a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18002bc9a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002bca5`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x18002bca5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bcfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18002bcfb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd12`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bc3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002bd12`

## string_xrefs

- `0x18002bc70`: `IOImplWinRT::getStorageFolderPath - get_Path failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Pal::WinRTPathInformation::getStorageFolderPath(
        __int64 a1,
        struct ABI::Windows::Storage::IStorageFolder *a2)
{
  struct ABI::Windows::Storage::IStorageItem *v4; // rdi
  __int64 (__fastcall *v5)(struct ABI::Windows::Storage::IStorageItem *, HSTRING *); // rbx
  int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rax
  __int64 v10; // rax
  PCWSTR StringRawBuffer; // rax
  HSTRING string; // [rsp+20h] [rbp-E0h] BYREF
  struct ABI::Windows::Storage::IStorageItem *v14; // [rsp+28h] [rbp-D8h] BYREF
  UINT32 length; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE pExceptionObject[24]; // [rsp+38h] [rbp-C8h] BYREF
  _BYTE v17[16]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v18[8]; // [rsp+60h] [rbp-A0h] BYREF
  _BYTE v19[232]; // [rsp+68h] [rbp-98h] BYREF
  _BYTE v20[32]; // [rsp+150h] [rbp+50h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  Pal::WinRTPathInformation::getStorageFolderItem(a2, &v14);
  string = 0;
  v4 = v14;
  v5 = *(__int64 (__fastcall **)(struct ABI::Windows::Storage::IStorageItem *, HSTRING *))(*(_QWORD *)v14 + 96LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(v4, &string);
  if ( v6 < 0 )
  {
    std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(v17);
    v7 = std::operator<<<std::char_traits<char>>(v18, "IOImplWinRT::getStorageFolderPath - get_Path failed");
    v8 = std::operator<<<std::char_traits<char>>(v7, " (HRESULT: 0x");
    v9 = std::ostream::operator<<(v8, std::hex);
    v10 = std::ostream::operator<<(v9, (unsigned int)v6);
    std::operator<<<std::char_traits<char>>(v10, ")");
    std::stringbuf::str(v19, v20);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  std::wstring::wstring(a1, StringRawBuffer);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return a1;
}

```

## disassembly

```asm
0x18002bbd8  mov     [rsp-8+arg_10], rbx
0x18002bbdd  push    rbp
0x18002bbde  push    rsi
0x18002bbdf  push    rdi
0x18002bbe0  lea     rbp, [rsp-80h]
0x18002bbe5  sub     rsp, 180h
0x18002bbec  mov     rax, cs:__security_cookie
0x18002bbf3  xor     rax, rsp
0x18002bbf6  mov     [rbp+90h+var_20], rax
0x18002bbfa  mov     rbx, rdx
0x18002bbfd  mov     rsi, rcx
0x18002bc00  mov     [rsp+190h+var_168], rcx
0x18002bc05  mov     [rsp+190h+var_168], 0
0x18002bc0e  lea     rcx, [rsp+190h+var_168]
0x18002bc13  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bc18  lea     rdx, [rsp+190h+var_168]; struct ABI::Windows::Storage::IStorageItem **
0x18002bc1d  mov     rcx, rbx; struct ABI::Windows::Storage::IStorageFolder *
0x18002bc20  call    ?getStorageFolderItem@WinRTPathInformation@Pal@@CAXPEAUIStorageFolder@Storage@Windows@ABI@@PEAPEAUIStorageItem@456@@Z; Pal::WinRTPathInformation::getStorageFolderItem(ABI::Windows::Storage::IStorageFolder *,ABI::Windows::Storage::IStorageItem * *)
0x18002bc25  mov     [rsp+190h+string], 0
0x18002bc2e  mov     rdi, [rsp+190h+var_168]
0x18002bc33  mov     rax, [rdi]
0x18002bc36  mov     rbx, [rax+60h]
0x18002bc3a  xor     ecx, ecx; string
0x18002bc3c  call    cs:__imp_WindowsDeleteString
0x18002bc42  mov     [rsp+190h+string], 0
0x18002bc4b  lea     rdx, [rsp+190h+string]
0x18002bc50  mov     rcx, rdi
0x18002bc53  mov     rax, rbx
0x18002bc56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bc5b  mov     ebx, eax
0x18002bc5d  test    eax, eax
0x18002bc5f  jns     loc_18002BCE9
0x18002bc65  lea     rcx, [rsp+190h+var_140]
0x18002bc6a  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x18002bc6f  nop
0x18002bc70  lea     rdx, aIoimplwinrtGet_0; "IOImplWinRT::getStorageFolderPath - get"...
0x18002bc77  lea     rcx, [rsp+190h+var_130]
0x18002bc7c  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002bc81  mov     rcx, rax
0x18002bc84  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x18002bc8b  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002bc90  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x18002bc97  mov     rcx, rax
0x18002bc9a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x18002bca0  mov     edx, ebx
0x18002bca2  mov     rcx, rax
0x18002bca5  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18002bcab  mov     rcx, rax
0x18002bcae  lea     rdx, asc_1800A4BE0; ")"
0x18002bcb5  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18002bcba  lea     rdx, [rbp+90h+var_40]
0x18002bcbe  lea     rcx, [rsp+190h+var_128]
0x18002bcc3  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x18002bcc8  nop
0x18002bcc9  lea     rdx, [rbp+90h+var_40]
0x18002bccd  lea     rcx, [rsp+190h+pExceptionObject]; this
0x18002bcd2  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x18002bcd7  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18002bcde  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x18002bce3  call    _CxxThrowException_0
0x18002bce9  mov     [rsp+190h+length], 0
0x18002bcf1  lea     rdx, [rsp+190h+length]; length
0x18002bcf6  mov     rcx, [rsp+190h+string]; string
0x18002bcfb  call    cs:__imp_WindowsGetStringRawBuffer
0x18002bd01  mov     rdx, rax
0x18002bd04  mov     rcx, rsi
0x18002bd07  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18002bd0c  nop
0x18002bd0d  mov     rcx, [rsp+190h+string]; string
0x18002bd12  call    cs:__imp_WindowsDeleteString
0x18002bd18  mov     [rsp+190h+string], 0
0x18002bd21  lea     rcx, [rsp+190h+var_168]
0x18002bd26  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18002bd2b  mov     rax, rsi
0x18002bd2e  mov     rcx, [rbp+90h+var_20]
0x18002bd32  xor     rcx, rsp; StackCookie
0x18002bd35  call    __security_check_cookie
0x18002bd3a  mov     rbx, [rsp+190h+arg_10]
0x18002bd42  add     rsp, 180h
0x18002bd49  pop     rdi
0x18002bd4a  pop     rsi
0x18002bd4b  pop     rbp
0x18002bd4c  retn
```
