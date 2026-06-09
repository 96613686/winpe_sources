# wprt::pt::PrintTicketProcessor::ProcessMediaSize(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)

- ea: `0x180006940`
- end: `0x180006dd3`
- name: `?ProcessMediaSize@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z`
- size: `1171`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006660`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d3c`
- `0x180005970`
- `0x180005b80`
- `0x180005eb0`
- `0x180006070`
- `0x180006940`
- `0x1800a030f`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dbe`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dc5`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dcc`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dbe`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dc5`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006dcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall wprt::pt::PrintTicketProcessor::ProcessMediaSize(__int64 a1, _QWORD *a2)
{
  unsigned int i; // r14d
  char v5; // bl
  void *v6; // rcx
  unsigned int j; // edi
  char v8; // bl
  void *v9; // rcx
  __int64 v10; // rdx
  char v11; // bl
  void *v12; // rcx
  HRESULT v13; // eax
  HSTRING v14; // rcx
  HRESULT v15; // eax
  HSTRING v16; // rcx
  __int64 v17; // [rsp+20h] [rbp-59h] BYREF
  __int128 v18; // [rsp+28h] [rbp-51h] BYREF
  __int64 v19; // [rsp+38h] [rbp-41h]
  unsigned __int64 v20; // [rsp+40h] [rbp-39h]
  int v21; // [rsp+48h] [rbp-31h] BYREF
  int v22; // [rsp+4Ch] [rbp-2Dh] BYREF
  HSTRING newString; // [rsp+50h] [rbp-29h] BYREF
  HSTRING v24; // [rsp+58h] [rbp-21h] BYREF
  _QWORD v25[2]; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v26; // [rsp+70h] [rbp-9h] BYREF
  unsigned int v27; // [rsp+74h] [rbp-5h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  __int64 v29; // [rsp+80h] [rbp+7h] BYREF
  __int64 v30; // [rsp+88h] [rbp+Fh] BYREF
  __int64 v31; // [rsp+90h] [rbp+17h] BYREF
  HSTRING v32; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v33; // [rsp+A0h] [rbp+27h] BYREF

  v25[1] = a2;
  v31 = 0;
  v27 = 0;
  if ( !(*(unsigned int (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 88LL))(*a2, &v31)
    && !(*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v31 + 48LL))(v31, &v27) )
  {
    for ( i = 0; i < v27; ++i )
    {
      v33 = 0;
      v30 = 0;
      v26 = 0;
      if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v31 + 56LL))(v31, i, &v33) )
      {
        v18 = 0;
        v19 = 0;
        v20 = 0;
        std::wstring::_Construct<1,wchar_t const *>(&v18, L"Option");
        v25[0] = v33;
        if ( v33 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 8LL))(v33);
        v5 = NODE_NAME_MATCHES_ANY_NAMESPACE(v25, &v18);
        if ( v20 >= 8 )
        {
          v6 = (void *)v18;
          if ( 2 * v20 + 2 >= 0x1000 )
          {
            v6 = *(void **)(v18 - 8);
            if ( (unsigned __int64)(v18 - (_QWORD)v6 - 8) > 0x1F )
            {
              _o__invalid_parameter_noinfo_noreturn(v6, 2 * v20 + 41);
LABEL_56:
              _o__invalid_parameter_noinfo_noreturn(v9, v10);
              __debugbreak();
            }
          }
          operator delete(v6);
        }
        if ( !v5
          || !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v33 + 88LL))(v33, &v30)
          && !(*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v30 + 48LL))(v30, &v26) )
        {
          for ( j = 0; j < v26; ++j )
          {
            v29 = 0;
            v32 = 0;
            string = 0;
            if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v30 + 56LL))(v30, j, &v29)
              && !(*(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v29 + 72LL))(v29, &v32) )
            {
              v17 = v29;
              if ( v29 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
              if ( !(unsigned int)GET_NAME_ATTRIBUTE_VALUE(&v17, &string) )
              {
                v18 = 0;
                v19 = 0;
                v20 = 0;
                std::wstring::_Construct<1,wchar_t const *>(&v18, L"MediaSizeWidth");
                newString = 0;
                WindowsDuplicateString_0(string, &newString);
                v8 = MATCHES_ANY_NAMESPACE(&newString, &v18);
                if ( v20 >= 8 )
                {
                  v9 = (void *)v18;
                  if ( 2 * v20 + 2 >= 0x1000 )
                  {
                    v10 = 2 * v20 + 41;
                    v9 = *(void **)(v18 - 8);
                    if ( (unsigned __int64)(v18 - (_QWORD)v9 - 8) > 0x1F )
                      goto LABEL_56;
                  }
                  operator delete(v9);
                }
                if ( v8 )
                {
                  v17 = v29;
                  if ( v29 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
                  if ( !(unsigned int)GET_INTEGER_PROPERTY_VALUE(&v17, &v21) )
                    *(_DWORD *)(a1 + 8) = v21;
                }
                else
                {
                  v18 = 0;
                  v19 = 0;
                  v20 = 0;
                  std::wstring::_Construct<1,wchar_t const *>(&v18, L"MediaSizeHeight");
                  v24 = 0;
                  WindowsDuplicateString_0(string, &v24);
                  v11 = MATCHES_ANY_NAMESPACE(&v24, &v18);
                  if ( v20 >= 8 )
                  {
                    v12 = (void *)v18;
                    if ( 2 * v20 + 2 >= 0x1000 )
                    {
                      v12 = *(void **)(v18 - 8);
                      if ( (unsigned __int64)(v18 - (_QWORD)v12 - 8) > 0x1F )
                      {
                        _o__invalid_parameter_noinfo_noreturn(v12, 2 * v20 + 41);
                        JUMPOUT(0x180006DD2LL);
                      }
                    }
                    operator delete(v12);
                  }
                  if ( v11 )
                  {
                    v17 = v29;
                    if ( v29 )
                      (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
                    if ( !(unsigned int)GET_INTEGER_PROPERTY_VALUE(&v17, &v22) )
                      *(_DWORD *)(a1 + 12) = v22;
                  }
                }
              }
            }
            v13 = WindowsDeleteString_0(string);
            v14 = string;
            if ( !v13 )
              v14 = 0;
            string = v14;
            v15 = WindowsDeleteString_0(v32);
            v16 = v32;
            if ( !v15 )
              v16 = 0;
            v32 = v16;
            if ( v29 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
          }
        }
      }
      if ( v30 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
      v30 = 0;
      if ( v33 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
    }
  }
  if ( v31 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v31 + 16LL))(v31);
  v31 = 0;
  if ( *a2 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  *a2 = 0;
}

```

## disassembly

```asm
0x180006940  mov     [rsp-8+arg_10], rbx
0x180006945  mov     [rsp-8+arg_18], rsi
0x18000694a  push    rbp
0x18000694b  push    rdi
0x18000694c  push    r12
0x18000694e  push    r14
0x180006950  push    r15
0x180006952  lea     rbp, [rsp-37h]
0x180006957  sub     rsp, 0B0h
0x18000695e  mov     rax, cs:__security_cookie
0x180006965  xor     rax, rsp
0x180006968  mov     [rbp+57h+var_28], rax
0x18000696c  mov     r15, rdx
0x18000696f  mov     rsi, rcx
0x180006972  mov     [rbp+57h+var_68], rdx
0x180006976  xor     r12d, r12d
0x180006979  mov     [rbp+57h+var_40], r12
0x18000697d  mov     [rbp+57h+var_5C], r12d
0x180006981  mov     rcx, [rdx]
0x180006984  mov     rax, [rcx]
0x180006987  lea     rdx, [rbp+57h+var_40]
0x18000698b  mov     rax, [rax+58h]
0x18000698f  call    cs:__guard_dispatch_icall_fptr
0x180006995  test    eax, eax
0x180006997  jnz     loc_180006D64
0x18000699d  mov     rcx, [rbp+57h+var_40]
0x1800069a1  mov     rax, [rcx]
0x1800069a4  lea     rdx, [rbp+57h+var_5C]
0x1800069a8  mov     rax, [rax+30h]
0x1800069ac  call    cs:__guard_dispatch_icall_fptr
0x1800069b2  test    eax, eax
0x1800069b4  jnz     loc_180006D64
0x1800069ba  mov     r14d, r12d
0x1800069bd  cmp     [rbp+57h+var_5C], r12d
0x1800069c1  jbe     loc_180006D64
0x1800069c7  nop     word ptr [rax+rax+00000000h]
0x1800069d0  mov     [rbp+57h+var_30], r12
0x1800069d4  mov     [rbp+57h+var_48], r12
0x1800069d8  mov     [rbp+57h+var_60], r12d
0x1800069dc  mov     rcx, [rbp+57h+var_40]
0x1800069e0  mov     rax, [rcx]
0x1800069e3  lea     r8, [rbp+57h+var_30]
0x1800069e7  mov     edx, r14d
0x1800069ea  mov     rax, [rax+38h]
0x1800069ee  call    cs:__guard_dispatch_icall_fptr
0x1800069f4  test    eax, eax
0x1800069f6  jnz     loc_180006D26
0x1800069fc  xorps   xmm0, xmm0
0x1800069ff  movups  [rbp+57h+var_A8], xmm0
0x180006a03  mov     [rbp+57h+var_98], r12
0x180006a07  mov     [rbp+57h+var_90], r12
0x180006a0b  lea     r8d, [rax+6]
0x180006a0f  lea     rdx, aOption; "Option"
0x180006a16  lea     rcx, [rbp+57h+var_A8]
0x180006a1a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006a1f  nop
0x180006a20  mov     rcx, [rbp+57h+var_30]
0x180006a24  mov     [rbp+57h+var_70], rcx
0x180006a28  test    rcx, rcx
0x180006a2b  jz      short loc_180006A3A
0x180006a2d  mov     rax, [rcx]
0x180006a30  mov     rax, [rax+8]
0x180006a34  call    cs:__guard_dispatch_icall_fptr
0x180006a3a  lea     rdx, [rbp+57h+var_A8]
0x180006a3e  lea     rcx, [rbp+57h+var_70]
0x180006a42  call    ?NODE_NAME_MATCHES_ANY_NAMESPACE@@YA_NV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NODE_NAME_MATCHES_ANY_NAMESPACE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,std::wstring const &)
0x180006a47  movzx   ebx, al
0x180006a4a  mov     rdx, [rbp+57h+var_90]
0x180006a4e  cmp     rdx, 8
0x180006a52  jb      short loc_180006A8A
0x180006a54  lea     rdx, ds:2[rdx*2]
0x180006a5c  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180006a60  mov     rax, rcx
0x180006a63  cmp     rdx, 1000h
0x180006a6a  jb      short loc_180006A85
0x180006a6c  add     rdx, 27h ; '''
0x180006a70  mov     rcx, [rcx-8]; Block
0x180006a74  sub     rax, rcx
0x180006a77  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006a7b  cmp     rax, 1Fh
0x180006a7f  ja      loc_180006DBE
0x180006a85  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006a8a  test    bl, bl
0x180006a8c  jz      short loc_180006AC8
0x180006a8e  mov     rcx, [rbp+57h+var_30]
0x180006a92  mov     rax, [rcx]
0x180006a95  lea     rdx, [rbp+57h+var_48]
0x180006a99  mov     rax, [rax+58h]
0x180006a9d  call    cs:__guard_dispatch_icall_fptr
0x180006aa3  test    eax, eax
0x180006aa5  jnz     loc_180006D26
0x180006aab  mov     rcx, [rbp+57h+var_48]
0x180006aaf  mov     rax, [rcx]
0x180006ab2  lea     rdx, [rbp+57h+var_60]
0x180006ab6  mov     rax, [rax+30h]
0x180006aba  call    cs:__guard_dispatch_icall_fptr
0x180006ac0  test    eax, eax
0x180006ac2  jnz     loc_180006D26
0x180006ac8  mov     edi, r12d
0x180006acb  cmp     [rbp+57h+var_60], r12d
0x180006acf  jbe     loc_180006D26
0x180006ad5  nop     word ptr [rax+rax+00000000h]
0x180006ae0  mov     [rbp+57h+var_50], r12
0x180006ae4  mov     [rbp+57h+var_38], r12
0x180006ae8  mov     [rbp+57h+string], r12
0x180006aec  mov     rcx, [rbp+57h+var_48]
0x180006af0  mov     rax, [rcx]
0x180006af3  lea     r8, [rbp+57h+var_50]
0x180006af7  mov     edx, edi
0x180006af9  mov     rax, [rax+38h]
0x180006afd  call    cs:__guard_dispatch_icall_fptr
0x180006b03  test    eax, eax
0x180006b05  jnz     loc_180006CD6
0x180006b0b  mov     rcx, [rbp+57h+var_50]
0x180006b0f  mov     rax, [rcx]
0x180006b12  lea     rdx, [rbp+57h+var_38]
0x180006b16  mov     rax, [rax+48h]
0x180006b1a  call    cs:__guard_dispatch_icall_fptr
0x180006b20  test    eax, eax
0x180006b22  jnz     loc_180006CD6
0x180006b28  mov     rcx, [rbp+57h+var_50]
0x180006b2c  mov     [rbp+57h+var_B0], rcx
0x180006b30  test    rcx, rcx
0x180006b33  jz      short loc_180006B42
0x180006b35  mov     rax, [rcx]
0x180006b38  mov     rax, [rax+8]
0x180006b3c  call    cs:__guard_dispatch_icall_fptr
0x180006b42  lea     rdx, [rbp+57h+string]
0x180006b46  lea     rcx, [rbp+57h+var_B0]
0x180006b4a  call    ?GET_NAME_ATTRIBUTE_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAVSmartHstring@@@Z; GET_NAME_ATTRIBUTE_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,SmartHstring &)
0x180006b4f  test    eax, eax
0x180006b51  jnz     loc_180006CD6
0x180006b57  xorps   xmm0, xmm0
0x180006b5a  movups  [rbp+57h+var_A8], xmm0
0x180006b5e  mov     [rbp+57h+var_98], r12
0x180006b62  mov     [rbp+57h+var_90], r12
0x180006b66  lea     r8d, [rax+0Eh]
0x180006b6a  lea     rdx, aMediasizewidth; "MediaSizeWidth"
0x180006b71  lea     rcx, [rbp+57h+var_A8]
0x180006b75  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006b7a  nop
0x180006b7b  mov     [rbp+57h+newString], r12
0x180006b7f  lea     rdx, [rbp+57h+newString]; newString
0x180006b83  mov     rcx, [rbp+57h+string]; string
0x180006b87  call    WindowsDuplicateString_0
0x180006b8c  lea     rdx, [rbp+57h+var_A8]
0x180006b90  lea     rcx, [rbp+57h+newString]
0x180006b94  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006b99  movzx   ebx, al
0x180006b9c  mov     rdx, [rbp+57h+var_90]
0x180006ba0  cmp     rdx, 8
0x180006ba4  jb      short loc_180006BDC
0x180006ba6  lea     rdx, ds:2[rdx*2]
0x180006bae  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180006bb2  mov     rax, rcx
0x180006bb5  cmp     rdx, 1000h
0x180006bbc  jb      short loc_180006BD7
0x180006bbe  add     rdx, 27h ; '''
0x180006bc2  mov     rcx, [rcx-8]; Block
0x180006bc6  sub     rax, rcx
0x180006bc9  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006bcd  cmp     rax, 1Fh
0x180006bd1  ja      loc_180006DC5
0x180006bd7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006bdc  test    bl, bl
0x180006bde  jz      short loc_180006C1A
0x180006be0  mov     rcx, [rbp+57h+var_50]
0x180006be4  mov     [rbp+57h+var_B0], rcx
0x180006be8  test    rcx, rcx
0x180006beb  jz      short loc_180006BFA
0x180006bed  mov     rax, [rcx]
0x180006bf0  mov     rax, [rax+8]
0x180006bf4  call    cs:__guard_dispatch_icall_fptr
0x180006bfa  lea     rdx, [rbp+57h+var_88]
0x180006bfe  lea     rcx, [rbp+57h+var_B0]
0x180006c02  call    ?GET_INTEGER_PROPERTY_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAH@Z; GET_INTEGER_PROPERTY_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,int &)
0x180006c07  test    eax, eax
0x180006c09  jnz     loc_180006CD6
0x180006c0f  mov     eax, [rbp+57h+var_88]
0x180006c12  mov     [rsi+8], eax
0x180006c15  jmp     loc_180006CD6
0x180006c1a  xorps   xmm0, xmm0
0x180006c1d  movups  [rbp+57h+var_A8], xmm0
0x180006c21  mov     [rbp+57h+var_98], r12
0x180006c25  mov     [rbp+57h+var_90], r12
0x180006c29  mov     r8d, 0Fh
0x180006c2f  lea     rdx, aMediasizeheigh; "MediaSizeHeight"
0x180006c36  lea     rcx, [rbp+57h+var_A8]
0x180006c3a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006c3f  nop
0x180006c40  mov     [rbp+57h+var_78], r12
0x180006c44  lea     rdx, [rbp+57h+var_78]; newString
0x180006c48  mov     rcx, [rbp+57h+string]; string
0x180006c4c  call    WindowsDuplicateString_0
0x180006c51  lea     rdx, [rbp+57h+var_A8]
0x180006c55  lea     rcx, [rbp+57h+var_78]
0x180006c59  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006c5e  movzx   ebx, al
0x180006c61  mov     rdx, [rbp+57h+var_90]
0x180006c65  cmp     rdx, 8
0x180006c69  jb      short loc_180006CA1
0x180006c6b  lea     rdx, ds:2[rdx*2]
0x180006c73  mov     rcx, qword ptr [rbp+57h+var_A8]
0x180006c77  mov     rax, rcx
0x180006c7a  cmp     rdx, 1000h
0x180006c81  jb      short loc_180006C9C
0x180006c83  add     rdx, 27h ; '''
0x180006c87  mov     rcx, [rcx-8]; Block
0x180006c8b  sub     rax, rcx
0x180006c8e  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006c92  cmp     rax, 1Fh
0x180006c96  ja      loc_180006DCC
0x180006c9c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006ca1  test    bl, bl
0x180006ca3  jz      short loc_180006CD6
0x180006ca5  mov     rcx, [rbp+57h+var_50]
0x180006ca9  mov     [rbp+57h+var_B0], rcx
0x180006cad  test    rcx, rcx
0x180006cb0  jz      short loc_180006CBF
0x180006cb2  mov     rax, [rcx]
0x180006cb5  mov     rax, [rax+8]
0x180006cb9  call    cs:__guard_dispatch_icall_fptr
0x180006cbf  lea     rdx, [rbp+57h+var_84]
0x180006cc3  lea     rcx, [rbp+57h+var_B0]
0x180006cc7  call    ?GET_INTEGER_PROPERTY_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAH@Z; GET_INTEGER_PROPERTY_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,int &)
0x180006ccc  test    eax, eax
0x180006cce  jnz     short loc_180006CD6
0x180006cd0  mov     eax, [rbp+57h+var_84]
0x180006cd3  mov     [rsi+0Ch], eax
0x180006cd6  mov     rcx, [rbp+57h+string]; string
0x180006cda  call    WindowsDeleteString_0
0x180006cdf  mov     rcx, [rbp+57h+string]
0x180006ce3  test    eax, eax
0x180006ce5  cmovz   rcx, r12
0x180006ce9  mov     [rbp+57h+string], rcx
0x180006ced  mov     rcx, [rbp+57h+var_38]; string
0x180006cf1  call    WindowsDeleteString_0
0x180006cf6  mov     rcx, [rbp+57h+var_38]
0x180006cfa  test    eax, eax
0x180006cfc  cmovz   rcx, r12
0x180006d00  mov     [rbp+57h+var_38], rcx
0x180006d04  mov     rcx, [rbp+57h+var_50]
0x180006d08  test    rcx, rcx
0x180006d0b  jz      short loc_180006D1B
0x180006d0d  mov     rax, [rcx]
0x180006d10  mov     rax, [rax+10h]
0x180006d14  call    cs:__guard_dispatch_icall_fptr
0x180006d1a  nop
0x180006d1b  inc     edi
0x180006d1d  cmp     edi, [rbp+57h+var_60]
0x180006d20  jb      loc_180006AE0
0x180006d26  mov     rcx, [rbp+57h+var_48]
0x180006d2a  test    rcx, rcx
0x180006d2d  jz      short loc_180006D3C
0x180006d2f  mov     rax, [rcx]
0x180006d32  mov     rax, [rax+10h]
0x180006d36  call    cs:__guard_dispatch_icall_fptr
0x180006d3c  mov     [rbp+57h+var_48], r12
0x180006d40  mov     rcx, [rbp+57h+var_30]
0x180006d44  test    rcx, rcx
0x180006d47  jz      short loc_180006D57
0x180006d49  mov     rax, [rcx]
0x180006d4c  mov     rax, [rax+10h]
0x180006d50  call    cs:__guard_dispatch_icall_fptr
0x180006d56  nop
0x180006d57  inc     r14d
0x180006d5a  cmp     r14d, [rbp+57h+var_5C]
0x180006d5e  jb      loc_1800069D0
0x180006d64  mov     rcx, [rbp+57h+var_40]
0x180006d68  test    rcx, rcx
0x180006d6b  jz      short loc_180006D7A
0x180006d6d  mov     rax, [rcx]
0x180006d70  mov     rax, [rax+10h]
0x180006d74  call    cs:__guard_dispatch_icall_fptr
0x180006d7a  mov     [rbp+57h+var_40], r12
0x180006d7e  mov     rcx, [r15]
0x180006d81  test    rcx, rcx
0x180006d84  jz      short loc_180006D93
0x180006d86  mov     rax, [rcx]
0x180006d89  mov     rax, [rax+10h]
0x180006d8d  call    cs:__guard_dispatch_icall_fptr
0x180006d93  mov     [r15], r12
0x180006d96  mov     rcx, [rbp+57h+var_28]
0x180006d9a  xor     rcx, rsp; StackCookie
0x180006d9d  call    __security_check_cookie
0x180006da2  lea     r11, [rsp+0D0h+var_20]
0x180006daa  mov     rbx, [r11+40h]
0x180006dae  mov     rsi, [r11+48h]
0x180006db2  mov     rsp, r11
0x180006db5  pop     r15
0x180006db7  pop     r14
0x180006db9  pop     r12
0x180006dbb  pop     rdi
0x180006dbc  pop     rbp
0x180006dbd  retn
0x180006dbe  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180006dc4  nop
0x180006dc5  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180006dcb  int     3; Trap to Debugger
0x180006dcc  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
  ... truncated ...
```
