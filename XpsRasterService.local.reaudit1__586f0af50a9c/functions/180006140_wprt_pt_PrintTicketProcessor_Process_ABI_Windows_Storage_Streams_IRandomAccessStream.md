# wprt::pt::PrintTicketProcessor::Process(ABI::Windows::Storage::Streams::IRandomAccessStream *)

- ea: `0x180006140`
- end: `0x18000664e`
- name: `?Process@PrintTicketProcessor@pt@wprt@@UEAA?AVPrintTicketData@@PEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@@Z`
- size: `1294`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, loader_planting`

## callees

- `0x180003180`
- `0x180003580`
- `0x180003d30`
- `0x180003d3c`
- `0x1800056f0`
- `0x180005eb0`
- `0x180006070`
- `0x180006140`
- `0x180006660`
- `0x1800a030f`
- `0x1800b30ec`
- `0x1800bf3b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006209`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006640`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006647`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006209`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006640`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180006647`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000621d`
- `api-ms-win-core-winrt-l1-1-0!RoActivateInstance` at `0x18000621d`

## string_xrefs

- `0x1800061a4`: `Windows.Data.Xml.Dom.XmlDocument`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
_DWORD *__fastcall wprt::pt::PrintTicketProcessor::Process(__int64 a1, _DWORD *a2, __int64 a3)
{
  int v5; // ebx
  const WCHAR *v6; // rcx
  WCHAR *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  unsigned int i; // r14d
  char v11; // bl
  WCHAR *v12; // rcx
  unsigned int j; // ebx
  char v14; // di
  WCHAR *v15; // rcx
  __int64 v16; // rdx
  HRESULT v17; // eax
  HSTRING v18; // rcx
  int v19; // r8d
  int v20; // r9d
  int v21; // r8d
  __int64 v23; // [rsp+20h] [rbp-69h] BYREF
  PCNZWCH sourceString[2]; // [rsp+28h] [rbp-61h] BYREF
  UINT32 length[4]; // [rsp+38h] [rbp-51h] BYREF
  HSTRING newString; // [rsp+48h] [rbp-41h] BYREF
  HSTRING v27; // [rsp+50h] [rbp-39h] BYREF
  HSTRING string; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v29; // [rsp+60h] [rbp-29h] BYREF
  unsigned int v30; // [rsp+64h] [rbp-25h] BYREF
  HSTRING v31; // [rsp+68h] [rbp-21h] BYREF
  __int64 v32; // [rsp+70h] [rbp-19h] BYREF
  __int64 v33; // [rsp+78h] [rbp-11h] BYREF
  __int64 v34; // [rsp+80h] [rbp-9h] BYREF
  __int64 v35; // [rsp+88h] [rbp-1h] BYREF
  __int64 v36; // [rsp+90h] [rbp+7h] BYREF
  __int64 v37; // [rsp+98h] [rbp+Fh] BYREF
  __int64 v38; // [rsp+A0h] [rbp+17h] BYREF

  v38 = 0;
  v5 = CreatePrintTicketBuffer(a3, &v38);
  v35 = 0;
  v37 = 0;
  if ( !v5 )
  {
    *(_OWORD *)sourceString = 0;
    *(_OWORD *)length = 0;
    std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Windows.Data.Xml.Dom.XmlDocument");
    string = 0;
    v6 = (const WCHAR *)sourceString;
    if ( *(_QWORD *)&length[2] >= 8u )
      v6 = sourceString[0];
    WindowsCreateString_0(v6, length[0], &string);
    if ( *(_QWORD *)&length[2] >= 8u )
    {
      v7 = (WCHAR *)sourceString[0];
      if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
      {
        v7 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
        if ( (unsigned __int64)((char *)sourceString[0] - (char *)v7 - 8) > 0x1F )
        {
          _o__invalid_parameter_noinfo_noreturn(v7, 2LL * *(_QWORD *)&length[2] + 41);
          __debugbreak();
        }
      }
      operator delete(v7);
    }
    v5 = RoActivateInstance(string, &v35);
    WindowsDeleteString_0(string);
    if ( !v5 )
    {
      v5 = (**(__int64 (__fastcall ***)(__int64, GUID *, __int64 *))v35)(
             v35,
             &GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1,
             &v37);
      if ( !v5 )
        v5 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v37 + 48LL))(v37, v38);
    }
  }
  v8 = 0;
  v34 = 0;
  v9 = 0;
  v33 = 0;
  v30 = 0;
  if ( !v5 )
  {
    if ( !(**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))v35)(
            v35,
            &GUID_1c741d59_2122_47d5_a856_83f3d4214875,
            &v34)
      && !(*(unsigned int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v34 + 88LL))(v34, &v33)
      && !(*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v33 + 48LL))(v33, &v30) )
    {
      for ( i = 0; i < v30; ++i )
      {
        string = 0;
        v32 = 0;
        v29 = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, HSTRING *))(*(_QWORD *)v33 + 56LL))(v33, i, &string) )
        {
          *(_OWORD *)sourceString = 0;
          memset(length, 0, sizeof(length));
          std::wstring::_Construct<1,wchar_t const *>(sourceString, L"PrintTicket");
          v27 = string;
          if ( string )
            (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 8LL))(string);
          v11 = NODE_NAME_MATCHES_ANY_NAMESPACE(&v27, sourceString);
          if ( *(_QWORD *)&length[2] >= 8u )
          {
            v12 = (WCHAR *)sourceString[0];
            if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
            {
              v12 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
              if ( (unsigned __int64)((char *)sourceString[0] - (char *)v12 - 8) > 0x1F )
              {
                _o__invalid_parameter_noinfo_noreturn(v12, 2LL * *(_QWORD *)&length[2] + 41);
LABEL_63:
                _o__invalid_parameter_noinfo_noreturn(v15, v16);
                JUMPOUT(0x18000664DLL);
              }
            }
            operator delete(v12);
          }
          if ( !v11
            || !(*(unsigned int (__fastcall **)(HSTRING, __int64 *))(*(_QWORD *)string + 88LL))(string, &v32)
            && !(*(unsigned int (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 48LL))(v32, &v29) )
          {
            for ( j = 0; j < v29; ++j )
            {
              v36 = 0;
              v31 = 0;
              if ( !(*(unsigned int (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 56LL))(v32, j, &v36)
                && !(*(unsigned int (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v36 + 72LL))(v36, &v31) )
              {
                *(_OWORD *)sourceString = 0;
                memset(length, 0, sizeof(length));
                std::wstring::_Construct<1,wchar_t const *>(sourceString, L"Feature");
                newString = 0;
                WindowsDuplicateString_0(v31, &newString);
                v14 = MATCHES_ANY_NAMESPACE(&newString, sourceString);
                if ( *(_QWORD *)&length[2] >= 8u )
                {
                  v15 = (WCHAR *)sourceString[0];
                  if ( (unsigned __int64)(2LL * *(_QWORD *)&length[2] + 2) >= 0x1000 )
                  {
                    v16 = 2LL * *(_QWORD *)&length[2] + 41;
                    v15 = (WCHAR *)*((_QWORD *)sourceString[0] - 1);
                    if ( (unsigned __int64)((char *)sourceString[0] - (char *)v15 - 8) > 0x1F )
                      goto LABEL_63;
                  }
                  operator delete(v15);
                }
                if ( v14 )
                {
                  v23 = v36;
                  if ( v36 )
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 8LL))(v36);
                  wprt::pt::PrintTicketProcessor::ProcessFeature(a1, &v23);
                }
              }
              v17 = WindowsDeleteString_0(v31);
              v18 = v31;
              if ( !v17 )
                v18 = 0;
              v31 = v18;
              if ( v36 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
            }
          }
        }
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
        v32 = 0;
        if ( string )
          (*(void (__fastcall **)(HSTRING))(*(_QWORD *)string + 16LL))(string);
      }
    }
    v8 = v34;
    v9 = v33;
  }
  if ( *(_BYTE *)(a1 + 16) )
  {
    v19 = *(_DWORD *)(a1 + 8);
    *(_DWORD *)(a1 + 8) = *(_DWORD *)(a1 + 12);
    *(_DWORD *)(a1 + 12) = v19;
  }
  v20 = *(_DWORD *)(a1 + 20);
  v21 = *(_DWORD *)(a1 + 12);
  *a2 = *(_DWORD *)(a1 + 8);
  a2[1] = v21;
  a2[2] = v20;
  if ( v9 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v9 + 16LL))(v9);
    v8 = v34;
  }
  v33 = 0;
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  v34 = 0;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  v37 = 0;
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  v35 = 0;
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  return a2;
}

```

## disassembly

```asm
0x180006140  push    rbp
0x180006142  push    rbx
0x180006143  push    rsi
0x180006144  push    rdi
0x180006145  push    r12
0x180006147  push    r14
0x180006149  push    r15
0x18000614b  lea     rbp, [rsp-27h]
0x180006150  sub     rsp, 0B0h
0x180006157  mov     rax, cs:__security_cookie
0x18000615e  xor     rax, rsp
0x180006161  mov     [rbp+57h+var_38], rax
0x180006165  mov     r15, rdx
0x180006168  mov     rsi, rcx
0x18000616b  xor     r12d, r12d
0x18000616e  mov     [rbp+57h+var_40], r12
0x180006172  lea     rdx, [rbp+57h+var_40]
0x180006176  mov     rcx, r8
0x180006179  call    ?CreatePrintTicketBuffer@@YAJPEAUIRandomAccessStream@Streams@Storage@Windows@ABI@@AEAV?$SmartComPtr@UIBuffer@Streams@Storage@Windows@ABI@@@@@Z; CreatePrintTicketBuffer(ABI::Windows::Storage::Streams::IRandomAccessStream *,SmartComPtr<ABI::Windows::Storage::Streams::IBuffer> &)
0x18000617e  mov     ebx, eax
0x180006180  mov     [rbp+57h+var_58], r12
0x180006184  mov     [rbp+57h+var_48], r12
0x180006188  test    eax, eax
0x18000618a  jnz     loc_18000626A
0x180006190  xorps   xmm0, xmm0
0x180006193  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180006197  xorps   xmm1, xmm1
0x18000619a  movdqu  xmmword ptr [rbp+57h+length], xmm1
0x18000619f  lea     r8d, [r12+20h]
0x1800061a4  lea     rdx, ?RuntimeClass_Windows_Data_Xml_Dom_XmlDocument@@3QB_WB; "Windows.Data.Xml.Dom.XmlDocument"
0x1800061ab  lea     rcx, [rbp+57h+sourceString]
0x1800061af  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800061b4  mov     [rbp+57h+string], r12
0x1800061b8  lea     rcx, [rbp+57h+sourceString]
0x1800061bc  cmp     qword ptr [rbp+57h+length+8], 8
0x1800061c1  cmovnb  rcx, [rbp+57h+sourceString]; sourceString
0x1800061c6  lea     r8, [rbp+57h+string]; string
0x1800061ca  mov     edx, [rbp+57h+length]; length
0x1800061cd  call    WindowsCreateString_0
0x1800061d2  mov     rdx, qword ptr [rbp+57h+length+8]
0x1800061d6  cmp     rdx, 8
0x1800061da  jb      short loc_180006215
0x1800061dc  lea     rdx, ds:2[rdx*2]
0x1800061e4  mov     rcx, [rbp+57h+sourceString]; Block
0x1800061e8  mov     rax, rcx
0x1800061eb  cmp     rdx, 1000h
0x1800061f2  jb      short loc_180006210
0x1800061f4  add     rdx, 27h ; '''
0x1800061f8  mov     rcx, [rcx-8]
0x1800061fc  sub     rax, rcx
0x1800061ff  add     rax, 0FFFFFFFFFFFFFFF8h
0x180006203  cmp     rax, 1Fh
0x180006207  jbe     short loc_180006210
0x180006209  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18000620f  int     3; Trap to Debugger
0x180006210  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180006215  lea     rdx, [rbp+57h+var_58]
0x180006219  mov     rcx, [rbp+57h+string]
0x18000621d  call    cs:__imp_RoActivateInstance
0x180006223  mov     ebx, eax
0x180006225  mov     rcx, [rbp+57h+string]; string
0x180006229  call    WindowsDeleteString_0
0x18000622e  test    ebx, ebx
0x180006230  jnz     short loc_18000626A
0x180006232  mov     rcx, [rbp+57h+var_58]
0x180006236  mov     rax, [rcx]
0x180006239  lea     r8, [rbp+57h+var_48]
0x18000623d  lea     rdx, _GUID_5d034661_7bd8_4ad5_9ebf_81e6347263b1
0x180006244  mov     rax, [rax]
0x180006247  call    cs:__guard_dispatch_icall_fptr
0x18000624d  mov     ebx, eax
0x18000624f  test    eax, eax
0x180006251  jnz     short loc_18000626A
0x180006253  mov     rcx, [rbp+57h+var_48]
0x180006257  mov     rax, [rcx]
0x18000625a  mov     rdx, [rbp+57h+var_40]
0x18000625e  mov     rax, [rax+30h]
0x180006262  call    cs:__guard_dispatch_icall_fptr
0x180006268  mov     ebx, eax
0x18000626a  mov     rcx, r12
0x18000626d  mov     [rbp+57h+var_60], rcx
0x180006271  mov     rax, r12
0x180006274  mov     [rbp+57h+var_68], rax
0x180006278  mov     [rbp+57h+var_7C], r12d
0x18000627c  test    ebx, ebx
0x18000627e  jnz     loc_180006574
0x180006284  mov     rcx, [rbp+57h+var_58]
0x180006288  mov     rax, [rcx]
0x18000628b  lea     r8, [rbp+57h+var_60]
0x18000628f  lea     rdx, _GUID_1c741d59_2122_47d5_a856_83f3d4214875
0x180006296  mov     rax, [rax]
0x180006299  call    cs:__guard_dispatch_icall_fptr
0x18000629f  test    eax, eax
0x1800062a1  jnz     loc_18000656C
0x1800062a7  mov     rcx, [rbp+57h+var_60]
0x1800062ab  mov     rax, [rcx]
0x1800062ae  lea     rdx, [rbp+57h+var_68]
0x1800062b2  mov     rax, [rax+58h]
0x1800062b6  call    cs:__guard_dispatch_icall_fptr
0x1800062bc  test    eax, eax
0x1800062be  jnz     loc_18000656C
0x1800062c4  mov     rcx, [rbp+57h+var_68]
0x1800062c8  mov     rax, [rcx]
0x1800062cb  lea     rdx, [rbp+57h+var_7C]
0x1800062cf  mov     rax, [rax+30h]
0x1800062d3  call    cs:__guard_dispatch_icall_fptr
0x1800062d9  test    eax, eax
0x1800062db  jnz     loc_18000656C
0x1800062e1  mov     r14d, r12d
0x1800062e4  cmp     [rbp+57h+var_7C], r12d
0x1800062e8  jbe     loc_18000656C
0x1800062ee  xchg    ax, ax
0x1800062f0  mov     [rbp+57h+string], r12
0x1800062f4  mov     [rbp+57h+var_70], r12
0x1800062f8  mov     [rbp+57h+var_80], r12d
0x1800062fc  mov     rcx, [rbp+57h+var_68]
0x180006300  mov     rax, [rcx]
0x180006303  lea     r8, [rbp+57h+string]
0x180006307  mov     edx, r14d
0x18000630a  mov     rax, [rax+38h]
0x18000630e  call    cs:__guard_dispatch_icall_fptr
0x180006314  test    eax, eax
0x180006316  jnz     loc_18000652E
0x18000631c  xorps   xmm0, xmm0
0x18000631f  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x180006323  mov     qword ptr [rbp+57h+length], r12
0x180006327  mov     qword ptr [rbp+57h+length+8], r12
0x18000632b  lea     r8d, [rax+0Bh]
0x18000632f  lea     rdx, aPrintticket; "PrintTicket"
0x180006336  lea     rcx, [rbp+57h+sourceString]
0x18000633a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x18000633f  nop
0x180006340  mov     rcx, [rbp+57h+string]
0x180006344  mov     [rbp+57h+var_90], rcx
0x180006348  test    rcx, rcx
0x18000634b  jz      short loc_18000635A
0x18000634d  mov     rax, [rcx]
0x180006350  mov     rax, [rax+8]
0x180006354  call    cs:__guard_dispatch_icall_fptr
0x18000635a  lea     rdx, [rbp+57h+sourceString]
0x18000635e  lea     rcx, [rbp+57h+var_90]
0x180006362  call    ?NODE_NAME_MATCHES_ANY_NAMESPACE@@YA_NV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; NODE_NAME_MATCHES_ANY_NAMESPACE(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>,std::wstring const &)
0x180006367  movzx   ebx, al
0x18000636a  mov     rdx, qword ptr [rbp+57h+length+8]
0x18000636e  cmp     rdx, 8
0x180006372  jb      short loc_1800063AA
0x180006374  lea     rdx, ds:2[rdx*2]
0x18000637c  mov     rcx, [rbp+57h+sourceString]
0x180006380  mov     rax, rcx
0x180006383  cmp     rdx, 1000h
0x18000638a  jb      short loc_1800063A5
0x18000638c  add     rdx, 27h ; '''
0x180006390  mov     rcx, [rcx-8]; Block
0x180006394  sub     rax, rcx
0x180006397  add     rax, 0FFFFFFFFFFFFFFF8h
0x18000639b  cmp     rax, 1Fh
0x18000639f  ja      loc_180006640
0x1800063a5  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800063aa  test    bl, bl
0x1800063ac  jz      short loc_1800063E8
0x1800063ae  mov     rcx, [rbp+57h+string]
0x1800063b2  mov     rax, [rcx]
0x1800063b5  lea     rdx, [rbp+57h+var_70]
0x1800063b9  mov     rax, [rax+58h]
0x1800063bd  call    cs:__guard_dispatch_icall_fptr
0x1800063c3  test    eax, eax
0x1800063c5  jnz     loc_18000652E
0x1800063cb  mov     rcx, [rbp+57h+var_70]
0x1800063cf  mov     rax, [rcx]
0x1800063d2  lea     rdx, [rbp+57h+var_80]
0x1800063d6  mov     rax, [rax+30h]
0x1800063da  call    cs:__guard_dispatch_icall_fptr
0x1800063e0  test    eax, eax
0x1800063e2  jnz     loc_18000652E
0x1800063e8  mov     ebx, r12d
0x1800063eb  cmp     [rbp+57h+var_80], ebx
0x1800063ee  jbe     loc_18000652E
0x1800063f4  nop     dword ptr [rax+00h]
0x1800063f8  nop     dword ptr [rax+rax+00000000h]
0x180006400  mov     [rbp+57h+var_50], r12
0x180006404  mov     [rbp+57h+var_78], r12
0x180006408  mov     rcx, [rbp+57h+var_70]
0x18000640c  mov     rax, [rcx]
0x18000640f  lea     r8, [rbp+57h+var_50]
0x180006413  mov     edx, ebx
0x180006415  mov     rax, [rax+38h]
0x180006419  call    cs:__guard_dispatch_icall_fptr
0x18000641f  test    eax, eax
0x180006421  jnz     loc_1800064F5
0x180006427  mov     rcx, [rbp+57h+var_50]
0x18000642b  mov     rax, [rcx]
0x18000642e  lea     rdx, [rbp+57h+var_78]
0x180006432  mov     rax, [rax+48h]
0x180006436  call    cs:__guard_dispatch_icall_fptr
0x18000643c  test    eax, eax
0x18000643e  jnz     loc_1800064F5
0x180006444  xorps   xmm0, xmm0
0x180006447  movups  xmmword ptr [rbp+57h+sourceString], xmm0
0x18000644b  mov     qword ptr [rbp+57h+length], r12
0x18000644f  mov     qword ptr [rbp+57h+length+8], r12
0x180006453  lea     r8d, [rax+7]
0x180006457  lea     rdx, aFeature; "Feature"
0x18000645e  lea     rcx, [rbp+57h+sourceString]
0x180006462  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180006467  nop
0x180006468  mov     [rbp+57h+newString], r12
0x18000646c  lea     rdx, [rbp+57h+newString]; newString
0x180006470  mov     rcx, [rbp+57h+var_78]; string
0x180006474  call    WindowsDuplicateString_0
0x180006479  lea     rdx, [rbp+57h+sourceString]
0x18000647d  lea     rcx, [rbp+57h+newString]
0x180006481  call    ?MATCHES_ANY_NAMESPACE@@YA_NVSmartHstring@@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; MATCHES_ANY_NAMESPACE(SmartHstring,std::wstring const &)
0x180006486  movzx   edi, al
0x180006489  mov     rdx, qword ptr [rbp+57h+length+8]
0x18000648d  cmp     rdx, 8
0x180006491  jb      short loc_1800064C9
0x180006493  lea     rdx, ds:2[rdx*2]
0x18000649b  mov     rcx, [rbp+57h+sourceString]
0x18000649f  mov     rax, rcx
0x1800064a2  cmp     rdx, 1000h
0x1800064a9  jb      short loc_1800064C4
0x1800064ab  add     rdx, 27h ; '''
0x1800064af  mov     rcx, [rcx-8]; Block
0x1800064b3  sub     rax, rcx
0x1800064b6  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800064ba  cmp     rax, 1Fh
0x1800064be  ja      loc_180006647
0x1800064c4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800064c9  test    dil, dil
0x1800064cc  jz      short loc_1800064F5
0x1800064ce  mov     rcx, [rbp+57h+var_50]
0x1800064d2  mov     [rbp+57h+var_C0], rcx
0x1800064d6  test    rcx, rcx
0x1800064d9  jz      short loc_1800064E8
0x1800064db  mov     rax, [rcx]
0x1800064de  mov     rax, [rax+8]
0x1800064e2  call    cs:__guard_dispatch_icall_fptr
0x1800064e8  lea     rdx, [rbp+57h+var_C0]
0x1800064ec  mov     rcx, rsi
0x1800064ef  call    ?ProcessFeature@PrintTicketProcessor@pt@wprt@@AEAAXV?$SmartComPtr@UIXmlNode@Dom@Xml@Data@Windows@ABI@@@@@Z; wprt::pt::PrintTicketProcessor::ProcessFeature(SmartComPtr<ABI::Windows::Data::Xml::Dom::IXmlNode>)
0x1800064f4  nop
0x1800064f5  mov     rcx, [rbp+57h+var_78]; string
0x1800064f9  call    WindowsDeleteString_0
0x1800064fe  mov     rcx, [rbp+57h+var_78]
0x180006502  test    eax, eax
0x180006504  cmovz   rcx, r12
0x180006508  mov     [rbp+57h+var_78], rcx
0x18000650c  mov     rcx, [rbp+57h+var_50]
0x180006510  test    rcx, rcx
0x180006513  jz      short loc_180006523
0x180006515  mov     rax, [rcx]
0x180006518  mov     rax, [rax+10h]
0x18000651c  call    cs:__guard_dispatch_icall_fptr
0x180006522  nop
0x180006523  inc     ebx
0x180006525  cmp     ebx, [rbp+57h+var_80]
0x180006528  jb      loc_180006400
0x18000652e  mov     rcx, [rbp+57h+var_70]
0x180006532  test    rcx, rcx
0x180006535  jz      short loc_180006544
0x180006537  mov     rax, [rcx]
0x18000653a  mov     rax, [rax+10h]
0x18000653e  call    cs:__guard_dispatch_icall_fptr
0x180006544  mov     [rbp+57h+var_70], r12
0x180006548  mov     rcx, [rbp+57h+string]
0x18000654c  test    rcx, rcx
0x18000654f  jz      short loc_18000655F
0x180006551  mov     rax, [rcx]
0x180006554  mov     rax, [rax+10h]
0x180006558  call    cs:__guard_dispatch_icall_fptr
0x18000655e  nop
0x18000655f  inc     r14d
0x180006562  cmp     r14d, [rbp+57h+var_7C]
0x180006566  jb      loc_1800062F0
0x18000656c  mov     rcx, [rbp+57h+var_60]
0x180006570  mov     rax, [rbp+57h+var_68]
0x180006574  cmp     byte ptr [rsi+10h], 0
0x180006578  jz      short loc_180006588
0x18000657a  mov     r8d, [rsi+8]
0x18000657e  mov     edx, [rsi+0Ch]
0x180006581  mov     [rsi+8], edx
0x180006584  mov     [rsi+0Ch], r8d
0x180006588  mov     r9d, [rsi+14h]
0x18000658c  mov     r8d, [rsi+0Ch]
0x180006590  mov     edx, [rsi+8]
0x180006593  mov     [r15], edx
0x180006596  mov     [r15+4], r8d
0x18000659a  mov     [r15+8], r9d
0x18000659e  test    rax, rax
0x1800065a1  jz      short loc_1800065BA
0x1800065a3  mov     rcx, [rax]
0x1800065a6  mov     rdx, [rcx+10h]
0x1800065aa  mov     rcx, rax
0x1800065ad  mov     rax, rdx
0x1800065b0  call    cs:__guard_dispatch_icall_fptr
0x1800065b6  mov     rcx, [rbp+57h+var_60]
0x1800065ba  mov     [rbp+57h+var_68], r12
0x1800065be  test    rcx, rcx
0x1800065c1  jz      short loc_1800065D0
0x1800065c3  mov     rax, [rcx]
  ... truncated ...
```
