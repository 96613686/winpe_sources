# _lambda_93dded920c56a3434eda5fab2f7d76d2_::operator()

- ea: `0x18005345c`
- end: `0x1800536d6`
- name: `_lambda_93dded920c56a3434eda5fab2f7d76d2_::operator()`
- size: `634`
- prototype: `__int64 __fastcall(HANDLE ***)`
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18008f4c4`

## callees

- `0x18005345c`
- `0x1800536dc`
- `0x180064a88`
- `0x180071ef0`
- `0x180072114`
- `0x180081f60`
- `0x1800af6f8`
- `0x180132e54`
- `0x18019d050`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535c4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800535c4`
- `WINSPOOL!OpenPrinterW` at `0x1800534bb`
- `WINSPOOL!OpenPrinterW` at `0x1800534bb`
- `WINSPOOL!GetPrinterW` at `0x180053599`
- `WINSPOOL!GetPrinterW` at `0x180053638`
- `WINSPOOL!GetPrinterW` at `0x180053599`
- `WINSPOOL!GetPrinterW` at `0x180053638`

## string_xrefs

- `0x180053480`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800534ee`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x180053560`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800535af`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800535f2`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x180053648`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`
- `0x1800536b1`: `onecore\printscan\print\lib\appprinterinstallationlib\appprinterinstaller\appprinterinstaller.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall lambda_93dded920c56a3434eda5fab2f7d76d2_::operator()(HANDLE ***a1)
{
  HANDLE *v2; // rdx
  unsigned int AppmonPort; // eax
  __int64 *v4; // rcx
  __int64 result; // rax
  signed int LastError; // eax
  char v7; // cl
  void *v8; // rdi
  const char *v9; // r9
  const struct AppMon::APPINFO *v10; // r8
  const struct AppMon::APPINFO *v11; // rax
  signed __int64 v12; // r9
  int v13; // edx
  int v14; // ecx
  int v15; // eax
  int pcbNeeded; // [rsp+20h] [rbp-58h]
  int pcbNeededa; // [rsp+20h] [rbp-58h]
  int pcbNeededb; // [rsp+20h] [rbp-58h]
  _PRINTER_DEFAULTSW pDefault; // [rsp+30h] [rbp-48h] BYREF
  _QWORD v20[6]; // [rsp+48h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+20h]
  __int64 *cbBuf; // [rsp+A0h] [rbp+28h] BYREF
  void *v23; // [rsp+A8h] [rbp+30h] BYREF
  __int64 *v24; // [rsp+B0h] [rbp+38h] BYREF
  HANDLE *v25; // [rsp+B8h] [rbp+40h] BYREF

  v2 = **a1;
  if ( !v2 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x17,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      (const char *)0x80070057LL,
      pcbNeeded);
  *v2 = 0;
  *(_OWORD *)&pDefault.pDatatype = 0;
  *(&pDefault.DesiredAccess + 1) = 0;
  pDefault.DesiredAccess = 983052;
  if ( !OpenPrinterW((LPWSTR)a1[1], **a1, &pDefault) )
  {
    AppmonPort = AppMon::AppPrinterInstaller::CreateAppmonPort(
                   (AppMon::AppPrinterInstaller *)a1[2],
                   (const struct AppMon::APPINFO *)a1[1]);
    if ( AppmonPort && AppmonPort != -2147024713 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x22,
        (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
        (const char *)AppmonPort,
        pcbNeeded);
    v25 = **a1;
    v4 = (__int64 *)a1[1];
    v24 = v4 + 32;
    v23 = v4 + 16;
    cbBuf = v4;
    v20[0] = &cbBuf;
    v20[1] = &v23;
    v20[2] = &v24;
    v20[3] = &v25;
    result = AppMon::CaptureAndConvertExceptionToHR__lambda_da0404bee759cc3360e31d661ac0678c___(v20);
    if ( (int)result < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x23,
        (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
        (const char *)(unsigned int)result,
        pcbNeeded);
    return result;
  }
  LODWORD(cbBuf) = 0;
  if ( GetPrinterW(***a1, 2u, 0, 0, (LPDWORD)&cbBuf) )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      (const char *)0x8000FFFFLL,
      pcbNeededa);
  LastError = GetLastError();
  if ( LastError == 122 )
  {
    v7 = 0;
LABEL_14:
    LastError = (unsigned __int16)LastError | 0x80070000;
    goto LABEL_15;
  }
  v7 = 1;
  if ( LastError > 0 )
    goto LABEL_14;
LABEL_15:
  if ( v7 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      (const char *)(unsigned int)LastError,
      pcbNeededa);
  v8 = operator new[]((unsigned int)cbBuf);
  v23 = v8;
  if ( !GetPrinterW(***a1, 2u, (LPBYTE)v8, (DWORD)cbBuf, (LPDWORD)&cbBuf) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x33,
      (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
      v9);
  if ( !wcscmp_0(*((const wchar_t **)v8 + 4), L"Microsoft Software Printer Driver") )
  {
    v10 = (const struct AppMon::APPINFO *)a1[1];
    v11 = (const struct AppMon::APPINFO *)*((_QWORD *)v8 + 3);
    v12 = (const struct AppMon::APPINFO *)((char *)v10 + 256) - v11;
    do
    {
      v13 = *(unsigned __int16 *)((char *)v11 + v12);
      v14 = *(unsigned __int16 *)v11 - v13;
      if ( v14 )
        break;
      v11 = (const struct AppMon::APPINFO *)((char *)v11 + 2);
    }
    while ( v13 );
    if ( v14 )
    {
      v15 = AppMon::AppPrinterInstaller::ChangeAppPrinterPort(
              (AppMon::AppPrinterInstaller *)a1[2],
              *((const unsigned __int16 **)v8 + 1),
              v10);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x3A,
          (unsigned int)"onecore\\printscan\\print\\lib\\appprinterinstallationlib\\appprinterinstaller\\appprinterinstaller.cpp",
          (const char *)(unsigned int)v15,
          pcbNeededb);
    }
  }
  return std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(&v23);
}

```

## disassembly

```asm
0x18005345c  push    rbp
0x18005345e  push    rbx
0x18005345f  push    rsi
0x180053460  push    rdi
0x180053461  mov     rbp, rsp
0x180053464  sub     rsp, 78h
0x180053468  mov     rbx, rcx
0x18005346b  mov     rax, [rcx]
0x18005346e  mov     rdx, [rax]
0x180053471  mov     rcx, [rbp+20h]; this
0x180053475  test    rdx, rdx
0x180053478  jnz     short loc_180053492
0x18005347a  mov     r9d, 80070057h; char *
0x180053480  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180053487  mov     edx, 17h; void *
0x18005348c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053492  mov     qword ptr [rdx], 0
0x180053499  xorps   xmm0, xmm0
0x18005349c  xor     eax, eax
0x18005349e  movups  xmmword ptr [rbp+pDefault.pDatatype], xmm0
0x1800534a2  mov     qword ptr [rbp+pDefault.DesiredAccess], rax
0x1800534a6  mov     [rbp+pDefault.DesiredAccess], 0F000Ch
0x1800534ad  mov     rdx, [rbx]
0x1800534b0  lea     r8, [rbp+pDefault]; pDefault
0x1800534b4  mov     rdx, [rdx]; phPrinter
0x1800534b7  mov     rcx, [rbx+8]; pPrinterName
0x1800534bb  call    cs:__imp_OpenPrinterW
0x1800534c2  nop     dword ptr [rax+rax+00h]
0x1800534c7  test    eax, eax
0x1800534c9  jnz     loc_180053572
0x1800534cf  mov     rdx, [rbx+8]; struct AppMon::APPINFO *
0x1800534d3  mov     rcx, [rbx+10h]; this
0x1800534d7  call    ?CreateAppmonPort@AppPrinterInstaller@AppMon@@AEAAJAEBUAPPINFO@2@@Z; AppMon::AppPrinterInstaller::CreateAppmonPort(AppMon::APPINFO const &)
0x1800534dc  test    eax, eax
0x1800534de  jz      short loc_180053500
0x1800534e0  cmp     eax, 800700B7h
0x1800534e5  jz      short loc_180053500
0x1800534e7  mov     rcx, [rbp+20h]; this
0x1800534eb  mov     r9d, eax; char *
0x1800534ee  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800534f5  mov     edx, 22h ; '"'; void *
0x1800534fa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053500  mov     rax, [rbx]
0x180053503  mov     rcx, [rax]
0x180053506  mov     [rbp+arg_18], rcx
0x18005350a  mov     rcx, [rbx+8]
0x18005350e  lea     rax, [rcx+100h]
0x180053515  mov     [rbp+arg_10], rax
0x180053519  lea     rax, [rcx+80h]
0x180053520  mov     [rbp+arg_8], rax
0x180053524  mov     [rbp+cbBuf], rcx
0x180053528  lea     rax, [rbp+cbBuf]
0x18005352c  mov     [rbp+var_30], rax
0x180053530  lea     rax, [rbp+arg_8]
0x180053534  mov     [rbp+var_28], rax
0x180053538  lea     rax, [rbp+arg_10]
0x18005353c  mov     [rbp+var_20], rax
0x180053540  lea     rax, [rbp+arg_18]
0x180053544  mov     [rbp+var_18], rax
0x180053548  lea     rcx, [rbp+var_30]
0x18005354c  call    AppMon__CaptureAndConvertExceptionToHR__lambda_da0404bee759cc3360e31d661ac0678c___
0x180053551  test    eax, eax
0x180053553  jns     loc_1800536CC
0x180053559  mov     rcx, [rbp+20h]; this
0x18005355d  mov     r9d, eax; char *
0x180053560  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x180053567  mov     edx, 23h ; '#'; void *
0x18005356c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053572  mov     dword ptr [rbp+cbBuf], 0
0x180053579  mov     rdi, [rbp+20h]
0x18005357d  mov     rax, [rbx]
0x180053580  mov     rcx, [rax]
0x180053583  lea     rax, [rbp+cbBuf]
0x180053587  mov     qword ptr [rsp+78h+pcbNeeded], rax; int
0x18005358c  xor     r9d, r9d; cbBuf
0x18005358f  xor     r8d, r8d; pPrinter
0x180053592  lea     edx, [r9+2]; Level
0x180053596  mov     rcx, [rcx]; hPrinter
0x180053599  call    cs:__imp_GetPrinterW
0x1800535a0  nop     dword ptr [rax+rax+00h]
0x1800535a5  test    eax, eax
0x1800535a7  jz      short loc_1800535C4
0x1800535a9  mov     r9d, 8000FFFFh; char *
0x1800535af  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800535b6  mov     edx, 2Bh ; '+'; void *
0x1800535bb  mov     rcx, rdi; this
0x1800535be  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800535c4  call    cs:__imp_GetLastError
0x1800535cb  nop     dword ptr [rax+rax+00h]
0x1800535d0  cmp     eax, 7Ah ; 'z'
0x1800535d3  jnz     short loc_1800535D9
0x1800535d5  xor     cl, cl
0x1800535d7  jmp     short loc_1800535DF
0x1800535d9  mov     cl, 1
0x1800535db  test    eax, eax
0x1800535dd  jle     short loc_1800535E7
0x1800535df  movzx   eax, ax
0x1800535e2  or      eax, 80070000h
0x1800535e7  mov     r10, [rbp+20h]
0x1800535eb  test    cl, cl
0x1800535ed  jz      short loc_180053607
0x1800535ef  mov     r9d, eax; char *
0x1800535f2  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800535f9  mov     edx, 2Dh ; '-'; void *
0x1800535fe  mov     rcx, r10; this
0x180053601  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180053607  mov     ecx, dword ptr [rbp+cbBuf]; unsigned __int64
0x18005360a  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18005360f  mov     rdi, rax
0x180053612  mov     [rbp+arg_8], rax
0x180053616  mov     rsi, [rbp+20h]
0x18005361a  mov     rcx, [rbx]
0x18005361d  mov     rcx, [rcx]
0x180053620  lea     rax, [rbp+cbBuf]
0x180053624  mov     qword ptr [rsp+78h+pcbNeeded], rax; int
0x180053629  mov     r9d, dword ptr [rbp+cbBuf]; cbBuf
0x18005362d  mov     r8, rdi; pPrinter
0x180053630  mov     edx, 2; Level
0x180053635  mov     rcx, [rcx]; hPrinter
0x180053638  call    cs:__imp_GetPrinterW
0x18005363f  nop     dword ptr [rax+rax+00h]
0x180053644  test    eax, eax
0x180053646  jnz     short loc_18005365B
0x180053648  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x18005364f  lea     edx, [rax+33h]; void *
0x180053652  mov     rcx, rsi; this
0x180053655  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18005365b  lea     rdx, aMicrosoftSoftw; "Microsoft Software Printer Driver"
0x180053662  mov     rcx, [rdi+20h]; String1
0x180053666  call    wcscmp_0
0x18005366b  test    eax, eax
0x18005366d  jnz     short loc_1800536C3
0x18005366f  mov     r8, [rbx+8]; struct AppMon::APPINFO *
0x180053673  lea     r9, [r8+100h]
0x18005367a  mov     rax, [rdi+18h]
0x18005367e  sub     r9, rax
0x180053681  movzx   ecx, word ptr [rax]
0x180053684  movzx   edx, word ptr [rax+r9]
0x180053689  sub     ecx, edx
0x18005368b  jnz     short loc_180053695
0x18005368d  add     rax, 2
0x180053691  test    edx, edx
0x180053693  jnz     short loc_180053681
0x180053695  test    ecx, ecx
0x180053697  jz      short loc_1800536C3
0x180053699  mov     rdx, [rdi+8]; unsigned __int16 *
0x18005369d  mov     rcx, [rbx+10h]; this
0x1800536a1  call    ?ChangeAppPrinterPort@AppPrinterInstaller@AppMon@@QEAAJPEBGAEBUAPPINFO@2@@Z; AppMon::AppPrinterInstaller::ChangeAppPrinterPort(ushort const *,AppMon::APPINFO const &)
0x1800536a6  mov     rcx, [rbp+20h]; this
0x1800536aa  test    eax, eax
0x1800536ac  jns     short loc_1800536C3
0x1800536ae  mov     r9d, eax; char *
0x1800536b1  lea     r8, aOnecorePrintsc; "onecore\\printscan\\print\\lib\\appprin"...
0x1800536b8  mov     edx, 3Ah ; ':'; void *
0x1800536bd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800536c3  lea     rcx, [rbp+arg_8]
0x1800536c7  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x1800536cc  add     rsp, 78h
0x1800536d0  pop     rdi
0x1800536d1  pop     rsi
0x1800536d2  pop     rbx
0x1800536d3  pop     rbp
0x1800536d4  retn
```
