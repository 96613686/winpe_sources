# VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(VirtualMon::VirtualPrinterInfo const &)

- ea: `0x180037c78`
- end: `0x180037f20`
- name: `?UninstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@QEAAJAEBUVirtualPrinterInfo@2@@Z`
- size: `680`
- prototype: `__int64 __fastcall(VirtualMon::VirtualPrinterInstaller *__hidden this, const struct VirtualMon::VirtualPrinterInfo *)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, installer_update`

## callers

- `0x18002a148`
- `0x18002a6f0`

## callees

- `0x180002d40`
- `0x180007a28`
- `0x18000876c`
- `0x18000f8a8`
- `0x1800182ec`
- `0x1800230fc`
- `0x180032dfc`
- `0x180032e6c`
- `0x180032ecc`
- `0x180036834`
- `0x180037acc`
- `0x180037c78`
- `0x180038174`

## import_xrefs

- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180037d2c`
- `ext-ms-win-printer-winspool-core-l1-1-0!ClosePrinter` at `0x180037d2c`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180037d60`
- `ext-ms-win-printer-winspool-core-l1-1-0!OpenPrinterW` at `0x180037d60`

## string_xrefs

- `0x180037cab`: `VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter`
- `0x180037dab`: `VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter`
- `0x180037e0e`: `VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(
        VirtualMon::VirtualPrinterInstaller *this,
        const struct VirtualMon::VirtualPrinterInfo *a2)
{
  __int64 v4; // rax
  WCHAR *v5; // rcx
  WCHAR *v6; // rdx
  const struct VirtualMon::VirtualPrinterInfo *v7; // r8
  __int64 v8; // r15
  unsigned int i; // edi
  __int64 v10; // rsi
  const struct VirtualMon::VirtualPrinterInfo *v11; // rcx
  const struct VirtualMon::VirtualPrinterInfo *v12; // rax
  signed __int64 v13; // rcx
  int v14; // edx
  int v15; // r8d
  __int64 v16; // rsi
  __int64 v17; // rax
  const unsigned __int16 *v18; // r8
  WCHAR *v19; // rdx
  unsigned int v21; // [rsp+20h] [rbp-D8h] BYREF
  HANDLE hPrinter; // [rsp+28h] [rbp-D0h] BYREF
  __int128 v23; // [rsp+30h] [rbp-C8h] BYREF
  __int64 v24; // [rsp+40h] [rbp-B8h]
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+48h] [rbp-B0h] BYREF
  LPWSTR pPrinterName[3]; // [rsp+60h] [rbp-98h] BYREF
  unsigned __int64 v27; // [rsp+78h] [rbp-80h]
  LPWSTR v28[4]; // [rsp+80h] [rbp-78h] BYREF
  _BYTE v29[32]; // [rsp+A0h] [rbp-58h] BYREF

  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter",
    L"Entered.");
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 983052;
  v4 = std::operator+<unsigned short>(v28, (char *)this + 128, L":");
  std::operator+<unsigned short>(pPrinterName, v4, (char *)a2 + 64);
  std::wstring::_Tidy_deallocate(v28);
  hPrinter = 0;
  v5 = (WCHAR *)pPrinterName;
  if ( v27 > 7 )
    v5 = pPrinterName[0];
  if ( OpenPrinterW(v5, &hPrinter, &pDefault) )
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const struct VirtualMon::VirtualPrinterInfo **)a2;
    v6 = (WCHAR *)pPrinterName;
    if ( v27 > 7 )
      v6 = pPrinterName[0];
    VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(this, v6, (const unsigned __int16 *)a2);
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) <= 7u )
      v7 = a2;
    else
      v7 = *(const struct VirtualMon::VirtualPrinterInfo **)a2;
    VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
      "VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter",
      L"Printer not found. Port Name: %ws",
      v7);
    v21 = 0;
    v23 = 0;
    v24 = 0;
    VirtualMon::VirtualPrinterInstaller::EnumeratePrinters(this, &v21, &v23);
    v8 = v23;
    for ( i = 0; i < v21; ++i )
    {
      v10 = 136LL * i;
      VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
        "VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter",
        L"Printer Name: %ws. Port Name: %ws",
        *(_QWORD *)(v10 + v8 + 8),
        *(_QWORD *)(v10 + v8 + 24));
      if ( *((_QWORD *)a2 + 3) <= 7u )
        v11 = a2;
      else
        v11 = *(const struct VirtualMon::VirtualPrinterInfo **)a2;
      v12 = *(const struct VirtualMon::VirtualPrinterInfo **)(v10 + v8 + 24);
      v13 = v11 - v12;
      do
      {
        v14 = *(unsigned __int16 *)((char *)v12 + v13);
        v15 = *(unsigned __int16 *)v12 - v14;
        if ( v15 )
          break;
        v12 = (const struct VirtualMon::VirtualPrinterInfo *)((char *)v12 + 2);
      }
      while ( v14 );
      if ( !v15 )
      {
        v16 = *(_QWORD *)(v10 + v8 + 8);
        v17 = std::operator+<unsigned short>(v29, (char *)this + 128, L":");
        std::operator+<unsigned short>(v28, v17, v16);
        std::wstring::_Tidy_deallocate(v29);
        if ( *((_QWORD *)a2 + 3) <= 7u )
          v18 = (const unsigned __int16 *)a2;
        else
          v18 = *(const unsigned __int16 **)a2;
        v19 = (WCHAR *)v28;
        if ( v28[3] > (LPWSTR)7 )
          v19 = v28[0];
        VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(this, v19, v18);
        std::wstring::_Tidy_deallocate(v28);
      }
    }
    std::vector<unsigned char>::_Tidy(&v23);
  }
  std::wstring::_Tidy_deallocate(pPrinterName);
  wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&hPrinter);
  return 0;
}

```

## disassembly

```asm
0x180037c78  mov     [rsp+arg_10], rbx
0x180037c7d  push    rsi
0x180037c7e  push    rdi
0x180037c7f  push    r12
0x180037c81  push    r14
0x180037c83  push    r15
0x180037c85  sub     rsp, 0D0h
0x180037c8c  mov     rax, cs:__security_cookie
0x180037c93  xor     rax, rsp
0x180037c96  mov     [rsp+0F8h+var_38], rax
0x180037c9e  mov     rbx, rdx
0x180037ca1  mov     r14, rcx
0x180037ca4  lea     rdx, aEntered; "Entered."
0x180037cab  lea     rcx, aVirtualmonVirt_0; "VirtualMon::VirtualPrinterInstaller::Un"...
0x180037cb2  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037cb7  mov     [rsp+0F8h+hPrinter], 0
0x180037cc0  xorps   xmm0, xmm0
0x180037cc3  xor     eax, eax
0x180037cc5  movups  xmmword ptr [rsp+0F8h+pDefault.pDatatype], xmm0
0x180037cca  mov     qword ptr [rsp+0F8h+pDefault.DesiredAccess], rax
0x180037ccf  mov     [rsp+0F8h+pDefault.DesiredAccess], 0F000Ch
0x180037cd7  lea     r12, [r14+80h]
0x180037cde  lea     r8, asc_18004E4AC; ":"
0x180037ce5  mov     rdx, r12
0x180037ce8  lea     rcx, [rsp+0F8h+var_78]
0x180037cf0  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180037cf5  nop
0x180037cf6  lea     r8, [rbx+40h]
0x180037cfa  mov     rdx, rax
0x180037cfd  lea     rcx, [rsp+0F8h+pPrinterName]
0x180037d02  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@AEBV10@@Z; std::operator+<ushort>(std::wstring &&,std::wstring const &)
0x180037d07  nop
0x180037d08  lea     rcx, [rsp+0F8h+var_78]
0x180037d10  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037d15  mov     rdi, [rsp+0F8h+hPrinter]
0x180037d1a  test    rdi, rdi
0x180037d1d  jz      short loc_180037D3C
0x180037d1f  lea     rcx, [rsp+0F8h+var_D8]; this
0x180037d24  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180037d29  mov     rcx, rdi; hPrinter
0x180037d2c  call    cs:__imp_ClosePrinter
0x180037d32  lea     rcx, [rsp+0F8h+var_D8]; this
0x180037d37  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180037d3c  mov     [rsp+0F8h+hPrinter], 0
0x180037d45  lea     rcx, [rsp+0F8h+pPrinterName]
0x180037d4a  cmp     [rsp+0F8h+var_80], 7
0x180037d50  cmova   rcx, [rsp+0F8h+pPrinterName]; pPrinterName
0x180037d56  lea     r8, [rsp+0F8h+pDefault]; pDefault
0x180037d5b  lea     rdx, [rsp+0F8h+hPrinter]; phPrinter
0x180037d60  call    cs:__imp_OpenPrinterW
0x180037d66  test    eax, eax
0x180037d68  jz      short loc_180037D95
0x180037d6a  cmp     qword ptr [rbx+18h], 7
0x180037d6f  jbe     short loc_180037D74
0x180037d71  mov     rbx, [rbx]
0x180037d74  lea     rdx, [rsp+0F8h+pPrinterName]
0x180037d79  cmp     [rsp+0F8h+var_80], 7
0x180037d7f  cmova   rdx, [rsp+0F8h+pPrinterName]; pPrinterName
0x180037d85  mov     r8, rbx; unsigned __int16 *
0x180037d88  mov     rcx, r14; this
0x180037d8b  call    ?UninstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG0@Z; VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(ushort const *,ushort const *)
0x180037d90  jmp     loc_180037EDA
0x180037d95  cmp     qword ptr [rbx+18h], 7
0x180037d9a  jbe     short loc_180037DA1
0x180037d9c  mov     r8, [rbx]
0x180037d9f  jmp     short loc_180037DA4
0x180037da1  mov     r8, rbx
0x180037da4  lea     rdx, aPrinterNotFoun; "Printer not found. Port Name: %ws"
0x180037dab  lea     rcx, aVirtualmonVirt_0; "VirtualMon::VirtualPrinterInstaller::Un"...
0x180037db2  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037db7  mov     [rsp+0F8h+var_D8], 0
0x180037dbf  xorps   xmm0, xmm0
0x180037dc2  movdqu  [rsp+0F8h+var_C8], xmm0
0x180037dc8  mov     [rsp+0F8h+var_B8], 0
0x180037dd1  lea     r8, [rsp+0F8h+var_C8]
0x180037dd6  lea     rdx, [rsp+0F8h+var_D8]
0x180037ddb  mov     rcx, r14
0x180037dde  call    ?EnumeratePrinters@VirtualPrinterInstaller@VirtualMon@@AEAAXAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z; VirtualMon::VirtualPrinterInstaller::EnumeratePrinters(ulong &,std::vector<uchar> &)
0x180037de3  mov     r15, qword ptr [rsp+0F8h+var_C8]
0x180037de8  xor     edi, edi
0x180037dea  cmp     edi, [rsp+0F8h+var_D8]
0x180037dee  jnb     loc_180037ECF
0x180037df4  mov     eax, edi
0x180037df6  imul    rsi, rax, 88h
0x180037dfd  mov     r9, [rsi+r15+18h]
0x180037e02  mov     r8, [rsi+r15+8]
0x180037e07  lea     rdx, aPrinterNameWsP; "Printer Name: %ws. Port Name: %ws"
0x180037e0e  lea     rcx, aVirtualmonVirt_0; "VirtualMon::VirtualPrinterInstaller::Un"...
0x180037e15  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x180037e1a  cmp     qword ptr [rbx+18h], 7
0x180037e1f  jbe     short loc_180037E26
0x180037e21  mov     rcx, [rbx]
0x180037e24  jmp     short loc_180037E29
0x180037e26  mov     rcx, rbx
0x180037e29  mov     rax, [rsi+r15+18h]
0x180037e2e  sub     rcx, rax
0x180037e31  movzx   r8d, word ptr [rax]
0x180037e35  movzx   edx, word ptr [rax+rcx]
0x180037e39  sub     r8d, edx
0x180037e3c  jnz     short loc_180037E46
0x180037e3e  add     rax, 2
0x180037e42  test    edx, edx
0x180037e44  jnz     short loc_180037E31
0x180037e46  test    r8d, r8d
0x180037e49  jnz     short loc_180037EC8
0x180037e4b  mov     rsi, [rsi+r15+8]
0x180037e50  lea     r8, asc_18004E4AC; ":"
0x180037e57  mov     rdx, r12
0x180037e5a  lea     rcx, [rsp+0F8h+var_58]
0x180037e62  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@QEBG@Z; std::operator+<ushort>(std::wstring const &,ushort const * const)
0x180037e67  nop
0x180037e68  mov     r8, rsi
0x180037e6b  mov     rdx, rax
0x180037e6e  lea     rcx, [rsp+0F8h+var_78]
0x180037e76  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@QEBG@Z; std::operator+<ushort>(std::wstring &&,ushort const * const)
0x180037e7b  nop
0x180037e7c  lea     rcx, [rsp+0F8h+var_58]
0x180037e84  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037e89  cmp     qword ptr [rbx+18h], 7
0x180037e8e  jbe     short loc_180037E95
0x180037e90  mov     r8, [rbx]
0x180037e93  jmp     short loc_180037E98
0x180037e95  mov     r8, rbx; unsigned __int16 *
0x180037e98  lea     rdx, [rsp+0F8h+var_78]
0x180037ea0  cmp     [rsp+0F8h+var_60], 7
0x180037ea9  cmova   rdx, [rsp+0F8h+var_78]; pPrinterName
0x180037eb2  mov     rcx, r14; this
0x180037eb5  call    ?UninstallVirtualPrinter@VirtualPrinterInstaller@VirtualMon@@AEAAXPEBG0@Z; VirtualMon::VirtualPrinterInstaller::UninstallVirtualPrinter(ushort const *,ushort const *)
0x180037eba  nop
0x180037ebb  lea     rcx, [rsp+0F8h+var_78]
0x180037ec3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037ec8  inc     edi
0x180037eca  jmp     loc_180037DEA
0x180037ecf  lea     rcx, [rsp+0F8h+var_C8]
0x180037ed4  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180037ed9  nop
0x180037eda  lea     rcx, [rsp+0F8h+pPrinterName]
0x180037edf  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180037ee4  nop
0x180037ee5  lea     rcx, [rsp+0F8h+hPrinter]
0x180037eea  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?ClosePrinter@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,int (*)(void *),&ClosePrinter(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180037eef  xor     eax, eax
0x180037ef1  jmp     short loc_180037EF7
0x180037ef3  mov     eax, [rsp+0F8h+var_D8]
0x180037ef7  mov     rcx, [rsp+0F8h+var_38]
0x180037eff  xor     rcx, rsp; StackCookie
0x180037f02  call    __security_check_cookie
0x180037f07  mov     rbx, [rsp+0F8h+arg_10]
0x180037f0f  add     rsp, 0D0h
0x180037f16  pop     r15
0x180037f18  pop     r14
0x180037f1a  pop     r12
0x180037f1c  pop     rdi
0x180037f1d  pop     rsi
0x180037f1e  retn
```
