# Pal::WinRTPathInformation::getStorageFolderPath(ABI::Windows::Storage::IStorageFolder *)

- ea: `0x180018548`
- end: `0x1800186bd`
- name: `?getStorageFolderPath@WinRTPathInformation@Pal@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIStorageFolder@Storage@Windows@ABI@@@Z`
- size: `373`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180017d98`

## callees

- `0x1800094a0`
- `0x18000a080`
- `0x18000b4b8`
- `0x18000c850`
- `0x18000cd80`
- `0x18001006c`
- `0x180010b18`
- `0x180018460`
- `0x180018548`
- `0x18001a7a8`
- `0x180043010`

## import_xrefs

- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001860a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z` at `0x18001860a`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018615`
- `msvcp_win!??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z` at `0x180018615`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018682`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800185ac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180018682`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001866b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18001866b`

## string_xrefs

- `0x1800185e0`: `IOImplWinRT::getStorageFolderPath - get_Path failed`

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
    v7 = std::operator<<<std::char_traits<char>>(
           (__int64)v18,
           (__int64)"IOImplWinRT::getStorageFolderPath - get_Path failed");
    v8 = std::operator<<<std::char_traits<char>>(v7, (__int64)" (HRESULT: 0x");
    v9 = std::ostream::operator<<(v8, std::hex);
    v10 = std::ostream::operator<<(v9, (unsigned int)v6);
    std::operator<<<std::char_traits<char>>(v10, (__int64)")");
    std::stringbuf::str(v19, v20);
    std::runtime_error::runtime_error((std::exception *)pExceptionObject);
    throw (std::runtime_error *)pExceptionObject;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  std::wstring::wstring(a1, (__int64)StringRawBuffer);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v14);
  return a1;
}

```

## disassembly

```asm
0x180018548  mov     [rsp-8+arg_10], rbx
0x18001854d  push    rbp
0x18001854e  push    rsi
0x18001854f  push    rdi
0x180018550  lea     rbp, [rsp-80h]
0x180018555  sub     rsp, 180h
0x18001855c  mov     rax, cs:__security_cookie
0x180018563  xor     rax, rsp
0x180018566  mov     [rbp+90h+var_20], rax
0x18001856a  mov     rbx, rdx
0x18001856d  mov     rsi, rcx
0x180018570  mov     [rsp+190h+var_168], rcx
0x180018575  mov     [rsp+190h+var_168], 0
0x18001857e  lea     rcx, [rsp+190h+var_168]
0x180018583  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180018588  lea     rdx, [rsp+190h+var_168]; struct ABI::Windows::Storage::IStorageItem **
0x18001858d  mov     rcx, rbx; struct ABI::Windows::Storage::IStorageFolder *
0x180018590  call    ?getStorageFolderItem@WinRTPathInformation@Pal@@CAXPEAUIStorageFolder@Storage@Windows@ABI@@PEAPEAUIStorageItem@456@@Z; Pal::WinRTPathInformation::getStorageFolderItem(ABI::Windows::Storage::IStorageFolder *,ABI::Windows::Storage::IStorageItem * *)
0x180018595  mov     [rsp+190h+string], 0
0x18001859e  mov     rdi, [rsp+190h+var_168]
0x1800185a3  mov     rax, [rdi]
0x1800185a6  mov     rbx, [rax+60h]
0x1800185aa  xor     ecx, ecx; string
0x1800185ac  call    cs:__imp_WindowsDeleteString
0x1800185b2  mov     [rsp+190h+string], 0
0x1800185bb  lea     rdx, [rsp+190h+string]
0x1800185c0  mov     rcx, rdi
0x1800185c3  mov     rax, rbx
0x1800185c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800185cb  mov     ebx, eax
0x1800185cd  test    eax, eax
0x1800185cf  jns     loc_180018659
0x1800185d5  lea     rcx, [rsp+190h+var_140]
0x1800185da  call    ??0?$basic_stringstream@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>::basic_stringstream<char,std::char_traits<char>,std::allocator<char>>(void)
0x1800185df  nop
0x1800185e0  lea     rdx, aIoimplwinrtGet_0; "IOImplWinRT::getStorageFolderPath - get"...
0x1800185e7  lea     rcx, [rsp+190h+var_130]
0x1800185ec  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x1800185f1  mov     rcx, rax
0x1800185f4  lea     rdx, aHresult0x_0; " (HRESULT: 0x"
0x1800185fb  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x180018600  lea     rdx, ?hex@std@@YAAEAVios_base@1@AEAV21@@Z; std::hex(std::ios_base &)
0x180018607  mov     rcx, rax
0x18001860a  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@P6AAEAVios_base@1@AEAV21@@Z@Z; std::ostream::operator<<(std::ios_base & (*)(std::ios_base &))
0x180018610  mov     edx, ebx
0x180018612  mov     rcx, rax
0x180018615  call    cs:__imp_??6?$basic_ostream@DU?$char_traits@D@std@@@std@@QEAAAEAV01@J@Z; std::ostream::operator<<(long)
0x18001861b  mov     rcx, rax
0x18001861e  lea     rdx, asc_180048470; ")"
0x180018625  call    ??$?6U?$char_traits@D@std@@@std@@YAAEAV?$basic_ostream@DU?$char_traits@D@std@@@0@AEAV10@PEBD@Z; std::operator<<<std::char_traits<char>>(std::ostream &,char const *)
0x18001862a  lea     rdx, [rbp+90h+var_40]
0x18001862e  lea     rcx, [rsp+190h+var_128]
0x180018633  call    ?str@?$basic_stringbuf@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@XZ; std::stringbuf::str(void)
0x180018638  nop
0x180018639  lea     rdx, [rbp+90h+var_40]
0x18001863d  lea     rcx, [rsp+190h+pExceptionObject]; this
0x180018642  call    ??0runtime_error@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::runtime_error::runtime_error(std::string const &)
0x180018647  lea     rdx, _TI2?AVruntime_error@std@@; pThrowInfo
0x18001864e  lea     rcx, [rsp+190h+pExceptionObject]; pExceptionObject
0x180018653  call    _CxxThrowException_0
0x180018659  mov     [rsp+190h+length], 0
0x180018661  lea     rdx, [rsp+190h+length]; length
0x180018666  mov     rcx, [rsp+190h+string]; string
0x18001866b  call    cs:__imp_WindowsGetStringRawBuffer
0x180018671  mov     rdx, rax
0x180018674  mov     rcx, rsi
0x180018677  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x18001867c  nop
0x18001867d  mov     rcx, [rsp+190h+string]; string
0x180018682  call    cs:__imp_WindowsDeleteString
0x180018688  mov     [rsp+190h+string], 0
0x180018691  lea     rcx, [rsp+190h+var_168]
0x180018696  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18001869b  mov     rax, rsi
0x18001869e  mov     rcx, [rbp+90h+var_20]
0x1800186a2  xor     rcx, rsp; StackCookie
0x1800186a5  call    __security_check_cookie
0x1800186aa  mov     rbx, [rsp+190h+arg_10]
0x1800186b2  add     rsp, 180h
0x1800186b9  pop     rdi
0x1800186ba  pop     rsi
0x1800186bb  pop     rbp
0x1800186bc  retn
```
