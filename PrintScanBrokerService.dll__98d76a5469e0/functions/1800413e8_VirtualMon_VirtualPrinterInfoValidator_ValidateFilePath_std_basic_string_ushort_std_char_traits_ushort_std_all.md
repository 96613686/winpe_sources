# VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x1800413e8`
- end: `0x1800414d7`
- name: `?ValidateFilePath@VirtualPrinterInfoValidator@VirtualMon@@CAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `239`
- prototype: `DWORD __fastcall(const WCHAR *lpFileName)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x180041788`
- `0x180041b34`

## callees

- `0x180003a48`
- `0x1800077c8`
- `0x18000fdd4`
- `0x180018224`
- `0x1800380cc`
- `0x180038174`
- `0x1800413e8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041418`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180041418`

## string_xrefs

- `0x1800413f8`: `VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath`
- `0x180041434`: `VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath`
- `0x180041489`: `VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath`
- `0x180041482`: `File path cannot be empty.`
- `0x18004144a`: `File path is invalid`
- `0x18004149f`: `File path cannot be empty`
- `0x18004142d`: `File path is invalid.`

## pseudocode

```c
DWORD __fastcall VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath(const WCHAR *lpFileName)
{
  DWORD result; // eax
  const struct winrt::impl::slim_source_location *v3; // rbx
  const struct winrt::impl::slim_source_location *v4; // rbx
  _BYTE pExceptionObject[24]; // [rsp+20h] [rbp-58h] BYREF
  _BYTE v6[24]; // [rsp+38h] [rbp-40h] BYREF
  _BYTE v7[40]; // [rsp+50h] [rbp-28h] BYREF

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo("VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath", L"Entered.");
  if ( !*((_QWORD *)lpFileName + 2) )
  {
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath",
      L"File path cannot be empty.");
    v4 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v6);
    winrt::param::hstring::hstring((winrt::param::hstring *)v7, L"File path cannot be empty");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v7,
      v4);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  if ( *((_QWORD *)lpFileName + 3) > 7u )
    lpFileName = *(const WCHAR **)lpFileName;
  result = GetFileAttributesW(lpFileName);
  if ( result == -1 || (result & 0x10) != 0 )
  {
    VirtualPrintDEHTelemetry::WriteDbgTraceError(
      "VirtualMon::VirtualPrinterInfoValidator::ValidateFilePath",
      L"File path is invalid.");
    v3 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(v6);
    winrt::param::hstring::hstring((winrt::param::hstring *)v7, L"File path is invalid");
    winrt::hresult_invalid_argument::hresult_invalid_argument(
      (winrt::hresult_invalid_argument *)pExceptionObject,
      (const struct winrt::param::hstring *)v7,
      v3);
    throw (winrt::hresult_invalid_argument *)pExceptionObject;
  }
  return result;
}

```

## disassembly

```asm
0x1800413e8  push    rbx
0x1800413ea  sub     rsp, 70h
0x1800413ee  mov     rbx, rcx
0x1800413f1  lea     rdx, aEntered; "Entered."
0x1800413f8  lea     rcx, aVirtualmonVirt_2; "VirtualMon::VirtualPrinterInfoValidator"...
0x1800413ff  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180041404  cmp     qword ptr [rbx+10h], 0
0x180041409  jz      short loc_180041482
0x18004140b  cmp     qword ptr [rbx+18h], 7
0x180041410  jbe     short loc_180041415
0x180041412  mov     rbx, [rbx]
0x180041415  mov     rcx, rbx; lpFileName
0x180041418  call    cs:__imp_GetFileAttributesW
0x18004141e  cmp     eax, 0FFFFFFFFh
0x180041421  jz      short loc_18004142D
0x180041423  test    al, 10h
0x180041425  jnz     short loc_18004142D
0x180041427  add     rsp, 70h
0x18004142b  pop     rbx
0x18004142c  retn
0x18004142d  lea     rdx, aFilePathIsInva; "File path is invalid."
0x180041434  lea     rcx, aVirtualmonVirt_2; "VirtualMon::VirtualPrinterInfoValidator"...
0x18004143b  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180041440  lea     rcx, [rsp+78h+var_40]
0x180041445  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18004144a  lea     rdx, aFilePathIsInva_0; "File path is invalid"
0x180041451  mov     rbx, rax
0x180041454  lea     rcx, [rsp+78h+var_28]; this
0x180041459  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x18004145e  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x180041461  lea     rdx, [rsp+78h+var_28]; struct winrt::param::hstring *
0x180041466  lea     rcx, [rsp+78h+pExceptionObject]; this
0x18004146b  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x180041470  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x180041477  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x18004147c  call    _CxxThrowException_0
0x180041482  lea     rdx, aFilePathCannot_0; "File path cannot be empty."
0x180041489  lea     rcx, aVirtualmonVirt_2; "VirtualMon::VirtualPrinterInfoValidator"...
0x180041490  call    ?WriteDbgTraceError@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceError(char *,ushort *,...)
0x180041495  lea     rcx, [rsp+78h+var_40]
0x18004149a  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18004149f  lea     rdx, aFilePathCannot; "File path cannot be empty"
0x1800414a6  mov     rbx, rax
0x1800414a9  lea     rcx, [rsp+78h+var_28]; this
0x1800414ae  call    ??0hstring@param@winrt@@QEAA@QEBG@Z; winrt::param::hstring::hstring(ushort const * const)
0x1800414b3  mov     r8, rbx; struct winrt::impl::slim_source_location *
0x1800414b6  lea     rdx, [rsp+78h+var_28]; struct winrt::param::hstring *
0x1800414bb  lea     rcx, [rsp+78h+pExceptionObject]; this
0x1800414c0  call    ??0hresult_invalid_argument@winrt@@QEAA@AEBUhstring@param@1@AEBUslim_source_location@impl@1@@Z; winrt::hresult_invalid_argument::hresult_invalid_argument(winrt::param::hstring const &,winrt::impl::slim_source_location const &)
0x1800414c5  lea     rdx, _TI2?AUhresult_invalid_argument@winrt@@; pThrowInfo
0x1800414cc  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800414d1  call    _CxxThrowException_0
```
