# VirtualMon::VirtualPrinterInstaller::EnumeratePrinters(ulong &,std::vector<uchar,std::allocator<uchar>> &)

- ea: `0x180036834`
- end: `0x180036a2c`
- name: `?EnumeratePrinters@VirtualPrinterInstaller@VirtualMon@@AEAAXAEAKAEAV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `504`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `12`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180037020`
- `0x180037c78`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18000f8a8`
- `0x180012498`
- `0x18001cf80`
- `0x18001d058`
- `0x18001d0a0`
- `0x1800291d0`
- `0x180030940`
- `0x180036834`
- `0x1800371a8`
- `0x180038174`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368ea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800368ea`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800369cb`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800369cb`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x1800368dc`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18003696c`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x1800368dc`
- `ext-ms-win-printer-winspool-core-l1-1-0!EnumPrintersW` at `0x18003696c`

## string_xrefs

- `0x180036881`: `ImpersonateUser failed!`
- `0x180036890`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036985`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800369e4`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x180036a1a`: `onecore\printscan\print\lib\virtualprinterinstallation\lib\virtualprinterinstaller.cpp`
- `0x1800369b7`: `No printers are installed`
- `0x1800369a4`: `VirtualMon::VirtualPrinterInstaller::EnumeratePrinters`
- `0x1800369be`: `VirtualMon::VirtualPrinterInstaller::EnumeratePrinters`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall VirtualMon::VirtualPrinterInstaller::EnumeratePrinters(__int64 a1, DWORD *a2, __int64 a3)
{
  _QWORD *v5; // rdx
  unsigned int v6; // eax
  LPBYTE v7; // rdx
  __int64 v8; // rsi
  unsigned __int64 v9; // rcx
  BYTE *v10; // rax
  size_t v11; // rbx
  unsigned int v12; // eax
  unsigned int v13; // eax
  const char *cbBuf; // [rsp+20h] [rbp-60h]
  const char *pcbNeeded; // [rsp+28h] [rbp-58h]
  const char *pcbNeededa; // [rsp+28h] [rbp-58h]
  const char *pcbNeededb; // [rsp+28h] [rbp-58h]
  DWORD v19; // [rsp+40h] [rbp-40h] BYREF
  DWORD pcReturned; // [rsp+44h] [rbp-3Ch] BYREF
  char v21; // [rsp+49h] [rbp-37h]
  _BYTE v22[32]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]

  v5 = (_QWORD *)(a1 + 128);
  if ( *(_QWORD *)(a1 + 152) > 7u )
    v5 = (_QWORD *)*v5;
  std::wstring::wstring((__int64)v22, (__int64)v5);
  v6 = PrintCore::UserImpersonationHelpers::ImpersonateUser((__int64)v22);
  wil::details::in1diag3::Throw_IfFailedMsg(
    retaddr,
    (void *)0xFA,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
    (const char *)v6,
    (int)"ImpersonateUser failed!",
    pcbNeeded);
  std::wstring::_Tidy_deallocate(v22);
  v21 = 1;
  *a2 = 0;
  v19 = 0;
  pcReturned = 0;
  if ( EnumPrintersW(0xAu, 0, 2u, 0, 0, &v19, &pcReturned) )
  {
    if ( !v19 )
    {
      VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
        "VirtualMon::VirtualPrinterInstaller::EnumeratePrinters",
        L"No printers are installed");
      goto LABEL_15;
    }
LABEL_16:
    wil::details::in1diag3::Throw_GetLastErrorMsg(
      retaddr,
      (void *)0x112,
      (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
      "EnumPrinters (no buffer) failed!",
      cbBuf);
  }
  if ( GetLastError() != 122 )
    goto LABEL_16;
  v7 = *(LPBYTE *)a3;
  v8 = *(_QWORD *)(a3 + 8);
  v9 = v8 - *(_QWORD *)a3;
  if ( v19 < v9 )
  {
    v10 = &v7[v19];
LABEL_11:
    *(_QWORD *)(a3 + 8) = v10;
    goto LABEL_12;
  }
  if ( v19 > v9 )
  {
    if ( (unsigned __int64)v19 <= *(_QWORD *)(a3 + 16) - (_QWORD)v7 )
    {
      v11 = v19 - v9;
      memset_0(*(void **)(a3 + 8), 0, v11);
      v10 = (BYTE *)(v11 + v8);
      goto LABEL_11;
    }
    std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, v19);
  }
LABEL_12:
  v12 = EnumPrintersW(0xAu, 0, 2u, *(LPBYTE *)a3, v19, &v19, &pcReturned);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x108,
    (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
    (const char *)v12,
    (int)"EnumPrinters (with buffer) failed!",
    pcbNeededb);
  *a2 = pcReturned;
  VirtualPrintDEHTelemetry::WriteDbgTraceInfo(
    "VirtualMon::VirtualPrinterInstaller::EnumeratePrinters",
    L"Enumerate Printers: %d");
LABEL_15:
  v13 = RevertToSelf();
  return wil::details::in1diag3::Log_IfWin32BoolFalseMsg(
           retaddr,
           (void *)0xFD,
           (unsigned int)"onecore\\printscan\\print\\lib\\virtualprinterinstallation\\lib\\virtualprinterinstaller.cpp",
           (const char *)v13,
           (int)"RevertToSelf failed!",
           pcbNeededa);
}

```

## disassembly

```asm
0x180036834  push    rbp
0x180036836  push    rbx
0x180036837  push    rsi
0x180036838  push    rdi
0x180036839  push    r14
0x18003683b  mov     rbp, rsp
0x18003683e  sub     rsp, 80h
0x180036845  mov     rax, cs:__security_cookie
0x18003684c  xor     rax, rsp
0x18003684f  mov     [rbp+var_10], rax
0x180036853  mov     rdi, r8
0x180036856  mov     r14, rdx
0x180036859  lea     rdx, [rcx+80h]
0x180036860  cmp     qword ptr [rdx+18h], 7
0x180036865  jbe     short loc_18003686A
0x180036867  mov     rdx, [rdx]
0x18003686a  lea     rcx, [rbp+var_30]
0x18003686e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180036873  nop
0x180036874  lea     rcx, [rbp+var_30]
0x180036878  call    ?ImpersonateUser@UserImpersonationHelpers@PrintCore@@SAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; PrintCore::UserImpersonationHelpers::ImpersonateUser(std::wstring const &)
0x18003687d  mov     rcx, [rbp+28h]; this
0x180036881  lea     rdx, aImpersonateuse_1; "ImpersonateUser failed!"
0x180036888  mov     qword ptr [rsp+80h+cbBuf], rdx; int
0x18003688d  mov     r9d, eax; char *
0x180036890  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036897  mov     edx, 0FAh; void *
0x18003689c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800368a1  nop
0x1800368a2  lea     rcx, [rbp+var_30]
0x1800368a6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800368ab  mov     [rbp+var_37], 1
0x1800368af  xor     ebx, ebx
0x1800368b1  mov     [r14], ebx
0x1800368b4  mov     [rbp+var_40], ebx
0x1800368b7  mov     [rbp+var_3C], ebx
0x1800368ba  lea     rax, [rbp+var_3C]
0x1800368be  mov     [rsp+80h+pcReturned], rax; pcReturned
0x1800368c3  lea     rax, [rbp+var_40]
0x1800368c7  mov     [rsp+80h+pcbNeeded], rax; char *
0x1800368cc  mov     [rsp+80h+cbBuf], ebx; char *
0x1800368d0  xor     r9d, r9d; pPrinterEnum
0x1800368d3  xor     edx, edx; Name
0x1800368d5  lea     ecx, [rbx+0Ah]; Flags
0x1800368d8  lea     r8d, [rbx+2]; Level
0x1800368dc  call    cs:__imp_EnumPrintersW
0x1800368e2  test    eax, eax
0x1800368e4  jnz     loc_1800369B2
0x1800368ea  call    cs:__imp_GetLastError
0x1800368f0  cmp     eax, 7Ah ; 'z'
0x1800368f3  jnz     loc_180036A0F
0x1800368f9  mov     ebx, [rbp+var_40]
0x1800368fc  mov     rdx, [rdi]
0x1800368ff  mov     rsi, [rdi+8]
0x180036903  mov     rcx, rsi
0x180036906  sub     rcx, rdx
0x180036909  cmp     rbx, rcx
0x18003690c  jnb     short loc_180036914
0x18003690e  lea     rax, [rdx+rbx]
0x180036912  jmp     short loc_180036943
0x180036914  jbe     short loc_180036947
0x180036916  mov     rax, [rdi+10h]
0x18003691a  sub     rax, rdx
0x18003691d  cmp     rbx, rax
0x180036920  jbe     short loc_18003692F
0x180036922  mov     rdx, rbx
0x180036925  mov     rcx, rdi
0x180036928  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18003692d  jmp     short loc_180036947
0x18003692f  sub     rbx, rcx
0x180036932  mov     r8, rbx; Size
0x180036935  xor     edx, edx; Val
0x180036937  mov     rcx, rsi; void *
0x18003693a  call    memset_0
0x18003693f  lea     rax, [rbx+rsi]
0x180036943  mov     [rdi+8], rax
0x180036947  mov     eax, [rbp+var_40]
0x18003694a  lea     rdx, [rbp+var_3C]
0x18003694e  mov     [rsp+80h+pcReturned], rdx; pcReturned
0x180036953  lea     rdx, [rbp+var_40]
0x180036957  mov     [rsp+80h+pcbNeeded], rdx; char *
0x18003695c  mov     [rsp+80h+cbBuf], eax; cbBuf
0x180036960  mov     r9, [rdi]; pPrinterEnum
0x180036963  xor     edx, edx; Name
0x180036965  lea     ecx, [rdx+0Ah]; Flags
0x180036968  lea     r8d, [rdx+2]; Level
0x18003696c  call    cs:__imp_EnumPrintersW
0x180036972  mov     rcx, [rbp+28h]; this
0x180036976  lea     rdx, aEnumprintersWi; "EnumPrinters (with buffer) failed!"
0x18003697d  mov     qword ptr [rsp+80h+cbBuf], rdx; int
0x180036982  mov     r9d, eax; char *
0x180036985  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x18003698c  mov     edx, 108h; void *
0x180036991  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180036996  mov     r8d, [rbp+var_3C]
0x18003699a  mov     [r14], r8d
0x18003699d  lea     rdx, aEnumeratePrint; "Enumerate Printers: %d"
0x1800369a4  lea     rcx, aVirtualmonVirt_7; "VirtualMon::VirtualPrinterInstaller::En"...
0x1800369ab  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800369b0  jmp     short loc_1800369CB
0x1800369b2  cmp     [rbp+var_40], ebx
0x1800369b5  jnz     short loc_180036A0F
0x1800369b7  lea     rdx, aNoPrintersAreI; "No printers are installed"
0x1800369be  lea     rcx, aVirtualmonVirt_7; "VirtualMon::VirtualPrinterInstaller::En"...
0x1800369c5  call    ?WriteDbgTraceInfo@VirtualPrintDEHTelemetry@@SAXPEADPEAGZZ; VirtualPrintDEHTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1800369ca  nop
0x1800369cb  call    cs:__imp_RevertToSelf
0x1800369d1  mov     rcx, [rbp+28h]; this
0x1800369d5  lea     rdx, aReverttoselfFa; "RevertToSelf failed!"
0x1800369dc  mov     qword ptr [rsp+80h+cbBuf], rdx; int
0x1800369e1  mov     r9d, eax; char *
0x1800369e4  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x1800369eb  mov     edx, 0FDh; void *
0x1800369f0  call    ?Log_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Log_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800369f5  mov     rcx, [rbp+var_10]
0x1800369f9  xor     rcx, rsp; StackCookie
0x1800369fc  call    __security_check_cookie
0x180036a01  add     rsp, 80h
0x180036a08  pop     r14
0x180036a0a  pop     rdi
0x180036a0b  pop     rsi
0x180036a0c  pop     rbx
0x180036a0d  pop     rbp
0x180036a0e  retn
0x180036a0f  mov     rcx, [rbp+28h]; this
0x180036a13  lea     r9, aEnumprintersNo; "EnumPrinters (no buffer) failed!"
0x180036a1a  lea     r8, aOnecorePrintsc_0; "onecore\\printscan\\print\\lib\\virtual"...
0x180036a21  mov     edx, 112h; void *
0x180036a26  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
```
