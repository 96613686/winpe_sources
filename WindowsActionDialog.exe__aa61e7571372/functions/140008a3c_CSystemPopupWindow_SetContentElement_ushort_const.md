# CSystemPopupWindow::_SetContentElement(ushort const *)

- ea: `0x140008a3c`
- end: `0x140008d41`
- name: `?_SetContentElement@CSystemPopupWindow@@AEAAJPEBG@Z`
- size: `773`
- prototype: `__int64 __fastcall(CSystemPopupWindow *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140008124`

## callees

- `0x140001460`
- `0x1400080c8`
- `0x1400080f4`
- `0x140008a3c`
- `0x14000a010`

## import_xrefs

- `KERNEL32!GetModuleHandleExW` at `0x140008ad4`
- `KERNEL32!GetModuleHandleExW` at `0x140008ad4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008afe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008b5c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008bd4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008c85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008ce5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008d09`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008afe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008b5c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008bd4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008c85`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008ce5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140008d09`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140008ba6`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x140008ba6`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x140008b2e`
- `DUI70!?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z` at `0x140008b2e`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x140008c75`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x140008c75`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008b0d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008b6b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008be3`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008c94`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008cf4`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008d18`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008b0d`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008b6b`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008be3`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008c94`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008cf4`
- `DUI70!?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ` at `0x140008d18`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x140008bfc`
- `DUI70!?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z` at `0x140008bfc`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x140008c24`
- `DUI70!?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z` at `0x140008c24`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x140008c1a`
- `DUI70!?_ZeroRelease@Value@DirectUI@@AEAAXXZ` at `0x140008c48`
- `DUI70!?_ZeroRelease@Value@DirectUI@@AEAAXXZ` at `0x140008c48`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x140008a88`
- `DUI70!?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z` at `0x140008a88`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CSystemPopupWindow::_SetContentElement(CSystemPopupWindow *this, const unsigned __int16 *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  DirectUI::DUIXmlParser *v7; // rbx
  const char *v8; // r9
  unsigned int LastError; // edi
  int v10; // eax
  int v11; // eax
  DirectUI::Element *v12; // r14
  struct DirectUI::Value *String; // rax
  DirectUI::Value *v14; // rsi
  int v15; // eax
  int v16; // [rsp+20h] [rbp-40h]
  int v17; // [rsp+20h] [rbp-40h]
  struct DirectUI::DUIXmlParser *v18; // [rsp+40h] [rbp-20h] BYREF
  HMODULE phModule; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v18 = 0;
  v4 = DirectUI::DUIXmlParser::Create(&v18, 0, 0, 0, 0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v4,
      v16);
    return v5;
  }
  v7 = v18;
  phModule = 0;
  if ( !GetModuleHandleExW(4u, (LPCWSTR)CSystemPopupWindow::_OnCommand, &phModule) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x82,
                  (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
                  v8);
    if ( phModule )
      FreeLibrary(phModule);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
    return LastError;
  }
  v10 = DirectUI::DUIXmlParser::SetXMLFromResource(v7, 0xC9u, phModule, (HINSTANCE)0x140000000LL);
  LastError = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x83,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v10,
      v16);
    if ( phModule )
      FreeLibrary(phModule);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
    return LastError;
  }
  v18 = 0;
  v11 = DirectUI::DUIXmlParser::CreateElement(v7, L"PlatformRoot", 0, 0, 0, &v18);
  LastError = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x88,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v11,
      v17);
    if ( phModule )
      FreeLibrary(phModule);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
    return LastError;
  }
  v12 = v18;
  String = DirectUI::Value::CreateString(a2, 0);
  v14 = String;
  if ( !String )
  {
    LastError = -2147024882;
LABEL_27:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8B,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)LastError,
      v17);
    if ( v12 )
      DirectUI::Element::Destroy(v12, 1);
    if ( phModule )
      FreeLibrary(phModule);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
    return LastError;
  }
  LastError = DirectUI::Element::SetValue(
                v12,
                (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ContentProp,
                1,
                String);
  if ( (*(_DWORD *)v14 & 0xFFFFFF80) != 0xFFFFFF80
    && ((_InterlockedExchangeAdd((volatile signed __int32 *)v14, 0xFFFFFF80) - 128) & 0xFFFFFF80) == 0 )
  {
    DirectUI::Value::_ZeroRelease(v14);
  }
  if ( (LastError & 0x80000000) != 0 )
    goto LABEL_27;
  v15 = (*(__int64 (__fastcall **)(_QWORD, DirectUI::Element *))(**(_QWORD **)this + 352LL))(*(_QWORD *)this, v12);
  LastError = v15;
  if ( v15 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x8C,
      (unsigned int)"drivers\\mobilepc\\location\\product\\winactiondialog\\lib\\popupwindow.cpp",
      (const char *)(unsigned int)v15,
      v17);
    if ( phModule )
      FreeLibrary(phModule);
    if ( v7 )
      DirectUI::DUIXmlParser::Destroy(v7);
    return LastError;
  }
  if ( phModule )
    FreeLibrary(phModule);
  if ( v7 )
    DirectUI::DUIXmlParser::Destroy(v7);
  return 0;
}

```

## disassembly

```asm
0x140008a3c  mov     [rsp-28h+arg_10], rbx
0x140008a41  push    rbp
0x140008a42  push    rsi
0x140008a43  push    rdi
0x140008a44  push    r14
0x140008a46  push    r15
0x140008a48  mov     rbp, rsp
0x140008a4b  sub     rsp, 60h
0x140008a4f  mov     rax, cs:__security_cookie
0x140008a56  xor     rax, rsp
0x140008a59  mov     [rbp+var_10], rax
0x140008a5d  mov     rsi, rdx
0x140008a60  mov     r15, rcx
0x140008a63  mov     [rbp+var_28], 0
0x140008a6b  mov     [rbp+var_20], 0
0x140008a73  mov     qword ptr [rsp+60h+var_40], 0; int
0x140008a7c  xor     r9d, r9d
0x140008a7f  xor     r8d, r8d
0x140008a82  xor     edx, edx
0x140008a84  lea     rcx, [rbp+var_20]
0x140008a88  call    cs:__imp_?Create@DUIXmlParser@DirectUI@@SAJPEAPEAV12@P6APEAVValue@2@PEBGPEAX@Z2P6AX11H2@Z2@Z; DirectUI::DUIXmlParser::Create(DirectUI::DUIXmlParser * *,DirectUI::Value * (*)(ushort const *,void *),void *,void (*)(ushort const *,ushort const *,int,void *),void *)
0x140008a8e  mov     ebx, eax
0x140008a90  test    eax, eax
0x140008a92  jns     short loc_140008AB4
0x140008a94  mov     rcx, [rbp+28h]; this
0x140008a98  mov     r9d, eax; char *
0x140008a9b  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008aa2  mov     edx, 7Ch ; '|'; void *
0x140008aa7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008aac  nop
0x140008aad  mov     eax, ebx
0x140008aaf  jmp     loc_140008D21
0x140008ab4  mov     rbx, [rbp+var_20]
0x140008ab8  mov     [rbp+var_28], rbx
0x140008abc  mov     [rbp+phModule], 0
0x140008ac4  lea     r8, [rbp+phModule]; phModule
0x140008ac8  lea     rdx, ?_OnCommand@CSystemPopupWindow@@CAJPEAUIPopupWindow@@PEAUIPopupCommand@@PEAX@Z; lpModuleName
0x140008acf  mov     ecx, 4; dwFlags
0x140008ad4  call    cs:__imp_GetModuleHandleExW
0x140008ada  test    eax, eax
0x140008adc  jnz     short loc_140008B1B
0x140008ade  mov     rcx, [rbp+28h]; this
0x140008ae2  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008ae9  mov     edx, 82h; void *
0x140008aee  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140008af3  mov     edi, eax
0x140008af5  mov     rcx, [rbp+phModule]; hLibModule
0x140008af9  test    rcx, rcx
0x140008afc  jz      short loc_140008B05
0x140008afe  call    cs:__imp_FreeLibrary
0x140008b04  nop
0x140008b05  test    rbx, rbx
0x140008b08  jz      short loc_140008B14
0x140008b0a  mov     rcx, rbx
0x140008b0d  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008b13  nop
0x140008b14  mov     eax, edi
0x140008b16  jmp     loc_140008D21
0x140008b1b  lea     r9, cs:140000000h
0x140008b22  mov     r8, [rbp+phModule]
0x140008b26  mov     edx, 0C9h
0x140008b2b  mov     rcx, rbx
0x140008b2e  call    cs:__imp_?SetXMLFromResource@DUIXmlParser@DirectUI@@QEAAJIPEAUHINSTANCE__@@0@Z; DirectUI::DUIXmlParser::SetXMLFromResource(uint,HINSTANCE__ *,HINSTANCE__ *)
0x140008b34  mov     edi, eax
0x140008b36  test    eax, eax
0x140008b38  jns     short loc_140008B74
0x140008b3a  mov     rcx, [rbp+28h]; this
0x140008b3e  mov     r9d, eax; char *
0x140008b41  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008b48  mov     edx, 83h; void *
0x140008b4d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008b52  nop
0x140008b53  mov     rcx, [rbp+phModule]; hLibModule
0x140008b57  test    rcx, rcx
0x140008b5a  jz      short loc_140008B63
0x140008b5c  call    cs:__imp_FreeLibrary
0x140008b62  nop
0x140008b63  test    rbx, rbx
0x140008b66  jz      short loc_140008B72
0x140008b68  mov     rcx, rbx
0x140008b6b  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008b71  nop
0x140008b72  jmp     short loc_140008B14
0x140008b74  mov     [rbp+var_30], 0
0x140008b7c  mov     [rbp+var_20], 0
0x140008b84  lea     rax, [rbp+var_20]
0x140008b88  mov     [rsp+60h+var_38], rax
0x140008b8d  mov     qword ptr [rsp+60h+var_40], 0; int
0x140008b96  xor     r9d, r9d
0x140008b99  xor     r8d, r8d
0x140008b9c  lea     rdx, aPlatformroot; "PlatformRoot"
0x140008ba3  mov     rcx, rbx
0x140008ba6  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x140008bac  mov     edi, eax
0x140008bae  test    eax, eax
0x140008bb0  jns     short loc_140008BEF
0x140008bb2  mov     rcx, [rbp+28h]; this
0x140008bb6  mov     r9d, eax; char *
0x140008bb9  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008bc0  mov     edx, 88h; void *
0x140008bc5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008bca  nop
0x140008bcb  mov     rcx, [rbp+phModule]; hLibModule
0x140008bcf  test    rcx, rcx
0x140008bd2  jz      short loc_140008BDB
0x140008bd4  call    cs:__imp_FreeLibrary
0x140008bda  nop
0x140008bdb  test    rbx, rbx
0x140008bde  jz      short loc_140008BEA
0x140008be0  mov     rcx, rbx
0x140008be3  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008be9  nop
0x140008bea  jmp     loc_140008B14
0x140008bef  mov     r14, [rbp+var_20]
0x140008bf3  mov     [rbp+var_30], r14
0x140008bf7  xor     edx, edx
0x140008bf9  mov     rcx, rsi
0x140008bfc  call    cs:__imp_?CreateString@Value@DirectUI@@SAPEAV12@PEBGPEAUHINSTANCE__@@@Z; DirectUI::Value::CreateString(ushort const *,HINSTANCE__ *)
0x140008c02  mov     rsi, rax
0x140008c05  test    rax, rax
0x140008c08  jnz     short loc_140008C11
0x140008c0a  mov     edi, 8007000Eh
0x140008c0f  jmp     short loc_140008C52
0x140008c11  mov     r9, rsi
0x140008c14  mov     r8d, 1
0x140008c1a  mov     rdx, cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x140008c21  mov     rcx, r14
0x140008c24  call    cs:__imp_?SetValue@Element@DirectUI@@QEAAJP6APEBUPropertyInfo@2@XZHPEAVValue@2@@Z; DirectUI::Element::SetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::Value *)
0x140008c2a  mov     edi, eax
0x140008c2c  mov     eax, [rsi]
0x140008c2e  mov     ecx, 0FFFFFF80h
0x140008c33  and     eax, ecx
0x140008c35  cmp     eax, ecx
0x140008c37  jz      short loc_140008C4E
0x140008c39  mov     eax, ecx
0x140008c3b  lock xadd [rsi], eax
0x140008c3f  add     eax, ecx
0x140008c41  test    ecx, eax
0x140008c43  jnz     short loc_140008C4E
0x140008c45  mov     rcx, rsi
0x140008c48  call    cs:__imp_?_ZeroRelease@Value@DirectUI@@AEAAXXZ; DirectUI::Value::_ZeroRelease(void)
0x140008c4e  test    edi, edi
0x140008c50  jns     short loc_140008CA0
0x140008c52  mov     rcx, [rbp+28h]; this
0x140008c56  mov     r9d, edi; char *
0x140008c59  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008c60  mov     edx, 8Bh; void *
0x140008c65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008c6a  nop
0x140008c6b  test    r14, r14
0x140008c6e  jz      short loc_140008C7C
0x140008c70  mov     dl, 1
0x140008c72  mov     rcx, r14
0x140008c75  call    cs:__imp_?Destroy@Element@DirectUI@@QEAAJ_N@Z; DirectUI::Element::Destroy(bool)
0x140008c7b  nop
0x140008c7c  mov     rcx, [rbp+phModule]; hLibModule
0x140008c80  test    rcx, rcx
0x140008c83  jz      short loc_140008C8C
0x140008c85  call    cs:__imp_FreeLibrary
0x140008c8b  nop
0x140008c8c  test    rbx, rbx
0x140008c8f  jz      short loc_140008C9B
0x140008c91  mov     rcx, rbx
0x140008c94  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008c9a  nop
0x140008c9b  jmp     loc_140008B14
0x140008ca0  mov     rcx, [r15]
0x140008ca3  mov     [rbp+var_30], 0
0x140008cab  mov     rax, [rcx]
0x140008cae  mov     rdx, r14
0x140008cb1  mov     rax, [rax+160h]
0x140008cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008cbd  mov     edi, eax
0x140008cbf  test    eax, eax
0x140008cc1  jns     short loc_140008D00
0x140008cc3  mov     rcx, [rbp+28h]; this
0x140008cc7  mov     r9d, eax; char *
0x140008cca  lea     r8, aDriversMobilep_1; "drivers\\mobilepc\\location\\product\\w"...
0x140008cd1  mov     edx, 8Ch; void *
0x140008cd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008cdb  nop
0x140008cdc  mov     rcx, [rbp+phModule]; hLibModule
0x140008ce0  test    rcx, rcx
0x140008ce3  jz      short loc_140008CEC
0x140008ce5  call    cs:__imp_FreeLibrary
0x140008ceb  nop
0x140008cec  test    rbx, rbx
0x140008cef  jz      short loc_140008CFB
0x140008cf1  mov     rcx, rbx
0x140008cf4  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008cfa  nop
0x140008cfb  jmp     loc_140008B14
0x140008d00  mov     rcx, [rbp+phModule]; hLibModule
0x140008d04  test    rcx, rcx
0x140008d07  jz      short loc_140008D10
0x140008d09  call    cs:__imp_FreeLibrary
0x140008d0f  nop
0x140008d10  test    rbx, rbx
0x140008d13  jz      short loc_140008D1F
0x140008d15  mov     rcx, rbx
0x140008d18  call    cs:__imp_?Destroy@DUIXmlParser@DirectUI@@QEAAXXZ; DirectUI::DUIXmlParser::Destroy(void)
0x140008d1e  nop
0x140008d1f  xor     eax, eax
0x140008d21  mov     rcx, [rbp+var_10]
0x140008d25  xor     rcx, rsp; StackCookie
0x140008d28  call    __security_check_cookie
0x140008d2d  mov     rbx, [rsp+60h+arg_10]
0x140008d35  add     rsp, 60h
0x140008d39  pop     r15
0x140008d3b  pop     r14
0x140008d3d  pop     rdi
0x140008d3e  pop     rsi
0x140008d3f  pop     rbp
0x140008d40  retn
```
