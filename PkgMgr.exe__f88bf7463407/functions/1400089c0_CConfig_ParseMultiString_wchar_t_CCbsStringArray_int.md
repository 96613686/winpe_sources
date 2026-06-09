# CConfig::ParseMultiString(wchar_t *,CCbsStringArray *,int)

- ea: `0x1400089c0`
- end: `0x140008bce`
- name: `?ParseMultiString@CConfig@@AEAAJPEA_WPEAVCCbsStringArray@@H@Z`
- size: `526`
- prototype: `int(CConfig *__hidden this, wchar_t *, struct CCbsStringArray *, int)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x140007524`

## callees

- `0x140002360`
- `0x1400056ac`
- `0x1400067bc`
- `0x140006c50`
- `0x14000726c`
- `0x1400072a8`
- `0x140007334`
- `0x1400089c0`
- `0x14000903c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140008a16`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140008a16`

## string_xrefs

- `0x140008ae6`: `onecore\base\cbs\pkgmgrshim\config.cpp`
- `0x140008b06`: `Failed getting full path`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CConfig::ParseMultiString(CConfig *this, wchar_t *a2, struct CCbsStringArray *a3, int a4)
{
  const wchar_t *v6; // rbx
  wchar_t *v7; // rax
  wchar_t *v8; // rdi
  int FullDirPathW; // ebx
  int v10; // edx
  __int64 v11; // rdx
  int v12; // edx
  int v13; // edx
  int v15; // [rsp+20h] [rbp-40h]
  int v16[2]; // [rsp+30h] [rbp-30h] BYREF
  wchar_t *v17[2]; // [rsp+38h] [rbp-28h] BYREF
  wchar_t *v18; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]

  v17[1] = (wchar_t *)-2LL;
  v6 = a2;
  v17[0] = 0;
  if ( a2 )
  {
    while ( *v6 )
    {
      v7 = wcschr(v6, 0x3Bu);
      v8 = v7;
      if ( v7 )
      {
        *v7 = 0;
        v8 = v7 + 1;
      }
      if ( a4 )
      {
        FullDirPathW = GetFullDirPathW(v17, v6);
        if ( FullDirPathW < 0 )
        {
          LODWORD(v18) = FullDirPathW;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed getting full path");
            *(_QWORD *)v16 = &v18;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v12,
              3,
              (unsigned int)": {}",
              (__int64)v16);
          }
          v11 = 472;
          goto LABEL_15;
        }
        v18 = v17[0];
        FullDirPathW = CCbsArrayBase<wchar_t *,CCbsStringArray>::InsertAt(a3, &v18, *((_QWORD *)a3 + 3));
        if ( FullDirPathW < 0 )
        {
          LODWORD(v18) = FullDirPathW;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add a value to the option array");
            *(_QWORD *)v16 = &v18;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v10,
              3,
              (unsigned int)": {}",
              (__int64)v16);
          }
          v11 = 474;
LABEL_15:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"onecore\\base\\cbs\\pkgmgrshim\\config.cpp",
            (const char *)(unsigned int)FullDirPathW,
            v15);
          goto LABEL_23;
        }
        v17[0] = 0;
      }
      else
      {
        FullDirPathW = CCbsStringArray::CopyAndAdd(a3, v6);
        if ( FullDirPathW < 0 )
        {
          LODWORD(v18) = FullDirPathW;
          if ( LogAdapter::g_Logger )
          {
            LogAdapter::Logger::LogNumObjects<>(LogAdapter::g_Logger, 0, 3, "Failed to add a value to the option array");
            *(_QWORD *)v16 = &v18;
            LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
              (_DWORD)LogAdapter::g_Logger,
              v13,
              3,
              (unsigned int)": {}",
              (__int64)v16);
          }
          v11 = 479;
          goto LABEL_15;
        }
      }
      if ( !v8 )
        break;
      v6 = v8;
    }
  }
  FullDirPathW = 0;
LABEL_23:
  Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(v17);
  return (unsigned int)FullDirPathW;
}

```

## disassembly

```asm
0x1400089c0  mov     rax, rsp
0x1400089c3  push    rbp
0x1400089c4  push    rsi
0x1400089c5  push    rdi
0x1400089c6  push    r14
0x1400089c8  push    r15
0x1400089ca  mov     rbp, rsp
0x1400089cd  sub     rsp, 60h
0x1400089d1  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFEh
0x1400089d9  mov     [rax+8], rbx
0x1400089dd  mov     rax, cs:__security_cookie
0x1400089e4  xor     rax, rsp
0x1400089e7  mov     [rbp+var_10], rax
0x1400089eb  mov     r14d, r9d
0x1400089ee  mov     rsi, r8
0x1400089f1  mov     rbx, rdx
0x1400089f4  xor     r15d, r15d
0x1400089f7  mov     [rbp+var_28], r15
0x1400089fb  test    rdx, rdx
0x1400089fe  jz      loc_140008BA0
0x140008a04  cmp     [rbx], r15w
0x140008a08  jz      loc_140008BA0
0x140008a0e  mov     edx, 3Bh ; ';'; Ch
0x140008a13  mov     rcx, rbx; Str
0x140008a16  call    cs:__imp_wcschr
0x140008a1c  mov     rdi, rax
0x140008a1f  test    rax, rax
0x140008a22  jz      short loc_140008A2C
0x140008a24  mov     [rax], r15w
0x140008a28  add     rdi, 2
0x140008a2c  mov     rdx, rbx; wchar_t *
0x140008a2f  test    r14d, r14d
0x140008a32  jz      short loc_140008A6B
0x140008a34  lea     rcx, [rbp+var_28]; wchar_t **
0x140008a38  call    ?GetFullDirPathW@@YAJPEAPEA_WPEB_W@Z; GetFullDirPathW(wchar_t * *,wchar_t const *)
0x140008a3d  mov     ebx, eax
0x140008a3f  test    eax, eax
0x140008a41  js      loc_140008AF7
0x140008a47  mov     rax, [rbp+var_28]
0x140008a4b  mov     [rbp+var_18], rax
0x140008a4f  mov     r8, [rsi+18h]
0x140008a53  lea     rdx, [rbp+var_18]
0x140008a57  mov     rcx, rsi
0x140008a5a  call    ?InsertAt@?$CCbsArrayBase@PEA_WVCCbsStringArray@@@@QEAAJAEBQEA_W_K@Z; CCbsArrayBase<wchar_t *,CCbsStringArray>::InsertAt(wchar_t * const &,unsigned __int64)
0x140008a5f  mov     ebx, eax
0x140008a61  test    eax, eax
0x140008a63  js      short loc_140008A8E
0x140008a65  mov     [rbp+var_28], r15
0x140008a69  jmp     short loc_140008A7D
0x140008a6b  mov     rcx, rsi; this
0x140008a6e  call    ?CopyAndAdd@CCbsStringArray@@QEAAJPEB_W@Z; CCbsStringArray::CopyAndAdd(wchar_t const *)
0x140008a73  mov     ebx, eax
0x140008a75  test    eax, eax
0x140008a77  js      loc_140008B4A
0x140008a7d  test    rdi, rdi
0x140008a80  jz      loc_140008BA0
0x140008a86  mov     rbx, rdi
0x140008a89  jmp     loc_140008A04
0x140008a8e  mov     dword ptr [rbp+var_18], ebx
0x140008a91  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008a98  test    rcx, rcx
0x140008a9b  jz      short loc_140008ADA
0x140008a9d  lea     r9, aFailedToAddAVa; "Failed to add a value to the option arr"...
0x140008aa4  mov     edi, 3
0x140008aa9  mov     r8d, edi
0x140008aac  xor     edx, edx
0x140008aae  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140008ab3  lea     rax, [rbp+var_18]
0x140008ab7  mov     qword ptr [rbp+var_30], rax
0x140008abb  lea     rax, [rbp+var_30]
0x140008abf  mov     qword ptr [rsp+60h+var_40], rax; int
0x140008ac4  lea     r9, asc_14002D4FC; ": {}"
0x140008acb  mov     r8d, edi
0x140008ace  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008ad5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140008ada  mov     edx, 1DAh; void *
0x140008adf  mov     rcx, [rbp+28h]; this
0x140008ae3  mov     r9d, ebx; char *
0x140008ae6  lea     r8, aOnecoreBaseCbs; "onecore\\base\\cbs\\pkgmgrshim\\config."...
0x140008aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140008af2  jmp     loc_140008BA3
0x140008af7  mov     dword ptr [rbp+var_18], ebx
0x140008afa  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008b01  test    rcx, rcx
0x140008b04  jz      short loc_140008B43
0x140008b06  lea     r9, aFailedGettingF; "Failed getting full path"
0x140008b0d  mov     edi, 3
0x140008b12  mov     r8d, edi
0x140008b15  xor     edx, edx
0x140008b17  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140008b1c  lea     rax, [rbp+var_18]
0x140008b20  mov     qword ptr [rbp+var_30], rax
0x140008b24  lea     rax, [rbp+var_30]
0x140008b28  mov     qword ptr [rsp+60h+var_40], rax
0x140008b2d  lea     r9, asc_14002D4FC; ": {}"
0x140008b34  mov     r8d, edi
0x140008b37  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008b3e  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140008b43  mov     edx, 1D8h
0x140008b48  jmp     short loc_140008ADF
0x140008b4a  mov     dword ptr [rbp+var_18], ebx
0x140008b4d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008b54  test    rcx, rcx
0x140008b57  jz      short loc_140008B96
0x140008b59  lea     r9, aFailedToAddAVa; "Failed to add a value to the option arr"...
0x140008b60  mov     edi, 3
0x140008b65  mov     r8d, edi
0x140008b68  xor     edx, edx
0x140008b6a  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x140008b6f  lea     rax, [rbp+var_18]
0x140008b73  mov     qword ptr [rbp+var_30], rax
0x140008b77  lea     rax, [rbp+var_30]
0x140008b7b  mov     qword ptr [rsp+60h+var_40], rax
0x140008b80  lea     r9, asc_14002D4FC; ": {}"
0x140008b87  mov     r8d, edi
0x140008b8a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x140008b91  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x140008b96  mov     edx, 1DFh
0x140008b9b  jmp     loc_140008ADF
0x140008ba0  mov     ebx, r15d
0x140008ba3  lea     rcx, [rbp+var_28]
0x140008ba7  call    ?Close@?$AutoGenericHandleBase@PEA_W$0A@VAutoScz@@@Windows@@QEAAXXZ; Windows::AutoGenericHandleBase<wchar_t *,0,AutoScz>::Close(void)
0x140008bac  mov     eax, ebx
0x140008bae  mov     rcx, [rbp+var_10]
0x140008bb2  xor     rcx, rsp; StackCookie
0x140008bb5  call    __security_check_cookie
0x140008bba  mov     rbx, [rsp+60h+arg_0]
0x140008bc2  add     rsp, 60h
0x140008bc6  pop     r15
0x140008bc8  pop     r14
0x140008bca  pop     rdi
0x140008bcb  pop     rsi
0x140008bcc  pop     rbp
0x140008bcd  retn
```
