# CWorkspaceAppID::Initialize(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>)

- ea: `0x180057700`
- end: `0x180057b99`
- name: `?Initialize@CWorkspaceAppID@@QEAAJV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0000@Z`
- size: `1177`
- prototype: `__int64 __fastcall(HCRYPTPROV *this, void *, void *, void *, void *, void *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002b1a8`
- `0x18002cab8`

## callees

- `0x1800055d0`
- `0x18000b1d8`
- `0x18000d8d4`
- `0x18000dbdc`
- `0x18000ec94`
- `0x18000ece0`
- `0x18001082c`
- `0x18001b7e4`
- `0x18001e974`
- `0x18005720c`
- `0x180057700`
- `0x18009a520`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180057b3f`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180057b3f`
- `ADVAPI32!CryptCreateHash` at `0x180057820`
- `ADVAPI32!CryptCreateHash` at `0x180057820`
- `ADVAPI32!CryptAcquireContextW` at `0x18005778d`
- `ADVAPI32!CryptAcquireContextW` at `0x18005778d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005782a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180057797`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005782a`

## pseudocode

```c
__int64 __fastcall CWorkspaceAppID::Initialize(HCRYPTPROV *this, void *a2, void *a3, void *a4, void *a5, void *a6)
{
  signed int LastError; // ebx
  unsigned int v11; // eax
  unsigned int v12; // eax
  __int64 v13; // rbx
  __int64 v14; // rax
  unsigned int v15; // eax
  unsigned int v16; // eax
  unsigned int v17; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  void *v20; // [rsp+38h] [rbp-2A0h]
  unsigned __int16 *v21; // [rsp+40h] [rbp-298h] BYREF
  unsigned int v22[2]; // [rsp+48h] [rbp-290h] BYREF
  __int64 v23; // [rsp+50h] [rbp-288h]
  void *v24; // [rsp+58h] [rbp-280h]
  void *v25; // [rsp+60h] [rbp-278h]
  void *v26; // [rsp+68h] [rbp-270h]
  __int64 v27; // [rsp+70h] [rbp-268h]
  void *v28; // [rsp+78h] [rbp-260h]
  unsigned __int16 v29[268]; // [rsp+80h] [rbp-258h] BYREF

  v23 = -2;
  v24 = a2;
  v25 = a3;
  v26 = a4;
  v20 = a5;
  v27 = (__int64)a5;
  v28 = a6;
  *(_QWORD *)v22 = 0;
  v21 = 0;
  if ( CryptAcquireContextW(this + 7, 0, L"Microsoft Enhanced RSA and AES Cryptographic Provider", 0x18u, 0xF0000000) )
  {
    if ( CryptCreateHash(this[7], 0x800Cu, 0, 0, this + 8) )
    {
      v29[0] = 0;
      v13 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a6);
      v14 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a2);
      LastError = StringCchPrintfW(v29, 0x104u, L"%s.%s", v14, v13);
      if ( LastError == -2147024774 )
        LastError = 0;
      if ( LastError >= 0 )
      {
        LastError = StringCchLengthW(v29, 0x104u, (unsigned __int64 *)v22);
        if ( LastError >= 0 )
        {
          LastError = CWorkspaceAppID::HashAppID((CWorkspaceAppID *)this, v29, v22[0], &v21);
          if ( LastError >= 0 )
          {
            LastError = StringCchPrintfW(v29, 0x104u, L"Microsoft.RemoteApp.%s", v21);
            if ( LastError >= 0 )
            {
              std::wstring::assign(this + 13, v29);
              std::wstring::operator=(this + 9, a3);
              std::wstring::operator=(this + 25, a4);
              std::wstring::operator=(this + 21, a5);
              std::wstring::operator=(this + 17, a6);
              LastError = 0;
            }
            else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                   && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                   && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
            {
              CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
              WPP_SF_DsD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                17,
                (unsigned int)WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
                CurrentThreadActivityIdPrefix,
                (__int64)"StringCchPrintf failed",
                LastError,
                LastError,
                a5);
            }
          }
          else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
                 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            v17 = RdpWppGetCurrentThreadActivityIdPrefix();
            WPP_SF_DsD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              16,
              (unsigned int)WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
              v17,
              (__int64)"Failed to hash the AppID",
              LastError,
              LastError,
              a5);
          }
          if ( v21 )
            operator delete[](v21);
        }
        else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
               && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v16 = RdpWppGetCurrentThreadActivityIdPrefix();
          WPP_SF_DsD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            15,
            (unsigned int)WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
            v16,
            (__int64)"StringCchLength failed",
            LastError,
            LastError,
            a5);
        }
      }
      else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
             && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
             && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v15 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_DsD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          14,
          (unsigned int)WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
          v15,
          (__int64)"StringCchPrintf failed",
          LastError,
          LastError,
          a5);
      }
    }
    else
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v12 = RdpWppGetCurrentThreadActivityIdPrefix();
        WPP_SF_Dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          13,
          WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
          v12,
          LastError);
      }
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      if ( LastError >= 0 )
        LastError = -2147467259;
    }
  }
  else
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = RdpWppGetCurrentThreadActivityIdPrefix();
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids,
        v11,
        LastError);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( LastError >= 0 )
      LastError = -2147467259;
  }
  std::wstring::~wstring(a2);
  std::wstring::~wstring(a3);
  std::wstring::~wstring(a4);
  std::wstring::~wstring(v20);
  std::wstring::~wstring(a6);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x180057700  push    rbx
0x180057702  push    rsi
0x180057703  push    rdi
0x180057704  push    r12
0x180057706  push    r13
0x180057708  push    r14
0x18005770a  push    r15
0x18005770c  sub     rsp, 2A0h
0x180057713  mov     [rsp+2D8h+var_288], 0FFFFFFFFFFFFFFFEh
0x18005771c  mov     rax, cs:__security_cookie
0x180057723  xor     rax, rsp
0x180057726  mov     [rsp+2D8h+var_40], rax
0x18005772e  mov     r15, r9
0x180057731  mov     r14, r8
0x180057734  mov     r12, rdx
0x180057737  mov     rsi, rcx
0x18005773a  mov     [rsp+2D8h+var_280], rdx
0x18005773f  mov     [rsp+2D8h+var_278], r8
0x180057744  mov     [rsp+2D8h+var_270], r9
0x180057749  mov     rax, [rsp+2D8h+arg_20]
0x180057751  mov     [rsp+2D8h+var_2A0], rax
0x180057756  mov     [rsp+2D8h+var_268], rax
0x18005775b  mov     r13, [rsp+2D8h+arg_28]
0x180057763  mov     [rsp+2D8h+var_260], r13
0x180057768  xor     edi, edi
0x18005776a  mov     qword ptr [rsp+2D8h+var_290], rdi
0x18005776f  mov     [rsp+2D8h+var_298], rdi
0x180057774  mov     [rsp+2D8h+dwFlags], 0F0000000h; dwFlags
0x18005777c  lea     r9d, [rdi+18h]; dwProvType
0x180057780  lea     r8, szProvider; "Microsoft Enhanced RSA and AES Cryptogr"...
0x180057787  xor     edx, edx; szContainer
0x180057789  add     rcx, 38h ; '8'; phProv
0x18005778d  call    cs:__imp_CryptAcquireContextW
0x180057793  test    eax, eax
0x180057795  jnz     short loc_180057808
0x180057797  call    cs:__imp_GetLastError
0x18005779d  mov     ebx, eax
0x18005779f  lea     rax, WPP_GLOBAL_Control
0x1800577a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800577ad  cmp     rcx, rax
0x1800577b0  jz      short loc_1800577E4
0x1800577b2  test    byte ptr [rcx+1Ch], 8
0x1800577b6  jz      short loc_1800577E4
0x1800577b8  cmp     byte ptr [rcx+19h], 2
0x1800577bc  jb      short loc_1800577E4
0x1800577be  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800577c3  lea     edx, [rdi+0Ch]
0x1800577c6  mov     [rsp+2D8h+dwFlags], ebx
0x1800577ca  mov     r9d, eax
0x1800577cd  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x1800577d4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800577db  mov     rcx, [rcx+10h]
0x1800577df  call    WPP_SF_Dd
0x1800577e4  test    ebx, ebx
0x1800577e6  jle     short loc_1800577F1
0x1800577e8  movzx   ebx, bx
0x1800577eb  or      ebx, 80070000h
0x1800577f1  mov     [rsp+2D8h+var_2A8], ebx
0x1800577f5  mov     eax, 80004005h
0x1800577fa  test    ebx, ebx
0x1800577fc  cmovns  ebx, eax
0x1800577ff  mov     [rsp+2D8h+var_2A8], ebx
0x180057803  jmp     loc_180057B46
0x180057808  lea     rax, [rsi+40h]
0x18005780c  mov     qword ptr [rsp+2D8h+dwFlags], rax; phHash
0x180057811  xor     r9d, r9d; dwFlags
0x180057814  xor     r8d, r8d; hKey
0x180057817  mov     edx, 800Ch; Algid
0x18005781c  mov     rcx, [rsi+38h]; hProv
0x180057820  call    cs:__imp_CryptCreateHash
0x180057826  test    eax, eax
0x180057828  jnz     short loc_18005789D
0x18005782a  call    cs:__imp_GetLastError
0x180057830  mov     ebx, eax
0x180057832  lea     rax, WPP_GLOBAL_Control
0x180057839  mov     rcx, cs:WPP_GLOBAL_Control
0x180057840  cmp     rcx, rax
0x180057843  jz      short loc_180057879
0x180057845  test    byte ptr [rcx+1Ch], 8
0x180057849  jz      short loc_180057879
0x18005784b  cmp     byte ptr [rcx+19h], 2
0x18005784f  jb      short loc_180057879
0x180057851  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057856  mov     edx, 0Dh
0x18005785b  mov     [rsp+2D8h+dwFlags], ebx
0x18005785f  mov     r9d, eax
0x180057862  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x180057869  mov     rcx, cs:WPP_GLOBAL_Control
0x180057870  mov     rcx, [rcx+10h]
0x180057874  call    WPP_SF_Dd
0x180057879  test    ebx, ebx
0x18005787b  jle     short loc_180057886
0x18005787d  movzx   ebx, bx
0x180057880  or      ebx, 80070000h
0x180057886  mov     [rsp+2D8h+var_2A8], ebx
0x18005788a  mov     eax, 80004005h
0x18005788f  test    ebx, ebx
0x180057891  cmovns  ebx, eax
0x180057894  mov     [rsp+2D8h+var_2A8], ebx
0x180057898  jmp     loc_180057B46
0x18005789d  mov     [rsp+2D8h+var_258], di
0x1800578a5  mov     rcx, r13
0x1800578a8  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800578ad  mov     rbx, rax
0x1800578b0  mov     rcx, r12
0x1800578b3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800578b8  mov     qword ptr [rsp+2D8h+dwFlags], rbx
0x1800578bd  mov     r9, rax
0x1800578c0  lea     r8, aSS; "%s.%s"
0x1800578c7  mov     edx, 104h; unsigned __int64
0x1800578cc  lea     rcx, [rsp+2D8h+var_258]; unsigned __int16 *
0x1800578d4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x1800578d9  mov     ebx, eax
0x1800578db  mov     [rsp+2D8h+var_2A8], eax
0x1800578df  cmp     eax, 8007007Ah
0x1800578e4  cmovz   ebx, edi
0x1800578e7  mov     [rsp+2D8h+var_2A8], ebx
0x1800578eb  test    ebx, ebx
0x1800578ed  jns     short loc_180057948
0x1800578ef  lea     rax, WPP_GLOBAL_Control
0x1800578f6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800578fd  cmp     rcx, rax
0x180057900  jz      short loc_180057943
0x180057902  test    byte ptr [rcx+1Ch], 8
0x180057906  jz      short loc_180057943
0x180057908  cmp     byte ptr [rcx+19h], 2
0x18005790c  jb      short loc_180057943
0x18005790e  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057913  mov     edx, 0Eh
0x180057918  mov     [rsp+2D8h+var_2B0], ebx
0x18005791c  lea     rcx, aStringcchprint_5; "StringCchPrintf failed"
0x180057923  mov     qword ptr [rsp+2D8h+dwFlags], rcx
0x180057928  mov     r9d, eax
0x18005792b  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x180057932  mov     rcx, cs:WPP_GLOBAL_Control
0x180057939  mov     rcx, [rcx+10h]
0x18005793d  call    WPP_SF_DsD
0x180057942  nop
0x180057943  jmp     loc_180057B46
0x180057948  lea     r8, [rsp+2D8h+var_290]; unsigned __int64 *
0x18005794d  mov     edx, 104h; unsigned __int64
0x180057952  lea     rcx, [rsp+2D8h+var_258]; unsigned __int16 *
0x18005795a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005795f  mov     ebx, eax
0x180057961  mov     [rsp+2D8h+var_2A8], eax
0x180057965  test    eax, eax
0x180057967  jns     short loc_1800579C2
0x180057969  lea     rax, WPP_GLOBAL_Control
0x180057970  mov     rcx, cs:WPP_GLOBAL_Control
0x180057977  cmp     rcx, rax
0x18005797a  jz      short loc_1800579BD
0x18005797c  test    byte ptr [rcx+1Ch], 8
0x180057980  jz      short loc_1800579BD
0x180057982  cmp     byte ptr [rcx+19h], 2
0x180057986  jb      short loc_1800579BD
0x180057988  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x18005798d  mov     edx, 0Fh
0x180057992  mov     [rsp+2D8h+var_2B0], ebx
0x180057996  lea     rcx, aStringcchlengt_0; "StringCchLength failed"
0x18005799d  mov     qword ptr [rsp+2D8h+dwFlags], rcx
0x1800579a2  mov     r9d, eax
0x1800579a5  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x1800579ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579b3  mov     rcx, [rcx+10h]
0x1800579b7  call    WPP_SF_DsD
0x1800579bc  nop
0x1800579bd  jmp     loc_180057B46
0x1800579c2  lea     r9, [rsp+2D8h+var_298]; unsigned __int16 **
0x1800579c7  mov     r8d, [rsp+2D8h+var_290]; unsigned int
0x1800579cc  lea     rdx, [rsp+2D8h+var_258]; unsigned __int16 *
0x1800579d4  mov     rcx, rsi; this
0x1800579d7  call    ?HashAppID@CWorkspaceAppID@@IEAAJPEAGKPEAPEAG@Z; CWorkspaceAppID::HashAppID(ushort *,ulong,ushort * *)
0x1800579dc  mov     ebx, eax
0x1800579de  mov     [rsp+2D8h+var_2A8], eax
0x1800579e2  test    eax, eax
0x1800579e4  jns     short loc_180057A3F
0x1800579e6  lea     rax, WPP_GLOBAL_Control
0x1800579ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800579f4  cmp     rcx, rax
0x1800579f7  jz      short loc_180057A3A
0x1800579f9  test    byte ptr [rcx+1Ch], 8
0x1800579fd  jz      short loc_180057A3A
0x1800579ff  cmp     byte ptr [rcx+19h], 2
0x180057a03  jb      short loc_180057A3A
0x180057a05  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057a0a  mov     edx, 10h
0x180057a0f  mov     [rsp+2D8h+var_2B0], ebx
0x180057a13  lea     rcx, aFailedToHashTh; "Failed to hash the AppID"
0x180057a1a  mov     qword ptr [rsp+2D8h+dwFlags], rcx
0x180057a1f  mov     r9d, eax
0x180057a22  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x180057a29  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a30  mov     rcx, [rcx+10h]
0x180057a34  call    WPP_SF_DsD
0x180057a39  nop
0x180057a3a  jmp     loc_180057B35
0x180057a3f  mov     r9, [rsp+2D8h+var_298]
0x180057a44  lea     r8, aMicrosoftRemot_0; "Microsoft.RemoteApp.%s"
0x180057a4b  mov     edx, 104h; unsigned __int64
0x180057a50  lea     rcx, [rsp+2D8h+var_258]; unsigned __int16 *
0x180057a58  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180057a5d  mov     ebx, eax
0x180057a5f  mov     [rsp+2D8h+var_2A8], eax
0x180057a63  test    eax, eax
0x180057a65  jns     short loc_180057ABD
0x180057a67  lea     rax, WPP_GLOBAL_Control
0x180057a6e  mov     rcx, cs:WPP_GLOBAL_Control
0x180057a75  cmp     rcx, rax
0x180057a78  jz      short loc_180057ABB
0x180057a7a  test    byte ptr [rcx+1Ch], 8
0x180057a7e  jz      short loc_180057ABB
0x180057a80  cmp     byte ptr [rcx+19h], 2
0x180057a84  jb      short loc_180057ABB
0x180057a86  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180057a8b  mov     edx, 11h
0x180057a90  mov     [rsp+2D8h+var_2B0], ebx
0x180057a94  lea     rcx, aStringcchprint_5; "StringCchPrintf failed"
0x180057a9b  mov     qword ptr [rsp+2D8h+dwFlags], rcx
0x180057aa0  mov     r9d, eax
0x180057aa3  lea     r8, WPP_f51c5e3e826e3b7bca8cf1008c817bdb_Traceguids
0x180057aaa  mov     rcx, cs:WPP_GLOBAL_Control
0x180057ab1  mov     rcx, [rcx+10h]
0x180057ab5  call    WPP_SF_DsD
0x180057aba  nop
0x180057abb  jmp     short loc_180057B35
0x180057abd  lea     rcx, [rsi+68h]
0x180057ac1  lea     rdx, [rsp+2D8h+var_258]
0x180057ac9  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x180057ace  lea     rcx, [rsi+48h]
0x180057ad2  mov     rdx, r14
0x180057ad5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180057ada  lea     rcx, [rsi+0C8h]
0x180057ae1  mov     rdx, r15
0x180057ae4  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180057ae9  lea     rcx, [rsi+0A8h]
0x180057af0  mov     rdx, [rsp+2D8h+var_2A0]
0x180057af5  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180057afa  lea     rcx, [rsi+88h]
0x180057b01  mov     rdx, r13
0x180057b04  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x180057b09  mov     ebx, edi
0x180057b0b  mov     [rsp+2D8h+var_2A8], ebx
0x180057b0f  jmp     short loc_180057B35
0x180057b11  jmp     short $+2
0x180057b13  mov     rax, [rsp+2D8h+var_268]
0x180057b18  mov     r13, [rsp+2D8h+var_260]
0x180057b1d  mov     [rsp+2D8h+var_2A0], rax
0x180057b22  mov     r15, [rsp+2D8h+var_270]
0x180057b27  mov     r14, [rsp+2D8h+var_278]
0x180057b2c  mov     r12, [rsp+2D8h+var_280]
0x180057b31  mov     ebx, [rsp+2D8h+var_2A8]
0x180057b35  mov     rcx, [rsp+2D8h+var_298]
0x180057b3a  test    rcx, rcx
0x180057b3d  jz      short loc_180057B46
0x180057b3f  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180057b45  nop
0x180057b46  mov     rcx, r12; void *
0x180057b49  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057b4e  nop
0x180057b4f  mov     rcx, r14; void *
0x180057b52  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057b57  nop
0x180057b58  mov     rcx, r15; void *
0x180057b5b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057b60  nop
0x180057b61  mov     rcx, [rsp+2D8h+var_2A0]; void *
0x180057b66  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057b6b  nop
0x180057b6c  mov     rcx, r13; void *
0x180057b6f  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180057b74  mov     eax, ebx
0x180057b76  mov     rcx, [rsp+2D8h+var_40]
0x180057b7e  xor     rcx, rsp; StackCookie
0x180057b81  call    __security_check_cookie
0x180057b86  add     rsp, 2A0h
0x180057b8d  pop     r15
0x180057b8f  pop     r14
0x180057b91  pop     r13
0x180057b93  pop     r12
0x180057b95  pop     rdi
0x180057b96  pop     rsi
0x180057b97  pop     rbx
0x180057b98  retn
```
