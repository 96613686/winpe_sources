# PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile(void)

- ea: `0x180049be0`
- end: `0x180049f51`
- name: `?SavePrintCapabilitesToCacheFile@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `881`
- prototype: `void __fastcall(PrintConfig::CConfigManager *__hidden this)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18001053c`
- `0x18001aecc`
- `0x18001b6d0`
- `0x180049b18`

## callees

- `0x1800032e0`
- `0x180004418`
- `0x18000e348`
- `0x18000f590`
- `0x180018818`
- `0x18002025c`
- `0x180049be0`
- `0x18004a688`
- `0x1801c3010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x180049c7a`
- `ole32!CreateStreamOnHGlobal` at `0x180049c7a`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180049dd4`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x180049dd4`
- `SHLWAPI!__imp_IStream_Copy` at `0x180049e46`
- `SHLWAPI!__imp_IStream_Copy` at `0x180049e46`
- `prntvpt!__imp_PTOpenProvider` at `0x180049c34`
- `prntvpt!__imp_PTOpenProvider` at `0x180049c34`
- `prntvpt!__imp_PTCloseProvider` at `0x180049efd`
- `prntvpt!__imp_PTCloseProvider` at `0x180049efd`
- `prntvpt!__imp_PTGetPrintCapabilities` at `0x180049c9f`
- `prntvpt!__imp_PTGetPrintCapabilities` at `0x180049c9f`

## string_xrefs

- `0x180049c51`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x180049c42`: `Failed to open PT provider`
- `0x180049de2`: `Failed to create stream on file`
- `0x180049d7a`: `ipp_print_capabilities.xml`
- `0x180049e8b`: `Failed to commit the stream`
- `0x180049e54`: `Failed to copy the stream`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile(PCWSTR *this)
{
  unsigned int v2; // eax
  HRESULT v3; // eax
  unsigned int v4; // eax
  int v5; // eax
  unsigned int v6; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  _QWORD *v9; // r9
  PCWSTR v10; // rcx
  const WCHAR *v11; // rcx
  unsigned int v12; // eax
  unsigned int v13; // eax
  LPCWSTR v14; // r9
  unsigned int v15; // eax
  unsigned int v16; // eax
  __int64 v17; // rcx
  const char *v18; // r9
  LPSTREAM v19; // rcx
  int pstmTemplate; // [rsp+20h] [rbp-C8h]
  int pstmTemplatea; // [rsp+20h] [rbp-C8h]
  LPWSTR pstmTemplateb; // [rsp+20h] [rbp-C8h]
  IStream **v23; // [rsp+28h] [rbp-C0h]
  IStream **v24; // [rsp+28h] [rbp-C0h]
  IStream **v25; // [rsp+28h] [rbp-C0h]
  IStream **v26; // [rsp+28h] [rbp-C0h]
  IStream **v27; // [rsp+28h] [rbp-C0h]
  IStream **v28; // [rsp+28h] [rbp-C0h]
  IStream **v29; // [rsp+28h] [rbp-C0h]
  IStream **v30; // [rsp+28h] [rbp-C0h]
  LPSTREAM ppstm; // [rsp+40h] [rbp-A8h] BYREF
  ASSOCSTR str[2]; // [rsp+48h] [rbp-A0h] BYREF
  HPTPROVIDER phProvider[2]; // [rsp+50h] [rbp-98h] BYREF
  LPCWSTR pszFile[4]; // [rsp+60h] [rbp-88h] BYREF
  _BYTE v35[16]; // [rsp+80h] [rbp-68h] BYREF
  LPCWSTR pszAssoc; // [rsp+90h] [rbp-58h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  phProvider[1] = (HPTPROVIDER)-2LL;
  if ( *((_DWORD *)this + 30) )
  {
    phProvider[0] = 0;
    v2 = PTOpenProvider(this[2], 1u, phProvider);
    try
    {
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4B5,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v2,
        (int)"Failed to open PT provider",
        (const char *)v23);
      ppstm = 0;
      v3 = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( v3 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4B8,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)(unsigned int)v3,
          pstmTemplate);
      v4 = PTGetPrintCapabilities(phProvider[0], 0, ppstm, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4BA,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v4,
        (int)"Failed to get print capabilities",
        (const char *)v24);
      memset_0(v35, 0, 0x50u);
      v5 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v35, 1);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x4BE,
          (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)(unsigned int)v5,
          pstmTemplatea);
      v6 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4BF,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v6,
        (int)"Failed to seek to the beginning of the stream",
        (const char *)v25);
      v9 = this + 4;
      v10 = this[6];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v10) < 0x1A )
        std::_Xlen_string();
      if ( (unsigned __int64)this[7] > 7 )
        v9 = (_QWORD *)*v9;
      std::wstring::wstring(pszFile, v7, v8, v9, v10, L"ipp_print_capabilities.xml", 26);
      *(_QWORD *)str = 0;
      v11 = (const WCHAR *)pszFile;
      if ( pszFile[3] > (LPCWSTR)7 )
        v11 = pszFile[0];
      v12 = SHCreateStreamOnFileEx(v11, 0x1031u, 0x8100080u, 1, 0, (IStream **)str);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4C4,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v12,
        (int)"Failed to create stream on file",
        (const char *)v26);
      v13 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))(**(_QWORD **)str + 40LL))(
              *(_QWORD *)str,
              0,
              0,
              0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4C6,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v13,
        (int)"Failed to seek to the beginning of the stream",
        (const char *)v27);
      v15 = IStream_Copy((ASSOCF)ppstm, str[0], (LPCWSTR)(unsigned int)pszAssoc, v14, pstmTemplateb, (DWORD *)v28);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4C7,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v15,
        (int)"Failed to copy the stream",
        (const char *)v29);
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)str + 64LL))(*(_QWORD *)str, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4C9,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v16,
        (int)"Failed to commit the stream",
        (const char *)v30);
      v17 = *(_QWORD *)str;
      if ( *(_QWORD *)str )
      {
        *(_QWORD *)str = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      }
      std::wstring::~wstring(pszFile);
      v19 = ppstm;
      if ( ppstm )
      {
        ppstm = 0;
        ((void (__fastcall *)(LPSTREAM))v19->lpVtbl->Release)(v19);
      }
      if ( phProvider[0] )
        PTCloseProvider(phProvider[0]);
    }
    catch ( ... )
    {
      wil::details::in1diag3::Log_CaughtException(
        retaddr,
        (void *)0x4CB,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        v18);
    }
  }
}

```

## disassembly

```asm
0x180049be0  mov     rax, rsp
0x180049be3  push    r15
0x180049be5  sub     rsp, 0E0h
0x180049bec  mov     [rsp+0E8h+var_90], 0FFFFFFFFFFFFFFFEh
0x180049bf5  mov     [rax+10h], rbx
0x180049bf9  mov     [rax+18h], rsi
0x180049bfd  mov     rax, cs:__security_cookie
0x180049c04  xor     rax, rsp
0x180049c07  mov     [rsp+0E8h+var_18], rax
0x180049c0f  mov     rbx, rcx
0x180049c12  cmp     dword ptr [rcx+78h], 0
0x180049c16  jnz     short loc_180049C1D
0x180049c18  jmp     loc_180049F04
0x180049c1d  mov     [rsp+0E8h+phProvider], 0
0x180049c26  lea     r8, [rsp+0E8h+phProvider]; phProvider
0x180049c2b  mov     edx, 1; dwVersion
0x180049c30  mov     rcx, [rcx+10h]; pszPrinterName
0x180049c34  call    cs:__imp_PTOpenProvider
0x180049c3a  mov     rcx, [rsp+0E8h]; this
0x180049c42  lea     rdx, aFailedToOpenPt; "Failed to open PT provider"
0x180049c49  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x180049c4e  mov     r9d, eax; char *
0x180049c51  lea     rsi, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x180049c58  mov     r8, rsi; unsigned int
0x180049c5b  mov     edx, 4B5h; void *
0x180049c60  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049c65  mov     [rsp+0E8h+ppstm], 0
0x180049c6e  lea     r8, [rsp+0E8h+ppstm]; ppstm
0x180049c73  mov     edx, 1; fDeleteOnRelease
0x180049c78  xor     ecx, ecx; hGlobal
0x180049c7a  call    cs:__imp_CreateStreamOnHGlobal
0x180049c80  mov     rcx, [rsp+0E8h]; this
0x180049c88  test    eax, eax
0x180049c8a  js      loc_180049F2A
0x180049c90  xor     r9d, r9d; pbstrErrorMessage
0x180049c93  mov     r8, [rsp+0E8h+ppstm]; pCapabilities
0x180049c98  xor     edx, edx; pPrintTicket
0x180049c9a  mov     rcx, [rsp+0E8h+phProvider]; hProvider
0x180049c9f  call    cs:__imp_PTGetPrintCapabilities
0x180049ca5  mov     rcx, [rsp+0E8h]; this
0x180049cad  lea     rdx, aFailedToGetPri_0; "Failed to get print capabilities"
0x180049cb4  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x180049cb9  mov     r9d, eax; char *
0x180049cbc  mov     r8, rsi; unsigned int
0x180049cbf  mov     edx, 4BAh; void *
0x180049cc4  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049cc9  xor     edx, edx; Val
0x180049ccb  lea     r8d, [rdx+50h]; Size
0x180049ccf  lea     rcx, [rsp+0E8h+var_68]; void *
0x180049cd7  call    memset_0
0x180049cdc  mov     rcx, [rsp+0E8h+ppstm]
0x180049ce1  mov     rax, [rcx]
0x180049ce4  mov     r8d, 1
0x180049cea  lea     rdx, [rsp+0E8h+var_68]
0x180049cf2  mov     rax, [rax+60h]
0x180049cf6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049cfb  mov     rcx, [rsp+0E8h]; this
0x180049d03  test    eax, eax
0x180049d05  js      loc_180049F3A
0x180049d0b  mov     rcx, [rsp+0E8h+ppstm]
0x180049d10  xor     edx, edx
0x180049d12  mov     rax, [rcx]
0x180049d15  xor     r9d, r9d
0x180049d18  xor     r8d, r8d
0x180049d1b  mov     rax, [rax+28h]
0x180049d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049d24  mov     rcx, [rsp+0E8h]; this
0x180049d2c  lea     r15, pszOut; "Failed to seek to the beginning of the "...
0x180049d33  mov     [rsp+0E8h+pstmTemplate], r15; int
0x180049d38  mov     r9d, eax; char *
0x180049d3b  mov     r8, rsi; unsigned int
0x180049d3e  mov     edx, 4BFh; void *
0x180049d43  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049d48  lea     r9, [rbx+20h]
0x180049d4c  mov     rcx, [r9+10h]
0x180049d50  mov     rax, 7FFFFFFFFFFFFFFEh
0x180049d5a  sub     rax, rcx
0x180049d5d  cmp     rax, 1Ah
0x180049d61  jb      loc_180049F4A
0x180049d67  cmp     qword ptr [r9+18h], 7
0x180049d6c  jbe     short loc_180049D71
0x180049d6e  mov     r9, [r9]
0x180049d71  mov     [rsp+0E8h+var_B8], 1Ah
0x180049d7a  lea     rax, aIppPrintCapabi; "ipp_print_capabilities.xml"
0x180049d81  mov     [rsp+0E8h+var_C0], rax
0x180049d86  mov     [rsp+0E8h+pstmTemplate], rcx
0x180049d8b  lea     rcx, [rsp+0E8h+pszFile]
0x180049d90  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x180049d95  nop
0x180049d96  mov     qword ptr [rsp+0E8h+str], 0
0x180049d9f  lea     rcx, [rsp+0E8h+pszFile]
0x180049da4  cmp     [rsp+0E8h+var_70], 7
0x180049daa  cmova   rcx, [rsp+0E8h+pszFile]; pszFile
0x180049db0  lea     rax, [rsp+0E8h+str]
0x180049db5  mov     [rsp+0E8h+var_C0], rax; char *
0x180049dba  mov     [rsp+0E8h+pstmTemplate], 0; pstmTemplate
0x180049dc3  mov     edx, 1031h; grfMode
0x180049dc8  mov     r9d, 1; fCreate
0x180049dce  mov     r8d, 8100080h; dwAttributes
0x180049dd4  call    cs:__imp_SHCreateStreamOnFileEx
0x180049dda  mov     rcx, [rsp+0E8h]; this
0x180049de2  lea     rdx, aFailedToCreate_1; "Failed to create stream on file"
0x180049de9  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x180049dee  mov     r9d, eax; char *
0x180049df1  mov     r8, rsi; unsigned int
0x180049df4  mov     edx, 4C4h; void *
0x180049df9  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049dfe  mov     rcx, qword ptr [rsp+0E8h+str]
0x180049e03  xor     edx, edx
0x180049e05  mov     rax, [rcx]
0x180049e08  xor     r9d, r9d
0x180049e0b  xor     r8d, r8d
0x180049e0e  mov     rax, [rax+28h]
0x180049e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e17  mov     rcx, [rsp+0E8h]; this
0x180049e1f  mov     [rsp+0E8h+pstmTemplate], r15; int
0x180049e24  mov     r9d, eax; char *
0x180049e27  mov     r8, rsi; unsigned int
0x180049e2a  mov     edx, 4C6h; void *
0x180049e2f  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049e34  mov     r8d, dword ptr [rsp+0E8h+pszAssoc]; pszAssoc
0x180049e3c  mov     rdx, qword ptr [rsp+0E8h+str]; str
0x180049e41  mov     rcx, [rsp+0E8h+ppstm]; flags
0x180049e46  call    cs:__imp_IStream_Copy
0x180049e4c  mov     rcx, [rsp+0E8h]; this
0x180049e54  lea     rdx, aFailedToCopyTh; "Failed to copy the stream"
0x180049e5b  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x180049e60  mov     r9d, eax; char *
0x180049e63  mov     r8, rsi; unsigned int
0x180049e66  mov     edx, 4C7h; void *
0x180049e6b  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049e70  mov     rcx, qword ptr [rsp+0E8h+str]
0x180049e75  mov     rax, [rcx]
0x180049e78  xor     edx, edx
0x180049e7a  mov     rax, [rax+40h]
0x180049e7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049e83  mov     rcx, [rsp+0E8h]; this
0x180049e8b  lea     rdx, aFailedToCommit_1; "Failed to commit the stream"
0x180049e92  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x180049e97  mov     r9d, eax; char *
0x180049e9a  mov     r8, rsi; unsigned int
0x180049e9d  mov     edx, 4C9h; void *
0x180049ea2  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x180049ea7  nop
0x180049ea8  mov     rcx, qword ptr [rsp+0E8h+str]
0x180049ead  test    rcx, rcx
0x180049eb0  jz      short loc_180049EC8
0x180049eb2  mov     qword ptr [rsp+0E8h+str], 0
0x180049ebb  mov     rax, [rcx]
0x180049ebe  mov     rax, [rax+10h]
0x180049ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ec7  nop
0x180049ec8  lea     rcx, [rsp+0E8h+pszFile]
0x180049ecd  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180049ed2  nop
0x180049ed3  mov     rcx, [rsp+0E8h+ppstm]
0x180049ed8  test    rcx, rcx
0x180049edb  jz      short loc_180049EF3
0x180049edd  mov     [rsp+0E8h+ppstm], 0
0x180049ee6  mov     rax, [rcx]
0x180049ee9  mov     rax, [rax+10h]
0x180049eed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049ef2  nop
0x180049ef3  mov     rcx, [rsp+0E8h+phProvider]; hProvider
0x180049ef8  test    rcx, rcx
0x180049efb  jz      short loc_180049F04
0x180049efd  call    cs:__imp_PTCloseProvider
0x180049f03  nop
0x180049f04  mov     rcx, [rsp+0E8h+var_18]
0x180049f0c  xor     rcx, rsp; StackCookie
0x180049f0f  call    __security_check_cookie
0x180049f14  lea     r11, [rsp+0E8h+var_8]
0x180049f1c  mov     rbx, [r11+18h]
0x180049f20  mov     rsi, [r11+20h]
0x180049f24  mov     rsp, r11
0x180049f27  pop     r15
0x180049f29  retn
0x180049f2a  mov     r9d, eax; char *
0x180049f2d  mov     r8, rsi; unsigned int
0x180049f30  mov     edx, 4B8h; void *
0x180049f35  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f3a  mov     r9d, eax; char *
0x180049f3d  mov     r8, rsi; unsigned int
0x180049f40  mov     edx, 4BEh; void *
0x180049f45  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180049f4a  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
