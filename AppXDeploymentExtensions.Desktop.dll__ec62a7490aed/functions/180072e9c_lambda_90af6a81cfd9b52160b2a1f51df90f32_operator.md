# _lambda_90af6a81cfd9b52160b2a1f51df90f32_::operator()

- ea: `0x180072e9c`
- end: `0x18007319a`
- name: `_lambda_90af6a81cfd9b52160b2a1f51df90f32_::operator()`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, installer_update`

## callers

- `0x180132d60`

## callees

- `0x180015590`
- `0x180064a88`
- `0x180071ef0`
- `0x1800720f0`
- `0x180072114`
- `0x180072e9c`
- `0x1800731a0`
- `0x1800aed10`
- `0x1800af1bc`
- `0x1800af6f8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007313e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180072ffd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007313e`
- `WINSPOOL!OpenPrinterW` at `0x180072f88`
- `WINSPOOL!OpenPrinterW` at `0x180072f88`
- `WINSPOOL!GetPrinterW` at `0x180072fd2`
- `WINSPOOL!GetPrinterW` at `0x180073087`
- `WINSPOOL!GetPrinterW` at `0x180072fd2`
- `WINSPOOL!GetPrinterW` at `0x180073087`
- `WINSPOOL!SetPrinterW` at `0x180073123`
- `WINSPOOL!SetPrinterW` at `0x180073123`

## string_xrefs

- `0x180072eff`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x180072f67`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x180072fe8`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x18007302e`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x18007309e`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800730c4`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800730f5`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x18007315d`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`

## pseudocode

```c
BOOL __fastcall lambda_90af6a81cfd9b52160b2a1f51df90f32_::operator()(__int64 a1)
{
  LPDWORD *v1; // rdx
  const struct AppMon::APPINFO **v2; // rbx
  const struct AppMon::APPINFO *v5; // r9
  int v6; // eax
  BOOL result; // eax
  signed int LastError; // eax
  char v9; // cl
  const unsigned __int16 **v10; // rax
  void **v11; // rcx
  const unsigned __int16 **v12; // rdi
  void *v13; // rax
  AppMon::AppPrinterInstaller *v14; // rcx
  const char *v15; // r9
  int v16; // eax
  unsigned int AppmonPort; // eax
  AppMon::AppPrinterInstaller *v18; // rcx
  signed int v19; // eax
  int pcbNeeded; // [rsp+20h] [rbp-E0h]
  LPDWORD pcbNeededa; // [rsp+20h] [rbp-E0h]
  int pcbNeededb; // [rsp+20h] [rbp-E0h]
  int pcbNeededc; // [rsp+20h] [rbp-E0h]
  DWORD cbBuf; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE phPrinter; // [rsp+38h] [rbp-C8h] BYREF
  struct _PRINTER_DEFAULTSW pDefault; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pPrinterName[528]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+4A8h] [rbp+3A8h]

  v1 = *(LPDWORD **)a1;
  v2 = (const struct AppMon::APPINFO **)(a1 + 8);
  if ( !**(_QWORD **)a1 || *v2 == (const struct AppMon::APPINFO *)-256LL )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDF,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      (const char *)0x80070057LL,
      pcbNeeded);
  v5 = *v2;
  phPrinter = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 983052;
  *(_OWORD *)&pDefault.pDatatype = 0;
  pcbNeededa = *v1;
  v6 = StringCchPrintfW(pPrinterName, 0x209u, L"%s:%s", (char *)v5 + 1556);
  if ( v6 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      (const char *)(unsigned int)v6,
      (int)pcbNeededa);
  result = OpenPrinterW(pPrinterName, &phPrinter, &pDefault);
  if ( result )
  {
    std::unique_ptr<void,AppMon::PrintHandleCloser>::reset(*(_QWORD *)(a1 + 16), phPrinter);
    cbBuf = 0;
    if ( GetPrinterW(phPrinter, 5u, 0, 0, &cbBuf) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
        (const char *)0x8000FFFFLL,
        pcbNeededb);
    LastError = GetLastError();
    if ( LastError == 122 )
    {
      v9 = 0;
    }
    else
    {
      v9 = 1;
      if ( LastError <= 0 )
      {
LABEL_16:
        if ( v9 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xF6,
            (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
            (const char *)(unsigned int)LastError,
            pcbNeededb);
        v10 = (const unsigned __int16 **)operator new[](cbBuf);
        v11 = *(void ***)(a1 + 24);
        v12 = v10;
        v13 = *v11;
        *v11 = v12;
        if ( v13 )
          operator delete(v13, (const struct std::nothrow_t *)1);
        if ( !GetPrinterW(phPrinter, 5u, (LPBYTE)v12, cbBuf, &cbBuf) )
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xFC,
            (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
            v15);
        v16 = AppMon::AppPrinterInstaller::RemoveAppmonPort(v14, v12[1]);
        if ( v16 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x100,
            (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
            (const char *)(unsigned int)v16,
            pcbNeededc);
        AppmonPort = AppMon::AppPrinterInstaller::CreateAppmonPort(*(AppMon::AppPrinterInstaller **)(a1 + 32), *v2);
        if ( AppmonPort && AppmonPort != -2147024713 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x104,
            (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
            (const char *)AppmonPort,
            pcbNeededc);
        v12[1] = (const unsigned __int16 *)((char *)*v2 + 256);
        result = SetPrinterW(phPrinter, 5u, (LPBYTE)v12, 0);
        if ( !result )
        {
          AppMon::AppPrinterInstaller::RemoveAppmonPort(v18, (const unsigned __int16 *)*v2 + 128);
          v19 = GetLastError();
          if ( v19 > 0 )
            v19 = (unsigned __int16)v19 | 0x80070000;
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x10D,
            (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
            (const char *)(unsigned int)v19,
            pcbNeededc);
        }
        return result;
      }
    }
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_16;
  }
  return result;
}

```

## disassembly

```asm
0x180072e9c  mov     [rsp-8+arg_8], rbx
0x180072ea1  mov     [rsp-8+arg_10], rsi
0x180072ea6  push    rbp
0x180072ea7  push    rdi
0x180072ea8  push    r15
0x180072eaa  lea     rbp, [rsp-390h]
0x180072eb2  sub     rsp, 490h
0x180072eb9  mov     rax, cs:__security_cookie
0x180072ec0  xor     rax, rsp
0x180072ec3  mov     [rbp+3A0h+var_20], rax
0x180072eca  mov     rdx, [rcx]
0x180072ecd  lea     rbx, [rcx+8]
0x180072ed1  mov     rsi, rcx
0x180072ed4  mov     r15d, 100h
0x180072eda  cmp     qword ptr [rdx], 0
0x180072ede  jz      short loc_180072EEC
0x180072ee0  mov     rax, [rbx]
0x180072ee3  add     rax, r15
0x180072ee6  jz      short loc_180072EEC
0x180072ee8  xor     al, al
0x180072eea  jmp     short loc_180072EEE
0x180072eec  mov     al, 1
0x180072eee  mov     rcx, [rbp+3A8h]; this
0x180072ef5  test    al, al
0x180072ef7  jz      short loc_180072F11
0x180072ef9  mov     r9d, 80070057h; char *
0x180072eff  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180072f06  mov     edx, 0DFh; void *
0x180072f0b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072f11  mov     r9, [rbx]
0x180072f14  lea     r8, aSS_1; "%s:%s"
0x180072f1b  xor     eax, eax
0x180072f1d  mov     [rsp+4A0h+phPrinter], 0
0x180072f26  mov     qword ptr [rsp+4A0h+pDefault.DesiredAccess], rax
0x180072f2b  lea     rcx, [rsp+4A0h+pPrinterName]; unsigned __int16 *
0x180072f30  xorps   xmm0, xmm0
0x180072f33  mov     [rsp+4A0h+pDefault.DesiredAccess], 0F000Ch
0x180072f3b  movups  xmmword ptr [rsp+4A0h+pDefault.pDatatype], xmm0
0x180072f40  mov     rax, [rdx]
0x180072f43  add     r9, 614h
0x180072f4a  mov     edx, 209h; unsigned __int64
0x180072f4f  mov     [rsp+4A0h+pcbNeeded], rax; int
0x180072f54  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180072f59  mov     rcx, [rbp+3A8h]; this
0x180072f60  test    eax, eax
0x180072f62  jns     short loc_180072F79
0x180072f64  mov     r9d, eax; char *
0x180072f67  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180072f6e  mov     edx, 0ECh; void *
0x180072f73  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072f79  lea     r8, [rsp+4A0h+pDefault]; pDefault
0x180072f7e  lea     rdx, [rsp+4A0h+phPrinter]; phPrinter
0x180072f83  lea     rcx, [rsp+4A0h+pPrinterName]; pPrinterName
0x180072f88  call    cs:__imp_OpenPrinterW
0x180072f8f  nop     dword ptr [rax+rax+00h]
0x180072f94  test    eax, eax
0x180072f96  jz      loc_180073172
0x180072f9c  mov     rdx, [rsp+4A0h+phPrinter]
0x180072fa1  mov     rcx, [rsi+10h]
0x180072fa5  call    ?reset@?$unique_ptr@XUPrintHandleCloser@AppMon@@@std@@QEAAXPEAX@Z; std::unique_ptr<void,AppMon::PrintHandleCloser>::reset(void *)
0x180072faa  mov     rcx, [rsp+4A0h+phPrinter]; hPrinter
0x180072faf  lea     rax, [rsp+4A0h+cbBuf]
0x180072fb4  mov     rdi, [rbp+3A8h]
0x180072fbb  xor     r9d, r9d; cbBuf
0x180072fbe  xor     r8d, r8d; pPrinter
0x180072fc1  mov     [rsp+4A0h+cbBuf], 0
0x180072fc9  mov     [rsp+4A0h+pcbNeeded], rax; int
0x180072fce  lea     edx, [r9+5]; Level
0x180072fd2  call    cs:__imp_GetPrinterW
0x180072fd9  nop     dword ptr [rax+rax+00h]
0x180072fde  test    eax, eax
0x180072fe0  jz      short loc_180072FFD
0x180072fe2  mov     r9d, 8000FFFFh; char *
0x180072fe8  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180072fef  mov     edx, 0F4h; void *
0x180072ff4  mov     rcx, rdi; this
0x180072ff7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180072ffd  call    cs:__imp_GetLastError
0x180073004  nop     dword ptr [rax+rax+00h]
0x180073009  cmp     eax, 7Ah ; 'z'
0x18007300c  jnz     short loc_180073012
0x18007300e  xor     cl, cl
0x180073010  jmp     short loc_180073018
0x180073012  mov     cl, 1
0x180073014  test    eax, eax
0x180073016  jle     short loc_180073020
0x180073018  movzx   eax, ax
0x18007301b  or      eax, 80070000h
0x180073020  mov     r10, [rbp+3A8h]
0x180073027  test    cl, cl
0x180073029  jz      short loc_180073043
0x18007302b  mov     r9d, eax; char *
0x18007302e  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180073035  mov     edx, 0F6h; void *
0x18007303a  mov     rcx, r10; this
0x18007303d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073043  mov     ecx, [rsp+4A0h+cbBuf]; unsigned __int64
0x180073047  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18007304c  mov     rcx, [rsi+18h]
0x180073050  mov     rdi, rax
0x180073053  mov     rax, [rcx]
0x180073056  mov     [rcx], rdi
0x180073059  test    rax, rax
0x18007305c  jz      short loc_18007306B
0x18007305e  mov     edx, 1; struct std::nothrow_t *
0x180073063  mov     rcx, rax; void *
0x180073066  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18007306b  mov     r9d, [rsp+4A0h+cbBuf]; cbBuf
0x180073070  lea     rax, [rsp+4A0h+cbBuf]
0x180073075  mov     rcx, [rsp+4A0h+phPrinter]; hPrinter
0x18007307a  mov     r8, rdi; pPrinter
0x18007307d  mov     edx, 5; Level
0x180073082  mov     [rsp+4A0h+pcbNeeded], rax; int
0x180073087  call    cs:__imp_GetPrinterW
0x18007308e  nop     dword ptr [rax+rax+00h]
0x180073093  test    eax, eax
0x180073095  jnz     short loc_1800730B0
0x180073097  mov     rcx, [rbp+3A8h]; this
0x18007309e  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800730a5  mov     edx, 0FCh; void *
0x1800730aa  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800730b0  mov     rdx, [rdi+8]; unsigned __int16 *
0x1800730b4  call    ?RemoveAppmonPort@AppPrinterInstaller@AppMon@@AEAAJPEBG@Z; AppMon::AppPrinterInstaller::RemoveAppmonPort(ushort const *)
0x1800730b9  test    eax, eax
0x1800730bb  jns     short loc_1800730D7
0x1800730bd  mov     rcx, [rbp+3A8h]; this
0x1800730c4  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800730cb  mov     r9d, eax; char *
0x1800730ce  mov     edx, r15d; void *
0x1800730d1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800730d7  mov     rdx, [rbx]; struct AppMon::APPINFO *
0x1800730da  mov     rcx, [rsi+20h]; this
0x1800730de  call    ?CreateAppmonPort@AppPrinterInstaller@AppMon@@AEAAJAEBUAPPINFO@2@@Z; AppMon::AppPrinterInstaller::CreateAppmonPort(AppMon::APPINFO const &)
0x1800730e3  test    eax, eax
0x1800730e5  jz      short loc_18007310A
0x1800730e7  cmp     eax, 800700B7h
0x1800730ec  jz      short loc_18007310A
0x1800730ee  mov     rcx, [rbp+3A8h]; this
0x1800730f5  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800730fc  mov     r9d, eax; char *
0x1800730ff  mov     edx, 104h; void *
0x180073104  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18007310a  mov     rax, [rbx]
0x18007310d  xor     r9d, r9d; Command
0x180073110  add     rax, r15
0x180073113  mov     r8, rdi; pPrinter
0x180073116  mov     [rdi+8], rax
0x18007311a  mov     rcx, [rsp+4A0h+phPrinter]; hPrinter
0x18007311f  lea     edx, [r9+5]; Level
0x180073123  call    cs:__imp_SetPrinterW
0x18007312a  nop     dword ptr [rax+rax+00h]
0x18007312f  test    eax, eax
0x180073131  jnz     short loc_180073172
0x180073133  mov     rdx, [rbx]
0x180073136  add     rdx, r15; unsigned __int16 *
0x180073139  call    ?RemoveAppmonPort@AppPrinterInstaller@AppMon@@AEAAJPEBG@Z; AppMon::AppPrinterInstaller::RemoveAppmonPort(ushort const *)
0x18007313e  call    cs:__imp_GetLastError
0x180073145  nop     dword ptr [rax+rax+00h]
0x18007314a  test    eax, eax
0x18007314c  jle     short loc_180073156
0x18007314e  movzx   eax, ax
0x180073151  or      eax, 80070000h
0x180073156  mov     rcx, [rbp+3A8h]; this
0x18007315d  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180073164  mov     r9d, eax; char *
0x180073167  mov     edx, 10Dh; void *
0x18007316c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180073172  mov     rcx, [rbp+3A0h+var_20]
0x180073179  xor     rcx, rsp; StackCookie
0x18007317c  call    __security_check_cookie
0x180073181  lea     r11, [rsp+4A0h+var_10]
0x180073189  mov     rbx, [r11+28h]
0x18007318d  mov     rsi, [r11+30h]
0x180073191  mov     rsp, r11
0x180073194  pop     r15
0x180073196  pop     rdi
0x180073197  pop     rbp
0x180073198  retn
```
