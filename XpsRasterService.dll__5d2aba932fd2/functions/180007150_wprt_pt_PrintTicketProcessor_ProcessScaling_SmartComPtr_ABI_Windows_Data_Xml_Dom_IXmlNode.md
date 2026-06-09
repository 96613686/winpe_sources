# wprt::pt::PrintTicketProcessor::ProcessScaling(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)

- ea: `0x180007150`
- end: `0x1800076c1`
- name: `?ProcessScaling@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z`
- size: `1393`
- prototype: `HRESULT __fastcall(__int64, _QWORD *)`
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
- `0x180007150`
- `0x1800a030f`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007697`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000769e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076a5`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076ac`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076b3`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076ba`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180007697`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18000769e`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076a5`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076ac`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076b3`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x1800076ba`

## pseudocode

```c
HRESULT __fastcall wprt::pt::PrintTicketProcessor::ProcessScaling(__int64 a1, _QWORD *a2)
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
  void *v14; // rcx
  __int64 v15; // rdx
  void *v16; // rcx
  __int64 v17; // rdx
  char v18; // di
  void *v19; // rcx
  HSTRING v20; // rcx
  __int64 v21; // [rsp+20h] [rbp-E0h] BYREF
  HSTRING newString; // [rsp+28h] [rbp-D8h] BYREF
  HSTRING v23; // [rsp+30h] [rbp-D0h] BYREF
  HSTRING v24; // [rsp+38h] [rbp-C8h] BYREF
  HSTRING v25; // [rsp+40h] [rbp-C0h] BYREF
  HSTRING v26; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+68h] [rbp-98h]
  unsigned __int64 v30; // [rsp+70h] [rbp-90h]
  __int128 v31; // [rsp+78h] [rbp-88h] BYREF
  __int64 v32; // [rsp+88h] [rbp-78h]
  unsigned __int64 v33; // [rsp+90h] [rbp-70h]
  __int128 v34; // [rsp+98h] [rbp-68h] BYREF
  __int64 v35; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v36; // [rsp+B0h] [rbp-50h]
  __int128 v37; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h]
  unsigned __int64 v39; // [rsp+D0h] [rbp-30h]
  _QWORD *v40; // [rsp+D8h] [rbp-28h]
  HSTRING string; // [rsp+E0h] [rbp-20h] BYREF
  unsigned int v42; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v43; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-8h] BYREF

  v40 = a2;
  v4 = 0;
  LODWORD(v21) = 0;
  v43 = 0;
  v42 = 0;
  result = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(*(_QWORD *)*a2 + 88LL))(*a2, &v43);
  if ( !result )
  {
    result = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v43 + 48LL))(v43, &v42);
    if ( !result )
    {
      for ( i = 0; i < v42; ++i )
      {
        v44 = 0;
        string = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v43 + 56LL))(v43, i, &v44) )
        {
          v28 = 0;
          v29 = 0;
          v30 = 0;
          std::wstring::_Construct<1,wchar_t const *>(&v28, L"Option", 6);
          v27 = v44;
          if ( v44 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
          v7 = NODE_NAME_MATCHES_ANY_NAMESPACE(&v27, &v28);
          if ( v30 >= 8 )
          {
            v8 = (void *)v28;
            if ( 2 * v30 + 2 >= 0x1000 )
            {
              v8 = *(void **)(v28 - 8);
              if ( (unsigned __int64)(v28 - (_QWORD)v8 - 8) > 0x1F )
              {
                _o__invalid_parameter_noinfo_noreturn(v8, 2 * v30 + 41);
LABEL_60:
                _o__invalid_parameter_noinfo_noreturn(v10, v11);
LABEL_61:
                _o__invalid_parameter_noinfo_noreturn(v12, v13);
LABEL_62:
                _o__invalid_parameter_noinfo_noreturn(v14, v15);
LABEL_63:
                _o__invalid_parameter_noinfo_noreturn(v16, v17);
                __debugbreak();
              }
            }
            operator delete(v8);
          }
          if ( v7 )
          {
            v21 = v44;
            if ( v44 )
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 8LL))(v44);
            if ( !(unsigned int)GET_NAME_ATTRIBUTE_VALUE(&v21, &string) )
            {
              v31 = 0;
              v32 = 0;
              v33 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v31, L"FitApplicationBleedSizeToPageImageableSize", 42);
              v4 |= 1u;
              LODWORD(v21) = v4;
              newString = 0;
              WindowsDuplicateString_0(string, &newString);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&newString, &v31) )
                goto LABEL_20;
              v37 = 0;
              v38 = 0;
              v39 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v37, L"FitApplicationContentSizeToPageImageableSize", 44);
              v4 |= 2u;
              LODWORD(v21) = v4;
              v23 = 0;
              WindowsDuplicateString_0(string, &v23);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&v23, &v37) )
                goto LABEL_20;
              v34 = 0;
              v35 = 0;
              v36 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v34, L"FitApplicationMediaSizeToPageImageableSize", 42);
              v4 |= 4u;
              LODWORD(v21) = v4;
              v24 = 0;
              WindowsDuplicateString_0(string, &v24);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&v24, &v34) )
                goto LABEL_20;
              v28 = 0;
              v29 = 0;
              v30 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v28, L"FitApplicationMediaSizeToPageMediaSize", 38);
              v4 |= 8u;
              LODWORD(v21) = v4;
              v25 = 0;
              WindowsDuplicateString_0(string, &v25);
              if ( (unsigned __int8)MATCHES_ANY_NAMESPACE(&v25, &v28) )
LABEL_20:
                v9 = 1;
              else
                v9 = 0;
              if ( (v4 & 8) != 0 )
              {
                v4 &= ~8u;
                if ( v30 >= 8 )
                {
                  v10 = (void *)v28;
                  if ( 2 * v30 + 2 >= 0x1000 )
                  {
                    v11 = 2 * v30 + 41;
                    v10 = *(void **)(v28 - 8);
                    if ( (unsigned __int64)(v28 - (_QWORD)v10 - 8) > 0x1F )
                      goto LABEL_60;
                  }
                  operator delete(v10);
                }
              }
              if ( (v4 & 4) != 0 )
              {
                v4 &= ~4u;
                if ( v36 >= 8 )
                {
                  v12 = (void *)v34;
                  if ( 2 * v36 + 2 >= 0x1000 )
                  {
                    v13 = 2 * v36 + 41;
                    v12 = *(void **)(v34 - 8);
                    if ( (unsigned __int64)(v34 - (_QWORD)v12 - 8) > 0x1F )
                      goto LABEL_61;
                  }
                  operator delete(v12);
                }
              }
              if ( (v4 & 2) != 0 )
              {
                v4 &= ~2u;
                if ( v39 >= 8 )
                {
                  v14 = (void *)v37;
                  if ( 2 * v39 + 2 >= 0x1000 )
                  {
                    v15 = 2 * v39 + 41;
                    v14 = *(void **)(v37 - 8);
                    if ( (unsigned __int64)(v37 - (_QWORD)v14 - 8) > 0x1F )
                      goto LABEL_62;
                  }
                  operator delete(v14);
                }
              }
              if ( (v4 & 1) != 0 )
              {
                v4 &= ~1u;
                if ( v33 >= 8 )
                {
                  v16 = (void *)v31;
                  if ( 2 * v33 + 2 >= 0x1000 )
                  {
                    v17 = 2 * v33 + 41;
                    v16 = *(void **)(v31 - 8);
                    if ( (unsigned __int64)(v31 - (_QWORD)v16 - 8) > 0x1F )
                      goto LABEL_63;
                  }
                  operator delete(v16);
                }
              }
              if ( v9 )
                *(_DWORD *)(a1 + 20) = 1;
              v31 = 0;
              v32 = 0;
              v33 = 0;
              std::wstring::_Construct<1,wchar_t const *>(&v31, L"None", 4);
              v26 = 0;
              WindowsDuplicateString_0(string, &v26);
              v18 = MATCHES_ANY_NAMESPACE(&v26, &v31);
              if ( v33 >= 8 )
              {
                v19 = (void *)v31;
                if ( 2 * v33 + 2 >= 0x1000 )
                {
                  v19 = *(void **)(v31 - 8);
                  if ( (unsigned __int64)(v31 - (_QWORD)v19 - 8) > 0x1F )
                  {
                    _o__invalid_parameter_noinfo_noreturn(v19, 2 * v33 + 41);
                    JUMPOUT(0x1800076C0LL);
                  }
                }
                operator delete(v19);
              }
              if ( v18 )
                *(_DWORD *)(a1 + 20) = 2;
            }
          }
        }
        result = WindowsDeleteString_0(string);
        v20 = string;
        if ( !result )
          v20 = 0;
        string = v20;
        if ( v44 )
          result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
      }
    }
  }
  if ( v43 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
  v43 = 0;
  if ( *a2 )
    result = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*a2 + 16LL))(*a2);
  *a2 = 0;
  return result;
}

```

## disassembly

```asm
0x180007150  mov     [rsp-8+arg_10], rbx
0x180007155  mov     [rsp-8+arg_18], rsi
0x18000715a  push    rbp
0x18000715b  push    rdi
0x18000715c  push    r12
0x18000715e  push    r14
0x180007160  push    r15
0x180007162  lea     rbp, [rsp-10h]
0x180007167  sub     rsp, 110h
0x18000716e  mov     rax, cs:__security_cookie
0x180007175  xor     rax, rsp
0x180007178  mov     [rbp+30h+var_30], rax
0x18000717c  mov     r15, rdx
0x18000717f  mov     r14, rcx
0x180007182  mov     [rbp+30h+var_58], rdx
0x180007186  xor     r12d, r12d
0x180007189  mov     ebx, r12d
0x18000718c  mov     dword ptr [rsp+130h+var_110], ebx
0x180007190  mov     [rbp+30h+var_40], r12
0x180007194  mov     [rbp+30h+var_48], r12d
0x180007198  mov     rcx, [rdx]
0x18000719b  mov     rax, [rcx]
0x18000719e  lea     rdx, [rbp+30h+var_40]
0x1800071a2  mov     rax, [rax+58h]
0x1800071a6  call    cs:__guard_dispatch_icall_fptr
0x1800071ac  test    eax, eax
0x1800071ae  jnz     loc_18000763D
0x1800071b4  mov     rcx, [rbp+30h+var_40]
0x1800071b8  mov     rax, [rcx]
0x1800071bb  lea     rdx, [rbp+30h+var_48]
0x1800071bf  mov     rax, [rax+30h]
0x1800071c3  call    cs:__guard_dispatch_icall_fptr
0x1800071c9  test    eax, eax
0x1800071cb  jnz     loc_18000763D
0x1800071d1  mov     esi, r12d
0x1800071d4  cmp     [rbp+30h+var_48], r12d
0x1800071d8  jbe     loc_18000763D
0x1800071de  xchg    ax, ax
0x1800071e0  mov     [rbp+30h+var_38], r12
0x1800071e4  mov     [rbp+30h+string], r12
0x1800071e8  mov     rcx, [rbp+30h+var_40]
0x1800071ec  mov     rax, [rcx]
0x1800071ef  lea     r8, [rbp+30h+var_38]
0x1800071f3  mov     edx, esi
0x1800071f5  mov     rax, [rax+38h]
0x1800071f9  call    cs:__guard_dispatch_icall_fptr
0x1800071ff  test    eax, eax
0x180007201  jnz     loc_180007604
0x180007207  xorps   xmm0, xmm0
0x18000720a  movups  [rsp+130h+var_D8], xmm0
0x18000720f  mov     [rsp+130h+var_C8], r12
0x180007214  mov     [rsp+130h+var_C0], r12
0x180007219  lea     r8d, [rax+6]
0x18000721d  lea     rdx, aOption; "Option"
0x180007224  lea     rcx, [rsp+130h+var_D8]
0x180007229  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000722e  nop
0x18000722f  mov     rcx, [rbp+30h+var_38]
0x180007233  mov     [rsp+130h+var_E0], rcx
0x180007238  test    rcx, rcx
0x18000723b  jz      short loc_18000724A
0x18000723d  mov     rax, [rcx]
0x180007240  mov     rax, [rax+8]
0x180007244  call    cs:__guard_dispatch_icall_fptr
0x18000724a  lea     rdx, [rsp+130h+var_D8]
0x18000724f  lea     rcx, [rsp+130h+var_E0]
0x180007254  call    ?NODE_NAME_MATCHES_ANY_NAMESPACE@@YA_NV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NODE_NAME_MATCHES_ANY_NAMESPACE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,std::wstring const &)
0x180007259  movzx   edi, al
0x18000725c  mov     rdx, [rsp+130h+var_C0]
0x180007261  cmp     rdx, 8
0x180007265  jb      short loc_18000729E
0x180007267  lea     rdx, ds:2[rdx*2]
0x18000726f  mov     rcx, qword ptr [rsp+130h+var_D8]
0x180007274  mov     rax, rcx
0x180007277  cmp     rdx, 1000h
0x18000727e  jb      short loc_180007299
0x180007280  add     rdx, 27h ; '''
0x180007284  mov     rcx, [rcx-8]; Block
0x180007288  sub     rax, rcx
0x18000728b  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000728f  cmp     rax, 1Fh
0x180007293  ja      loc_180007697
0x180007299  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000729e  test    dil, dil
0x1800072a1  jz      loc_180007604
0x1800072a7  mov     rcx, [rbp+30h+var_38]
0x1800072ab  mov     [rsp+130h+var_110], rcx
0x1800072b0  test    rcx, rcx
0x1800072b3  jz      short loc_1800072C2
0x1800072b5  mov     rax, [rcx]
0x1800072b8  mov     rax, [rax+8]
0x1800072bc  call    cs:__guard_dispatch_icall_fptr
0x1800072c2  lea     rdx, [rbp+30h+string]
0x1800072c6  lea     rcx, [rsp+130h+var_110]
0x1800072cb  call    ?GET_NAME_ATTRIBUTE_VALUE@@YAJV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEAVSmartHstring@@@Z; GET_NAME_ATTRIBUTE_VALUE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,SmartHstring &)
0x1800072d0  test    eax, eax
0x1800072d2  jnz     loc_180007604
0x1800072d8  xorps   xmm0, xmm0
0x1800072db  movups  [rsp+130h+var_B8], xmm0
0x1800072e0  mov     [rbp+30h+var_A8], r12
0x1800072e4  mov     [rbp+30h+var_A0], r12
0x1800072e8  lea     r8d, [rax+2Ah]
0x1800072ec  lea     rdx, aFitapplication_0; "FitApplicationBleedSizeToPageImageableS"...
0x1800072f3  lea     rcx, [rsp+130h+var_B8]
0x1800072f8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800072fd  nop
0x1800072fe  or      ebx, 1
0x180007301  mov     dword ptr [rsp+130h+var_110], ebx
0x180007305  mov     [rsp+130h+newString], r12
0x18000730a  lea     rdx, [rsp+130h+newString]; newString
0x18000730f  mov     rcx, [rbp+30h+string]; string
0x180007313  call    WindowsDuplicateString_0
0x180007318  lea     rdx, [rsp+130h+var_B8]
0x18000731d  lea     rcx, [rsp+130h+newString]
0x180007322  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180007327  test    al, al
0x180007329  jnz     loc_180007433
0x18000732f  xorps   xmm0, xmm0
0x180007332  movups  [rbp+30h+var_78], xmm0
0x180007336  mov     [rbp+30h+var_68], r12
0x18000733a  mov     [rbp+30h+var_60], r12
0x18000733e  mov     r8d, 2Ch ; ','
0x180007344  lea     rdx, aFitapplication_1; "FitApplicationContentSizeToPageImageabl"...
0x18000734b  lea     rcx, [rbp+30h+var_78]
0x18000734f  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007354  nop
0x180007355  or      ebx, 2
0x180007358  mov     dword ptr [rsp+130h+var_110], ebx
0x18000735c  mov     [rsp+130h+var_100], r12
0x180007361  lea     rdx, [rsp+130h+var_100]; newString
0x180007366  mov     rcx, [rbp+30h+string]; string
0x18000736a  call    WindowsDuplicateString_0
0x18000736f  lea     rdx, [rbp+30h+var_78]
0x180007373  lea     rcx, [rsp+130h+var_100]
0x180007378  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x18000737d  test    al, al
0x18000737f  jnz     loc_180007433
0x180007385  xorps   xmm0, xmm0
0x180007388  movups  [rbp+30h+var_98], xmm0
0x18000738c  mov     [rbp+30h+var_88], r12
0x180007390  mov     [rbp+30h+var_80], r12
0x180007394  mov     r8d, 2Ah ; '*'
0x18000739a  lea     rdx, aFitapplication; "FitApplicationMediaSizeToPageImageableS"...
0x1800073a1  lea     rcx, [rbp+30h+var_98]
0x1800073a5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800073aa  nop
0x1800073ab  or      ebx, 4
0x1800073ae  mov     dword ptr [rsp+130h+var_110], ebx
0x1800073b2  mov     [rsp+130h+var_F8], r12
0x1800073b7  lea     rdx, [rsp+130h+var_F8]; newString
0x1800073bc  mov     rcx, [rbp+30h+string]; string
0x1800073c0  call    WindowsDuplicateString_0
0x1800073c5  lea     rdx, [rbp+30h+var_98]
0x1800073c9  lea     rcx, [rsp+130h+var_F8]
0x1800073ce  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x1800073d3  test    al, al
0x1800073d5  jnz     short loc_180007433
0x1800073d7  xorps   xmm0, xmm0
0x1800073da  movups  [rsp+130h+var_D8], xmm0
0x1800073df  mov     [rsp+130h+var_C8], r12
0x1800073e4  mov     [rsp+130h+var_C0], r12
0x1800073e9  mov     r8d, 26h ; '&'
0x1800073ef  lea     rdx, aFitapplication_2; "FitApplicationMediaSizeToPageMediaSize"
0x1800073f6  lea     rcx, [rsp+130h+var_D8]
0x1800073fb  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007400  nop
0x180007401  or      ebx, 8
0x180007404  mov     dword ptr [rsp+130h+var_110], ebx
0x180007408  mov     [rsp+130h+var_F0], r12
0x18000740d  lea     rdx, [rsp+130h+var_F0]; newString
0x180007412  mov     rcx, [rbp+30h+string]; string
0x180007416  call    WindowsDuplicateString_0
0x18000741b  lea     rdx, [rsp+130h+var_D8]
0x180007420  lea     rcx, [rsp+130h+var_F0]
0x180007425  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x18000742a  test    al, al
0x18000742c  jnz     short loc_180007433
0x18000742e  xor     dil, dil
0x180007431  jmp     short loc_180007436
0x180007433  mov     dil, 1
0x180007436  test    bl, 8
0x180007439  jz      short loc_180007481
0x18000743b  and     ebx, 0FFFFFFF7h
0x18000743e  mov     rdx, [rsp+130h+var_C0]
0x180007443  cmp     rdx, 8
0x180007447  jb      short loc_180007481
0x180007449  lea     rdx, ds:2[rdx*2]
0x180007451  mov     rcx, qword ptr [rsp+130h+var_D8]
0x180007456  mov     rax, rcx
0x180007459  cmp     rdx, 1000h
0x180007460  jb      short loc_18000747B
0x180007462  add     rdx, 27h ; '''
0x180007466  mov     rcx, [rcx-8]; Block
0x18000746a  sub     rax, rcx
0x18000746d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180007471  cmp     rax, 1Fh
0x180007475  ja      loc_18000769E
0x18000747b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007480  nop
0x180007481  test    bl, 4
0x180007484  jz      short loc_1800074CA
0x180007486  and     ebx, 0FFFFFFFBh
0x180007489  mov     rdx, [rbp+30h+var_80]
0x18000748d  cmp     rdx, 8
0x180007491  jb      short loc_1800074CA
0x180007493  lea     rdx, ds:2[rdx*2]
0x18000749b  mov     rcx, qword ptr [rbp+30h+var_98]
0x18000749f  mov     rax, rcx
0x1800074a2  cmp     rdx, 1000h
0x1800074a9  jb      short loc_1800074C4
0x1800074ab  add     rdx, 27h ; '''
0x1800074af  mov     rcx, [rcx-8]; Block
0x1800074b3  sub     rax, rcx
0x1800074b6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800074ba  cmp     rax, 1Fh
0x1800074be  ja      loc_1800076A5
0x1800074c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800074c9  nop
0x1800074ca  test    bl, 2
0x1800074cd  jz      short loc_180007513
0x1800074cf  and     ebx, 0FFFFFFFDh
0x1800074d2  mov     rdx, [rbp+30h+var_60]
0x1800074d6  cmp     rdx, 8
0x1800074da  jb      short loc_180007513
0x1800074dc  lea     rdx, ds:2[rdx*2]
0x1800074e4  mov     rcx, qword ptr [rbp+30h+var_78]
0x1800074e8  mov     rax, rcx
0x1800074eb  cmp     rdx, 1000h
0x1800074f2  jb      short loc_18000750D
0x1800074f4  add     rdx, 27h ; '''
0x1800074f8  mov     rcx, [rcx-8]; Block
0x1800074fc  sub     rax, rcx
0x1800074ff  add     rax, 0FFFFFFFFFFFFFFF8h
0x180007503  cmp     rax, 1Fh
0x180007507  ja      loc_1800076AC
0x18000750d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180007512  nop
0x180007513  test    bl, 1
0x180007516  jz      short loc_18000755C
0x180007518  and     ebx, 0FFFFFFFEh
0x18000751b  mov     rdx, [rbp+30h+var_A0]
0x18000751f  cmp     rdx, 8
0x180007523  jb      short loc_18000755C
0x180007525  lea     rdx, ds:2[rdx*2]
0x18000752d  mov     rcx, qword ptr [rsp+130h+var_B8]
0x180007532  mov     rax, rcx
0x180007535  cmp     rdx, 1000h
0x18000753c  jb      short loc_180007557
0x18000753e  add     rdx, 27h ; '''
0x180007542  mov     rcx, [rcx-8]; Block
0x180007546  sub     rax, rcx
0x180007549  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000754d  cmp     rax, 1Fh
0x180007551  ja      loc_1800076B3
0x180007557  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000755c  test    dil, dil
0x18000755f  jz      short loc_180007569
0x180007561  mov     dword ptr [r14+14h], 1
0x180007569  xorps   xmm0, xmm0
0x18000756c  movups  [rsp+130h+var_B8], xmm0
0x180007571  mov     [rbp+30h+var_A8], r12
0x180007575  mov     [rbp+30h+var_A0], r12
0x180007579  mov     r8d, 4
0x18000757f  lea     rdx, aNone; "None"
0x180007586  lea     rcx, [rsp+130h+var_B8]
0x18000758b  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180007590  nop
0x180007591  mov     [rsp+130h+var_E8], r12
0x180007596  lea     rdx, [rsp+130h+var_E8]; newString
0x18000759b  mov     rcx, [rbp+30h+string]; string
0x18000759f  call    WindowsDuplicateString_0
0x1800075a4  lea     rdx, [rsp+130h+var_B8]
0x1800075a9  lea     rcx, [rsp+130h+var_E8]
0x1800075ae  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x1800075b3  movzx   edi, al
0x1800075b6  mov     rdx, [rbp+30h+var_A0]
0x1800075ba  cmp     rdx, 8
0x1800075be  jb      short loc_1800075F7
0x1800075c0  lea     rdx, ds:2[rdx*2]
0x1800075c8  mov     rcx, qword ptr [rsp+130h+var_B8]
0x1800075cd  mov     rax, rcx
0x1800075d0  cmp     rdx, 1000h
0x1800075d7  jb      short loc_1800075F2
0x1800075d9  add     rdx, 27h ; '''
0x1800075dd  mov     rcx, [rcx-8]; Block
0x1800075e1  sub     rax, rcx
0x1800075e4  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800075e8  cmp     rax, 1Fh
0x1800075ec  ja      loc_1800076BA
0x1800075f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800075f7  test    dil, dil
0x1800075fa  jz      short loc_180007604
0x1800075fc  mov     dword ptr [r14+14h], 2
0x180007604  mov     rcx, [rbp+30h+string]; string
0x180007608  call    WindowsDeleteString_0
0x18000760d  mov     rcx, [rbp+30h+string]
0x180007611  test    eax, eax
0x180007613  cmovz   rcx, r12
0x180007617  mov     [rbp+30h+string], rcx
0x18000761b  mov     rcx, [rbp+30h+var_38]
  ... truncated ...
```
