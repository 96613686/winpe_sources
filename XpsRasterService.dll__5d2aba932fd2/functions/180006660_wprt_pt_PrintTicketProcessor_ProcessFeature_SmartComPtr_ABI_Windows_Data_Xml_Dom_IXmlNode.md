# wprt::pt::PrintTicketProcessor::ProcessFeature(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)

- ea: `0x180006660`
- end: `0x180006937`
- name: `?ProcessFeature@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z`
- size: `727`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006140`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d3c`
- `0x180005b80`
- `0x180005eb0`
- `0x180006660`
- `0x180006940`
- `0x180006de0`
- `0x180007150`
- `0x1800a030f`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000673e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800067f7`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800068b0`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000673e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800067f7`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800068b0`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
HRESULT __fastcall wprt::pt::PrintTicketProcessor::ProcessFeature(__int64 a1, HSTRING *a2)
{
  HSTRING v4; // rcx
  char v5; // si
  void *v6; // rcx
  HSTRING v7; // rcx
  char v8; // si
  void *v9; // rcx
  HSTRING v10; // rcx
  char v11; // si
  void *v12; // rcx
  HSTRING v13; // rcx
  HRESULT result; // eax
  HSTRING v15; // rcx
  HSTRING newString; // [rsp+20h] [rbp-40h] BYREF
  void *Block[2]; // [rsp+28h] [rbp-38h] BYREF
  __int128 v18; // [rsp+38h] [rbp-28h]
  HSTRING *v19; // [rsp+48h] [rbp-18h]
  HSTRING string; // [rsp+50h] [rbp-10h] BYREF

  v19 = a2;
  string = 0;
  v4 = *a2;
  newString = v4;
  if ( v4 )
    (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v4 + 8LL))(v4);
  if ( !(unsigned int)GET_NAME_ATTRIBUTE_VALUE(&newString, (__int64)&string) )
  {
    *(_OWORD *)Block = 0;
    v18 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)Block, L"PageMediaSize", 0xDu);
    newString = 0;
    WindowsDuplicateString_0(string, &newString);
    v5 = MATCHES_ANY_NAMESPACE(&newString, Block);
    if ( *((_QWORD *)&v18 + 1) >= 8u )
    {
      v6 = Block[0];
      if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
      {
        v6 = (void *)*((_QWORD *)Block[0] - 1);
        if ( (unsigned __int64)((char *)Block[0] - (char *)v6 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v6, 2LL * *((_QWORD *)&v18 + 1) + 41);
          __debugbreak();
        }
      }
      operator delete(v6);
    }
    if ( v5 )
    {
      v7 = *a2;
      newString = v7;
      if ( v7 )
        (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v7 + 8LL))(v7);
      wprt::pt::PrintTicketProcessor::ProcessMediaSize(a1, &newString);
    }
    else
    {
      *(_OWORD *)Block = 0;
      v18 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)Block, L"PageOrientation", 0xFu);
      newString = 0;
      WindowsDuplicateString_0(string, &newString);
      v8 = MATCHES_ANY_NAMESPACE(&newString, Block);
      if ( *((_QWORD *)&v18 + 1) >= 8u )
      {
        v9 = Block[0];
        if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
        {
          v9 = (void *)*((_QWORD *)Block[0] - 1);
          if ( (unsigned __int64)((char *)Block[0] - (char *)v9 - 8) > 0x1F )
          {
            _o__invalid_parameter_noinfo_noreturn(v9, 2LL * *((_QWORD *)&v18 + 1) + 41);
            __debugbreak();
          }
        }
        operator delete(v9);
      }
      if ( v8 )
      {
        v10 = *a2;
        newString = v10;
        if ( v10 )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v10 + 8LL))(v10);
        wprt::pt::PrintTicketProcessor::ProcessOrientation(a1, &newString);
      }
      else
      {
        *(_OWORD *)Block = 0;
        v18 = 0;
        std::wstring::_Construct<1,wchar_t const *>((char **)Block, L"PageScaling", 0xBu);
        newString = 0;
        WindowsDuplicateString_0(string, &newString);
        v11 = MATCHES_ANY_NAMESPACE(&newString, Block);
        if ( *((_QWORD *)&v18 + 1) >= 8u )
        {
          v12 = Block[0];
          if ( (unsigned __int64)(2LL * *((_QWORD *)&v18 + 1) + 2) >= 0x1000 )
          {
            v12 = (void *)*((_QWORD *)Block[0] - 1);
            if ( (unsigned __int64)((char *)Block[0] - (char *)v12 - 8) > 0x1F )
            {
              _o__invalid_parameter_noinfo_noreturn(v12, 2LL * *((_QWORD *)&v18 + 1) + 41);
              __debugbreak();
            }
          }
          operator delete(v12);
        }
        if ( v11 )
        {
          v13 = *a2;
          newString = v13;
          if ( v13 )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)v13 + 8LL))(v13);
          wprt::pt::PrintTicketProcessor::ProcessScaling(a1, &newString);
        }
      }
    }
  }
  result = WindowsDeleteString_0(string);
  v15 = string;
  if ( !result )
    v15 = 0;
  string = v15;
  if ( *a2 )
    result = (*(__int64 (__fastcall **)(HSTRING))(*(_QWORD *)*a2 + 16LL))(*a2);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180006660  mov     [rsp-18h+arg_10], rbx
0x180006665  mov     [rsp-18h+arg_18], rsi
0x18000666a  push    rbp
0x18000666b  push    rdi
0x18000666c  push    r14
0x18000666e  mov     rbp, rsp
0x180006671  sub     rsp, 60h
0x180006675  mov     rax, cs:__security_cookie
0x18000667c  xor     rax, rsp
0x18000667f  mov     [rbp+var_8], rax
0x180006683  mov     rbx, rdx
0x180006686  mov     rdi, rcx
0x180006689  mov     [rbp+var_18], rdx
0x18000668d  xor     r14d, r14d
0x180006690  mov     [rbp+string], r14
0x180006694  mov     rcx, [rdx]
0x180006697  mov     [rbp+newString], rcx
0x18000669b  test    rcx, rcx
0x18000669e  jz      short loc_1800066AD
0x1800066a0  mov     rax, [rcx]
0x1800066a3  mov     rax, [rax+8]
0x1800066a7  call    cs:__guard_dispatch_icall_fptr
0x1800066ad  lea     rdx, [rbp+string]
0x1800066b1  lea     rcx, [rbp+newString]
0x1800066b5  call    ?GET_NAME_ATTRIBUTE_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAVSmartHstring@@@Z; GET_NAME_ATTRIBUTE_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,SmartHstring &)
0x1800066ba  test    eax, eax
0x1800066bc  jnz     loc_1800068E7
0x1800066c2  xorps   xmm0, xmm0
0x1800066c5  movups  xmmword ptr [rbp+Block], xmm0
0x1800066c9  xorps   xmm1, xmm1
0x1800066cc  movdqu  [rbp+var_28], xmm1
0x1800066d1  lea     r8d, [rax+0Dh]
0x1800066d5  lea     rdx, aPagemediasize; "PageMediaSize"
0x1800066dc  lea     rcx, [rbp+Block]
0x1800066e0  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800066e5  nop
0x1800066e6  mov     [rbp+newString], r14
0x1800066ea  lea     rdx, [rbp+newString]; newString
0x1800066ee  mov     rcx, [rbp+string]; string
0x1800066f2  call    WindowsDuplicateString_0
0x1800066f7  lea     rdx, [rbp+Block]
0x1800066fb  lea     rcx, [rbp+newString]
0x1800066ff  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006704  movzx   esi, al
0x180006707  mov     rdx, qword ptr [rbp+var_28+8]
0x18000670b  cmp     rdx, 8
0x18000670f  jb      short loc_18000674A
0x180006711  lea     rdx, ds:2[rdx*2]
0x180006719  mov     rcx, [rbp+Block]; Block
0x18000671d  mov     rax, rcx
0x180006720  cmp     rdx, 1000h
0x180006727  jb      short loc_180006745
0x180006729  add     rdx, 27h ; '''
0x18000672d  mov     rcx, [rcx-8]
0x180006731  sub     rax, rcx
0x180006734  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006738  cmp     rax, 1Fh
0x18000673c  jbe     short loc_180006745
0x18000673e  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180006744  int     3; Trap to Debugger
0x180006745  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000674a  test    sil, sil
0x18000674d  jz      short loc_180006779
0x18000674f  mov     rcx, [rbx]
0x180006752  mov     [rbp+newString], rcx
0x180006756  test    rcx, rcx
0x180006759  jz      short loc_180006768
0x18000675b  mov     rax, [rcx]
0x18000675e  mov     rax, [rax+8]
0x180006762  call    cs:__guard_dispatch_icall_fptr
0x180006768  lea     rdx, [rbp+newString]
0x18000676c  mov     rcx, rdi
0x18000676f  call    ?ProcessMediaSize@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z; wprt::pt::PrintTicketProcessor::ProcessMediaSize(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)
0x180006774  jmp     loc_1800068E7
0x180006779  xorps   xmm0, xmm0
0x18000677c  movups  xmmword ptr [rbp+Block], xmm0
0x180006780  xorps   xmm1, xmm1
0x180006783  movdqu  [rbp+var_28], xmm1
0x180006788  mov     r8d, 0Fh
0x18000678e  lea     rdx, aPageorientatio; "PageOrientation"
0x180006795  lea     rcx, [rbp+Block]
0x180006799  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000679e  nop
0x18000679f  mov     [rbp+newString], r14
0x1800067a3  lea     rdx, [rbp+newString]; newString
0x1800067a7  mov     rcx, [rbp+string]; string
0x1800067ab  call    WindowsDuplicateString_0
0x1800067b0  lea     rdx, [rbp+Block]
0x1800067b4  lea     rcx, [rbp+newString]
0x1800067b8  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x1800067bd  movzx   esi, al
0x1800067c0  mov     rdx, qword ptr [rbp+var_28+8]
0x1800067c4  cmp     rdx, 8
0x1800067c8  jb      short loc_180006803
0x1800067ca  lea     rdx, ds:2[rdx*2]
0x1800067d2  mov     rcx, [rbp+Block]; Block
0x1800067d6  mov     rax, rcx
0x1800067d9  cmp     rdx, 1000h
0x1800067e0  jb      short loc_1800067FE
0x1800067e2  add     rdx, 27h ; '''
0x1800067e6  mov     rcx, [rcx-8]
0x1800067ea  sub     rax, rcx
0x1800067ed  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800067f1  cmp     rax, 1Fh
0x1800067f5  jbe     short loc_1800067FE
0x1800067f7  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800067fd  int     3; Trap to Debugger
0x1800067fe  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006803  test    sil, sil
0x180006806  jz      short loc_180006832
0x180006808  mov     rcx, [rbx]
0x18000680b  mov     [rbp+newString], rcx
0x18000680f  test    rcx, rcx
0x180006812  jz      short loc_180006821
0x180006814  mov     rax, [rcx]
0x180006817  mov     rax, [rax+8]
0x18000681b  call    cs:__guard_dispatch_icall_fptr
0x180006821  lea     rdx, [rbp+newString]
0x180006825  mov     rcx, rdi
0x180006828  call    ?ProcessOrientation@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z; wprt::pt::PrintTicketProcessor::ProcessOrientation(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)
0x18000682d  jmp     loc_1800068E7
0x180006832  xorps   xmm0, xmm0
0x180006835  movups  xmmword ptr [rbp+Block], xmm0
0x180006839  xorps   xmm1, xmm1
0x18000683c  movdqu  [rbp+var_28], xmm1
0x180006841  mov     r8d, 0Bh
0x180006847  lea     rdx, aPagescaling; "PageScaling"
0x18000684e  lea     rcx, [rbp+Block]
0x180006852  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006857  nop
0x180006858  mov     [rbp+newString], r14
0x18000685c  lea     rdx, [rbp+newString]; newString
0x180006860  mov     rcx, [rbp+string]; string
0x180006864  call    WindowsDuplicateString_0
0x180006869  lea     rdx, [rbp+Block]
0x18000686d  lea     rcx, [rbp+newString]
0x180006871  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006876  movzx   esi, al
0x180006879  mov     rdx, qword ptr [rbp+var_28+8]
0x18000687d  cmp     rdx, 8
0x180006881  jb      short loc_1800068BC
0x180006883  lea     rdx, ds:2[rdx*2]
0x18000688b  mov     rcx, [rbp+Block]; Block
0x18000688f  mov     rax, rcx
0x180006892  cmp     rdx, 1000h
0x180006899  jb      short loc_1800068B7
0x18000689b  add     rdx, 27h ; '''
0x18000689f  mov     rcx, [rcx-8]
0x1800068a3  sub     rax, rcx
0x1800068a6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800068aa  cmp     rax, 1Fh
0x1800068ae  jbe     short loc_1800068B7
0x1800068b0  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x1800068b6  int     3; Trap to Debugger
0x1800068b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800068bc  test    sil, sil
0x1800068bf  jz      short loc_1800068E7
0x1800068c1  mov     rcx, [rbx]
0x1800068c4  mov     [rbp+newString], rcx
0x1800068c8  test    rcx, rcx
0x1800068cb  jz      short loc_1800068DA
0x1800068cd  mov     rax, [rcx]
0x1800068d0  mov     rax, [rax+8]
0x1800068d4  call    cs:__guard_dispatch_icall_fptr
0x1800068da  lea     rdx, [rbp+newString]
0x1800068de  mov     rcx, rdi
0x1800068e1  call    ?ProcessScaling@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z; wprt::pt::PrintTicketProcessor::ProcessScaling(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)
0x1800068e6  nop
0x1800068e7  mov     rcx, [rbp+string]; string
0x1800068eb  call    WindowsDeleteString_0
0x1800068f0  mov     rcx, [rbp+string]
0x1800068f4  test    eax, eax
0x1800068f6  cmovz   rcx, r14
0x1800068fa  mov     [rbp+string], rcx
0x1800068fe  mov     rcx, [rbx]
0x180006901  test    rcx, rcx
0x180006904  jz      short loc_180006913
0x180006906  mov     rax, [rcx]
0x180006909  mov     rax, [rax+10h]
0x18000690d  call    cs:__guard_dispatch_icall_fptr
0x180006913  mov     [rbx], r14
0x180006916  mov     rcx, [rbp+var_8]
0x18000691a  xor     rcx, rsp; StackCookie
0x18000691d  call    __security_check_cookie
0x180006922  lea     r11, [rsp+60h+var_s0]
0x180006927  mov     rbx, [r11+30h]
0x18000692b  mov     rsi, [r11+38h]
0x18000692f  mov     rsp, r11
0x180006932  pop     r14
0x180006934  pop     rdi
0x180006935  pop     rbp
0x180006936  retn
```
