# wprt::pt::PrintTicketProcessor::ProcessOrientation(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)

- ea: `0x180006de0`
- end: `0x180007142`
- name: `?ProcessOrientation@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z`
- size: `866`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180006660`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d3c`
- `0x180005b80`
- `0x180005eb0`
- `0x180006070`
- `0x180006de0`
- `0x1800a030f`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000712d`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007134`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000713b`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000712d`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007134`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000713b`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
HRESULT __fastcall wprt::pt::PrintTicketProcessor::ProcessOrientation(__int64 a1, _QWORD *a2)
{
  int v4; // ebx
  HRESULT result; // eax
  unsigned int i; // esi
  char v7; // di
  void *v8; // rcx
  char v9; // di
  void *v10; // rcx
  __int64 v11; // rdx
  void *v12; // rcx
  __int64 v13; // rdx
  HSTRING v14; // rcx
  __int64 v15; // [rsp+20h] [rbp-59h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-51h] BYREF
  HSTRING v17; // [rsp+30h] [rbp-49h] BYREF
  __int64 v18; // [rsp+38h] [rbp-41h] BYREF
  __int128 v19; // [rsp+40h] [rbp-39h] BYREF
  __int64 v20; // [rsp+50h] [rbp-29h]
  unsigned __int64 v21; // [rsp+58h] [rbp-21h]
  __int128 v22; // [rsp+60h] [rbp-19h] BYREF
  __int64 v23; // [rsp+70h] [rbp-9h]
  unsigned __int64 v24; // [rsp+78h] [rbp-1h]
  _QWORD *v25; // [rsp+80h] [rbp+7h]
  unsigned int v26; // [rsp+88h] [rbp+Fh] BYREF
  HSTRING string; // [rsp+90h] [rbp+17h] BYREF
  __int64 v28; // [rsp+98h] [rbp+1Fh] BYREF
  __int64 v29; // [rsp+A0h] [rbp+27h] BYREF

  v25 = a2;
  v4 = 0;
  LODWORD(v15) = 0;
  v28 = 0;
  v26 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 88LL))(*a2, &v28);
  if ( !result )
  {
    result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v28 + 48LL))(v28, &v26);
    if ( !result )
    {
      for ( i = 0; i < v26; ++i )
      {
        v29 = 0;
        string = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v28 + 56LL))(v28, i, &v29) )
        {
          v19 = 0;
          v20 = 0;
          v21 = 0;
          std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"Option", 6u);
          v18 = v29;
          if ( v29 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
          v7 = NODE_NAME_MATCHES_ANY_NAMESPACE(&v18, &v19);
          if ( v21 >= 8 )
          {
            v8 = (void *)v19;
            if ( 2 * v21 + 2 >= 0x1000 )
            {
              v8 = *(void **)(v19 - 8);
              if ( (unsigned __int64)(v19 - (_QWORD)v8 - 8) > 0x1F )
              {
                _o__invalid_parameter_noinfo_noreturn(v8, 2 * v21 + 41);
LABEL_42:
                _o__invalid_parameter_noinfo_noreturn(v10, v11);
LABEL_43:
                _o__invalid_parameter_noinfo_noreturn(v12, v13);
                JUMPOUT(0x180007141LL);
              }
            }
            operator delete(v8);
          }
          if ( v7 )
          {
            v15 = v29;
            if ( v29 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 8LL))(v29);
            if ( !(unsigned int)GET_NAME_ATTRIBUTE_VALUE(&v15, (__int64)&string) )
            {
              v22 = 0;
              v23 = 0;
              v24 = 0;
              std::wstring::_Construct<1,wchar_t const *>((char **)&v22, L"Landscape", 9u);
              v4 |= 1u;
              LODWORD(v15) = v4;
              newString = 0;
              WindowsDuplicateString_0(string, &newString);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&newString, &v22) )
                goto LABEL_18;
              v19 = 0;
              v20 = 0;
              v21 = 0;
              std::wstring::_Construct<1,wchar_t const *>((char **)&v19, L"ReverseLandscape", 0x10u);
              v4 |= 2u;
              LODWORD(v15) = v4;
              v17 = 0;
              WindowsDuplicateString_0(string, &v17);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&v17, &v19) )
LABEL_18:
                v9 = 1;
              else
                v9 = 0;
              if ( (v4 & 2) != 0 )
              {
                v4 &= ~2u;
                if ( v21 >= 8 )
                {
                  v10 = (void *)v19;
                  if ( 2 * v21 + 2 >= 0x1000 )
                  {
                    v11 = 2 * v21 + 41;
                    v10 = *(void **)(v19 - 8);
                    if ( (unsigned __int64)(v19 - (_QWORD)v10 - 8) > 0x1F )
                      goto LABEL_42;
                  }
                  operator delete(v10);
                }
              }
              if ( (v4 & 1) != 0 )
              {
                v4 &= ~1u;
                if ( v24 >= 8 )
                {
                  v12 = (void *)v22;
                  if ( 2 * v24 + 2 >= 0x1000 )
                  {
                    v13 = 2 * v24 + 41;
                    v12 = *(void **)(v22 - 8);
                    if ( (unsigned __int64)(v22 - (_QWORD)v12 - 8) > 0x1F )
                      goto LABEL_43;
                  }
                  operator delete(v12);
                }
              }
              if ( v9 )
                *(_BYTE *)(a1 + 16) = 1;
            }
          }
        }
        result = WindowsDeleteString_0(string);
        v14 = string;
        if ( !result )
          v14 = 0;
        string = v14;
        if ( v29 )
          result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
      }
    }
  }
  if ( v28 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
  v28 = 0;
  if ( *a2 )
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180006de0  mov     [rsp-8+arg_10], rbx
0x180006de5  mov     [rsp-8+arg_18], rsi
0x180006dea  push    rbp
0x180006deb  push    rdi
0x180006dec  push    r12
0x180006dee  push    r14
0x180006df0  push    r15
0x180006df2  lea     rbp, [rsp-37h]
0x180006df7  sub     rsp, 0B0h
0x180006dfe  mov     rax, cs:__security_cookie
0x180006e05  xor     rax, rsp
0x180006e08  mov     [rbp+57h+var_28], rax
0x180006e0c  mov     r14, rdx
0x180006e0f  mov     r15, rcx
0x180006e12  mov     [rbp+57h+var_50], rdx
0x180006e16  xor     r12d, r12d
0x180006e19  mov     ebx, r12d
0x180006e1c  mov     dword ptr [rbp+57h+var_B0], ebx
0x180006e1f  mov     [rbp+57h+var_38], r12
0x180006e23  mov     [rbp+57h+var_48], r12d
0x180006e27  mov     rcx, [rdx]
0x180006e2a  mov     rax, [rcx]
0x180006e2d  lea     rdx, [rbp+57h+var_38]
0x180006e31  mov     rax, [rax+58h]
0x180006e35  call    cs:__guard_dispatch_icall_fptr
0x180006e3b  test    eax, eax
0x180006e3d  jnz     loc_1800070D3
0x180006e43  mov     rcx, [rbp+57h+var_38]
0x180006e47  mov     rax, [rcx]
0x180006e4a  lea     rdx, [rbp+57h+var_48]
0x180006e4e  mov     rax, [rax+30h]
0x180006e52  call    cs:__guard_dispatch_icall_fptr
0x180006e58  test    eax, eax
0x180006e5a  jnz     loc_1800070D3
0x180006e60  mov     esi, r12d
0x180006e63  cmp     [rbp+57h+var_48], r12d
0x180006e67  jbe     loc_1800070D3
0x180006e6d  nop     dword ptr [rax]
0x180006e70  mov     [rbp+57h+var_30], r12
0x180006e74  mov     [rbp+57h+string], r12
0x180006e78  mov     rcx, [rbp+57h+var_38]
0x180006e7c  mov     rax, [rcx]
0x180006e7f  lea     r8, [rbp+57h+var_30]
0x180006e83  mov     edx, esi
0x180006e85  mov     rax, [rax+38h]
0x180006e89  call    cs:__guard_dispatch_icall_fptr
0x180006e8f  test    eax, eax
0x180006e91  jnz     loc_18000709A
0x180006e97  xorps   xmm0, xmm0
0x180006e9a  movups  [rbp+57h+var_90], xmm0
0x180006e9e  mov     [rbp+57h+var_80], r12
0x180006ea2  mov     [rbp+57h+var_78], r12
0x180006ea6  lea     r8d, [rax+6]
0x180006eaa  lea     rdx, aOption; "Option"
0x180006eb1  lea     rcx, [rbp+57h+var_90]
0x180006eb5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006eba  nop
0x180006ebb  mov     rcx, [rbp+57h+var_30]
0x180006ebf  mov     [rbp+57h+var_98], rcx
0x180006ec3  test    rcx, rcx
0x180006ec6  jz      short loc_180006ED5
0x180006ec8  mov     rax, [rcx]
0x180006ecb  mov     rax, [rax+8]
0x180006ecf  call    cs:__guard_dispatch_icall_fptr
0x180006ed5  lea     rdx, [rbp+57h+var_90]
0x180006ed9  lea     rcx, [rbp+57h+var_98]
0x180006edd  call    ?NODE_NAME_MATCHES_ANY_NAMESPACE@@YA_NV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NODE_NAME_MATCHES_ANY_NAMESPACE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,std::wstring const &)
0x180006ee2  movzx   edi, al
0x180006ee5  mov     rdx, [rbp+57h+var_78]
0x180006ee9  cmp     rdx, 8
0x180006eed  jb      short loc_180006F25
0x180006eef  lea     rdx, ds:2[rdx*2]
0x180006ef7  mov     rcx, qword ptr [rbp+57h+var_90]
0x180006efb  mov     rax, rcx
0x180006efe  cmp     rdx, 1000h
0x180006f05  jb      short loc_180006F20
0x180006f07  add     rdx, 27h ; '''
0x180006f0b  mov     rcx, [rcx-8]; Block
0x180006f0f  sub     rax, rcx
0x180006f12  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006f16  cmp     rax, 1Fh
0x180006f1a  ja      loc_18000712D
0x180006f20  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006f25  test    dil, dil
0x180006f28  jz      loc_18000709A
0x180006f2e  mov     rcx, [rbp+57h+var_30]
0x180006f32  mov     [rbp+57h+var_B0], rcx
0x180006f36  test    rcx, rcx
0x180006f39  jz      short loc_180006F48
0x180006f3b  mov     rax, [rcx]
0x180006f3e  mov     rax, [rax+8]
0x180006f42  call    cs:__guard_dispatch_icall_fptr
0x180006f48  lea     rdx, [rbp+57h+string]
0x180006f4c  lea     rcx, [rbp+57h+var_B0]
0x180006f50  call    ?GET_NAME_ATTRIBUTE_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAVSmartHstring@@@Z; GET_NAME_ATTRIBUTE_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,SmartHstring &)
0x180006f55  test    eax, eax
0x180006f57  jnz     loc_18000709A
0x180006f5d  xorps   xmm0, xmm0
0x180006f60  movups  [rbp+57h+var_70], xmm0
0x180006f64  mov     [rbp+57h+var_60], r12
0x180006f68  mov     [rbp+57h+var_58], r12
0x180006f6c  lea     r8d, [rax+9]
0x180006f70  lea     rdx, aLandscape; "Landscape"
0x180006f77  lea     rcx, [rbp+57h+var_70]
0x180006f7b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006f80  nop
0x180006f81  or      ebx, 1
0x180006f84  mov     dword ptr [rbp+57h+var_B0], ebx
0x180006f87  mov     [rbp+57h+newString], r12
0x180006f8b  lea     rdx, [rbp+57h+newString]; newString
0x180006f8f  mov     rcx, [rbp+57h+string]; string
0x180006f93  call    WindowsDuplicateString_0
0x180006f98  lea     rdx, [rbp+57h+var_70]
0x180006f9c  lea     rcx, [rbp+57h+newString]
0x180006fa0  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006fa5  test    al, al
0x180006fa7  jnz     short loc_180006FFC
0x180006fa9  xorps   xmm0, xmm0
0x180006fac  movups  [rbp+57h+var_90], xmm0
0x180006fb0  mov     [rbp+57h+var_80], r12
0x180006fb4  mov     [rbp+57h+var_78], r12
0x180006fb8  mov     r8d, 10h
0x180006fbe  lea     rdx, aReverselandsca; "ReverseLandscape"
0x180006fc5  lea     rcx, [rbp+57h+var_90]
0x180006fc9  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006fce  nop
0x180006fcf  or      ebx, 2
0x180006fd2  mov     dword ptr [rbp+57h+var_B0], ebx
0x180006fd5  mov     [rbp+57h+var_A0], r12
0x180006fd9  lea     rdx, [rbp+57h+var_A0]; newString
0x180006fdd  mov     rcx, [rbp+57h+string]; string
0x180006fe1  call    WindowsDuplicateString_0
0x180006fe6  lea     rdx, [rbp+57h+var_90]
0x180006fea  lea     rcx, [rbp+57h+var_A0]
0x180006fee  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006ff3  test    al, al
0x180006ff5  jnz     short loc_180006FFC
0x180006ff7  xor     dil, dil
0x180006ffa  jmp     short loc_180006FFF
0x180006ffc  mov     dil, 1
0x180006fff  test    bl, 2
0x180007002  jz      short loc_180007048
0x180007004  and     ebx, 0FFFFFFFDh
0x180007007  mov     rdx, [rbp+57h+var_78]
0x18000700b  cmp     rdx, 8
0x18000700f  jb      short loc_180007048
0x180007011  lea     rdx, ds:2[rdx*2]
0x180007019  mov     rcx, qword ptr [rbp+57h+var_90]
0x18000701d  mov     rax, rcx
0x180007020  cmp     rdx, 1000h
0x180007027  jb      short loc_180007042
0x180007029  add     rdx, 27h ; '''
0x18000702d  mov     rcx, [rcx-8]; Block
0x180007031  sub     rax, rcx
0x180007034  add     rax, 0FFFFFFFFFFFFFFF8h
0x180007038  cmp     rax, 1Fh
0x18000703c  ja      loc_180007134
0x180007042  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007047  nop
0x180007048  test    bl, 1
0x18000704b  jz      short loc_180007090
0x18000704d  and     ebx, 0FFFFFFFEh
0x180007050  mov     rdx, [rbp+57h+var_58]
0x180007054  cmp     rdx, 8
0x180007058  jb      short loc_180007090
0x18000705a  lea     rdx, ds:2[rdx*2]
0x180007062  mov     rcx, qword ptr [rbp+57h+var_70]
0x180007066  mov     rax, rcx
0x180007069  cmp     rdx, 1000h
0x180007070  jb      short loc_18000708B
0x180007072  add     rdx, 27h ; '''
0x180007076  mov     rcx, [rcx-8]; Block
0x18000707a  sub     rax, rcx
0x18000707d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180007081  cmp     rax, 1Fh
0x180007085  ja      loc_18000713B
0x18000708b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007090  test    dil, dil
0x180007093  jz      short loc_18000709A
0x180007095  mov     byte ptr [r15+10h], 1
0x18000709a  mov     rcx, [rbp+57h+string]; string
0x18000709e  call    WindowsDeleteString_0
0x1800070a3  mov     rcx, [rbp+57h+string]
0x1800070a7  test    eax, eax
0x1800070a9  cmovz   rcx, r12
0x1800070ad  mov     [rbp+57h+string], rcx
0x1800070b1  mov     rcx, [rbp+57h+var_30]
0x1800070b5  test    rcx, rcx
0x1800070b8  jz      short loc_1800070C8
0x1800070ba  mov     rax, [rcx]
0x1800070bd  mov     rax, [rax+10h]
0x1800070c1  call    cs:__guard_dispatch_icall_fptr
0x1800070c7  nop
0x1800070c8  inc     esi
0x1800070ca  cmp     esi, [rbp+57h+var_48]
0x1800070cd  jb      loc_180006E70
0x1800070d3  mov     rcx, [rbp+57h+var_38]
0x1800070d7  test    rcx, rcx
0x1800070da  jz      short loc_1800070E9
0x1800070dc  mov     rax, [rcx]
0x1800070df  mov     rax, [rax+10h]
0x1800070e3  call    cs:__guard_dispatch_icall_fptr
0x1800070e9  mov     [rbp+57h+var_38], r12
0x1800070ed  mov     rcx, [r14]
0x1800070f0  test    rcx, rcx
0x1800070f3  jz      short loc_180007102
0x1800070f5  mov     rax, [rcx]
0x1800070f8  mov     rax, [rax+10h]
0x1800070fc  call    cs:__guard_dispatch_icall_fptr
0x180007102  mov     [r14], r12
0x180007105  mov     rcx, [rbp+57h+var_28]
0x180007109  xor     rcx, rsp; StackCookie
0x18000710c  call    __security_check_cookie
0x180007111  lea     r11, [rsp+0D0h+var_20]
0x180007119  mov     rbx, [r11+40h]
0x18000711d  mov     rsi, [r11+48h]
0x180007121  mov     rsp, r11
0x180007124  pop     r15
0x180007126  pop     r14
0x180007128  pop     r12
0x18000712a  pop     rdi
0x18000712b  pop     rbp
0x18000712c  retn
0x18000712d  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180007133  nop
0x180007134  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18000713a  nop
0x18000713b  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
```
