# CertificateInfo::GetDisplayNameFromVersionInfo(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x18004cf04`
- end: `0x18004d355`
- name: `?GetDisplayNameFromVersionInfo@CertificateInfo@@SAJAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAV23@@Z`
- size: `1105`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x18003886c`

## callees

- `0x180002520`
- `0x18001045c`
- `0x180011e18`
- `0x180014c04`
- `0x18001f998`
- `0x1800214c4`
- `0x1800366b4`
- `0x18004c958`
- `0x18004cb8c`
- `0x18004cf04`
- `0x18004d604`

## import_xrefs

- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18004cf45`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18004cf45`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18004cfa8`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18004cfa8`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18004d19e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18004d19e`

## string_xrefs

- `0x18004cf6b`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004cfcc`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\certificateinfo.cpp`
- `0x18004d099`: `CompanyName`
- `0x18004d139`: `[QueryAppIdentity] Version info for file %s: ProductName='%s', FileDescription='%s', CompanyName='%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall CertificateInfo::GetDisplayNameFromVersionInfo(char *a1, __int64 a2)
{
  char *v3; // rbx
  DWORD FileVersionInfoSizeW; // eax
  DWORD v5; // edi
  const WCHAR *v7; // rcx
  unsigned int LastErrorMsg; // ebx
  const wchar_t *v9; // r9
  char **v10; // rcx
  char **v11; // rax
  const WCHAR *v12; // r8
  int v13; // ebx
  __int64 v14; // rax
  int v15; // [rsp+20h] [rbp-E0h]
  int v16; // [rsp+20h] [rbp-E0h]
  int v17; // [rsp+20h] [rbp-E0h]
  unsigned int puLen; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v19; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v20; // [rsp+48h] [rbp-B8h]
  char v21; // [rsp+58h] [rbp-A8h]
  LPVOID lpBuffer; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID lpData[3]; // [rsp+68h] [rbp-98h] BYREF
  char *v24[4]; // [rsp+80h] [rbp-80h] BYREF
  char v25; // [rsp+A0h] [rbp-60h]
  char *v26[4]; // [rsp+A8h] [rbp-58h] BYREF
  char v27; // [rsp+C8h] [rbp-38h]
  __int128 v28; // [rsp+D0h] [rbp-30h] BYREF
  __int128 v29; // [rsp+E0h] [rbp-20h]
  char v30; // [rsp+F0h] [rbp-10h]
  __int128 v31; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v32; // [rsp+108h] [rbp+8h]
  _OWORD v33[2]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  v3 = a1;
  if ( *((_QWORD *)a1 + 3) > 7u )
    a1 = *(char **)a1;
  FileVersionInfoSizeW = GetFileVersionInfoSizeW((LPCWSTR)a1, 0);
  v5 = FileVersionInfoSizeW;
  if ( FileVersionInfoSizeW )
  {
    std::vector<unsigned char>::vector<unsigned char>(lpData, FileVersionInfoSizeW);
    if ( *((_QWORD *)v3 + 3) <= 7u )
      v7 = (const WCHAR *)v3;
    else
      v7 = *(const WCHAR **)v3;
    if ( GetFileVersionInfoW(v7, 0, v5, lpData[0]) )
    {
      v28 = 0;
      v29 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v28, L"ProductName", 0xBu);
      CertificateInfo::QueryVersionInfoString(&v19, lpData[0], &v28, 1033, 1200);
      std::wstring::~wstring((char **)&v28);
      v31 = 0;
      v32 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"FileDescription", 0xFu);
      LOWORD(v15) = 1200;
      CertificateInfo::QueryVersionInfoString(v26, lpData[0], &v31, 1033, v15);
      std::wstring::~wstring((char **)&v31);
      memset(v33, 0, sizeof(v33));
      std::wstring::_Construct<1,wchar_t const *>((char **)v33, L"CompanyName", 0xBu);
      LOWORD(v16) = 1200;
      CertificateInfo::QueryVersionInfoString(v24, lpData[0], v33, 1033, v16);
      std::wstring::~wstring((char **)v33);
      v9 = L"<not found>";
      if ( v25 )
      {
        v10 = v24;
        if ( v24[3] > (char *)7 )
          v10 = (char **)v24[0];
      }
      else
      {
        v10 = (char **)L"<not found>";
      }
      if ( v27 )
      {
        v11 = v26;
        if ( v26[3] > (char *)7 )
          v11 = (char **)v26[0];
      }
      else
      {
        v11 = (char **)L"<not found>";
      }
      if ( v21 )
      {
        v9 = (const wchar_t *)&v19;
        if ( *((_QWORD *)&v20 + 1) > 7u )
          v9 = (const wchar_t *)v19;
      }
      if ( *((_QWORD *)v3 + 3) <= 7u )
        v12 = (const WCHAR *)v3;
      else
        v12 = *(const WCHAR **)v3;
      Log(
        4u,
        L"[QueryAppIdentity] Version info for file %s: ProductName='%s', FileDescription='%s', CompanyName='%s'",
        v12,
        v9,
        v11,
        v10);
      if ( !v21 || !v27 || !v25 )
      {
        if ( *((_QWORD *)v3 + 3) > 7u )
          v3 = *(char **)v3;
        Log(
          4u,
          L"[QueryAppIdentity] Some version info properties are missing. Looking at the first language/codepage pair for file %s",
          v3);
        lpBuffer = 0;
        puLen = 0;
        if ( VerQueryValueW(lpData[0], L"\\VarFileInfo\\Translation", &lpBuffer, &puLen) && lpBuffer && puLen >= 4 )
        {
          v13 = *(_DWORD *)lpBuffer;
          v31 = 0;
          v32 = 0;
          std::wstring::_Construct<1,wchar_t const *>((char **)&v31, L"ProductName", 0xBu);
          LOWORD(v17) = HIWORD(v13);
          v14 = CertificateInfo::QueryVersionInfoString(&v28, lpData[0], &v31, (unsigned __int16)v13, v17);
          if ( *(_BYTE *)(v14 + 32) )
          {
            if ( v21 )
            {
              std::wstring::operator=(&v19, v14);
            }
            else
            {
              v19 = 0;
              v20 = 0;
              v19 = *(_OWORD *)v14;
              v20 = *(_OWORD *)(v14 + 16);
              *(_WORD *)v14 = 0;
              *(_QWORD *)(v14 + 16) = 0;
              *(_QWORD *)(v14 + 24) = 7;
              v21 = 1;
            }
          }
          else if ( v21 )
          {
            std::wstring::~wstring((char **)&v19);
            v21 = 0;
          }
          if ( v30 )
            std::wstring::~wstring((char **)&v28);
          std::wstring::~wstring((char **)&v31);
        }
      }
      if ( v21 )
      {
        std::wstring::wstring((__int64)&v28, (__int64)&v19);
      }
      else
      {
        v28 = 0;
        v29 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)&v28, &word_180096C4C, 0);
      }
      std::wstring::operator=(a2, &v28);
      std::wstring::~wstring((char **)&v28);
      if ( v25 )
        std::wstring::~wstring(v24);
      if ( v27 )
        std::wstring::~wstring(v26);
      if ( v21 )
        std::wstring::~wstring((char **)&v19);
      LastErrorMsg = 0;
    }
    else
    {
      if ( *((_QWORD *)v3 + 3) > 7u )
        v3 = *(char **)v3;
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x83,
                       (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
                       "[QueryAppIdentity] GetFileVersionInfo failed for file %s",
                       v3);
    }
    std::vector<unsigned char>::~vector<unsigned char>(lpData);
    return LastErrorMsg;
  }
  else
  {
    if ( *((_QWORD *)v3 + 3) > 7u )
      v3 = *(char **)v3;
    return wil::details::in1diag3::Return_GetLastErrorMsg(
             retaddr,
             (void *)0x7E,
             (unsigned int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\certificateinfo.cpp",
             "[QueryAppIdentity] GetFileVersionInfoSize failed for file %s",
             v3);
  }
}

```

## disassembly

```asm
0x18004cf04  mov     [rsp-8+arg_10], rbx
0x18004cf09  mov     [rsp-8+arg_18], rsi
0x18004cf0e  push    rbp
0x18004cf0f  push    rdi
0x18004cf10  push    r13
0x18004cf12  push    r14
0x18004cf14  push    r15
0x18004cf16  lea     rbp, [rsp-40h]
0x18004cf1b  sub     rsp, 140h
0x18004cf22  mov     rax, cs:__security_cookie
0x18004cf29  xor     rax, rsp
0x18004cf2c  mov     [rbp+60h+var_28], rax
0x18004cf30  mov     rsi, rdx
0x18004cf33  mov     rbx, rcx
0x18004cf36  xor     r15d, r15d
0x18004cf39  cmp     qword ptr [rcx+18h], 7
0x18004cf3e  jbe     short loc_18004CF43
0x18004cf40  mov     rcx, [rcx]; lptstrFilename
0x18004cf43  xor     edx, edx; lpdwHandle
0x18004cf45  call    cs:__imp_GetFileVersionInfoSizeW
0x18004cf4b  mov     edi, eax
0x18004cf4d  test    eax, eax
0x18004cf4f  jnz     short loc_18004CF81
0x18004cf51  cmp     qword ptr [rbx+18h], 7
0x18004cf56  jbe     short loc_18004CF5B
0x18004cf58  mov     rbx, [rbx]
0x18004cf5b  mov     rcx, [rbp+68h]; this
0x18004cf5f  mov     [rsp+160h+var_140], rbx; char *
0x18004cf64  lea     r9, aQueryappidenti_1; "[QueryAppIdentity] GetFileVersionInfoSi"...
0x18004cf6b  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004cf72  mov     edx, 7Eh ; '~'; void *
0x18004cf77  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004cf7c  jmp     loc_18004D32D
0x18004cf81  mov     rdx, rdi
0x18004cf84  lea     rcx, [rsp+160h+lpData]
0x18004cf89  call    ??0?$vector@EV?$allocator@E@std@@@std@@QEAA@_KAEBV?$allocator@E@1@@Z; std::vector<uchar>::vector<uchar>(unsigned __int64,std::allocator<uchar> const &)
0x18004cf8e  nop
0x18004cf8f  cmp     qword ptr [rbx+18h], 7
0x18004cf94  jbe     short loc_18004CF9B
0x18004cf96  mov     rcx, [rbx]
0x18004cf99  jmp     short loc_18004CF9E
0x18004cf9b  mov     rcx, rbx; lptstrFilename
0x18004cf9e  mov     r9, [rsp+160h+lpData]; lpData
0x18004cfa3  mov     r8d, edi; dwLen
0x18004cfa6  xor     edx, edx; dwHandle
0x18004cfa8  call    cs:__imp_GetFileVersionInfoW
0x18004cfae  test    eax, eax
0x18004cfb0  jnz     short loc_18004CFE4
0x18004cfb2  cmp     qword ptr [rbx+18h], 7
0x18004cfb7  jbe     short loc_18004CFBC
0x18004cfb9  mov     rbx, [rbx]
0x18004cfbc  mov     rcx, [rbp+68h]; this
0x18004cfc0  mov     [rsp+160h+var_140], rbx; char *
0x18004cfc5  lea     r9, aQueryappidenti_33; "[QueryAppIdentity] GetFileVersionInfo f"...
0x18004cfcc  lea     r8, aOnecoreuapWind_16; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18004cfd3  mov     edx, 83h; void *
0x18004cfd8  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004cfdd  mov     ebx, eax
0x18004cfdf  jmp     loc_18004D321
0x18004cfe4  xorps   xmm0, xmm0
0x18004cfe7  movups  [rbp+60h+var_90], xmm0
0x18004cfeb  xorps   xmm1, xmm1
0x18004cfee  movdqu  [rbp+60h+var_80], xmm1
0x18004cff3  mov     r13d, 0Bh
0x18004cff9  mov     r8d, r13d
0x18004cffc  lea     rdx, aProductname; "ProductName"
0x18004d003  lea     rcx, [rbp+60h+var_90]
0x18004d007  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d00c  nop
0x18004d00d  mov     edi, 409h
0x18004d012  mov     r14d, 4B0h
0x18004d018  mov     r9d, edi
0x18004d01b  mov     word ptr [rsp+160h+var_140], r14w
0x18004d021  lea     r8, [rbp+60h+var_90]
0x18004d025  mov     rdx, [rsp+160h+lpData]
0x18004d02a  lea     rcx, [rsp+160h+var_128]
0x18004d02f  call    ?QueryVersionInfoString@CertificateInfo@@CA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBEAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@GG@Z; CertificateInfo::QueryVersionInfoString(uchar const *,std::wstring const &,ushort,ushort)
0x18004d034  nop
0x18004d035  lea     rcx, [rbp+60h+var_90]
0x18004d039  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d03e  xorps   xmm0, xmm0
0x18004d041  movups  [rbp+60h+var_68], xmm0
0x18004d045  xorps   xmm1, xmm1
0x18004d048  movdqu  [rbp+60h+var_58], xmm1
0x18004d04d  lea     r8d, [r13+4]
0x18004d051  lea     rdx, aFiledescriptio; "FileDescription"
0x18004d058  lea     rcx, [rbp+60h+var_68]
0x18004d05c  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d061  nop
0x18004d062  mov     r9d, edi
0x18004d065  mov     word ptr [rsp+160h+var_140], r14w
0x18004d06b  lea     r8, [rbp+60h+var_68]
0x18004d06f  mov     rdx, [rsp+160h+lpData]
0x18004d074  lea     rcx, [rbp+60h+var_B8]
0x18004d078  call    ?QueryVersionInfoString@CertificateInfo@@CA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBEAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@GG@Z; CertificateInfo::QueryVersionInfoString(uchar const *,std::wstring const &,ushort,ushort)
0x18004d07d  nop
0x18004d07e  lea     rcx, [rbp+60h+var_68]
0x18004d082  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d087  xorps   xmm0, xmm0
0x18004d08a  movups  [rbp+60h+var_48], xmm0
0x18004d08e  xorps   xmm1, xmm1
0x18004d091  movdqu  [rbp+60h+var_38], xmm1
0x18004d096  mov     r8d, r13d
0x18004d099  lea     rdx, aCompanyname; "CompanyName"
0x18004d0a0  lea     rcx, [rbp+60h+var_48]
0x18004d0a4  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d0a9  nop
0x18004d0aa  mov     r9d, edi
0x18004d0ad  mov     word ptr [rsp+160h+var_140], r14w
0x18004d0b3  lea     r8, [rbp+60h+var_48]
0x18004d0b7  mov     rdx, [rsp+160h+lpData]
0x18004d0bc  lea     rcx, [rbp+60h+var_E0]
0x18004d0c0  call    ?QueryVersionInfoString@CertificateInfo@@CA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBEAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@GG@Z; CertificateInfo::QueryVersionInfoString(uchar const *,std::wstring const &,ushort,ushort)
0x18004d0c5  nop
0x18004d0c6  lea     rcx, [rbp+60h+var_48]
0x18004d0ca  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d0cf  lea     r9, aNotFound; "<not found>"
0x18004d0d6  cmp     [rbp+60h+var_C0], r15b
0x18004d0da  jz      short loc_18004D0EC
0x18004d0dc  lea     rcx, [rbp+60h+var_E0]
0x18004d0e0  cmp     [rbp+60h+var_C8], 7
0x18004d0e5  cmova   rcx, [rbp+60h+var_E0]
0x18004d0ea  jmp     short loc_18004D0EF
0x18004d0ec  mov     rcx, r9
0x18004d0ef  cmp     [rbp+60h+var_98], r15b
0x18004d0f3  jz      short loc_18004D105
0x18004d0f5  lea     rax, [rbp+60h+var_B8]
0x18004d0f9  cmp     [rbp+60h+var_A0], 7
0x18004d0fe  cmova   rax, [rbp+60h+var_B8]
0x18004d103  jmp     short loc_18004D108
0x18004d105  mov     rax, r9
0x18004d108  cmp     [rsp+160h+var_108], r15b
0x18004d10d  jz      short loc_18004D120
0x18004d10f  lea     r9, [rsp+160h+var_128]
0x18004d114  cmp     qword ptr [rsp+160h+var_118+8], 7
0x18004d11a  cmova   r9, qword ptr [rsp+160h+var_128]
0x18004d120  cmp     qword ptr [rbx+18h], 7
0x18004d125  jbe     short loc_18004D12C
0x18004d127  mov     r8, [rbx]
0x18004d12a  jmp     short loc_18004D12F
0x18004d12c  mov     r8, rbx
0x18004d12f  mov     [rsp+160h+var_138], rcx
0x18004d134  mov     [rsp+160h+var_140], rax
0x18004d139  lea     rdx, aQueryappidenti_21; "[QueryAppIdentity] Version info for fil"...
0x18004d140  mov     edi, 4
0x18004d145  mov     ecx, edi; unsigned __int8
0x18004d147  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004d14c  cmp     [rsp+160h+var_108], r15b
0x18004d151  jz      short loc_18004D163
0x18004d153  cmp     [rbp+60h+var_98], r15b
0x18004d157  jz      short loc_18004D163
0x18004d159  cmp     [rbp+60h+var_C0], r15b
0x18004d15d  jnz     loc_18004D2A2
0x18004d163  cmp     qword ptr [rbx+18h], 7
0x18004d168  jbe     short loc_18004D16D
0x18004d16a  mov     rbx, [rbx]
0x18004d16d  mov     r8, rbx
0x18004d170  lea     rdx, aQueryappidenti_4; "[QueryAppIdentity] Some version info pr"...
0x18004d177  mov     ecx, edi; unsigned __int8
0x18004d179  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18004d17e  mov     [rsp+160h+lpBuffer], r15
0x18004d183  mov     [rsp+160h+puLen], r15d
0x18004d188  lea     r9, [rsp+160h+puLen]; puLen
0x18004d18d  lea     r8, [rsp+160h+lpBuffer]; lplpBuffer
0x18004d192  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18004d199  mov     rcx, [rsp+160h+lpData]; pBlock
0x18004d19e  call    cs:__imp_VerQueryValueW
0x18004d1a4  test    eax, eax
0x18004d1a6  jz      loc_18004D2A2
0x18004d1ac  mov     rbx, [rsp+160h+lpBuffer]
0x18004d1b1  test    rbx, rbx
0x18004d1b4  jz      loc_18004D2A2
0x18004d1ba  cmp     [rsp+160h+puLen], edi
0x18004d1be  jb      loc_18004D2A2
0x18004d1c4  mov     ebx, [rbx]
0x18004d1c6  mov     edi, ebx
0x18004d1c8  shr     edi, 10h
0x18004d1cb  xorps   xmm0, xmm0
0x18004d1ce  movups  [rbp+60h+var_68], xmm0
0x18004d1d2  xorps   xmm1, xmm1
0x18004d1d5  movdqu  [rbp+60h+var_58], xmm1
0x18004d1da  mov     r8, r13
0x18004d1dd  lea     rdx, aProductname; "ProductName"
0x18004d1e4  lea     rcx, [rbp+60h+var_68]
0x18004d1e8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d1ed  nop
0x18004d1ee  movzx   r9d, bx
0x18004d1f2  mov     word ptr [rsp+160h+var_140], di
0x18004d1f7  lea     r8, [rbp+60h+var_68]
0x18004d1fb  mov     rdx, [rsp+160h+lpData]
0x18004d200  lea     rcx, [rbp+60h+var_90]
0x18004d204  call    ?QueryVersionInfoString@CertificateInfo@@CA?AV?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@PEBEAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@3@GG@Z; CertificateInfo::QueryVersionInfoString(uchar const *,std::wstring const &,ushort,ushort)
0x18004d209  mov     rcx, rax
0x18004d20c  cmp     [rax+20h], r15b
0x18004d210  jz      short loc_18004D273
0x18004d212  cmp     [rsp+160h+var_108], r15b
0x18004d217  jz      short loc_18004D228
0x18004d219  mov     rdx, rax
0x18004d21c  lea     rcx, [rsp+160h+var_128]
0x18004d221  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d226  jmp     short loc_18004D289
0x18004d228  xorps   xmm0, xmm0
0x18004d22b  movups  [rsp+160h+var_128], xmm0
0x18004d230  xorps   xmm1, xmm1
0x18004d233  movdqu  [rsp+160h+var_118], xmm1
0x18004d239  mov     rax, [rax]
0x18004d23c  mov     qword ptr [rsp+160h+var_128], rax
0x18004d241  mov     rax, [rcx+8]
0x18004d245  mov     qword ptr [rsp+160h+var_128+8], rax
0x18004d24a  mov     rax, [rcx+10h]
0x18004d24e  mov     qword ptr [rsp+160h+var_118], rax
0x18004d253  mov     rax, [rcx+18h]
0x18004d257  mov     qword ptr [rsp+160h+var_118+8], rax
0x18004d25c  mov     [rcx], r15w
0x18004d260  mov     [rcx+10h], r15
0x18004d264  mov     qword ptr [rcx+18h], 7
0x18004d26c  mov     [rsp+160h+var_108], 1
0x18004d271  jmp     short loc_18004D289
0x18004d273  cmp     [rsp+160h+var_108], r15b
0x18004d278  jz      short loc_18004D289
0x18004d27a  lea     rcx, [rsp+160h+var_128]
0x18004d27f  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d284  mov     [rsp+160h+var_108], r15b
0x18004d289  cmp     [rbp+60h+var_70], r15b
0x18004d28d  jz      short loc_18004D299
0x18004d28f  lea     rcx, [rbp+60h+var_90]
0x18004d293  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d298  nop
0x18004d299  lea     rcx, [rbp+60h+var_68]
0x18004d29d  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d2a2  lea     rcx, [rbp+60h+var_90]
0x18004d2a6  cmp     [rsp+160h+var_108], r15b
0x18004d2ab  jz      short loc_18004D2B9
0x18004d2ad  lea     rdx, [rsp+160h+var_128]
0x18004d2b2  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004d2b7  jmp     short loc_18004D2D7
0x18004d2b9  xorps   xmm0, xmm0
0x18004d2bc  movups  [rbp+60h+var_90], xmm0
0x18004d2c0  xorps   xmm1, xmm1
0x18004d2c3  movdqu  [rbp+60h+var_80], xmm1
0x18004d2c8  xor     r8d, r8d
0x18004d2cb  lea     rdx, word_180096C4C
0x18004d2d2  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18004d2d7  lea     rdx, [rbp+60h+var_90]
0x18004d2db  mov     rcx, rsi
0x18004d2de  call    ??4?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004d2e3  lea     rcx, [rbp+60h+var_90]
0x18004d2e7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d2ec  nop
0x18004d2ed  cmp     [rbp+60h+var_C0], r15b
0x18004d2f1  jz      short loc_18004D2FD
0x18004d2f3  lea     rcx, [rbp+60h+var_E0]
0x18004d2f7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d2fc  nop
0x18004d2fd  cmp     [rbp+60h+var_98], r15b
0x18004d301  jz      short loc_18004D30D
0x18004d303  lea     rcx, [rbp+60h+var_B8]
0x18004d307  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d30c  nop
0x18004d30d  cmp     [rsp+160h+var_108], r15b
0x18004d312  jz      short loc_18004D31E
0x18004d314  lea     rcx, [rsp+160h+var_128]
0x18004d319  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18004d31e  mov     ebx, r15d
0x18004d321  lea     rcx, [rsp+160h+lpData]
0x18004d326  call    ??1?$vector@EV?$allocator@E@std@@@std@@QEAA@XZ; std::vector<uchar>::~vector<uchar>(void)
0x18004d32b  mov     eax, ebx
0x18004d32d  mov     rcx, [rbp+60h+var_28]
0x18004d331  xor     rcx, rsp; StackCookie
0x18004d334  call    __security_check_cookie
0x18004d339  lea     r11, [rsp+160h+var_20]
0x18004d341  mov     rbx, [r11+40h]
0x18004d345  mov     rsi, [r11+48h]
0x18004d349  mov     rsp, r11
0x18004d34c  pop     r15
0x18004d34e  pop     r14
0x18004d350  pop     r13
0x18004d352  pop     rdi
0x18004d353  pop     rbp
0x18004d354  retn
```
