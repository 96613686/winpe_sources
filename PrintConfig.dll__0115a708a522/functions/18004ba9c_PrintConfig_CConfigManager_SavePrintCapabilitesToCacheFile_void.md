# PrintConfig::CConfigManager::SavePrintCapabilitesToCacheFile(void)

- ea: `0x18004ba9c`
- end: `0x18004be32`
- name: `?SavePrintCapabilitesToCacheFile@CConfigManager@PrintConfig@@QEAAXXZ`
- size: `918`
- prototype: `void __fastcall(PCWSTR *this)`
- caller_count: `4`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180010abc`
- `0x18001bb3c`
- `0x18001c364`
- `0x18004b9cc`

## callees

- `0x180003400`
- `0x180004558`
- `0x18000e750`
- `0x18000fa4c`
- `0x180019388`
- `0x180020c8c`
- `0x18004ba9c`
- `0x18004c574`
- `0x1801cb010`

## import_xrefs

- `ole32!CreateStreamOnHGlobal` at `0x18004bb3c`
- `ole32!CreateStreamOnHGlobal` at `0x18004bb3c`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18004bca2`
- `SHLWAPI!SHCreateStreamOnFileEx` at `0x18004bca2`
- `SHLWAPI!__imp_IStream_Copy` at `0x18004bd1a`
- `SHLWAPI!__imp_IStream_Copy` at `0x18004bd1a`
- `prntvpt!__imp_PTOpenProvider` at `0x18004baf0`
- `prntvpt!__imp_PTOpenProvider` at `0x18004baf0`
- `prntvpt!__imp_PTCloseProvider` at `0x18004bdd7`
- `prntvpt!__imp_PTCloseProvider` at `0x18004bdd7`
- `prntvpt!__imp_PTGetPrintCapabilities` at `0x18004bb67`
- `prntvpt!__imp_PTGetPrintCapabilities` at `0x18004bb67`

## string_xrefs

- `0x18004bb13`: `printscan\print\drivers\usermode\config\printconfig\configmanager.cpp`
- `0x18004bb04`: `Failed to open PT provider`
- `0x18004bcb6`: `Failed to create stream on file`
- `0x18004bc48`: `ipp_print_capabilities.xml`
- `0x18004bd65`: `Failed to commit the stream`
- `0x18004bd2e`: `Failed to copy the stream`

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
  PCWSTR *v9; // r9
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
  if ( *((_DWORD *)this + 31) )
  {
    phProvider[0] = 0;
    v2 = PTOpenProvider(this[2], 1u, phProvider);
    try
    {
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4C8,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v2,
        (int)"Failed to open PT provider",
        (const char *)v23);
      ppstm = 0;
      v3 = CreateStreamOnHGlobal(0, 1, &ppstm);
      if ( v3 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          1227,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)(unsigned int)v3,
          pstmTemplate);
      v4 = PTGetPrintCapabilities(phProvider[0], 0, ppstm, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4CD,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v4,
        (int)"Failed to get print capabilities",
        (const char *)v24);
      memset_0(v35, 0, 0x50u);
      v5 = ((__int64 (__fastcall *)(LPSTREAM, _BYTE *, __int64))ppstm->lpVtbl->Stat)(ppstm, v35, 1);
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          1233,
          (__int64)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
          (const char *)(unsigned int)v5,
          pstmTemplatea);
      v6 = ((__int64 (__fastcall *)(LPSTREAM, _QWORD, _QWORD, _QWORD))ppstm->lpVtbl->Seek)(ppstm, 0, 0, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4D2,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v6,
        (int)"Failed to seek to the beginning of the stream",
        (const char *)v25);
      v9 = this + 4;
      v10 = this[6];
      if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - (_QWORD)v10) < 0x1A )
        std::_Xlen_string();
      if ( (unsigned __int64)this[7] > 7 )
        v9 = (PCWSTR *)*v9;
      std::wstring::wstring((char *)pszFile, v7, v8, v9, (__int64)v10, (void *)L"ipp_print_capabilities.xml", 26);
      *(_QWORD *)str = 0;
      v11 = (const WCHAR *)pszFile;
      if ( pszFile[3] > (LPCWSTR)7 )
        v11 = pszFile[0];
      v12 = SHCreateStreamOnFileEx(v11, 0x1031u, 0x8100080u, 1, 0, (IStream **)str);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4D7,
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
        (void *)0x4D9,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v13,
        (int)"Failed to seek to the beginning of the stream",
        (const char *)v27);
      v15 = IStream_Copy((ASSOCF)ppstm, str[0], (LPCWSTR)(unsigned int)pszAssoc, v14, pstmTemplateb, (DWORD *)v28);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4DA,
        (unsigned int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        (const char *)v15,
        (int)"Failed to copy the stream",
        (const char *)v29);
      v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)str + 64LL))(*(_QWORD *)str, 0);
      wil::details::in1diag3::Throw_IfFailedMsg(
        retaddr,
        (void *)0x4DC,
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
      std::wstring::~wstring((char **)pszFile);
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
        (void *)0x4DE,
        (int)"printscan\\print\\drivers\\usermode\\config\\printconfig\\configmanager.cpp",
        v18);
    }
  }
}

```

## disassembly

```asm
0x18004ba9c  mov     rax, rsp
0x18004ba9f  push    r15
0x18004baa1  sub     rsp, 0E0h
0x18004baa8  mov     [rsp+0E8h+var_90], 0FFFFFFFFFFFFFFFEh
0x18004bab1  mov     [rax+10h], rbx
0x18004bab5  mov     [rax+18h], rsi
0x18004bab9  mov     rax, cs:__security_cookie
0x18004bac0  xor     rax, rsp
0x18004bac3  mov     [rsp+0E8h+var_18], rax
0x18004bacb  mov     rbx, rcx
0x18004bace  cmp     dword ptr [rcx+7Ch], 0
0x18004bad2  jnz     short loc_18004BAD9
0x18004bad4  jmp     loc_18004BDE4
0x18004bad9  mov     [rsp+0E8h+phProvider], 0
0x18004bae2  lea     r8, [rsp+0E8h+phProvider]; phProvider
0x18004bae7  mov     edx, 1; dwVersion
0x18004baec  mov     rcx, [rcx+10h]; pszPrinterName
0x18004baf0  call    cs:__imp_PTOpenProvider
0x18004baf7  nop     dword ptr [rax+rax+00h]
0x18004bafc  mov     rcx, [rsp+0E8h]; this
0x18004bb04  lea     rdx, aFailedToOpenPt; "Failed to open PT provider"
0x18004bb0b  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x18004bb10  mov     r9d, eax; char *
0x18004bb13  lea     rsi, aPrintscanPrint_7; "printscan\\print\\drivers\\usermode\\co"...
0x18004bb1a  mov     r8, rsi; unsigned int
0x18004bb1d  mov     edx, 4C8h; void *
0x18004bb22  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bb27  mov     [rsp+0E8h+ppstm], 0
0x18004bb30  lea     r8, [rsp+0E8h+ppstm]; ppstm
0x18004bb35  mov     edx, 1; fDeleteOnRelease
0x18004bb3a  xor     ecx, ecx; hGlobal
0x18004bb3c  call    cs:__imp_CreateStreamOnHGlobal
0x18004bb43  nop     dword ptr [rax+rax+00h]
0x18004bb48  mov     rcx, [rsp+0E8h]; this
0x18004bb50  test    eax, eax
0x18004bb52  js      loc_18004BE0B
0x18004bb58  xor     r9d, r9d; pbstrErrorMessage
0x18004bb5b  mov     r8, [rsp+0E8h+ppstm]; pCapabilities
0x18004bb60  xor     edx, edx; pPrintTicket
0x18004bb62  mov     rcx, [rsp+0E8h+phProvider]; hProvider
0x18004bb67  call    cs:__imp_PTGetPrintCapabilities
0x18004bb6e  nop     dword ptr [rax+rax+00h]
0x18004bb73  mov     rcx, [rsp+0E8h]; this
0x18004bb7b  lea     rdx, aFailedToGetPri_0; "Failed to get print capabilities"
0x18004bb82  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x18004bb87  mov     r9d, eax; char *
0x18004bb8a  mov     r8, rsi; unsigned int
0x18004bb8d  mov     edx, 4CDh; void *
0x18004bb92  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bb97  xor     edx, edx; Val
0x18004bb99  lea     r8d, [rdx+50h]; Size
0x18004bb9d  lea     rcx, [rsp+0E8h+var_68]; void *
0x18004bba5  call    memset_0
0x18004bbaa  mov     rcx, [rsp+0E8h+ppstm]
0x18004bbaf  mov     rax, [rcx]
0x18004bbb2  mov     r8d, 1
0x18004bbb8  lea     rdx, [rsp+0E8h+var_68]
0x18004bbc0  mov     rax, [rax+60h]
0x18004bbc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbc9  mov     rcx, [rsp+0E8h]; this
0x18004bbd1  test    eax, eax
0x18004bbd3  js      loc_18004BE1B
0x18004bbd9  mov     rcx, [rsp+0E8h+ppstm]
0x18004bbde  xor     edx, edx
0x18004bbe0  mov     rax, [rcx]
0x18004bbe3  xor     r9d, r9d
0x18004bbe6  xor     r8d, r8d
0x18004bbe9  mov     rax, [rax+28h]
0x18004bbed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbf2  mov     rcx, [rsp+0E8h]; this
0x18004bbfa  lea     r15, pszOut; "Failed to seek to the beginning of the "...
0x18004bc01  mov     [rsp+0E8h+pstmTemplate], r15; int
0x18004bc06  mov     r9d, eax; char *
0x18004bc09  mov     r8, rsi; unsigned int
0x18004bc0c  mov     edx, 4D2h; void *
0x18004bc11  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bc16  lea     r9, [rbx+20h]
0x18004bc1a  mov     rcx, [r9+10h]
0x18004bc1e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18004bc28  sub     rax, rcx
0x18004bc2b  cmp     rax, 1Ah
0x18004bc2f  jb      loc_18004BE2B
0x18004bc35  cmp     qword ptr [r9+18h], 7
0x18004bc3a  jbe     short loc_18004BC3F
0x18004bc3c  mov     r9, [r9]
0x18004bc3f  mov     [rsp+0E8h+var_B8], 1Ah
0x18004bc48  lea     rax, aIppPrintCapabi; "ipp_print_capabilities.xml"
0x18004bc4f  mov     [rsp+0E8h+var_C0], rax
0x18004bc54  mov     [rsp+0E8h+pstmTemplate], rcx
0x18004bc59  lea     rcx, [rsp+0E8h+pszFile]
0x18004bc5e  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18004bc63  nop
0x18004bc64  mov     qword ptr [rsp+0E8h+str], 0
0x18004bc6d  lea     rcx, [rsp+0E8h+pszFile]
0x18004bc72  cmp     [rsp+0E8h+var_70], 7
0x18004bc78  cmova   rcx, [rsp+0E8h+pszFile]; pszFile
0x18004bc7e  lea     rax, [rsp+0E8h+str]
0x18004bc83  mov     [rsp+0E8h+var_C0], rax; char *
0x18004bc88  mov     [rsp+0E8h+pstmTemplate], 0; pstmTemplate
0x18004bc91  mov     edx, 1031h; grfMode
0x18004bc96  mov     r9d, 1; fCreate
0x18004bc9c  mov     r8d, 8100080h; dwAttributes
0x18004bca2  call    cs:__imp_SHCreateStreamOnFileEx
0x18004bca9  nop     dword ptr [rax+rax+00h]
0x18004bcae  mov     rcx, [rsp+0E8h]; this
0x18004bcb6  lea     rdx, aFailedToCreate_1; "Failed to create stream on file"
0x18004bcbd  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x18004bcc2  mov     r9d, eax; char *
0x18004bcc5  mov     r8, rsi; unsigned int
0x18004bcc8  mov     edx, 4D7h; void *
0x18004bccd  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bcd2  mov     rcx, qword ptr [rsp+0E8h+str]
0x18004bcd7  xor     edx, edx
0x18004bcd9  mov     rax, [rcx]
0x18004bcdc  xor     r9d, r9d
0x18004bcdf  xor     r8d, r8d
0x18004bce2  mov     rax, [rax+28h]
0x18004bce6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bceb  mov     rcx, [rsp+0E8h]; this
0x18004bcf3  mov     [rsp+0E8h+pstmTemplate], r15; int
0x18004bcf8  mov     r9d, eax; char *
0x18004bcfb  mov     r8, rsi; unsigned int
0x18004bcfe  mov     edx, 4D9h; void *
0x18004bd03  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bd08  mov     r8d, dword ptr [rsp+0E8h+pszAssoc]; pszAssoc
0x18004bd10  mov     rdx, qword ptr [rsp+0E8h+str]; str
0x18004bd15  mov     rcx, [rsp+0E8h+ppstm]; flags
0x18004bd1a  call    cs:__imp_IStream_Copy
0x18004bd21  nop     dword ptr [rax+rax+00h]
0x18004bd26  mov     rcx, [rsp+0E8h]; this
0x18004bd2e  lea     rdx, aFailedToCopyTh; "Failed to copy the stream"
0x18004bd35  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x18004bd3a  mov     r9d, eax; char *
0x18004bd3d  mov     r8, rsi; unsigned int
0x18004bd40  mov     edx, 4DAh; void *
0x18004bd45  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bd4a  mov     rcx, qword ptr [rsp+0E8h+str]
0x18004bd4f  mov     rax, [rcx]
0x18004bd52  xor     edx, edx
0x18004bd54  mov     rax, [rax+40h]
0x18004bd58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bd5d  mov     rcx, [rsp+0E8h]; this
0x18004bd65  lea     rdx, aFailedToCommit_1; "Failed to commit the stream"
0x18004bd6c  mov     [rsp+0E8h+pstmTemplate], rdx; int
0x18004bd71  mov     r9d, eax; char *
0x18004bd74  mov     r8, rsi; unsigned int
0x18004bd77  mov     edx, 4DCh; void *
0x18004bd7c  call    ?Throw_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Throw_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x18004bd81  nop
0x18004bd82  mov     rcx, qword ptr [rsp+0E8h+str]
0x18004bd87  test    rcx, rcx
0x18004bd8a  jz      short loc_18004BDA2
0x18004bd8c  mov     qword ptr [rsp+0E8h+str], 0
0x18004bd95  mov     rax, [rcx]
0x18004bd98  mov     rax, [rax+10h]
0x18004bd9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bda1  nop
0x18004bda2  lea     rcx, [rsp+0E8h+pszFile]
0x18004bda7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004bdac  nop
0x18004bdad  mov     rcx, [rsp+0E8h+ppstm]
0x18004bdb2  test    rcx, rcx
0x18004bdb5  jz      short loc_18004BDCD
0x18004bdb7  mov     [rsp+0E8h+ppstm], 0
0x18004bdc0  mov     rax, [rcx]
0x18004bdc3  mov     rax, [rax+10h]
0x18004bdc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bdcc  nop
0x18004bdcd  mov     rcx, [rsp+0E8h+phProvider]; hProvider
0x18004bdd2  test    rcx, rcx
0x18004bdd5  jz      short loc_18004BDE4
0x18004bdd7  call    cs:__imp_PTCloseProvider
0x18004bdde  nop     dword ptr [rax+rax+00h]
0x18004bde3  nop
0x18004bde4  mov     rcx, [rsp+0E8h+var_18]
0x18004bdec  xor     rcx, rsp; StackCookie
0x18004bdef  call    __security_check_cookie
0x18004bdf4  lea     r11, [rsp+0E8h+var_8]
0x18004bdfc  mov     rbx, [r11+18h]
0x18004be00  mov     rsi, [r11+20h]
0x18004be04  mov     rsp, r11
0x18004be07  pop     r15
0x18004be09  retn
0x18004be0b  mov     r9d, eax; char *
0x18004be0e  mov     r8, rsi; unsigned int
0x18004be11  mov     edx, 4CBh; void *
0x18004be16  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be1b  mov     r9d, eax; char *
0x18004be1e  mov     r8, rsi; unsigned int
0x18004be21  mov     edx, 4D1h; void *
0x18004be26  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18004be2b  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
```
